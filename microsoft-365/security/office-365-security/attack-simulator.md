---
title: Angrepps Simulator i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda en angrepps Simulator för att köra simulerade nät för nätfiske och lösen ord i Microsoft 365 E5-eller Microsoft Defender för Office 365 plan 2-organisationer.
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615210"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Angrepps Simulator i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som innehåller [hot undersökningar och svars funktioner](office-365-ti.md), kan du använda angrepps simulatorn i säkerhets & Compliance Center för att köra realistiska angrepp i din organisation. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din botten linje. Läs den här artikeln om du vill veta mer.

> [!NOTE]
> Information om attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster. Mer information finns i [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).

> [!TIP]
> Utbildning för attack simulering är tillgängligt för offentlig för hands version i Microsoft 365 säkerhets Center. Ta en titt på [simulera ett nät fiske angrepp med Microsoft Defender för Office 365](attack-simulation-training.md) för mer information.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter. Angrepps simulatorn  finns i \> **angrepps** hanterings tjänsten. Gå direkt till angrepps simulatorn, öppen <https://protection.office.com/attacksimulator> .

- Mer information om tillgängligheten för angrepps enheter för olika Microsoft 365-prenumerationer finns i [Beskrivning av Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Du måste vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** . Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i angrepps Simulator. Anvisningar finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

- Nät fiske kampanjer samlar in och bearbetar händelser i 30 dagar. Historiska kampanj data kommer att vara tillgängliga i upp till 90 dagar efter att du har lanserat kampanjen.

- Det finns inga motsvarande PowerShell-cmdlets för angrepps Simulator.

## <a name="spear-phishing-campaigns"></a>Spear nät fiske kampanjer

*Nätfiske* är en generisk term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. *Spear nätfiske* är ett riktat nätfiske-angrepp som använder prioriterat och anpassat innehåll som är specifikt skräddarsydda för de riktade mottagarna (vanligt vis efter Reconnaissance på mottagarna).

I angrepps simulatorer är två olika typer av Spear nät fiske kampanjer tillgängliga:

- **Spear nätfiske (uppgifter om skörd)**: ett försök görs att få mottagarna att klicka på en URL i meddelandet. Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter. Om de gör det tas de till någon av följande platser:

  - En standard sida som förklarar att detta var ett test och ger tips för att känna igen nät fiske meddelanden.

    ![Vad användarna ser om de klickar på nätfiske-länken och anger deras autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - En anpassad sida (URL) som du anger.

- **Spear nätfiske (bifogad fil)**: med angreppet försöker mottagarna att öppna en. docx-eller. pdf-bilaga i meddelandet. Den bifogade filen innehåller samma innehåll från den vanliga nät fiske länken, men den första meningen börjar med " \<Display Name\> , du ser det här meddelandet som ett nyligen öppnade e-postmeddelande...".

> [!NOTE]
> För närvarande upphör Spear nät fiske kampanjer inte att gälla.

### <a name="create-a-spear-phishing-campaign"></a>Skapa en Spear nätfiske-kampanj

En viktig del av alla Spear nät fiske kampanjer är utseendet och känslan hos det e-postmeddelande som skickas till mottagarna. För att skapa och konfigurera e-postmeddelandet har du följande alternativ:

- **Använda en inbyggd e-postmall**: två inbyggda mallar är tillgängliga: **pris gåvo kampanjen** och **löne uppdatering**. Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa en återanvändbar e-postmall**: när du har skapat och sparat e-postmallen kan du använda den igen i framtida Spear nät fiske kampanjer. Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa e-postmeddelandet i guiden**: du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar Spear phishing-kampanjen.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Steg 1 (valfritt): skapa en anpassad e-postmall

Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.

1. I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.

2. På sidan **simulera attacker** , i något av **Spear phishing-** eller **Spear phishing-** avsnitt, klickar du på **angrepps information**.

   Det spelar ingen roll var du skapar mallen. De tillgängliga alternativen i mallen är desamma för båda typerna av nät fiske attacker.

3. Klicka på **ny mall** **i området för** **nätfiske-mallar** på sidan **information om attack** som öppnas.

4. Guiden **Konfigurera nätfiske-mall** startas i en ny utfällning. Ange ett unikt visnings namn för mallen i steget **Starta** och klicka sedan på **Nästa**.

5. Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :

   - **From (namn)**: visnings namnet som används för meddelande avsändare.

   - **Från (e-post)**: avsändarens e-postadress.

   - **URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan. Det här är URL-adressen som användarna blir frestade att klicka på. Alternativen är:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Alla URL-adresser är avsiktligt http, inte https.
     >
     > - En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra. Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.

   - **Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter. Den här länken ersätter standard ingångs sidan. Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.

   - **Kategori**: den här inställningen används inte (något du anger ignoreras).

   - **Ämne**: fältet **subject** i e-postmeddelandet.

   När du är klar klickar du på **Nästa**.

6. I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet. Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du vill. Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}` infogar URL-adressen för ett **nätfiske-inloggningsnamn** från föregående steg.

   När du är klar klickar du på **Nästa**.

7. Klicka på **Slutför** i steget **Bekräfta** .

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Steg 2: skapa och starta Spear phishing-kampanjen

1. I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.

2. På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:

   - I avsnittet **Spear phishing (identifierings skörd)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .

   - I avsnittet **Spear phishing (bilaga)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .

3. Guiden **Konfigurera nätfiske-attack** startas med en ny utfällning. Gör något av följande i steget **Starta** :

   - I rutan **namn** anger du ett unikt visnings namn för kampanjen. Klicka inte på **Använd mall** eftersom du kommer att skapa e-postmeddelandet senare i guiden.

   - Klicka på **Använd mall** och välj en inbyggd eller anpassad e-postmall. När du har valt mallen fylls **namn** rutan i automatiskt baserat på mallen, men du kan ändra namnet.

   ![Start sida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   När du är klar klickar du på **Nästa**.

4. Gör något av följande i steget **mål mottagare** :

   - Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen. Varje riktad mottagare måste ha en Exchange Online-postlåda. Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.

   - Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   När du är klar klickar du på **Nästa**.

5. Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :

   Om du har valt en mall i **Start** steget är de flesta dessa värden redan konfigurerade, men du kan ändra dem.

   - **From (namn)**: visnings namnet som används för meddelande avsändare.

   - **Från (e-post)**: avsändarens e-postadress. Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän, eller så kan du ange en verklig eller falsk extern e-postadress. En giltig avsändares e-postadress från din organisation löses faktiskt i mottagarens e-postklient.

   - **URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan. Det här är URL-adressen som användarna blir frestade att klicka på. Alternativen är:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Alla URL-adresser är avsiktligt http, inte https.
     >
     > - En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra. Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.
     >
     > - Du måste välja en URL-adress. För **Spear nätfiske (Attachment)** kan du ta bort länken från meddelande texten i nästa steg (annars innehåller meddelandet både en länk **och** en bifogad fil).

   - **Typ av bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** . Klicka på den nedrullningsbara List rutan och välj **. DOCX** eller **. PDF** i listan.

   - **Namn på bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** . Ange ett fil namn för. docx-eller. pdf-bilagan.

   - **Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter. Den här länken ersätter standard ingångs sidan. Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.

   - **Ämne**: fältet **subject** i e-postmeddelandet.

   När du är klar klickar du på **Nästa**.

6. I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet. Om du har valt en mall i **Start** steget är meddelande texten redan konfigurerad, men du kan anpassa den. Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du vill. Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}` infogar URL-värdet för **nätfiske-inloggningsnamn** .

   För **Spear phishing-kampanjer (bifogade filer)** bör du ta bort länken från meddelande texten (annars kommer meddelandet att innehålla både en länk **och** en bifogad fil, och länkar klickar spåras inte till en bifogad fil).

   ![Skriv e-postmeddelande](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   När du är klar klickar du på **Nästa**.

7. Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen. Nät fiske meddelandet levereras till mottagarna.

## <a name="password-attack-campaigns"></a>Lösen ords attacker

Ett *lösen ords angrepp* försöker gissa lösen ord för användar konton i en organisation, vanligt vis efter att angriparen har identifierat ett eller flera giltiga användar konton.

I angrepps simulatorer är två olika typer av lösen ords attacker tillgängliga för dig för att testa komplexiteten hos användarnas lösen ord:

- **Råa force-lösenord (ordbok)**: en upptaget-eller *ordlisteattacker* *använder en stor* ordbok med lösen ord på ett användar konto med en fråga om att en av dem ska fungera (många lösen ord mot ett konto). Felaktig låsning-gräns för lösen ord

  För ord listor kan du ange ett eller flera lösen ord (som anges manuellt eller i en uppladdad fil) och du kan ange en eller flera användare.

- **Attack för lösen ords besprutning**: ett *lösen* ord som används för att skydda en dator använder samma noggrant övervägda lösen ord mot en lista över användar konton (ett lösen ord mot många konton) Lösen ords dusch attacker är svårare att upptäcka än problem med råa lösen ord (sannolikheten att lyckas ökar när en angripare försöker med ett lösen ord på dussin tals eller hundratals konton utan risk för att Tripping användarens felaktiga lösen ord).

  För angrepp med lösen ord kan du bara ange ett lösen ord och du kan ange en eller flera användare.

> [!NOTE]
> Lösen ords attacker i angrepps Simulator vidarebefordrar användar namn och lösen ord för grundläggande autentisering till en slut punkt, så de fungerar även med andra autentiseringsmetoder (AD FS, lösen ords-hash-synkronisering, vidarekoppling, PingFederate, osv.). För användare som har MFA aktiverat, även om lösen ords attackeret försöker nå sitt faktiska lösen ord, kommer försöket alltid att registreras som ett fel (med andra ord kommer MFA-användarna aldrig att synas i kampanjens antal **lyckade försök** . Det här är det förväntade resultatet. MFA är en primär metod för att skydda mot lösen ords attacker.

### <a name="create-and-launch-a-password-attack-campaign"></a>Skapa och starta en kampanj för att attackera lösen ord

1. I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.

2. På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:

   - I avsnittet **råa force-lösenord (ordbok)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .

   - Klicka på **Starta** attacker eller klicka på **angrepps information** i avsnittet **lösen ords besprutnings attacker** \> .

3. Guiden **Konfigurera lösen ords attacker** startar i en ny utfällning. Ange ett unikt visnings namn för kampanjen i steget **Starta** och klicka sedan på **Nästa**.

4. Gör något av följande i steget **mål användare** :

   - Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen. Varje riktad mottagare måste ha en Exchange Online-postlåda. Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.

   - Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   När du är klar klickar du på **Nästa**.

5. Välj vad du vill göra i steget **Välj angrepps inställningar** :

   - **Råa force-lösenord (ordbok)**: gör något av följande:

     - **Ange lösen ord manuellt**: Skriv in ett lösen ord i rutan **Tryck på RETUR för att lägga till ett** lösenord och tryck sedan på RETUR. Upprepa det här steget så många gånger det behövs.

     - **Ladda upp lösen ord från en ordlistefil**: Klicka på **Ladda upp** för att importera en befintlig textfil som innehåller ett lösen ord på varje rad och en tom sista rad. Text filen måste vara 10 MB eller mindre och får inte innehålla fler än 30000 lösen ord.

   - **Lösen ords besprutning**: Skriv ett lösen ord i **lösen ordet som ska användas i angrepps** rutan.

   När du är klar klickar du på **Nästa**.

6. Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen. De angivna lösen orden är på användare som du har angett.

## <a name="view-campaign-results"></a>Visa kampanj resultat

När du har lanserat en kampanj kan du kontrol lera förlopp och resultat på huvud sidan **simulera attacker** .

Aktiva kampanjer visar ett statusfält, ett slutfört procent värde och "(slutförda användare) av (totalt antal användare). Om du klickar på knappen **Uppdatera** uppdateras alla aktiva kampanjer. Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.

När kampanjen är klar ändras status till **angreppet**. Du kan visa kampanj resultaten genom att göra något av följande:

- Klicka på **Visa rapport** under namnet på kampanjen på huvud sidan för **simulerade attacker** .

- På huvud sidan **simulera attacker** klickar du på **angrepps information** i avsnittet för typen av attack. På sidan **information om attack** som öppnas väljer du kampanjen i avsnittet **attack historik** .

En av de föregående åtgärderna tar dig till en sida med namnet **angrepps information**. Informationen som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Spear nätfiske (identitets skörd) kampanj resultat

Följande information finns på sidan **attack information** för varje kampanj:

- Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.

- **Totalt antal riktade användare**

- **Lyckade försök**: antalet användare som klickade på länken **och** angett sina *autentiseringsuppgifter (användar* namn och lösen ord).

- **Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.

- **Snabbast Klicka** här: hur lång tid det tog för den första användaren att klicka på länken efter att du startade kampanjen.

- **Genomsnittligt Klicka** på: summan av hur lång tid det tog för alla att klicka på länken dividerat med antalet användare som klickade på länken.

- **Klicka på framgång-frekvens**: en procents ATS som beräknas av (antal användare som klickade på länken)/ **totalt riktade användare**.

- **Snabbaste uppgifter**: hur länge den tog den första användaren att ange sina autentiseringsuppgifter efter att du har lanserat kampanjen.

- **Genomsnittligt antal autentiseringsuppgifter**: summan av hur lång tid det tog för alla att ange sina inloggnings uppgifter dividerat med antalet användare som angav sina autentiseringsuppgifter.

- **Framgång för lyckade** uppgifter: en procents ATS som beräknas av (antal användare som angav sina uppgifter)/ **totalt riktade till användare**.

- Ett stapeldiagram som visar numret på den **klickade** och den **angivna autentiseringsuppgiften** per dag.

- Ett cirkel diagram som visar den **länk som klickas** på, **autentiseringsuppgifter** och **ingen** procents ATS för kampanjen.

- I avsnittet **kompromissade användare** visas information om de användare som klickade på länken:

  - Användarens e-postadress

  - Datum/tid när de klickade på länken.

  - IP-adress för klienter.

  - Information om användarens version av Windows och webbläsare.

  Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.

### <a name="spear-phishing-attachment-campaign-results"></a>Spear phishing (bilagor) kampanj resultat

Följande information finns på sidan **attack information** för varje kampanj:

- Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.

- **Totalt antal riktade användare**

- **Lyckade försök**: antalet användare som öppnade eller hämtade och öppnade den bifogade filen (för hands version).

- **Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.

- **Snabbare öppning av bifogade filer**: hur lång tid det tog för den första användaren att öppna den bifogade filen när du startade kampanjen.

- **Genomsnittlig öppnings tid för bifogade filer**: summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.

- Slut för **ande frekvens för bifogad fil**: en procents ATS som beräknas av (antal användare som öppnade bilagan)/ **totalt riktade användare**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Lösen ords intrång (ord listor) kampanj resultat

Följande information finns på sidan **attack information** för varje kampanj:

- Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.

- **Totalt antal riktade användare**

- **Lyckade försök**: antalet användare som har hittat ett angivet lösen ord.

- **Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.

- I avsnittet **kompromissade användare** visas e-postadresserna till de berörda användarna. Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.

### <a name="password-spray-attack-campaign-results"></a>Lösen ords spridningen kampanj resultat

Följande information finns på sidan **attack information** för varje kampanj:

- Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.

- **Totalt antal riktade användare**

- **Lyckade försök**: antalet användare som har hittats med det angivna lösen ordet.

- **Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.
