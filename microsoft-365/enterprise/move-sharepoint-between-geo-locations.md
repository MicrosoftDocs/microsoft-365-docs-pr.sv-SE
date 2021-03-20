---
title: Flytta en SharePoint-webbplats till en annan geoplats
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
description: Lär dig hur du flyttar en SharePoint-webbplats till en annan geoplats i din multigeobaserade miljö och kommunicerar förväntningar på ändringarna till användarna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed323b2e2b8f68a4a603052657e17495bb17690
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910936"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Flytta en SharePoint-webbplats till en annan geoplats

Med geoflyttning av SharePoint-webbplats kan du flytta SharePoint-webbplatser till andra geoplatser i din geomiljö.

Följande typer av webbplatser kan flyttas mellan geografiska platser:

- Gruppanslutna Microsoft 365-webbplatser
- Moderna webbplatser utan någon Microsoft 365-gruppassociatorganisation
- Klassiska SharePoint-webbplatser
- Kommunikationswebbplatser

Du måste vara global administratör eller SharePoint-administratör för att kunna flytta en webbplats mellan geografiska platser.

Det finns ett skrivskyddade fönster under geoflyttningen av SharePoint-webbplatsen på ungefär 4–6 timmar, beroende på webbplatsens innehåll.

## <a name="best-practices"></a>Metodtips

- Prova att flytta runt på en SharePoint-webbplats på en testwebbplats för att bekanta dig med proceduren.
- Kontrollera om webbplatsen kan flyttas innan du schemalägger eller utför flytten.
- När möjliga scheman flyttas mellan geowebbplatser för extern arbetstid för att minska påverkan på användarna.
- Kommunicera med påverkade användare innan webbplatserna flyttas.

## <a name="communicating-to-your-users"></a>Kommunicera till användarna

När du flyttar SharePoint-webbplatser mellan geografiska platser är det viktigt att kommunicera med användarna (i allmänhet alla som har möjlighet att redigera webbplatsen) vad de kan förvänta sig. Det kan minska risken för förvirring och samtal till supportavdelningen. Skicka e-post till användarna av webbplatserna innan flytten och informera dem om följande information:

- När flyttningen förväntas starta och hur lång tid den förväntas ta
- Vilken geoplats deras webbplats flyttas till och URL-adressen för att komma åt den nya platsen
- De bör stänga sina filer och inte göra ändringar under flytten.
- Filbehörigheter och delning ändras inte på grund av flytten.
- Vad du kan förvänta dig av användarupplevelsen i en geomiljö med flera miljöer

Se till att skicka ett e-postmeddelande till webbplatsanvändarna när flytten har slutförts och informera dem om att de kan fortsätta arbeta på sina webbplatser.

## <a name="scheduling-sharepoint-site-moves"></a>Schemalägga flyttningar av SharePoint-webbplatser

Du kan schemalägga flyttningar av SharePoint-webbplatser i förväg (beskrivs senare i den här artikeln). Du kan schemalägga flyttningar enligt följande:

- Du kan schemalägga upp till 4 000 flyttningar i taget.
- När flytten börjar kan du schemalägga fler, med högst 4 000 väntande flyttningar i kön och en viss tid.

Om du vill schemalägga en geoflyttning av en SharePoint-webbplats till ett senare tillfälle tar du med någon av följande parametrar när du startar flytten:

- `PreferredMoveBeginDate` – Flyttningen börjar förmodligen vid den här angivna tiden.
- `PreferredMoveEndDate` – Flytten kommer sannolikt att slutföras den här angivna tiden med bästa möjliga ansträngning.

Tid måste anges i UTC (Coordinated Universal Time) för båda parametrarna.

## <a name="moving-the-site"></a>Flytta webbplatsen

Geoflyttning av SharePoint-webbplats kräver att du ansluter och utför flytten från SharePoint-administratörs-URL:en på den geoplats där webbplatsen finns.

