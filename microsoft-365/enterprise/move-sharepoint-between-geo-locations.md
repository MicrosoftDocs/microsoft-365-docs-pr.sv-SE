---
title: Flytta en SharePoint webbplats till en annan geoplats
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Lär dig hur du flyttar SharePoint en webbplats till en annan geoplats i din multigeobaserade miljö och kommunicerar förväntningar på ändringarna till användarna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a49098045dbce94ef1c474497b8da1b397ac0b0
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362360"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Flytta en SharePoint webbplats till en annan geoplats

Med SharePoint geoflyttning av webbplats kan du SharePoint till andra geoplatser i din geomiljö.

Följande typer av webbplatser kan flyttas mellan geografiska platser:

- Microsoft 365 Gruppanslutna webbplatser, inklusive de som är kopplade till Microsoft Teams
- Moderna webbplatser utan Microsoft 365 för grupp
- Klassiska SharePoint webbplatser
- Kommunikationswebbplatser

Du måste vara global administratör eller SharePoint administratör för att flytta en webbplats mellan geoplatser.

Det finns ett skrivskyddade fönster under tiden SharePoint geoflyttning av webbplatsen på ungefär 4–6 timmar, beroende på webbplatsens innehåll.

## <a name="best-practices"></a>Metodtips

- Prova att SharePoint en webbplats som du flyttar runt på en testwebbplats för att bekanta dig med proceduren.
- Kontrollera om webbplatsen kan flyttas innan du schemalägger eller utför flytten.
- När möjliga scheman flyttas mellan geowebbplatser för extern arbetstid för att minska påverkan på användarna.
- Kommunicera med påverkade användare innan webbplatserna flyttas.

## <a name="communicating-to-your-users"></a>Kommunicera till användarna

När du SharePoint webbplatser mellan geografiska platser är det viktigt att kommunicera med webbplatsens användare (vanligtvis alla som har möjlighet att redigera webbplatsen) vad de kan förvänta sig. Det kan minska risken för förvirring och samtal till supportavdelningen. Skicka e-post till användarna av webbplatserna innan flytten och informera dem om följande information:

- När flyttningen förväntas starta och hur lång tid den förväntas ta
- Vilken geoplats deras webbplats flyttas till och URL-adressen för att komma åt den nya platsen
- De bör stänga sina filer och inte göra ändringar under flytten.
- Filbehörigheter och delning ändras inte på grund av flytten.
- Vad du kan förvänta dig av användarupplevelsen i en geomiljö med flera miljöer

Se till att skicka ett e-postmeddelande till webbplatsanvändarna när flytten har slutförts och informera dem om att de kan fortsätta arbeta på sina webbplatser.

## <a name="scheduling-sharepoint-site-moves"></a>Schemalägga SharePoint flyttningar av webbplatser

Du kan schemalägga SharePoint i förväg (beskrivs senare i den här artikeln). Du kan schemalägga flyttningar enligt följande:

- Du kan schemalägga upp till 4 000 flyttningar i taget.
- När flytten börjar kan du schemalägga fler, med högst 4 000 väntande flyttningar i kön och en viss tid.

Om du vill SharePoint en geoflyttningswebbplats till en senare tidpunkt tar du med någon av följande parametrar när du startar flytten:

- `PreferredMoveBeginDate` – Flyttningen börjar förmodligen vid den här angivna tiden.
- `PreferredMoveEndDate` – Flytten kommer sannolikt att slutföras den här angivna tiden med bästa möjliga ansträngning.

Tid måste anges i UTC (Coordinated Universal Time) för båda parametrarna.

## <a name="moving-the-site"></a>Flytta webbplatsen

SharePoint geoflyttning av en webbplats kräver att du ansluter och utför flytten från SharePoint-administratörs-URL:en på den geoplats där webbplatsen finns.

