---
title: Konfigurera vidarebefordran av e-post
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med Office365.
ms.openlocfilehash: d19e2c533be6fac927bdf2aa65d72acab9fad6f6
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645533"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="e2971-103">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="e2971-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e2971-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="e2971-104">The admin center is changing.</span></span> <span data-ttu-id="e2971-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e2971-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="e2971-106">Som administratör för en organisation kan du ha företags krav för att konfigurera e-postvidarekoppling för en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="e2971-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="e2971-107">Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="e2971-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="e2971-108">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="e2971-108">Configure email forwarding</span></span>

 <span data-ttu-id="e2971-109">Observera följande innan du konfigurerar e-postvidarebefordran:</span><span class="sxs-lookup"><span data-stu-id="e2971-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="e2971-110">När du har konfigurerat e-postvidarebefordran blir bara **nya** e-postmeddelanden som skickas till  *från*  -post lådan vidare.</span><span class="sxs-lookup"><span data-stu-id="e2971-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="e2971-111">För e-postvidarekoppling krävs det att  *from*  -kontot har en licens.</span><span class="sxs-lookup"><span data-stu-id="e2971-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="e2971-112">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e2971-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="e2971-113">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="e2971-113">This way several people can access it.</span></span> <span data-ttu-id="e2971-114">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="e2971-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="e2971-115">Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="e2971-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="e2971-116">Mer information finns i avsnittet [om administratörs roller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e2971-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2971-117">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="e2971-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="e2971-118">Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.</span><span class="sxs-lookup"><span data-stu-id="e2971-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="e2971-119">Välj **Hantera e-postvidarebefordran**på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="e2971-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="e2971-120">På sidan e-postchatt väljer du **vidarebefordra alla e-postmeddelanden som skickas till den här post lådan**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e2971-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e2971-121">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="e2971-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e2971-122">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="e2971-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="e2971-123">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna.</span><span class="sxs-lookup"><span data-stu-id="e2971-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e2971-124">Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e2971-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e2971-125">Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e2971-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e2971-126">Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!</span><span class="sxs-lookup"><span data-stu-id="e2971-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e2971-127">Om du gör det stoppas e-postvidarekoppling.</span><span class="sxs-lookup"><span data-stu-id="e2971-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="e2971-128">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="e2971-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="e2971-129">Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.</span><span class="sxs-lookup"><span data-stu-id="e2971-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="e2971-130">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **e-postvidarebefordran** .</span><span class="sxs-lookup"><span data-stu-id="e2971-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e2971-131">På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e2971-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e2971-132">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="e2971-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e2971-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e2971-133">Select **Save**.</span></span>
    
    <span data-ttu-id="e2971-134">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna.</span><span class="sxs-lookup"><span data-stu-id="e2971-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e2971-135">Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e2971-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e2971-136">Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e2971-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e2971-137">Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!</span><span class="sxs-lookup"><span data-stu-id="e2971-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e2971-138">Om du gör det stoppas e-postvidarekoppling.</span><span class="sxs-lookup"><span data-stu-id="e2971-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="e2971-139">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="e2971-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="e2971-140">Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.</span><span class="sxs-lookup"><span data-stu-id="e2971-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="e2971-141">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **e-postvidarebefordran** .</span><span class="sxs-lookup"><span data-stu-id="e2971-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e2971-142">På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e2971-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e2971-143">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="e2971-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e2971-144">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e2971-144">Select **Save**.</span></span>
    
    <span data-ttu-id="e2971-145">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna.</span><span class="sxs-lookup"><span data-stu-id="e2971-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e2971-146">Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e2971-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="e2971-147">Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e2971-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="e2971-148">Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!</span><span class="sxs-lookup"><span data-stu-id="e2971-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e2971-149">Om du gör det stoppas e-postvidarekoppling.</span><span class="sxs-lookup"><span data-stu-id="e2971-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
