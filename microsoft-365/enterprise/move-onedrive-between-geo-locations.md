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
ms.openlocfilehash: 9e75c8e4102f82d4ab6e0f99ea26e1c0ad8b4bab
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362252"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="0e71b-103">Flytta en OneDrive webbplats till en annan geoplats</span><span class="sxs-lookup"><span data-stu-id="0e71b-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="0e71b-104">Med OneDrive geoflyttning kan du flytta en användares OneDrive till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="0e71b-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="0e71b-105">OneDrive geoflyttning utförs av den SharePoint onlineadministratören eller den Microsoft 365 globala administratören.</span><span class="sxs-lookup"><span data-stu-id="0e71b-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="0e71b-106">Innan du startar en OneDrive geoflyt måste du meddela den användare vars OneDrive flyttas och rekommendera att de stänger alla filer under hela flyttningen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="0e71b-107">(Om användaren har ett dokument öppet med Office-klienten under flyttningen måste dokumentet sparas på den nya platsen när flyttningen slutförts.) Flyttningen kan vid behov schemaläggas till en kommande tid.</span><span class="sxs-lookup"><span data-stu-id="0e71b-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="0e71b-108">Tjänsten OneDrive använder Azure Blob Storage för att lagra innehåll.</span><span class="sxs-lookup"><span data-stu-id="0e71b-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="0e71b-109">Den Storage blob som är kopplad till användarens OneDrive kommer att flyttas från källan till den geoa målplatsen inom 40 dagar efter att OneDrive vara tillgänglig för användaren.</span><span class="sxs-lookup"><span data-stu-id="0e71b-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="0e71b-110">Åtkomsten till användarens OneDrive återställs så snart måladressen OneDrive tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0e71b-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="0e71b-111">Under OneDrive geoflyttningsfönster (ca 2–6 timmar) är användarens OneDrive skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="0e71b-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="0e71b-112">Användaren kan fortfarande komma åt sina filer via OneDrive-synkronisering appen eller deras OneDrive på SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0e71b-112">The user can still access their files via the OneDrive sync app or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="0e71b-113">När OneDrive geoflyttning är klar ansluts användaren automatiskt till sin OneDrive på den geoplats där de navigerar till OneDrive i Microsoft 365-startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="0e71b-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="0e71b-114">Synkroniseringsappen börjar automatiskt synkronisera från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-114">The sync app will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="0e71b-115">Procedurerna i den här artikeln [kräver Microsoft Office SharePoint Online PowerShell Module.](https://www.microsoft.com/download/details.aspx?id=35588)</span><span class="sxs-lookup"><span data-stu-id="0e71b-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="0e71b-116">Kommunicera till användarna</span><span class="sxs-lookup"><span data-stu-id="0e71b-116">Communicating to your users</span></span>

<span data-ttu-id="0e71b-117">När du OneDrive webbplatser mellan geografiska platser är det viktigt att kommunicera till användarna vad de kan förvänta sig.</span><span class="sxs-lookup"><span data-stu-id="0e71b-117">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect.</span></span> <span data-ttu-id="0e71b-118">Det kan minska risken för förvirring och samtal till supportavdelningen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-118">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="0e71b-119">Skicka e-post till användarna innan flytten och informera dem om följande information:</span><span class="sxs-lookup"><span data-stu-id="0e71b-119">Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="0e71b-120">När flyttningen förväntas starta och hur lång tid den förväntas ta</span><span class="sxs-lookup"><span data-stu-id="0e71b-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="0e71b-121">Vilken geoplats deras OneDrive flyttas till och URL:en för att komma åt den nya platsen</span><span class="sxs-lookup"><span data-stu-id="0e71b-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="0e71b-122">De bör stänga sina filer och inte göra ändringar under flytten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="0e71b-123">Filbehörigheter och delning ändras inte som ett resultat av flyttningen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="0e71b-124">Vad du kan förvänta dig [av användarupplevelsen i en geomiljö med flera miljöer](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="0e71b-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="0e71b-125">Se till att skicka ett e-postmeddelande till användarna när flytten har slutförts och informera dem om att de kan fortsätta arbeta i OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0e71b-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="0e71b-126">Schemalägga OneDrive flyttningar av webbplatser</span><span class="sxs-lookup"><span data-stu-id="0e71b-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="0e71b-127">Du kan schemalägga OneDrive webbplatsflyttningar i förväg (beskrivs senare i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="0e71b-127">You can schedule OneDrive site moves in advance (described later in this article).</span></span> <span data-ttu-id="0e71b-128">Vi rekommenderar att du börjar med ett litet antal användare för att verifiera dina arbetsflöden och kommunikationsstrategier.</span><span class="sxs-lookup"><span data-stu-id="0e71b-128">We recommend that you start with a small number of users to validate your workflows and communication strategies.</span></span> <span data-ttu-id="0e71b-129">När du har känner till processen kan du schemalägga flyttningar enligt följande:</span><span class="sxs-lookup"><span data-stu-id="0e71b-129">Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="0e71b-130">Du kan schemalägga upp till 4 000 flyttningar i taget.</span><span class="sxs-lookup"><span data-stu-id="0e71b-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="0e71b-131">När flytten börjar kan du schemalägga fler, med högst 4 000 väntande flyttningar i kön och en viss tid.</span><span class="sxs-lookup"><span data-stu-id="0e71b-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="0e71b-132">Den maximala storleken på en OneDrive som kan flyttas är 1 terabyte (1 TB).</span><span class="sxs-lookup"><span data-stu-id="0e71b-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="0e71b-133">Flytta en OneDrive webbplats</span><span class="sxs-lookup"><span data-stu-id="0e71b-133">Moving a OneDrive site</span></span>

