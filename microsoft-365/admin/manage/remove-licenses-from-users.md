---
title: Ta bort tilldelningen av licenser från användare
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
description: Lär dig hur du tar bort tilldelning av licenser från användar konton.
ms.date: 07/01/2020
ms.openlocfilehash: 455348e7dba20913e54e5a4059755f9391644e03
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645101"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="7ae13-103">Ta bort tilldelningen av licenser från användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7ae13-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="7ae13-104">The admin center is changing.</span></span> <span data-ttu-id="7ae13-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7ae13-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="7ae13-106">Du kan ta bort licenser från användare på sidan **aktiva användare** eller på sidan **licenser** .</span><span class="sxs-lookup"><span data-stu-id="7ae13-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="7ae13-107">Vilken metod du använder beror på om du vill ta bort tilldelning av produkt licenser från specifika användare eller ta bort licenser för användare från en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="7ae13-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="7ae13-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="7ae13-108">Before you begin</span></span>

- <span data-ttu-id="7ae13-109">Du måste vara global licens och användar administratör för att ta bort licenser.</span><span class="sxs-lookup"><span data-stu-id="7ae13-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="7ae13-110">Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7ae13-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="7ae13-111">Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="7ae13-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="7ae13-112">Du kan också [ta bort användar konton](../add-users/delete-a-user.md) som har tilldelats en licens om du vill göra licensen tillgänglig för andra användare.</span><span class="sxs-lookup"><span data-stu-id="7ae13-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="7ae13-113">När du tar bort ett användar konto är deras licens omedelbart tillgänglig och kan kopplas till någon annan.</span><span class="sxs-lookup"><span data-stu-id="7ae13-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="7ae13-114">Använd sidan licenser för att ta bort licenser</span><span class="sxs-lookup"><span data-stu-id="7ae13-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="7ae13-115">När du använder sidan **licenser** för att ta bort licenser tar du bort licenser för en viss produkt för upp till 20 användare.</span><span class="sxs-lookup"><span data-stu-id="7ae13-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="7ae13-116">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="7ae13-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7ae13-117">Välj den produkt som du vill ta bort tilldelning av licenser för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="7ae13-118">Välj de användare som du vill ta bort tilldelning av licenser för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="7ae13-119">Välj **ta bort licenser**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="7ae13-120">Välj **ta bort tilldelning**i rutan **ta bort licenser** .</span><span class="sxs-lookup"><span data-stu-id="7ae13-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="7ae13-121">Använd sidan aktiva användare för att ta bort licenser</span><span class="sxs-lookup"><span data-stu-id="7ae13-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="7ae13-122">När du använder sidan **aktiva användare** för att ta bort licenser tar du bort produkt licenser från användare.</span><span class="sxs-lookup"><span data-stu-id="7ae13-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="7ae13-123">Ta bort licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="7ae13-124">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-125">Markera raden för den användare som du vill ta bort en licens för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="7ae13-126">I det högra fönstret väljer du **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="7ae13-127">Expandera avsnittet **licenser** , avmarkera rutorna för de licenser du vill ta bort och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="7ae13-128">Ta bort licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="7ae13-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-130">Välj den användare som du vill koppla licensen för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="7ae13-131">Välj **Redigera**till höger på raden **produkt licenser** .</span><span class="sxs-lookup"><span data-stu-id="7ae13-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="7ae13-132">I fönstret **produkt licenser** växlar du växlings knappen till **utanför** position för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7ae13-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="7ae13-133">Om du till exempel stänger av licensen för Office 365 Enterprise, E3 tilldelar den licensen och alla tjänster under den användaren.</span><span class="sxs-lookup"><span data-stu-id="7ae13-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="7ae13-134">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="7ae13-135">Ta bort licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="7ae13-136">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-137">Välj den användare som du vill koppla licensen för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="7ae13-138">Välj **Redigera**till höger på raden **produkt licenser** .</span><span class="sxs-lookup"><span data-stu-id="7ae13-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="7ae13-139">I fönstret **produkt licenser** växlar du växlings knappen till **utanför** position för den licens du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7ae13-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="7ae13-140">Om du till exempel stänger av licensen för Office 365 Enterprise, E3 tilldelar den licensen och alla tjänster under den användaren.</span><span class="sxs-lookup"><span data-stu-id="7ae13-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="7ae13-141">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="7ae13-142">Ta bort licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="7ae13-143">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-144">Välj cirklarna bredvid namnen på de användare som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="7ae13-145">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="7ae13-146">I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="7ae13-147">Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="7ae13-148">Ta bort licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="7ae13-149">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-150">Markera kryss rutorna för de användare som du vill ta bort alla licenser för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="7ae13-151">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="7ae13-152">I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="7ae13-153">Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="7ae13-154">Ta bort licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="7ae13-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="7ae13-155">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="7ae13-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7ae13-156">Markera kryss rutorna för de användare som du vill ta bort alla licenser för.</span><span class="sxs-lookup"><span data-stu-id="7ae13-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="7ae13-157">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="7ae13-158">I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="7ae13-159">Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7ae13-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="7ae13-160">Vad händer med en användares data när de tar bort sin licens?</span><span class="sxs-lookup"><span data-stu-id="7ae13-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="7ae13-161">När en licens tas bort från en användare sparas data som är kopplade till kontot i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="7ae13-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="7ae13-162">Efter 30 dagars perioden raderas data och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="7ae13-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="7ae13-163">Filer som sparats i OneDrive för företag tas inte bort om användaren inte tas bort från Microsoft 365 Admin Center eller tas bort med Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="7ae13-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="7ae13-164">Mer information finns i [OneDrive-bevarande och borttagning](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="7ae13-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="7ae13-165">När licensen tas bort är användarens post låda inte längre sökbar genom att använda ett eDiscovery-verktyg som innehålls sökning eller Avancerad eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7ae13-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="7ae13-166">Mer information finns i "söka efter frånkopplade eller de licensierade postlådor" i [innehålls sökning i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="7ae13-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="7ae13-167">Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise E3, kan du använda Exchange Online för att bevara post lådorna för ett borttaget användar konto med hjälp av [inaktiva post lådor](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="7ae13-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="7ae13-168">Mer information finns i [skapa och hantera inaktiva post lådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="7ae13-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="7ae13-169">Information om hur du blockerar en användares åtkomst till Microsoft 365-data efter att den har tagits bort och hur du får till gång till informationen finns i [ta bort en tidigare anställd](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="7ae13-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="7ae13-170">Om du tar bort en användares licens och de fortfarande har Office-appar installerade visas olicensierad [produkt och aktiverings fel i Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) när de använder Office-appar.</span><span class="sxs-lookup"><span data-stu-id="7ae13-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ae13-171">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7ae13-171">Next steps</span></span>

<span data-ttu-id="7ae13-172">Om du inte ska [koppla de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)bör du överväga att [ta bort licenserna från ditt abonnemang](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.</span><span class="sxs-lookup"><span data-stu-id="7ae13-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="7ae13-173">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="7ae13-173">Related content</span></span>

<span data-ttu-id="7ae13-174">[Ta bort licenser från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="7ae13-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="7ae13-175">[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="7ae13-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="7ae13-176">[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7ae13-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>