---
title: Tilldela administratörsroller i administrationscentret för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Lär dig hur du tilldelar administratörsroller till en eller flera användare i företaget så att de kan utföra specifika uppgifter i administrationscentret.
ms.openlocfilehash: 5c40199823c93968be97302efc8e2d404f3cfed1
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604339"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="baa23-103">Tilldela administratörsroller</span><span class="sxs-lookup"><span data-stu-id="baa23-103">Assign admin roles</span></span>

<span data-ttu-id="baa23-104">Om du är den person som köpte Microsoft Business-prenumerationen är du global administratör. Det innebär att du har obegränsad kontroll över produkterna i dina prenumerationer och att du kan komma åt de flesta data.</span><span class="sxs-lookup"><span data-stu-id="baa23-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="baa23-105">Mer information finns i [Om administratörsroller](about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="baa23-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="baa23-106">Om du lägger till nya användare och inte tilldelar dem  en administratörsroll kommer de att ha användarrollen och inte ha administratörsbehörighet till något av Microsofts administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="baa23-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="baa23-107">Men om du behöver hjälp med att få saker gjorda kan du tilldela en administratörsroll till en användare.</span><span class="sxs-lookup"><span data-stu-id="baa23-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="baa23-108">Om du till exempel behöver någon som ska hjälpa till att återställa lösenord, ska du inte tilldela dem rollen som global administratör, bör du tilldela dem rollen som lösenordsadministratör.</span><span class="sxs-lookup"><span data-stu-id="baa23-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="baa23-109">Att ha för många globala administratörer, med obegränsad åtkomst till dina data och online-företag, är en säkerhetsrisk.</span><span class="sxs-lookup"><span data-stu-id="baa23-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="baa23-110">Titta: Lägg till en administratör.</span><span class="sxs-lookup"><span data-stu-id="baa23-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="baa23-111">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="baa23-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="baa23-112">Tilldela administratörsroller</span><span class="sxs-lookup"><span data-stu-id="baa23-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="baa23-113">Du kan tilldela användare till en roll på 2 olika sätt:</span><span class="sxs-lookup"><span data-stu-id="baa23-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="baa23-114">Du kan gå till användarens information och Hantera **roller och** tilldela en roll till användaren.</span><span class="sxs-lookup"><span data-stu-id="baa23-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="baa23-115">Du kan också gå **till Roller** och välja rollen och sedan lägga till flera användare i den.</span><span class="sxs-lookup"><span data-stu-id="baa23-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="baa23-116">Tilldela administratörsroller till användare med hjälp av Roller</span><span class="sxs-lookup"><span data-stu-id="baa23-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="baa23-117">I administrationscentret går du till **Roller**.</span><span class="sxs-lookup"><span data-stu-id="baa23-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="baa23-118">Välj **flikarna Azure AD** **eller Intune för** att visa de administratörsroller som är tillgängliga för din organisation.</span><span class="sxs-lookup"><span data-stu-id="baa23-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="baa23-119">Välj den administratörsroll som du vill tilldela användaren.</span><span class="sxs-lookup"><span data-stu-id="baa23-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="baa23-120">Välj **Tilldelade administratörer Lägg** > **till.**</span><span class="sxs-lookup"><span data-stu-id="baa23-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="baa23-121">Skriv användarens **visningsnamn** **eller användarnamn** och välj sedan användaren i listan med förslag.</span><span class="sxs-lookup"><span data-stu-id="baa23-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="baa23-122">Lägg till flera användare tills du är klar.</span><span class="sxs-lookup"><span data-stu-id="baa23-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="baa23-123">Välj **Spara** så läggs användaren till i listan över tilldelade administratörer.</span><span class="sxs-lookup"><span data-stu-id="baa23-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="baa23-124">Tilldela en användare till en administratörsroll från aktiva användare</span><span class="sxs-lookup"><span data-stu-id="baa23-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="baa23-125">I administrationscentret går du till **sidan** > [Användare aktiva](https://go.microsoft.com/fwlink/p/?linkid=834822) användare.</span><span class="sxs-lookup"><span data-stu-id="baa23-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="baa23-126">På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="baa23-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="baa23-127">Välj Hantera roller under Roller i **den utfäll** **du fönsterrutan.**</span><span class="sxs-lookup"><span data-stu-id="baa23-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="baa23-128">Välj den administratörsroll som du vill tilldela användaren.</span><span class="sxs-lookup"><span data-stu-id="baa23-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="baa23-129">Om du inte ser den roll du letar efter väljer du **Visa alla** längst ned i listan.</span><span class="sxs-lookup"><span data-stu-id="baa23-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="baa23-130">I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="baa23-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="baa23-131">På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="baa23-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="baa23-132">Välj Redigera bredvid Roller i det **utfällade** **fönstret.**</span><span class="sxs-lookup"><span data-stu-id="baa23-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="baa23-133">Om du inte ser alternativet Redigera **har** du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer.</span><span class="sxs-lookup"><span data-stu-id="baa23-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="baa23-134">Be en global administratör i företaget att tilldela roller åt dig.</span><span class="sxs-lookup"><span data-stu-id="baa23-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="baa23-135">I ett litet företag är företagsägaren (den person som köpte prenumerationen) en global administratör. I ett stort företag är viktiga personer i IT-avdelningen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="baa23-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="baa23-136">Välj **Anpassad administratör** för att se en lista över roller som är anpassad för dig.</span><span class="sxs-lookup"><span data-stu-id="baa23-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="baa23-137">En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="baa23-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="baa23-138">I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="baa23-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="baa23-139">På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="baa23-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="baa23-140">Välj Redigera bredvid Roller i det **utfällade** **fönstret.**</span><span class="sxs-lookup"><span data-stu-id="baa23-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="baa23-141">Om du inte ser alternativet Redigera **har** du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer.</span><span class="sxs-lookup"><span data-stu-id="baa23-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="baa23-142">Be en global administratör i företaget att tilldela roller åt dig.</span><span class="sxs-lookup"><span data-stu-id="baa23-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="baa23-143">I ett litet företag är företagsägaren (den person som köpte prenumerationen) en global administratör. I ett stort företag är viktiga personer i IT-avdelningen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="baa23-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="baa23-144">Välj **Anpassad administratör** för att se en lista över roller som är anpassad för dig.</span><span class="sxs-lookup"><span data-stu-id="baa23-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="baa23-145">En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="baa23-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="baa23-146">Tilldela administratörsroller till flera användare</span><span class="sxs-lookup"><span data-stu-id="baa23-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="baa23-147">Om du känner till PowerShell kan du [gå till Tilldela roller till användarkonton med PowerShell.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="baa23-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="baa23-148">Det är ett bra sätt att tilldela roller till hundratals användare.</span><span class="sxs-lookup"><span data-stu-id="baa23-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="baa23-149">Använd följande instruktioner för att tilldela roller till mer än tio användare åt gången.</span><span class="sxs-lookup"><span data-stu-id="baa23-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="baa23-150">Kontrollera administratörsroller i organisationen</span><span class="sxs-lookup"><span data-stu-id="baa23-150">Check admin roles in your organization</span></span>

