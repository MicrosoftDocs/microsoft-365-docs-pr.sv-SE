---
title: Stäng, öppna och ta bort core eDiscovery-ärenden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du hanterar grundläggande eDiscovery-ärenden. Det handlar bland annat om att stänga ett ärende, öppna ett stängt ärende och ta bort ett ärende.
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532452"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="6c42b-104">Stäng, öppna och ta bort en eDiscovery-basfall</span><span class="sxs-lookup"><span data-stu-id="6c42b-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="6c42b-105">I den här artikeln beskrivs hur du stänger, öppnar och tar bort grundläggande eDiscovery-ärenden i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c42b-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="6c42b-106">Stänga ett ärende</span><span class="sxs-lookup"><span data-stu-id="6c42b-106">Close a case</span></span>

<span data-ttu-id="6c42b-107">När det juridiska ärende eller den undersökning som stöds av en bas-eDiscovery-ärende har slutförts kan du stänga ärendet.</span><span class="sxs-lookup"><span data-stu-id="6c42b-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="6c42b-108">Så här stänger du ett ärende:</span><span class="sxs-lookup"><span data-stu-id="6c42b-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="6c42b-109">Om ärendet innehåller eDiscovery-innehåll kommer det att inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="6c42b-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="6c42b-110">När vänttiden är inaktiverad tillämpas en respitperiod på 30 dagar (kallas för *fördröjning)* på platser som var i väntläge.</span><span class="sxs-lookup"><span data-stu-id="6c42b-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="6c42b-111">Det här förhindrar att innehåll tas bort omedelbart, och administratörer kan söka efter och återställa innehåll innan det tas bort permanent efter att undantaget fördröjts.</span><span class="sxs-lookup"><span data-stu-id="6c42b-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="6c42b-112">Mer information finns i Ta [bort innehållsplatser från en eDiscovery-plats.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="6c42b-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="6c42b-113">Om du stänger ett ärende inaktiveras bara det som är kopplat till det aktuella ärendet.</span><span class="sxs-lookup"><span data-stu-id="6c42b-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="6c42b-114">Om andra bevarande placeras på en plats för innehåll (t.ex. bevarande av juridiska skäl, en bevarandeprincip eller ett bevarande från ett annat bas-eDiscovery-ärende) kommer de kvarhållningen att bibehållas.</span><span class="sxs-lookup"><span data-stu-id="6c42b-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="6c42b-115">Ärendet är fortfarande listat på sidan Bas-eDiscovery i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="6c42b-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6c42b-116">Informationen, som sätts i spärrade fall, sökningar och medlemmar i ett stängt ärende bevaras.</span><span class="sxs-lookup"><span data-stu-id="6c42b-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="6c42b-117">Du kan redigera ett ärende när det har stängts.</span><span class="sxs-lookup"><span data-stu-id="6c42b-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="6c42b-118">Du kan till exempel lägga till eller ta bort medlemmar, skapa sökningar och exportera sökresultat.</span><span class="sxs-lookup"><span data-stu-id="6c42b-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="6c42b-119">Den största skillnaden mellan aktiva och stängda ärenden är att eDiscovery-kvarhåller har inaktiverats när ett ärende stängs.</span><span class="sxs-lookup"><span data-stu-id="6c42b-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="6c42b-120">Så här stänger du ett ärende:</span><span class="sxs-lookup"><span data-stu-id="6c42b-120">To close a case:</span></span>
  
