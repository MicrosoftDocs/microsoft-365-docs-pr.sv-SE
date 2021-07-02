---
title: Ta bort tilldelningen av licenser från användare
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Vilken metod du använder för att ta bort licenser beror på om du tar bort licenser från specifika användare eller från en viss produkt.
ms.date: 06/07/2021
ms.openlocfilehash: 6220ddc15e7b3381da1d78ad3ac4f3c2204bda78
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256837"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="6b1be-103">Ta bort tilldelningen av licenser från användare</span><span class="sxs-lookup"><span data-stu-id="6b1be-103">Unassign licenses from users</span></span>

<span data-ttu-id="6b1be-104">Du kan ta bort licenser från användare på **sidan Aktiva** användare eller på **sidan** Licenser.</span><span class="sxs-lookup"><span data-stu-id="6b1be-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="6b1be-105">Vilken metod du använder beror på om du vill ta bort licenser från specifika användare eller ta bort licenser för användare från en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="6b1be-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1be-106">Som administratör kan du inte tilldela eller ta bort licenser för en självbetjäningsprenumeration som köpts av en användare i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6b1be-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="6b1be-107">Du kan [ta över en självbetjäningsprenumeration](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)och sedan tilldela eller ta bort licenser.</span><span class="sxs-lookup"><span data-stu-id="6b1be-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6b1be-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6b1be-108">Before you begin</span></span>

- <span data-ttu-id="6b1be-109">Du måste vara global, licens och användaradministratör för att kunna ta bort licenser.</span><span class="sxs-lookup"><span data-stu-id="6b1be-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="6b1be-110">Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="6b1be-111">Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="6b1be-112">Du kan också [ta bort användarkonton](../add-users/delete-a-user.md) som har tilldelats en licens om du vill göra licensen tillgänglig för andra användare.</span><span class="sxs-lookup"><span data-stu-id="6b1be-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="6b1be-113">När du tar bort ett användarkonto blir licensen direkt tillgänglig att tilldela till någon annan.</span><span class="sxs-lookup"><span data-stu-id="6b1be-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="6b1be-114">Använda sidan Licenser för att ta bort licenser</span><span class="sxs-lookup"><span data-stu-id="6b1be-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="6b1be-115">När du använder sidan **Licenser** för att ta bort licenser tar du bort licenser för en viss produkt för upp till 20 användare.</span><span class="sxs-lookup"><span data-stu-id="6b1be-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6b1be-116">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6b1be-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="6b1be-117">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6b1be-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="6b1be-118">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6b1be-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="6b1be-119">Välj den produkt som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="6b1be-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="6b1be-120">Välj de användare som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="6b1be-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="6b1be-121">Välj **Ta bort licenser**.</span><span class="sxs-lookup"><span data-stu-id="6b1be-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="6b1be-122">Välj **Ta bort tilldelning i** rutan Ta **bort licenser.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="6b1be-123">Använda sidan Aktiva användare för att ta bort licenser</span><span class="sxs-lookup"><span data-stu-id="6b1be-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="6b1be-124">När du använder sidan **Aktiva användare** för att ta bort licenser tar du bort produktlicenser från användare.</span><span class="sxs-lookup"><span data-stu-id="6b1be-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="6b1be-125">Ta bort licenser från en användare</span><span class="sxs-lookup"><span data-stu-id="6b1be-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6b1be-126">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="6b1be-127">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="6b1be-128">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="6b1be-129">Markera raden för den användare som du vill ta bort en licens för.</span><span class="sxs-lookup"><span data-stu-id="6b1be-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="6b1be-130">I det högra fönstret väljer du **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="6b1be-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="6b1be-131">Expandera avsnittet **Licenser,** avmarkera rutorna för de licenser som du vill ta bort och välj sedan **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="6b1be-132">Ta bort licenser från flera användare</span><span class="sxs-lookup"><span data-stu-id="6b1be-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6b1be-133">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="6b1be-134">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="6b1be-135">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6b1be-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="6b1be-136">Markera cirklarna bredvid namnen på de användare som du vill ta bort licenser för.</span><span class="sxs-lookup"><span data-stu-id="6b1be-136">Select the circles next to the names of the users who you want to unassign licenses for.</span></span>
3. <span data-ttu-id="6b1be-137">Längst upp väljer du **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="6b1be-137">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="6b1be-138">I fönstret **Hantera produktlicenser** väljer du **Ta bort alla Spara**  >  **ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-138">In the **Manage product licenses** pane, select **Unassign all** > **Save changes**.</span></span>
5. <span data-ttu-id="6b1be-139">Välj Klar längst ned i **fönstret.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-139">At the bottom of the pane, select **Done**.</span></span>  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="6b1be-140">Vad händer med en användares data när du tar bort deras licens?</span><span class="sxs-lookup"><span data-stu-id="6b1be-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="6b1be-141">När en licens tas bort från en användare Exchange onlinedata som är kopplade till det kontot i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="6b1be-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="6b1be-142">Efter respitperioden på 30 dagar tas data bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="6b1be-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="6b1be-143">Filer som sparas OneDrive för företag tas inte bort såvida inte användaren tas bort från Administrationscenter för Microsoft 365 tas bort via Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="6b1be-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="6b1be-144">Mer information finns i OneDrive [och ta bort](/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="6b1be-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="6b1be-145">När licensen tas bort är användarens postlåda inte längre sökbar med hjälp av ett eDiscovery-verktyg som innehållssökning eller Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6b1be-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="6b1be-146">Mer information finns i "Söka i frånkopplade eller avlicensierade postlådor" i [Innehållssökning i Microsoft 365](../../compliance/content-search.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="6b1be-147">Om du har ett Enterprise-abonnemang, till exempel Office 365 Enterprise E3, kan Exchange Online bevara e-postdata för ett borttagna användarkonto genom att använda [inaktiva postlådor.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6b1be-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="6b1be-148">Mer information finns i Skapa [och hantera inaktiva postlådor i Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="6b1be-149">Information om hur du blockerar en användares åtkomst till data i Microsoft 365 efter att licensen har tagits bort, och hur du får åtkomst till data efteråt, finns i Ta bort en [tidigare anställd](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="6b1be-150">Om du tar bort en [användares](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) licens och användaren fortfarande har Office-appar installerade visas felmeddelanden om ej licensierad produkt och aktivering i Office när de använder Office program.</span><span class="sxs-lookup"><span data-stu-id="6b1be-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b1be-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6b1be-151">Next steps</span></span>

<span data-ttu-id="6b1be-152">Om du inte tänker [](../../managed-desktop/get-started/assign-licenses.md)omtilldela de oanvända [](../../commerce/licenses/buy-licenses.md) licenserna till andra användare bör du ta bort licenserna från prenumerationen så att du inte betalar för fler licenser än vad som behövs.</span><span class="sxs-lookup"><span data-stu-id="6b1be-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="6b1be-153">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="6b1be-153">Related content</span></span>

<span data-ttu-id="6b1be-154">[Ta bort licenser från din prenumeration](../../commerce/licenses/buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6b1be-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="6b1be-155">[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6b1be-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="6b1be-156">[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6b1be-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
