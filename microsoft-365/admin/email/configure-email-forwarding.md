---
title: Konfigurera vidarebefordran av e-post
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med Office365.
ms.openlocfilehash: 8cd86bcab4d73719e527f9942cd41a3174966c2d
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140459"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="fe783-103">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="fe783-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fe783-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="fe783-104">The admin center is changing.</span></span> <span data-ttu-id="fe783-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fe783-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="fe783-106">Som administratör för en organisation kan du ha företagskrav för att konfigurera vidarebefordran av e-post för en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="fe783-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="fe783-107">Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe783-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="fe783-108">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="fe783-108">Configure email forwarding</span></span>

 <span data-ttu-id="fe783-109">Innan du konfigurerar vidarebefordran av e-post bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="fe783-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="fe783-110">När du har konfigurerat vidarebefordran av e-post kommer endast **nya** e-postmeddelanden som skickas till *från* postlådan att användas.</span><span class="sxs-lookup"><span data-stu-id="fe783-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="fe783-111">Vidarebefordran av e-post kräver att *från-kontot* har en licens.</span><span class="sxs-lookup"><span data-stu-id="fe783-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="fe783-112">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="fe783-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="fe783-113">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="fe783-113">This way several people can access it.</span></span> <span data-ttu-id="fe783-114">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="fe783-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="fe783-115">Du måste vara Exchange-administratör eller Global administratör i Microsoft 365 för att kunna göra så här.</span><span class="sxs-lookup"><span data-stu-id="fe783-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="fe783-116">Mer information finns i avsnittet [Om administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fe783-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="fe783-117">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="fe783-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="fe783-118">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="fe783-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="fe783-119">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="fe783-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="fe783-120">Välj **Hantera vidarebefordran av e-post**på fliken **E-post** .</span><span class="sxs-lookup"><span data-stu-id="fe783-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="fe783-121">På sidan vidarebefordran av e-post väljer du **Vidarebefordra alla e-postmeddelanden som skickas till den här postlådan,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fe783-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fe783-122">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="fe783-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fe783-123">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="fe783-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="fe783-124">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="fe783-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fe783-125">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fe783-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fe783-126">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fe783-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fe783-127">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="fe783-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fe783-128">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="fe783-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="fe783-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="fe783-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fe783-130">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="fe783-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fe783-131">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .</span><span class="sxs-lookup"><span data-stu-id="fe783-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fe783-132">På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fe783-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fe783-133">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="fe783-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fe783-134">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fe783-134">Select **Save**.</span></span>
    
    <span data-ttu-id="fe783-135">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="fe783-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fe783-136">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fe783-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fe783-137">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fe783-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fe783-138">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="fe783-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fe783-139">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="fe783-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="fe783-140">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="fe783-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="fe783-141">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="fe783-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="fe783-142">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .</span><span class="sxs-lookup"><span data-stu-id="fe783-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fe783-143">På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fe783-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fe783-144">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="fe783-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fe783-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fe783-145">Select **Save**.</span></span>
    
    <span data-ttu-id="fe783-146">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="fe783-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fe783-147">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fe783-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="fe783-148">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fe783-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="fe783-149">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="fe783-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fe783-150">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="fe783-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
