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
description: 'Ta bort licensen från en delad post låda för att tilldela den till en annan användare. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698309"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="3818e-103">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="3818e-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3818e-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="3818e-104">The admin center is changing.</span></span> <span data-ttu-id="3818e-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3818e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="3818e-106">Delade post lådor kräver normalt ingen licens.</span><span class="sxs-lookup"><span data-stu-id="3818e-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="3818e-107">Följ de här anvisningarna om du vill ta bort en licens från en delad post låda så att du kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.</span><span class="sxs-lookup"><span data-stu-id="3818e-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="3818e-108">En licens krävs i följande fall:</span><span class="sxs-lookup"><span data-stu-id="3818e-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="3818e-109">Den delade post lådan har mer än 50 GB lagrings utrymme.</span><span class="sxs-lookup"><span data-stu-id="3818e-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="3818e-110">Den delade post lådan använder arkivering på plats.</span><span class="sxs-lookup"><span data-stu-id="3818e-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="3818e-111">Den delade post lådan placeras i en tvist.</span><span class="sxs-lookup"><span data-stu-id="3818e-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="3818e-112">Den delade post lådan har en Microsoft Defender-licens tilldelad.</span><span class="sxs-lookup"><span data-stu-id="3818e-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="3818e-113">Ta bort licensen</span><span class="sxs-lookup"><span data-stu-id="3818e-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3818e-114">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="3818e-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3818e-115">Du måste ta bort licensen från sidan aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="3818e-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3818e-116">Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar.</span><span class="sxs-lookup"><span data-stu-id="3818e-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="3818e-117">Välj den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="3818e-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="3818e-118">Fliken **licenser och appar** , expandera **licenser** och avmarkera kryss rutan för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="3818e-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="3818e-119">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="3818e-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="3818e-120">När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="3818e-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3818e-121">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="3818e-121">You're still paying for the license.</span></span> <span data-ttu-id="3818e-122">Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3818e-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3818e-123">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="3818e-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3818e-124">Du måste ta bort licensen från sidan aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="3818e-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3818e-125">Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar.</span><span class="sxs-lookup"><span data-stu-id="3818e-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3818e-126">Välj den delade post lådan och välj sedan **redigera** bredvid **produkt licenser**.</span><span class="sxs-lookup"><span data-stu-id="3818e-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3818e-127">Sidan **produkt licenser** väljer du växling till **av** för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="3818e-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3818e-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3818e-128">Select **Save**.</span></span>

5. <span data-ttu-id="3818e-129">När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="3818e-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3818e-130">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="3818e-130">You're still paying for the license.</span></span> <span data-ttu-id="3818e-131">Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3818e-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3818e-132">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="3818e-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3818e-133">Du måste ta bort licensen från sidan aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="3818e-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3818e-134">Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar.</span><span class="sxs-lookup"><span data-stu-id="3818e-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3818e-135">Välj den delade post lådan och välj sedan **redigera** bredvid **produkt licenser**.</span><span class="sxs-lookup"><span data-stu-id="3818e-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3818e-136">Sidan **produkt licenser** väljer du växling till **av** för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="3818e-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3818e-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3818e-137">Select **Save**.</span></span>

5. <span data-ttu-id="3818e-138">När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.</span><span class="sxs-lookup"><span data-stu-id="3818e-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3818e-139">Du betalar fortfarande för licensen.</span><span class="sxs-lookup"><span data-stu-id="3818e-139">You're still paying for the license.</span></span> <span data-ttu-id="3818e-140">Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3818e-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="3818e-141">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="3818e-141">Related articles</span></span>

[<span data-ttu-id="3818e-142">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="3818e-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3818e-143">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="3818e-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3818e-144">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="3818e-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3818e-145">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="3818e-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="3818e-146">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="3818e-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
