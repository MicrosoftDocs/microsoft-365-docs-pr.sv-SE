---
title: Attack Simulator i ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder Attack Simulator för att köra simulerade nätfiske- och lösenordsattacker i din Microsoft 365 E5- eller ATP Plan 2-organisation.
ms.openlocfilehash: 166a8ab9f6ef08ca089bc8924b686e392e870526
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587574"
---
# <a name="attack-simulator-in-atp"></a>Attack Simulator i ATP

**Sammanfattning** Om du är en global administratör eller en säkerhetsadministratör och din organisation har Office 365 Advanced Threat Protection Plan 2, som innehåller [hotutrednings- och svarsfunktioner,](office-365-ti.md)kan du använda Attack Simulator för att köra realistiska attackscenarier i organisationen. Detta kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din vinst. Läs den här artikeln om du vill veta mer.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter. Attack simulator finns på **Threat management** \> **Attack simulator**.

  ![Hothantering - Attack Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- Mer information om tillgängligheten för Attack Simulator för olika Microsoft 365-prenumerationer finns i [office 365-tjänstbeskrivning för avancerat skydd mot hot](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Du måste vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Ditt konto måste konfigureras för MFA (Multi Factor Authentication) för att skapa och hantera kampanjer i Attack Simulator. Instruktioner finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

För att en attack ska kunna startas kontrollerar du att kontot du använder för att köra simulerade attacker använder multifaktorautentisering. Dessutom måste du vara global administratör eller säkerhetsadministratör. (Mer information om roller och behörigheter finns [i Behörigheter i Säkerhets- & Compliance Center](permissions-in-the-security-and-compliance-center.md).)

- Nätfiskekampanjer samlar in och behandlar händelser i 30 dagar. Historiska kampanjdata kommer att vara tillgängliga i upp till 90 dagar efter att du har startat kampanjen.

- Det finns inga motsvarande PowerShell-cmdlets för Attack Simulator.

## <a name="spear-phishing-campaigns"></a>Nätfiskekampanjer för spjut

*Nätfiske* är en allmän term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar komma från legitima eller betrodda avsändare. *Spear phishing* är en riktad nätfiskeattack som använder mycket fokuserat och anpassat innehåll som är särskilt anpassat till de riktade mottagarna (vanligtvis efter spaning på mottagarna av angriparen).

- Du är global administratör eller säkerhetsadministratör

I Attack Simulator finns två olika typer av nätfiskekampanjer för spjut:

- [Multifaktorautentisering/villkorlig åtkomst](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) är aktiverat för åtminstone det globala administratörskontot och säkerhetsadministratörerna som ska använda Attack Simulator. (Helst är multifaktorautentisering/villkorlig åtkomst aktiverad för alla användare i organisationen.)

  - En standardsida som förklarar detta var bara ett test och ger tips om hur du känner igen nätfiskemeddelanden.

    ![Vad användarna ser om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - En anpassad sida (URL) som du anger.

- **Spear phishing (bilaga)**: Attacken försöker övertyga mottagarna att öppna en .docx eller .pdf-bilaga i meddelandet. Den bifogade filen innehåller samma innehåll från standardlänken för nätfiske, men den första meningen börjar med " \<Display Name\> visas det här meddelandet som ett nytt e-postmeddelande som du öppnade...".

> [!NOTE]
> För närvarande upphör inte spjutfiskekampanjer i Attack Simulator.

### <a name="create-a-spear-phishing-campaign"></a>Skapa en nätfiskekampanj för spjut

En viktig del av en spjutfiskekampanj är utseendet på det e-postmeddelande som skickas till de riktade mottagarna. Om du vill skapa och konfigurera e-postmeddelandet har du följande alternativ:

- **Använd en inbyggd e-postmall:** Två inbyggda mallar finns tillgängliga: **Pris giveaway** och **lön Uppdatering**. Du kan ytterligare anpassa vissa, alla eller ingen av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa en återanvändningsbar e-postmall**: När du har skapat och sparat e-postmallen kan du använda den igen i framtida nätfiskekampanjer. Du kan ytterligare anpassa vissa, alla eller ingen av e-postegenskaperna från mallen när du skapar och startar kampanjen.

- **Skapa e-postmeddelandet i guiden**: Du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar nätfiskekampanjen för spjutet.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Steg 1 (valfritt): Skapa en anpassad e-postmall

Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.

1. Gå till simulator för **angreppshantering** för & säkerhet i \> **Attack simulator**säkerhetsorganisationscenter .

2. Klicka på **Attackinformation**i avsnitten **Spear Phishing (Credentials Harvest)** eller **Spear Phishing (Attachment)** på sidan **Simulera attacker.**

   Det spelar ingen roll var du skapar mallen. De tillgängliga alternativen i mallen är desamma för båda typerna av nätfiskeattacker.

3. Klicka på **Ny mall**i avsnittet Skapa mallar i avsnittet **Skapa mallar** på sidan **Attackinformation** som öppnas. **Create Templates**

4. Guiden **Konfigurera nätfiskemall** börjar i ett nytt utfällbart utfällbart. I steget **Start** anger du ett unikt visningsnamn för mallen och klickar sedan på **Nästa**.

5. Konfigurera följande inställningar i steget **Konfigurera e-postinformation:**

   - **Från (Namn)**: Visningsnamnet som används för meddelandeavsändaren.

   - **Från (E-post)**: Avsändarens e-postadress.

   - **Url till nätloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Detta är webbadressen som användarna kommer att frestas att klicka. Alternativen är:

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
     > <ul><li>Alla webbadresser är avsiktligt http, inte https.</li><li>En URL-ryktestjänst kan identifiera en eller flera av dessa webbadresser som osäkra. Kontrollera tillgängligheten för webbadressen i webbläsare som stöds innan du använder webbadressen i en nätfiskekampanj.</li></ul>

   - **Url till anpassad målsida**: Ange en valfri målsida där användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter. Den här länken ersätter standardmålsidan. Om du till exempel har intern medvetenhetsutbildning kan du ange webbadressen här.

   - **Kategori**: För närvarande används inte den här inställningen (allt du anger ignoreras).

   - **Ämne**: **Fältet Ämne** i e-postmeddelandet.

   När du är klar klickar du på **Nästa**.

6. Skapa meddelandetexten för e-postmeddelandet i steget **Skriv e-post.** Du kan använda fliken **E-post** (en rtf-redigerare) eller fliken **Källa** (rå HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du behöver den för att vara. Du kan infoga bilder och text för att förbättra meddelandets trovärdighet i mottagarens e-postklient.

   - `${username}`infogar mottagarens namn.

   - `${loginserverurl}`**Url-värdet för nätfiske inloggningsservern** infogas från föregående steg.

   När du är klar klickar du på **Nästa**.

7. Klicka på **Slutför**i steget **Bekräfta.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Steg 2: Skapa och starta nätfiskekampanjen för spjut

1. Gå till simulator för **angreppshantering** för & säkerhet i \> **Attack simulator**säkerhetsorganisationscenter .

2. På sidan **Simulera attacker** gör du något av följande val baserat på vilken typ av kampanj du vill skapa:

   - Klicka på **Starta attack** i avsnittet **Spear Phishing (Credentials Harvest)** eller klicka på **Attack Details** \> **Attackinformation Launch Attack**.

   - Klicka på **Starta attack** i avsnittet **Spear Phishing (Attachment).** **Attack Details** \> **Launch Attack**

3. Guiden **Konfigurera nätfiskeattack** startar i ett nytt utfällbart utfällbart. Gör **Start** något av följande i startsteget:

   - Ange ett unikt visningsnamn för kampanjen i rutan **Namn.** Klicka inte på **Använd mall**eftersom du skapar e-postmeddelandet senare i guiden.

   - Klicka på **Använd mall** och välj en inbyggd eller anpassad e-postmall. När du har valt mallen fylls rutan **Namn** automatiskt baserat på mallen, men du kan ändra namnet.

   ![Startsida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   När du är klar klickar du på **Nästa**.

4. Gör något av följande i steget **Målmottagare:**

   - Klicka på **Adressbok** om du vill välja mottagare (användare eller grupper) för kampanjen. Varje riktad mottagare måste ha en Exchange Online-postlåda. Om du klickar på **Filtrera** och **tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka på **Importera** och sedan **Filimport** om du vill importera ett kommaavgränsat värde (CSV) eller radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   När du är klar klickar du på **Nästa**.

5. Konfigurera följande inställningar i steget **Konfigurera e-postinformation:**

   Om du har valt en mall i **startsteget** är de flesta av dessa värden redan konfigurerade, men du kan ändra dem.

   - **Från (Namn)**: Visningsnamnet som används för meddelandeavsändaren.

   - **Från (E-post)**: Avsändarens e-postadress. Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän, eller så kan du ange en verklig eller falsk extern e-postadress. En giltig e-postadress för avsändaren från organisationen kommer faktiskt att matchas i mottagarens e-postklient.

   - **Url till nätloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan. Detta är webbadressen som användarna kommer att frestas att klicka. Alternativen är:

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
     > <ul><li>Alla webbadresser är avsiktligt http, inte https.</li><li>En URL-ryktestjänst kan identifiera en eller flera av dessa webbadresser som osäkra. Kontrollera tillgängligheten för webbadressen i webbläsare som stöds innan du använder webbadressen i en nätfiskekampanj.</li><li>Du måste välja en webbadress. För kampanjer <b>med spearfiske (bifogad fil)</b> kan du ta bort länken från meddelandets brödtext i nästa steg (annars innehåller meddelandet både en länk <b>och</b> en bifogad fil).</li></ul>

   - **Typ av bifogade filer**: Den här inställningen är endast tillgänglig i **spearfiskekampanjer (bifogad fil).** Klicka på listrutan och välj **. DOCX** eller **. PDF** från listan.

   - **Namn på bifogade filer**: Den här inställningen är endast tillgänglig i **spearfiskekampanjer (bifogad fil).** Ange ett filnamn för bifogad fil i .docx eller .pdf.

   - **Url till anpassad målsida**: Ange en valfri målsida där användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter. Den här länken ersätter standardmålsidan. Om du till exempel har intern medvetenhetsutbildning kan du ange webbadressen här.

   - **Ämne**: **Fältet Ämne** i e-postmeddelandet.

   När du är klar klickar du på **Nästa**.

6. Skapa meddelandetexten för e-postmeddelandet i steget **Skriv e-post.** Om du har valt en mall i **startsteget** är meddelandetexten redan konfigurerad, men du kan anpassa den. Du kan använda fliken **E-post** (en rtf-redigerare) eller fliken **Källa** (rå HTML-kod).

   HTML-formateringen kan vara så enkel eller komplex som du behöver den för att vara. Du kan infoga bilder och text för att förbättra meddelandets trovärdighet i mottagarens e-postklient.

   - `${username}`infogar mottagarens namn.

   - `${loginserverurl}`Url-värdet för **nätfiske inloggningsservern** infogas.

   För kampanjer **med nätfiske (bifogad fil)** bör du ta bort länken från meddelandets brödtext (annars innehåller meddelandet både en länk **och** en bifogad fil och länkklick spåras inte i en kampanj för bifogade filer).

   ![Skriv e-postkropp](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   När du är klar klickar du på **Nästa**.

7. Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen. Nätfiskemeddelandet levereras till de riktade mottagarna.

## <a name="password-attack-campaigns"></a>Kampanjer för lösenordsattacker

En *lösenordsattack* försöker gissa lösenord för användarkonton i en organisation, vanligtvis efter att angriparen har identifierat ett eller flera giltiga användarkonton.

I Attack Simulator är två olika typer av lösenordsattackkampanjer tillgängliga för dig att testa komplexiteten i användarnas lösenord:

- **Brute force lösenord (ordbok attack)**: En *brute force* eller *ordbok* attack använder en stor ordbok fil av lösenord på ett användarkonto med hopp om att en av dem kommer att fungera (många lösenord mot ett konto). Felaktiga lösenordsspärrar hjälper till att avskräcka attacker mot brute force-lösenord.

  För ordlisteattacken kan du ange ett eller flera lösenord som ska provas (manuellt inmatat eller i en uppladdad fil) och du kan ange en eller flera användare.

- **Lösenord spray attack:** Ett *lösenord spray* attack använder samma noggrant genomtänkta lösenord mot en lista över användarkonton (ett lösenord mot många konton). Lösenord spray attacker är svårare att upptäcka än brute force lösenord attacker (sannolikheten för framgång ökar när en angripare försöker ett lösenord över dussintals eller hundratals konton utan risk för att snubbla användarens felaktiga lösenord lock-out).

  För lösenordssprayattacken kan du bara ange ett lösenord att prova, och du kan ange en eller flera användare.

> [!NOTE]
> Lösenordsattackerna i Attack Simulator skickar användarnamn och lösenord Grundläggande auth-begäranden till en slutpunkt, så de fungerar också med andra autentiseringsmetoder (AD FS, lösenordshösksynkronisering, vidaregång, PingFederate, etc.). För användare som har MFA aktiverat, även om **lösenordsattacken** försöker sitt faktiska lösenord, kommer försöket alltid att registrera sig som ett fel (med andra ord kommer MFA-användare aldrig att visas i antalet lyckade försök för kampanjen). Detta är det förväntade resultatet. MFA är en primär metod för att skydda mot lösenordsattacker.

### <a name="create-and-launch-a-password-attack-campaign"></a>Skapa och starta en kampanj för lösenordsattack

1. Gå till simulator för **angreppshantering** för & säkerhet i \> **Attack simulator**säkerhetsorganisationscenter .

2. På sidan **Simulera attacker** gör du något av följande val baserat på vilken typ av kampanj du vill skapa:

   - Klicka på **Starta attack** i avsnittet Brute Force **Password (Dictionary Attack)** eller klicka på **Attack Details** \> **Attackinformation Launch Attack**.

   - I avsnittet **Lösenord spray attack,** klicka **på Starta attack** eller klicka på Attack **Detaljer** \> **Launch Attack**.

3. Guiden **Konfigurera lösenordsattack** startar i ett nytt utfällbart alternativ. I steget **Start** anger du ett unikt visningsnamn för kampanjen och klickar sedan på **Nästa**.

4. Gör något av följande i steget **Rikta användare:**

   - Klicka på **Adressbok** om du vill välja mottagare (användare eller grupper) för kampanjen. Varje riktad mottagare måste ha en Exchange Online-postlåda. Om du klickar på **Filtrera** och **tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.

   - Klicka på **Importera** och sedan **Filimport** om du vill importera ett kommaavgränsat värde (CSV) eller radavgränsad fil med e-postadresser. Varje rad måste innehålla mottagarens e-postadress.

   När du är klar klickar du på **Nästa**.

5. I steget **Välj attackinställningar** väljer du vad du ska göra baserat på kampanjtypen:

   - **Brute Force Password (Dictionary Attack)**: Gör något av följande steg:

     - **Ange lösenord manuellt**: Skriv ett lösenord i rutan **Tryck på retur för att lägga till ett lösenord** och tryck sedan på RETUR. Upprepa det här steget så många gånger det behövs.

     - **Ladda upp lösenord från en ordlistefil:** Klicka på **Ladda upp** om du vill importera en befintlig textfil som innehåller ett lösenord på varje rad och en tom sista rad. Textfilen måste vara 10 MB eller mindre stor och får inte innehålla fler än 3 0000 lösenord.

   - **Lösenord spray attack:** I **det lösenord (er) att använda i attackrutan,** ange ett lösenord.

   När du är klar klickar du på **Nästa**.

6. Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen. De angivna lösenorden provas på användare som du har angett.

## <a name="view-campaign-results"></a>Visa kampanjresultat

När du har startat en kampanj kan du kontrollera förloppet och resultaten på huvudsidan **för simulera attacker.**

Aktiva kampanjer visar ett statusfält, ett slutfört procentvärde och antalet "(slutförda användare) (totalt antal användare).Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count. Om du klickar på knappen **Uppdatera** uppdatera uppdateras förloppet för alla aktiva kampanjer. Du kan också klicka på **Avsluta** för att stoppa en aktiv kampanj.

När kampanjen är klar ändras statusen till **Attack slutförd**. Du kan visa resultatet av kampanjen genom att utföra någon av följande åtgärder:

- Klicka på **Visa rapport** under namnet på kampanjen på sidan **Simulera attacker.**

- På sidan Simulera **attacker** för huvudformat klickar du på **Attackinformation** i avsnittet för typen av attack. På sidan **Attackinformation** som öppnas väljer du kampanjen i avsnittet **Attackhistorik.**

Någon av de tidigare åtgärderna tar dig till en sida med namnet **Attackinformation**. Den information som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Kampanjresultat för Spear Phishing (Credentials Harvest)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).

- **Totalt antal användare riktade**

- **Lyckade försök**: Antalet användare som klickade på länken **och** angav sina autentiseringsuppgifter *(alla* användarnamn och lösenordsvärde).

- **Total framgång:** En procentsats som beräknas av **Lyckade försök**  /  **Totalt antal användare som är inriktade på**.

- **Snabbaste klick:** Hur lång tid det tog den första användaren att klicka på länken efter att du startat kampanjen.

- **Genomsnittligt klick:** Summan av hur lång tid det tog för alla att klicka på länken dividerat med antalet användare som klickade på länken.

- **Klicka på Framgång:** En procentsats som beräknas av (antal användare som klickade på länken) / **Totalt antal användare riktade**.

- **Snabbaste autentiseringsuppgifter:** Hur lång tid det tog för den första användaren att ange sina autentiseringsuppgifter efter att du startat kampanjen.

- **Genomsnittlig autentiseringsuppgifter:** Summan av hur lång tid det tog för alla att ange sina autentiseringsuppgifter dividerat med antalet användare som angett sina autentiseringsuppgifter.

- **Autentiseringsuppgifter Framgång:** En procentsats som beräknas av (antal användare som angett sina autentiseringsuppgifter) / **Totalt antal användare riktade**.

- Ett stapeldiagram som visar **länken klickade** på och **Autentiseringsuppgifter som anges** nummer per dag.

- Ett cirkeldiagram som visar **länken klickade på**, **Autentiseringsuppgifter som angetts**och **Inga** procentsatser för kampanjen.

- Avsnittet **Komprometterade användare** visar information om de användare som klickade på länken:

  - Användarens e-postadress

  - Datum/tid då de klickade på länken.

  - Klientens IP-adress.

  - Information om användarens version av Windows och webbläsare.

  Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="spear-phishing-attachment-campaign-results"></a>Kampanjresultat för Spear Phishing (Attachment)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).

- **Totalt antal användare riktade**

- **Lyckade försök**: Antalet användare som öppnade eller hämtade och öppnade den bifogade filen (förhandsgranskning räknas inte).

- **Total framgång:** En procentsats som beräknas av **Lyckade försök**  /  **Totalt antal användare som är inriktade på**.

- **Snabbaste öppen tid för bifogade filer**: Hur lång tid det tog för den första användaren att öppna den bifogade filen när du startade kampanjen.

- **Genomsnittlig öppen tid för bifogade filer**: Summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade bilagan.

- **Bifogad fil öppen framgång:** En procentsats som beräknas av (antal användare som öppnade bilagan) / **Totalt antal användare riktade**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Kampanjresultat för Brute Force Password (Dictionary Attack)

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).

- **Totalt antal användare riktade**

- **Lyckade försök**: Antalet användare som visade sig använda ett av de angivna lösenorden.

- **Total framgång:** En procentsats som beräknas av **Lyckade försök**  /  **Totalt antal användare som är inriktade på**.

- I avsnittet **Komprometterade användare** visas de berörda användarnas e-postadresser. Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.

### <a name="password-spray-attack-campaign-results"></a>Kampanjresultat för lösenordssprayattack

Följande information finns på sidan **Attackinformation** för varje kampanj:

- Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).

- **Totalt antal användare riktade**

- **Lyckade försök**: Antalet användare som visade sig använda det angivna lösenordet.

- **Total framgång:** En procentsats som beräknas av **Lyckade försök**  /  **Totalt antal användare som är inriktade på**.
