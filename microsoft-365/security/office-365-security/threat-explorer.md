---
title: Threat Explorer och real tids identifiering
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Lär dig hur du använder Utforskaren och real tids identifiering i &amp; Center för säkerhets kontroll för att undersöka och reagera på hot effektivt och effektivt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4220c850e5ef7f830f7fc6ec57bb220cca29eaf4
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47322046"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer och real tids identifiering

Om din organisation har [office 365 Avancerat skydd](office-365-atp.md) (Office 365 ATP) och du har de [nödvändiga behörigheterna](#required-licenses-and-permissions)har du antingen **Explorer** **-eller real tids identifiering** (tidigare *real tids rapporter* – [se vad som är nytt](#new-features-in-threat-explorer-and-real-time-detections)!). Gå till **Threat Management**i säkerhets & efterlevnad och välj sedan **Utforskaren** _eller_ **identifiering av real tid**.

|Med ATP-abonnemang 2 ser du:|Med ATP-abonnemang 1 ser du:|
|---|---|
|![Threat Explorer](../../media/threatmgmt-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

Med Explorer (eller real tids identifieringar) har du en kraftfull rapport som gör det möjligt för säkerhets åtgärds gruppen att undersöka och reagera på hot effektivt och effektivt. Rapporten ser ut ungefär så här:

![Gå till Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Med den här rapporten kan du:

- [Se malware identifieras av Microsoft 365-säkerhetsfunktioner](#see-malware-detected-in-email-by-technology)
- [Visa data om nät fiske adresser och klicka på Verdict](#view-data-about-phishing-urls-and-click-verdict)
- [Starta en automatiserad undersökning och svars process från en vy i Utforskaren](#start-automated-investigation-and-response) (endast ATP-abonnemang 2)
- ... [Undersök skadlig e-post och mycket mer](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Upplev förbättringar av Threat Explorer och identifiering i real tid

Som en del av att förbättra jakt processen har vi gjort några uppdateringar för Threat Explorer och identifiering av real tid. Det här är en "Experience" förbättringar, med fokus på att göra jakt upplevelsen mer enhetlig. Dessa ändringar beskrivs nedan:

- [Förbättringar av tidszon](#timezone-improvements)
- [Uppdatera i uppdaterings processen](#update-in-the-refresh-process)
- [Diagram specificering att lägga till i filter](#chart-drilldown-to-add-to-filters)
- [Uppdateringar av produkt information](#in-product-information-updates)

### <a name="timezone-improvements"></a>Förbättringar av tidszon

Vi kommer att Visa tids zonen för e-postmeddelandena i portalen samt för exporterade data. Tids zonen visas i upplevelser som e-postrutnät, information utfällbar, e-posttids linje och liknande e-postmeddelanden, så att tids zonen för resultat uppsättningen är klar för användaren.

![Visa tids zonen i Utforskaren](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Uppdatera i uppdaterings processen

Vi har hört att få feedback kring förvirring med automatisk uppdatering (t. ex. för datum så fort du ändrar datumet kommer sidan att uppdateras) och manuell uppdatering (för andra filter). På samma sätt kan borttagning av filter leda till automatisk uppdatering, vilket gör att situationer där det går att ändra de olika filtren när du ändrar frågan är inkonsekventa Sök upplevelser. För att lösa det här flyttar vi till en manuell filtrerings funktion.
Från en miljö synpunkt kan användaren tillämpa och ta bort det olika intervallet med filter (från filter uppsättning och datum) och klicka på knappen Uppdatera för att filtrera resultaten när de har definierats. Knappen Uppdatera har också uppdaterats så att den visas tydligt på skärmen. Vi har också uppdaterat beskrivningar och dokumentation i produkten kring den här ändringen.

![Klicka på Uppdatera för att filtrera resultat](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Diagram specificering att lägga till i filter

Du kommer nu att kunna Klicka på diagrammets serie värden för att lägga till det värdet som ett filter. Observera att du fortfarande måste klicka på knappen Uppdatera för att filtrera resultaten som en del av ändringen som beskrivs ovan.

![Filtrera fram diagram](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Uppdateringar av produkt information

Du bör också läsa mer om produkten. Det totala antalet Sök resultat inom rutnätet (se nedan), samt förbättringar kring etiketter, fel meddelanden och beskrivningar, för att ge mer information kring filter, Sök funktioner och resultat uppsättning.

![Visa information om produkten](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Utökade funktioner i Threat Explorer

### <a name="top-targeted-users"></a>Vanligaste riktade användare

Idag står det för en lista över de vanligaste riktade användarna i vyn mot skadlig kod för e-postmeddelanden (i den övre delen av familjen med skadlig kod). Vi kommer att utöka den här vyn i Phish och alla e-postvyer, där du kan se de fem vanligaste användarna tillsammans med antalet försök för varje användare för motsvarande vy (till exempel för Phish-vy kan du se antalet Phish-försök).
Du kan också exportera listan med riktade användare till en gräns på 3000 tillsammans med antalet försök för offline-analys för varje e-postvy. Det är bara att välja Nej. av försök (till exempel 13 försök nedan) öppnar en filtrerad vy i Threat Explorer så att du kan titta på mer information i alla e-postmeddelanden och hot för den användaren. 

![Vanligaste riktade användare](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a>Exchange Transport-regler
Som en del av data berikning bör du även kunna se alla olika transport regler som används för ett meddelande. Den här informationen visas i vyn e-post-rutnät (om du vill visa det väljer du kolumn alternativ i rutnätet och Lägg till Exchange-transportläge från kolumn alternativen i rutnätet) samt information som visas i e-postmeddelandet.
Du kan se både GUID och namnet på de transport regler som har lagts till i meddelandet. Dessutom kan du söka efter meddelanden med hjälp av namnet på transport regeln. Det här är en "innehåller"-sökning vilket innebär att du kan söka i vissa sökningar. 

#### <a name="important-note"></a>Viktigt Obs! 
Exchange Sök-och namn tillgänglighet beror på vilken roll som har tilldelats dig. Du måste ha någon av följande roller/behörigheter för att kunna visa Exchange namn och sökning.  Om du inte har någon av följande roller kopplade till dig kan du inte se namnen på transport reglerna och söka efter meddelanden med hjälp av Exchange-namnen. Men du kan se Exchange etikett och GUID-information i e-postinformationen. Det går inte att visa poster i e-postrutnät, e-flyouts, filter och export påverkas inte. 
 
- Endast EXO – förhindra data förlust: alla
- Endast EXO-O365SupportViewConfig: alla
- AAD eller EXO-säkerhets administratör: alla
- AAD eller EXO – säkerhets läsare: alla
- Endast EXO – transport regler: alla
- Endast EXO-endast visning-konfiguration: alla

I e-postrutnätet, den utfällbara informationen och exporterad CSV-fil visas ETR med ett namn/GUID som visas nedan. 

![Exchange Transport-regler](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Inkommande kopplingar 

Kopplingar är en samling instruktioner som anpassar hur din e-post flödar till och från din Microsoft 365-eller Office 365-organisation, med möjligheten att tillämpa säkerhets begränsningar eller kontroller. I Threat Explorer kan du nu Visa kopplingarna som är relaterade till ett e-postmeddelande och söka efter e-postmeddelanden med hjälp av kopplings namnen. Sök efter anslutningar är "innehåller", vilket innebär att ofullständiga nyckelords sökningar också fungerar. I vyn huvud rutnät, den utfällbara informationen och den exporterade CSV-filen visas kopplingarna i namn/GUID-formatet enligt nedan: 

![Anslutnings information](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nya funktioner i Threat Explorer och identifiering av real tid

Tre nya funktioner läggs till i Threat Explorer och real tids identifiering:

- [Förhandsgranska e-posthuvud och hämta e-postmeddelande](#preview-email-header-and-download-email-body)
- [E-posttids linje](#email-timeline)
- [Exportera URL Klicka på data](#export-url-click-data)

Dessa nya funktioner beskrivs nedan.

### <a name="preview-email-header-and-download-email-body"></a>Förhandsgranska e-posthuvud och hämta e-postmeddelande

Möjligheten att förhandsgranska ett e-posthuvud och hämta e-postmeddelandet är nya funktioner som är tillgängliga i Threat Explorer. Administratörer kan analysera hämtade meddelandehuvuden/e-postmeddelanden för hot. Eftersom hämtning av e-postmeddelanden kan påverka exponeringen av informationen styrs processen av en rollbaserad åtkomst kontroll (RBAC). En ny roll, för *hands version*, måste läggas till i en annan roll grupp (som säkerhets åtgärder eller säkerhets administratör) för att tillåta möjligheten att hämta e-post och förhandsgranska rubriker i alla e-postmeddelanden.

Men Explorer (och real tids identifieringar) lägger också till nya fält som är utformade för att ge dig en mer fullständig bild av var e-postmeddelandena hamnar. En del av syftet med ändringen är att göra det lättare för säkerhetsledandet att skydda dig, men netto resultatet är att du snabbt kan se var det finns problem med e-postmeddelanden.

Hur gör du det här? Leverans status är nu uppdelad i två kolumner:

- **Leverans åtgärd** – vilken är statusen för det här meddelandet?
- **Leverans plats** – var hette detta e-postmeddelande som ett resultat?

Leverans åtgärden är den åtgärd som utförs via e-post på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som ett e-postmeddelande kan ta:

|Levereras|Skräp post|Blockering|Byta|
|---|---|---|---|
|E-postmeddelandet skickades till Inkorgen eller mappen för en användare och användaren kan komma åt den direkt.|E-postmeddelandet skickades till antingen en användares skräppost eller borttagna mapp och användaren har till gång till e-post i dessa mappar.|Alla e-postmeddelanden som har satts i karantän, som misslyckats eller tagits bort. Det här är fullständigt otillgängligt för användaren!|Alla e-postmeddelanden där skadliga bifogade filer ersätts med txt-filer som gör att den bifogade filen har skadligt.|

|Levereras|Skräp post|Blockering|Byta|
|---|---|---|---|
|E-postmeddelandet skickades till användarens inkorg eller till en annan mapp, och användaren kan komma åt den direkt.|E-postmeddelandet skickades antingen till användarens skräppostmappen eller mappen borttagen, och användaren har till gång till e-postmeddelanden i dessa mappar.|Alla e-postmeddelanden som har satts i karantän, som misslyckats eller tagits bort och inte är tillgängliga för användaren.|Alla e-postmeddelanden där skadliga bifogade filer ersattes med txt-filer som anger att de bifogade filerna var skadliga.|
|

Så här ser användaren vad de kan se och vad de inte kan:

|Tillgänglig för slutanvändare|Ej tillgänglig för slutanvändare|
|---|---|
|Levereras|Blockering|
|Skräp post|Byta|

Leverans platsen visar resultaten av principer och upptäckter med efter-leverans. Den är länkad till en leverans åtgärd. Det här fältet lades till för att ge insyn i den åtgärd som utförs när ett problem har uppstått. Här är möjliga värden för leverans plats:

- **Inkorgen eller mapp**: e-postmeddelandet finns i Inkorgen eller i en mapp (enligt dina e-postregler).
- **On-lokala eller external**: post lådan finns inte i molnet, men den är lokal.
- **Skräppostmappen**: e-postmeddelandet finns i skräppostmappen för en användare.
- **Mappen Borttaget**: e-post i mappen Borttaget för en användare.
- **Karantän**: e-postmeddelandet i karantän och finns inte i en användares post låda.
- **Misslyckades**: det gick inte att nå post lådan.
- **Släppt**: e-postmeddelandet tappas bort någonstans i e-postflödet.

### <a name="email-timeline"></a>E-posttids linje

**E-Posttids linjen** är en ny Explorer-funktion som syftar till att förbättra jakt upplevelsen för administratörer. Den minskar med slumpmässigheten eftersom det är mindre tid att kontrol lera olika platser för att försöka förstå händelsen. När flera händelser inträffar till, eller nära till, samma tid i ett e-postmeddelande, visas händelserna i vyn tids linje. Vissa händelser som inträffar efter leverans till din e-post sparas i förhållande till "särskild åtgärd"-kolumnen. Om du kombinerar informationen från tids linjen för det e-postmeddelandet med den speciella åtgärden som utförs på post-leveransen får administratörer inblick i hur deras principer fungerar, där e-postmeddelandet slutligen skickades och, i vissa fall, vad den slutliga utvärderingen var.

Mer information om hur du undersöker illasinnade e-postmeddelanden finns i [undersöka och åtgärda skadlig e-post som har levererats i Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportera URL Klicka på data

Du kan då nu exportera rapporter för URL-musklick till Microsoft Excel för att visa både deras nätverks meddelande-ID och deras Klicka på Verdict, så att du kan förstå var din URL-adress klicka på trafik har blivit enklare. Så här fungerar det. Starta med Threat Management i snabb start för Office 365 genom att klicka igenom den här kedjan:

**Utforskaren** \> **Visa Phish** \> **Klickar på** \> **De översta URL-adresserna eller webb adressen** \> **Klicka på en post för att öppna webb adressen**

När du klickar på en URL-adress i listan visas en ny exportera-knapp på panelen utflygande. Använd den här knappen för att flytta data till ett Excel-kalkylblad för enklare rapportering.

Du kan komma till samma plats i rapporten för rapporter i real tid så här:

**Utforskaren** \> **Real tids identifiering** \> **Visa Phish** \> **URL: er** \> **Översta URL-adresser eller högst upp** \> **Klicka på en post för att öppna webb adressen** \> **Gå till fliken klickningar.**

> [!TIP]
> Nätverks meddelande-ID mappar Klicka på tillbaka till specifika e-postmeddelanden när du söker via Utforskaren eller tillhör ande tredje parts verktyg via nätverks meddelande-ID. Om du söker igenom nätverks meddelande-ID: t får administratörer det specifika e-postmeddelandet som är associerat med ett Klicka Vid exporten blir samarbeten av ID för nätverks meddelande-ID för snabb och mer effektiv analys.

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Se malware identifierat i e-post efter teknik

Anta att du vill se hur skadlig kod identifieras i e-post, av Microsoft 365-teknologi. För att göra det här använder du [e-postmeddelandet med > skadlig program vara](threat-explorer-views.md#email--malware) för Explorer (eller real tids identifiering).

1. [https://protection.office.com](https://protection.office.com)Välj **Threat Management**  >  **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **View** **e-**  >  **postmalware**på Visa-menyn.

   ![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicka på **avsändare**och välj sedan **grundläggande**  >  **identifierings teknik**.

   Din identifierings teknik är nu tillgänglig som filter för rapporten.

   ![Tekniker för identifiering av skadlig program vara](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Välj ett alternativ och klicka sedan på knappen **Uppdatera** för att tillämpa filtret.

   ![Vald identifierings teknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Rapporten uppdateras för att visa resultatet skadlig program vara som identifieras i e-post, med det teknik alternativ du valt. Härifrån kan du göra ytterligare analyser.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visa data om nät fiske adresser och klicka på Verdict

Anta att du vill se nät fiske försök via URL: er via e-post, inklusive en lista med URL-adresser som tilläts, blockerades och åsidosatts. Om du vill konfigurera URL-adresser som har klickats måste du ha ett [ATP Safe Links](atp-safe-links.md) . Kontrol lera att du har ställt in [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md) för att kunna Klicka på skydd och loggning av Klicka Verdicts via säkra Länkar för ATP.

Om du vill granska Phish URL-adresser i meddelanden och klickar på URL: er i Phish meddelanden använder du [e-post> Phish](threat-explorer-views.md#email--phish) vyn av Utforskaren (eller real tids identifieringar).

1. [https://protection.office.com](https://protection.office.com)Välj **Threat Management**  >  **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **e-** Phish på **Visa** -menyn  >  **Phish**.

   ![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicka på **avsändare**och välj **URL-adresser**  >  **på Verdict**.

4. Välj ett eller flera alternativ, till exempel **blockerat** och **blockera**, och klicka sedan på knappen **Uppdatera** på samma rad som de alternativ som används för att tillämpa filtret. (Uppdatera inte webbläsarfönstret.)

   ![URL: er och klicka på verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    Rapporten uppdateras och visar två olika URL-tabeller på fliken URL under rapporten:

   - De **vanligaste URL** -adresserna är de URL-adresser som visas i de meddelanden som du har filtrerat ned till och hur många e-postleveranser som är tillgängliga I Phish e-postvy innehåller listan normalt legitima URL: er. Attackerare inkluderar en blandning av bra och dåliga URL-adresser i sina meddelanden för att försöka komma åt dem, men de tar bort de skadliga länkarna mer intressant för användaren att klicka på. Tabellen med URL-adresser sorteras efter totalt antal e-postmeddelanden (men Observera att den här kolumnen är dold för att förenkla vyn).

   - De **bästa klickningarna** är de inkapslade länkarna som du har klickat på, sorterat efter totalt antal klickningar (den här kolumnen visas inte för att förenkla vyn). Kolumnen totalt antal gånger visar de säkra länkarna Klicka på Verdict antal för varje klickning-URL. I Phish e-postvy är de oftare misstänkta eller illasinnade webb adresser, men kan innehålla URL-adresser som inte är Hot men som är i Phish meddelanden. URL-klickningar på ej figursatta länkar visas inte här.

   I de två URL-tabellerna visas de högsta URL-adresserna i phishing-e-postmeddelanden efter leverans åtgärd och plats, och de visar URL-klickningar som har blockerats (eller som besökts trots en varning) så att du kan förstå vilka potentiella felaktiga länkar som användare har fått och interagerat med av användare. Härifrån kan du göra ytterligare analyser. Under diagrammet kan du till exempel se de högsta URL-adresserna i e-postmeddelanden som har blockerats i organisationens miljö.

   ![Explorer-URL: er som blockerats](../../media/ExplorerPhishClickVerdictURLs.png)

   Välj en URL för att visa mer detaljerad information.

   > [!NOTE]
   > I dialog rutan URL-utfällbar text tas filtreringen av e-postmeddelanden bort så att du får fullständig vy över URL-vyns exponering i miljön. Med den här funktionen kan du filtrera ned e-postmeddelanden i Utforskaren till dem du är orolig för, hitta specifika URL-adresser som är potentiella hot och sedan utöka din förståelse av URL-exponeringen i din miljö (via dialog rutan URL-information) utan att behöva lägga till URL-filter i själva Utforskarvyn.


**Tolkning av olika klick verdicts**

I e-postmeddelandet eller URL-flyouts, de viktigaste tryckningarna samt i vår filter upplevelse ser du olika klick värden som en del av din jakt upplevelse. I det här avsnittet kan du välja Verdicts och deras tolkning:

- **Ingen**: det gick inte att skapa Verdict för URL-adressen. Användaren kanske har klickat via webb adressen.
- **Tillåten**: användaren har fått åtkomst till URL-adressen.
- **Blockerat**: användaren hindrades från att navigera till webb adressen.
- **Väntande Verdict**: användaren har presenter ATS med den väntande sidan för Sprängaren.
- **Blockerad åsidosatt**: användaren hindrades från att gå till URL-adressen. användaren overrode dock att gå till URL-adressen.
- **Väntande Verdict förbigåde**: användaren uppvisade sig med sidan detonation; användaren overrode till sidan för att gå till URL-adressen.
- **Fel**: användaren uppvisade fel sidan. Det kan också betyda att det fanns ett fel när du hämtade Verdict.
- **Fel**: ett okänt undantag uppstod när du hämtade Verdict. Användaren kanske har klickat via webb adressen. 

## <a name="review-email-messages-reported-by-users"></a>Granska e-postmeddelanden som rapporter ATS av användare

Anta att du vill se e-postmeddelanden som användare i organisationen har rapporterat som skräp post, inte skräp post eller nätfiske med hjälp av [rapport tillägget för Outlook och Outlook på webben](enable-the-report-message-add-in.md). För att göra detta kan du använda [e-post>-](threat-explorer-views.md#email--submissions) vyn i Utforskaren (eller real tids identifieringar).

1. [https://protection.office.com](https://protection.office.com)Välj **Threat Management**  >  **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **View** **e-**  >  **postinlägg**i menyn Visa.

   ![Visa-menyn för Utforskaren](../../media/explorer-view-menu-email-user-reported.png)

3. Klicka på **avsändare**och välj sedan **enkel**  >  **typ av rapport**.

4. Välj ett alternativ, till exempel **Phish**, och klicka sedan på knappen **Uppdatera** .

   ![Användardefinierad Phish](../../media/EmailUserReportedReportType.png)

Rapporten uppdateras och visar information om e-postmeddelanden som personer i organisationen har rapporterat som ett nät fiske försök. Du kan använda den här informationen för att utföra ytterligare analyser och, om det behövs, justera dina [ATP-skydds principer](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Starta automatisk undersökning och svar

> [!NOTE]
> Automatiserade undersökningar och svars funktioner finns i **Office 365 ATP-abonnemang 2** och **Office 365 E5**.

(Ny!) Den [automatiska undersökningen och svaret](automated-investigation-response-office.md) kan spara säkerhets arbets gruppen i stort sett tid och ansträngning för att undersöka och begränsa cyberattacks. Förutom att konfigurera aviseringar som kan utlösa en säkerhets Playbook kan du starta en automatiserad undersökning och svars process från en vy i Utforskaren.

För mer information, se [exempel: en säkerhets administratör utlöser en undersökning från Utforskaren](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Fler sätt att använda Explorer (eller real tids identifiering)

Utöver de scenarier som beskrivs i den här artikeln finns det många fler rapporterings alternativ som är tillgängliga med Explorer (eller real tids identifieringar).

- [Hitta och undersöka skadlig e-post som har levererats](investigate-malicious-email-that-was-delivered.md)
- [Visa skadliga filer som identifieras i SharePoint Online, OneDrive och Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Få en översikt över vyerna i Threat Explorer (och identifieringar i real tid)](threat-explorer-views.md)
- [Automatisk undersökning och svar i skydd mot Microsoft Threat](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Nödvändiga licenser och behörigheter

Du måste ha [Office 365 ATP](office-365-atp.md) för att få Explorer eller real tids identifiering.

- Explorer ingår i Office 365 ATP-abonnemang 2.
- Rapporten om real tids identifiering ingår i Office 365 ATP-abonnemang 1.
- Planera för att tilldela licenser för alla användare som ska skyddas av Office 365 ATP. (Explorer eller real tids identifiering visar identifierings data för licensierade användare.)

Om du vill visa och använda Explorer-eller real tids identifiering måste du ha lämplig behörighet, till exempel en säkerhets administratör eller en säkerhets läsare.

- För säkerhetsrelaterade &amp; Center måste du ha någon av följande roller tilldelade:

  - Organisationshantering
  - Säkerhets administratör (detta kan tilldelas i Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Säkerhets läsare

- För Exchange Online måste du ha någon av följande roller tilldelade i antingen administrations centret för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) eller med PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Organisationshantering
  - Organisations hantering för endast visning
  - Rollen skrivskyddade mottagare
  - Hantering av efterlevnad

Mer information om roller och behörigheter finns i följande resurser:

- [Behörigheter i säkerhetsrelaterade &amp; Center](permissions-in-the-security-and-compliance-center.md)
- [Behörigheter för funktioner i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Skillnader mellan Threat Explorer och identifiering av real tid

- Rapporten om **identifiering av real tid** är tillgänglig i Office 365 ATP-abonnemang 1, medan **hot Explorer** är tillgängligt i Office 365 ATP-abonnemang 2.
- Med rapporten **real tids identifiering** kan du Visa identifieringar i real tid. **Threat Explorer** fungerar också, men du kan även visa ytterligare information om en viss attack.
- En **all e-** postvy är tillgänglig i **Threat Explorer** (och är inte med i rapporten om **identifiering i real tid** ).
- Fler filter funktioner och tillgängliga åtgärder ingår i **Threat Explorer**.

Mer information finns i avsnittet [Office 365 ATP Service Description: funktions tillgänglighet för abonnemang för avancerat hot Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
