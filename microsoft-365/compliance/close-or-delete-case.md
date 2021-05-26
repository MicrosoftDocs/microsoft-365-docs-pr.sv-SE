---
title: Stänga eller ta bort ett ärende
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Ta reda på vad som händer när en undersökning eller ett juridiskt ärende som stöds Advanced eDiscovery ett ärende stängs eller tas bort.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657657"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="0f654-103">Stänga eller ta bort ett Advanced eDiscovery ärende</span><span class="sxs-lookup"><span data-stu-id="0f654-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="0f654-104">Om det juridiska ärende eller den juridiska undersökningen som stöds Advanced eDiscovery slutföras kan du stänga eller ta bort ett ärende.</span><span class="sxs-lookup"><span data-stu-id="0f654-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="0f654-105">Du kan också öppna ett stängt ärende igen.</span><span class="sxs-lookup"><span data-stu-id="0f654-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="0f654-106">Stänga ett ärende</span><span class="sxs-lookup"><span data-stu-id="0f654-106">Close a case</span></span>

<span data-ttu-id="0f654-107">Följande händer när du stänger ett Advanced eDiscovery ärende:</span><span class="sxs-lookup"><span data-stu-id="0f654-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="0f654-108">Om ärendet innehåller platser där innehåll är spärrat inaktiveras de.</span><span class="sxs-lookup"><span data-stu-id="0f654-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="0f654-109">När vänttiden är inaktiverad tillämpas en respitperiod på 30 dagar (kallas för *fördröjning)* på platser som var i väntläge.</span><span class="sxs-lookup"><span data-stu-id="0f654-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="0f654-110">Det här förhindrar att innehåll tas bort omedelbart, och administratörer kan söka efter eller återställa innehåll som tas bort permanent efter att fördröjningsperioden förfaller.</span><span class="sxs-lookup"><span data-stu-id="0f654-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="0f654-111">Mer information finns i Ta [bort innehållsplatser från en eDiscovery-plats.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="0f654-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="0f654-112">Om du stänger ett ärende inaktiveras bara det som är kopplat till det aktuella ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f654-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="0f654-113">Om andra innehåll sätts på en plats (t.ex. bevarande av juridiska skäl, bevarande av bas för eDiscovery eller ett bevarande från ett annat Advanced eDiscovery ärende) kommer de innehållna innehållet fortfarande att bibehållas.</span><span class="sxs-lookup"><span data-stu-id="0f654-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="0f654-114">Ärendet är fortfarande listat på sidan eDiscovery i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="0f654-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0f654-115">Informationen, som sätts i spärrade fall, sökningar och medlemmar i ett stängt ärende bevaras.</span><span class="sxs-lookup"><span data-stu-id="0f654-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="0f654-116">Du kan redigera ett ärende när det har stängts.</span><span class="sxs-lookup"><span data-stu-id="0f654-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="0f654-117">Du kan till exempel lägga till eller ta bort medlemmar, skapa sökningar, exportera sökresultat och förbereda sökresultat för analys i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0f654-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="0f654-118">Den största skillnaden mellan aktiva och stängda ärenden är att kvarstad är inaktiverad när ett ärende stängs.</span><span class="sxs-lookup"><span data-stu-id="0f654-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="0f654-119">Så här stänger du ett ärende:</span><span class="sxs-lookup"><span data-stu-id="0f654-119">To close a case:</span></span>

1. <span data-ttu-id="0f654-120">På **Advanced eDiscovery** sidan väljer du det ärende du vill stänga.</span><span class="sxs-lookup"><span data-stu-id="0f654-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="0f654-121">På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="0f654-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0f654-122">Längst ned på den **utfällade sidan** Ärendeinformation klickar du på (**...**) **Fler alternativ**, och klicka sedan på **Stäng ärende**.</span><span class="sxs-lookup"><span data-stu-id="0f654-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Alternativ på menyn Fler alternativ för att stänga ett Advanced eDiscovery ärende](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="0f654-124">Det kan ta upp till 60 minuter innan avslutsprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="0f654-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="0f654-125">Öppna ett stängt ärende igen</span><span class="sxs-lookup"><span data-stu-id="0f654-125">Reopen a closed case</span></span>

<span data-ttu-id="0f654-126">När du öppnar Advanced eDiscovery återöppnar ett ärende kommer eventuella kvarhåller som fanns när ärendet stängdes inte att återställas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0f654-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="0f654-127">När ärendet har öppnats på nytt måste du gå till fliken **Spärrar** och aktivera tidigare kvartr.</span><span class="sxs-lookup"><span data-stu-id="0f654-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="0f654-128">Om du vill aktivera ett väntande objekt markerar du det så att den utfäll sida visas och ställer sedan in **statusreglaget** på **På**.</span><span class="sxs-lookup"><span data-stu-id="0f654-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="0f654-129">Så här öppnar du ett stängt ärende:</span><span class="sxs-lookup"><span data-stu-id="0f654-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="0f654-130">På **Advanced eDiscovery** väljer du det ärende som du vill öppna igen.</span><span class="sxs-lookup"><span data-stu-id="0f654-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="0f654-131">På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="0f654-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0f654-132">Längst ned på den **utfällade sidan** Ärendeinformation klickar du på (**...**) **Fler alternativ** och klicka sedan på **Öppna ärendet igen.**</span><span class="sxs-lookup"><span data-stu-id="0f654-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Alternativ i menyn Fler alternativ för att öppna ett Advanced eDiscovery ärende](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="0f654-134">Det kan ta upp till 60 minuter innan återöppnandeprocessen slutförs.</span><span class="sxs-lookup"><span data-stu-id="0f654-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="0f654-135">Ta bort ett ärende</span><span class="sxs-lookup"><span data-stu-id="0f654-135">Delete a case</span></span>

<span data-ttu-id="0f654-136">Du kan ta bort både aktiva och stängda Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="0f654-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="0f654-137">När du tar bort ett ärende tas alla komponenter som är associerade med ärendet bort, till exempel listan över biblioteksarier, kommunikationer, sökningar, granskningsuppsättningar och exportjobb.</span><span class="sxs-lookup"><span data-stu-id="0f654-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="0f654-138">Ärendet tas bort från listan över ärenden på sidan **Advanced eDiscovery** i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="0f654-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0f654-139">Du kan inte återskapa eller öppna ett borttagna ärende.</span><span class="sxs-lookup"><span data-stu-id="0f654-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="0f654-140">Vid data spill är det enda sättet att ta bort objekt i en granskningsuppsättning att ta bort det Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="0f654-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="0f654-141">Andra "söknings- och rensningsmetoder" tar inte bort objekt från en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="0f654-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="0f654-142">Innan du kan ta bort ett ärende (oavsett om det är aktivt eller stängt) måste du först ta bort *allt* som är kopplat till ärendet.</span><span class="sxs-lookup"><span data-stu-id="0f654-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="0f654-143">Det omfattar borttagning av filer som har statusen **Av.**</span><span class="sxs-lookup"><span data-stu-id="0f654-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="0f654-144">Så här tar du bort spärrade objekt som är kopplade till ett ärende:</span><span class="sxs-lookup"><span data-stu-id="0f654-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="0f654-145">Gå till **fliken** Spärrar i det Advanced eDiscovery ärende som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0f654-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="0f654-146">Klicka på det håll du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0f654-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="0f654-147">Klicka på Ta bort håll på den **utfällade sidan.**</span><span class="sxs-lookup"><span data-stu-id="0f654-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="0f654-148">Så här tar du bort ett ärende:</span><span class="sxs-lookup"><span data-stu-id="0f654-148">To delete a case:</span></span>

1. <span data-ttu-id="0f654-149">På **Advanced eDiscovery** väljer du det ärende du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0f654-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="0f654-150">På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="0f654-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0f654-151">Längst ned på den **utfällade sidan** Ärendeinformation klickar du på (**...**) **Fler alternativ och** klicka sedan på Ta **bort ärende.**</span><span class="sxs-lookup"><span data-stu-id="0f654-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Alternativ på menyn Fler alternativ för att ta bort ett Advanced eDiscovery ärende](..\Media\DeleteAdvancedeDiscoveryCase.png)
