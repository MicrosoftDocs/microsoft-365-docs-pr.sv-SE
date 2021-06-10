---
title: Konfigurera en koppling för att importera fysiska data
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Administratörer kan konfigurera en dataanslutning för att importera data från organisationens fysiska badgingsystem till Microsoft 365. På så sätt kan du använda dessa data i insider-riskhanteringsprinciper för att hjälpa dig att upptäcka åtkomst till dina fysiska byggnader av specifika användare som kan ange ett internt hot mot organisationen.
ms.openlocfilehash: a300107af1d3fe07f208f7e3f239f75a9cd6e5af
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162809"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Konfigurera en koppling för att importera fysiska data (förhandsversion)

Du kan konfigurera en datakoppling i efterlevnadscentret för Microsoft 365 för att importera fysiska dåliga data, till exempel anställdas fysiska åtkomsthändelser eller fysiska åtkomsta alarm som genereras av organisationens aktivitetssystem. Exempel på fysiska åtkomstpunkter är en post till en byggnad eller en post till ett serverrum eller datacenter. Fysiska badgingdata kan användas av Microsoft 365 [](insider-risk-management.md) insider-riskhanteringslösning för att skydda organisationen från skadlig aktivitet eller datastöld i organisationen.

Konfigurera en fysisk badging-koppling består av följande uppgifter:

- Skapa en app i Azure Active Directory (Azure AD) för att få åtkomst till en API-slutpunkt som accepterar en JSON-nyttolast som innehåller fysiska data.

- Skapa JSON-nyttolasten med ett schema som definieras av fysisk badging-datakoppling.

- Skapa en fysisk badging-datakoppling i Microsoft 365 kompatibilitetscenter.

- Köra ett skript för att skicka fysiska badging-data till API-slutpunkten.

- Om du vill kan du schemalägga skriptet så att det körs automatiskt för att importera fysiska badgingdata.

## <a name="before-you-set-up-the-connector"></a>Innan du konfigurerar kopplingen

- Den användare som skapar den fysiska badgingkopplingen i steg 3 måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en ny rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

- Du måste bestämma hur du hämtar eller exporterar data från organisationens fysiska aktivitetssystem (dagligen) och skapa en JSON-fil som beskrivs i steg 2. Skriptet som du kör i Steg 4 push-push-data i JSON-filen till API-slutpunkten.

- Exempelskriptet som du kör i Steg 4 pushar fysiska feldata från JSON-filen till kopplings-API:t så att den kan användas av insider-riskhanteringslösningen. Det här exempelskriptet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskriptet ges i befintligt skick utan garantier av något slag. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, men inte begränsat till, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen vilar på dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Steg 1: Skapa en app i Azure Active Directory

Det första steget är att skapa och registrera en ny app i Azure Active Directory (Azure AD). Appen motsvarar den fysiska badgingkoppling som du skapar i steg 3. När du skapar det här programmet kan Azure AD autentisera push-begäran för JSON-nyttolast som innehåller fysiska badging-data. När den här Azure AD-appen skapas sparar du följande information. Dessa värden används i senare steg.

- Azure AD-program-ID (kallas även *app-ID* eller *klient-ID)*

- Azure AD-programhemlighet (kallas även *klienthemlighet)*

- Klientorganisations-ID (kallas även *katalog-ID*)

