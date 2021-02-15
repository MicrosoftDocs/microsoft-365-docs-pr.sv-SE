---
title: Hotutforskaren och identifieringar i realtid
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Använd identifieringar i Utforskaren och realtid i &amp; Säkerhetsefterlevnadscenter för att undersöka och reagera på hot effektivt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5cbb8bd57a2e9bde8d19c960a71066d3ea5531c1
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233648"
---
# <a name="threat-explorer-and-real-time-detections"></a>Hotutforskaren och identifieringar i realtid


**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Om din organisation har Microsoft Defender för Office [365](office-365-atp.md)och  du har nödvändiga behörigheter har  du antingen Utforskaren eller identifieringar i realtid **(tidigare** realtidsrapporter – se vad som är [nytt!](#new-features-in-threat-explorer-and-real-time-detections)). [](#required-licenses-and-permissions) I Säkerhets- & går du till **Hantering av** hot och väljer sedan Identifieringar i **Utforskaren**  **eller Realtid.**


|Med Microsoft Defender för Office 365 abonnemang 2 ser du:|Med Microsoft Defender för Office 365 abonnemang 1 ser du:|
|---|---|
|![Hotutforskaren](../../media/threatmgmt-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

Explorer eller identifiering i realtid hjälper din säkerhetsgrupp att undersöka och reagera på hot effektivt. Rapporten liknar följande bild:

![Gå till \> Hothanteringsutforskaren](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Med den här rapporten kan du:

- [Visa skadlig programvara som upptäckts av Säkerhetsfunktioner i Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Visa nätfiske-URL och klicka på bedömningsdata](#view-phishing-url-and-click-verdict-data)
- [Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren](#start-automated-investigation-and-response) (endast Defender för Office 365 abonnemang 2)
- [Undersöka skadlig e-post med mera](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Förbättringar av Hotutforskaren och identifieringar i realtid

### <a name="tags-in-threat-explorer"></a>Taggar i Hotutforskaren

> [!NOTE]
> Funktionen med användartaggar *är i förhandsversion,* är inte tillgänglig för alla och kan komma att ändras. Mer information om versionsschemat finns i Microsoft 365-översikten.

Användartaggar identifierar specifika grupper av användare i Microsoft Defender för Office 365. Mer information om taggar, inklusive licensiering och konfiguration, finns i [Användartaggar.](user-tags.md)

I Threat Explorer kan du se information om användartaggar i följande funktioner.

#### <a name="email-grid-view"></a>Rutnätsvy för e-post

Kolumnen **Taggar** i e-postrutnätet innehåller alla taggar som har tillämpats på avsändarens eller mottagarens postlådor. Som standard visas systemtaggar som prioritetskonton först.

> [!div class="mx-imgBorder"]
> ![Filtrera taggar i rutnätsvyn för e-post](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtrering

Du kan använda taggar som ett filter. Jaga bara på prioritetskonton eller specifika användartaggsscenarier. Du kan också utesluta resultat som har vissa taggar. Kombinera den här funktionen med andra filter för att begränsa undersökningens omfattning.

[![Filtertaggar](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Filtertaggar gäller inte](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Utfällnivå för e-postinformation
Om du vill visa de enskilda taggarna för avsändare och mottagare väljer du ett ämne för att öppna den utfällna meddelandeinformationen. På fliken **Sammanfattning** visas taggarna för avsändare och mottagare separat, om de finns för e-post.
Informationen om enskilda taggar för avsändare och mottagare omfattar även exporterade CSV-data, där du kan se den här informationen i två separata kolumner.

> [!div class="mx-imgBorder"]
> ![Taggar för e-postinformation](../../media/tags-flyout.png)

Information om taggar visas också i url-klickningens utfällsida. Om du vill visa den går du till vyn Phish eller All e-post och **sedan fliken URL-adresser** **eller URL-klickningar.** Välj en utfällsida för en enskild URL om du vill visa mer information om klickningar för URL-adressen, inklusive taggar kopplade till den klickningen.

> [!div class="mx-imgBorder"]
> ![URL-taggar](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Förbättringar av upplevelsen av hot efter hot (kommande)

### <a name="updated-threat-information-for-emails"></a>Uppdaterad information om hot för e-postmeddelanden

Vi har fokuserat på plattforms- och datakvalitetsförbättringar för att öka dataprecisionen och konsekvensen för e-postposter. Förbättringarna är bland annat konsolidering av information om förleverans och efterleverans, till exempel åtgärder som utförs på ett e-postmeddelande som en del av ZAP-processen, i en enda post. Ytterligare information som skräppostutskick, hot på entitetsnivå (till exempel vilken URL som var skadlig) och senaste leveransplatser ingår också.

Efter dessa uppdateringar visas en post för varje meddelande, oavsett vilka händelser efter leverans som påverkar meddelandet. Åtgärder kan omfatta ZAP, manuell åtgärd (vilket innebär administrativa åtgärder), dynamisk leverans och så vidare.

Förutom att visa skadlig programvara och nätfiskehot kan du se skräpposten som är kopplad till ett e-postmeddelande. I e-postmeddelandet ser du alla hot som är kopplade till e-postmeddelandet tillsammans med motsvarande identifieringsteknik. Ett e-postmeddelande kan innehålla noll, ett eller flera hot. Du ser de aktuella hoten i avsnittet Information i e-postmeddelandet.  För flera hot (till exempel skadlig  kod och nätfiske) visar det tekniska fältet Identifiering av hotmappningen, som är den identifieringsteknik som identifierade hoten.

Uppsättningen identifieringstekniker innehåller nu nya identifieringsmetoder och teknik för identifiering av skräppost. Du kan använda samma uppsättning identifieringstekniker för att filtrera resultatet i olika e-postvyer (skadlig kod, phish, all e-post).

> [!NOTE]
> Analys av analys av bedömningsanalys kanske inte nödvändigtvis är knuten till enheter. Ett e-postmeddelande kan till exempel klassificeras som phish eller spam, men det finns inga URL-adresser som är stämplade med ett phish/spam-bedömning. Det beror på att filtren också utvärderar innehåll och annan information för ett e-postmeddelande innan en bedömning tilldelas.

#### <a name="threats-in-urls"></a>Hot i URL:er

Nu kan du se det specifika hot som finns för en URL på den utfällade fliken Information för **e-post.** Hot kan vara skadlig *kod,* *nätt,* *skräppost* eller *ingen.)*

> [!div class="mx-imgBorder"]
> ![URL-hot](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Uppdaterad tidslinjevy (kommande)

> [!div class="mx-imgBorder"]
> ![Uppdaterad tidslinjevy](../../media/Email_Timeline.png)

Tidslinjevyn identifierar alla leverans- och efterleveranshändelser. Den innehåller information om hot som identifierats vid den tidpunkten för en delmängd av dessa händelser. I vyn Tidslinje finns också information om alla ytterligare åtgärder som vidtas (till exempel ZAP eller manuell åtgärd), tillsammans med resultatet av den åtgärden. Information om tidslinjevyn är bland annat:

- **Källa:** Källan till händelsen. Det kan vara admin/system/användare.
- **Händelse:** Innehåller händelser på högsta nivån som ursprunglig leverans, manuell åtgärd, ZAP, inskickade funktioner och dynamisk leverans.
- **Åtgärd:** Den specifika åtgärd som har vidtagits antingen som en del av ZAP- eller administratörsåtgärden (till exempel mjuk borttagning).
- **Hot:** Täcker de hot (skadlig kod, nätt och skräppost) som identifierades vid den tidpunkten.
- **Resultat/information:** Mer information om åtgärdens resultat, till exempel om det utfördes som en del av ZAP/administratörsåtgärd.

### <a name="original-and-latest-delivery-location"></a>Ursprunglig och senaste leveransplats

För närvarande surface vi leveransplats i e-postrutnätet och utfällfältet för e-post. Fältet **Leveransplats** får ett nytt namn **_på den ursprungliga leveransplatsen_*_. Och vi introducerar ett annat fält, _*_Senaste leveransplats._**

**Den ursprungliga leveransplatsen** ger mer information om var ett e-postmeddelande levererades från början. **Senaste leveransplats** kan ange var ett e-postmeddelande landade efter systemåtgärder som *ZAP* eller administrativa åtgärder som *Flytta till borttagna objekt.* Den senaste leveransplatsen är avsedd att meddela administratörerna meddelandets senast kända plats efter leverans eller eventuella system-/administratörsåtgärder. Den innehåller inga slutanvändaråtgärder för e-postmeddelandet. Om en användare till exempel tagit bort ett meddelande eller flyttat meddelandet till arkivering/pst uppdateras inte meddelandets leveransplats. Men om en systemåtgärd uppdaterade platsen (till exempel ZAP som resulterade i att ett e-postmeddelande flyttas till **karantän)** visades den senaste leveransplatsen som "karantän".

> [!div class="mx-imgBorder"]
> ![Uppdaterade leveransplatser](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Det finns några fall där åtgärden **Leveransplats** **och Leverans kan** visas som "okänd":
>
> - Du kan se **Leveransplats** som  "Levererat" och Leveransplats som "okänd" om meddelandet levererades, men en regel för Inkorgen flyttade meddelandet till en standardmapp (till exempel Utkast eller Arkiv) i stället för till Inkorgen eller mappen Skräppost.
>
> - **Senaste leveransplats** kan vara okänd om en åtgärd för administratör/system (till exempel ZAP) försöktes, men meddelandet hittades inte. Vanligtvis händer åtgärden efter att användaren flyttat eller tagit bort meddelandet. Kontrollera i så fall kolumnen **Resultat/Detaljer** i tidslinjevyn. Leta efter uttrycket "Meddelandet har flyttats eller tagits bort av användaren".

> [!div class="mx-imgBorder"]
> ![Leveransplatser för tidslinjen](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Ytterligare åtgärder

*Ytterligare åtgärder* tillämpades efter leverans av e-postmeddelandet. De kan omfatta *ZAP,* manuell åtgärd *(åtgärd* som vidtas av en administratör som mjuk *borttagning),* dynamisk leverans och ombearbetning *(för* e-postmeddelanden som retroaktivt identifierats som bra).

> [!NOTE]
> - Som en del av de väntande ändringarna försvinner värdet "Borttaget av ZAP" som visas i filtret Leveransåtgärd. Du kan söka efter all e-post med ZAP-försöket via **Ytterligare åtgärder.**
>
> - Det kommer att finnas nya fält och värden för **identifieringstekniker** **och ytterligare åtgärder (särskilt** för ZAP-scenarier). Du måste utvärdera dina befintliga sparade frågor och spårade frågor för att se till att de fungerar med de nya värdena.

> [!div class="mx-imgBorder"]

> ![Ytterligare åtgärder i Utforskaren](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>System åsidosätter

*Med system åsidosättningar* kan du göra undantag till den avsedda leveransplatsen för ett meddelande. Du åsidosätter leveransplatsen som tillhandahålls av systemet, baserat på hot och andra identifieringar som identifieras av filtreringsstacken. System åsidosättningar kan ställas in via klientorganisations- eller användarprincipen för att leverera meddelandet som föreslås av principen. En åsidosättning kan identifiera oavsiktlig leverans av skadliga meddelanden på grund av luckor i konfigurationen, till exempel en för omfattande princip för Betrodd avsändare som har angetts av en användare. Dessa åsidosättningsvärden kan vara:

- Tillåts av användarprincip: En användare skapar principer på postlådenivå för att tillåta domäner eller avsändare.
- Blockeras av användarprincip: En användare skapar principer på e-postråddsnivå för att blockera domäner eller avsändare.
- Tillåts i organisationens princip: Organisationens säkerhetsteam har angett principer eller Exchange-e-postflödesregler (kallas även transportregler) för att tillåta avsändare och domäner för användare i organisationen. Det kan vara för en uppsättning användare eller för hela organisationen.
- Blockeras av organisationens policy: Organisationens säkerhetsteam anger principer eller e-postflödesregler för att blockera avsändare, domäner, meddelandespråk eller käll-IP:er för användare i organisationen. Det kan tillämpas på en uppsättning användare eller hela organisationen.
- Filnamnstillägg som blockeras av organisationsprincipen: En organisations säkerhetsgrupp blockerar ett filnamnstillägg via inställningarna för policyn mot skadlig programvara. Värdena visas nu i e-postinformation som hjälp vid undersökningar. Sekopsteam kan också använda rtf-filtreringsfunktioner för att filtrera på blockerade filnamnstillägg.

[![System åsidosättningar i Utforskaren](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Rutnät för system åsidosättning i Utforskaren](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Förbättringar för URL- och klickupplevelsen

Förbättringarna är bland annat:

- Visa den fullständigt klickade URL:en (inklusive alla frågeparametrar som är en del av URL:en) i avsnittet **Klick** på den utfällliga URL-adressen. För närvarande visas URL-domänen och sökvägen i namnlisten. Vi utökar den informationen så att den fullständiga URL:en visas.

- Korrigeringar bland URL-filter *(URL-* eller *URL-domän* kontra *URL-domän* och sökväg): Uppdateringarna påverkar sökningen efter meddelanden som innehåller en URL-adress/klickning. Vi har aktiverat stöd för protokoll-agnostic-sökningar, så att du kan söka efter en URL utan att `http` använda. Som standard mappas URL-sökningen till http, om inte ett annat värde uttryckligen anges. Till exempel:

   -  Sök med och utan `http://` prefixet i **filterfälten URL,** **URL Domain** och URL Domain **och Path.** Sökningarna ska visa samma resultat.

   -  Sök efter `https://` prefixet i **URL.** När inget värde anges `http://` antas prefixet.

   - `/`ignoreras i början och slutet av **URL-sökvägen,** **URL-domän,** **URL-domän och sökvägsfält.** `/` i slutet av **URL-fältet** ignoreras.

### <a name="phish-confidence-level"></a>Phish konfidensnivå

Phish konfidensnivå hjälper till att identifiera graden av förtroende som ett e-postmeddelande kategoriserades som "phish". De två möjliga värdena är *Höga* och *Normal.* I de inledande stegen är filtret bara tillgängligt i Phish-vyn för Hotutforskaren.

[![Konfidensnivå för phish i Utforskaren](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL-signal

ZAP URL-signalen används vanligtvis för ZAP Phish-aviseringsscenarier där ett e-postmeddelande identifierades som Phish och togs bort efter leverans. Den här signalen ansluter aviseringen till motsvarande resultat i Utforskaren. Det är en av I/ICS för aviseringen.

Vi har uppdaterat Hot Explorer och identifieringar i realtid för att göra upplevelsen mer enhetlig för vis hela tiden. Ändringarna beskrivs här:

- [Förbättringar av tidszoner](#timezone-improvements)
- [Uppdatera i uppdateringsprocessen](#update-in-the-refresh-process)
- [Diagram, granska för att lägga till i filter](#chart-drilldown-to-add-to-filters)
- [I uppdateringar av produktinformation](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrera efter användartaggar

Nu kan du sortera och filtrera på system- eller anpassade användartaggar för att snabbt förstå omfattningen av hot. Mer information finns i [Användartaggar.](user-tags.md)

> [!IMPORTANT]
> Filtrering och sortering efter användartaggar är för närvarande en offentlig förhandsgranskning. Den här funktionen kan komma att ändras väsentligt innan den släpps kommersiellt. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som ges om den.

![Kolumnen Taggar i Utforskaren](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Förbättringar av tidszoner

Tidszonen för e-postposterna i portalen och för exporterade data visas. Den visas i funktioner som e-postrutnät, den utfällbara informationen, tidslinjen för e-post och liknande e-postmeddelanden, så tidszonen för resultatuppsättningen är tydlig.

> [!div class="mx-imgBorder"]
> ![Visa tidszon i Utforskaren](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Uppdatera i uppdateringsprocessen

Vissa användare har kommenterat att det är förvirrande med automatisk uppdatering (till exempel så fort du ändrar datumet, sidan uppdateras) och manuell uppdatering (för andra filter). På samma sätt leder borttagning av filter till automatisk uppdatering. Om du ändrar filter samtidigt som frågan ändras kan det orsaka inkonsekventa sökupplevelser. För att lösa de här problemen flyttar vi till en manuell filtreringsmekanism.

Ur en perspektiv kan användaren tillämpa och ta bort de olika filterområdet (från filteruppsättningen och datumet) och välja uppdateringsknappen för att filtrera resultaten när de har definierat frågan. Uppdateringsknappen är nu också framhävd på skärmen. Vi har även uppdaterat relaterade verktygstips och produktdokumentation.

> [!div class="mx-imgBorder"]
> ![Välj Uppdatera för att filtrera resultat](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Diagram, granska för att lägga till i filter

Nu kan du lägga till förklaringsvärden i diagram som filter. Filtrera **resultatet genom** att välja knappen Uppdatera.

> [!div class="mx-imgBorder"]
> ![Granska nedåt genom diagram för att filtrera](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Uppdateringar av information i produkten

Ytterligare information är nu tillgänglig i produkten, till exempel det totala antalet sökresultat i rutnätet (se nedan). Vi har förbättrat etiketter, felmeddelanden och verktygstips för att ge mer information om filter, sökupplevelse och resultatuppsättning.

> [!div class="mx-imgBorder"]
> ![Visa produktinformation](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Utökade funktioner i Hotutforskaren

### <a name="top-targeted-users"></a>Mest riktade användare

I dag visar vi listan över de mest riktade användarna i vyn Skadlig programvara för e-postmeddelanden i avsnittet **Top Malware Families.** Vi utökar den här vyn i vyerna Phish och All E-post. Du kan se de fem främsta riktade användarna, tillsammans med antalet försök för varje användare för motsvarande vy. För phishvyn ser du till exempel antalet phish-försök.

Du kan exportera listan med riktade användare, upp till 3 000, tillsammans med antalet försök för offlineanalys för varje e-postvy. Om du väljer antalet försök (till exempel 13 försök i bilden nedan) öppnas en filtrerad vy i Hotutforskaren, så att du kan se mer information om e-postmeddelanden och hot för den användaren.

> [!div class="mx-imgBorder"]
> ![Mest riktade användare](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange-transportregler

Som en del av databerikningen kan du se alla olika Exchange-transportregler (ETR) som har tillämpats på ett meddelande. Den här informationen är tillgänglig i rutnätsvyn för e-post. Du visar den genom att **välja Kolumnalternativ** i rutnätet och sedan **Lägga till Exchange-transportregel** bland kolumnalternativen. Det visas också på den **utfällbara informationen** i e-postmeddelandet.

Du kan se både GUID och namnet på de transportregler som tillämpats på meddelandet. Du kan söka efter meddelandena med hjälp av namnet på transportregeln. Det här är en "Innehåller"-sökning, vilket innebär att du även kan göra partiella sökningar.

#### <a name="important-note"></a>Viktigt meddelande:

ETR-sökning och namntillgänglighet beror på den specifika roll som har tilldelats till dig. Du måste ha någon av följande roller/behörigheter för att visa ETR-namn och sökning. Om du inte har någon av de här rollerna tilldelad till dig kan du inte se namnen på transportreglerna eller söka efter meddelanden med hjälp av ETR-namn. Däremot kunde du se ETR-etiketten och GUID-informationen i e-postinformationen. Andra funktioner för postvisning i e-postrutnät, utfällblad för e-post, filter och export påverkas inte.

- Exo Only – Skydd mot dataförlust: Alla
- Endast EXO - O365SupportViewConfig: Alla
- Microsoft Azure Active Directory eller EXO – säkerhetsadministratör: Alla
- AAD eller EXO – Säkerhetsläsare: Alla
- EXO Only – Transportregler: Alla
- Endast EXO – View-Only konfiguration: Alla

I e-postrutnätet, den utfällliga informationen och den exporterade CSV-filen visas ETR-ETR-linjerna med ett namn/GUID enligt nedan.

> [!div class="mx-imgBorder"]
> ![Exchange-transportregler](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Inkommande kopplingar

Kopplingar är en samling instruktioner som anpassar hur din e-post flödar till och från din Microsoft 365- eller Office 365-organisation. Med hjälp av dem kan du tillämpa säkerhetsbegränsningar och kontroller. I Threat Explorer kan du nu visa kopplingar som är relaterade till ett e-postmeddelande och söka efter e-postmeddelanden med hjälp av kopplingsnamn.

Sökningen efter kopplingar är "innehåller" till sin natur, vilket innebär att partiella nyckelordssökningar också bör fungera. I huvudrutnätet, den utfällliga informationen och den exporterade CSV-filen, visas kopplingarna i formatet Namn/GUID enligt följande exempel:

> [!div class="mx-imgBorder"]
> ![Information om kopplingar](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nya funktioner i Hotutforskaren och identifieringar i realtid

Tre nya funktioner är tillgängliga i Threat Explorer och identifieringar i realtid:

- [Förhandsgranska e-posthuvud och ladda ned brödtext för e-post](#preview-email-header-and-download-email-body)
- [E-posttidslinje](#email-timeline)
- [Exportera URL-klickdata](#export-url-click-data)

De nya funktionerna beskrivs nedan.

### <a name="preview-email-header-and-download-email-body"></a>Förhandsgranska e-posthuvud och ladda ned brödtext för e-post

Nu kan du förhandsgranska ett e-posthuvud och ladda ned e-posttexten i Threat Explorer-administratörerna kan analysera nedladdade rubriker/e-postmeddelanden för hot. Eftersom nedladdning av e-postmeddelanden kan riskera exponering av information styrs den här processen av rollbaserad åtkomstkontroll (RBAC). En ny *roll,* Förhandsversion, måste läggas till i en annan rollgrupp (till exempel säkerhetsåtgärder eller säkerhetsadministratör) för att det ska gå att ladda ned e-postmeddelanden i vyn för alla e-postmeddelanden. Det krävs dock ingen ytterligare roll för att visa e-posthuvuden (förutom vad som krävs för att visa meddelanden i Hotutforskaren).

Identifieringar av Utforskaren och Realtid får också nya fält som ger en mer fullständig bild av var dina e-postmeddelanden hamnar. Dessa ändringar gör det enklare att hitta Säkerhetsvakterna. Men det viktigaste resultatet är att du snabbt kan se platsen för de problemmeddelanden som uppstår.

Hur gör man det? Leveransstatus delas nu upp i två kolumner:

- **Leveransåtgärd** – Status för e-postmeddelandet.
- **Leveransplats** – dit e-postmeddelandet har dirigerats.

*Leveransåtgärd* är den åtgärd som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärderna för ett e-postmeddelande:

|Levererad|Skräppost|Blockerad|Ersatt|
|---|---|---|---|
|E-post levererades till inkorgen eller mappen för en användare och användaren kan komma åt den.|E-post skickades till användarens skräppostmapp eller borttaget och användaren kan komma åt den.|E-postmeddelanden som har satts i karantän, misslyckats eller släppts. De här e-postmeddelandena är inte tillgängliga för användaren.|E-post har ersatts med skadliga bifogade filer av TXT-filer som säger att den bifogade filen var skadlig.|

Det här kan och kan användaren inte se:

|Tillgängligt för slutanvändare|Inte tillgänglig för slutanvändare|
|---|---|
|Levererad|Blockerad|
|Skräppost|Ersatt|

**Leveransplats** visar resultatet av principer och identifieringar som körs efter leverans. Det är länkat till **_leveransåtgärden._** Det här är de möjliga värdena:

- *Inkorgen eller mappen:* E-postmeddelandet ligger i Inkorgen eller i en mapp (enligt dina e-postregler).
- *Lokal eller extern:* Postlådan finns inte i molnet men är lokal.
- *Skräppostmapp:* E-postmeddelandet finns i användarens skräppostmapp.
- *Mappen Borttaget:* E-postmeddelandet i en användares mapp Borttaget.
- *Karantän:* E-postmeddelandet ligger i karantän och inte i en användares postlåda.
- *Misslyckades:* E-postmeddelandet kunde inte nå postlådan.
- *Släppt:* E-postmeddelandet försvann någonstans i e-postflödet.

### <a name="email-timeline"></a>E-posttidslinje

Tidslinjen **för e-post** är en ny funktion i Utforskaren som förbättrar upplevelsen för administratörer. Det klipper av tiden som läggs på att kontrollera olika platser för att försöka förstå händelsen. När flera händelser inträffar samtidigt som ett e-postmeddelande skickas visas de i en tidslinjevy. Vissa händelser som inträffar för din e-post efter leverans visas i kolumnen **Specialåtgärd.** Administratörer kan kombinera information från tidslinjen med den särskilda åtgärd som vidtas på e-postmeddelandet efter leveransen för att få insyn i hur deras principer fungerar, var e-postmeddelandet slutligen skickades och, i vissa fall, vad den slutliga bedömningen var.

Mer information finns i [Undersöka och åtgärda skadlig e-post som har levererats i Office 365.](investigate-malicious-email-that-was-delivered.md)

### <a name="export-url-click-data"></a>Exportera URL-klickdata

Nu kan du exportera rapporter för URL-klick  till Microsoft Excel för att visa deras nätverksmeddelande-ID och klicka på **bedömning,** vilket hjälper till att förklara var URL-klicktrafiken kom. Så här fungerar det: Följ den här kedjan i Hantering av hot i snabbstartsfältet i Office 365:

**Utforskaren** \> **Visa phish** \> **Klick** \> **Url:er eller** **Url Top Clicks väljer** en post för att öppna den \> utfällliga URL-adressen.

När du väljer en URL i listan visas en ny **Export-knapp** i den utfällbaserade panelen. Använd den här knappen för att flytta data till ett Excel-kalkylblad för enklare rapportering.

Följ den här sökvägen för att komma till samma plats i rapporten om identifieringar i realtid:

**Utforskaren** \> **Identifieringar i realtid** \> **Visa phish** \> **URL:er** \> **Övre URL:er** **eller Översta klick väljer** en post för att öppna den \> utfällliga URL-adressen, \> gå till fliken **Klick.**

> [!TIP]
> Nätverksmeddelande-ID mappar klick tillbaka till specifika e-postmeddelanden när du söker på ID:t i Utforskaren eller tillhörande verktyg från tredje part. Sådana sökningar identifierar e-postmeddelandet som är associerat med ett klickresultat. Om ett korrelerat nätverksmeddelande-ID används går det att göra en snabbare och kraftfullare analys.

> [!div class="mx-imgBorder"]
> ![Fliken Klick i Utforskaren](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Visa skadlig programvara som identifieras i e-post efter teknik

Anta att du vill se skadlig kod som upptäckts i e-post sorterad med Microsoft 365-teknik. Det gör du genom att använda [e> vyn för](threat-explorer-views.md#email--malware) skadlig programvara i Utforskaren (eller identifieringar i realtid).

1. I Säkerhets- & Center <https://protection.office.com> (), väljer du Hothanteringsutforskaren  \>  **(eller identifieringar i realtid).** (I det här exemplet används Utforskaren.)

2. Välj Skadlig **programvara för** e-post på **visa-menyn.** \> 

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicka **på Avsändaren** och välj sedan teknik för **enkel** \> **identifiering.**

   Dina identifieringstekniker är nu tillgängliga som filter för rapporten.

   > [!div class="mx-imgBorder"]
   > ![Teknik för identifiering av skadlig programvara](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Välj ett alternativ. Välj sedan knappen **Uppdatera** för att använda filtret.

   > [!div class="mx-imgBorder"]
   > ![Vald identifieringsteknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Rapporten uppdateras för att visa resultat som skadlig programvara upptäckt i e-post med hjälp av det teknikalternativ som du har valt. Härifrån kan du göra ytterligare analyser.

## <a name="view-phishing-url-and-click-verdict-data"></a>Visa nätfiske-URL och klicka på bedömningsdata

Anta att du vill se nätfiskeförsök via URL:er i e-post, inklusive en lista över URL-adresser som tillåts, blockeras och åsidosätts. Om du vill identifiera URL:er som har [klickats på måste](atp-safe-links.md) Säkra länkar konfigureras. Kontrollera att du har angett principer [för säkra](set-up-atp-safe-links-policies.md) länkar för tidsbe klickar-skydd och loggning av klicka-beslut med hjälp av säkra länkar.

Om du vill granska phish-URL:er i meddelanden och klickar på URL:er i phish-meddelanden använder du e-post [   >  **phish-vyn**](threat-explorer-views.md#email--phish) i Utforskaren eller identifieringar i realtid.

1. I Säkerhets- & Center <https://protection.office.com> (), väljer du Hothanteringsutforskaren  \>  **(eller identifieringar i realtid).** (I det här exemplet används Utforskaren.)

2. Välj **E-postfras** **på** \> **visa-menyn.**

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för Utforskaren i nätfiskekontext](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicka **på Avsändare** och välj sedan **URL:er klicka** på \> **bedömning.**

4. Välj ett eller flera  alternativ, till exempel Blockerad och  Blockera åsidosättt, och välj sedan knappen Uppdatera på samma rad som alternativen för att använda filtret. (Uppdatera inte webbläsarfönstret.)

   > [!div class="mx-imgBorder"]
   > ![URL:er och klicka på beslut](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Rapporten uppdateras så att två olika URL-tabeller visas på fliken URL under rapporten:

   - **Url:er** är url:er i meddelanden som du filtrerat ned till och åtgärden för e-postleverans räknas för varje URL. I e-postvyn phish innehåller den här listan vanligtvis legitima URL:er. Attacker innehåller en blandning av bra och dåliga URL:er i sina meddelanden för att försöka leverera dem, men de skadliga länkarna ser mer intressanta ut. Tabellen med URL-adresser sorteras efter totalt antal e-postmeddelanden, men den här kolumnen är dold för att förenkla vyn.

   - **De översta klicken** är de URL-adresser som är säkra länkar som har klickats på, sorterade efter totalt antal klick. Den här kolumnen visas inte heller för att förenkla vyn. Totalt antal per kolumn anger antalet säkra länkar vid klickning för varje klickad URL. I e-postvyn i Phish är det oftast misstänkta eller skadliga URL-adresser. Men vyn kan innehålla URL:er som inte är hot men som är i phish-meddelanden. URL-klick på olästa länkar visas inte här.

   De två URL-tabellerna visar de viktigaste webbadresserna i nätfiskemeddelanden efter leveransåtgärd och plats. Tabellerna visar URL-klick som har blockerats eller besökts trots en varning, så att du kan se vilka potentiella dåliga länkar som visas för användare och att användaren har klickat på dem. Härifrån kan du göra ytterligare analyser. Under diagrammet kan du till exempel se de översta WEBBADRESSerna i e-postmeddelanden som har blockerats i organisationens miljö.

   > [!div class="mx-imgBorder"]
   > ![URL-adresser i Utforskaren som har blockerats](../../media/ExplorerPhishClickVerdictURLs.png)

   Välj en URL om du vill visa mer detaljerad information.

   > [!NOTE]
   > I den utfällningsdialogrutan för URL-adressen tas filtreringen av e-postmeddelanden bort för att visa den fullständiga visningen av exponering av URL:en i miljön. På så sätt kan du filtrera efter e-postmeddelanden som du är orolig för i Utforskaren, hitta specifika URL:er som är potentiella hot och sedan utöka förståelsen av exponering av URL-adresser i din miljö (via dialogrutan URL-information) utan att behöva lägga till URL-filter i själva Utforskarvyn.

### <a name="interpretation-of-click-verdicts"></a>Tolkning av klickningar

I de utfällade e-postmeddelandena eller URL-adresserna, de bästa klicken och i filtreringen visas olika värden för klickningar:

- **Inget:** Det går inte att registrera url-adressens bedömning. Användaren kan ha klickat genom URL:en.
- **Tillåtet:** Användaren tilläts navigera till URL-adressen.
- **Blockerad:** Användaren blockerades från att navigera till URL-adressen.
- **Väntande bedömning:** Användaren visades en sida som väntar på att detonation.
- **Blockerad åsidosätts:** Användaren blockerades från att navigera direkt till URL-adressen. Men användaren överbröt blocket för att navigera till URL:en.
- **Väntande bedömning kringgås:** Användaren visades en detonationssida. Men användaren överbröt meddelandet för att få åtkomst till URL-adressen.
- **Fel:** Användaren visades på felsidan eller så uppstod ett fel vid inspelning av bedömningsfelet.
- **Fel:** Ett okänt undantag inträffade vid inspelningen av händelsen. Användaren kan ha klickat genom URL:en.

## <a name="review-email-messages-reported-by-users"></a>Granska e-postmeddelanden som rapporterats av användare

Anta att du vill se [e-postmeddelanden](enable-the-report-message-add-in.md) som användare i organisationen  rapporterat som *skräppost,* inte skräppost eller nätfiske via tillägget Rapportmeddelande eller tillägget [Rapport nätfiske.](enable-the-report-phish-add-in.md) Om du vill visa dem kan du använda [   >  **vyn För**](threat-explorer-views.md#email--submissions) inskickade e-postmeddelanden i Utforskaren (eller identifieringar i realtid).

1. I Säkerhets- & Center <https://protection.office.com> (), väljer du Hothanteringsutforskaren  \>  **(eller identifieringar i realtid).** (I det här exemplet används Utforskaren.)

2. Välj Skicka **e-post** i  \> **visa-menyn.**

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för e-postmeddelanden i Utforskaren](../../media/explorer-view-menu-email-user-reported.png)

3. Klicka **på Avsändare** och välj sedan **Grundläggande** \> **rapporttyp.**

4. Välj ett alternativ, till **exempel Phish,** och välj sedan **knappen** Uppdatera.

   > [!div class="mx-imgBorder"]
   > ![Användarrapporterad phish](../../media/EmailUserReportedReportType.png)

Rapporten uppdateras för att visa data om e-postmeddelanden som personer i organisationen har rapporterat som nätfiskeförsök. Du kan använda den här informationen för ytterligare analyser och, om det behövs, justera dina principer för skydd mot nätfiske i [Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="start-automated-investigation-and-response"></a>Starta automatisk undersökning och svar

> [!NOTE]
> Funktioner för automatisk undersökning och svar finns i *Microsoft Defender för Office 365 abonnemang 2* och Office *365 E5.*

[Med automatiserad undersökning och](automated-investigation-response-office.md) svar kan du spara tid och arbete med att undersöka och minska cyberattacker. Förutom att konfigurera aviseringar som kan utlösa en säkerhetsspelbok kan du starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren. Mer information finns i [exempel: En säkerhetsadministratör utlöser en undersökning från Utforskaren.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Fler sätt att använda identifieringar i Utforskaren och Realtid

Utöver scenarierna som beskrivs i den här artikeln finns det många fler rapportalternativ med Utforskaren (eller identifieringar i realtid). Se följande artiklar:

- [Hitta och undersöka skadlig e-post som har levererats](investigate-malicious-email-that-was-delivered.md)
- [Visa skadliga filer som upptäckts i SharePoint Online, OneDrive och Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Få en översikt över vyerna i Threat Explorer (och identifieringar i realtid)](threat-explorer-views.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Automatiserad undersökning och svar i Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Licenser och behörigheter som krävs

Du måste ha [Microsoft Defender för Office 365 för](office-365-atp.md) att kunna använda Utforskaren eller identifiering i realtid.

- Utforskaren ingår i Defender för Office 365 abonnemang 2.
- Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.
- Planera att tilldela licenser för alla användare som ska skyddas av Defender för Office 365. Identifieringar i Utforskaren och Realtid visar identifieringsdata för licensierade användare.

Om du vill visa och använda identifieringar i Utforskaren eller Realtid måste du ha rätt behörighet, till exempel de som beviljas till en säkerhetsadministratör eller säkerhetsläsare.

- För Säkerhets- & Efterlevnadscenter måste du ha någon av följande roller tilldelade:

  - Organisationshantering
  - Säkerhetsadministratör (detta kan tilldelas i administrationscentret för Azure Active Directory ( <https://aad.portal.azure.com> )
  - Säkerhetsläsare

- För Exchange Online måste du ha någon av följande roller tilldelade i administrationscentret för Exchange ( ) eller <https://admin.protection.outlook.com/ecp/> [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Organisationshantering
  - View-Only Organisationshantering
  - View-Only mottagare
  - Efterlevnadshantering

Mer information om roller och behörigheter finns i följande resurser:

- [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)
- [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Skillnader mellan identifieringar av hotutforskaren och realtidsidentifiering

- Rapporten *identifieringar i realtid* finns i Defender för Office 365 abonnemang 1. *Threat Explorer* finns i Defender för Office 365 abonnemang 2.
- Med rapporten Realtidsidentifiering kan du visa identifieringar i realtid. Threat Explorer gör det här också, men det ger också ytterligare information om en viss attack.
- Vyn *All e-post* är tillgänglig i Hotutforskaren men inte i rapporten om identifieringar i realtid.
- Fler filtreringsfunktioner och tillgängliga åtgärder ingår i Hotutforskaren. Mer information finns i [Tjänstbeskrivning för Microsoft Defender för Office 365: Funktionstillgänglighet i Defender för Office 365-abonnemang.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
