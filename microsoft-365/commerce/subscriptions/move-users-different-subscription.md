---
title: Flytta användare till en annan prenumeration
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Läs om hur du flyttar användare mellan prenumerationer.
ms.date: 07/01/2020
ms.openlocfilehash: d110ee7c49befa34f5a2cd3bb44dc114aec25b62
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016554"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="8ffd3-103">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="8ffd3-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8ffd3-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-104">The admin center is changing.</span></span> <span data-ttu-id="8ffd3-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8ffd3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8ffd3-106">Om du har mer än en prenumeration, har användare med en licens för en prenumeration, men vill flytta dem till en annan prenumeration, kan du ersätta deras befintliga licens med en annan.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8ffd3-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="8ffd3-107">Before you begin</span></span>

<span data-ttu-id="8ffd3-108">Du måste vara global administratör, licens eller användaradministratör för att kunna tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="8ffd3-109">Mer information finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8ffd3-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="8ffd3-110">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="8ffd3-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8ffd3-111">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8ffd3-112">Markera cirklarna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="8ffd3-113">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="8ffd3-114">I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8ffd3-115">Växla växlingsknappen till **påpositionen** för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="8ffd3-116">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="8ffd3-117">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="8ffd3-118">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="8ffd3-119">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8ffd3-120">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8ffd3-121">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="8ffd3-122">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="8ffd3-123">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8ffd3-124">Växla växlingsknappen till **påpositionen** för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="8ffd3-125">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="8ffd3-126">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="8ffd3-127">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="8ffd3-128">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8ffd3-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8ffd3-130">Markera kryssrutorna bredvid namnen på de användare som du vill ersätta befintliga licenser för.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="8ffd3-131">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="8ffd3-132">I fönstret **Tilldela produkter** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8ffd3-133">Växla växlingsknappen till **påpositionen** för de licenser som du vill tilldela dessa användare.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="8ffd3-134">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="8ffd3-135">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="8ffd3-136">Alla tidigare tilldelade licenser för de markerade användarna tas bort.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="8ffd3-137">Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="8ffd3-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8ffd3-138">Next steps</span></span>

<span data-ttu-id="8ffd3-139">Om du inte tänker [tilldela om de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)kan du överväga att ta bort [licenserna från prenumerationen](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.</span><span class="sxs-lookup"><span data-stu-id="8ffd3-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="8ffd3-140">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="8ffd3-140">Related content</span></span>

<span data-ttu-id="8ffd3-141">[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8ffd3-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="8ffd3-142">[Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8ffd3-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="8ffd3-143">[Ändra planer manuellt](change-plans-manually.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8ffd3-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="8ffd3-144">[Förstå prenumerationer och licenser i Microsoft 365 för företag](../licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8ffd3-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="8ffd3-145">[Köp en annan Microsoft 365 för företag-prenumeration](../buy-another-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8ffd3-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>