<span data-ttu-id="0e71b-134">För att OneDrive en geoflyttning måste innehavaradministratören först ange lämplig plats för användarens önskade dataplats (PDL).</span><span class="sxs-lookup"><span data-stu-id="0e71b-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="0e71b-135">När PDL har angetts väntar du i minst 24 timmar på att PDL-uppdateringen ska synkroniseras mellan de geografiska platserna innan du påbörjar OneDrive geoflyttningen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="0e71b-136">När du använder cmdlets för geoflyttning ansluter du till SPO-tjänsten på användarens aktuella OneDrive geoplats med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0e71b-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="0e71b-137">Till exempel: Om du OneDrive användarens "Matt@contosoenergy.onmicrosoft.com" kan du ansluta till EURO SharePoint administrationscenter eftersom användarens OneDrive är i euro geoplats:</span><span class="sxs-lookup"><span data-stu-id="0e71b-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Skärmbild av PowerShell-fönstret med cmdleten connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="0e71b-139">Validera miljön</span><span class="sxs-lookup"><span data-stu-id="0e71b-139">Validating the environment</span></span>

<span data-ttu-id="0e71b-140">Innan du startar en OneDrive geoflyttning rekommenderar vi att du verifierar miljön.</span><span class="sxs-lookup"><span data-stu-id="0e71b-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="0e71b-141">Om du vill säkerställa att alla geoplatser är kompatibla kör du:</span><span class="sxs-lookup"><span data-stu-id="0e71b-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="0e71b-142">En lista över dina geografiska platser visas och om innehåll kan flyttas mellan dem kallas "Kompatibel".</span><span class="sxs-lookup"><span data-stu-id="0e71b-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="0e71b-143">Om kommandot returnerar "Inkompatibelt" försöker du igen med att validera statusen vid ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="0e71b-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="0e71b-144">Om en OneDrive innehåller en underwebbplats kan den till exempel inte flyttas.</span><span class="sxs-lookup"><span data-stu-id="0e71b-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="0e71b-145">Du kan använda Start-SPOUserAndContentMove-cmdleten med parametern -ValidationOnly för att verifiera om OneDrive kan flyttas:</span><span class="sxs-lookup"><span data-stu-id="0e71b-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="0e71b-146">Det returnerar Success om OneDrive är redo att flyttas eller Misslyckades om det finns ett juridiskt väntande eller en underwebbplats som skulle förhindra flytten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-146">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move.</span></span> <span data-ttu-id="0e71b-147">När du har verifierat att OneDrive är redo att flytta kan du starta flytten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-147">Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="0e71b-148">Starta en OneDrive geoflyttning</span><span class="sxs-lookup"><span data-stu-id="0e71b-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="0e71b-149">Starta flytten genom att köra:</span><span class="sxs-lookup"><span data-stu-id="0e71b-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="0e71b-150">Med hjälp av dessa parametrar:</span><span class="sxs-lookup"><span data-stu-id="0e71b-150">Using these parameters:</span></span>

