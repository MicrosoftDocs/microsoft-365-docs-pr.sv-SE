---
title: Attack Attack i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur de kan använda Attack Attack För att köra simulerade nätfiske- och lösenordsattacker i sina organisationer av Microsoft 365 E5 eller Microsoft Defender för Office 365 Abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 637e84281b85e8c859207ae81342a3c6ab3d00be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073513"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Attack Attack i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för** [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som innehåller funktioner för hotundersökning och [svar,](office-365-ti.md)kan du använda Attack Attack Attack i Säkerhets- & och efterlevnadscenter för att köra realistiska attackscenarier i din organisation. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nedersta linje. Läs den här artikeln om du vill veta mer.

> [!NOTE]
>
> Attack Attack Så som beskrivs i den här artikeln  är nu skrivskyddad och har ersatts av utbildning av attack simulering **i E-& samarbetsnod** i Säkerhetscenter för [Microsoft 365.](https://security.microsoft.com) Mer information finns i Komma [igång med att använda simuleringsutbildning för attacker](attack-simulation-training-get-started.md).
>
> Möjligheten att starta nya simuleringar från den här versionen av Attack Attack har inaktiverats. Du kan dock fortfarande komma åt rapporter i upp till 90 dagar från den 24 januari 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter. Attackattack finns tillgänglig på **Threat management** \> **Attack attack**. Gå direkt till attack så öppnar du <https://protection.office.com/attacksimulator> .

- Mer information om tillgängligheten för Attack Defender för olika Microsoft 365-prenumerationer finns i Tjänstbeskrivning för [Microsoft Defender för Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Du måste vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i Attack Attack Så här gör du. Anvisningar finns i [Konfigurera multifaktorautentisering.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Attack Det fungerar bara för molnbaserade postlådor.

- Nätfiskekampanjer samlar in och bearbetar händelser i 30 dagar. Historiska kampanjdata blir tillgängliga i upp till 90 dagar efter att du startade kampanjen.

- Attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster. Mer information finns i [Microsoft 365-dataplatser.](../../enterprise/o365-data-locations.md)

- Det finns inga motsvarande PowerShell-cmdlets för Attack Attack.

## <a name="spear-phishing-campaigns"></a>Nätfiskekampanjer mot nätfiske

*Nätfiske* är en allmän term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. *Nätfiske* är en riktad nätfiskeattack som använder fokuserat och anpassat innehåll som är specifikt anpassat efter de riktade mottagarna (vanligtvis efter att ha fått ny information om mottagarna av attackeraren).

I Attack Attack Attack finns det två olika typer av nätfiskekampanjer:

- **Nätfiske (autentiseringsuppgifter för skörd)**: Attacken försöker övertyga mottagarna att klicka på en URL i meddelandet. Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter. I så fall tas de till någon av följande platser:

  - En standardsida som förklarar att det var ett test med tips om hur du känner igen nätfiskemeddelanden.

    ![Vad användarna ser om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - En anpassad sida (URL) som du anger.

- **Nätfiske (bifogad fil)**: Attacken försöker övertyga mottagarna att öppna en bifogad DOCX- eller PDF-fil i meddelandet. Den bifogade filen innehåller samma innehåll från standardlänken för nätfiske, men den första meningen börjar med " , du ser det här meddelandet som ett nyligen öppnat \<Display Name\> e-postmeddelande ...".

> [!NOTE]
> För närvarande upphör inte nätfiskekampanjer i Attack Attack att gälla.

### <a name="create-a-spear-phishing-campaign"></a>Skapa en nätfiskekampanj

En viktig del av alla nätfiskekampanjer är utseendet på e-postmeddelandet som skickas till de riktade mottagarna. Om du vill skapa och konfigurera e-postmeddelandet har du följande alternativ:

- **Använda en inbyggd e-postmall:** Två inbyggda mallar är tillgängliga: Gåkampanj **för pris och** **löneuppdatering**. Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa en återanvändningsbar e-postmall:** När du har skapat och sparat e-postmallen kan du använda den igen i kommande nätfiskekampanjer. Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa e-postmeddelandet i guiden**: Du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar nätfiskekampanjen.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Steg 1 (valfritt): Skapa en anpassad e-postmall

Om du kommer att använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Attack** \> **för hothantering .**

2. På sidan **Simulera attacker klickar** du på Attackinformation i avsnitten Nätfiske **(autentiseringsuppgifter)** eller Nätfiske **(bifogad** **fil).**

   Det spelar ingen roll var du skapar mallen. De tillgängliga alternativen i mallen är desamma för båda typerna av nätfiskeattacker.

3. Klicka **på Ny mall** i området Skapa mallar  i **avsnittet Nätfiskemallar** på sidan **Attackinformation som öppnas.**

4. Guiden **Konfigurera nätfiskemall** startar i en ny utfällningsguide. I steget **Start** anger du ett unikt visningsnamn för mallen och klickar sedan på **Nästa.**

5. I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:

   - **Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.

   - **Från (E-post)**: Avsändarens e-postadress.

   - **URL för nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Det här är url-adressen som användarna kommer att frestas att klicka på. Alternativen är:

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
     > Ett rykte för URL-adresser kan identifiera en eller flera av dessa URL:er som osäkra. Kontrollera webbadressens tillgänglighet i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.

   - **Anpassad landsides-URL:** Ange en valfri landningssida dit användare tas om de klickar på nätfiskelänken och anger sina inloggningsuppgifter. Den här länken ersätter standardlandningssidan. Om du till exempel har intern informationsutbildning kan du ange url:en här.

   - **Kategori:** För närvarande används inte den här inställningen (något du anger ignoreras).

   - **Ämne:** Fältet **Ämne** i e-postmeddelandet.

   Klicka på Nästa när du är **klar.**

6. I steget **Skriv e-postmeddelande** skapar du meddelandetexten i e-postmeddelandet. Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken Källa** (raw HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du behöver den. Du kan infoga bilder och text för att göra meddelandet lätt att läsa i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}` infogar **url-värdet för nätfiskeinloggningsservern** från föregående steg.

   Klicka på Nästa när du är **klar.**

7. Klicka på **Slutför** i steget **Bekräfta.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Steg 2: Skapa och starta nätfiskekampanjen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Attack** \> **för hothantering .**

2. Gör **något av** följande val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:

   - I avsnittet **Phishing Phishing (Credentials Harvest) klickar** du på Starta **attack** eller klickar på **Starta attackinformation** \> **starta attack**.

   - I avsnittet **Nätfiske (bifogad fil) klickar** du på **Starta attack** eller klickar på **Starta attackinformation.** \> 

3. Guiden **Konfigurera nätfiskeattack** startar i en ny utfällklar plats. I **steget Start** gör du något av följande:

   - I rutan **Namn** anger du ett unikt visningsnamn för kampanjen. Klicka inte på **Använd mall** eftersom du kommer att skapa e-postmeddelandet senare i guiden.

   - Klicka **på Använd mall** och välj en inbyggd eller anpassad e-postmall. När du har valt mallen **fylls** rutan Namn automatiskt i baserat på mallen, men du kan ändra namnet.

   > [!div class="mx-imgBorder"]
   > ![Nätfiskestartsida](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Klicka på Nästa när du är **klar.**

4. Gör **något av följande** i steget Målmottagare:

   - Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen. Varje mottagare måste ha en Exchange Online-postlåda. Om du klickar **på** Filtrera **och tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka **på Importera** och sedan på **Filimport** för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   Klicka på Nästa när du är **klar.**

5. I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:

   Om du valde en mall i **steget Start** är de flesta av dessa värden redan konfigurerade, men du kan ändra dem.

   - **Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.

   - **Från (E-post)**: Avsändarens e-postadress. Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän eller ange en riktig eller falsk extern e-postadress. En giltig avsändares e-postadress från organisationen matchas faktiskt i mottagarens e-postklient.

   - **URL för nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Det här är url-adressen som användarna kommer att frestas att klicka på. Alternativen är:

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
     > - Alla URL:er är avsiktligt http, inte https.
     >
     > - Ett rykte för URL-adresser kan identifiera en eller flera av dessa URL:er som osäkra. Kontrollera webbadressens tillgänglighet i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.
     >
     > - Du måste välja en URL-adress. Vid **nätfiskekampanjer (bifogade filer)** kan du ta bort länken från brödtexten i meddelandet i nästa steg (annars innehåller meddelandet både en länk och en **bifogad** fil).

   - **Typ av** bifogad fil: Den här inställningen är endast tillgänglig för nätfiskekampanjer **(attachment).** Klicka på listrutan och välj **. DOCX** eller **. PDF** från listan.

   - **Namn på bifogad** fil: Den här inställningen är endast tillgänglig för nätfiskekampanjer **(attachment).** Ange ett filnamn för den bifogade filen .docx eller .pdf.

   - **Anpassad landsides-URL:** Ange en valfri landningssida dit användare tas om de klickar på nätfiskelänken och anger sina inloggningsuppgifter. Den här länken ersätter standardlandningssidan. Om du till exempel har intern informationsutbildning kan du ange url:en här.

   - **Ämne:** Fältet **Ämne** i e-postmeddelandet.

   Klicka på Nästa när du är **klar.**

6. I steget **Skriv e-postmeddelande** skapar du meddelandetexten i e-postmeddelandet. Om du valde en mall i **steget Start** är meddelandetexten redan konfigurerad, men du kan anpassa den. Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken Källa** (raw HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du behöver den. Du kan infoga bilder och text för att göra meddelandet lätt att läsa i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}`infogar **URL-värdet för nätfiskeinloggningsservern.**

   Vid **nätfiskekampanjer (bifogade filer)** bör du ta bort länken från brödtexten i  meddelandet (annars innehåller meddelandet både en länk och en bifogad fil och länkklickningar spåras inte i en kampanj för bifogade filer).

   > [!div class="mx-imgBorder"]
   > ![Skriv brödtext för e-post](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Klicka på Nästa när du är **klar.**

7. I steget **Bekräfta** klickar du på **Slutför för** att starta kampanjen. Nätfiskemeddelandet levereras till de mottagare som är mottagare.

## <a name="password-attack-campaigns"></a>Kampanjer för lösenordsattack

En *lösenordsattack* försöker gissa lösenord för användarkonton i en organisation, vanligtvis efter att attackeraren har identifierat ett eller flera giltiga användarkonton.

I Attack Attack Attack finns det två olika typer av lösenordsattackkampanjer som du kan använda för att testa komplexiteten på användarnas lösenord:

- **Råstyrt** lösenord (ordlisteattack)  : En råstyrt attack eller ordlisteattack använder en stor ordlistefil med lösenord på ett användarkonto och hoppas att ett av dem fungerar (många lösenord mot ett konto).  Felaktiga lösenordslåsningar hjälper till att förhindra råstyra lösenordsattacker.

  För ordlisteattack kan du ange ett eller flera lösenord att prova (manuellt angivna eller i en uppladdad fil), och du kan ange en eller flera användare.

- **Lösenordsattack:** En *lösenordsattack* använder samma noggrant övervägde lösenord mot en lista med användarkonton (ett lösenord mot många konton). Lösenordsattacker är svårare att identifiera än råstyra lösenordsattacker (sannolikheten att lyckas ökar när en attackerare försöker ett lösenord med dussintals eller hundratals konton utan risk för att låsa upp användarens felaktiga lösenord).

  För lösenordsattack kan du bara ange ett lösenord att prova och du kan ange en eller flera användare.

> [!NOTE]
> Lösenordsattackerna i Attack Attack Pass användarnamn och lösenord Grundläggande autentiseringsbegäranden till en slutpunkt, så de fungerar även med andra autentiseringsmetoder (AD FS, synkronisering av lösenordshashar, direkt, PingFederate osv.). För användare som har MFA aktiverat, även om lösenordsattacken försöker ange sitt faktiska lösenord, registreras försöket alltid  som ett fel (MFA-användare visas alltså aldrig i antal lyckade försök för kampanjen). Det här är det förväntade resultatet. MFA är en primär metod för att skydda mot lösenordsattacker.

### <a name="create-and-launch-a-password-attack-campaign"></a>Skapa och starta en kampanj för lösenordsattack

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Attack** \> **för hothantering .**

2. Gör **något av** följande val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:

   - I avsnittet **Råstyrt lösenord (ordlisteattack) klickar** du på **Starta attack** eller klicka på **Starta attackinformation.** \> 

   - i avsnittet **Lösenord för attack** klickar du på Starta attack **eller** klickar på **Starta attackinformation.** \> 

3. Guiden **Konfigurera lösenordsattack** startar i en ny utfällklar. I steget **Start** anger du ett unikt visningsnamn för kampanjen och klickar sedan på **Nästa.**

4. Gör **något av följande** i steget Målanvändare:

   - Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen. Varje mottagare måste ha en Exchange Online-postlåda. Om du klickar **på** Filtrera **och tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka **på Importera** och sedan på **Filimport** för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   Klicka på Nästa när du är **klar.**

5. I steget **Välj attackinställningar** väljer du vad du vill göra baserat på kampanjtypen:

   - **Råstyrt lösenord (Ordlisteattack)**: Gör något av följande:

     - **Ange lösenord manuellt:** Skriv ett lösenord **i rutan Tryck på** Retur för att lägga till ett lösenord och tryck sedan på RETUR. Upprepa det här steget så många gånger det behövs.

     - **Ladda upp lösenord från en ordlistefil**: Klicka på Ladda upp om du vill importera en befintlig textfil som innehåller ett lösenord för varje rad och en tom sista rad.  Textfilen måste vara 10 MB eller mindre och får inte innehålla fler än 3 0000 lösenord.

   - **Lösenordsattack:** **Skriv ett lösenord** i lösenordsrutan som ska användas i attackrutan.

   Klicka på Nästa när du är **klar.**

6. I steget **Bekräfta** klickar du på **Slutför för** att starta kampanjen. De angivna lösenorden provas för användare som du angett.

## <a name="view-campaign-results"></a>Visa kampanjresultat

När du har lanserat en kampanj kan du kontrollera förloppet och resultaten på huvudsidan **För simulera attacker.**

Aktiva kampanjer visar ett statusfält, ett slutfört procentvärde och antalet "(slutförda användare) (totalt antal användare)". Om du **klickar** på knappen Uppdatera uppdateras förloppet för alla aktiva kampanjer. Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.

När kampanjen är klar ändras status till **Attack slutfört**. Du kan visa resultatet av kampanjen genom att göra något av följande:

- På huvudsidan **Simulera attacker** klickar du **på Visa** rapport under namnet på kampanjen.

- På huvudsidan **Simulera attacker** klickar du **på Attackinformation** i avsnittet för typen av attack. På sidan **Attackinformation** som öppnas väljer du kampanjen i **avsnittet Attackhistorik.**

Någon av de tidigare åtgärderna tar dig till en sida med namnet **Attackinformation.** Informationen som finns tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Kampanjresultat för nätfiske (autentiseringsuppgifter)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/starttid och slutdatum/-tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som klickade på länken och angav sina autentiseringsuppgifter (val *av användarnamn* och lösenord). 

- **Övergripande framgångsfrekvens:** Ett procenttal som beräknas med **Lyckade** försök  /  **Totalt antal användare riktad**.

- **Snabbast klicka:** Hur lång tid det tog för den första användaren att klicka på länken efter att du startat kampanjen.

- **Genomsnittligt** klick: Summan av hur lång tid det tog att klicka på länken dividerat med antalet användare som klickade på länken.

- **Klicka på** Framgångsfrekvens: Ett procenttal som beräknas av (antalet användare som klickade på länken) **/Totalt antal användare riktade**.

- **Snabbast:** Hur lång tid det tog för den första användaren att ange sina autentiseringsuppgifter efter att du startade kampanjen.

- **Medelautentiseringsuppgifter:** Summan av hur lång tid det tog för alla att ange sina autentiseringsuppgifter dividerat med antalet användare som angav deras autentiseringsuppgifter.

- **Lyckades autentiseringsuppgifter: Ett** procenttal som beräknas av (antalet användare som angett sina autentiseringsuppgifter) **/Totalt antal användare riktade**.

- Ett stapeldiagram som visar **de tal som klickas på** länk och **autentiseringsuppgifter** som anges per dag.

- Ett cirkeldiagram som visar **klickad länk,** **autentiseringsuppgifter som anges** och **Inga** procent för kampanjen.

- I **avsnittet Komprometterade** användare visas information om de användare som klickade på länken:

  - Användarens e-postadress

  - Datum/tid då de klickade på länken.

  - Klientens IP-adress.

  - Information om användarens version av Windows och webbläsare.

  Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="spear-phishing-attachment-campaign-results"></a>Kampanjresultat för nätfiske (bifogad fil)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/starttid och slutdatum/-tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som öppnade eller hämtade och öppnade den bifogade filen (förhandsgranskning räknas inte).

- **Övergripande framgångsfrekvens:** Ett procenttal som beräknas med **Lyckade** försök  /  **Totalt antal användare riktad**.

- **Snabbast öppningstid för** bifogade filer: Hur lång tid tog det för den första användaren att öppna den bifogade filen efter att du startade kampanjen.

- **Genomsnittlig öppen tid för bifogade** filer: Summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.

- **Antal användare som öppnat den** bifogade filen : Ett procenttal som beräknas av (antalet användare som öppnade den bifogade filen) **/Totalt antal användare riktad**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Kampanjresultat av råstyrt lösenord (ordlisteattack)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/starttid och slutdatum/-tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som hittades använda ett av de angivna lösenorden.

- **Övergripande framgångsfrekvens:** Ett procenttal som beräknas med **Lyckade** försök  /  **Totalt antal användare riktad**.

- I **avsnittet Komprometterade** användare visas e-postadresserna till de användare som påverkas. Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="password-spray-attack-campaign-results"></a>Resultat från attackkampanjer på lösenord

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/starttid och slutdatum/-tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som hittades använda det angivna lösenordet.

- **Övergripande framgångsfrekvens:** Ett procenttal som beräknas med **Lyckade** försök  /  **Totalt antal användare riktad**.