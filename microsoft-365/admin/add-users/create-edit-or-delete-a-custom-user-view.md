---
title: Skapa, redigera eller ta bort en anpassad användarvy i Office 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Lär dig att använda filter för att skapa, redigera eller ta bort anpassad användarvy i Office 365.
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42807185"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="0ba9a-103">Skapa, redigera eller ta bort en anpassad användarvy i Office 365</span><span class="sxs-lookup"><span data-stu-id="0ba9a-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="0ba9a-104">Om du är en global administratör eller användarhanteringsadministratör för Office 365 kan du skapa anpassade användarvyer för att visa en viss delmängd av användare.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="0ba9a-105">Dessa vyer är utöver den standarduppsättning vyer som medföljer Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="0ba9a-106">Du kan skapa, redigera eller ta bort anpassade användarvyer och de anpassade vyer du skapar är tillgängliga för alla administratörer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0ba9a-107">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="0ba9a-108">Anpassade användarvyer i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="0ba9a-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="0ba9a-109">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i **filterlistan** som alla administratörer i företaget ser när de går till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0ba9a-110">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0ba9a-111">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de går till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0ba9a-112">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0ba9a-113">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de går till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0ba9a-114">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="0ba9a-115">Standardanvändarvyer visas som standard i listrutan **Filter.**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="0ba9a-116">Standardfiltren omfattar **Alla användare,** **licensierade användare,** **Gästanvändare,** **Inloggning tillåten**, **Logga in blockerad,** **Olicensierade användare,** **Användare med fel,** **Faktureringsadministratörer,** **Globala administratörer,** **Helpdesk-administratörer,** **Tjänstadministratörer**och **användarhanteringsadministratörer**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="0ba9a-117">Du kan inte redigera eller ta bort standardvyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="0ba9a-118">Några saker att notera om standardvyer:</span><span class="sxs-lookup"><span data-stu-id="0ba9a-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="0ba9a-119">Vissa standardvyer visar en osorterad lista om det finns fler än 2 000 användare i listan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-119">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="0ba9a-120">Om du vill hitta specifika användare i den här listan använder du sökrutan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-120">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="0ba9a-121">Om du inte har köpt Office 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-121">If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="0ba9a-122">Mer information finns i [Tilldela administratörsroller](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0ba9a-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="0ba9a-123">Välj filter för din anpassade användarvy</span><span class="sxs-lookup"><span data-stu-id="0ba9a-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="0ba9a-124">Du kan skapa och redigera dina anpassade vyer i **fönstret Anpassat filter.**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="0ba9a-125">Om du väljer flera filteralternativ får du resultat som innehåller användare som matchar alla valda villkor.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="0ba9a-126">I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare på en viss domän som befinner sig i Kanada.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="0ba9a-127">**A - Domän** Om du har flera domäner för din organisation kan du välja från en listruta med domäner som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="0ba9a-128">**B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="0ba9a-129">**C - Plats** Välj en plats i en listruta med länder.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="0ba9a-130">**D - Tilldelad produktlicens** Välj bland en listruta med licenser som är tillgängliga i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="0ba9a-131">Använd det här filtret om du vill visa användare som har den licens som du har tilldelat dem.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="0ba9a-132">Användare kan också ha ytterligare licenser.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="0ba9a-133">Du kan också filtrera efter ytterligare användarprofilinformation som används i din organisation, till exempel avdelning, stad, stat eller provins, land eller region eller befattning.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="0ba9a-134">**Övriga villkor:**</span><span class="sxs-lookup"><span data-stu-id="0ba9a-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="0ba9a-135">**Synkroniserade användare** Välj den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="0ba9a-136">**Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="0ba9a-137">**Olicensierade användare** Välj den här rutan om du vill söka efter alla användare som inte har tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-137">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="0ba9a-138">Resultaten för den här vyn kan också omfatta användare som har en Exchange-postlåda men som inte har en licens.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-138">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="0ba9a-139">Om du vill spåra dessa användare specifikt använder du filtret **Olicensierade användare med Exchange-postlådor eller arkiv**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-139">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="0ba9a-140">Resultaten för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men som inte har någon licens.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-140">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="0ba9a-141">**Olicensierade användare med Exchange-postlådor eller arkiv** Välj den här rutan om du vill visa användarkonton som har skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats en Office 365-licens.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license.</span></span> <span data-ttu-id="0ba9a-142">Resultatet av det här filtret inkluderar användare som har eller som har tilldelats ett Exchange-arkiv.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 
    
> [!TIP]
> <span data-ttu-id="0ba9a-143">Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="0ba9a-144">I det här fallet använder du sökrutan för att hitta användare eller redigera den anpassade vyn för att förfina sökningen.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="0ba9a-145">Skapa en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="0ba9a-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0ba9a-146">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="0ba9a-147">På sidan **Aktiva användare** väljer du **Filter** och väljer **Nytt filter**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="0ba9a-148">På sidan **Anpassat filter** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0ba9a-149">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0ba9a-150">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0ba9a-151">På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0ba9a-152">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0ba9a-153">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="0ba9a-154">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="0ba9a-155">På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0ba9a-156">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0ba9a-157">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="0ba9a-158">Redigera eller ta bort en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="0ba9a-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0ba9a-159">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="0ba9a-160">På sidan **Aktiva användare** väljer du **Filter,** markerar det filter som du vill ändra och väljer sedan **Redigera filter**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0ba9a-161">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0ba9a-162">På sidan **Anpassat filter** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0ba9a-163">Om du vill ta bort filtret väljer du **Ta bort**längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0ba9a-164">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0ba9a-165">På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter du vill ändra och väljer sedan **Redigera den här vyn**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0ba9a-166">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0ba9a-167">På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0ba9a-168">Om du vill ta bort filtret väljer du **Ta bort anpassad vy**längst ned på sidan .</span><span class="sxs-lookup"><span data-stu-id="0ba9a-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0ba9a-169">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="0ba9a-170">På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter du vill ändra och väljer sedan **Redigera den här vyn**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0ba9a-171">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0ba9a-172">På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0ba9a-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0ba9a-173">Om du vill ta bort filtret väljer du **Ta bort anpassad vy**längst ned på sidan .</span><span class="sxs-lookup"><span data-stu-id="0ba9a-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     

