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
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="2bf3d-103">Flytta en SharePoint-webbplats till en annan Geo-plats</span><span class="sxs-lookup"><span data-stu-id="2bf3d-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="2bf3d-104">Med SharePoint-webbplatsen geo Move kan du flytta SharePoint-webbplatser till andra geo-platser i din multi-geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="2bf3d-105">Följande typer av webbplatser kan flyttas mellan geo platserna:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="2bf3d-106">Microsoft 365-gruppanslutna webbplatser</span><span class="sxs-lookup"><span data-stu-id="2bf3d-106">Microsoft 365 Group-connected sites</span></span>
- <span data-ttu-id="2bf3d-107">Moderna webbplatser utan en Microsoft 365-gruppassociation</span><span class="sxs-lookup"><span data-stu-id="2bf3d-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="2bf3d-108">Klassiska SharePoint-webbplatser</span><span class="sxs-lookup"><span data-stu-id="2bf3d-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="2bf3d-109">Kommunikations webbplatser</span><span class="sxs-lookup"><span data-stu-id="2bf3d-109">Communication sites</span></span>

<span data-ttu-id="2bf3d-110">Du måste vara global administratör eller SharePoint-administratör för att kunna flytta en webbplats mellan geo platserna.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="2bf3d-111">Det finns ett skrivskyddat fönster under en SharePoint-webbplats geo flytt mellan 4-6 timmar, beroende på webbplats innehåll.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>
 
## <a name="best-practices"></a><span data-ttu-id="2bf3d-112">Metodtips</span><span class="sxs-lookup"><span data-stu-id="2bf3d-112">Best practices</span></span>

- <span data-ttu-id="2bf3d-113">Pröva en SharePoint-webbplats på en testwebbplats för att få bekanta dig med proceduren.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span> 
- <span data-ttu-id="2bf3d-114">Verifiera om webbplatsen kan flyttas innan den schemaläggs eller när den flyttas.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span> 
- <span data-ttu-id="2bf3d-115">När möjligt schemaläggning mellan olika geo-webbplatser flyttas för mer än en arbets tid för att minska användar påverkan.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="2bf3d-116">Kommunicera med påverkade användare innan platserna flyttas.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-116">Communicate with impacted users prior to the sites move.</span></span> 

## <a name="communicating-to-your-users"></a><span data-ttu-id="2bf3d-117">Kommunicera med användarna</span><span class="sxs-lookup"><span data-stu-id="2bf3d-117">Communicating to your users</span></span>

