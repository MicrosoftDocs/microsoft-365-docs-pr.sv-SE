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
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, kopplat till ditt Microsoft 365 för företagskonto. '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780295"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="a77d3-103">Lägga till ytterligare ett e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="a77d3-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a77d3-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="a77d3-104">The admin center is changing.</span></span> <span data-ttu-id="a77d3-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a77d3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="a77d3-106">Den här artikeln är avsedd för Microsoft 365-administratörer som har företagsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="a77d3-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="a77d3-107">Den är inte avsedd för hemanvändare.</span><span class="sxs-lookup"><span data-stu-id="a77d3-107">It's not for home users.</span></span>
  
<span data-ttu-id="a77d3-108">En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som en användare tilldelades när deras konto skapades.</span><span class="sxs-lookup"><span data-stu-id="a77d3-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="a77d3-109">När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar.</span><span class="sxs-lookup"><span data-stu-id="a77d3-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="a77d3-110">De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företagskonto.</span><span class="sxs-lookup"><span data-stu-id="a77d3-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="a77d3-111">Dessa ytterligare adresser kallas alias.</span><span class="sxs-lookup"><span data-stu-id="a77d3-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="a77d3-112">Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också få e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet.</span><span class="sxs-lookup"><span data-stu-id="a77d3-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="a77d3-113">Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="a77d3-114">Du kan skapa upp till 400 alias för en användare.</span><span class="sxs-lookup"><span data-stu-id="a77d3-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="a77d3-115">Inga ytterligare avgifter eller licenser tillkommer.</span><span class="sxs-lookup"><span data-stu-id="a77d3-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="a77d3-116">Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress som info@NodPublishers.com eller sales@NodPublishers.com skapar du en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="a77d3-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="a77d3-117">Mer information finns i [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="a77d3-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="a77d3-118">Lägga till e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="a77d3-118">Add email aliases to a user</span></span>
<span data-ttu-id="a77d3-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="a77d3-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="a77d3-120">Du måste ha [administratörsbehörighet](../add-users/about-admin-roles.md) för att kunna göra detta.</span><span class="sxs-lookup"><span data-stu-id="a77d3-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="a77d3-121">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a77d3-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a77d3-122">På sidan **Aktiva användare** väljer du användaren > **Hantera e-postalias**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="a77d3-123">Det här alternativet visas inte om personen inte har tilldelats någon licens.</span><span class="sxs-lookup"><span data-stu-id="a77d3-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="a77d3-124">Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.</span><span class="sxs-lookup"><span data-stu-id="a77d3-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="a77d3-125">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="a77d3-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="a77d3-126">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="a77d3-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="a77d3-127">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="a77d3-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="a77d3-128">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="a77d3-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="a77d3-129">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="a77d3-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="a77d3-130">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a77d3-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="a77d3-131">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="a77d3-131">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="a77d3-132">När du är klar väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="a77d3-133">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="a77d3-133">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="a77d3-134">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="a77d3-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="a77d3-135">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="a77d3-136">**När användaren svarar blir *från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="a77d3-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="a77d3-137">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="a77d3-138">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="a77d3-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="a77d3-139">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a77d3-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="a77d3-140">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a77d3-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="a77d3-141">Välj **Redigera** **bredvid Användarnamn/E-postalias**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="a77d3-142">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="a77d3-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="a77d3-143">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="a77d3-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="a77d3-144">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="a77d3-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="a77d3-145">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="a77d3-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="a77d3-146">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="a77d3-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="a77d3-147">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="a77d3-147">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="a77d3-148">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a77d3-149">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="a77d3-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="a77d3-150">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a77d3-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="a77d3-151">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="a77d3-151">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="a77d3-152">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="a77d3-153">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="a77d3-153">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="a77d3-154">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="a77d3-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="a77d3-155">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="a77d3-156">**När användaren svarar blir *från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="a77d3-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="a77d3-157">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="a77d3-158">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="a77d3-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a77d3-159">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="a77d3-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="a77d3-160">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="a77d3-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="a77d3-161">Välj **Redigera** **bredvid Användarnamn/E-postalias**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="a77d3-162">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="a77d3-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="a77d3-163">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="a77d3-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="a77d3-164">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="a77d3-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="a77d3-165">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="a77d3-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="a77d3-166">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="a77d3-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="a77d3-167">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="a77d3-167">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="a77d3-168">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a77d3-169">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="a77d3-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="a77d3-170">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a77d3-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="a77d3-171">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="a77d3-171">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="a77d3-172">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a77d3-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="a77d3-173">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="a77d3-173">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="a77d3-174">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="a77d3-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="a77d3-175">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="a77d3-176">**När användaren svarar blir *från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="a77d3-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="a77d3-177">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="a77d3-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="a77d3-178">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="a77d3-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="a77d3-179">Fick du "En parameter kan inte hittas som matchar parameternamnet EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="a77d3-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="a77d3-180">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet EmailAddresses**" betyder det att det tar lite längre tid att slutföra inrättandet av din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="a77d3-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="a77d3-181">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="a77d3-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="a77d3-182">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="a77d3-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="a77d3-183">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="a77d3-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="a77d3-184">Har du köpt prenumerationen från GoDaddy eller från en annan partner?</span><span class="sxs-lookup"><span data-stu-id="a77d3-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="a77d3-185">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="a77d3-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="a77d3-186">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a77d3-186">Related articles</span></span>

[<span data-ttu-id="a77d3-187">Skicka e-post från en annan adress</span><span class="sxs-lookup"><span data-stu-id="a77d3-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="a77d3-188">Ändra ett användarnamn och en e-postadress</span><span class="sxs-lookup"><span data-stu-id="a77d3-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

