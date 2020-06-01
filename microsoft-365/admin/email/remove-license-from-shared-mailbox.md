---
title: Ta bort licens från delad postlåda
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: 401b334efeccf6d7c4caca20be3cc9767b2df945
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432225"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="62910-103">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="62910-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="62910-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="62910-104">The admin center is changing.</span></span> <span data-ttu-id="62910-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="62910-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="62910-106">Delade postlådor kräver vanligtvis ingen licens.</span><span class="sxs-lookup"><span data-stu-id="62910-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="62910-107">Följ dessa instruktioner om du vill ta bort en licens från en delad postlåda så att du antingen kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.</span><span class="sxs-lookup"><span data-stu-id="62910-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="62910-108">En licens krävs i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="62910-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="62910-109">Den delade postlådan har mer än 50 GB lagringsutrymme som används.</span><span class="sxs-lookup"><span data-stu-id="62910-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="62910-110">Den delade postlådan använder arkivering på plats.</span><span class="sxs-lookup"><span data-stu-id="62910-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="62910-111">Den delade postlådan placeras i bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="62910-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="62910-112">Ta bort licensen</span><span class="sxs-lookup"><span data-stu-id="62910-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="62910-113">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="62910-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62910-114">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="62910-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="62910-115">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="62910-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="62910-116">Markera den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="62910-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="62910-117">En av fliken **Licenser och appar,** expandera **Licenser** och avmarkera rutan för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="62910-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="62910-118">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="62910-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="62910-119">När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="62910-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="62910-120">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="62910-120">You're still paying for the license.</span></span> <span data-ttu-id="62910-121">Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="62910-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="62910-122">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="62910-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62910-123">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="62910-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="62910-124">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="62910-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="62910-125">Markera den delade postlådan och välj sedan **Redigera bredvid** **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="62910-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="62910-126">En av sidan **Produktlicenser** anger du växlingsknappen till **Av** för den licens som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="62910-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="62910-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62910-127">Select **Save**.</span></span>

5. <span data-ttu-id="62910-128">När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="62910-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="62910-129">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="62910-129">You're still paying for the license.</span></span> <span data-ttu-id="62910-130">Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="62910-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="62910-131">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="62910-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62910-132">Du måste ta bort licensen från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="62910-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="62910-133">Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="62910-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="62910-134">Markera den delade postlådan och välj sedan **Redigera bredvid** **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="62910-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="62910-135">En av sidan **Produktlicenser** anger du växlingsknappen till **Av** för den licens som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="62910-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="62910-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62910-136">Select **Save**.</span></span>

5. <span data-ttu-id="62910-137">När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="62910-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="62910-138">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="62910-138">You're still paying for the license.</span></span> <span data-ttu-id="62910-139">Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="62910-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="62910-140">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="62910-140">Related articles</span></span>

[<span data-ttu-id="62910-141">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="62910-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="62910-142">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="62910-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="62910-143">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="62910-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="62910-144">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="62910-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="62910-145">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="62910-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
