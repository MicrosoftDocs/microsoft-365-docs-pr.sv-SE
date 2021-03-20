---
title: Tilldela licenser till användare
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Lär dig hur man tilldelar licenser till användare.
ms.date: 08/14/2020
ms.openlocfilehash: 9f044f29cabf4976d5fbf17b22777da62e4414c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915500"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="edea3-103">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="edea3-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="edea3-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="edea3-104">The admin center is changing.</span></span> <span data-ttu-id="edea3-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="edea3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="edea3-106">Du kan tilldela licenser till användare antingen på sidan **Aktiva användare** eller på sidan **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="edea3-107">Metoden du använder beror på om du vill tilldela produktlicenser till särskilda användare eller tilldela licenser för en särskild produkt till användare.</span><span class="sxs-lookup"><span data-stu-id="edea3-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="edea3-108">[Läs om hur du lägger till ett användare och tilldelar en licens samtidigt](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="edea3-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="edea3-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="edea3-109">Before you begin</span></span>

- <span data-ttu-id="edea3-110">Du måste vara global-, licens- eller användaradministratör för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="edea3-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="edea3-111">Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="edea3-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="edea3-112">Du kan [tilldela licenser till användarkonton med Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="edea3-112">You can [assign licenses to user accounts with Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="edea3-113">Information om hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="edea3-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="edea3-114">Vissa tjänster, till exempel Sway, tilldelas automatiskt till användarna och behöver inte tilldelas individuellt.</span><span class="sxs-lookup"><span data-stu-id="edea3-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="edea3-115">Använd sidan licenser för att tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="edea3-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="edea3-116">När du tilldelar licenser på sidan **Licenser** tilldelar du licenser för en särskild produkt till upp till 20 användare.</span><span class="sxs-lookup"><span data-stu-id="edea3-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="edea3-117">På sidan **Licenser** ser du en lista över alla produkter som du har prenumerationer för.</span><span class="sxs-lookup"><span data-stu-id="edea3-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="edea3-118">Du ser också det totala antalet licenser för varje produkt, hur många licenser som har tilldelats och hur många som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="edea3-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="edea3-119">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="edea3-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="edea3-120">Välj en produkt.</span><span class="sxs-lookup"><span data-stu-id="edea3-120">Select a product.</span></span>
3. <span data-ttu-id="edea3-121">Välj **Tilldela licenser** på sidan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="edea3-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="edea3-122">I fönstret **Tilldela licenser till användare** börjar du skriva ett namn och väljer sedan namnet från resultatet för att lägga till det i listan.</span><span class="sxs-lookup"><span data-stu-id="edea3-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="edea3-123">Du kan lägga till upp till 20 användare åt gången.</span><span class="sxs-lookup"><span data-stu-id="edea3-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="edea3-124">Välj **Aktivera eller inaktivera appar och tjänster** för att tilldela eller ta bort åtkomst till särskilda objekt.</span><span class="sxs-lookup"><span data-stu-id="edea3-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="edea3-125">När du är klar väljer du **Tilldela** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="edea3-126">Vid konflikt visas ett meddelande som talar om vad problemet är och hur du åtgärdar det.</span><span class="sxs-lookup"><span data-stu-id="edea3-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="edea3-127">Om du till exempel valt licenser där det finns tjänster som är i konflikt, står det i meddelandet att du ska granska de tjänster som ingår i varje licens och försöka igen.</span><span class="sxs-lookup"><span data-stu-id="edea3-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="edea3-128">Ändra de appar och tjänster som en användare har åtkomst till:</span><span class="sxs-lookup"><span data-stu-id="edea3-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="edea3-129">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="edea3-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="edea3-130">På sidan **Licenser** väljer du raden för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="edea3-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="edea3-131">I det högra fönstret markerar eller avmarkerar du de appar och tjänster som du vill ge åtkomst till eller ta bort åtkomst för.</span><span class="sxs-lookup"><span data-stu-id="edea3-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="edea3-132">När du är klar väljer du **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="edea3-133">Använd sidan Aktiva användare för att tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="edea3-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="edea3-134">När du använder sidan **Aktiva användare** för att tilldela licenser tilldelar du användarlicenser till produkter.</span><span class="sxs-lookup"><span data-stu-id="edea3-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="edea3-135">Tilldela licenser till flera användare</span><span class="sxs-lookup"><span data-stu-id="edea3-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="edea3-136">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-137">Markera cirklarna bredvid namnen på de användare som du vill tilldela licenser till.</span><span class="sxs-lookup"><span data-stu-id="edea3-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="edea3-138">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="edea3-139">I fönstret **Hantera produktlicenser** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="edea3-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="edea3-140">I fönstret **Lägg till i befintliga produkter** ställer du reglaget i läget **På** för den licens som du vill att de valda användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="edea3-141">Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="edea3-142">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="edea3-143">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="edea3-144">Längst ned i fönstret väljer du **Lägg till** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="edea3-145">Tilldela licenser till flera användare</span><span class="sxs-lookup"><span data-stu-id="edea3-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="edea3-146">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-147">Markera kryssrutorna bredvid namnen på de användare som du vill tilldela licenser till.</span><span class="sxs-lookup"><span data-stu-id="edea3-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="edea3-148">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="edea3-149">I fönstret **Tilldela produkter** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="edea3-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="edea3-150">Ställ reglaget i läget **På** för de licenser som du vill att de valda användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="edea3-151">Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="edea3-152">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="edea3-153">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="edea3-154">Längst ned i fönstret **Lägg till i befintliga produkter** väljer du **Lägg till** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="edea3-155">Tilldela licenser till flera användare</span><span class="sxs-lookup"><span data-stu-id="edea3-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="edea3-156">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-157">Markera kryssrutorna bredvid namnen på de användare som du vill tilldela licenser till.</span><span class="sxs-lookup"><span data-stu-id="edea3-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="edea3-158">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="edea3-159">I fönstret **Tilldela produkter** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="edea3-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="edea3-160">Ställ reglaget i läget **På** för de licenser som du vill att de valda användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="edea3-161">Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="edea3-162">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="edea3-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="edea3-163">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="edea3-164">Längst ned i fönstret **Lägg till i befintliga produkter** väljer du **Lägg till** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="edea3-165">Tilldela licenser till en användare</span><span class="sxs-lookup"><span data-stu-id="edea3-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="edea3-166">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-167">Markerar raden för den användare som du vill tilldela en licens till.</span><span class="sxs-lookup"><span data-stu-id="edea3-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="edea3-168">I det högra fönstret väljer du **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="edea3-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="edea3-169">Expandera avsnittet **Licenser**, markera kryssrutorna för de licenser som du vill tilldela och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="edea3-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="edea3-170">Tilldela licenser till en användare</span><span class="sxs-lookup"><span data-stu-id="edea3-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="edea3-171">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-172">Markera kryssrutan bredvid namnet på den användare som du vill tilldela en licens till.</span><span class="sxs-lookup"><span data-stu-id="edea3-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="edea3-173">I det högra fönstret väljer du **Redigera** på raden **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="edea3-174">I fönstret **Produktlicenser** flyttar du reglaget till positionen **På** för den licens du vill tilldela användaren</span><span class="sxs-lookup"><span data-stu-id="edea3-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="edea3-175">Som standard är tilldelas alla tjänster som är associerade till den licensen automatiskt till användaren.</span><span class="sxs-lookup"><span data-stu-id="edea3-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="edea3-176">Du kan begränsa vilka tjänster som är tillgängliga för användaren.</span><span class="sxs-lookup"><span data-stu-id="edea3-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="edea3-177">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användaren ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="edea3-178">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="edea3-179">Tilldela licenser till en användare</span><span class="sxs-lookup"><span data-stu-id="edea3-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="edea3-180">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="edea3-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="edea3-181">Markera kryssrutan bredvid namnet på den användare som du vill tilldela en licens till.</span><span class="sxs-lookup"><span data-stu-id="edea3-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="edea3-182">I det högra fönstret väljer du **Redigera** på raden **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="edea3-183">I fönstret **Produktlicenser** flyttar du reglaget till positionen **På** för den licens du vill tilldela användaren</span><span class="sxs-lookup"><span data-stu-id="edea3-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="edea3-184">Som standard är tilldelas alla tjänster som är associerade till den licensen automatiskt till användaren.</span><span class="sxs-lookup"><span data-stu-id="edea3-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="edea3-185">Du kan begränsa vilka tjänster som är tillgängliga för användaren.</span><span class="sxs-lookup"><span data-stu-id="edea3-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="edea3-186">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användaren ska ha.</span><span class="sxs-lookup"><span data-stu-id="edea3-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="edea3-187">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="edea3-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="edea3-188">Tilldela en licens till en gästanvändare</span><span class="sxs-lookup"><span data-stu-id="edea3-188">Assign a license to a guest user</span></span>

<span data-ttu-id="edea3-189">Du kan bjuda in gästanvändare att samarbeta med din organisation i Azure Active Directory administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="edea3-189">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="edea3-190">För information om gästanvändaren, se [Vad är gästanvändaråtkomst i Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="edea3-190">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="edea3-191">Om du inte har någon gästanvändare se [Snabb start: lägga till gästanvändare i katalogen i Azure-portalen](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="edea3-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edea3-192">Du måste vara en global administratör för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="edea3-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="edea3-193">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory-administratörcenter</a></span><span class="sxs-lookup"><span data-stu-id="edea3-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="edea3-194">Välj **Användare** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="edea3-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="edea3-195">På **Användare | Alla användare (Förhandsgranskning)** sidan väljer du **Lägg till filter**.</span><span class="sxs-lookup"><span data-stu-id="edea3-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="edea3-196">I **Välj ett fält** väljer du **Användartyp** och sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="edea3-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="edea3-197">I nästa meny väljer du **Gäst**.</span><span class="sxs-lookup"><span data-stu-id="edea3-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="edea3-198">Välj den användare som behöver en licens i resultatlistan.</span><span class="sxs-lookup"><span data-stu-id="edea3-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="edea3-199">Under **Hantera** väljer du **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="edea3-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="edea3-200">Välj **Uppgifter**.</span><span class="sxs-lookup"><span data-stu-id="edea3-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="edea3-201">På sidan **Uppdatera licenstilldelningar** väljer du den produkt som du vill tilldela en licens för.</span><span class="sxs-lookup"><span data-stu-id="edea3-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="edea3-202">Gå till höger och avmarkera kryssrutorna för de tjänster som du inte vill att gäst användaren ska ha tillgång till.</span><span class="sxs-lookup"><span data-stu-id="edea3-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="edea3-203">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="edea3-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="edea3-204">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="edea3-204">Next steps</span></span>

<span data-ttu-id="edea3-205">Om dina användare inte har installerat Office-apparna kan du dela [snabbstartsguide för anställda](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) med dina användare att konfigurera saker, t. ex. [hur du laddar ned och installerar Microsoft 365 eller Office 2019 på en PC-eller Mac-](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och [hur du konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="edea3-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="edea3-206">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="edea3-206">Related content</span></span>

<span data-ttu-id="edea3-207">[Allmänt om prenumerationer och licenser](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="edea3-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="edea3-208">[Ta bort tilldelningen av licenser från användare](remove-licenses-from-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="edea3-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="edea3-209">[Köpa eller ta bort licenser för prenumerationen](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="edea3-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>