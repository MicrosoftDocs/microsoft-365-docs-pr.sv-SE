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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, kopplat till ditt Microsoft 365 för företagskonto. '
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048813"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="98558-103">Lägga till ytterligare ett e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="98558-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="98558-104">Den här artikeln är avsedd för Microsoft 365-administratörer som har företagsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="98558-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="98558-105">Den är inte avsedd för hemanvändare.</span><span class="sxs-lookup"><span data-stu-id="98558-105">It's not for home users.</span></span>
  
<span data-ttu-id="98558-106">En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som en användare tilldelades när deras konto skapades.</span><span class="sxs-lookup"><span data-stu-id="98558-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="98558-107">När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar.</span><span class="sxs-lookup"><span data-stu-id="98558-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="98558-108">De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företag-konto.</span><span class="sxs-lookup"><span data-stu-id="98558-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="98558-109">Dessa ytterligare adresser kallas alias.</span><span class="sxs-lookup"><span data-stu-id="98558-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="98558-110">Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också få e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet.</span><span class="sxs-lookup"><span data-stu-id="98558-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="98558-111">Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="98558-112">Du kan skapa upp till 400 alias för en användare.</span><span class="sxs-lookup"><span data-stu-id="98558-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="98558-113">Inga ytterligare avgifter eller licenser tillkommer.</span><span class="sxs-lookup"><span data-stu-id="98558-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="98558-114">Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress som info@NodPublishers.com eller sales@NodPublishers.com skapar du en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="98558-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="98558-115">Mer information finns i [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="98558-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="98558-116">Lägga till e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="98558-116">Add email aliases to a user</span></span>
<span data-ttu-id="98558-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="98558-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="98558-118">Du måste ha [administratörsbehörighet](../add-users/about-admin-roles.md) för att kunna göra detta.</span><span class="sxs-lookup"><span data-stu-id="98558-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98558-119">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="98558-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="98558-120">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="98558-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="98558-121">På sidan **Aktiva användare** väljer du användaren > **Hantera e-postalias**.</span><span class="sxs-lookup"><span data-stu-id="98558-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="98558-122">Det här alternativet visas inte om personen inte har tilldelats någon licens.</span><span class="sxs-lookup"><span data-stu-id="98558-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="98558-123">Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.</span><span class="sxs-lookup"><span data-stu-id="98558-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="98558-124">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="98558-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98558-125">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="98558-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98558-126">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="98558-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98558-127">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="98558-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="98558-128">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="98558-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98558-129">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="98558-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98558-130">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="98558-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="98558-131">När du är klar väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="98558-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="98558-132">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="98558-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="98558-133">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="98558-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98558-134">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98558-135">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="98558-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98558-136">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98558-137">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="98558-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="98558-138">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="98558-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="98558-139">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="98558-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="98558-140">Välj Redigera **bredvid Användarnamn/E-postalias** **.**</span><span class="sxs-lookup"><span data-stu-id="98558-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="98558-141">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="98558-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98558-142">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="98558-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98558-143">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="98558-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98558-144">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="98558-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="98558-145">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="98558-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="98558-146">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="98558-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="98558-147">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="98558-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98558-148">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="98558-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98558-149">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="98558-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98558-150">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="98558-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="98558-151">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98558-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="98558-152">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="98558-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="98558-153">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="98558-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98558-154">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98558-155">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="98558-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98558-156">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98558-157">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="98558-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98558-158">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="98558-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="98558-159">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="98558-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="98558-160">Välj Redigera **bredvid Användarnamn/E-postalias** **.**</span><span class="sxs-lookup"><span data-stu-id="98558-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="98558-161">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="98558-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98558-162">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="98558-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98558-163">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="98558-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98558-164">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="98558-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="98558-165">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="98558-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="98558-166">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="98558-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="98558-167">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="98558-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98558-168">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="98558-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="98558-169">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="98558-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="98558-170">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="98558-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="98558-171">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98558-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="98558-172">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="98558-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="98558-173">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="98558-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="98558-174">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="98558-175">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="98558-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="98558-176">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="98558-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="98558-177">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="98558-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="98558-178">Fick du "En parameter kan inte hittas som matchar parameternamnet EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="98558-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="98558-179">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet EmailAddresses**" betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="98558-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="98558-180">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="98558-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="98558-181">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="98558-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="98558-182">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="98558-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="98558-183">Har du köpt prenumerationen från GoDaddy eller från en annan partner?</span><span class="sxs-lookup"><span data-stu-id="98558-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="98558-184">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="98558-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="98558-185">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="98558-185">Related articles</span></span>

[<span data-ttu-id="98558-186">Skicka e-post från en annan adress</span><span class="sxs-lookup"><span data-stu-id="98558-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="98558-187">Ändra ett användarnamn och en e-postadress</span><span class="sxs-lookup"><span data-stu-id="98558-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

