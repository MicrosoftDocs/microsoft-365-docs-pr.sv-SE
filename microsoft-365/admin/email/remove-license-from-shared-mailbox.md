---
title: Ta bort licens från delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Ta bort licens från en delad postlåda för att tilldela den till en annan användare. '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915692"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="ce718-103">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ce718-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ce718-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="ce718-104">The admin center is changing.</span></span> <span data-ttu-id="ce718-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ce718-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ce718-106">Delade postlådor kräver vanligtvis inte en licens.</span><span class="sxs-lookup"><span data-stu-id="ce718-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="ce718-107">Följ de här anvisningarna om du vill ta bort en licens från en delad postlåda så att du kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.</span><span class="sxs-lookup"><span data-stu-id="ce718-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="ce718-108">En licens krävs i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="ce718-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="ce718-109">Den delade postlådan har mer än 50 GB lagringsutrymme som används.</span><span class="sxs-lookup"><span data-stu-id="ce718-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="ce718-110">Den delade postlådan använder arkivering på plats.</span><span class="sxs-lookup"><span data-stu-id="ce718-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="ce718-111">Den delade postlådan ligger i ett bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="ce718-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="ce718-112">Den delade postlådan har en tilldelad Microsoft Defender-licens.</span><span class="sxs-lookup"><span data-stu-id="ce718-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="ce718-113">Ta bort licensen</span><span class="sxs-lookup"><span data-stu-id="ce718-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ce718-114">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ce718-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ce718-115">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="ce718-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ce718-116">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="ce718-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="ce718-117">Välj den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ce718-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="ce718-118">På fliken **Licenser och appar** expanderar du **Licenser** och avmarkerar rutan för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ce718-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="ce718-119">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ce718-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="ce718-120">När du återgår till **sidan Aktiva** användare blir statusen för den delade postlådan **Ej licensierad.**</span><span class="sxs-lookup"><span data-stu-id="ce718-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ce718-121">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="ce718-121">You're still paying for the license.</span></span> <span data-ttu-id="ce718-122">Ta bort licensen från prenumerationen [om du vill sluta betala för den.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ce718-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ce718-123">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ce718-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce718-124">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="ce718-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ce718-125">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="ce718-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="ce718-126">Markera den delade postlådan och välj sedan **Redigera** bredvid **Produktlicenser.**</span><span class="sxs-lookup"><span data-stu-id="ce718-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="ce718-127">På sidan **Produktlicenser** ställer du in växlingsknappen på **Av** för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ce718-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="ce718-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce718-128">Select **Save**.</span></span>

5. <span data-ttu-id="ce718-129">När du återgår till **sidan Aktiva** användare blir statusen för den delade postlådan **Ej licensierad.**</span><span class="sxs-lookup"><span data-stu-id="ce718-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ce718-130">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="ce718-130">You're still paying for the license.</span></span> <span data-ttu-id="ce718-131">Ta bort licensen från prenumerationen [om du vill sluta betala för den.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ce718-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ce718-132">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ce718-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce718-133">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="ce718-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ce718-134">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="ce718-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="ce718-135">Markera den delade postlådan och välj sedan **Redigera** bredvid **Produktlicenser.**</span><span class="sxs-lookup"><span data-stu-id="ce718-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="ce718-136">På sidan **Produktlicenser** ställer du in växlingsknappen på **Av** för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ce718-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="ce718-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce718-137">Select **Save**.</span></span>

5. <span data-ttu-id="ce718-138">När du återgår till **sidan Aktiva** användare blir statusen för den delade postlådan **Ej licensierad.**</span><span class="sxs-lookup"><span data-stu-id="ce718-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ce718-139">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="ce718-139">You're still paying for the license.</span></span> <span data-ttu-id="ce718-140">Ta bort licensen från prenumerationen [om du vill sluta betala för den.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ce718-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="ce718-141">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ce718-141">Related articles</span></span>

[<span data-ttu-id="ce718-142">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ce718-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ce718-143">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ce718-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="ce718-144">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ce718-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="ce718-145">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ce718-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="ce718-146">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ce718-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)