-   <span data-ttu-id="0e71b-151">_UserPrincipalName_ – UPN för användaren vars OneDrive flyttas.</span><span class="sxs-lookup"><span data-stu-id="0e71b-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="0e71b-152">_DestinationDataLocation_ – Geo-Location här OneDrive behöver flyttas.</span><span class="sxs-lookup"><span data-stu-id="0e71b-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="0e71b-153">Det ska vara samma som användarens önskade dataplats.</span><span class="sxs-lookup"><span data-stu-id="0e71b-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="0e71b-154">Om du till exempel vill flytta OneDrive matt@contosoenergy.onmicrosoft.com från EURO till AUS kör du:</span><span class="sxs-lookup"><span data-stu-id="0e71b-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Skärmbild av PowerShell-fönstret med Start-SPOUserAndContentMove cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="0e71b-156">Om du vill schemalägga en geoflyttning till en senare tid använder du någon av följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="0e71b-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="0e71b-157">_PreferredMoveBeginDate_ – Flyttningen börjar troligtvis vid den här angivna tiden.</span><span class="sxs-lookup"><span data-stu-id="0e71b-157">_PreferredMoveBeginDate_ – The move will likely begin at this specified time.</span></span> <span data-ttu-id="0e71b-158">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="0e71b-158">Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="0e71b-159">_PreferredMoveEndDate_ – Flyttningen slutförs förmodligen vid den angivna tiden, med bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="0e71b-159">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis.</span></span> <span data-ttu-id="0e71b-160">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="0e71b-160">Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="0e71b-161">Avbryta en OneDrive geoflyttning</span><span class="sxs-lookup"><span data-stu-id="0e71b-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="0e71b-162">Du kan stoppa geoflyttningen av en användares OneDrive, förutsatt att flyttningen inte pågår eller slutförs med hjälp av cmdleten:</span><span class="sxs-lookup"><span data-stu-id="0e71b-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="0e71b-163">Där _UserPrincipalName_ är UPN för den användare vars OneDrive du vill stoppa.</span><span class="sxs-lookup"><span data-stu-id="0e71b-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="0e71b-164">Fastställa aktuell status</span><span class="sxs-lookup"><span data-stu-id="0e71b-164">Determining current status</span></span>

<span data-ttu-id="0e71b-165">Du kan kontrollera statusen för OneDrive geoflyttning in i eller ut ur den geo som du är ansluten till med hjälp av Get-SPOUserAndContentMoveState-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="0e71b-166">Flyttningsstatusen beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="0e71b-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e71b-167">Status</span><span class="sxs-lookup"><span data-stu-id="0e71b-167">Status</span></span></th>
<th align="left"><span data-ttu-id="0e71b-168">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e71b-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="0e71b-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="0e71b-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="0e71b-170">Flyttningen har inte startat.</span><span class="sxs-lookup"><span data-stu-id="0e71b-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e71b-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="0e71b-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="0e71b-172">Flyttningen pågår i ett av följande tillstånd: Verifiering (1/4), Säkerhetskopiering (2/4), Återställ (3/4), Rensning (4/4).</span><span class="sxs-lookup"><span data-stu-id="0e71b-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e71b-173">Klart</span><span class="sxs-lookup"><span data-stu-id="0e71b-173">Success</span></span></td>
<td align="left"><span data-ttu-id="0e71b-174">Flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0e71b-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e71b-175">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="0e71b-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="0e71b-176">Flyttningen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="0e71b-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0e71b-177">Ta reda på statusen för en specifik användares flytt med parametern UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="0e71b-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="0e71b-178">Om du vill hitta status för alla flyttningar in eller ut från den geoplats som du är ansluten till använder du parametern MoveState med något av följande värden: NotStarted, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="0e71b-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="0e71b-179">Du kan också lägga till `-Verbose` parametern för fler utförliga beskrivningar av flyttningstillståndet.</span><span class="sxs-lookup"><span data-stu-id="0e71b-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="0e71b-180">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="0e71b-180">User Experience</span></span>

<span data-ttu-id="0e71b-181">Användare av OneDrive märker minimal störning om deras OneDrive flyttas till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="0e71b-181">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location.</span></span> <span data-ttu-id="0e71b-182">Förutom ett kort skrivskyddad tillstånd under flyttningen kommer befintliga länkar och behörigheter att fungera som förväntat när flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0e71b-182">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="users-onedrive"></a><span data-ttu-id="0e71b-183">Användarens OneDrive</span><span class="sxs-lookup"><span data-stu-id="0e71b-183">User's OneDrive</span></span>

<span data-ttu-id="0e71b-184">Medan flytten pågår är användarens OneDrive skrivskydd.</span><span class="sxs-lookup"><span data-stu-id="0e71b-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="0e71b-185">När flytten är slutförd dirigeras användaren till sin OneDrive på den nya geoplatsen när de navigerar till OneDrive Microsoft 365-startprogrammet eller en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="0e71b-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="0e71b-186">Behörigheter för OneDrive innehåll</span><span class="sxs-lookup"><span data-stu-id="0e71b-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="0e71b-187">Användare med behörighet OneDrive innehåll har fortsatt åtkomst till innehållet under flytten och när det är klart.</span><span class="sxs-lookup"><span data-stu-id="0e71b-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-app"></a><span data-ttu-id="0e71b-188">OneDrive-synkronisering appen</span><span class="sxs-lookup"><span data-stu-id="0e71b-188">OneDrive sync app</span></span> 

