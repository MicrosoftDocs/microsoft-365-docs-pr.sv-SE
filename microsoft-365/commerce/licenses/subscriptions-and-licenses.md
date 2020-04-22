---
title: Förstå prenumerationer och licenser i Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: 'Lär dig mer om prenumerationer och licenser i Microsoft 365 för företag och vet vem som kan tilldela licenser och vad som händer när du tilldelar en licens till någon. '
ms.custom: okr_SMB
ms.openlocfilehash: 1508daa6dae30c35a9517fceb81b0a4d2b4a7f58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635442"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="bb3b2-103">Förstå prenumerationer och licenser i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="bb3b2-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="bb3b2-104">I den här artikeln beskrivs relationen mellan prenumerationer och licenser och ytterligare information om [vem som kan tilldela licenser,](#find-out-who-can-assign-licenses)förstå vad som händer när du [tilldelar en licens till någon](#understand-what-happens-when-you-assign-a-license-to-someone)och hur många enheter som kan installera Office [på](#how-many-devices-can-people-install-office-on).</span><span class="sxs-lookup"><span data-stu-id="bb3b2-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="bb3b2-105">Den innehåller också länkar till att [förstå licenser för postlådor som inte är användare](#understand-licenses-for-non-user-mailboxes)och artiklar om hur du hanterar [licenser](#articles-about-managing-licenses).</span><span class="sxs-lookup"><span data-stu-id="bb3b2-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="bb3b2-106">När du köper en prenumeration på Microsoft 365 för företag registrerar du dig för en uppsättning program och tjänster som du betalar för antingen månadsvis eller årsvis.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="bb3b2-107">Vilka program och tjänster du får som en del av prenumerationen beror på vilken produkt du har köpt, till exempel Microsoft 365 Apps for business eller Microsoft 365 Business Standard.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="bb3b2-108">Du kan granska vad som medföljer varje produkt på [sidan Köp Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span><span class="sxs-lookup"><span data-stu-id="bb3b2-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="bb3b2-109">När du köper en prenumeration anger du det antal licenser som du behöver, baserat på hur många personer som finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-109">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="bb3b2-110">Efter att köpet är klart skapar du konton för personerna och tilldelar en licens till var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-110">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="bb3b2-111">När dina organisationsbehov ändras kan du köpa fler licenser för att anpassa nya personer eller tilldela om licenser till andra användare när någon lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-111">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="bb3b2-112">Om du har mer än en prenumeration kan du tilldela licenser till olika personer för varje prenumeration.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-112">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="bb3b2-113">Alla användare kan till exempel tilldelas alla Microsoft 365-program och -tjänster som en del av en Microsoft 365 Business Standard-prenumeration, medan en delmängd användare också kan tilldelas Visio Online via en separat Visio-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-113">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="bb3b2-114">Ta reda på vem som kan tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="bb3b2-114">Find out who can assign licenses</span></span>

<span data-ttu-id="bb3b2-p105">Olika typer av administratörer kan arbeta med licenser på olika sätt beroende på deras respektive roller. I följande tabell finns de vanligaste alternativen. En fullständig lista över administrationsroller och behörigheter finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb3b2-p105">Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="bb3b2-118">**Administratörsroller**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-118">**Admin role**</span></span>|<span data-ttu-id="bb3b2-119">**Tilldela en licens**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-119">**Assign a license**</span></span>|<span data-ttu-id="bb3b2-120">**Ta bort en licens**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-120">**Remove a license**</span></span>|<span data-ttu-id="bb3b2-121">**Köp flera licenser**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-121">**Purchase more licenses**</span></span>|<span data-ttu-id="bb3b2-122">**Ta bort ett konto**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-122">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb3b2-123">Global administratör</span><span class="sxs-lookup"><span data-stu-id="bb3b2-123">Global admin</span></span>  <br/> |<span data-ttu-id="bb3b2-124">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-124">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-125">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-125">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-126">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-126">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-127">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-127">Yes</span></span>  <br/> |
|<span data-ttu-id="bb3b2-128">Faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="bb3b2-128">Billing admin</span></span>  <br/> |<span data-ttu-id="bb3b2-129">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-129">No</span></span>  <br/> |<span data-ttu-id="bb3b2-130">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-130">No</span></span>  <br/> |<span data-ttu-id="bb3b2-131">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-131">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-132">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-132">No</span></span>  <br/> |
|<span data-ttu-id="bb3b2-133">Användarhanteringsadministratör</span><span class="sxs-lookup"><span data-stu-id="bb3b2-133">User management admin</span></span>  <br/> |<span data-ttu-id="bb3b2-134">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-134">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-135">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-135">Yes</span></span>  <br/> |<span data-ttu-id="bb3b2-136">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-136">No</span></span>  <br/> |<span data-ttu-id="bb3b2-137">Ja</span><span class="sxs-lookup"><span data-stu-id="bb3b2-137">Yes</span></span>  <br/> |
|<span data-ttu-id="bb3b2-138">Tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="bb3b2-138">Service admin</span></span>  <br/> |<span data-ttu-id="bb3b2-139">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-139">No</span></span>  <br/> |<span data-ttu-id="bb3b2-140">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-140">No</span></span>  <br/> |<span data-ttu-id="bb3b2-141">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-141">No</span></span>  <br/> |<span data-ttu-id="bb3b2-142">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-142">No</span></span>  <br/> |
|<span data-ttu-id="bb3b2-143">Lösenordsadministratör</span><span class="sxs-lookup"><span data-stu-id="bb3b2-143">Password admin</span></span>  <br/> |<span data-ttu-id="bb3b2-144">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-144">No</span></span>  <br/> |<span data-ttu-id="bb3b2-145">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-145">No</span></span>  <br/> |<span data-ttu-id="bb3b2-146">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-146">No</span></span>  <br/> |<span data-ttu-id="bb3b2-147">Nej</span><span class="sxs-lookup"><span data-stu-id="bb3b2-147">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="bb3b2-148">Förstå vad som händer när du tilldelar en licens till någon</span><span class="sxs-lookup"><span data-stu-id="bb3b2-148">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="bb3b2-149">I följande tabell anges vad som sker automatiskt när du tilldelar en licens till en person:</span><span class="sxs-lookup"><span data-stu-id="bb3b2-149">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="bb3b2-150">**Om prenumerationen har den här tjänsten**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-150">**If the subscription has this service**</span></span>|<span data-ttu-id="bb3b2-151">**sker detta automatiskt**</span><span class="sxs-lookup"><span data-stu-id="bb3b2-151">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb3b2-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bb3b2-152">Exchange Online</span></span>  <br/> |<span data-ttu-id="bb3b2-153">En postlåda skapas för den personen.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-153">A mailbox is created for that person.</span></span>  <br/> |
|<span data-ttu-id="bb3b2-154">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3b2-154">SharePoint Online</span></span>  <br/> |<span data-ttu-id="bb3b2-155">Personen tilldelas redigeringsbehörigheter på SharePoint Online-standardgruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-155">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="bb3b2-156">Skype för företag - Online</span><span class="sxs-lookup"><span data-stu-id="bb3b2-156">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="bb3b2-157">Personen får åtkomst till de funktioner som är kopplade till licensen.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-157">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="bb3b2-158">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="bb3b2-158">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="bb3b2-159">Personen kan ladda ned Microsoft Office på upp till 5 Mac- eller PC-datorer, 5 surfplattor och 5 smartphones.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-159">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="bb3b2-160">Hur många enheter går det att installera Office på?</span><span class="sxs-lookup"><span data-stu-id="bb3b2-160">How many devices can people install Office on?</span></span>

<span data-ttu-id="bb3b2-161">Om prenumerationen innehåller någon av följande produkter kan varje person installera Office på upp till 5 PC- eller Mac-datorer, 5 surfplattor och 5 telefoner.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-161">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="bb3b2-162">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="bb3b2-162">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="bb3b2-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="bb3b2-163">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="bb3b2-164">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="bb3b2-164">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="bb3b2-165">Office 365 Enterprise, E3</span><span class="sxs-lookup"><span data-stu-id="bb3b2-165">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="bb3b2-166">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="bb3b2-166">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="bb3b2-167">Allmänt om licenser för postlådor som inte är kopplade till någon användare</span><span class="sxs-lookup"><span data-stu-id="bb3b2-167">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="bb3b2-p106">Du behöver inte tilldela licenser till resurspostlådor, rumspostlådor och delade postlådor, förutom när de är över sin lagringskvot på 50 GB. Mer information om postlådor som inte är kopplade till någon användare finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="bb3b2-p106">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="bb3b2-170">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="bb3b2-170">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="bb3b2-171">[Delade postlådor i Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) för alla andra Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-171">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="bb3b2-172">Skapa och hantera rumspostlådor</span><span class="sxs-lookup"><span data-stu-id="bb3b2-172">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="bb3b2-173">Hantera utrustningspostlådor</span><span class="sxs-lookup"><span data-stu-id="bb3b2-173">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="bb3b2-174">Artiklar om hantering av licenser</span><span class="sxs-lookup"><span data-stu-id="bb3b2-174">Articles about managing licenses</span></span>

- [<span data-ttu-id="bb3b2-175">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="bb3b2-175">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="bb3b2-176">Ta bort licenser från användare</span><span class="sxs-lookup"><span data-stu-id="bb3b2-176">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="bb3b2-177">Köpa licenser för prenumerationen</span><span class="sxs-lookup"><span data-stu-id="bb3b2-177">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="bb3b2-178">Köpa en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="bb3b2-178">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="bb3b2-179">Köpa eller redigera ett tillägg</span><span class="sxs-lookup"><span data-stu-id="bb3b2-179">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="bb3b2-180">Ta bort licenser från prenumerationen</span><span class="sxs-lookup"><span data-stu-id="bb3b2-180">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="bb3b2-181">Lösa licenskonflikter</span><span class="sxs-lookup"><span data-stu-id="bb3b2-181">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="bb3b2-182">Hantera Yammer-användarlicenser</span><span class="sxs-lookup"><span data-stu-id="bb3b2-182">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
