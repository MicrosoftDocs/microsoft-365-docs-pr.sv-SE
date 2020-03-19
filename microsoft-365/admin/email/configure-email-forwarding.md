---
title: Konfigurera vidarebefordran av e-post i Office 365
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
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807872"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="a29b3-103">Konfigurera vidarebefordran av e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="a29b3-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="a29b3-p101">Som administratör för en Office 365-organisation kan du stöta på företagskrav för att konfigurera vidarebefordran av e-post för en användares brevlåda. Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="a29b3-p101">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="a29b3-106">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="a29b3-106">Configure email forwarding</span></span>

 <span data-ttu-id="a29b3-107">Innan du konfigurerar vidarebefordran av e-post bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="a29b3-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="a29b3-108">När du har konfigurerat vidarebefordran av e-post kommer endast **nya** e-postmeddelanden som skickas till *från* postlådan att användas.</span><span class="sxs-lookup"><span data-stu-id="a29b3-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="a29b3-109">Vidarebefordran av e-post kräver att *från-kontot* har en licens.</span><span class="sxs-lookup"><span data-stu-id="a29b3-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="a29b3-110">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="a29b3-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="a29b3-111">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="a29b3-111">This way several people can access it.</span></span> <span data-ttu-id="a29b3-112">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="a29b3-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="a29b3-113">Du måste vara Exchange-administratör eller global administratör i Office 365 för att kunna göra så här.</span><span class="sxs-lookup"><span data-stu-id="a29b3-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="a29b3-114">Mer information finns i avsnittet [Om administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a29b3-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="a29b3-115">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="a29b3-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="a29b3-116">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a29b3-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="a29b3-117">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="a29b3-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="a29b3-118">Välj **Hantera vidarebefordran av e-post**på fliken **E-post** .</span><span class="sxs-lookup"><span data-stu-id="a29b3-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="a29b3-119">På sidan vidarebefordran av e-post väljer du **Vidarebefordra alla e-postmeddelanden som skickas till den här postlådan,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a29b3-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a29b3-120">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="a29b3-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a29b3-121">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a29b3-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="a29b3-122">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="a29b3-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a29b3-123">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="a29b3-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="a29b3-124">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a29b3-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="a29b3-125">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="a29b3-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a29b3-126">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="a29b3-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="a29b3-127">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a29b3-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="a29b3-128">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="a29b3-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="a29b3-129">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .</span><span class="sxs-lookup"><span data-stu-id="a29b3-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="a29b3-130">På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a29b3-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a29b3-131">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="a29b3-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a29b3-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a29b3-132">Select **Save**.</span></span>
    
    <span data-ttu-id="a29b3-133">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="a29b3-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a29b3-134">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="a29b3-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="a29b3-135">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a29b3-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="a29b3-136">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="a29b3-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a29b3-137">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="a29b3-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="a29b3-138">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a29b3-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="a29b3-139">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="a29b3-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="a29b3-140">Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .</span><span class="sxs-lookup"><span data-stu-id="a29b3-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="a29b3-141">På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a29b3-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="a29b3-142">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="a29b3-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="a29b3-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a29b3-143">Select **Save**.</span></span>
    
    <span data-ttu-id="a29b3-144">**Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="a29b3-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="a29b3-145">Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="a29b3-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="a29b3-146">Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i det och ställ sedan in vidarebefordran för att peka på DL med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a29b3-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="a29b3-147">Ta inte bort kontot för den användare som skickar e-post till dig som vidarebefordrar eller tar bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="a29b3-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="a29b3-148">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="a29b3-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
