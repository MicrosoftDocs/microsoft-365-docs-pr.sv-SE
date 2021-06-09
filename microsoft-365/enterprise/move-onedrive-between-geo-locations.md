---
title: Flytta en OneDrive webbplats till en annan geoplats
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Hitta information om hur du flyttar OneDrive en webbplats till en annan geo plats, till exempel hur du schemalägger flyttningar av webbplatser och kommunicerar förväntningar till användarna.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694295"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="6e647-103">Flytta en OneDrive webbplats till en annan geoplats</span><span class="sxs-lookup"><span data-stu-id="6e647-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="6e647-104">Med OneDrive geoflyttning kan du flytta en användares OneDrive till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="6e647-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="6e647-105">OneDrive geoflyttning utförs av den SharePoint onlineadministratören eller den Microsoft 365 globala administratören.</span><span class="sxs-lookup"><span data-stu-id="6e647-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="6e647-106">Innan du startar en OneDrive geoflyt måste du meddela den användare vars OneDrive flyttas och rekommendera att de stänger alla filer under hela flyttningen.</span><span class="sxs-lookup"><span data-stu-id="6e647-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="6e647-107">(Om användaren har ett dokument öppet med Office-klienten under flyttningen måste dokumentet sparas på den nya platsen när flyttningen slutförts.) Flyttningen kan vid behov schemaläggas till en kommande tid.</span><span class="sxs-lookup"><span data-stu-id="6e647-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="6e647-108">Tjänsten OneDrive använder Azure Blob Storage för att lagra innehåll.</span><span class="sxs-lookup"><span data-stu-id="6e647-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="6e647-109">Den Storage blob som är kopplad till användarens OneDrive kommer att flyttas från källan till den geoa målplatsen inom 40 dagar efter att OneDrive vara tillgänglig för användaren.</span><span class="sxs-lookup"><span data-stu-id="6e647-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="6e647-110">Åtkomsten till användarens OneDrive återställs så snart måladressen OneDrive tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6e647-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="6e647-111">Under OneDrive geoflyttningsfönster (ca 2–6 timmar) är användarens OneDrive skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="6e647-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="6e647-112">Användaren kan fortfarande komma åt sina filer via OneDrive synkroniseringsklienten eller deras OneDrive på SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6e647-112">The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="6e647-113">När OneDrive geoflyttning är klar ansluts användaren automatiskt till sin OneDrive på den geoplats där de navigerar till OneDrive i Microsoft 365-startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="6e647-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="6e647-114">Synkroniseringsklienten börjar automatiskt synkronisera från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="6e647-114">The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="6e647-115">Procedurerna i den här artikeln [kräver Microsoft Office SharePoint Online PowerShell Module.](https://www.microsoft.com/download/details.aspx?id=35588)</span><span class="sxs-lookup"><span data-stu-id="6e647-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="6e647-116">Kommunicera till användarna</span><span class="sxs-lookup"><span data-stu-id="6e647-116">Communicating to your users</span></span>

