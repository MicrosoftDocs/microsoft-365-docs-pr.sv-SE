---
title: Tilldela licenser till användare
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: Lär dig hur man tilldelar licenser till användare.
ms.openlocfilehash: 3622be180ae622d5d08066cc03773a8175fe9342
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398169"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="5fbeb-103">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="5fbeb-103">Assign licenses to users</span></span>

<span data-ttu-id="5fbeb-104">Du kan tilldela licenser till användare antingen på sidan **Aktiva användare** eller på sidan **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="5fbeb-105">Metoden du använder beror på om du vill tilldela produktlicenser till särskilda användare eller tilldela licenser för en särskild produkt till användare.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="5fbeb-106">Som administratör kan du inte tilldela eller ta bort licenser för en självbetjäningsprenumeration som köpts av en användare i din organisation.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="5fbeb-107">Du kan [ta över en självbetjäningsprenumeration](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)och sedan tilldela eller ta bort licenser.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="5fbeb-108">[Läs om hur du lägger till ett användare och tilldelar en licens samtidigt](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5fbeb-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="5fbeb-109">Before you begin</span></span>

- <span data-ttu-id="5fbeb-110">Du måste vara global-, licens- eller användaradministratör för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="5fbeb-111">Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="5fbeb-112">Du kan [tilldela licenser till användarkonton med Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-112">You can [assign licenses to user accounts with Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="5fbeb-113">Information om hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="5fbeb-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="5fbeb-114">Vissa tjänster, till exempel Sway, tilldelas automatiskt till användarna och behöver inte tilldelas individuellt.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="5fbeb-115">Använd sidan licenser för att tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="5fbeb-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="5fbeb-116">När du tilldelar licenser på sidan **Licenser** tilldelar du licenser för en särskild produkt till upp till 20 användare.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="5fbeb-117">På sidan **Licenser** ser du en lista över alla produkter som du har prenumerationer för.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="5fbeb-118">Du ser också det totala antalet licenser för varje produkt, hur många licenser som har tilldelats och hur många som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5fbeb-119">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5fbeb-120">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5fbeb-121">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5fbeb-122">Välj en produkt.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-122">Select a product.</span></span>
3. <span data-ttu-id="5fbeb-123">Välj **Tilldela licenser** på sidan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="5fbeb-124">I fönstret **Tilldela licenser till användare** börjar du skriva ett namn och väljer sedan namnet från resultatet för att lägga till det i listan.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="5fbeb-125">Du kan lägga till upp till 20 användare åt gången.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="5fbeb-126">Välj **Aktivera eller inaktivera appar och tjänster** för att tilldela eller ta bort åtkomst till särskilda objekt.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="5fbeb-127">När du är klar väljer du **Tilldela** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="5fbeb-128">Vid konflikt visas ett meddelande som talar om vad problemet är och hur du åtgärdar det.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="5fbeb-129">Om du till exempel valt licenser där det finns tjänster som är i konflikt, står det i meddelandet att du ska granska de tjänster som ingår i varje licens och försöka igen.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="5fbeb-130">Ändra de appar och tjänster som en användare har åtkomst till:</span><span class="sxs-lookup"><span data-stu-id="5fbeb-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5fbeb-131">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-131">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5fbeb-132">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5fbeb-133">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5fbeb-134">På sidan **Licenser** väljer du raden för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="5fbeb-135">I det högra fönstret markerar eller avmarkerar du de appar och tjänster som du vill ge åtkomst till eller ta bort åtkomst för.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="5fbeb-136">När du är klar väljer du **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="5fbeb-137">Använd sidan Aktiva användare för att tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="5fbeb-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="5fbeb-138">När du använder sidan **Aktiva användare** för att tilldela licenser tilldelar du användarlicenser till produkter.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="5fbeb-139">Tilldela licenser till flera användare</span><span class="sxs-lookup"><span data-stu-id="5fbeb-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5fbeb-140">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5fbeb-141">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-141">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5fbeb-142">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-142">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5fbeb-143">Markera cirklarna bredvid namnen på de användare som du vill tilldela licenser till.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="5fbeb-144">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-144">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="5fbeb-145">I fönstret **Hantera produktlicenser** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="5fbeb-146">I fönstret **Lägg till i befintliga produkter** ställer du reglaget i läget **På** för den licens som du vill att de valda användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="5fbeb-147">Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="5fbeb-148">Du kan begränsa vilka tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="5fbeb-149">Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="5fbeb-150">Längst ned i fönstret väljer du **Lägg till** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="5fbeb-151">Tilldela licenser till en användare</span><span class="sxs-lookup"><span data-stu-id="5fbeb-151">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5fbeb-152">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5fbeb-153">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5fbeb-154">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-154">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="5fbeb-155">Markerar raden för den användare som du vill tilldela en licens till.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-155">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="5fbeb-156">I det högra fönstret väljer du **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-156">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="5fbeb-157">Expandera avsnittet **Licenser**, markera kryssrutorna för de licenser som du vill tilldela och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-157">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="5fbeb-158">Tilldela en licens till en gästanvändare</span><span class="sxs-lookup"><span data-stu-id="5fbeb-158">Assign a license to a guest user</span></span>

<span data-ttu-id="5fbeb-159">Du kan bjuda in gästanvändare att samarbeta med din organisation i Azure Active Directory administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-159">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="5fbeb-160">För information om gästanvändaren, se [Vad är gästanvändaråtkomst i Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-160">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="5fbeb-161">Om du inte har någon gästanvändare se [Snabb start: lägga till gästanvändare i katalogen i Azure-portalen](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-161">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fbeb-162">Du måste vara en global administratör för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-162">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="5fbeb-163">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory-administratörcenter</a></span><span class="sxs-lookup"><span data-stu-id="5fbeb-163">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="5fbeb-164">Välj **Användare** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-164">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="5fbeb-165">På **Användare | Alla användare (Förhandsgranskning)** sidan väljer du **Lägg till filter**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-165">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="5fbeb-166">I **Välj ett fält** väljer du **Användartyp** och sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-166">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="5fbeb-167">I nästa meny väljer du **Gäst**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-167">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="5fbeb-168">Välj den användare som behöver en licens i resultatlistan.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-168">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="5fbeb-169">Under **Hantera** väljer du **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-169">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="5fbeb-170">Välj **Uppgifter**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-170">Select **Assignments**.</span></span>
9. <span data-ttu-id="5fbeb-171">På sidan **Uppdatera licenstilldelningar** väljer du den produkt som du vill tilldela en licens för.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-171">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="5fbeb-172">Gå till höger och avmarkera kryssrutorna för de tjänster som du inte vill att gäst användaren ska ha tillgång till.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-172">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="5fbeb-173">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5fbeb-173">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fbeb-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5fbeb-174">Next steps</span></span>

<span data-ttu-id="5fbeb-175">Om dina användare inte har installerat Office-apparna kan du dela [snabbstartsguide för anställda](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) med dina användare att konfigurera saker, t. ex. [hur du laddar ned och installerar Microsoft 365 eller Office 2019 på en PC-eller Mac-](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och [hur du konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="5fbeb-175">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="5fbeb-176">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="5fbeb-176">Related content</span></span>

<span data-ttu-id="5fbeb-177">[Allmänt om prenumerationer och licenser](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5fbeb-177">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="5fbeb-178">[Ta bort tilldelningen av licenser från användare](remove-licenses-from-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5fbeb-178">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="5fbeb-179">[Köpa eller ta bort licenser för prenumerationen](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5fbeb-179">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>