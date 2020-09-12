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
ms.openlocfilehash: 819496b9f7612afa1db902e6fc5a0844e99d7a8e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545642"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="b5f94-103">Flytta en SharePoint-webbplats till en annan Geo-plats</span><span class="sxs-lookup"><span data-stu-id="b5f94-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="b5f94-104">Med SharePoint-webbplatsen geo Move kan du flytta SharePoint-webbplatser till andra geo-platser i din multi-geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="b5f94-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="b5f94-105">Följande typer av webbplatser kan flyttas mellan geo platserna:</span><span class="sxs-lookup"><span data-stu-id="b5f94-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="b5f94-106">Microsoft 365-gruppanslutna webbplatser</span><span class="sxs-lookup"><span data-stu-id="b5f94-106">Microsoft 365 Group-connected sites</span></span>
- <span data-ttu-id="b5f94-107">Moderna webbplatser utan en Microsoft 365-gruppassociation</span><span class="sxs-lookup"><span data-stu-id="b5f94-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="b5f94-108">Klassiska SharePoint-webbplatser</span><span class="sxs-lookup"><span data-stu-id="b5f94-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="b5f94-109">Kommunikations webbplatser</span><span class="sxs-lookup"><span data-stu-id="b5f94-109">Communication sites</span></span>

<span data-ttu-id="b5f94-110">Du måste vara global administratör eller SharePoint-administratör för att kunna flytta en webbplats mellan geo platserna.</span><span class="sxs-lookup"><span data-stu-id="b5f94-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="b5f94-111">Det finns ett skrivskyddat fönster under en SharePoint-webbplats geo flytt mellan 4-6 timmar, beroende på webbplats innehåll.</span><span class="sxs-lookup"><span data-stu-id="b5f94-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>

## <a name="best-practices"></a><span data-ttu-id="b5f94-112">Metodtips</span><span class="sxs-lookup"><span data-stu-id="b5f94-112">Best practices</span></span>

- <span data-ttu-id="b5f94-113">Pröva en SharePoint-webbplats på en testwebbplats för att få bekanta dig med proceduren.</span><span class="sxs-lookup"><span data-stu-id="b5f94-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span>
- <span data-ttu-id="b5f94-114">Verifiera om webbplatsen kan flyttas innan den schemaläggs eller när den flyttas.</span><span class="sxs-lookup"><span data-stu-id="b5f94-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span>
- <span data-ttu-id="b5f94-115">När möjligt schemaläggning mellan olika geo-webbplatser flyttas för mer än en arbets tid för att minska användar påverkan.</span><span class="sxs-lookup"><span data-stu-id="b5f94-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="b5f94-116">Kommunicera med påverkade användare innan platserna flyttas.</span><span class="sxs-lookup"><span data-stu-id="b5f94-116">Communicate with impacted users prior to the sites move.</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="b5f94-117">Kommunicera med användarna</span><span class="sxs-lookup"><span data-stu-id="b5f94-117">Communicating to your users</span></span>

