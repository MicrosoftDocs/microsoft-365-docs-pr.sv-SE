---
title: Skapa, redigera eller ta bort en anpassad användarvy
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Lär dig hur du använder filter för att skapa, redigera eller ta bort anpassad användarvy i Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755578"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="0b7fe-103">Skapa, redigera eller ta bort en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="0b7fe-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="0b7fe-104">Om du är global administratör eller användarhanteringsadministratör för en Microsoft 365 för företag-prenumeration kan du skapa anpassade användarvyer för att visa en viss delmängd av användarna.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="0b7fe-105">Dessa vyer är ett tillägg till standarduppsättningen med vyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="0b7fe-106">Du kan skapa, redigera eller ta bort anpassade användarvyer, och de anpassade vyer som du skapar är tillgängliga för alla administratörer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="0b7fe-107">Anpassade användarvyer i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="0b7fe-107">Custom user views in the admin center</span></span>

<span data-ttu-id="0b7fe-108">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i **listan Filter** som alla administratörer i företaget ser när de går till **sidan** Användare.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0b7fe-109">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="0b7fe-110">Standardvyer visas som standard i **listrutan** Filter.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="0b7fe-111">Standardfiltren omfattar Alla användare **,** Licensierade användare **,** Gästanvändare **,** Tillåtna inloggningar, Inloggning blockerade **,** Ej **licensierade** användare , Användare med fel , **Faktureringsadministratörer**, **Globala** administratörer , **Supportadministratörer**, **Tjänstadministratörer** och Användarhanteringsadministratörer. </span><span class="sxs-lookup"><span data-stu-id="0b7fe-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="0b7fe-112">Du kan inte redigera eller ta bort standardvyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="0b7fe-113">Några saker att tänka på om standardvyer:</span><span class="sxs-lookup"><span data-stu-id="0b7fe-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="0b7fe-114">I vissa standardvyer visas en osorterad lista om det finns fler än 2 000 användare i listan.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-114">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="0b7fe-115">Använd sökrutan för att hitta specifika användare i listan.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-115">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="0b7fe-116">Om du inte köpte Microsoft 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="0b7fe-117">Mer information finns i [Tilldela administratörsroller.](assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0b7fe-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="0b7fe-118">Välja filter för den anpassade användarvyn</span><span class="sxs-lookup"><span data-stu-id="0b7fe-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="0b7fe-119">Du kan skapa och redigera dina anpassade vyer i **fönstret Anpassat** filter.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="0b7fe-120">Om du markerar flera filteralternativ visas resultat som innehåller användare som matchar alla de valda villkoren.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="0b7fe-121">I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare i en viss domän som finns i Kanada.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="0b7fe-122">**A - Domän** Om du har flera domäner för organisationen kan du välja i en listrutan med domäner som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="0b7fe-123">**B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="0b7fe-124">**C - Plats** Välj en plats i en listrutan över länder.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="0b7fe-125">**D – Tilldelad produktlicens** Välj från en listrutan med licenser som är tillgängliga i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="0b7fe-126">Använd det här filtret för att visa användare som har den licens du valde tilldelad.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="0b7fe-127">Användare kan också ha ytterligare licenser.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="0b7fe-128">Du kan också filtrera efter ytterligare användarprofilinformation som används i organisationen, till exempel avdelning, ort, region, land eller region eller befattning.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="0b7fe-129">**Övriga villkor:**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="0b7fe-130">**Endast synkroniserade användare** Markera den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="0b7fe-131">**Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="0b7fe-132">**Olicensierade användare** Markera den här rutan om du vill hitta alla användare som inte har tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-132">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="0b7fe-133">Resultatet för den här vyn kan också omfatta användare som har en Exchange-postlåda men inte har en licens.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-133">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="0b7fe-134">Om du vill spåra de användarna specifikt använder du **filtret Ej licensierade användare med Exchange-postlådor eller Exchange-arkiv.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-134">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="0b7fe-135">Resultatet för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men inte har en licens.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-135">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="0b7fe-136">**Olicensierade användare med Exchange-postlådor eller Exchange-arkiv** Markera den här rutan om du vill visa användarkonton som skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats någon Microsoft 365-licens.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="0b7fe-137">Resultaten av det här filtret omfattar användare som har eller har tilldelats ett Exchange-arkiv.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="0b7fe-138">Filtret **Olicensierade användare med Exchange-postlådor** fungerar när:</span><span class="sxs-lookup"><span data-stu-id="0b7fe-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="0b7fe-139">Postlådan har nyligen konverterats från **delad** **till användare** och den har ingen licens.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="0b7fe-140">Postlådan har nyligen migrerats till Microsoft 365 men ingen licens har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="0b7fe-141">Postlådan har skapats med PowerShell och ingen licens har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="0b7fe-142">En ny postlåda som har skapats lokalt med en New-RemoteMailbox-cmdlet tillhandahålls för användaren.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="0b7fe-143">Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="0b7fe-144">I så fall kan du använda sökrutan för att hitta användare eller redigera den anpassade vyn för att förfina sökningen.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="0b7fe-145">Skapa en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="0b7fe-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b7fe-146">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="0b7fe-147">På sidan **Aktiva användare** väljer du **Filter** och sedan **Nytt filter**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="0b7fe-148">På sidan **Anpassat filter** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0b7fe-149">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0b7fe-150">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="0b7fe-151">På sidan **Aktiva användare** väljer du Vyer **och** sedan Lägg till **anpassad vy.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0b7fe-152">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0b7fe-153">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b7fe-154">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="0b7fe-155">På sidan **Aktiva användare** väljer du Vyer **och** sedan Lägg till **anpassad vy.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0b7fe-156">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0b7fe-157">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="0b7fe-158">Redigera eller ta bort en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="0b7fe-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b7fe-159">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="0b7fe-160">På sidan **Aktiva** användare väljer du **Filter**, väljer filtret du vill ändra och väljer sedan **Redigera filter**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0b7fe-161">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0b7fe-162">På sidan **Anpassat filter** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0b7fe-163">Eller välj Ta bort längst ned på sidan om du vill ta **bort filtret.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0b7fe-164">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="0b7fe-165">På sidan **Aktiva användare** väljer du **Vyer**, väljer filtret du vill ändra och väljer sedan Redigera den **här vyn.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0b7fe-166">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0b7fe-167">Redigera **informationen efter behov** på sidan Anpassad vy och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0b7fe-168">Om du vill ta bort filtret väljer du Ta bort anpassad vy längst **ned på sidan.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b7fe-169">Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="0b7fe-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="0b7fe-170">På sidan **Aktiva användare** väljer du **Vyer**, väljer filtret du vill ändra och väljer sedan Redigera den **här vyn.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0b7fe-171">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0b7fe-172">Redigera **informationen efter behov** på sidan Anpassad vy och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0b7fe-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0b7fe-173">Om du vill ta bort filtret väljer du Ta bort anpassad vy längst **ned på sidan.**</span><span class="sxs-lookup"><span data-stu-id="0b7fe-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     