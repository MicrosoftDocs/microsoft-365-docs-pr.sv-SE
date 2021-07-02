---
title: Starta kvarhållning när en händelse inträffar
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Vanligtvis kan du som en del av en lösning för hantering av arkivhandlingar konfigurera en kvarhållningsetikett för att starta kvarhållningsperioden baserat på en händelse som du identifierar.
ms.openlocfilehash: 83f1be417b706fdb66b1df71ba351ce16d5ad485
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226629"
---
# <a name="start-retention-when-an-event-occurs"></a>Starta kvarhållning när en händelse inträffar

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

När du behåller innehåll baseras kvarhållningsperioden ofta på innehållets ålder. Du kan till exempel hålla kvar dokument i sju år efter att de har skapats och sedan ta bort dem. Men när du konfigurerar [kvarhållningsetiketter](retention.md#retention-labels) kan du också basera en kvarhållningsperiod på när en specifik typ av händelse inträffar. Händelsen utlöser start av kvarhållningsperioden, och allt innehåll med en kvarhållningsetikett för den typen av händelse tillämpad behandlas enligt etikettens kvarhållningsåtgärder.
  
Exempel på användning av händelsebaserad kvarhållning:
  
- **Anställda som lämnar organisationen** Anta att handlingar för anställda måste behållas i tio år från det att en anställd lämnar organisationen. Efter tio år måste alla dokument som är relaterade till anställning, prestanda och uppsägning av den medarbetaren förstöras. Händelsen som utlöser kvarhållningsperioden på tio år är att den anställde lämnar organisationen. 
    
- **Avtal som upphör att gälla** Anta att alla arkivhandlingar som är relaterade till avtal måste behållas i fem år från det att avtalet upphör att gälla. Den händelse som utlöser kvarhållningsperioden på fem år är avtalets upphörande. 
    
- **Produktlivslängd** Organisationen kan ha kvarhållningskrav relaterade till senaste tillverkningsdatum för produkter för innehåll som exempelvis tekniska specifikationer. I så fall är sista tillverkningsdatum den händelse som utlöser kvarhållningsperioden. 
    
Händelsebaserad kvarhållning används vanligtvis som en del av en process för hantering av arkivhandlingar. Det innebär att:
  
- Kvarhållningsetiketter baserade på händelser markerar vanligtvis också objekt som en post, som en del av en lösning för hantering av arkivhandlingar. Mer information finns i [Läs mer om hantering av arkivhandlingar](records-management.md).

- Ett dokument som har deklarerats som en post men vars händelseutlösare ännu inte har inträffat, behålls på obestämd tid (arkivhandlingar kan inte tas bort permanent) förrän en händelse utlöser dokumentets kvarhållningsperiod.
    
- Kvarhållningsetiketter baserade på händelser utlöser vanligtvis en borttagningsgranskning i slutet av kvarhållningsperioden så att den ansvariga för arkivhandlingar kan granska och förstöra innehållet manuellt. Mer information finns i [Borttagning av innehåll](disposition.md).
    

En kvarhållningsetikett som är baserad på en händelse har samma funktioner som kvarhållningsetiketter i Microsoft 365. Mer information finns i [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Förstå förhållandet mellan händelsetyper, etiketter, händelser och tillgångs-ID

Om du vill använda händelsebaserad kvarhållning är det viktigt att förstå förhållandet mellan händelsetyper, kvarhållningsetiketter, händelser och tillgångs-ID, som illustreras i diagrammen och den förklaring som följer: 
  
![Diagram 1 av 2: Händelsetyp, etiketter, händelser och tillgångs-ID](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagram 2 av 2: Händelsetyp, etiketter, händelser och tillgångs-ID](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Du skapar kvarhållningsetiketter för olika typer av innehåll och kopplar dem sedan till en typ av händelse. Kvarhållningsetiketter för olika typer av produktfiler och -poster är till exempel kopplade till en händelsetyp som heter Produktlivslängd eftersom de posterna måste behållas i tio år från det att produkten når slutet av produktens livscykel.
    
2. Användare (vanligtvis personer som hanterar arkivhandlingar) tillämpar dessa kvarhållningsetiketter på innehåll och (för dokument i SharePoint och OneDrive) anger ett tillgångs-ID för varje objekt. I det här exemplet är tillgångs-ID ett produktnamn eller en kod som används av organisationen. Varje produkts poster tilldelas sedan en kvarhållningsetikett och varje post har en egenskap som innehåller ett tillgångs-ID. Diagrammet representerar **allt innehåll** för alla produktposter i en organisation och varje objekt innehar tillgångs-ID:t för produkten som posten hör till. 
    
3. Produktlivslängd är händelsetypen. När en specifik produkt når slutet av livscykeln är det en händelse. När en händelse av den händelsetypen inträffar – i det här fallet när en produkt når slutet av sin livslängd – skapar du en händelse som anger:
    
   - Ett tillgångs-ID (för SharePoint- och OneDrive-dokument)
    
   - Nyckelord (för Exchange-objekt). I det här exemplet använder organisationen en produktkod i meddelanden som innehåller produktposter, så nyckelordet för Exchange-objekt fungerar på samma sätt som tillgångs-ID:t för SharePoint- och OneDrive-dokument.
    
   - Datumet när händelsen inträffade. Det här datumet används som start för kvarhållningsperioden. Datumet kan vara det aktuella, ett tidigare eller ett framtida datum.

4. När du har skapat en händelse synkroniseras händelsedatumet med allt innehåll som har en kvarhållningsetikett för den händelsetypen och som innehåller det angivna tillgångs-ID:t eller nyckelordet. Precis som alla kvarhållningsetiketter kan den här synkroniseringen ta upp till sju dagar. I det föregående diagrammet utlöses kvarhållningsperioden av den här händelsen för alla objekt som ringats in i rött. När produkten når slutet av sin livslängd utlöser händelsen med andra ord kvarhållningsperioden för den produktens poster.

Det är viktigt att förstå att om du inte anger ett tillgångs-ID eller nyckelord för en händelse, utlöser händelsen kvarhållningsperioden för **allt innehåll** med en etikett av den händelsetypen. Det innebär att kvarhållningen för allt innehåll i det föregående diagrammet skulle startas.. Det kanske inte är vad du avsåg.

Slutligen måste du komma ihåg att varje kvarhållningsetikett har egna kvarhållningsinställningar. I det här exemplet anges alla som tio år, men en händelse kan utlösa kvarhållningsetiketter där varje etikett har olika kvarhållningsperioder.
  
## <a name="how-to-set-up-event-driven-retention"></a>Konfigurera händelseutlöst kvarhållning

Arbetsflöde på hög nivå för händelseberoende kvarhållning:
  
![Diagram över arbetsflödet för att konfigurera händelseutlöst kvarhållning](../media/event-based-retention-process.png)
  
> [!TIP]
> I [Hantera livscykeln för dokument som lagras i SharePoint med hjälp av kvarhållningsetiketter](auto-apply-retention-labels-scenario.md) finns ett exempelscenario om hur du använder hanterade egenskaper i SharePoint för att automatiskt tillämpa kvarhållningsetiketter och implementera händelseutlöst kvarhållning.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Steg 1: Skapa en etikett vars kvarhållningstid baseras på en händelse.

Anvisningar för hur du skapar och konfigurerar kvarhållningsetiketter finns i [Skapa kvarhållningsetiketter](./create-apply-retention-labels.md#step-1-create-retention-labels). När det gäller händelsebaserad kvarhållning går du till sidan **Definiera kvarhållningsinställningar** i guiden Skapa kvarhållningsetikett. Efter **Starta kvarhållningsperioden baserat på** väljer du någon av standardhändelsetyperna i listrutan eller skapar en egen genom att välja **Skapa ny händelsetyp**:

![Skapa en ny händelsetyp för en kvarhållningsetikett](../media/SPRetention6.png)

En händelsetyp är bara en allmän beskrivning av en händelse som du vill associera med en kvarhållningsetikett.

Standardhändelsetyperna har **(händelsetyp)** efter namnet i listrutan för enklare identifiering, och du kan även visa och skapa händelsetyp från fliken **Hantering av arkivhandlingar** > **Händelser** > **Hantera händelsetyper**.

För händelsebaserad kvarhållning krävs inställningar för kvarhållning som:
  
- Behåller innehållet.
    
- Tar bort innehållet automatiskt eller utlöser en borttagningsgranskning i slutet av kvarhållningsperioden.
  
Händelsebaserad kvarhållning används vanligtvis för innehåll som deklarerar en arkivpost. Det är därför ett bra tillfälle att kontrollera om du även behöver välja det alternativ som markerar innehåll som en [post](records-management.md#records).

Om du använder en befintlig händelsetyp i stället för att skapa en ny händelsetyp går du vidare till steg 3.

> [!NOTE]
> När du väljer en händelsetyp och sparar kvarhållningsetiketten kan händelsetypen inte ändras.

### <a name="step-2-create-a-new-event-type-for-your-label"></a>Steg 2: Skapa en ny händelsetyp för en kvarhållningsetikett

Om du har valt **Skapa ny händelsetyp** anger du ett namn och en beskrivning för kvarhållningsinställningarna. Välj sedan **Nästa**, **Skicka** och **Klart**.

Tillbaka på sidan **Definiera kvarhållningsinställningar** väljer du händelsetypen som du skapade i listrutan i **Starta kvarhållningsperioden baserat på**.

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Steg 3: Publicera eller tillämpa de händelsebaserade kvarhållningsetiketterna automatiskt

Precis som för alla kvarhållningsetiketter måste du publicera eller tillämpa en händelsebaserad etikett automatiskt för att den ska kunna användas manuellt eller automatiskt på innehåll:
- [Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)
- [Använda en kvarhållningsetikett på innehåll automatiskt](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a>Steg 4: Ange ett tillgångs-ID

När en händelsebaserad etikett används på innehåll kan du ange ett tillgångs-ID för varje objekt. Din organisation kan till exempel använda:
  
- Produktkoder som du kan använda för att hålla kvar innehåll för endast en specifik produkt.
    
- Projektkoder som du kan använda för att hålla kvar innehåll för endast ett specifikt projekt.
    
- Anställnings-ID:n som du kan använda för att hålla kvar innehåll för endast en specifik person.
    
Tillgångs-ID är bara ytterligare en dokumentegenskap som är tillgänglig i SharePoint och OneDrive. Organisationen kanske redan använder andra dokumentegenskaper och ID:n för att klassificera innehåll. I så fall kan du även använda de egenskaperna och värdena när du skapar en händelse – se steg 6 som följer. Det viktiga är att du måste använda en *egenskap:värde*-kombination i dokumentegenskaperna för att associera objektet med en händelsetyp.
  
![Textruta för att ange ett tillgångs-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Steg 5: Skapa en händelse

När en viss instans av den händelsetypen inträffar, till exempel när en produkt når slutet av sin livslängd, går du till sidan **Hantering av arkivhandlingar** > **Händelser** i efterlevnadscentret för Microsoft 365 och väljer **+ Skapa** för att skapa en händelse. Du utlöser händelsen genom att skapa den här.

![Skapa en händelse för att utlösa start av kvarhållningsperioden för händelsebaserade kvarhållningsetiketter](../media/create-event-records-management.png)

Upp till en miljon händelser stöds per klientorganisation.

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Steg 6: Välj samma händelsetyp som används av etiketten i steg 2

När du skapar händelsen väljer du samma händelsetyp som anges i inställningarna för kvarhållningsetiketten i steg 2. Om du till exempel valde **Produktlivslängd** som händelsetyp för etikettinställningarna väljer du **Produktlivslängd** när du skapar händelsen. Kvarhållningsperioden utlöses bara för innehåll med kvarhållningsetiketter av den händelsetypen.

![Alternativ i Händelseinställningar för att välja en händelsetyp](../media/choose-event-type-records-management.png)

Om du behöver skapa en händelse för flera kvarhållningsetiketter som har olika händelsetyper väljer du alternativet **Välj befintliga etiketter**. Välj sedan de etiketter som är konfigurerade för de händelsetyper som du vill associera med händelsen.

### <a name="step-7-enter-keywords-or-query-for-exchange-asset-id-for-sharepoint-and-onedrive"></a>Steg 7: ange nyckelord eller fråga för Exchange, tillgångs-ID för SharePoint och OneDrive

Nu begränsar du innehålletsomfattning. För Exchange-innehåll gör du detta genom att ange nyckelord eller en fråga. För SharePoint- och OneDrive-innehåll gör du detta genom att ange tillgångs-ID:n.

För Exchange-objekt använder du nyckelord eller en fråga som använder KQL (Keyword Query Language). Mer information om frågesyntax finns i [Syntaxreferensen för KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference). Mer information om de sökbara egenskaper du kan använda för Exchange finns i [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md).

För tillgångs-ID:n kommer kvarhållning endast att tillämpas på innehåll med angiven kombination av *egenskap:värde*. Om du till exempel använder egenskapen tillgångs-ID anger du `ComplianceAssetID:<value>` i rutan för tillgångs-ID:n som visas  i följande bild.

Om ett tillgångs-ID inte anges får allt innehåll med etiketter av den händelsetypen samma kvarhållningsdatum.

Din organisation kan ha använt andra egenskaper och ID:n för dokument relaterade till den här händelsetypen. Om du till exempel behöver identifiera en specifik produkts poster kan ID:t vara en kombination av ditt anpassade produkt-ID och värdet ”XYZ”. I det här fallet anger du `ProductID:XYZ` i rutan för tillgångs-ID:n som visas i följande bild.

Välj slutligen datumet då händelsen inträffade. Det här datumet används som start för kvarhållningsperioden. När du har skapat en händelse synkroniseras händelsedatumet med allt innehåll med en kvarhållningsetikett för den händelsetypen, tillgångs-ID:t och nyckelorden eller frågor. Precis som för alla kvarhållningsetiketter kan den här synkroniseringen ta upp till sju dagar.
  
![Sidan Händelseinställningar](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

När en händelse har skapats används kvarhållningsinställningarna för innehåll som redan har etiketter och indexerats. Om kvarhållningsetiketten läggs till i nytt innehåll efter det att händelsen har skapats måste du skapa en ny händelse med samma information.

När en händelse tas bort avbryts inte kvarhållningsinställningarna som nu tillämpas för innehåll som redan har etiketter. Det gör du genom att skapa en ny händelse med samma information, men lämna datumet tomt. 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Använda innehållssökning för att hitta allt innehåll med en viss etikett eller ett visst tillgångs-ID

När kvarhållningsetiketter har tilldelats till innehåll kan du använda innehållssökning för att hitta allt innehåll som klassificeras med en specifik kvarhållningsetikett eller som innehåller ett specifikt tillgångs-ID:
  
- Om du vill söka efter allt innehåll med en specifik kvarhållningsetikett väljer du villkoret **Kvarhållningsetikett** och anger sedan hela etikettnamnet eller en del av det och använder ett jokertecken. 
    
- Om du vill hitta allt innehåll med ett specifikt tillgångs-ID anger du egenskapen **ComplianceAssetID** och ett värde med hjälp av formatet `ComplianceAssetID:<value>`. 
    
Mer information finns i [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md).

## <a name="automate-events-by-using-powershell"></a>Automatisera händelser med hjälp av PowerShell

Du kan använda ett PowerShell-skript för att automatisera händelsebaserad kvarhållning från dina affärsprogram. PowerShell-cmdletarna som är tillgängliga för händelsebaserad kvarhållning:
  
- [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [New-ComplianceRetentionEventType](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [Remove-ComplianceRetentionEventType](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [Set-ComplianceRetentionEventType](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [Get-ComplianceRetentionEvent](/powershell/module/exchange/get-complianceretentionevent)
    
- [New-ComplianceRetentionEvent](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a>Automatisera händelser med hjälp av ett REST-API

Du kan använda ett REST-API för att automatiskt skapa händelser som utlöser starten av kvarhållningsperioden.

Ett REST-API är en tjänsteslutpunkt som stöder uppsättningar av HTTP-åtgärder (metoder), som ger åtkomst till tjänstens resurser för att skapa/hämta/uppdatera/ta bort. Mer information finns i [Komponenter i en REST-API-begäran/ett REST-API-svar](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). Med hjälp av REST-API för Microsoft 365 kan händelser skapas och hämtas med hjälp av metoderna POST och GET.

Det finns två alternativ för att använda REST-API:

- **Microsoft Power Automate eller ett liknande program** för att utlösa förekomsten av en händelse automatiskt. Microsoft Power Automate är en orkestrator för anslutning till andra system, så du behöver inte skriva en anpassad lösning. Mer information finns på [webbplatsen Power Automate](https://flow.microsoft.com/sv-SE/).

- **PowerShell eller en HTTP-klient för att anropa REST-API** för att skapa händelser med hjälp av PowerShell (version 6 eller senare), som är en del av en anpassad lösning.

Innan du använder REST-API, som global administratör, bekräftar du URL-adressen som ska användas för kvarhållningshändelseanrop. Det gör du genom att köra ett GET-anrop för kvarhållningshändelse med hjälp av REST-API-URL:en:

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

Kontrollera svarskoden. Om den är 302 hämtar du den omdirigerade URL-adressen från egenskapen Plats för svarshuvudet och använder den URL-adressen i stället för `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` i anvisningarna nedan.

Händelser som skapas automatiskt kan bekräftas genom att de visas i Efterlevnadscenter för Microsoft 365 > **Hantering av arkivhandlingar** >  **Händelser**.

### <a name="use-microsoft-power-automate-to-create-the-event"></a>Använda Microsoft Power Automate för att skapa händelsen

Skapa ett flöde som skapar en händelse med hjälp av REST-API för Microsoft 365:

![Använda Flow för att skapa en händelse](../media/automate-event-driven-retention-flow-1.png)

![Använda Flow för att anropa REST-API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a>Skapa en händelse

Exempelkod som anropar REST API:et:

- **Method**: POST
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Headers**: Key = Content-Type, Value = application/atom+xml
- **Body**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- **Authentication**: Basic
- **Username**: "Complianceuser"
- **Password**: "Compliancepassword"


##### <a name="available-parameters"></a>Tillgängliga parametrar


|Parametrar|Beskrivning|Kommentar|
|--- |--- |--- |
|<d:Name></d:Name>|Ange ett unikt namn för händelsen|Får inte innehålla avslutande blanksteg eller följande tecken: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Ange namn på händelsetyp (eller GUID),|Exempel: "Uppsägning av anställd". Händelsetypen måste associeras med en kvarhållningsetikett.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Ange "ComplianceAssetId:" + anställnings-ID|Exempel: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Datum och tid för händelse|Format: åååå-MM-ddTHH:mm:ssZ, Exempel: 2018-12-01T00:00:00Z
|

###### <a name="response-codes"></a>Svarskoder

| Svarskod | Beskrivning       |
| ----------------- | --------------------- |
| 302               | Omdirigera              |
| 201               | Skapades               |
| 403               | Auktorisering misslyckades  |
| 401               | Autentisering misslyckades |

##### <a name="get-events-based-on-a-time-range"></a>Hämta händelser baserat på ett tidsintervall

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"


###### <a name="response-codes"></a>Svarskoder

| Svarskod | Beskrivning                   |
| ----------------- | --------------------------------- |
| 200               | OK, en lista över händelser i atom+ xml |
| 404               | Hittades inte                         |
| 302               | Omdirigera                          |
| 401               | Auktorisering misslyckades              |
| 403               | Autentisering misslyckades             |

##### <a name="get-an-event-by-id"></a>Hämta en händelse med hjälp av ID

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"

###### <a name="response-codes"></a>Svarskoder

| Svarskod | Beskrivning                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, svarets brödtext innehåller händelsen i atom+xml |
| 404               | Hittades inte                                            |
| 302               | Omdirigera                                             |
| 401               | Auktorisering misslyckades                                 |
| 403               | Autentisering misslyckades                                |

##### <a name="get-an-event-by-name"></a>Hämta en händelse med hjälp av namnet

- **Method**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Authentication**: Basic

- **Username**: "Complianceuser"

- **Password**: "Compliancepassword"


###### <a name="response-codes"></a>Svarskoder

| Svarskod | Beskrivning                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, svarets brödtext innehåller händelsen i atom+xml |
| 404               | Hittades inte                                            |
| 302               | Omdirigera                                             |
| 401               | Auktorisering misslyckades                                 |
| 403               | Autentisering misslyckades                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a>Använda PowerShell eller någon HTTP-klient för att skapa händelsen

PowerShell måste vara version 6 eller senare.

Kör följande skript i en PowerShell-session:

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```