<span data-ttu-id="baa23-151">Du kanske inte har rätt behörighet för att tilldela administratörsroller till andra användare.</span><span class="sxs-lookup"><span data-stu-id="baa23-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="baa23-152">Kontrollera att du har rätt behörigheter eller be en annan administratör att tilldela roller åt dig.</span><span class="sxs-lookup"><span data-stu-id="baa23-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="baa23-153">Du kan kontrollera administratörsrollbehörigheter på 2 olika sätt:</span><span class="sxs-lookup"><span data-stu-id="baa23-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="baa23-154">Du kan gå till användarens information och titta under **Roller** på **kontosidan.**</span><span class="sxs-lookup"><span data-stu-id="baa23-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="baa23-155">Du kan också gå **till Roller** och välja administratörsroll och välja tilldelade administratörer för att se vilka användare som har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="baa23-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="baa23-156">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="baa23-156">Related articles</span></span>

[<span data-ttu-id="baa23-157">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="baa23-157">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="baa23-158">Administratörens rollbehörigheter i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="baa23-158">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[<span data-ttu-id="baa23-159">Tilldela roller till användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="baa23-159">Assign roles to user accounts with PowerShell</span></span>](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[<span data-ttu-id="baa23-160">Auktorisera eller ta bort partnerrelationer</span><span class="sxs-lookup"><span data-stu-id="baa23-160">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)