<span data-ttu-id="0e71b-189">Appen OneDrive-synkronisering automatiskt identifiera och överföra synkronisering till den nya OneDrive när OneDrive geoflyttningen är klar.</span><span class="sxs-lookup"><span data-stu-id="0e71b-189">The OneDrive sync app will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="0e71b-190">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0e71b-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="0e71b-191">(Version 17.3.6943.0625 eller senare av synkroniseringsappen krävs.)</span><span class="sxs-lookup"><span data-stu-id="0e71b-191">(Version 17.3.6943.0625 or later of the sync app required.)</span></span>

<span data-ttu-id="0e71b-192">Om en användare uppdaterar en fil medan OneDrive geoflyttning pågår får de ett meddelande i synkroniseringsappen om att filuppladdningar väntar medan flytten pågår.</span><span class="sxs-lookup"><span data-stu-id="0e71b-192">If a user updates a file while the OneDrive geo move is in progress, the sync app will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="0e71b-193">Delningslänkar</span><span class="sxs-lookup"><span data-stu-id="0e71b-193">Sharing links</span></span> 

<span data-ttu-id="0e71b-194">När OneDrive geoflytts slutförande omdirigeras de befintliga delade länkarna för de filer som har flyttats automatiskt till den nya geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="0e71b-195">OneNote Upplevelse</span><span class="sxs-lookup"><span data-stu-id="0e71b-195">OneNote Experience</span></span> 

<span data-ttu-id="0e71b-196">OneNote hos win32-klienten och UWP-appen (Universell) identifierar och synkroniserar automatiskt anteckningsböcker till den nya OneDrive-platsen när OneDrive geoflyttningen är klar.</span><span class="sxs-lookup"><span data-stu-id="0e71b-196">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete.</span></span> <span data-ttu-id="0e71b-197">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0e71b-197">The user does not need to sign-in again or take any other action.</span></span> <span data-ttu-id="0e71b-198">Den enda synliga indikatorn för användaren är att synkroniseringen av anteckningsboken misslyckades OneDrive geoflyttning pågår.</span><span class="sxs-lookup"><span data-stu-id="0e71b-198">The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress.</span></span> <span data-ttu-id="0e71b-199">Den här versionen är tillgänglig på följande OneNote klientversioner:</span><span class="sxs-lookup"><span data-stu-id="0e71b-199">This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="0e71b-200">OneNote win32 – version 16.0.8326.2096 (och senare)</span><span class="sxs-lookup"><span data-stu-id="0e71b-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="0e71b-201">OneNote UWP – version 16.0.8431.1006 (och senare)</span><span class="sxs-lookup"><span data-stu-id="0e71b-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="0e71b-202">OneNote Mobilapp – version 16.0.8431.1011 (och senare)</span><span class="sxs-lookup"><span data-stu-id="0e71b-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="0e71b-203">Teams appen</span><span class="sxs-lookup"><span data-stu-id="0e71b-203">Teams app</span></span>

<span data-ttu-id="0e71b-204">När OneDrive geoflyttning är klart har användarna åtkomst till sina OneDrive-filer i Teams programmet.</span><span class="sxs-lookup"><span data-stu-id="0e71b-204">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app.</span></span> <span data-ttu-id="0e71b-205">Dessutom kommer filer som delas via Teams chatt från deras OneDrive innan geoflyttningen att fungera när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="0e71b-205">Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-mobile-app-ios"></a><span data-ttu-id="0e71b-206">OneDrive Mobilapp (iOS)</span><span class="sxs-lookup"><span data-stu-id="0e71b-206">OneDrive Mobile App (iOS)</span></span> 

<span data-ttu-id="0e71b-207">När OneDrive geoflyttning är slutförd måste användaren logga ut och logga in igen i iOS-mobilappen för att synkronisera till den nya OneDrive platsen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="0e71b-208">Befintliga följda grupper och webbplatser</span><span class="sxs-lookup"><span data-stu-id="0e71b-208">Existing followed groups and sites</span></span>

<span data-ttu-id="0e71b-209">Följda webbplatser och grupper visas i användarens OneDrive oavsett deras geografiska position.</span><span class="sxs-lookup"><span data-stu-id="0e71b-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="0e71b-210">Webbplatser och grupper som ligger på en annan geoplats öppnas på en separat flik.</span><span class="sxs-lookup"><span data-stu-id="0e71b-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="0e71b-211">Delve Geo-URL-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="0e71b-211">Delve Geo URL updates</span></span>

<span data-ttu-id="0e71b-212">Användare skickas bara till den Delve geo som motsvarar deras PDL när deras OneDrive har flyttats till det nya geo.</span><span class="sxs-lookup"><span data-stu-id="0e71b-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