<span data-ttu-id="2bf3d-118">När du flyttar SharePoint-webbplatser mellan geo platser är det viktigt att du kommunicerar med användarnas användare (i allmänhet vem som helst som kan redigera webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="2bf3d-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="2bf3d-119">Detta kan hjälpa till att minska användarnas förvirring och samtal till din supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="2bf3d-120">E-posta användarnas användare innan de flyttar och meddela dem följande information:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="2bf3d-121">När flytten förväntas starta och hur lång tid det förväntas ta</span><span class="sxs-lookup"><span data-stu-id="2bf3d-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="2bf3d-122">Vilken Geo-plats webbplatsen flyttas till och URL-adressen till den nya platsen</span><span class="sxs-lookup"><span data-stu-id="2bf3d-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="2bf3d-123">De bör stänga sina filer och inte göra ändringar under flytten.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="2bf3d-124">Fil behörigheter och delning ändras inte på grund av flytten.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="2bf3d-125">Vad du kan förvänta dig av användar gränssnittet i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="2bf3d-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="2bf3d-126">Var noga med att skicka ett e-postmeddelande till dina användare när flytten har slutförts och få arbeta på sina webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="2bf3d-127">Schemalägga flyttning av SharePoint-webbplats</span><span class="sxs-lookup"><span data-stu-id="2bf3d-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="2bf3d-128">Du kan schemalägga att en SharePoint-webbplats flyttas i förväg (beskrivs längre fram i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="2bf3d-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="2bf3d-129">Du kan schemalägga flyttningar så här:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="2bf3d-130">Du kan schemalägga upp till 4 000 i taget.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="2bf3d-131">När flytten börjar kan du schemalägga mer, med högst 4 000 i kön och när som helst.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
 
<span data-ttu-id="2bf3d-132">Om du vill schemalägga en SharePoint-webbplats med geo-flytt för en senare tillfälle, lägger du till en av följande parametrar när du börjar flytta:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>
- <span data-ttu-id="2bf3d-133">`PreferredMoveBeginDate` – Flytten kommer sannolikt att börja vid den här tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="2bf3d-134">`PreferredMoveEndDate` – Flytten kommer sannolikt att genomföras efter den angivna tiden, på bästa möjliga sätt.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span> 

<span data-ttu-id="2bf3d-135">Tid måste anges i UTC (Coordinated Universal Time) för båda parametrarna.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="2bf3d-136">Flytta webbplatsen</span><span class="sxs-lookup"><span data-stu-id="2bf3d-136">Moving the site</span></span>

<span data-ttu-id="2bf3d-137">För att SharePoint-webbplatsen ska kunna flyttas måste du ansluta och genomföra flytten från URL-adressen för SharePoint-administration på den Geo-plats där webbplatsen är.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="2bf3d-138">Om du till exempel har webbplats-URL: en https://contosohealthcare.sharepoint.com/sites/Turbines , ansluter du till administrations-URL: en för SharePoint på https://contosohealthcare-admin.sharepoint.com:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-138">For example, if the site URL is https://contosohealthcare.sharepoint.com/sites/Turbines, connect to the SharePoint Admin URL at https://contosohealthcare-admin.sharepoint.com:</span></span>

`Connect-SPOService -url https://contosohealthcare-admin.sharepoint.com`

![](../media/move-onedrive-between-geo-locations-image1.png)
 
### <a name="validating-the-environment"></a><span data-ttu-id="2bf3d-139">Verifiera miljön</span><span class="sxs-lookup"><span data-stu-id="2bf3d-139">Validating the environment</span></span>

<span data-ttu-id="2bf3d-140">Vi rekommenderar att du gör en verifiering för att se till att webbplatsen kan flyttas innan du schemalägger en webbplats förflyttning.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-140">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="2bf3d-141">Vi stöder inte flytt av webbplatser med:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-141">We do not support moving sites with:</span></span>
-    <span data-ttu-id="2bf3d-142">Konnektivitetstjänster för företag</span><span class="sxs-lookup"><span data-stu-id="2bf3d-142">Business Connectivity Services</span></span>
-    <span data-ttu-id="2bf3d-143">InfoPath-formulär</span><span class="sxs-lookup"><span data-stu-id="2bf3d-143">InfoPath forms</span></span> 
- <span data-ttu-id="2bf3d-144">Använda IRM-mallar (Information Rights Management)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-144">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="2bf3d-145">För att säkerställa att alla geo-platser är kompatibla kör du `Get-SPOGeoMoveCrossCompatibilityStatus` .</span><span class="sxs-lookup"><span data-stu-id="2bf3d-145">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="2bf3d-146">Då visas alla dina geo-platser och om miljön är kompatibel med geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-146">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="2bf3d-147">Om du vill utföra en verifierings kontroll på webbplatsen använder du `Start-SPOSiteContentMove` `-ValidationOnly` parametern för att validera om webbplatsen kan flyttas.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-147">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="2bf3d-148">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-148">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="2bf3d-149">Detta returnerar *framgång* om webbplatsen är redo att flyttas eller *inte fungerar* om något av de blockerade villkoren är uppfyllt.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-149">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="2bf3d-150">Starta en SharePoint-webbplats geo Move för en webbplats utan associerad Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="2bf3d-150">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="2bf3d-151">Som standard ändras initial URL för webbplatsen till URL-adressen för målets Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-151">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="2bf3d-152">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-152">For example:</span></span>

<span data-ttu-id="2bf3d-153">https://Contoso.sharepoint.com/sites/projectx som https://ContosoEUR.sharepoint.com/sites/projectx</span><span class="sxs-lookup"><span data-stu-id="2bf3d-153">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projectx</span></span>

<span data-ttu-id="2bf3d-154">För webbplatser som inte har Microsoft 365-gruppassociationer kan du även byta namn på webbplatsen med hjälp av `-DestinationUrl` parametern.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-154">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="2bf3d-155">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-155">For example:</span></span>

<span data-ttu-id="2bf3d-156">https://Contoso.sharepoint.com/sites/projectx som https://ContosoEUR.sharepoint.com/sites/projecty</span><span class="sxs-lookup"><span data-stu-id="2bf3d-156">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projecty</span></span>

<span data-ttu-id="2bf3d-157">Starta webbplatsen genom att köra:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-157">To start the site move, run:</span></span>

`Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>`

![Skärm bild av PowerShell-fönstret med start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="2bf3d-159">Starta en SharePoint-webbplats geo Move för en Microsoft 365-gruppansluten webbplats</span><span class="sxs-lookup"><span data-stu-id="2bf3d-159">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="2bf3d-160">Om du vill flytta en Office 365-gruppansluten webbplats måste den globala administratören eller SharePoint-administratören först ändra den förvalda data plats (PDL) för gruppen Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-160">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="2bf3d-161">Så här anger du PDL för en Microsoft 365-grupp:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-161">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```
<span data-ttu-id="2bf3d-162">När du har uppdaterat PDL kan du börja flytta webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-162">Once you have updated the PDL, you can start the site move:</span></span> 

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="2bf3d-163">Avbryta en SharePoint-webbplats geo Move</span><span class="sxs-lookup"><span data-stu-id="2bf3d-163">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="2bf3d-164">Du kan stoppa en SharePoint-webbplats geo flytt, förutsatt att flytten inte pågår eller slutförs med hjälp av `Stop-SPOSiteContentMove` cmdleten.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-164">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="2bf3d-165">Kontrol lera status för en SharePoint-webbplats geo Move</span><span class="sxs-lookup"><span data-stu-id="2bf3d-165">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="2bf3d-166">Du kan bestämma statusen för en webbplats som flyttas i vårt från den geo som du är ansluten till genom att använda följande cmdletar:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-166">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="2bf3d-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (icke-gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="2bf3d-168">Get-SPOUnifiedGroupMoveState (gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-168">Get-SPOUnifiedGroupMoveState (Group-connected sites)</span></span>

<span data-ttu-id="2bf3d-169">Använd `-SourceSiteUrl` parametern för att ange den webbplats som du vill visa status för.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-169">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="2bf3d-170">Flytt status beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-170">The move statuses are described in the following table.</span></span>

|<span data-ttu-id="2bf3d-171">Status</span><span class="sxs-lookup"><span data-stu-id="2bf3d-171">Status</span></span>|<span data-ttu-id="2bf3d-172">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bf3d-172">Description</span></span>|
|:-----|:----------|
|<span data-ttu-id="2bf3d-173">Redo att utlösa</span><span class="sxs-lookup"><span data-stu-id="2bf3d-173">Ready to Trigger</span></span>|<span data-ttu-id="2bf3d-174">Flytten har inte påbörjats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-174">The move has not started.</span></span>|
|<span data-ttu-id="2bf3d-175">Överföring</span><span class="sxs-lookup"><span data-stu-id="2bf3d-175">Scheduled</span></span>|<span data-ttu-id="2bf3d-176">Flyttningen är i kö men har inte startat ännu.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-176">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="2bf3d-177">Inaktivitet (ej tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-177">InProgress (n/4)</span></span>|<span data-ttu-id="2bf3d-178">Flytten pågår i något av följande lägen: verifiering (1/4), säkerhets kopiering (2/4), återställning (3/4), rensning (4/4).</span><span class="sxs-lookup"><span data-stu-id="2bf3d-178">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="2bf3d-179">Bra</span><span class="sxs-lookup"><span data-stu-id="2bf3d-179">Success</span></span>|<span data-ttu-id="2bf3d-180">Flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-180">The move has completed successfully.</span></span>|
|<span data-ttu-id="2bf3d-181">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="2bf3d-181">Failed</span></span>|<span data-ttu-id="2bf3d-182">Det gick inte att flytta.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-182">The move failed.</span></span>|

<span data-ttu-id="2bf3d-183">Du kan också använda `-Verbose` alternativet för att visa ytterligare information om flytten.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-183">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="2bf3d-184">Användar upplevelse</span><span class="sxs-lookup"><span data-stu-id="2bf3d-184">User experience</span></span>

<span data-ttu-id="2bf3d-185">Webbplats användare bör meddela minimala störningar när deras webbplats flyttas till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-185">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="2bf3d-186">Om du tar bort ett kort känsligt tillstånd under flytten fortsätter befintliga länkar och behörigheter att fungera som förväntat när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-186">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="2bf3d-187">Webbplatsmallar</span><span class="sxs-lookup"><span data-stu-id="2bf3d-187">Site</span></span>

<span data-ttu-id="2bf3d-188">När flytten pågår är webbplatsen skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-188">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="2bf3d-189">När flytten är klar dirigeras användaren till den nya webbplatsen på den nya geo platsen när de klickar på bok märken eller andra länkar till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-189">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="2bf3d-190">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2bf3d-190">Permissions</span></span>

<span data-ttu-id="2bf3d-191">Användare som har behörighet till webbplatsen fortsätter att ha åtkomst till webbplatsen under flytten och när den är slutförd.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-191">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-client"></a><span data-ttu-id="2bf3d-192">Synkroniseringsklient</span><span class="sxs-lookup"><span data-stu-id="2bf3d-192">Sync Client</span></span>

<span data-ttu-id="2bf3d-193">Synkroniseringsklienten kommer automatiskt att upptäcka och överföra synkronisering till den nya platsen när webbplatsen har flyttats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-193">The sync client will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="2bf3d-194">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-194">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="2bf3d-195">(Version 17.3.6943.0625 eller senare krävs för synkroniseringsklient.)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-195">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="2bf3d-196">Om en användare uppdaterar en fil medan flytten pågår visas en avisering om att fil överföringar är väntande när flytten pågår.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-196">If a user updates a file while the move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="2bf3d-197">Dela länkar</span><span class="sxs-lookup"><span data-stu-id="2bf3d-197">Sharing links</span></span>

<span data-ttu-id="2bf3d-198">När SharePoint-webbplatsens geo Move-flyttning är klar omdirigeras de befintliga delade länkarna för de filer som flyttas automatiskt till den nya geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-198">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="2bf3d-199">Senast använda filer i Office (MRU)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-199">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="2bf3d-200">MRU-tjänsten uppdateras med webbplats-URL: en och dess innehålls webb adresser när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-200">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="2bf3d-201">Det här gäller för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-201">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="2bf3d-202">OneNote-upplevelse</span><span class="sxs-lookup"><span data-stu-id="2bf3d-202">OneNote experience</span></span>

<span data-ttu-id="2bf3d-203">I OneNote Win32-klient-och UWP (Universal) identifieras och sömlöst synkronisera antecknings böcker automatiskt när webbplatsen flyttas.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-203">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="2bf3d-204">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-204">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="2bf3d-205">Den enda synliga indikatorn för användaren är att synkronisering av antecknings boken Miss lyckas när webbplatsen flyttas.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-205">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="2bf3d-206">Den här funktionen finns i följande OneNote-klient versioner:</span><span class="sxs-lookup"><span data-stu-id="2bf3d-206">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="2bf3d-207">OneNote Win32 – version 16.0.8326.2096 (och senare)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-207">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="2bf3d-208">OneNote UWP – version 16.0.8431.1006 (och senare)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-208">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="2bf3d-209">OneNote-mobilapp – version 16.0.8431.1011 (och senare)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-209">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="2bf3d-210">Team (gäller för Microsoft 365-gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-210">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="2bf3d-211">När SharePoint-webbplatsens geo Move-flyttning är klar har användarna åtkomst till sina Microsoft 365-gruppfiler i Teams-appen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-211">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="2bf3d-212">Dessutom fortsätter filer som delas via Teams chatt från sina webbplatser innan de geo flytten fortsätta att fungera när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-212">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="2bf3d-213">SharePoint-mobilapp (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="2bf3d-213">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="2bf3d-214">SharePoint-mobilappen är Cross geo-kompatibel och kan upptäcka webbplatsens nya Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-214">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="2bf3d-215">SharePoint-arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="2bf3d-215">SharePoint workflows</span></span>

<span data-ttu-id="2bf3d-216">SharePoint 2013-arbets flöden måste publiceras igen efter att webbplatsen har flyttats.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-216">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="2bf3d-217">SharePoint 2010-arbets flöden fungerar normalt.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-217">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="2bf3d-218">Appar</span><span class="sxs-lookup"><span data-stu-id="2bf3d-218">Apps</span></span>

<span data-ttu-id="2bf3d-219">Om du flyttar en webbplats med appar måste du återaktivera programmet på den nya geo-platsen för webbplatsen, och dess anslutningar kanske inte är tillgängliga på Geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-219">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="2bf3d-220">Flyter</span><span class="sxs-lookup"><span data-stu-id="2bf3d-220">Flow</span></span>

<span data-ttu-id="2bf3d-221">I de flesta fall fortsätter flöden att fungera efter en SharePoint-webbplats geo-flytt.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-221">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="2bf3d-222">Vi rekommenderar att du testar dem när flytten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-222">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="2bf3d-223">PowerApps</span><span class="sxs-lookup"><span data-stu-id="2bf3d-223">PowerApps</span></span>

<span data-ttu-id="2bf3d-224">PowerApps måste återskapas på mål platsen.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-224">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="2bf3d-225">Data förflyttning mellan geo-platser</span><span class="sxs-lookup"><span data-stu-id="2bf3d-225">Data movement between geo locations</span></span>

<span data-ttu-id="2bf3d-226">SharePoint använder Azure Blob Storage för innehållet, medan metadata som är kopplade till webbplatser och dess filer lagras i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-226">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="2bf3d-227">När webbplatsen har flyttats från källans Geo-plats till dess mål plats, flyttas även dess tillhör ande blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-227">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="2bf3d-228">Blob-lagringen flyttas i cirka 40 dagar.</span><span class="sxs-lookup"><span data-stu-id="2bf3d-228">Blob Storage moves complete in approximately 40 days.</span></span> 
