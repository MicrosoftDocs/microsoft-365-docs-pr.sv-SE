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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2020
ms.locfileid: "52161569"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="373e4-104">Stäng, öppna och ta bort en eDiscovery-basfall</span><span class="sxs-lookup"><span data-stu-id="373e4-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="373e4-105">I den här artikeln beskrivs hur du stänger, öppnar och tar bort grundläggande eDiscovery-ärenden i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="373e4-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="373e4-106">Stänga ett ärende</span><span class="sxs-lookup"><span data-stu-id="373e4-106">Close a case</span></span>

<span data-ttu-id="373e4-107">När det juridiska ärende eller den undersökning som stöds av en bas-eDiscovery-ärende har slutförts kan du stänga ärendet.</span><span class="sxs-lookup"><span data-stu-id="373e4-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="373e4-108">Så här stänger du ett ärende:</span><span class="sxs-lookup"><span data-stu-id="373e4-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="373e4-109">Om ärendet innehåller platser för innehåll som är spärrade för e-dataidentifiering inaktiveras innehållet.</span><span class="sxs-lookup"><span data-stu-id="373e4-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="373e4-110">När vänttiden är inaktiverad tillämpas en respitperiod på 30 dagar (kallas för *fördröjning)* på platser som var i väntläge.</span><span class="sxs-lookup"><span data-stu-id="373e4-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="373e4-111">Det här förhindrar att innehåll tas bort omedelbart, och administratörer kan söka efter och återställa innehåll innan det tas bort permanent efter att undantaget fördröjts.</span><span class="sxs-lookup"><span data-stu-id="373e4-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="373e4-112">Mer information finns i Ta [bort innehållsplatser från en eDiscovery-plats.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="373e4-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="373e4-113">Om du stänger ett ärende inaktiveras bara det som är kopplat till det aktuella ärendet.</span><span class="sxs-lookup"><span data-stu-id="373e4-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="373e4-114">Om andra bevarande placeras på en plats för innehåll (t.ex. bevarande av juridiska skäl, en bevarandeprincip eller ett bevarande från ett annat bas-eDiscovery-ärende) kommer de kvarhållningen att bibehållas.</span><span class="sxs-lookup"><span data-stu-id="373e4-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="373e4-115">Ärendet är fortfarande listat på sidan Bas-eDiscovery i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="373e4-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="373e4-116">Informationen, som sätts i spärrade fall, sökningar och medlemmar i ett stängt ärende bevaras.</span><span class="sxs-lookup"><span data-stu-id="373e4-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="373e4-117">Du kan redigera ett ärende när det har stängts.</span><span class="sxs-lookup"><span data-stu-id="373e4-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="373e4-118">Du kan till exempel lägga till eller ta bort medlemmar, skapa sökningar och exportera sökresultat.</span><span class="sxs-lookup"><span data-stu-id="373e4-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="373e4-119">Den största skillnaden mellan aktiva och stängda ärenden är att eDiscovery-kvarhåller har inaktiverats när ett ärende stängs.</span><span class="sxs-lookup"><span data-stu-id="373e4-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="373e4-120">Så här stänger du ett ärende:</span><span class="sxs-lookup"><span data-stu-id="373e4-120">To close a case:</span></span>
  
1. <span data-ttu-id="373e4-121">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="373e4-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="373e4-122">Klicka på namnet på det ärende du vill stänga.</span><span class="sxs-lookup"><span data-stu-id="373e4-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="373e4-123">Den **utfällsida** för Hantera det här fallet visas.</span><span class="sxs-lookup"><span data-stu-id="373e4-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="373e4-124">Klicka **på Stäng ärende under** Hantera **ärendestatus.**</span><span class="sxs-lookup"><span data-stu-id="373e4-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="373e4-125">En varning visas om att det som är kopplat till ärendet har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="373e4-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="373e4-126">Stäng **ärendet genom** att klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="373e4-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="373e4-127">Statusen på sidan **Hantera det här ärendet** ändras från **Aktiv** till **Avslutande.**</span><span class="sxs-lookup"><span data-stu-id="373e4-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="373e4-128">Stäng sidan **Hantera detta** ärende.</span><span class="sxs-lookup"><span data-stu-id="373e4-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="373e4-129">På sidan **Bas-eDiscovery** klickar du på **Uppdatera** för att uppdatera statusen för det stängda ärendet.</span><span class="sxs-lookup"><span data-stu-id="373e4-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="373e4-130">Det kan ta upp till 60 minuter innan avslutsprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="373e4-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="373e4-131">När processen är klar ändras statusen för ärendet till **Stängd på** sidan **Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="373e4-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="373e4-132">Klicka på namnet på ärendet  igen så att sidan Hantera det här ärendet visas, som innehåller information om när ärendet stängdes och vem som stängde det.</span><span class="sxs-lookup"><span data-stu-id="373e4-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="373e4-133">Öppna ett stängt ärende igen</span><span class="sxs-lookup"><span data-stu-id="373e4-133">Reopen a closed case</span></span>

