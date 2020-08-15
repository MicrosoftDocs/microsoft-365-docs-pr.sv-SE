---
title: Flytta en OneDrive-webbplats till en annan Geo-plats
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
description: Hitta information om hur du flyttar en OneDrive-webbplats till en annan Geo-plats, inklusive hur du schemalägger webbplatser, flyttar och kommunicerar förväntningar till användarna.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694295"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="bb5d7-103">Flytta en OneDrive-webbplats till en annan Geo-plats</span><span class="sxs-lookup"><span data-stu-id="bb5d7-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="bb5d7-104">Med OneDrive geo-flytt kan du flytta en användares OneDrive till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="bb5d7-105">OneDrive geo-flytten utförs av SharePoint Online-administratören eller den globala administratören för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="bb5d7-106">Innan du påbörjar en geo-flytt med OneDrive bör du meddela användaren vars OneDrive flyttas och rekommenderar att de stänger alla filer under hela flytt tiden.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="bb5d7-107">(Om användaren har ett dokument öppet med Office-klienten under flytten måste dokumentet sparas på den nya platsen.) Det går att schemalägga en framtida tid om du vill.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="bb5d7-108">OneDrive-tjänsten använder Azure Blob Storage för att lagra innehåll.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="bb5d7-109">Den lagrings-blob som är associerad med användarens OneDrive flyttas från källan till målets Geo-plats inom 40 dagar efter det att OneDrive är tillgängligt för användaren.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="bb5d7-110">Åtkomst till användarens OneDrive återställs så snart mål platsen OneDrive är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="bb5d7-111">Under fönstret OneDrive geo Move (ca 2-6 timmar) är användarens OneDrive skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="bb5d7-112">Användaren kan fortfarande komma åt sina filer via OneDrive-synkroniseringsklienten eller OneDrive-webbplats i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-112">The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="bb5d7-113">När OneDrive geo-flytten är klar kopplas användaren automatiskt till deras OneDrive på Geo-platsen när de navigerar till OneDrive i Microsoft 365-Start programmet.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="bb5d7-114">Synkroniseringsklienten börjar automatiskt synkronisera från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-114">The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="bb5d7-115">Procedurerna i den här artikeln kräver [PowerShell-modulen för Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="bb5d7-116">Kommunicera med användarna</span><span class="sxs-lookup"><span data-stu-id="bb5d7-116">Communicating to your users</span></span>

<span data-ttu-id="bb5d7-117">När du flyttar OneDrive-webbplatser mellan geo platser är det viktigt att du kommunicerar med dina användare vad du kan förvänta dig.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-117">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect.</span></span> <span data-ttu-id="bb5d7-118">Detta kan hjälpa till att minska användarnas förvirring och samtal till din supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-118">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="bb5d7-119">Skicka e-post till dina användare innan du flyttar och meddela dem följande information:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-119">Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="bb5d7-120">När flytten förväntas starta och hur lång tid det förväntas ta</span><span class="sxs-lookup"><span data-stu-id="bb5d7-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="bb5d7-121">Vilken Geo-plats deras OneDrive flyttas till och URL-adressen till den nya platsen</span><span class="sxs-lookup"><span data-stu-id="bb5d7-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="bb5d7-122">De bör stänga sina filer och inte göra ändringar under flytten.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="bb5d7-123">Fil behörigheter och delning ändras inte som ett resultat av flytten.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="bb5d7-124">Vad du kan förvänta dig av [användar gränssnittet i en multi-geo-miljö](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="bb5d7-125">Glöm inte att skicka ett e-postmeddelande till dina användare när flytten har slutförts och du kan fortsätta arbeta på OneDrive.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="bb5d7-126">Schemalägga flytt av OneDrive-webbplatser</span><span class="sxs-lookup"><span data-stu-id="bb5d7-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="bb5d7-127">Du kan schemalägga flytt av OneDrive-webbplatser i förväg (beskrivs längre fram i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-127">You can schedule OneDrive site moves in advance (described later in this article).</span></span> <span data-ttu-id="bb5d7-128">Vi rekommenderar att du börjar med ett fåtal användare för att verifiera dina arbets flöden och kommunikations strategier.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-128">We recommend that you start with a small number of users to validate your workflows and communication strategies.</span></span> <span data-ttu-id="bb5d7-129">När du är van vid processen kan du schemalägga flytten så här:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-129">Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="bb5d7-130">Du kan schemalägga upp till 4 000 i taget.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="bb5d7-131">När flytten börjar kan du schemalägga mer, med högst 4 000 i kön och när som helst.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="bb5d7-132">Den maximala storleken på ett OneDrive som kan flyttas är 1 terabyte (1 TB).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="bb5d7-133">Flytta en OneDrive-webbplats</span><span class="sxs-lookup"><span data-stu-id="bb5d7-133">Moving a OneDrive site</span></span>

<span data-ttu-id="bb5d7-134">För att göra en OneDrive geo-flyttning måste klient administratören först ange användarens önskade data plats (PDL) på lämplig Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="bb5d7-135">När PDL har ställts in väntar du i minst 24 timmar innan uppdatering av PDL ska synkroniseras på de geo platserna innan OneDrive geo-flytten börjar.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="bb5d7-136">När du använder cmdlets för geo Move ansluter du till SPO-tjänsten på användarens aktuella OneDrive-Geo-plats med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="bb5d7-137">Om du till exempel vill flytta OneDrive för användaren ' Matt@contosoenergy.onmicrosoft.com ' ansluter du till det EUR SharePoint Admin Center som användarens OneDrive finns i Geo-platsen i EUR:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Skärm bild av PowerShell-fönstret som visar cmdleten Connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="bb5d7-139">Verifiera miljön</span><span class="sxs-lookup"><span data-stu-id="bb5d7-139">Validating the environment</span></span>

<span data-ttu-id="bb5d7-140">Innan du påbörjar en geo-flytt med OneDrive rekommenderar vi att du validerar miljön.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="bb5d7-141">För att säkerställa att alla geo platser är kompatibla kör du:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="bb5d7-142">Du kommer att se en lista över dina geo platser och om innehållet kan flyttas mellan betecknas som "kompatibel".</span><span class="sxs-lookup"><span data-stu-id="bb5d7-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="bb5d7-143">Om kommandot returnerar "inkompatibelt" kan du försöka med att bekräfta statusen senare.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="bb5d7-144">Om OneDrive innehåller en under webbplats kan du till exempel inte flytta den.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="bb5d7-145">Du kan använda cmdleten Start-SPOUserAndContentMove med parametern-ValidationOnly för att kontrol lera om OneDrive kan flyttas:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="bb5d7-146">Detta returnerar framgång om OneDrive är klar att flyttas eller inte fungerar om det finns en laglig plats eller under webbplats som kan förhindra flytten.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-146">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move.</span></span> <span data-ttu-id="bb5d7-147">När du har verifierat att OneDrive är klar att flyttas kan du börja flytta.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-147">Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="bb5d7-148">Starta en OneDrive geo-flyttning</span><span class="sxs-lookup"><span data-stu-id="bb5d7-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="bb5d7-149">Starta flytten genom att köra:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="bb5d7-150">Med dessa parametrar:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-150">Using these parameters:</span></span>

-   <span data-ttu-id="bb5d7-151">_UserPrincipalName_ – UPN för den användare vars OneDrive flyttas.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="bb5d7-152">_DestinationDataLocation_ – Geo-plats dit OneDrive måste flyttas.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="bb5d7-153">Det ska vara samma som användarens förvalda plats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="bb5d7-154">Om du till exempel vill flytta OneDrive för matt@contosoenergy.onmicrosoft.com från EUR till Australien kör du:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Skärm bild av PowerShell-fönstret med start-SPOUserAndContentMove cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="bb5d7-156">Om du vill schemalägga en geo-flytt senare kan du använda en av följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="bb5d7-157">_PreferredMoveBeginDate_ – flytten kommer sannolikt att börja vid den här tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-157">_PreferredMoveBeginDate_ – The move will likely begin at this specified time.</span></span> <span data-ttu-id="bb5d7-158">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-158">Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="bb5d7-159">_PreferredMoveEndDate_ – flytten kommer sannolikt att genomföras efter den angivna tiden, på bästa möjliga sätt.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-159">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis.</span></span> <span data-ttu-id="bb5d7-160">Tid måste anges i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-160">Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="bb5d7-161">Avbryta en OneDrive geo-flyttning</span><span class="sxs-lookup"><span data-stu-id="bb5d7-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="bb5d7-162">Du kan stoppa geo-flytten för en användares OneDrive, förutsatt att flytten inte pågår eller slutförs med hjälp av cmdleten:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="bb5d7-163">Där _userPrincipalName_ är UPN för den användare vars OneDrive-flytt du vill stoppa.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="bb5d7-164">Aktuell status bestäms</span><span class="sxs-lookup"><span data-stu-id="bb5d7-164">Determining current status</span></span>

<span data-ttu-id="bb5d7-165">Du kan kontrol lera statusen för en OneDrive geo Move in eller ut ur den geo som du är ansluten till med hjälp av cmdleten Get-SPOUserAndContentMoveState.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="bb5d7-166">Flytt status beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb5d7-167"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="bb5d7-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="bb5d7-168"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="bb5d7-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="bb5d7-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="bb5d7-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="bb5d7-170">Flytten har inte påbörjats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bb5d7-171">Inaktivitet (<em>ej tillämpligt</em>)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="bb5d7-172">Flytten pågår i något av följande lägen: verifiering (1/4), säkerhets kopiering (2/4), återställning (3/4), rensning (4/4).</span><span class="sxs-lookup"><span data-stu-id="bb5d7-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bb5d7-173">Bra</span><span class="sxs-lookup"><span data-stu-id="bb5d7-173">Success</span></span></td>
<td align="left"><span data-ttu-id="bb5d7-174">Flyttningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bb5d7-175">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="bb5d7-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="bb5d7-176">Det gick inte att flytta.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bb5d7-177">Använd parametern UserPrincipalName för att hitta statusen för en viss användares flyttning:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="bb5d7-178">Om du vill hitta statusen för alla flyttningar i eller från den Geo-plats som du är ansluten till använder du parametern MoveState med något av följande värden: NotStarted, pågående, lyckades, misslyckades, alla.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="bb5d7-179">Du kan också lägga till `-Verbose` parametern för mer detaljerade beskrivningar av flytt läget.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="bb5d7-180">Användar upplevelse</span><span class="sxs-lookup"><span data-stu-id="bb5d7-180">User Experience</span></span>

<span data-ttu-id="bb5d7-181">Användare av OneDrive bör uppmärksammas i minimalt avbrott om deras OneDrive flyttas till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-181">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location.</span></span> <span data-ttu-id="bb5d7-182">Om du tar bort ett kort känsligt tillstånd under flytten fortsätter befintliga länkar och behörigheter att fungera som förväntat när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-182">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="bb5d7-183">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="bb5d7-183">OneDrive for Business</span></span>

<span data-ttu-id="bb5d7-184">När flytten pågår är användarens OneDrive skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="bb5d7-185">När flytten är klar dirigeras användaren till OneDrive på den nya geo-platsen när de navigerar till OneDrive-startprogrammet för Microsoft 365 eller en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="bb5d7-186">Behörigheter för OneDrive-innehåll</span><span class="sxs-lookup"><span data-stu-id="bb5d7-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="bb5d7-187">Användare med behörigheter till OneDrive-innehåll kommer att fortsätta att ha åtkomst till innehållet under flytten och när det är klart.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="bb5d7-188">OneDrive-synkroniseringsklient</span><span class="sxs-lookup"><span data-stu-id="bb5d7-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="bb5d7-189">OneDrive-synkroniseringsklienten kommer automatiskt att upptäcka och överföra synkronisering till den nya OneDrive-platsen när OneDrive geo-flyttningen är klar.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-189">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="bb5d7-190">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="bb5d7-191">(Version 17.3.6943.0625 eller senare krävs för synkroniseringsklient.)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-191">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="bb5d7-192">Om en användare uppdaterar en fil när en OneDrive geo-flyttning pågår meddelar synkroniseringsklienten dem att fil överföringar är väntande när flytten pågår.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="bb5d7-193">Dela länkar</span><span class="sxs-lookup"><span data-stu-id="bb5d7-193">Sharing links</span></span> 

<span data-ttu-id="bb5d7-194">När OneDrive geo-flytten är klar omdirigeras de befintliga delade länkarna för de filer som flyttas automatiskt till den nya geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="bb5d7-195">OneNote-upplevelse</span><span class="sxs-lookup"><span data-stu-id="bb5d7-195">OneNote Experience</span></span> 

<span data-ttu-id="bb5d7-196">I OneNote Win32-klient-och UWP (Universal) identifieras och sömlöst synkronisera antecknings böcker automatiskt när OneDrive geo-flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-196">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete.</span></span> <span data-ttu-id="bb5d7-197">Användaren behöver inte logga in igen eller vidta någon annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-197">The user does not need to sign-in again or take any other action.</span></span> <span data-ttu-id="bb5d7-198">Den enda synliga indikatorn för användaren är att synkronisering av bärbara datorer Miss lyckas när OneDrive geo-flytt pågår.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-198">The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress.</span></span> <span data-ttu-id="bb5d7-199">Den här funktionen finns i följande OneNote-klient versioner:</span><span class="sxs-lookup"><span data-stu-id="bb5d7-199">This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="bb5d7-200">OneNote Win32 – version 16.0.8326.2096 (och senare)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="bb5d7-201">OneNote UWP – version 16.0.8431.1006 (och senare)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="bb5d7-202">OneNote-mobilapp – version 16.0.8431.1011 (och senare)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="bb5d7-203">Teams-appen</span><span class="sxs-lookup"><span data-stu-id="bb5d7-203">Teams app</span></span>

<span data-ttu-id="bb5d7-204">När OneDrive geo-flytt är klar har användarna åtkomst till sina OneDrive-filer i Teams-appen.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-204">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app.</span></span> <span data-ttu-id="bb5d7-205">Dessutom fortsätter filer som delas via Teams chatt från sina OneDrive innan de geo-flytten fungerar när flytten är klar.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-205">Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="bb5d7-206">OneDrive för företag – mobilappen (iOS)</span><span class="sxs-lookup"><span data-stu-id="bb5d7-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="bb5d7-207">När OneDrive geo är klart måste användaren logga ut och logga in igen på iOS-mobilappen för att synkronisera med den nya OneDrive-platsen.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="bb5d7-208">Befintliga grupper och webbplatser som följs</span><span class="sxs-lookup"><span data-stu-id="bb5d7-208">Existing followed groups and sites</span></span>

<span data-ttu-id="bb5d7-209">Följda webbplatser och grupper visas i användarens OneDrive oavsett Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="bb5d7-210">Webbplatser och grupper som finns på en annan Geo-plats öppnas på en separat flik.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="bb5d7-211">Uppdateringar för Delve geo URL</span><span class="sxs-lookup"><span data-stu-id="bb5d7-211">Delve Geo URL updates</span></span>

<span data-ttu-id="bb5d7-212">Användare skickas till den Delve-geo som motsvarar sin PDL först efter det att OneDrive har flyttats till den nya geoen.</span><span class="sxs-lookup"><span data-stu-id="bb5d7-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