Stegvisa instruktioner för hur du skapar en app i Azure AD finns i [Registrera ett program med Microsofts identitetsplattform.](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Steg 2: Förbereda en JSON-fil med fysiska data

Nästa steg är att skapa en JSON-fil som innehåller information om anställdas fysiska åtkomstdata. Som förklaras i avsnittet innan du börjar måste du avgöra hur du skapar den här JSON-filen från din organisations fysiska badgingsystem.

JSON-filen måste följa schemadefinitionen som krävs av kopplingen. Här visas beskrivningar av de schemaegenskaper som krävs för JSON-filen:

|Egenskap|Beskrivning|Datatyp|
|---|---|---|
|UserId|En anställd kan ha flera digitala identiteter i systemen. Indata måste ha Azure AD-ID redan löst av källsystemet.|UPN eller e-postadress|
|AssetId|Referens-ID för den fysiska tillgången eller fysiska åtkomstpunkten.|Alfanumerisk sträng|
|Tillgångsnamn|Eget namn på den fysiska tillgången eller den fysiska åtkomstpunkten.|Alfanumerisk sträng|
|EventTime|Tidsstämpeln för åtkomst.|Datum och tid i UTC-format|
|AccessStatus|Värdet på `Success` eller `Failed`|Sträng|
|||

Här är ett exempel på en JSON-fil som överensstämmer med det obligatoriska schemat:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",
        "AccessStatus":"Success",
    }
]
```

Du kan också ladda ned följande schemadefinition för JSON-filen från guiden när du skapar den fysiska badgingkopplingen i steg 3.

```text
{
   "title" : "Physical Badging Signals",
   "description" : "Access signals from physical badging systems",
   "DataType" : {
      "description" : "Identify what is the data type for input signal",
      "type" : "string",
   },
   "type" : "object",
   "properties": {
      "UserId" : {
         "description" : "Unique identifier AAD Id resolved by the source system",
         "type" : "string",
      },
      "AssetId": {
         "description" : "Unique ID of the physical asset/access point",
         "type" : "string",
      },
      "AssetName": {
         "description" : "friendly name of the physical asset/access point",
         "type" : "string",
      },
      "EventTime" : {
         "description" : "timestamp of access",
         "type" : "string",
      },
      "AccessStatus" : {
         "description" : "what was the status of access attempt - Success/Failed",
         "type" : "string",
      },
   }
   "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Steg 3: Skapa den fysiska badgingkopplingen

Nästa steg är att skapa en fysisk badging-koppling i Microsoft 365 kompatibilitetscenter. När du har kört skriptet i steg 4 bearbetas JSON-filen som du skapade i steg 3 och skickas till API-slutpunkten som du konfigurerade i steg 1. I det här steget ska du kopiera jobb-ID:t som skapades när du skapar kopplingen. Du kommer att använda JobId när du kör skriptet.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på Datakopplingar i den vänstra **navigeringsfältet.**

2. På sidan **Datakopplingar** under **Fysisk aktivitet klickar du** på **Visa**.

3. På sidan **Fysisk aktivitet klickar du** på Lägg till **koppling**.

4. På sidan **Autentiseringsuppgifter** gör du följande och klickar sedan på **Nästa:**

   1. Skriv eller klistra in Azure AD-program-ID för Azure-appen som du skapade i steg 1.

   2. Ladda ned exempelschemat för referensen för att skapa JSON-filen.

   3. Skriv ett unikt namn för den fysiska badgingkopplingen.

5. På sidan **Granska** granskar du inställningarna och klickar sedan på **Slutför för** att skapa kopplingen.

6. En statussida visas som bekräftar att anslutningen skapades. Den här sidan innehåller även jobb-ID:t. Du kan kopiera jobb-ID från den här sidan eller från kopplingssidan. Du behöver det här jobb-ID:t när du kör skriptet.

   Statussidan innehåller även en länk till skriptet. Läs det här skriptet för att förstå hur du publicerar JSON-filen till API-slutpunkten.

7. Klicka på **Klar**.

   Den nya kopplingen visas i listan på **fliken Kopplingar.**

8. Klicka på den fysiska badgingkopplingen som du just har skapat för att visa den utfällliga sidan, som innehåller egenskaper och annan information om kopplingen.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Steg 4: Kör skriptet för att PUBLICERA JSON-filen som innehåller fysiska aktivitetsdata

Nästa steg för att konfigurera en fysisk badging-koppling är att köra ett skript som push-kör fysiska badgingdata i JSON-filen (som du skapade i steg 2) till API-slutpunkten som du skapade i steg 1. Vi tillhandahåller ett exempelskript för referensen och du kan välja att använda det eller skapa ett eget skript för att publicera JSON-filen till API-slutpunkten.

När du har kört skriptet skickas JSON-filen som innehåller fysiska data till din Microsoft 365-organisation där den kan kommas åt av insider-riskhanteringslösningen. Vi rekommenderar att du publicerar fysiska badging-data varje dag. Det kan du göra genom att automatisera processen för att generera JSON-filen varje dag från ditt fysiska badgingsystem och sedan schemalägga skriptet för att pusha data.

> [!NOTE]
> Det maximala antalet poster i JSON-filen som kan bearbetas av API:et är 50 000 poster.

1. Gå till [den GitHub webbplatsen för](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) att komma åt exempelskriptet.

2. Klicka på **knappen Raw** för att visa skriptet i textvyn

3. Kopiera alla rader i exempelskriptet och spara dem sedan i en textfil.

4. Ändra exempelskriptet för din organisation, om det behövs.

5. Spara textfilen som en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel PhysicalBadging.ps1.

6. Öppna en kommandotolk på den lokala datorn och gå till katalogen där du sparade skriptet.

7. Kör följande kommando för att skicka fysiska data i JSON-filen till Microsoft-molnet. till exempel:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   I följande tabell beskrivs de parametrar som ska användas med skriptet och deras obligatoriska värden. Informationen som du fick i föregående steg används i värdena för dessa parametrar.

   |Parameter|Beskrivning|
   |---|---|
   |tenantId|Det här är id:t för Microsoft 365 organisation som du fick i steg 1. Du kan också hämta organisationens klient-ID i **översiktsbladet** i Azure AD-administrationscentret. Används för att identifiera din organisation.|
   |appId|Det här är Azure AD-program-ID för appen som du skapade i Azure AD i steg 1. Det här används av Azure AD för autentisering när skriptet försöker komma åt din Microsoft 365 organisation.|
   |appSecret|Det här är Azure AD-programhemligheten för appen som du skapade i Azure AD i steg 1. Det här används också för autentisering.|
   |jobId|Det här är Jobb-ID för den fysiska badgingkoppling som du skapade i steg 3. Detta används för att associera fysiska data som skickas till Microsoft-molnet med den fysiska badgingkopplingen.|
   |JsonFilePath|Det här är filsökvägen på den lokala datorn (den som du använder för att köra skriptet) för JSON-filen som du skapade i steg 2. Den här filen måste följa exempelschemat som beskrivs i steg 3.|
   |||

   Här är ett exempel på syntaxen för det fysiska badging-kopplingsskriptet som använder faktiska värden för varje parameter:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Om överföringen lyckas visas följande meddelande i **skriptet Upload Lyckades.**

   Om du har flera JSON-filer måste du köra skriptet för varje fil.

> [!NOTE]
> Du kan också välja att pusha fysiska badging-data till API-slutpunkten med andra metoder än genom att köra föregående skript. Här är till exempel ett exempel för användning av Postman för att skicka data till API-slutpunkten.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Steg 5: Övervaka den fysiska anslutningen

När du har skapat den fysiska badgingkopplingen och överför dina fysiska dåliga data kan du visa anslutningen och ladda upp status i Microsoft 365 kompatibilitetscenter. Om du schemalägger skriptet så att det körs automatiskt regelbundet kan du också visa aktuell status efter den senaste gången skriptet kördes.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den fysiska anslutningen för att visa den utfällliga sidan. Den här sidan innehåller egenskaper och information om kopplingen.

   ![Utfällsida för status för fysiskt badging-koppling](..\media\PhysicalBadgingStatusFlyout.png)

3. Under **Senaste import** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om varje gång skriptet körs och laddar upp data från CSV-filen till Microsoft-molnet.

   ![Fysiskt fel i kopplingsloggfil visar antal rader från JSON-fil som har laddats upp](..\media\PhysicalBadgingConnectorLogFile.png)

   Fältet **RecordsSaved** anger antalet rader i CSV-filen som har laddats upp. Om CSV-filen till exempel innehåller fyra rader är värdet för fälten **RecordsSaved** 4, om skriptet har laddat upp alla rader i CSV-filen.

Om du inte har kört skriptet i steg 4 visas en länk för att ladda ned skriptet under **Senaste import.** Du kan ladda ned skriptet och sedan följa stegen i steg 4 för att köra det.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Valfritt) Steg 6: Schemalägga skriptet så att det körs automatiskt

