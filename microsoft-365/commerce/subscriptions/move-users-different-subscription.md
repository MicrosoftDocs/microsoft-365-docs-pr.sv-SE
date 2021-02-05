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
description: Lär dig hur du flyttar användare mellan prenumerationer.
ms.date: 07/01/2020
ms.openlocfilehash: ec9385d10cc1799509c6f1d2fa88059eecf3bd8c
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114675"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="ca8e0-103">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="ca8e0-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ca8e0-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-104">The admin center is changing.</span></span> <span data-ttu-id="ca8e0-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ca8e0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="ca8e0-106">Om du har fler än en prenumeration har du användare med en licens för en prenumeration, men vill flytta dem till en annan prenumeration, kan du ersätta deras befintliga licens med en annan.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ca8e0-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="ca8e0-107">Before you begin</span></span>

<span data-ttu-id="ca8e0-108">Du måste vara global-, licens- eller användaradministratör för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="ca8e0-109">Mer information finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="ca8e0-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="ca8e0-110">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="ca8e0-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca8e0-111">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ca8e0-112">Markera cirklarna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="ca8e0-113">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="ca8e0-114">I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="ca8e0-115">Ställ reglaget **i** läget På för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="ca8e0-116">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="ca8e0-117">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="ca8e0-118">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="ca8e0-119">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca8e0-120">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ca8e0-121">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="ca8e0-122">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="ca8e0-123">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="ca8e0-124">Ställ reglaget **i** läget På för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="ca8e0-125">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="ca8e0-126">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="ca8e0-127">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="ca8e0-128">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca8e0-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ca8e0-130">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="ca8e0-131">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="ca8e0-132">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="ca8e0-133">Ställ reglaget **i** läget På för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="ca8e0-134">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="ca8e0-135">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="ca8e0-136">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="ca8e0-137">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="ca8e0-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ca8e0-138">Next steps</span></span>

<span data-ttu-id="ca8e0-139">Om du inte tänker [](../../managed-desktop/get-started/assign-licenses.md)tilldela de oanvända licenserna [](../../commerce/licenses/buy-licenses.md) till andra användare kan du ta bort licenserna från prenumerationen så att du inte betalar för fler licenser än vad du behöver.</span><span class="sxs-lookup"><span data-stu-id="ca8e0-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="ca8e0-140">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="ca8e0-140">Related content</span></span>

<span data-ttu-id="ca8e0-141">[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ca8e0-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="ca8e0-142">[Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ca8e0-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="ca8e0-143">[Ändra abonnemang manuellt](change-plans-manually.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ca8e0-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="ca8e0-144">[Förstå prenumerationer och licenser i Microsoft 365 för företag](../licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ca8e0-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="ca8e0-145">[Köpa en annan Microsoft 365 för företag-prenumeration](../buy-another-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ca8e0-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>