<span data-ttu-id="6e647-117">När du OneDrive webbplatser mellan geografiska platser är det viktigt att kommunicera till användarna vad de kan förvänta sig.</span><span class="sxs-lookup"><span data-stu-id="6e647-117">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect.</span></span> <span data-ttu-id="6e647-118">Det kan minska risken för förvirring och samtal till supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="6e647-118">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="6e647-119">Skicka e-post till användarna innan flytten och informera dem om följande information:</span><span class="sxs-lookup"><span data-stu-id="6e647-119">Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="6e647-120">När flyttningen förväntas starta och hur lång tid den förväntas ta</span><span class="sxs-lookup"><span data-stu-id="6e647-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="6e647-121">Vilken geoplats deras OneDrive flyttas till och URL:en för att komma åt den nya platsen</span><span class="sxs-lookup"><span data-stu-id="6e647-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="6e647-122">De bör stänga sina filer och inte göra ändringar under flytten.</span><span class="sxs-lookup"><span data-stu-id="6e647-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="6e647-123">Filbehörigheter och delning ändras inte som ett resultat av flyttningen.</span><span class="sxs-lookup"><span data-stu-id="6e647-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="6e647-124">Vad du kan förvänta dig [av användarupplevelsen i en geomiljö med flera miljöer](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="6e647-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="6e647-125">Se till att skicka ett e-postmeddelande till användarna när flytten har slutförts och informera dem om att de kan fortsätta arbeta i OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6e647-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="6e647-126">Schemalägga OneDrive flyttningar av webbplatser</span><span class="sxs-lookup"><span data-stu-id="6e647-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="6e647-127">Du kan schemalägga OneDrive webbplatsflyttningar i förväg (beskrivs senare i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="6e647-127">You can schedule OneDrive site moves in advance (described later in this article).</span></span> <span data-ttu-id="6e647-128">Vi rekommenderar att du börjar med ett litet antal användare för att verifiera dina arbetsflöden och kommunikationsstrategier.</span><span class="sxs-lookup"><span data-stu-id="6e647-128">We recommend that you start with a small number of users to validate your workflows and communication strategies.</span></span> <span data-ttu-id="6e647-129">När du har känner till processen kan du schemalägga flyttningar enligt följande:</span><span class="sxs-lookup"><span data-stu-id="6e647-129">Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="6e647-130">Du kan schemalägga upp till 4 000 flyttningar i taget.</span><span class="sxs-lookup"><span data-stu-id="6e647-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="6e647-131">När flytten börjar kan du schemalägga fler, med högst 4 000 väntande flyttningar i kön och en viss tid.</span><span class="sxs-lookup"><span data-stu-id="6e647-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="6e647-132">Den maximala storleken på en OneDrive som kan flyttas är 1 terabyte (1 TB).</span><span class="sxs-lookup"><span data-stu-id="6e647-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="6e647-133">Flytta en OneDrive webbplats</span><span class="sxs-lookup"><span data-stu-id="6e647-133">Moving a OneDrive site</span></span>

<span data-ttu-id="6e647-134">För att OneDrive en geoflyttning måste innehavaradministratören först ange lämplig plats för användarens önskade dataplats (PDL).</span><span class="sxs-lookup"><span data-stu-id="6e647-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="6e647-135">När PDL har angetts väntar du i minst 24 timmar på att PDL-uppdateringen ska synkroniseras mellan de geografiska platserna innan du påbörjar OneDrive geoflyttningen.</span><span class="sxs-lookup"><span data-stu-id="6e647-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="6e647-136">När du använder cmdlets för geoflyttning ansluter du till SPO-tjänsten på användarens aktuella OneDrive geoplats med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6e647-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="6e647-137">Till exempel: Om du OneDrive användarens "Matt@contosoenergy.onmicrosoft.com" kan du ansluta till EURO SharePoint administrationscenter eftersom användarens OneDrive är i euro geoplats:</span><span class="sxs-lookup"><span data-stu-id="6e647-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Skärmbild av PowerShell-fönstret med cmdleten connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="6e647-139">Validera miljön</span><span class="sxs-lookup"><span data-stu-id="6e647-139">Validating the environment</span></span>

<span data-ttu-id="6e647-140">Innan du startar en OneDrive geoflyttning rekommenderar vi att du verifierar miljön.</span><span class="sxs-lookup"><span data-stu-id="6e647-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="6e647-141">Om du vill säkerställa att alla geoplatser är kompatibla kör du:</span><span class="sxs-lookup"><span data-stu-id="6e647-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="6e647-142">En lista över dina geografiska platser visas och om innehåll kan flyttas mellan dem kallas "Kompatibel".</span><span class="sxs-lookup"><span data-stu-id="6e647-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="6e647-143">Om kommandot returnerar "Inkompatibelt" försöker du igen med att validera statusen vid ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="6e647-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="6e647-144">Om en OneDrive innehåller en underwebbplats kan den till exempel inte flyttas.</span><span class="sxs-lookup"><span data-stu-id="6e647-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="6e647-145">Du kan använda Start-SPOUserAndContentMove-cmdleten med parametern -ValidationOnly för att verifiera om OneDrive kan flyttas:</span><span class="sxs-lookup"><span data-stu-id="6e647-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="6e647-146">Det returnerar Success om OneDrive är redo att flyttas eller Misslyckades om det finns ett juridiskt väntande eller en underwebbplats som skulle förhindra flytten.</span><span class="sxs-lookup"><span data-stu-id="6e647-146">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move.</span></span> <span data-ttu-id="6e647-147">När du har verifierat att OneDrive är redo att flytta kan du starta flytten.</span><span class="sxs-lookup"><span data-stu-id="6e647-147">Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="6e647-148">Starta en OneDrive geoflyttning</span><span class="sxs-lookup"><span data-stu-id="6e647-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="6e647-149">Starta flytten genom att köra:</span><span class="sxs-lookup"><span data-stu-id="6e647-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="6e647-150">Med hjälp av dessa parametrar:</span><span class="sxs-lookup"><span data-stu-id="6e647-150">Using these parameters:</span></span>

-   <span data-ttu-id="6e647-151">_UserPrincipalName_ – UPN för användaren vars OneDrive flyttas.</span><span class="sxs-lookup"><span data-stu-id="6e647-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="6e647-152">_DestinationDataLocation_ – Geo-Location här OneDrive behöver flyttas.</span><span class="sxs-lookup"><span data-stu-id="6e647-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="6e647-153">Det ska vara samma som användarens önskade dataplats.</span><span class="sxs-lookup"><span data-stu-id="6e647-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="6e647-154">Om du till exempel vill flytta OneDrive matt@contosoenergy.onmicrosoft.com från EURO till AUS kör du:</span><span class="sxs-lookup"><span data-stu-id="6e647-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Skärmbild av PowerShell-fönstret med Start-SPOUserAndContentMove cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="6e647-156">Om du vill schemalägga en geoflyttning till en senare tid använder du någon av följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="6e647-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="6e647-157">_PreferredMoveBeginDate_ – Flyttningen börjar troligtvis vid den här angivna tiden.</span><span class="sxs-lookup"><span data-stu-id="6e647-157">_PreferredMoveBeginDate_ – The move will likely begin at this specified time.</span></span> <span data-ttu-id="6e647-158">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="6e647-158">Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="6e647-159">_PreferredMoveEndDate_ – Flyttningen slutförs förmodligen vid den angivna tiden, med bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="6e647-159">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis.</span></span> <span data-ttu-id="6e647-160">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="6e647-160">Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="6e647-161">Avbryta en OneDrive geoflyttning</span><span class="sxs-lookup"><span data-stu-id="6e647-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="6e647-162">Du kan stoppa geoflyttningen av en användares OneDrive, förutsatt att flyttningen inte pågår eller slutförs med hjälp av cmdleten:</span><span class="sxs-lookup"><span data-stu-id="6e647-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="6e647-163">Där _UserPrincipalName_ är UPN för den användare vars OneDrive du vill stoppa.</span><span class="sxs-lookup"><span data-stu-id="6e647-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="6e647-164">Fastställa aktuell status</span><span class="sxs-lookup"><span data-stu-id="6e647-164">Determining current status</span></span>

<span data-ttu-id="6e647-165">Du kan kontrollera statusen för OneDrive geoflyttning in i eller ut ur den geo som du är ansluten till med hjälp av Get-SPOUserAndContentMoveState-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="6e647-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="6e647-166">Flyttningsstatusen beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6e647-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e647-167"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="6e647-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="6e647-168"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="6e647-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6e647-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="6e647-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="6e647-170">Flyttningen har inte startat.</span><span class="sxs-lookup"><span data-stu-id="6e647-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6e647-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="6e647-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="6e647-172">Flyttningen pågår i ett av följande tillstånd: Verifiering (1/4), Säkerhetskopiering (2/4), Återställ (3/4), Rensning (4/4).</span><span class="sxs-lookup"><span data-stu-id="6e647-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="6e647-173">Lyckades</span><span class="sxs-lookup"><span data-stu-id="6e647-173">Success</span></span></td>
<td align="left"><span data-ttu-id="6e647-174">Flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6e647-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6e647-175">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="6e647-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="6e647-176">Flyttningen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="6e647-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6e647-177">Ta reda på statusen för en specifik användares flytt med parametern UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="6e647-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="6e647-178">Om du vill hitta status för alla flyttningar in eller ut från den geoplats som du är ansluten till använder du parametern MoveState med något av följande värden: NotStarted, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="6e647-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="6e647-179">Du kan också lägga till `-Verbose` parametern för fler utförliga beskrivningar av flyttningstillståndet.</span><span class="sxs-lookup"><span data-stu-id="6e647-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="6e647-180">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="6e647-180">User Experience</span></span>

<span data-ttu-id="6e647-181">Användare av OneDrive märker minimal störning om deras OneDrive flyttas till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="6e647-181">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location.</span></span> <span data-ttu-id="6e647-182">Förutom ett kort skrivskyddad tillstånd under flyttningen kommer befintliga länkar och behörigheter att fungera som förväntat när flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6e647-182">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="6e647-183">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="6e647-183">OneDrive for Business</span></span>

<span data-ttu-id="6e647-184">Medan flytten pågår är användarens OneDrive skrivskydd.</span><span class="sxs-lookup"><span data-stu-id="6e647-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="6e647-185">När flytten är slutförd dirigeras användaren till sin OneDrive på den nya geoplatsen när de navigerar till OneDrive Microsoft 365-startprogrammet eller en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="6e647-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="6e647-186">Behörigheter för OneDrive innehåll</span><span class="sxs-lookup"><span data-stu-id="6e647-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="6e647-187">Användare med behörighet OneDrive innehåll har fortsatt åtkomst till innehållet under flytten och när det är klart.</span><span class="sxs-lookup"><span data-stu-id="6e647-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="6e647-188">OneDrive Synkroniseringsklient</span><span class="sxs-lookup"><span data-stu-id="6e647-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="6e647-189">Synkroniseringsklienten OneDrive automatiskt identifiera och överföra synkroniseringen till den nya OneDrive-platsen när OneDrive geoflyttningen är klar.</span><span class="sxs-lookup"><span data-stu-id="6e647-189">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="6e647-190">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6e647-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="6e647-191">(Version 17.3.6943.0625 eller senare av synkroniseringsklienten krävs.)</span><span class="sxs-lookup"><span data-stu-id="6e647-191">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="6e647-192">Om en användare uppdaterar en fil medan OneDrive geoflyttning pågår meddelar synkroniseringsklienten att filuppladdningar väntar medan flyttningen pågår.</span><span class="sxs-lookup"><span data-stu-id="6e647-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="6e647-193">Delningslänkar</span><span class="sxs-lookup"><span data-stu-id="6e647-193">Sharing links</span></span> 

<span data-ttu-id="6e647-194">När OneDrive geoflytts slutförande omdirigeras de befintliga delade länkarna för de filer som har flyttats automatiskt till den nya geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="6e647-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="6e647-195">OneNote Upplevelse</span><span class="sxs-lookup"><span data-stu-id="6e647-195">OneNote Experience</span></span> 

<span data-ttu-id="6e647-196">OneNote hos win32-klienten och UWP-appen (Universell) identifierar och synkroniserar automatiskt anteckningsböcker till den nya OneDrive-platsen när OneDrive geoflyttningen är klar.</span><span class="sxs-lookup"><span data-stu-id="6e647-196">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete.</span></span> <span data-ttu-id="6e647-197">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6e647-197">The user does not need to sign-in again or take any other action.</span></span> <span data-ttu-id="6e647-198">Den enda synliga indikatorn för användaren är att synkroniseringen av anteckningsboken misslyckades OneDrive geoflyttning pågår.</span><span class="sxs-lookup"><span data-stu-id="6e647-198">The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress.</span></span> <span data-ttu-id="6e647-199">Den här versionen är tillgänglig på följande OneNote klientversioner:</span><span class="sxs-lookup"><span data-stu-id="6e647-199">This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="6e647-200">OneNote win32 – version 16.0.8326.2096 (och senare)</span><span class="sxs-lookup"><span data-stu-id="6e647-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="6e647-201">OneNote UWP – version 16.0.8431.1006 (och senare)</span><span class="sxs-lookup"><span data-stu-id="6e647-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="6e647-202">OneNote Mobilapp – version 16.0.8431.1011 (och senare)</span><span class="sxs-lookup"><span data-stu-id="6e647-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="6e647-203">Teams appen</span><span class="sxs-lookup"><span data-stu-id="6e647-203">Teams app</span></span>

<span data-ttu-id="6e647-204">När OneDrive geoflyttning är klart har användarna åtkomst till sina OneDrive-filer i Teams programmet.</span><span class="sxs-lookup"><span data-stu-id="6e647-204">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app.</span></span> <span data-ttu-id="6e647-205">Dessutom kommer filer som delas via Teams chatt från deras OneDrive innan geoflyttningen att fungera när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="6e647-205">Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="6e647-206">OneDrive för företag Mobilapp (iOS)</span><span class="sxs-lookup"><span data-stu-id="6e647-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="6e647-207">När OneDrive geoflyttning är slutförd måste användaren logga ut och logga in igen i iOS-mobilappen för att synkronisera till den nya OneDrive platsen.</span><span class="sxs-lookup"><span data-stu-id="6e647-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="6e647-208">Befintliga följda grupper och webbplatser</span><span class="sxs-lookup"><span data-stu-id="6e647-208">Existing followed groups and sites</span></span>

<span data-ttu-id="6e647-209">Följda webbplatser och grupper visas i användarens OneDrive oavsett deras geografiska position.</span><span class="sxs-lookup"><span data-stu-id="6e647-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="6e647-210">Webbplatser och grupper som ligger på en annan geoplats öppnas på en separat flik.</span><span class="sxs-lookup"><span data-stu-id="6e647-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="6e647-211">Delve Geo-URL-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="6e647-211">Delve Geo URL updates</span></span>

<span data-ttu-id="6e647-212">Användare skickas bara till den Delve geo som motsvarar deras PDL när deras OneDrive har flyttats till det nya geo.</span><span class="sxs-lookup"><span data-stu-id="6e647-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