Om webbplats-URL:en till exempel är <https://contosohealthcare.sharepoint.com/sites/Turbines> ansluter du till SharePoint-URL:en <https://contosohealthcare-admin.sharepoint.com> på:

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Fönstret Online Management Shell som visar Connect-SPOService kommando](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Validera miljön

Vi rekommenderar att du, innan du schemalägger en flytt av webbplats, utför en verifiering för att säkerställa att webbplatsen kan flyttas.

Vi stöder inte flytt av webbplatser med:

- Konnektivitetstjänster för företag
- InfoPath-formulär
- IRM-mallar (Information Rights Management) används

Om du vill säkerställa att alla geoplatser är kompatibla kör du `Get-SPOGeoMoveCrossCompatibilityStatus` . Då visas alla dina geografiska platser och om miljön är kompatibel med den geoplats som används som destination.

Om du vill utföra en verifieringskontroll på webbplatsen använder du parametern för att `Start-SPOSiteContentMove` verifiera om webbplatsen kan `-ValidationOnly` flyttas. Till exempel:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Det returnerar *"Lyckades"* om webbplatsen är redo att flyttas eller *Fel* om något av blockerade villkoren finns.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Starta en SharePoint geoflyttning för en webbplats utan tillhörande Microsoft 365 grupp

Som standard ändras den ursprungliga URL:en för webbplatsen till URL:en för den geoplats som är destinationen. Till exempel:

<https://Contoso.sharepoint.com/sites/projectx> till <https://ContosoEUR.sharepoint.com/sites/projectx>

För webbplatser utan Microsoft 365 grupp kan du också byta namn på webbplatsen med `-DestinationUrl` parametern. Till exempel:

<https://Contoso.sharepoint.com/sites/projectx> till <https://ContosoEUR.sharepoint.com/sites/projecty>

Starta flytten av webbplatsen genom att köra:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Skärmbild av PowerShell-fönstret med Start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Starta en SharePoint geoflyttning av en webbplats Microsoft 365 gruppansluten webbplats

För att flytta en Office 365 gruppansluten webbplats måste den globala administratören eller SharePoint-administratören först ändra attributet Föredragen dataplats (PDL) för Office 365-gruppen.

Så här anger du PDF-filer för Microsoft 365 grupp:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

När du har uppdaterat PDF-filer kan du starta flytten av webbplatsen:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Avbryta en SharePoint geoflyttning av webbplats

Du kan stoppa SharePoint geoflyttning av en webbplats förutsatt att flyttningen inte pågår eller slutförts med hjälp av `Stop-SPOSiteContentMove` cmdleten.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Fastställa status för en geoflyttning SharePoint webbplats

Du kan ta reda på statusen för en webbplats ur geo som du är ansluten till med hjälp av följande cmdlets:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (icke-gruppanslutna webbplatser)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (gruppanslutna webbplatser)

Använd `-SourceSiteUrl` parametern för att ange den webbplats som du vill se flyttningsstatus för.

Flyttningsstatusen beskrivs i följande tabell.

****

|Status|Beskrivning|
|---|---|
|Redo att utlösare|Flyttningen har inte startat.|
|Schemalagd|Flyttningen ligger i kö men har ännu inte påbörjats.|
|InProgress (n/4)|Flyttningen pågår i ett av följande tillstånd: Verifiering (1/4), Säkerhetskopiering (2/4), Återställ (3/4), Rensning (4/4).|
|Klart|Flyttningen har slutförts.|
|Misslyckades|Flyttningen misslyckades.|
|

Du kan också använda alternativet `-Verbose` om du vill se ytterligare information om flytten.

## <a name="user-experience"></a>Användarupplevelse

Webbplatsanvändarna bör märka minimal störning när deras webbplats flyttas till en annan geoplats. Förutom ett kort skrivskyddad tillstånd under flyttningen kommer befintliga länkar och behörigheter att fungera som förväntat när flyttningen har slutförts.

### <a name="site"></a>Webbplats

Medan flytten pågår är webbplatsen skrivskyddd. När flytten är slutförd dirigeras användaren till den nya webbplatsen på den nya geoplatsen när de klickar på bokmärken eller andra länkar till webbplatsen.

### <a name="permissions"></a>Behörigheter

Användare med behörighet till webbplatsen fortsätter att ha åtkomst till webbplatsen under flytten och efter att den är slutförd.

### <a name="sync-app"></a>Synkroniseringsapp

Synkroniseringsappen identifierar och överför automatiskt synkronisering till den nya webbplatsen när webbplatsflyttningen är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. (Version 17.3.6943.0625 eller senare av synkroniseringsappen krävs.)

Om en användare uppdaterar en fil medan flyttningen pågår meddelar synkroniseringsappen att filuppladdningar väntar medan flyttningen pågår.

### <a name="sharing-links"></a>Delningslänkar

När SharePoint geoflyt har slutförts omdirigeras de befintliga delade länkarna för de filer som har flyttats automatiskt till den nya geoplatsen.

### <a name="most-recently-used-files-in-office-mru"></a>Senast använda filer i Office (MRU)

Tjänsten M MRU uppdateras med webbplats-URL:en och dess innehålls-URL:er när flyttningen har slutförts. Det här gäller word, Excel och PowerPoint.

### <a name="onenote-experience"></a>OneNote upplevelse

OneNote hos win32-klienten och UWP-appen (Universell) identifierar och synkroniserar automatiskt anteckningsböcker till den nya webbplatsen när flytten är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. Den enda synliga indikatorn för användaren är synkronisering av anteckningsboken misslyckades när webbplatsflyttning pågår. Den här versionen är tillgänglig på följande OneNote klientversioner:

- OneNote win32 – version 16.0.8326.2096 (och senare)
- OneNote UWP – version 16.0.8431.1006 (och senare)
- OneNote Mobilapp – version 16.0.8431.1011 (och senare)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (gäller endast Microsoft 365 gruppanslutna webbplatser)

När SharePoint geoflyttning har slutförts har användarna åtkomst till sina gruppwebbplatsfiler Microsoft 365 gruppwebbplats i appen Teams webbplats. Dessutom kommer filer som delas via Teams från deras webbplats innan geoflyttning fortsätta att fungera när flytten är klar.

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint Mobilapp (iOS/Android)

The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.

### <a name="sharepoint-workflows"></a>SharePoint arbetsflöden

SharePoint 2013-arbetsflöden måste publiceras på nytt efter webbplatsflyttningen. SharePoint 2010-arbetsflöden ska fortsätta att fungera normalt.

### <a name="apps"></a>Appar

Om du flyttar en webbplats med appar måste du instansiera appen igen på webbplatsens nya geoplats eftersom appen och dess anslutningar kanske inte är tillgängliga på den geoplats som är destinationen.

### <a name="flow"></a>Flow

I de flesta fall fortsätter Flöden att fungera efter en SharePoint geoflyttning av webbplatsen. Vi rekommenderar att du testar dem när flyttningen är klar.

### <a name="powerapps"></a>PowerApps

PowerApps måste återskapas på målplatsen.

### <a name="data-movement-between-geo-locations"></a>Datarörelse mellan geoplatser

SharePoint använder Blob-lagring i Azure för sitt innehåll, medan metadata som är kopplade till webbplatser och dess filer lagras i SharePoint. När webbplatsen flyttas från dess geoplats för källan till sin geoplats för destinationen flyttar tjänsten även den tillhörande Blob-Storage. Blob Storage slutförs om ungefär 40 dagar.