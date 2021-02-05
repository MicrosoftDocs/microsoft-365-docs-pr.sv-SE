---
title: Lägga till ytterligare ett e-postalias för en användare
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Lär dig hur du kan ha fler än en e-postadress, ett så kallat e-postalias, som är kopplat till ditt Microsoft 365 för företag-konto. '
ms.openlocfilehash: afb576a0499577b910fe3ed14eff75ae0a52b394
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114039"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="9914b-103">Lägga till ytterligare ett e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="9914b-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9914b-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="9914b-104">The admin center is changing.</span></span> <span data-ttu-id="9914b-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9914b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
<span data-ttu-id="9914b-106">Den här artikeln är för Microsoft 365-administratörer som har företagsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="9914b-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="9914b-107">Den är inte avsedd för hemanvändare.</span><span class="sxs-lookup"><span data-stu-id="9914b-107">It's not for home users.</span></span>
  
<span data-ttu-id="9914b-108">En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som användaren tilldelades när sitt konto skapades.</span><span class="sxs-lookup"><span data-stu-id="9914b-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="9914b-109">När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar.</span><span class="sxs-lookup"><span data-stu-id="9914b-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="9914b-110">De kan också ha fler än en e-postadress kopplad till sitt Microsoft 365 för företag-konto.</span><span class="sxs-lookup"><span data-stu-id="9914b-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="9914b-111">Dessa ytterligare adresser kallas alias.</span><span class="sxs-lookup"><span data-stu-id="9914b-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="9914b-112">Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också ta emot e-post på jen@contosoco.com eftersom vissa refererar till henne med det namnet.</span><span class="sxs-lookup"><span data-stu-id="9914b-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="9914b-113">Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="9914b-114">Du kan skapa upp till 400 alias för en användare.</span><span class="sxs-lookup"><span data-stu-id="9914b-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="9914b-115">Inga ytterligare avgifter eller licenser tillkommer.</span><span class="sxs-lookup"><span data-stu-id="9914b-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="9914b-116">Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress, till info@NodPublishers.com eller sales@NodPublishers.com, skapar du en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="9914b-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="9914b-117">Mer information finns i Skapa [en delad postlåda.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9914b-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="9914b-118">Lägga till e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="9914b-118">Add email aliases to a user</span></span>
<span data-ttu-id="9914b-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="9914b-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="9914b-120">Du måste ha [administratörsbehörighet för](../add-users/about-admin-roles.md) att göra detta.</span><span class="sxs-lookup"><span data-stu-id="9914b-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="9914b-121">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="9914b-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="9914b-122">På sidan **Aktiva användare** väljer du den användare som > **Hantera e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="9914b-123">Du ser inte det här alternativet om personen inte har någon tilldelad licens.</span><span class="sxs-lookup"><span data-stu-id="9914b-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="9914b-124">Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.</span><span class="sxs-lookup"><span data-stu-id="9914b-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="9914b-125">Om du får felmeddelandet " Det går inte att hitta en parameter som matchar **parameternamnet 'E-postadresser'"** innebär det att det tar lite längre tid att slutföra klientorganisationen, eller den anpassade domänen om du nyligen har lagt till en.</span><span class="sxs-lookup"><span data-stu-id="9914b-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="9914b-126">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="9914b-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="9914b-127">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="9914b-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="9914b-128">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="9914b-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="9914b-129">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="9914b-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="9914b-130">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="9914b-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="9914b-131">Information om hur du lägger till ett annat domännamn i listan [finns i Lägga till en domän i Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="9914b-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="9914b-132">Välj Spara ändringar när du **är klar.**</span><span class="sxs-lookup"><span data-stu-id="9914b-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="9914b-133">Vänta 24 timmar för att de nya aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9914b-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="9914b-134">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="9914b-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="9914b-135">Till exempel skickas all e-post till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="9914b-136">**När användaren svarar kommer *från-adressen att*  vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="9914b-137">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="9914b-138">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="9914b-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="9914b-139">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="9914b-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="9914b-140">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="9914b-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="9914b-141">Välj **Redigera** **bredvid användarnamn/e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="9914b-142">Om du får felmeddelandet " Det går inte att hitta en parameter som matchar **parameternamnet 'E-postadresser'"** innebär det att det tar lite längre tid att slutföra klientorganisationen, eller den anpassade domänen om du nyligen har lagt till en.</span><span class="sxs-lookup"><span data-stu-id="9914b-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="9914b-143">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="9914b-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="9914b-144">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="9914b-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="9914b-145">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="9914b-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="9914b-146">I textrutan under **Alias skriver** du den första delen av det nya e-postaliaset.</span><span class="sxs-lookup"><span data-stu-id="9914b-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="9914b-147">Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="9914b-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="9914b-148">Välj sedan **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="9914b-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9914b-149">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="9914b-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="9914b-150">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="9914b-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="9914b-151">Information om hur du lägger till ett annat domännamn i listan [finns i Lägga till en domän i Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="9914b-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="9914b-152">Välj Spara när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="9914b-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="9914b-153">Vänta 24 timmar för att de nya aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9914b-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="9914b-154">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="9914b-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="9914b-155">Till exempel kommer all e-post som skickats till ErnaCks primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="9914b-156">**När användaren svarar kommer *från-adressen att*  vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="9914b-157">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="9914b-158">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="9914b-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9914b-159">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="9914b-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="9914b-160">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="9914b-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="9914b-161">Välj **Redigera** **bredvid användarnamn/e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="9914b-162">Om du får felmeddelandet " Det går inte att hitta en parameter som matchar **parameternamnet 'E-postadresser'"** innebär det att det tar lite längre tid att slutföra klientorganisationen, eller den anpassade domänen om du nyligen har lagt till en.</span><span class="sxs-lookup"><span data-stu-id="9914b-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="9914b-163">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="9914b-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="9914b-164">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="9914b-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="9914b-165">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="9914b-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="9914b-166">I textrutan under **Alias skriver** du den första delen av det nya e-postaliaset.</span><span class="sxs-lookup"><span data-stu-id="9914b-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="9914b-167">Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="9914b-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="9914b-168">Välj sedan **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="9914b-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9914b-169">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="9914b-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="9914b-170">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="9914b-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="9914b-171">Information om hur du lägger till ett annat domännamn i listan [finns i Lägga till en domän i Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="9914b-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="9914b-172">Välj Spara när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="9914b-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="9914b-173">Vänta 24 timmar för att de nya aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9914b-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="9914b-174">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="9914b-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="9914b-175">Till exempel skickas all e-post till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="9914b-176">**När användaren svarar kommer *från-adressen att*  vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="9914b-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="9914b-177">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="9914b-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="9914b-178">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="9914b-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="9914b-179">Fick du meddelandet "Det hittades ingen parameter som matchar parameternamnet E-postadresser"?</span><span class="sxs-lookup"><span data-stu-id="9914b-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="9914b-180">Om du får felmeddelandet " Det gick inte att hitta en parameter som matchar **parameternamnet E-postadresser**" innebär det att det tar lite längre tid att slutföra klientorganisationen, eller den anpassade domänen om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="9914b-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="9914b-181">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="9914b-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="9914b-182">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="9914b-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="9914b-183">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="9914b-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="9914b-184">Har du köpt prenumerationen från GoDaddy eller från en annan partner?</span><span class="sxs-lookup"><span data-stu-id="9914b-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="9914b-185">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="9914b-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="9914b-186">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9914b-186">Related articles</span></span>

[<span data-ttu-id="9914b-187">Skicka e-post från en annan adress</span><span class="sxs-lookup"><span data-stu-id="9914b-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="9914b-188">Ändra ett användarnamn och en e-postadress</span><span class="sxs-lookup"><span data-stu-id="9914b-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