<span data-ttu-id="b5f94-118">När du flyttar SharePoint-webbplatser mellan geo platser är det viktigt att du kommunicerar med användarnas användare (i allmänhet vem som helst som kan redigera webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="b5f94-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="b5f94-119">Detta kan hjälpa till att minska användarnas förvirring och samtal till din supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="b5f94-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="b5f94-120">E-posta användarnas användare innan de flyttar och meddela dem följande information:</span><span class="sxs-lookup"><span data-stu-id="b5f94-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="b5f94-121">När flytten förväntas starta och hur lång tid det förväntas ta</span><span class="sxs-lookup"><span data-stu-id="b5f94-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="b5f94-122">Vilken Geo-plats webbplatsen flyttas till och URL-adressen till den nya platsen</span><span class="sxs-lookup"><span data-stu-id="b5f94-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="b5f94-123">De bör stänga sina filer och inte göra ändringar under flytten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="b5f94-124">Fil behörigheter och delning ändras inte på grund av flytten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="b5f94-125">Vad du kan förvänta dig av användar gränssnittet i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="b5f94-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="b5f94-126">Var noga med att skicka ett e-postmeddelande till dina användare när flytten har slutförts och få arbeta på sina webbplatser.</span><span class="sxs-lookup"><span data-stu-id="b5f94-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="b5f94-127">Schemalägga flyttning av SharePoint-webbplats</span><span class="sxs-lookup"><span data-stu-id="b5f94-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="b5f94-128">Du kan schemalägga att en SharePoint-webbplats flyttas i förväg (beskrivs längre fram i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="b5f94-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="b5f94-129">Du kan schemalägga flyttningar så här:</span><span class="sxs-lookup"><span data-stu-id="b5f94-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="b5f94-130">Du kan schemalägga upp till 4 000 i taget.</span><span class="sxs-lookup"><span data-stu-id="b5f94-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="b5f94-131">När flytten börjar kan du schemalägga mer, med högst 4 000 i kön och när som helst.</span><span class="sxs-lookup"><span data-stu-id="b5f94-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>

<span data-ttu-id="b5f94-132">Om du vill schemalägga en SharePoint-webbplats med geo-flytt för en senare tillfälle, lägger du till en av följande parametrar när du börjar flytta:</span><span class="sxs-lookup"><span data-stu-id="b5f94-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>

- <span data-ttu-id="b5f94-133">`PreferredMoveBeginDate` – Flytten kommer sannolikt att börja vid den här tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="b5f94-134">`PreferredMoveEndDate` – Flytten kommer sannolikt att genomföras efter den angivna tiden, på bästa möjliga sätt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span>

<span data-ttu-id="b5f94-135">Tid måste anges i UTC (Coordinated Universal Time) för båda parametrarna.</span><span class="sxs-lookup"><span data-stu-id="b5f94-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="b5f94-136">Flytta webbplatsen</span><span class="sxs-lookup"><span data-stu-id="b5f94-136">Moving the site</span></span>

<span data-ttu-id="b5f94-137">För att SharePoint-webbplatsen ska kunna flyttas måste du ansluta och genomföra flytten från URL-adressen för SharePoint-administration på den Geo-plats där webbplatsen är.</span><span class="sxs-lookup"><span data-stu-id="b5f94-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="b5f94-138">Om webb adressen till webbplatsen är <https://contosohealthcare.sharepoint.com/sites/Turbines> , ansluter du till URL-adressen för SharePoint-administratörer på <https://contosohealthcare-admin.sharepoint.com> :</span><span class="sxs-lookup"><span data-stu-id="b5f94-138">For example, if the site URL is <https://contosohealthcare.sharepoint.com/sites/Turbines>, connect to the SharePoint Admin URL at <https://contosohealthcare-admin.sharepoint.com>:</span></span>

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Online Management Shell-fönstret med kommandot Connect-SPOService](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a><span data-ttu-id="b5f94-140">Verifiera miljön</span><span class="sxs-lookup"><span data-stu-id="b5f94-140">Validating the environment</span></span>

<span data-ttu-id="b5f94-141">Vi rekommenderar att du gör en verifiering för att se till att webbplatsen kan flyttas innan du schemalägger en webbplats förflyttning.</span><span class="sxs-lookup"><span data-stu-id="b5f94-141">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="b5f94-142">Vi stöder inte flytt av webbplatser med:</span><span class="sxs-lookup"><span data-stu-id="b5f94-142">We do not support moving sites with:</span></span>

- <span data-ttu-id="b5f94-143">Konnektivitetstjänster för företag</span><span class="sxs-lookup"><span data-stu-id="b5f94-143">Business Connectivity Services</span></span>
- <span data-ttu-id="b5f94-144">InfoPath-formulär</span><span class="sxs-lookup"><span data-stu-id="b5f94-144">InfoPath forms</span></span>
- <span data-ttu-id="b5f94-145">Använda IRM-mallar (Information Rights Management)</span><span class="sxs-lookup"><span data-stu-id="b5f94-145">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="b5f94-146">För att säkerställa att alla geo-platser är kompatibla kör du `Get-SPOGeoMoveCrossCompatibilityStatus` .</span><span class="sxs-lookup"><span data-stu-id="b5f94-146">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="b5f94-147">Då visas alla dina geo-platser och om miljön är kompatibel med geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-147">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="b5f94-148">Om du vill utföra en verifierings kontroll på webbplatsen använder du `Start-SPOSiteContentMove` `-ValidationOnly` parametern för att validera om webbplatsen kan flyttas.</span><span class="sxs-lookup"><span data-stu-id="b5f94-148">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="b5f94-149">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b5f94-149">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="b5f94-150">Detta returnerar *framgång* om webbplatsen är redo att flyttas eller *inte fungerar* om något av de blockerade villkoren är uppfyllt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-150">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="b5f94-151">Starta en SharePoint-webbplats geo Move för en webbplats utan associerad Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="b5f94-151">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="b5f94-152">Som standard ändras initial URL för webbplatsen till URL-adressen för målets Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-152">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="b5f94-153">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b5f94-153">For example:</span></span>

<span data-ttu-id="b5f94-154"><https://Contoso.sharepoint.com/sites/projectx> som <https://ContosoEUR.sharepoint.com/sites/projectx></span><span class="sxs-lookup"><span data-stu-id="b5f94-154"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projectx></span></span>

<span data-ttu-id="b5f94-155">För webbplatser som inte har Microsoft 365-gruppassociationer kan du även byta namn på webbplatsen med hjälp av `-DestinationUrl` parametern.</span><span class="sxs-lookup"><span data-stu-id="b5f94-155">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="b5f94-156">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b5f94-156">For example:</span></span>

<span data-ttu-id="b5f94-157"><https://Contoso.sharepoint.com/sites/projectx> som <https://ContosoEUR.sharepoint.com/sites/projecty></span><span class="sxs-lookup"><span data-stu-id="b5f94-157"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projecty></span></span>

<span data-ttu-id="b5f94-158">Starta webbplatsen genom att köra:</span><span class="sxs-lookup"><span data-stu-id="b5f94-158">To start the site move, run:</span></span>

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Skärm bild av PowerShell-fönstret med start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="b5f94-160">Starta en SharePoint-webbplats geo Move för en Microsoft 365-gruppansluten webbplats</span><span class="sxs-lookup"><span data-stu-id="b5f94-160">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="b5f94-161">Om du vill flytta en Office 365-gruppansluten webbplats måste den globala administratören eller SharePoint-administratören först ändra den förvalda data plats (PDL) för gruppen Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5f94-161">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="b5f94-162">Så här anger du PDL för en Microsoft 365-grupp:</span><span class="sxs-lookup"><span data-stu-id="b5f94-162">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

<span data-ttu-id="b5f94-163">När du har uppdaterat PDL kan du börja flytta webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="b5f94-163">Once you have updated the PDL, you can start the site move:</span></span>

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="b5f94-164">Avbryta en SharePoint-webbplats geo Move</span><span class="sxs-lookup"><span data-stu-id="b5f94-164">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="b5f94-165">Du kan stoppa en SharePoint-webbplats geo flytt, förutsatt att flytten inte pågår eller slutförs med hjälp av `Stop-SPOSiteContentMove` cmdleten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-165">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="b5f94-166">Kontrol lera status för en SharePoint-webbplats geo Move</span><span class="sxs-lookup"><span data-stu-id="b5f94-166">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="b5f94-167">Du kan bestämma statusen för en webbplats som flyttas i vårt från den geo som du är ansluten till genom att använda följande cmdletar:</span><span class="sxs-lookup"><span data-stu-id="b5f94-167">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="b5f94-168">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (icke-gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="b5f94-168">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="b5f94-169">[Get-SPOUnifiedGroupMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="b5f94-169">[Get-SPOUnifiedGroupMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Group-connected sites)</span></span>

<span data-ttu-id="b5f94-170">Använd `-SourceSiteUrl` parametern för att ange den webbplats som du vill visa status för.</span><span class="sxs-lookup"><span data-stu-id="b5f94-170">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="b5f94-171">Flytt status beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="b5f94-171">The move statuses are described in the following table.</span></span>

****

|<span data-ttu-id="b5f94-172">Status</span><span class="sxs-lookup"><span data-stu-id="b5f94-172">Status</span></span>|<span data-ttu-id="b5f94-173">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b5f94-173">Description</span></span>|
|---|---|
|<span data-ttu-id="b5f94-174">Redo att utlösa</span><span class="sxs-lookup"><span data-stu-id="b5f94-174">Ready to Trigger</span></span>|<span data-ttu-id="b5f94-175">Flytten har inte påbörjats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-175">The move has not started.</span></span>|
|<span data-ttu-id="b5f94-176">Överföring</span><span class="sxs-lookup"><span data-stu-id="b5f94-176">Scheduled</span></span>|<span data-ttu-id="b5f94-177">Flyttningen är i kö men har inte startat ännu.</span><span class="sxs-lookup"><span data-stu-id="b5f94-177">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="b5f94-178">Inaktivitet (ej tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="b5f94-178">InProgress (n/4)</span></span>|<span data-ttu-id="b5f94-179">Flytten pågår i något av följande lägen: verifiering (1/4), säkerhets kopiering (2/4), återställning (3/4), rensning (4/4).</span><span class="sxs-lookup"><span data-stu-id="b5f94-179">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="b5f94-180">Bra</span><span class="sxs-lookup"><span data-stu-id="b5f94-180">Success</span></span>|<span data-ttu-id="b5f94-181">Flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="b5f94-181">The move has completed successfully.</span></span>|
|<span data-ttu-id="b5f94-182">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="b5f94-182">Failed</span></span>|<span data-ttu-id="b5f94-183">Det gick inte att flytta.</span><span class="sxs-lookup"><span data-stu-id="b5f94-183">The move failed.</span></span>|
|

<span data-ttu-id="b5f94-184">Du kan också använda `-Verbose` alternativet för att visa ytterligare information om flytten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-184">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="b5f94-185">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="b5f94-185">User experience</span></span>

<span data-ttu-id="b5f94-186">Webbplats användare bör meddela minimala störningar när deras webbplats flyttas till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-186">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="b5f94-187">Om du tar bort ett kort känsligt tillstånd under flytten fortsätter befintliga länkar och behörigheter att fungera som förväntat när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="b5f94-187">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="b5f94-188">Webbplatsmallar</span><span class="sxs-lookup"><span data-stu-id="b5f94-188">Site</span></span>

<span data-ttu-id="b5f94-189">När flytten pågår är webbplatsen skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="b5f94-189">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="b5f94-190">När flytten är klar dirigeras användaren till den nya webbplatsen på den nya geo platsen när de klickar på bok märken eller andra länkar till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-190">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="b5f94-191">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b5f94-191">Permissions</span></span>

<span data-ttu-id="b5f94-192">Användare som har behörighet till webbplatsen fortsätter att ha åtkomst till webbplatsen under flytten och när den är slutförd.</span><span class="sxs-lookup"><span data-stu-id="b5f94-192">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-client"></a><span data-ttu-id="b5f94-193">Synkroniseringsklient</span><span class="sxs-lookup"><span data-stu-id="b5f94-193">Sync Client</span></span>

<span data-ttu-id="b5f94-194">Synkroniseringsklienten kommer automatiskt att upptäcka och överföra synkronisering till den nya platsen när webbplatsen har flyttats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-194">The sync client will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="b5f94-195">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b5f94-195">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="b5f94-196">(Version 17.3.6943.0625 eller senare krävs för synkroniseringsklient.)</span><span class="sxs-lookup"><span data-stu-id="b5f94-196">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="b5f94-197">Om en användare uppdaterar en fil medan flytten pågår visas en avisering om att fil överföringar är väntande när flytten pågår.</span><span class="sxs-lookup"><span data-stu-id="b5f94-197">If a user updates a file while the move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="b5f94-198">Dela länkar</span><span class="sxs-lookup"><span data-stu-id="b5f94-198">Sharing links</span></span>

<span data-ttu-id="b5f94-199">När SharePoint-webbplatsens geo Move-flyttning är klar omdirigeras de befintliga delade länkarna för de filer som flyttas automatiskt till den nya geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-199">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="b5f94-200">Senast använda filer i Office (MRU)</span><span class="sxs-lookup"><span data-stu-id="b5f94-200">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="b5f94-201">MRU-tjänsten uppdateras med webbplats-URL: en och dess innehålls webb adresser när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="b5f94-201">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="b5f94-202">Det här gäller för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="b5f94-202">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="b5f94-203">OneNote-upplevelse</span><span class="sxs-lookup"><span data-stu-id="b5f94-203">OneNote experience</span></span>

<span data-ttu-id="b5f94-204">I OneNote Win32-klient-och UWP (Universal) identifieras och sömlöst synkronisera antecknings böcker automatiskt när webbplatsen flyttas.</span><span class="sxs-lookup"><span data-stu-id="b5f94-204">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="b5f94-205">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b5f94-205">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="b5f94-206">Den enda synliga indikatorn för användaren är att synkronisering av antecknings boken Miss lyckas när webbplatsen flyttas.</span><span class="sxs-lookup"><span data-stu-id="b5f94-206">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="b5f94-207">Den här funktionen finns i följande OneNote-klient versioner:</span><span class="sxs-lookup"><span data-stu-id="b5f94-207">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="b5f94-208">OneNote Win32 – version 16.0.8326.2096 (och senare)</span><span class="sxs-lookup"><span data-stu-id="b5f94-208">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="b5f94-209">OneNote UWP – version 16.0.8431.1006 (och senare)</span><span class="sxs-lookup"><span data-stu-id="b5f94-209">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="b5f94-210">OneNote-mobilapp – version 16.0.8431.1011 (och senare)</span><span class="sxs-lookup"><span data-stu-id="b5f94-210">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="b5f94-211">Team (gäller för Microsoft 365-gruppanslutna webbplatser)</span><span class="sxs-lookup"><span data-stu-id="b5f94-211">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="b5f94-212">När SharePoint-webbplatsens geo Move-flyttning är klar har användarna åtkomst till sina Microsoft 365-gruppfiler i Teams-appen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-212">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="b5f94-213">Dessutom fortsätter filer som delas via Teams chatt från sina webbplatser innan de geo flytten fortsätta att fungera när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="b5f94-213">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="b5f94-214">SharePoint-mobilapp (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="b5f94-214">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="b5f94-215">SharePoint-mobilappen är Cross geo-kompatibel och kan upptäcka webbplatsens nya Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-215">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="b5f94-216">SharePoint-arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="b5f94-216">SharePoint workflows</span></span>

<span data-ttu-id="b5f94-217">SharePoint 2013-arbets flöden måste publiceras igen efter att webbplatsen har flyttats.</span><span class="sxs-lookup"><span data-stu-id="b5f94-217">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="b5f94-218">SharePoint 2010-arbets flöden fungerar normalt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-218">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="b5f94-219">Appar</span><span class="sxs-lookup"><span data-stu-id="b5f94-219">Apps</span></span>

<span data-ttu-id="b5f94-220">Om du flyttar en webbplats med appar måste du återaktivera programmet på den nya geo-platsen för webbplatsen, och dess anslutningar kanske inte är tillgängliga på Geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-220">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="b5f94-221">Flyter</span><span class="sxs-lookup"><span data-stu-id="b5f94-221">Flow</span></span>

<span data-ttu-id="b5f94-222">I de flesta fall fortsätter flöden att fungera efter en SharePoint-webbplats geo-flytt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-222">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="b5f94-223">Vi rekommenderar att du testar dem när flytten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="b5f94-223">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="b5f94-224">PowerApps</span><span class="sxs-lookup"><span data-stu-id="b5f94-224">PowerApps</span></span>

<span data-ttu-id="b5f94-225">PowerApps måste återskapas på mål platsen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-225">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="b5f94-226">Data förflyttning mellan geo-platser</span><span class="sxs-lookup"><span data-stu-id="b5f94-226">Data movement between geo locations</span></span>

<span data-ttu-id="b5f94-227">SharePoint använder Azure Blob Storage för innehållet, medan metadata som är kopplade till webbplatser och dess filer lagras i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b5f94-227">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="b5f94-228">När webbplatsen har flyttats från källans Geo-plats till dess mål plats, flyttas även dess tillhör ande blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="b5f94-228">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="b5f94-229">Blob-lagringen flyttas i cirka 40 dagar.</span><span class="sxs-lookup"><span data-stu-id="b5f94-229">Blob Storage moves complete in approximately 40 days.</span></span>
