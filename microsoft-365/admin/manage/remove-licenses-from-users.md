---
title: Ta bort tilldelningen av licenser från användare
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
description: Läs om hur du avtillvisar licenser från användarkonton.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015941"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="425d0-103">Ta bort tilldelningen av licenser från användare</span><span class="sxs-lookup"><span data-stu-id="425d0-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="425d0-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="425d0-104">The admin center is changing.</span></span> <span data-ttu-id="425d0-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="425d0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="425d0-106">Du kan ta bort tilldelning av licenser från användare på sidan **Aktiva användare** eller på sidan **Licenser.**</span><span class="sxs-lookup"><span data-stu-id="425d0-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="425d0-107">Vilken metod du använder beror på om du vill ta bort tilldelningen av produktlicenser från specifika användare eller ta bort tilldelning av användarlicenser från en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="425d0-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="425d0-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="425d0-108">Before you begin</span></span>

- <span data-ttu-id="425d0-109">Du måste vara global, licens, användaradministratör för att ta bort tilldelningslicenser.</span><span class="sxs-lookup"><span data-stu-id="425d0-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="425d0-110">Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="425d0-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="425d0-111">Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="425d0-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="425d0-112">Du kan också [ta bort användarkonton](../add-users/delete-a-user.md) som har tilldelats en licens för att göra deras licens tillgänglig för andra användare.</span><span class="sxs-lookup"><span data-stu-id="425d0-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="425d0-113">När du tar bort ett användarkonto är deras licens omedelbart tillgänglig för att tilldela någon annan.</span><span class="sxs-lookup"><span data-stu-id="425d0-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="425d0-114">Använd sidan Licenser för att ta bort tilldelning av licenser</span><span class="sxs-lookup"><span data-stu-id="425d0-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="425d0-115">När du använder sidan **Licenser** för att ta bort tilldelning av licenser avtar du licenser för en viss produkt för upp till 20 användare.</span><span class="sxs-lookup"><span data-stu-id="425d0-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="425d0-116">Gå till sidan **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="425d0-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="425d0-117">Välj den produkt som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="425d0-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="425d0-118">Välj de användare som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="425d0-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="425d0-119">Välj **Licenser för ta bort tilldelning**.</span><span class="sxs-lookup"><span data-stu-id="425d0-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="425d0-120">Välj **Ta bort tilldelning**i rutan Licenser för **avtilldelning** .</span><span class="sxs-lookup"><span data-stu-id="425d0-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="425d0-121">Använd sidan Aktiva användare för att ta bort tilldelning av licenser</span><span class="sxs-lookup"><span data-stu-id="425d0-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="425d0-122">När du använder sidan **Aktiva användare** för att ta bort tilldelning av licenser avtar du produktlicenser från användare.</span><span class="sxs-lookup"><span data-stu-id="425d0-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="425d0-123">Ta bort tilldelning av licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="425d0-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="425d0-124">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-125">Markera raden för den användare som du vill ta bort en licens för.</span><span class="sxs-lookup"><span data-stu-id="425d0-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="425d0-126">I det högra fönstret väljer du **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="425d0-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="425d0-127">Expandera avsnittet **Licenser,** rensa rutorna för de licenser som du vill ta bort och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="425d0-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="425d0-128">Ta bort tilldelning av licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="425d0-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="425d0-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-130">Välj den användare som du vill ta bort tilldelningen av licensen för.</span><span class="sxs-lookup"><span data-stu-id="425d0-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="425d0-131">Välj **Redigera**på raden **Produktlicenser** till höger .</span><span class="sxs-lookup"><span data-stu-id="425d0-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="425d0-132">I fönstret **Produktlicenser** växlar du växlingsknappen till **avpositionen** för den licens som du vill ta bort tilldelningen för användaren.</span><span class="sxs-lookup"><span data-stu-id="425d0-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="425d0-133">Om du till exempel stänger av Office 365 Enterprise E3-licensen avtilldelningar den licensen och alla tjänster under den licensen för den användaren.</span><span class="sxs-lookup"><span data-stu-id="425d0-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="425d0-134">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="425d0-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="425d0-135">Ta bort tilldelning av licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="425d0-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="425d0-136">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-137">Välj den användare som du vill ta bort tilldelningen av licensen för.</span><span class="sxs-lookup"><span data-stu-id="425d0-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="425d0-138">Välj **Redigera**på raden **Produktlicenser** till höger .</span><span class="sxs-lookup"><span data-stu-id="425d0-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="425d0-139">I fönstret **Produktlicenser** växlar du växlingsknappen till **avpositionen** för den licens som du vill ta bort tilldelningen för användaren.</span><span class="sxs-lookup"><span data-stu-id="425d0-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="425d0-140">Om du till exempel stänger av Office 365 Enterprise E3-licensen avtilldelningar den licensen och alla tjänster under den licensen för den användaren.</span><span class="sxs-lookup"><span data-stu-id="425d0-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="425d0-141">Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="425d0-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="425d0-142">Ta bort tilldelning av licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="425d0-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="425d0-143">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-144">Markera cirklarna bredvid namnen på de användare som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="425d0-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="425d0-145">Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="425d0-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="425d0-146">I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="425d0-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="425d0-147">Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="425d0-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="425d0-148">Ta bort tilldelning av licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="425d0-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="425d0-149">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-150">Markera rutorna bredvid namnen på de användare som du vill ta bort alla licenser för.</span><span class="sxs-lookup"><span data-stu-id="425d0-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="425d0-151">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="425d0-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="425d0-152">I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="425d0-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="425d0-153">Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **Close** \> **Stäng Stäng**.</span><span class="sxs-lookup"><span data-stu-id="425d0-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="425d0-154">Ta bort tilldelning av licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="425d0-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="425d0-155">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="425d0-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="425d0-156">Markera rutorna bredvid namnen på de användare som du vill ta bort alla licenser för.</span><span class="sxs-lookup"><span data-stu-id="425d0-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="425d0-157">I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="425d0-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="425d0-158">I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="425d0-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="425d0-159">Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **Close** \> **Stäng Stäng**.</span><span class="sxs-lookup"><span data-stu-id="425d0-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="425d0-160">Vad händer med en användares data när du tar bort deras licens?</span><span class="sxs-lookup"><span data-stu-id="425d0-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="425d0-161">När en licens tas bort från en användare lagras data som är associerade med det kontot i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="425d0-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="425d0-162">Efter respitperioden på 30 dagar tas data bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="425d0-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="425d0-163">Filer som sparats i OneDrive för företag tas inte bort om inte användaren tas bort från administrationscentret för Microsoft 365 eller tas bort via Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="425d0-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="425d0-164">Mer information finns i [OneDrive-lagring och borttagning](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="425d0-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="425d0-165">När licensen tas bort kan användarens postlåda inte längre sökas med hjälp av ett eDiscovery-verktyg som Content Search eller Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="425d0-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="425d0-166">Mer information finns i "Söka frånkopplade eller avlicensierade postlådor" i [Innehållssökning i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="425d0-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="425d0-167">Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise E3, kan du bevara postlådedata för ett borttaget användarkonto med hjälp av [inaktiva postlådor](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="425d0-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="425d0-168">Mer information finns i [Skapa och hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="425d0-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="425d0-169">Mer information om hur du blockerar en användares åtkomst till Microsoft 365-data efter att licensen har tagits bort och hur du får åtkomst till data efteråt finns i [Ta bort en tidigare anställd](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="425d0-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="425d0-170">Om du tar bort en användares licens och de fortfarande har Office-appar installerade visas [Olicensierade produkt- och aktiveringsfel i Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) när de använder Office-appar.</span><span class="sxs-lookup"><span data-stu-id="425d0-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="425d0-171">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="425d0-171">Next steps</span></span>

<span data-ttu-id="425d0-172">Om du inte tänker [tilldela om de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)kan du överväga att ta bort [licenserna från prenumerationen](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.</span><span class="sxs-lookup"><span data-stu-id="425d0-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="425d0-173">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="425d0-173">Related content</span></span>

<span data-ttu-id="425d0-174">[Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="425d0-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="425d0-175">[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="425d0-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="425d0-176">[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="425d0-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>