Vi rekommenderar att du schemalägger skriptet så att det körs automatiskt återkommande, till exempel en gång om dagen, för att se till att de senaste fysiska badgingdata från organisationen är tillgängliga för verktyg som Insider-riskhanteringslösningen. Det här kräver också att du uppdaterar fysiska data till JSON-fil med ett liknande schema (om inte samma) så att det innehåller den senaste informationen om anställda som lämnar organisationen. Målet är att ladda upp de senaste fysiska badgingdata så att den fysiska badgingkopplingen kan göra den tillgänglig för insider-riskhanteringslösningen.

Du kan använda appen Schemaläggaren i Windows att automatiskt köra skriptet varje dag.

1. Klicka på startknappen på den Windows **datorn** och skriv sedan **Schemaläggaren**.

2. Klicka på **appen Schemaläggaren** för att öppna den.

3. Klicka på **Skapa** uppgift i **avsnittet Åtgärder.**

4. Ange ett **beskrivande** namn för den schemalagda aktiviteten på fliken Allmänt. till exempel **skript för fysiskt dåligt koppling**. Du kan också lägga till en valfri beskrivning.

5. Gör **följande under** Säkerhetsalternativ:

   1. Bestäm om skriptet endast ska köras när du är inloggad på datorn eller om det ska köras när du är inloggad eller inte.

   2. Kontrollera att kryssrutan **Kör med högst behörighet** är markerad.

