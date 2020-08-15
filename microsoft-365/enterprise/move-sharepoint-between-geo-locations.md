---
title: Flytta en SharePoint-webbplats till en annan Geo-plats
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
description: Lär dig hur du flyttar en SharePoint-webbplats till en annan Geo-plats i din multi-geo-miljö och förmedlar förväntningarna på ändringarna för användarna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e96c422b1d2685c9fe3d4c8c45aa8437a6776621
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694301"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Flytta en SharePoint-webbplats till en annan Geo-plats

Med SharePoint-webbplatsen geo Move kan du flytta SharePoint-webbplatser till andra geo-platser i din multi-geo-miljö.

Följande typer av webbplatser kan flyttas mellan geo platserna:

- Microsoft 365-gruppanslutna webbplatser
- Moderna webbplatser utan en Microsoft 365-gruppassociation
- Klassiska SharePoint-webbplatser
- Kommunikations webbplatser

Du måste vara global administratör eller SharePoint-administratör för att kunna flytta en webbplats mellan geo platserna.

Det finns ett skrivskyddat fönster under en SharePoint-webbplats geo flytt mellan 4-6 timmar, beroende på webbplats innehåll.
 
## <a name="best-practices"></a>Metodtips

- Pröva en SharePoint-webbplats på en testwebbplats för att få bekanta dig med proceduren. 
- Verifiera om webbplatsen kan flyttas innan den schemaläggs eller när den flyttas. 
- När möjligt schemaläggning mellan olika geo-webbplatser flyttas för mer än en arbets tid för att minska användar påverkan.
- Kommunicera med påverkade användare innan platserna flyttas. 

## <a name="communicating-to-your-users"></a>Kommunicera med användarna

När du flyttar SharePoint-webbplatser mellan geo platser är det viktigt att du kommunicerar med användarnas användare (i allmänhet vem som helst som kan redigera webbplatsen). Detta kan hjälpa till att minska användarnas förvirring och samtal till din supportavdelning. E-posta användarnas användare innan de flyttar och meddela dem följande information:

- När flytten förväntas starta och hur lång tid det förväntas ta
- Vilken Geo-plats webbplatsen flyttas till och URL-adressen till den nya platsen
- De bör stänga sina filer och inte göra ändringar under flytten.
- Fil behörigheter och delning ändras inte på grund av flytten.
- Vad du kan förvänta dig av användar gränssnittet i en multi-geo-miljö

Var noga med att skicka ett e-postmeddelande till dina användare när flytten har slutförts och få arbeta på sina webbplatser.

## <a name="scheduling-sharepoint-site-moves"></a>Schemalägga flyttning av SharePoint-webbplats

Du kan schemalägga att en SharePoint-webbplats flyttas i förväg (beskrivs längre fram i den här artikeln). Du kan schemalägga flyttningar så här:

- Du kan schemalägga upp till 4 000 i taget.
- När flytten börjar kan du schemalägga mer, med högst 4 000 i kön och när som helst.
 
Om du vill schemalägga en SharePoint-webbplats med geo-flytt för en senare tillfälle, lägger du till en av följande parametrar när du börjar flytta:
- `PreferredMoveBeginDate` – Flytten kommer sannolikt att börja vid den här tidpunkten.
- `PreferredMoveEndDate` – Flytten kommer sannolikt att genomföras efter den angivna tiden, på bästa möjliga sätt. 

Tid måste anges i UTC (Coordinated Universal Time) för båda parametrarna.

## <a name="moving-the-site"></a>Flytta webbplatsen

För att SharePoint-webbplatsen ska kunna flyttas måste du ansluta och genomföra flytten från URL-adressen för SharePoint-administration på den Geo-plats där webbplatsen är.

Om du till exempel har webbplats-URL: en https://contosohealthcare.sharepoint.com/sites/Turbines , ansluter du till administrations-URL: en för SharePoint på https://contosohealthcare-admin.sharepoint.com:

`Connect-SPOService -url https://contosohealthcare-admin.sharepoint.com`

![](../media/move-onedrive-between-geo-locations-image1.png)
 
### <a name="validating-the-environment"></a>Verifiera miljön

Vi rekommenderar att du gör en verifiering för att se till att webbplatsen kan flyttas innan du schemalägger en webbplats förflyttning.

Vi stöder inte flytt av webbplatser med:
-    Konnektivitetstjänster för företag
-    InfoPath-formulär 
- Använda IRM-mallar (Information Rights Management)

För att säkerställa att alla geo-platser är kompatibla kör du `Get-SPOGeoMoveCrossCompatibilityStatus` . Då visas alla dina geo-platser och om miljön är kompatibel med geo-platsen.

Om du vill utföra en verifierings kontroll på webbplatsen använder du `Start-SPOSiteContentMove` `-ValidationOnly` parametern för att validera om webbplatsen kan flyttas. Till exempel:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Detta returnerar *framgång* om webbplatsen är redo att flyttas eller *inte fungerar* om något av de blockerade villkoren är uppfyllt.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Starta en SharePoint-webbplats geo Move för en webbplats utan associerad Microsoft 365-grupp

Som standard ändras initial URL för webbplatsen till URL-adressen för målets Geo-plats. Till exempel:

https://Contoso.sharepoint.com/sites/projectx som https://ContosoEUR.sharepoint.com/sites/projectx

För webbplatser som inte har Microsoft 365-gruppassociationer kan du även byta namn på webbplatsen med hjälp av `-DestinationUrl` parametern. Till exempel:

https://Contoso.sharepoint.com/sites/projectx som https://ContosoEUR.sharepoint.com/sites/projecty

Starta webbplatsen genom att köra:

`Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>`

