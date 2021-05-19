---
title: Felsöka eDiscovery-undantag
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Felsöka fel relaterade till juridiska fel som tillämpas på systemer och icke-godtyckliga datakällor i Core eDiscovery.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538477"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="d2c0b-103">Felsöka eDiscovery-undantag</span><span class="sxs-lookup"><span data-stu-id="d2c0b-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="d2c0b-104">I den här artikeln beskrivs vanliga problem som kan uppstå med eDiscovery-kvarhåller och hur du löser dem.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="d2c0b-105">Artikeln innehåller även rekommenderade metoder för att hjälpa dig att minimera eller undvika dessa problem.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="d2c0b-106">Rekommenderade metoder</span><span class="sxs-lookup"><span data-stu-id="d2c0b-106">Recommended practices</span></span>

<span data-ttu-id="d2c0b-107">För att minska antalet fel som rör eDiscovery-rymmer rekommenderar vi följande tillvägagångssätt:</span><span class="sxs-lookup"><span data-stu-id="d2c0b-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="d2c0b-108">Om det fortfarande finns en väntande distribution, med statusen eller , väntar du tills kvarstående fördelning är klar `On (Pending)` innan du gör ytterligare `Off (Pending)` uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="d2c0b-109">Kontrollera om en princip för väntande avsöker innan du gör ytterligare uppdateringar av principen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="d2c0b-110">Kör följande kommandon eller spara dem i ett PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="d2c0b-111">Sammanfoga dina uppdateringar till ett eDiscovery-lager i en enda massbegäran i stället för att uppdatera principen för att behålla flera gånger för varje transaktion.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="d2c0b-112">Om du till exempel vill lägga till flera användarpostlådor i en befintlig blockeringsprincip med hjälp av cmdleten [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) kör du kommandot (eller lägger till som ett kodblock i ett skript) så att det bara körs en gång för att lägga till flera användare.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="d2c0b-113">**Rätt**</span><span class="sxs-lookup"><span data-stu-id="d2c0b-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="d2c0b-114">**Fel**</span><span class="sxs-lookup"><span data-stu-id="d2c0b-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="d2c0b-115">I det föregående felaktiga exemplet kör cmdleten fem separata gånger för att slutföra aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="d2c0b-116">Mer information om rekommenderade metoder för att lägga till användare i en princip för att lagra finns i [avsnittet Mer information.](#more-information)</span><span class="sxs-lookup"><span data-stu-id="d2c0b-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="d2c0b-117">Innan du kontaktar Microsoft Support om problem med eDiscovery-spärrade eDiscovery följer du stegen i avsnittet [Fel/problem:](#errorissue-holds-dont-sync) Innehåller inte synkroniseras för att försöka att spärra distributionen igen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="d2c0b-118">Den här processen löser ofta tillfälliga problem, inklusive interna serverfel.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="d2c0b-119">Fel/problem: Det går inte att synkronisera spärrar</span><span class="sxs-lookup"><span data-stu-id="d2c0b-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="d2c0b-120">Om du ser något av följande felmeddelanden när du försätter källinformation och datakällor i förvaring kan du använda lösningsstegen för att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="d2c0b-121">Resurser: Det tar längre tid än förväntat att distribuera principen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="d2c0b-122">Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så kom tillbaka om några timmar.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="d2c0b-123">Principen kan inte distribueras till innehållskällan på grund av ett tillfälligt problem Office 365 datacentret.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="d2c0b-124">Den aktuella principen tillämpas inte på något innehåll i källan, så det påverkar inte den blockerade distributionen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="d2c0b-125">Prova att distribuera principen på nytt för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="d2c0b-126">Det gick tyvärr inte att utföra de begärda ändringarna av principen på grund av ett tillfälligt internt serverfel.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="d2c0b-127">Försök igen om 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="d2c0b-128">Lösning</span><span class="sxs-lookup"><span data-stu-id="d2c0b-128">Resolution</span></span>

1. <span data-ttu-id="d2c0b-129">Anslut [säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör följande kommando för ett eDiscovery-skal:</span><span class="sxs-lookup"><span data-stu-id="d2c0b-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="d2c0b-130">Undersök värdet i *parametern Fördelningsdetaljer.*</span><span class="sxs-lookup"><span data-stu-id="d2c0b-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="d2c0b-131">Leta efter fel som följande:</span><span class="sxs-lookup"><span data-stu-id="d2c0b-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="d2c0b-132">Fel: Resurser: Det tar längre tid än förväntat att distribuera principen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="d2c0b-133">Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så kom tillbaka om några timmar.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="d2c0b-134">Prova att köra **kommandot Set-CaseHoldPolicy -RetryDistribution** för principen för väntande trafik. till exempel:</span><span class="sxs-lookup"><span data-stu-id="d2c0b-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="d2c0b-135">Fel: SharePoint är skrivskyddade eller inte åtkomliga</span><span class="sxs-lookup"><span data-stu-id="d2c0b-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="d2c0b-136">Om du ser följande felmeddelande när du spärrar användare och datakällor innebär det att organisationens globala administratör eller [SharePoint-administratör](/sharepoint/sharepoint-admin-role) har låst webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="d2c0b-137">En låst webbplats blockerar eDiscovery från att placera ett område på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="d2c0b-138">Webbplatsen SharePoint skrivskyddade eller inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="d2c0b-139">Kontakta webbplatsadministratören om du vill göra webbplatsen skrivbar och distribuera sedan principen igen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="d2c0b-140">Lösning</span><span class="sxs-lookup"><span data-stu-id="d2c0b-140">Resolution</span></span>

<span data-ttu-id="d2c0b-141">Lås upp webbplatsen (eller be en administratör låsa upp den) för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="d2c0b-142">Mer information om hur du ändrar låsläge för en webbplats finns i Låsa [och låsa upp webbplatser.](/sharepoint/manage-lock-status)</span><span class="sxs-lookup"><span data-stu-id="d2c0b-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="d2c0b-143">Fel: Postlådan eller SharePoint kanske inte finns</span><span class="sxs-lookup"><span data-stu-id="d2c0b-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="d2c0b-144">Om du ser följande felmeddelande när de förs in i ett bibliotek och datakällor i förvaring använder du lösningsstegen för att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="d2c0b-145">Postlådan eller SharePoint kanske inte finns.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="d2c0b-146">Kontakta Microsoft Support om detta är felaktigt.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="d2c0b-147">Annars ber vi dig ta bort den från policyn.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="d2c0b-148">Lösning</span><span class="sxs-lookup"><span data-stu-id="d2c0b-148">Resolution</span></span>

- <span data-ttu-id="d2c0b-149">Kör [Get-Mailbox](/powershell/module/exchange/get-mailbox) i Exchange Online PowerShell för att kontrollera om användarpostlådan finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="d2c0b-150">Kör [cmdlet:en Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) i SharePoint PowerShell för att kontrollera om webbplatsen finns i din organisation.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="d2c0b-151">Kontrollera om webbplatsens URL har ändrats.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="d2c0b-152">Mer information</span><span class="sxs-lookup"><span data-stu-id="d2c0b-152">More information</span></span>

<span data-ttu-id="d2c0b-153">I avsnittet Rekommenderade metoder (Rekommenderade metoder) för flera användare får du information om att systemet blockerar samtidiga uppdateringar av en princip för spärrade konton.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="d2c0b-154">Det innebär att när en uppdaterad princip för innehåll är tillämpad på nya innehållsplatser och principen för kvarstående innehåll är väntande, kan inte ytterligare innehållsplatser läggas till i principen för kvarstående innehåll.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="d2c0b-155">Här är några saker att tänka på för att hjälpa dig att minimera problemet:</span><span class="sxs-lookup"><span data-stu-id="d2c0b-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="d2c0b-156">Varje gång ett väntande tillstånd uppdateras hamnar det omedelbart i ett väntande tillstånd.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="d2c0b-157">Status för väntande tillstånd innebär att vänteläget tillämpas på innehållsplatser.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="d2c0b-158">Om du har ett skript som kör en slinga och lägger till platser för principen en och en (liknande det felaktiga exemplet som visas i avsnittet Rekommenderade metoder) initierar den första innehållsplatsen (till exempel en användarpostlåda) synkroniseringsprocessen som utlöser den väntande statusen.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="d2c0b-159">Det innebär att andra användare som läggs till i principen i efterföljande loopar resulterar i ett fel.</span><span class="sxs-lookup"><span data-stu-id="d2c0b-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="d2c0b-160">Om organisationen använder ett skript som kör en slinga för att uppdatera innehållsplatser för en princip för körning måste du uppdatera skriptet så att det uppdaterar platser i en enda massåtgärd (som i rätt exempel i avsnittet Rekommenderade metoder).</span><span class="sxs-lookup"><span data-stu-id="d2c0b-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
