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
description: Lär dig att använda filter för att skapa, redigera eller ta bort anpassad användarvy i Microsoft 365.
ms.openlocfilehash: 265aa1a7c22475710a12a93c2bfee0b7749f438b
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431647"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="bb872-103">Skapa, redigera eller ta bort en anpassad användarvy i Office 365</span><span class="sxs-lookup"><span data-stu-id="bb872-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="bb872-104">Om du är global administratör eller användarhanteringsadministratör för Office 365 kan du skapa anpassade användarvyer för att visa en viss delmängd användare.</span><span class="sxs-lookup"><span data-stu-id="bb872-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="bb872-105">Dessa vyer är utöver standarduppsättningen vyer som medverkar med Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb872-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="bb872-106">Du kan skapa, redigera eller ta bort anpassade användarvyer och de anpassade vyer som du skapar är tillgängliga för alla administratörer.</span><span class="sxs-lookup"><span data-stu-id="bb872-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="bb872-107">Anpassade användarvyer i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="bb872-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="bb872-108">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Filter** som alla administratörer i företaget ser när de kommer till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="bb872-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="bb872-109">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="bb872-110">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de kommer till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="bb872-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="bb872-111">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="bb872-112">När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de kommer till sidan **Användare.**</span><span class="sxs-lookup"><span data-stu-id="bb872-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="bb872-113">Du kan skapa upp till 50 anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="bb872-114">Standardanvändarvyer visas som standard i **listrutan Filter.**</span><span class="sxs-lookup"><span data-stu-id="bb872-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="bb872-115">Standardfiltren omfattar **Alla användare**, **Licensierade användare**, **Gästanvändare**, Inloggning tillåten , **Inloggningsblockerad**, **Olicensierade användare**, Användare med **fel,** **Faktureringsadministratörer**, **Globala administratörer**, **Helpdesk-administratörer**, **Tjänstadministratörer**och **Användarhanteringsadministratörer**. **Sign-in allowed**</span><span class="sxs-lookup"><span data-stu-id="bb872-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="bb872-116">Du kan inte redigera eller ta bort standardvyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="bb872-117">Några saker att notera om standardvyer:</span><span class="sxs-lookup"><span data-stu-id="bb872-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="bb872-118">Vissa standardvyer visar en osorterad lista om det finns fler än 2 000 användare i listan.</span><span class="sxs-lookup"><span data-stu-id="bb872-118">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="bb872-119">Om du vill hitta specifika användare i den här listan använder du sökrutan.</span><span class="sxs-lookup"><span data-stu-id="bb872-119">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="bb872-120">Om du inte köpte Microsoft 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan.</span><span class="sxs-lookup"><span data-stu-id="bb872-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="bb872-121">Mer information finns i [Tilldela administratörsroller](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb872-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="bb872-122">Välj filter för din anpassade användarvy</span><span class="sxs-lookup"><span data-stu-id="bb872-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="bb872-123">Du kan skapa och redigera anpassade vyer i fönstret **Anpassad filter.**</span><span class="sxs-lookup"><span data-stu-id="bb872-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="bb872-124">Om du väljer flera filteralternativ får du resultat som innehåller användare som matchar alla valda villkor.</span><span class="sxs-lookup"><span data-stu-id="bb872-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="bb872-125">I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare på en viss domän som finns i Kanada.</span><span class="sxs-lookup"><span data-stu-id="bb872-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="bb872-126">**A - Domän** Om du har flera domäner för din organisation kan du välja från en listruta med domäner som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="bb872-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="bb872-127">**B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade.</span><span class="sxs-lookup"><span data-stu-id="bb872-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="bb872-128">**C - Plats** Välj en plats i en listruta över länder.</span><span class="sxs-lookup"><span data-stu-id="bb872-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="bb872-129">**D - Tilldelad produktlicens** Välj från en listruta med licenser som är tillgängliga i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bb872-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="bb872-130">Använd det här filtret om du vill visa användare som har den licens som du har valt tilldelats dem.</span><span class="sxs-lookup"><span data-stu-id="bb872-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="bb872-131">Användare kan också ha ytterligare licenser.</span><span class="sxs-lookup"><span data-stu-id="bb872-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="bb872-132">Du kan också filtrera efter ytterligare användarprofilinformation som används i organisationen, till exempel avdelning, ort, delstat eller provins, land eller region eller befattning.</span><span class="sxs-lookup"><span data-stu-id="bb872-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="bb872-133">**Övriga villkor:**</span><span class="sxs-lookup"><span data-stu-id="bb872-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="bb872-134">**Endast synkroniserade användare** Markera den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte.</span><span class="sxs-lookup"><span data-stu-id="bb872-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="bb872-135">**Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel.</span><span class="sxs-lookup"><span data-stu-id="bb872-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="bb872-136">**Olicensierade användare** Markera den här rutan om du vill söka efter alla användare som inte har tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="bb872-136">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="bb872-137">Resultaten för den här vyn kan också omfatta användare som har en Exchange-postlåda men inte har någon licens.</span><span class="sxs-lookup"><span data-stu-id="bb872-137">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="bb872-138">Om du vill spåra dessa användare specifikt använder du filtret **Olicensierade användare med Exchange-postlådor eller arkiv**.</span><span class="sxs-lookup"><span data-stu-id="bb872-138">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="bb872-139">Resultaten för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men som inte har någon licens.</span><span class="sxs-lookup"><span data-stu-id="bb872-139">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="bb872-140">**Olicensierade användare med Exchange-postlådor eller arkiv** Markera den här rutan om du vill visa användarkonton som har skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats en Microsoft 365-licens.</span><span class="sxs-lookup"><span data-stu-id="bb872-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="bb872-141">Resultatet av det här filtret omfattar användare som har eller har tilldelats ett Exchange-arkiv.</span><span class="sxs-lookup"><span data-stu-id="bb872-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="bb872-142">Filtret **Olicensierade användare med Exchange-postlådor** fungerar när:</span><span class="sxs-lookup"><span data-stu-id="bb872-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="bb872-143">Postlådan har nyligen konverterats från **delad** till **användare** och den har ingen licens.</span><span class="sxs-lookup"><span data-stu-id="bb872-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="bb872-144">Postlådan har nyligen migrerats till Microsoft 365 men en licens har inte tilldelats.</span><span class="sxs-lookup"><span data-stu-id="bb872-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="bb872-145">Postlådan har skapats med PowerShell och en licens har inte tilldelats.</span><span class="sxs-lookup"><span data-stu-id="bb872-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="bb872-146">En ny postlåda som har skapats lokalt med en Cmdlet New-RemoteMailbox etableras för användaren.</span><span class="sxs-lookup"><span data-stu-id="bb872-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="bb872-147">Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan.</span><span class="sxs-lookup"><span data-stu-id="bb872-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="bb872-148">I det här fallet använder du sökrutan för att hitta användare eller redigera din anpassade vy för att förfina sökningen.</span><span class="sxs-lookup"><span data-stu-id="bb872-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="bb872-149">Skapa en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="bb872-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bb872-150">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="bb872-151">På sidan **Aktiva användare** väljer du **Filter** och väljer **Nytt filter**.</span><span class="sxs-lookup"><span data-stu-id="bb872-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="bb872-152">På sidan **Anpassad filter** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="bb872-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="bb872-153">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="bb872-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bb872-154">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="bb872-155">På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="bb872-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="bb872-156">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="bb872-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="bb872-157">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="bb872-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="bb872-158">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="bb872-159">På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="bb872-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="bb872-160">På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="bb872-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="bb872-161">Den anpassade vyn ingår nu i listrutan med filter.</span><span class="sxs-lookup"><span data-stu-id="bb872-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="bb872-162">Redigera eller ta bort en anpassad användarvy</span><span class="sxs-lookup"><span data-stu-id="bb872-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bb872-163">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="bb872-164">På sidan **Aktiva användare** väljer du **Filter,** markerar det filter som du vill ändra och väljer sedan **Redigera filter**.</span><span class="sxs-lookup"><span data-stu-id="bb872-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="bb872-165">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="bb872-166">På sidan **Anpassad filter** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bb872-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="bb872-167">Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="bb872-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bb872-168">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="bb872-169">På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter som du vill ändra och väljer sedan **Redigera den här vyn**.</span><span class="sxs-lookup"><span data-stu-id="bb872-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="bb872-170">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="bb872-171">På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bb872-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="bb872-172">Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="bb872-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bb872-173">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="bb872-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="bb872-174">På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter som du vill ändra och väljer sedan **Redigera den här vyn**.</span><span class="sxs-lookup"><span data-stu-id="bb872-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="bb872-175">Du kan bara redigera anpassade vyer.</span><span class="sxs-lookup"><span data-stu-id="bb872-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="bb872-176">På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bb872-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="bb872-177">Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort anpassad vy**.</span><span class="sxs-lookup"><span data-stu-id="bb872-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     