Om webbplats-URL:en till exempel är <https://contosohealthcare.sharepoint.com/sites/Turbines> ansluter du till SharePoint-administratörs-URL:en <https://contosohealthcare-admin.sharepoint.com> på:

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Online Management Shell-fönstret som visar Connect-SPOService kommando](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Validera miljön

Vi rekommenderar att du, innan du schemalägger en flytt av webbplats, utför en verifiering för att säkerställa att webbplatsen kan flyttas.

Vi stöder inte flytt av webbplatser med:

- Konnektivitetstjänster för företag
- InfoPath-formulär
- IRM-mallar (Information Rights Management) används

Om du vill säkerställa att alla geoplatser är kompatibla kör du `Get-SPOGeoMoveCrossCompatibilityStatus` . Då visas alla dina geografiska platser och om miljön är kompatibel med den geoplats som används som destination.

Om du vill utföra en verifieringskontroll på webbplatsen använder du parametern för att `Start-SPOSiteContentMove` verifiera om webbplatsen kan `-ValidationOnly` flyttas. Ett exempel:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Det returnerar *"Lyckades"* om webbplatsen är redo att flyttas eller *Fel* om något av blockerade villkoren finns.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Starta en geoflyttning av en SharePoint-webbplats för en webbplats utan tillhörande Microsoft 365-grupp

Som standard ändras den ursprungliga URL:en för webbplatsen till URL:en för den geoplats som är destinationen. Ett exempel:

<https://Contoso.sharepoint.com/sites/projectx> till <https://ContosoEUR.sharepoint.com/sites/projectx>

För webbplatser som inte har någon Microsoft 365-gruppassociatorganisation kan du också byta namn på webbplatsen med `-DestinationUrl` parametern. Ett exempel:

<https://Contoso.sharepoint.com/sites/projectx> till <https://ContosoEUR.sharepoint.com/sites/projecty>

Starta flytten av webbplatsen genom att köra:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Skärmbild av PowerShell-fönstret med Start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Starta en geoflyttning av en SharePoint-webbplats för en Gruppansluten Microsoft 365-webbplats

För att flytta en gruppansluten Office 365-webbplats måste den globala administratören eller SharePoint-administratören först ändra attributet Föredragen dataplats (PDL) för Office 365-gruppen.

Så här anger du PDF-filer för en Microsoft 365-grupp:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

När du har uppdaterat PDF-filer kan du starta flytten av webbplatsen:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Avbryta geoflyttning av SharePoint-webbplats

Du kan stoppa en geoflyttning av en SharePoint-webbplats förutsatt att flyttningen inte pågår eller slutförts med hjälp av `Stop-SPOSiteContentMove` cmdleten.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Fastställa status för en geoflyttning av SharePoint-webbplats

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
|Lyckades|Flyttningen har slutförts.|
|Misslyckades|Flyttningen misslyckades.|
|

Du kan också använda alternativet `-Verbose` om du vill se ytterligare information om flytten.

## <a name="user-experience"></a>Användarupplevelse

Webbplatsanvändarna bör märka minimal störning när deras webbplats flyttas till en annan geoplats. Förutom ett kort skrivskyddad tillstånd under flyttningen kommer befintliga länkar och behörigheter att fungera som förväntat när flyttningen har slutförts.

### <a name="site"></a>Webbplats

Medan flytten pågår är webbplatsen skrivskyddd. När flytten är slutförd dirigeras användaren till den nya webbplatsen på den nya geoplatsen när de klickar på bokmärken eller andra länkar till webbplatsen.

### <a name="permissions"></a>Behörigheter

Användare med behörighet till webbplatsen fortsätter att ha åtkomst till webbplatsen under flytten och efter att den är slutförd.

### <a name="sync-client"></a>Synkroniseringsklient

Synkroniseringsklienten identifierar och överför automatiskt synkroniseringen till den nya webbplatsen när webbplatsflyttningen är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. (Version 17.3.6943.0625 eller senare av synkroniseringsklienten krävs.)

Om en användare uppdaterar en fil medan flyttningen pågår meddelar synkroniseringsklienten att filuppladdningar väntar medan flyttningen pågår.

### <a name="sharing-links"></a>Delningslänkar

När den geoflytda av SharePoint-webbplatsen har slutförts omdirigeras de befintliga delade länkarna för de filer som har flyttats automatiskt till den nya geoplatsen.

### <a name="most-recently-used-files-in-office-mru"></a>Senast använda filer i Office

Tjänsten M MRU uppdateras med webbplats-URL:en och dess innehålls-URL:er när flyttningen har slutförts. Det här gäller Word, Excel och PowerPoint.

### <a name="onenote-experience"></a>OneNote-upplevelse

Appen OneNote win32-klient och UWP (Universal) identifierar och synkroniserar automatiskt anteckningsböcker till den nya webbplatsen när webbplatsflyttningen är klar. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. Den enda synliga indikatorn för användaren är synkronisering av anteckningsboken misslyckades när webbplatsflyttning pågår. Den här versionen är tillgänglig i följande OneNote-klientversioner:

- OneNote win32 – version 16.0.8326.2096 (och senare)
- UWP för OneNote – version 16.0.8431.1006 (och senare)
- OneNote-mobilappen – version 16.0.8431.1011 (och senare)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (gäller för gruppanslutna webbplatser i Microsoft 365)

När geoflyttningen av SharePoint-webbplatsen har slutförts har användarna åtkomst till sina Microsoft 365-gruppwebbplatsfiler i Teams-appen. Dessutom kommer filer som delas via Teams-chatt från deras webbplats innan geoflyttning fortsätta att fungera när flyttningen är slutförd.

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint-mobilappen (iOS/Android)

SharePoint-mobilappen är geokompatibel och kan identifiera webbplatsens nya geoplats.

### <a name="sharepoint-workflows"></a>SharePoint-arbetsflöden

SharePoint 2013-arbetsflöden måste publiceras på nytt efter webbplatsflyttningen. SharePoint 2010-arbetsflöden bör fortsätta att fungera normalt.

### <a name="apps"></a>Appar

Om du flyttar en webbplats med appar måste du instansiera appen igen på webbplatsens nya geoplats eftersom appen och dess anslutningar kanske inte är tillgängliga på den geoplats som är destinationen.

### <a name="flow"></a>Flöde

I de flesta fall kommer flöden att fortsätta fungera efter en geoflyttning av SharePoint-webbplats. Vi rekommenderar att du testar dem när flyttningen är klar.

### <a name="powerapps"></a>PowerApps

PowerApps måste återskapas på målplatsen.

### <a name="data-movement-between-geo-locations"></a>Datarörelse mellan geoplatser

SharePoint använder Blob-lagring i Azure för sitt innehåll medan metadata som associeras med webbplatser och dess filer lagras i SharePoint. När webbplatsen flyttas från dess geografiska källplats till destinationens geoplats flyttar tjänsten också den tillhörande Blob Storage. Blob Storage flyttas slutföras om ungefär 40 dagar.