1. <span data-ttu-id="6c42b-121">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6c42b-122">Klicka på namnet på det ärende du vill stänga.</span><span class="sxs-lookup"><span data-stu-id="6c42b-122">Click the name of the case that you want to close.</span></span>

   ![Stänga ärende på startsidan för ärende](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="6c42b-124">Klicka på Stäng ärende under **Status** på **startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="6c42b-125">En varning visas om att det som är kopplat till ärendet har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="6c42b-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="6c42b-126">Stäng **ärendet genom** att klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="6c42b-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="6c42b-127">Statusen på ärendehemsidan ändras från **Aktiv till** **Avslutande.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="6c42b-128">På sidan **Bas-eDiscovery** klickar du på **Uppdatera** för att uppdatera statusen för det stängda ärendet.</span><span class="sxs-lookup"><span data-stu-id="6c42b-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="6c42b-129">Det kan ta upp till 60 minuter innan avslutsprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="6c42b-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="6c42b-130">När processen är klar ändras statusen för ärendet till **Stängd på** sidan **Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="6c42b-131">Öppna ett stängt ärende igen</span><span class="sxs-lookup"><span data-stu-id="6c42b-131">Reopen a closed case</span></span>

<span data-ttu-id="6c42b-132">När du öppnar ett ärende på nytt återställs inte eventuella eDiscovery-kvarhåller som fanns när ärendet stängdes.</span><span class="sxs-lookup"><span data-stu-id="6c42b-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="6c42b-133">När ärendet har öppnats på nytt måste du gå till sidan **med spärrade** sidor och aktivera tidigare insidor.</span><span class="sxs-lookup"><span data-stu-id="6c42b-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="6c42b-134">Om du vill aktivera ett väntande objekt markerar du det så att den utfäll sida visas och ställer sedan in **statusreglaget** på **På**.</span><span class="sxs-lookup"><span data-stu-id="6c42b-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="6c42b-135">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6c42b-136">Klicka på namnet på det ärende som du vill öppna igen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-136">Click the name of the case that you want to reopen.</span></span>

   ![Öppna ett stängt ärende igen](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="6c42b-138">Klicka på Öppna ärende igen under **Status** **på startsidan.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="6c42b-139">En varning visas om att det som var kopplat till ärendet när det stängdes inte aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6c42b-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="6c42b-140">Klicka **på Ja** om du vill öppna ärendet igen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="6c42b-141">Statusen på startsidans utfäll sida för ärende ändras från **Stängd** till **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="6c42b-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="6c42b-142">På sidan **Bas-eDiscovery** klickar du på **Uppdatera för** att uppdatera statusen för det öppnade ärendet.</span><span class="sxs-lookup"><span data-stu-id="6c42b-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="6c42b-143">Det kan ta upp till 60 minuter innan återöppnandeprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="6c42b-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="6c42b-144">När processen är klar ändras statusen för ärendet till **Aktiv** på sidan **Bas-eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="6c42b-145">(Valfritt) Om du vill aktivera eventuella spärrade objekt  kopplade till det öppnade ärendet går du till fliken Spärrar, markerar ett ärende och markerar kryssrutan under **Status** på den utfällbordssidan för håll.</span><span class="sxs-lookup"><span data-stu-id="6c42b-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="6c42b-146">Ta bort ett ärende</span><span class="sxs-lookup"><span data-stu-id="6c42b-146">Delete a case</span></span>

<span data-ttu-id="6c42b-147">Du kan också ta bort aktiva och stängda Core eDiscovery-ärenden.</span><span class="sxs-lookup"><span data-stu-id="6c42b-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="6c42b-148">När du tar bort ett ärende tas alla sökningar och exporter i ärendet bort och ärendet tas bort från listan över ärenden på sidan **Core eDiscovery** i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="6c42b-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6c42b-149">Du kan inte öppna ett borttagna ärende igen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="6c42b-150">Innan du kan ta bort ett ärende (oavsett om det är aktivt eller stängt) måste du först ta bort *alla* eDiscovery-objekt som är kopplade till ärendet.</span><span class="sxs-lookup"><span data-stu-id="6c42b-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="6c42b-151">Det omfattar borttagning av filer som har statusen **Av.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="6c42b-152">Så här tar du bort en e-dataidentifierings hold:</span><span class="sxs-lookup"><span data-stu-id="6c42b-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="6c42b-153">Gå till **fliken** Spärrar för det ärende som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="6c42b-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="6c42b-154">Markera det håll du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="6c42b-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="6c42b-155">Klicka på Ta bort på den utfällade **sidan.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-155">On the flyout page, click **Delete**.</span></span>

      ![Ta bort ett eDiscovery-håll](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="6c42b-157">Så här tar du bort ett ärende:</span><span class="sxs-lookup"><span data-stu-id="6c42b-157">To delete a case:</span></span>

1. <span data-ttu-id="6c42b-158">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6c42b-159">Klicka på namnet på det ärende du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="6c42b-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="6c42b-160">Klicka på Ta bort ärende under **Status** på **startsidan för ärendet.**</span><span class="sxs-lookup"><span data-stu-id="6c42b-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Ta bort ett ärende](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="6c42b-162">Om det ärende som du försöker ta bort fortfarande innehåller eDiscovery-innehåll får du ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="6c42b-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="6c42b-163">Du måste ta bort alla fodral som är kopplade till ärendet och sedan försöka ta bort ärendet igen.</span><span class="sxs-lookup"><span data-stu-id="6c42b-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
