---
title: Flytta användare till en annan prenumeration
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Lär dig hur du flyttar användare mellan abonnemang.
ms.date: 07/01/2020
ms.openlocfilehash: 79f3e4636ff047c4d6f27d83e3644913a8fbb0b5
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647801"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="b441b-103">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="b441b-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b441b-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="b441b-104">The admin center is changing.</span></span> <span data-ttu-id="b441b-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b441b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b441b-106">Om du har fler än en prenumeration, har du användare med en licens för ett abonnemang, men vill flytta dem till ett annat abonnemang, kan du ersätta den befintliga licensen med en annan.</span><span class="sxs-lookup"><span data-stu-id="b441b-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b441b-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b441b-107">Before you begin</span></span>

<span data-ttu-id="b441b-108">Du måste vara global-, licens- eller användaradministratör för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="b441b-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="b441b-109">Mer information finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b441b-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="b441b-110">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="b441b-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b441b-111">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="b441b-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="b441b-112">Välj cirklarna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="b441b-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="b441b-113">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="b441b-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="b441b-114">I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b441b-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="b441b-115">Ändra växlings knappen till **på** för de licenser som du vill tilldela dessa användare. </span><span class="sxs-lookup"><span data-stu-id="b441b-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="b441b-116">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="b441b-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="b441b-117">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="b441b-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="b441b-118">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="b441b-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="b441b-119">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b441b-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b441b-120">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="b441b-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="b441b-121">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="b441b-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="b441b-122">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="b441b-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="b441b-123">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b441b-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="b441b-124">Ändra växlings knappen till **på** för de licenser som du vill tilldela dessa användare. </span><span class="sxs-lookup"><span data-stu-id="b441b-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="b441b-125">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="b441b-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="b441b-126">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="b441b-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="b441b-127">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="b441b-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="b441b-128">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b441b-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b441b-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="b441b-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="b441b-130">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="b441b-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="b441b-131">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="b441b-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="b441b-132">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b441b-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="b441b-133">Ändra växlings knappen till **på** för de licenser som du vill tilldela dessa användare. </span><span class="sxs-lookup"><span data-stu-id="b441b-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="b441b-134">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="b441b-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="b441b-135">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="b441b-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="b441b-136">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="b441b-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="b441b-137">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b441b-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="b441b-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b441b-138">Next steps</span></span>

<span data-ttu-id="b441b-139">Om du inte ska [koppla de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)bör du överväga att [ta bort licenserna från ditt abonnemang](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.</span><span class="sxs-lookup"><span data-stu-id="b441b-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="b441b-140">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="b441b-140">Related content</span></span>

<span data-ttu-id="b441b-141">[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="b441b-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="b441b-142">[Ta bort licenser från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="b441b-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="b441b-143">[Ändra abonnemang manuellt](change-plans-manually.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="b441b-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="b441b-144">[Förstå abonnemang och licenser i Microsoft 365 för företag](../licenses/subscriptions-and-licenses.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="b441b-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="b441b-145">[Köpa en annan Microsoft 365 för företag-prenumeration](../buy-another-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b441b-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>