6. Välj fliken **Utlösare,** klicka **på Ny** och gör sedan följande:

   1. Under **Inställningar** väljer du **alternativet** Varje dag och väljer sedan ett datum och en tid då skriptet ska köras för första gången. Skriptet körs varje dag vid samma angivna tidpunkt.

   2. Kontrollera **att kryssrutan** Aktiverad är **markerad** under Avancerade inställningar.

   3. Klicka **på OK.**

7. Välj fliken **Åtgärder,** klicka **på Ny** och gör sedan följande:

   ![Åtgärdsinställningar för att skapa en ny schemalagd aktivitet för det fysiska badging-kopplingsskriptet](..\media\SchedulePhysicalBadgingScript1.png)

   1. I **listrutan** Åtgärd kontrollerar du att Starta **ett program** är markerat.

   2. I rutan **Program/skript** klickar du på Bläddra **och** går till följande plats och väljer den så att sökvägen visas i rutan: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. I rutan **Lägg till argument (valfritt)** klistrar du in samma skriptkommando som du körde i steg 4. Exempel: .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. I rutan **Börja i (valfritt)** klistrar du in mappplatsen för skriptet som du körde i steg 4. Till exempel C:\Users\contosoadmin\Desktop\Scripts.

   5. Spara inställningarna för den nya åtgärden genom att klicka på **OK.**

8. Spara den **schemalagda aktiviteten** genom att klicka **på Ok** i fönstret Skapa aktivitet. Du kanske blir ombedd att ange dina autentiseringsuppgifter för användarkontot.

   Den nya uppgiften visas i Schemaläggarbiblioteket.

   ![Den nya uppgiften visas i Schemaläggarbiblioteket](..\media\SchedulePhysicalBadgingScript2.png)

Den senaste gången skriptet kördes och nästa gång det schemalagts att köras visas. Du kan dubbelklicka på uppgiften för att redigera den.

Du kan också verifiera den senaste gången skriptet kördes på den utfällliga sidan för motsvarande fysiska badging-koppling i efterlevnadscentret.