<span data-ttu-id="373e4-134">När du öppnar ett ärende på nytt återställs inte eventuella eDiscovery-kvarhåller som fanns när ärendet stängdes.</span><span class="sxs-lookup"><span data-stu-id="373e4-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="373e4-135">När ärendet har öppnats på nytt måste du gå till sidan **med spärrade** sidor och aktivera tidigare insidor.</span><span class="sxs-lookup"><span data-stu-id="373e4-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="373e4-136">Om du vill aktivera ett väntande objekt markerar du det så att den utfäll sida visas och ställer sedan in **statusreglaget** på **På**.</span><span class="sxs-lookup"><span data-stu-id="373e4-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="373e4-137">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="373e4-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="373e4-138">Klicka på namnet på det ärende som du vill öppna igen.</span><span class="sxs-lookup"><span data-stu-id="373e4-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="373e4-139">Den **utfällsida** för Hantera det här fallet visas.</span><span class="sxs-lookup"><span data-stu-id="373e4-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="373e4-140">Klicka **på Öppna ärendet igen** under Hantera **ärendestatus.**</span><span class="sxs-lookup"><span data-stu-id="373e4-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="373e4-141">En varning visas om att det som var kopplat till ärendet när det stängdes inte aktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="373e4-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="373e4-142">Klicka **på Ja** om du vill öppna ärendet igen.</span><span class="sxs-lookup"><span data-stu-id="373e4-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="373e4-143">Statusen på sidan **Hantera det här ärendet** ändras från Stängd **till** **Aktiv.**</span><span class="sxs-lookup"><span data-stu-id="373e4-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="373e4-144">Stäng sidan **Hantera detta** ärende.</span><span class="sxs-lookup"><span data-stu-id="373e4-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="373e4-145">På sidan **Bas-eDiscovery** klickar du på **Uppdatera för** att uppdatera statusen för det öppnade ärendet.</span><span class="sxs-lookup"><span data-stu-id="373e4-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="373e4-146">Det kan ta upp till 60 minuter innan återöppnandeprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="373e4-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="373e4-147">När processen är klar ändras statusen för ärendet till **Aktiv** på sidan **Bas-eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="373e4-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="373e4-148">Ta bort ett ärende</span><span class="sxs-lookup"><span data-stu-id="373e4-148">Delete a case</span></span>

<span data-ttu-id="373e4-149">Du kan också ta bort aktiva och stängda Core eDiscovery-ärenden.</span><span class="sxs-lookup"><span data-stu-id="373e4-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="373e4-150">När du tar bort ett ärende tas alla sökningar och exporter i ärendet bort och ärendet tas bort från listan över ärenden på sidan **Core eDiscovery** i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="373e4-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="373e4-151">Du kan inte öppna ett borttagna ärende igen.</span><span class="sxs-lookup"><span data-stu-id="373e4-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="373e4-152">Innan du kan ta bort ett ärende (oavsett om det är aktivt eller stängt) måste du först ta bort *alla* eDiscovery-objekt som är kopplade till ärendet.</span><span class="sxs-lookup"><span data-stu-id="373e4-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="373e4-153">Det omfattar borttagning av filer som har statusen **Av.**</span><span class="sxs-lookup"><span data-stu-id="373e4-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="373e4-154">Så här tar du bort en e-dataidentifierings hold:</span><span class="sxs-lookup"><span data-stu-id="373e4-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="373e4-155">Gå till **fliken** Spärrar för det ärende som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="373e4-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="373e4-156">Klicka på det håll du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="373e4-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="373e4-157">Klicka på Ta bort håll på den **utfällade sidan.**</span><span class="sxs-lookup"><span data-stu-id="373e4-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="373e4-158">Så här tar du bort ett ärende:</span><span class="sxs-lookup"><span data-stu-id="373e4-158">To delete a case:</span></span>

1. <span data-ttu-id="373e4-159">I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="373e4-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="373e4-160">Klicka på namnet på det ärende du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="373e4-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="373e4-161">Klicka **på Ta bort ärende** under Hantera ärendestatus på den **utfällällade sidan.**</span><span class="sxs-lookup"><span data-stu-id="373e4-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="373e4-162">Om det ärende som du försöker ta bort fortfarande innehåller eDiscovery-innehåll får du ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="373e4-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="373e4-163">Du måste ta bort alla fodral som är kopplade till ärendet och sedan försöka ta bort ärendet igen.</span><span class="sxs-lookup"><span data-stu-id="373e4-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