![Skärm bild av PowerShell-fönstret med start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Starta en SharePoint-webbplats geo Move för en Microsoft 365-gruppansluten webbplats

Om du vill flytta en Office 365-gruppansluten webbplats måste den globala administratören eller SharePoint-administratören först ändra den förvalda data plats (PDL) för gruppen Office 365.

Så här anger du PDL för en Microsoft 365-grupp:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```
När du har uppdaterat PDL kan du börja flytta webbplatsen: 

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Avbryta en SharePoint-webbplats geo Move

Du kan stoppa en SharePoint-webbplats geo flytt, förutsatt att flytten inte pågår eller slutförs med hjälp av `Stop-SPOSiteContentMove` cmdleten.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Kontrol lera status för en SharePoint-webbplats geo Move

Du kan bestämma statusen för en webbplats som flyttas i vårt från den geo som du är ansluten till genom att använda följande cmdletar:

- [Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (icke-gruppanslutna webbplatser)
- Get-SPOUnifiedGroupMoveState (gruppanslutna webbplatser)

Använd `-SourceSiteUrl` parametern för att ange den webbplats som du vill visa status för.

Flytt status beskrivs i följande tabell.

|Status|Beskrivning|
|:-----|:----------|
|Redo att utlösa|Flytten har inte påbörjats.|
|Överföring|Flyttningen är i kö men har inte startat ännu.|
|Inaktivitet (ej tillämpligt)|Flytten pågår i något av följande lägen: verifiering (1/4), säkerhets kopiering (2/4), återställning (3/4), rensning (4/4).|
|Bra|Flyttningen har slutförts.|
|Misslyckades|Det gick inte att flytta.|

Du kan också använda `-Verbose` alternativet för att visa ytterligare information om flytten.

## <a name="user-experience"></a>Användar upplevelse

Webbplats användare bör meddela minimala störningar när deras webbplats flyttas till en annan Geo-plats. Om du tar bort ett kort känsligt tillstånd under flytten fortsätter befintliga länkar och behörigheter att fungera som förväntat när flytten är klar.

### <a name="site"></a>Webbplatsmallar

När flytten pågår är webbplatsen skrivskyddad. När flytten är klar dirigeras användaren till den nya webbplatsen på den nya geo platsen när de klickar på bok märken eller andra länkar till webbplatsen.

### <a name="permissions"></a>Behörigheter

Användare som har behörighet till webbplatsen fortsätter att ha åtkomst till webbplatsen under flytten och när den är slutförd.

### <a name="sync-client"></a>Synkroniseringsklient

Synkroniseringsklienten kommer automatiskt att upptäcka och överföra synkronisering till den nya platsen när webbplatsen har flyttats. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. (Version 17.3.6943.0625 eller senare krävs för synkroniseringsklient.)

Om en användare uppdaterar en fil medan flytten pågår visas en avisering om att fil överföringar är väntande när flytten pågår.

### <a name="sharing-links"></a>Dela länkar

När SharePoint-webbplatsens geo Move-flyttning är klar omdirigeras de befintliga delade länkarna för de filer som flyttas automatiskt till den nya geo-platsen.

### <a name="most-recently-used-files-in-office-mru"></a>Senast använda filer i Office (MRU)

MRU-tjänsten uppdateras med webbplats-URL: en och dess innehålls webb adresser när flytten är klar. Det här gäller för Word, Excel och PowerPoint.

### <a name="onenote-experience"></a>OneNote-upplevelse

I OneNote Win32-klient-och UWP (Universal) identifieras och sömlöst synkronisera antecknings böcker automatiskt när webbplatsen flyttas. Användaren behöver inte logga in igen eller vidta någon annan åtgärd. Den enda synliga indikatorn för användaren är att synkronisering av antecknings boken Miss lyckas när webbplatsen flyttas. Den här funktionen finns i följande OneNote-klient versioner:

- OneNote Win32 – version 16.0.8326.2096 (och senare)
- OneNote UWP – version 16.0.8431.1006 (och senare)
- OneNote-mobilapp – version 16.0.8431.1011 (och senare)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Team (gäller för Microsoft 365-gruppanslutna webbplatser)

När SharePoint-webbplatsens geo Move-flyttning är klar har användarna åtkomst till sina Microsoft 365-gruppfiler i Teams-appen. Dessutom fortsätter filer som delas via Teams chatt från sina webbplatser innan de geo flytten fortsätta att fungera när flytten är klar.

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint-mobilapp (iOS/Android)

SharePoint-mobilappen är Cross geo-kompatibel och kan upptäcka webbplatsens nya Geo-plats.

### <a name="sharepoint-workflows"></a>SharePoint-arbetsflöden

SharePoint 2013-arbets flöden måste publiceras igen efter att webbplatsen har flyttats. SharePoint 2010-arbets flöden fungerar normalt.

### <a name="apps"></a>Appar

Om du flyttar en webbplats med appar måste du återaktivera programmet på den nya geo-platsen för webbplatsen, och dess anslutningar kanske inte är tillgängliga på Geo-platsen.

### <a name="flow"></a>Flyter

I de flesta fall fortsätter flöden att fungera efter en SharePoint-webbplats geo-flytt. Vi rekommenderar att du testar dem när flytten har slutförts.

### <a name="powerapps"></a>PowerApps

PowerApps måste återskapas på mål platsen.

### <a name="data-movement-between-geo-locations"></a>Data förflyttning mellan geo-platser

SharePoint använder Azure Blob Storage för innehållet, medan metadata som är kopplade till webbplatser och dess filer lagras i SharePoint. När webbplatsen har flyttats från källans Geo-plats till dess mål plats, flyttas även dess tillhör ande blob-lagring. Blob-lagringen flyttas i cirka 40 dagar. 
