---
title: AttackTat In Microsoft Defender för Office 365
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
description: Administratörer kan lära sig hur de kan använda Attack Program för att köra simulerade nätfiske- och lösenordsattacker i sina organisationer med Microsoft 365 E5 eller Microsoft Defender för Office 365 Abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c88a5df6fae61e1ffe70214ad4a73deef4b380e
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717614"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>AttackTat In Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller Microsoft** [Defender för Office 365 abonnemang 2](office-365-atp.md)

Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som omfattar funktioner för hotundersökning och [svar,](office-365-ti.md)kan du använda Attack i Säkerhets- & Efterlevnadscenter för att köra realistiska attackscenarier i organisationen. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nederkant. Läs den här artikeln om du vill veta mer.

> [!NOTE]
>
> AttackAnvisningarna som beskrivs i den här artikeln är  nu skrivskyddad och har ersatts av utbildning för attacksimulering i noden **E-post &** samarbete i [Säkerhetscenter för Microsoft 365.](https://security.microsoft.com) Mer information finns i Komma igång [med att använda attacksimuleringsutbildning.](attack-simulation-training-get-started.md)
>
> Möjligheten att starta nya simuleringar från den här versionen av attackattacken har inaktiverats. Du kan dock fortfarande komma åt rapporter i upp till 90 dagar från den 24 januari 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter. Attackattack är tillgänglig vid **hothanteringsattack.** \>  Gå direkt till attack nu, <https://protection.office.com/attacksimulator> öppna.

- Mer information om tillgängligheten för AttackTrafik för olika Microsoft 365-prenumerationer finns i [tjänstbeskrivningen för Microsoft Defender för Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Du måste vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i Attack Den här enheten. Instruktioner finns i Konfigurera [multifaktorautentisering.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Attack Det fungerar bara för molnbaserade postlådor.

- Nätfiskekampanjer samlar in och bearbetar händelser i 30 dagar. Historiska kampanjdata är tillgängliga i upp till 90 dagar efter att du startade kampanjen.

- Attackattack och utbildningsrelaterade data lagras med andra kunddata för Microsoft 365-tjänster. Mer information finns i [Microsoft 365-dataplatser.](/microsoft-365/enterprise/o365-data-locations)

- Det finns inga Motsvarande PowerShell-cmdlets för Attack Attack Attack.

## <a name="spear-phishing-campaigns"></a>Nätfiskekampanjer

*Nätfiske* är en vanlig term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar komma från legitima eller betrodda avsändare. *Nätfiske* är en riktad nätfiskeattack som använder fokuserat och anpassat innehåll som är specifikt anpassat efter de riktade mottagarna (vanligtvis efterkontroll på mottagarna av attacken).

Två olika typer av nätfiskekampanjer är tillgängliga i Attack Det finns två olika typer av nätfiskekampanjer:

- **Nätfiske (autentiseringsuppgifter)**: Attacken försöker övertyga mottagarna att klicka på en URL i meddelandet. Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter. I så fall tas de till någon av följande platser:

  - En standardsida som förklarar att det var ett test och ger tips om hur du känner igen nätfiskemeddelanden.

    ![Vad användarna ser om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - En anpassad sida (URL) som du anger.

- **Nätfiske (bifogad fil)**: Attacken försöker övertyga mottagarna att öppna en bifogad DOCX- eller .PDF-fil i meddelandet. Den bifogade filen innehåller samma innehåll från standardlänken för nätfiske, men den första meningen börjar med ", du ser det här meddelandet som ett nyligen öppnat \<Display Name\> e-postmeddelande...".

> [!NOTE]
> För närvarande upphör inte nätfiskekampanjer i Attack Det här gäller inte längre.

### <a name="create-a-spear-phishing-campaign"></a>Skapa en nätfiskekampanj

En viktig del av alla nätfiskekampanjer är utseendet och känslan i e-postmeddelandet som skickas till de riktade mottagarna. Om du vill skapa och konfigurera e-postmeddelandet har du följande alternativ:

- **Använd en inbyggd e-postmall:** Två inbyggda mallar är tillgängliga: Gåkampanj **och** **löneuppdatering.** Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa en återanvändningsbar e-postmall:** När du har skapat och sparat e-postmallen kan du använda den igen i kommande nätfiskekampanjer. Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa e-postmeddelandet i guiden:** Du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar nätfiskekampanjen.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Steg 1 (valfritt): Skapa en anpassad e-postmall

Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.

1. I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**

2. På sidan **Simulera attacker,** i antingen avsnitten **Nätfiske (autentiseringsinloggning)** eller **Nätfiske (bifogad fil),** klickar du **på Attackinformation.**

   Det spelar ingen roll var du skapar mallen. De tillgängliga alternativen i mallen är desamma för båda typerna av nätfiskeattacker.

3. Klicka på **Ny** mall i  området Skapa mallar  på sidan Attackinformation som öppnas i avsnittet **Nätfiskemallar.**

4. Guiden **Konfigurera nätfiskemall** startar i en ny utfällningsguide. Ange ett unikt visningsnamn för mallen i steget **Start** och klicka sedan på **Nästa.**

5. I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:

   - **Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.

   - **Från (E-post)**: Avsändarens e-postadress.

   - **URL till nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Det här är URL-adressen som användarna frestas att klicka på. Alternativen är:

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
     > Ett rykte på en URL-tjänst kan identifiera en eller flera av dessa URL:er som osäkra. Kontrollera om URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.

   - **Anpassad webbadress till startsidan:** Ange en valfri landningssida dit användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter. Den här länken ersätter standardlandningssidan. Om du till exempel har intern informationsutbildning kan du ange url:en här.

   - **Kategori:** Den här inställningen används inte för närvarande (allt du anger ignoreras).

   - **Ämne:** **Ämnesfältet** i e-postmeddelandet.

   Klicka på Nästa när du är **klar.**

6. Skapa **meddelandetexten i e-postmeddelandet** i steget Skriv e-postmeddelande. Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken** Källa (raw HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du vill ha den. Du kan infoga bilder och text för att göra meddelandet bättre i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}` infogar **URL-adressen för nätfiskeinloggningsservern** från föregående steg.

   Klicka på Nästa när du är **klar.**

7. Klicka på **Slutför** i steget **Bekräfta.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Steg 2: Skapa och starta nätfiskekampanjen

1. I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**

2. Gör något **av följande** val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:

   - Klicka på Starta attack eller klicka  på Starta attack med information om nätfiske (autentiseringsuppgifter) **i** avsnittet Om  \> **nätfiske**(autentiseringsstart).

   - Klicka på Starta attack eller  klicka på Attack **Details** Launch Attack i avsnittet Nätfiske **(bifogad** \> **fil).**

3. Guiden **Konfigurera nätfiskeattack** startar i en ny utfällning. Gör något **av** följande i startsteget:

   - Ange **ett** unikt visningsnamn för kampanjen i rutan Namn. Klicka inte på **Använd mall** eftersom du skapar e-postmeddelandet senare i guiden.

   - Klicka **på Använd mall** och välj en inbyggd eller anpassad e-postmall. När du har valt mallen **fylls** rutan Namn automatiskt i baserat på mallen, men du kan ändra namnet.

   > [!div class="mx-imgBorder"]
   > ![Startsida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Klicka på Nästa när du är **klar.**

4. Gör något **av följande** i steget Målmottagare:

   - Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen. Varje mottagare måste ha en Exchange Online-postlåda. Om du klickar **på Filtrera** **och använd** utan att ange sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka **på** Importera **och sedan på Importera** fil för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   Klicka på Nästa när du är **klar.**

5. I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:

   Om du valde en mall i **Start-steget** är de flesta av dessa värden redan konfigurerade, men du kan ändra dem.

   - **Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.

   - **Från (E-post)**: Avsändarens e-postadress. Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän eller ange en verklig eller falsk extern e-postadress. En giltig avsändares e-postadress från organisationen fungerar faktiskt i mottagarens e-postklient.

   - **URL till nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Det här är URL-adressen som användarna frestas att klicka på. Alternativen är:

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
     > - Ett rykte på en URL-tjänst kan identifiera en eller flera av dessa URL:er som osäkra. Kontrollera om URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.
     >
     > - Du måste välja en URL-adress. Vid kampanjer mot nätfiske **(bifogad fil)** kan du ta bort länken från brödtexten i  meddelandet i nästa steg (annars innehåller meddelandet både en länk och en bifogad fil).

   - **Typ av** bifogad fil: Den här inställningen är endast tillgänglig i kampanjer för **nätfiske (bifogad** fil). Klicka på listrutan och **välj. DOCX** eller **. PDF** från listan.

   - **Namn på** bifogad fil: Den här inställningen är endast tillgänglig i kampanjer för **nätfiske (bifogad** fil). Ange ett filnamn för den bifogade filen .docx eller .pdf.

   - **Anpassad webbadress till startsidan:** Ange en valfri landningssida dit användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter. Den här länken ersätter standardlandningssidan. Om du till exempel har intern informationsutbildning kan du ange url:en här.

   - **Ämne:** **Ämnesfältet** i e-postmeddelandet.

   Klicka på Nästa när du är **klar.**

6. Skapa **meddelandetexten i e-postmeddelandet** i steget Skriv e-postmeddelande. Om du valde en mall i **Start-steget** är meddelandetexten redan konfigurerad, men du kan anpassa den. Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken** Källa (raw HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du vill ha den. Du kan infoga bilder och text för att göra meddelandet bättre i mottagarens e-postklient.

   - `${username}` infogar mottagarens namn.

   - `${loginserverurl}`infogar **URL-värdet för nätfiskeinloggningsservern.**

   Vid kampanjer mot nätfiske **(bifogad fil)** bör du ta bort länken från brödtexten i meddelandet (annars innehåller meddelandet både en länk och en bifogad fil och länkklick spåras inte i en kampanj för bifogade filer). 

   > [!div class="mx-imgBorder"]
   > ![Skriv e-posttext](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Klicka på Nästa när du är **klar.**

7. Klicka på **Slutför** i steget **Bekräfta för** att starta kampanjen. Nätfiskemeddelandet levereras till de riktade mottagarna.

## <a name="password-attack-campaigns"></a>Lösenordsattackkampanjer

En *lösenordsattack* försöker gissa lösenord för användarkonton i en organisation, vanligtvis efter att attackeraren har identifierat ett eller flera giltiga användarkonton.

I Attack Complex finns det två olika typer av lösenordsattackkampanjer som du kan använda för att testa användarnas lösenords komplexitet:

- **Råstyrt** lösenord (ordlisteattack)  : En rå kraft- eller ordlisteattack använder en stor ordlistefil med lösenord för ett användarkonto och hoppas att ett av dem fungerar (många lösenord mot ett konto).  Felaktiga lösenordslåsningar hjälper till att avstyra råstyra lösenordsattacker.

  För ordlisteattacken kan du ange ett eller flera lösenord att prova (manuellt anges eller i en uppladdad fil) och du kan ange en eller flera användare.

- **Lösenordsattack:** En *lösenordsattack* använder samma noggrant övervägde lösenord mot en lista med användarkonton (ett lösenord mot många konton). Lösenordsattacker är svårare att identifiera än råstyra lösenordsattacker (sannolikheten för att en attack lyckas ökar när en attacker försöker ett lösenord med dussintals eller hundratals konton utan risk för att utlåsa användarens felaktiga lösenord).

  För lösenordsattacken kan du bara ange ett lösenord att prova och du kan ange en eller flera användare.

> [!NOTE]
> Lösenordsattackerna i Attack Pass användarnamn och lösenord Basic begär till en slutpunkt, så de fungerar även med andra autentiseringsmetoder (AD FS, synkronisering av lösenordshashar, direktuppspelning, PingFederate osv.). För användare som har MFA aktiverat, även om lösenordsattacken försöker med sitt faktiska lösenord, registreras försöket alltid  som ett fel (MFA-användare visas alltså aldrig i antalet lyckade försök för kampanjen). Det här är det förväntade resultatet. MFA är en primär metod för att skydda mot lösenordsattacker.

### <a name="create-and-launch-a-password-attack-campaign"></a>Skapa och starta en kampanj för lösenordsattack

1. I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**

2. Gör något **av följande** val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:

   - Klicka på Starta attack eller klicka på  Starta attackinformation i avsnittet Råstyrt tvinga lösenord  (Ordlisteattack).  \> 

   - i avsnittet **Lösenordsattack klickar** du på **Starta** attack eller klickar på Starta **attackinformation.** \> 

3. Guiden **Konfigurera lösenordsattack** startar i en ny utfäll kant. Ange ett **unikt** visningsnamn för kampanjen i steget Start och klicka sedan på **Nästa.**

4. Gör något **av följande** i steget Målanvändare:

   - Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen. Varje mottagare måste ha en Exchange Online-postlåda. Om du klickar **på Filtrera** **och använd** utan att ange sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka **på** Importera **och sedan på Importera** fil för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   Klicka på Nästa när du är **klar.**

5. I steget **Välj attackinställningar** väljer du vad du vill göra baserat på kampanjtypen:

   - **Råstyrt lösenord (ordlisteattack)**: Gör något av följande:

     - **Ange lösenord manuellt:** Skriv ett lösenord **i rutan** Tryck på Retur för att lägga till ett lösenord och tryck sedan på RETUR. Upprepa det här steget så många gånger det behövs.

     - **Ladda upp lösenord från en ordlistefil:** Klicka på Ladda upp om du vill importera en befintlig textfil som innehåller ett lösenord på varje rad och en tom sista rad.  Textfilen måste vara 10 MB eller mindre och får inte innehålla fler än 3 0000 lösenord.

   - **Lösenordsattack:** **Ange ett lösenord i** lösenordsrutan som ska användas i attackrutan.

   Klicka på Nästa när du är **klar.**

6. Klicka på **Slutför** i steget **Bekräfta för** att starta kampanjen. De angivna lösenorden används av användare som du angett.

## <a name="view-campaign-results"></a>Visa kampanjresultat

När du har lanserat en kampanj kan du kontrollera förloppet och resultaten på **huvudsidan För simulera attacker.**

Aktiva kampanjer visar ett statusfält, ett slutfört procentvärde och antalet "(slutförda användare) (totalt antal användare)". Om du **klickar på** knappen Uppdatera uppdateras förloppet för alla aktiva kampanjer. Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.

När kampanjen är klar har statusen ändras till **Attack.** Du kan visa resultatet av kampanjen genom att göra något av följande:

- På huvudsidan **För simulera** attacker klickar **du på Visa** rapport under namnet på kampanjen.

- På huvudsidan **Simulera attacker** klickar du **på Attackinformation** i avsnittet för typen av attack. Välj **kampanjen i** avsnittet Attackhistorik på sidan Attackinformation **som** öppnas.

Någon av de föregående åtgärderna tar dig till en sida som heter **Attack details.** Informationen som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Kampanjresultat för nätfiske (autentiseringsuppgifter)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/tid och slutdatum/tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som klickade på länken **och** angav sina autentiseringsuppgifter *(val av* användarnamn och lösenord).

- **Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**

- **Snabbast klicka:** Hur lång tid det tog den första användaren att klicka på länken efter att du startat kampanjen.

- **Genomsnittligt** klick: Summan av hur lång tid det tog att klicka på länken dividerat med antalet användare som klickade på länken.

- **Klicka på Framgång:** En procentandel som beräknas utifrån (antalet användare som klickade på länken) **/Totalt antal riktade användare.**

- **Snabbast:** Hur lång tid det tog för den första användaren att ange sina autentiseringsuppgifter efter att du startat kampanjen.

- **Genomsnittligt** antal autentiseringsuppgifter: Summan av hur lång tid det tog för alla att ange sina autentiseringsuppgifter dividerat med antalet användare som angav deras autentiseringsuppgifter.

- **Lyckade autentiseringsuppgifter: En** procentandel som beräknas av (antalet användare som angett sina autentiseringsuppgifter) **/Totalt antal riktade användare.**

- Ett stapeldiagram som visar **den länk som klickas** och **de autentiseringsuppgifter som anges** för varje dag.

- Ett cirkeldiagram som visar **klickad länk,** de **autentiseringsuppgifter som anges** **och inga** procenttal för kampanjen.

- I **avsnittet Komprometterade** användare visas information om de användare som klickade på länken:

  - Användarens e-postadress

  - Datum/tid då de klickade på länken.

  - Klientens IP-adress.

  - Information om användarens version av Windows och webbläsare.

  Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="spear-phishing-attachment-campaign-results"></a>Kampanjresultat för nätfiske (bifogad fil)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/tid och slutdatum/tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som öppnade eller hämtade och öppnade den bifogade filen (förhandsgranskningen räknas inte).

- **Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**

- **Snabbast öppningstid för** bifogade filer: Hur lång tid det tog den första användaren att öppna den bifogade filen efter att du startade kampanjen.

- **Genomsnittlig öppen tid för bifogade** filer: Summan av hur lång tid det tog att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.

- **Antal användare som öppnat den** bifogade filen som lyckades: En procentandel som beräknas av (antalet användare som öppnade den bifogade filen) **/Totalt antal riktade användare.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Kampanjresultat för råstyrt lösenord (ordlisteattack)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/tid och slutdatum/tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som hittades använda ett av de angivna lösenorden.

- **Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**

- I **avsnittet Komprometterade** användare visas e-postadresserna till de berörda användarna. Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="password-spray-attack-campaign-results"></a>Kampanjresultat för lösenordsattack

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/tid och slutdatum/tid).

- **Totalt antal riktade användare**

- **Lyckade försök:** Antalet användare som hittades använda det angivna lösenordet.

- **Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**
