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
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140518"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="0c504-103">Lägga till ytterligare ett e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="0c504-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0c504-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="0c504-104">The admin center is changing.</span></span> <span data-ttu-id="0c504-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0c504-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="0c504-106">Den här artikeln är avsedd för Microsoft 365-administratörer som har företagsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="0c504-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="0c504-107">Den är inte avsedd för hemanvändare.</span><span class="sxs-lookup"><span data-stu-id="0c504-107">It's not for home users.</span></span>
  
<span data-ttu-id="0c504-108">En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som en användare tilldelades när deras konto skapades.</span><span class="sxs-lookup"><span data-stu-id="0c504-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="0c504-109">När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar.</span><span class="sxs-lookup"><span data-stu-id="0c504-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="0c504-110">De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företag-konto.</span><span class="sxs-lookup"><span data-stu-id="0c504-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="0c504-111">Dessa ytterligare adresser kallas alias.</span><span class="sxs-lookup"><span data-stu-id="0c504-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="0c504-112">Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också få e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet.</span><span class="sxs-lookup"><span data-stu-id="0c504-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="0c504-113">Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="0c504-114">Du kan skapa upp till 400 alias för en användare.</span><span class="sxs-lookup"><span data-stu-id="0c504-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="0c504-115">Inga ytterligare avgifter eller licenser tillkommer.</span><span class="sxs-lookup"><span data-stu-id="0c504-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="0c504-116">Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress som info@NodPublishers.com eller sales@NodPublishers.com skapar du en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="0c504-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="0c504-117">Mer information finns i [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="0c504-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="0c504-118">Lägga till e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="0c504-118">Add email aliases to a user</span></span>
<span data-ttu-id="0c504-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="0c504-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="0c504-120">Du måste ha [administratörsbehörighet](../add-users/about-admin-roles.md) för att kunna göra detta.</span><span class="sxs-lookup"><span data-stu-id="0c504-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0c504-121">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="0c504-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="0c504-122">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0c504-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0c504-123">På sidan **Aktiva användare** väljer du användaren > **Hantera e-postalias**.</span><span class="sxs-lookup"><span data-stu-id="0c504-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="0c504-124">Det här alternativet visas inte om personen inte har tilldelats någon licens.</span><span class="sxs-lookup"><span data-stu-id="0c504-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="0c504-125">Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.</span><span class="sxs-lookup"><span data-stu-id="0c504-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="0c504-126">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="0c504-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0c504-127">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="0c504-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0c504-128">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="0c504-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0c504-129">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="0c504-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="0c504-130">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="0c504-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0c504-131">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0c504-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0c504-132">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="0c504-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="0c504-133">När du är klar väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="0c504-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="0c504-134">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c504-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="0c504-135">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="0c504-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0c504-136">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0c504-137">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="0c504-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0c504-138">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0c504-139">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0c504-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="0c504-140">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0c504-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="0c504-141">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0c504-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="0c504-142">Välj Redigera **bredvid Användarnamn/E-postalias** **.**</span><span class="sxs-lookup"><span data-stu-id="0c504-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="0c504-143">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="0c504-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0c504-144">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="0c504-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0c504-145">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="0c504-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0c504-146">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="0c504-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="0c504-147">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="0c504-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="0c504-148">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="0c504-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="0c504-149">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0c504-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c504-150">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="0c504-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0c504-151">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0c504-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0c504-152">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="0c504-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="0c504-153">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0c504-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="0c504-154">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c504-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="0c504-155">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="0c504-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0c504-156">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0c504-157">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="0c504-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0c504-158">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0c504-159">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0c504-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c504-160">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="0c504-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="0c504-161">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="0c504-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="0c504-162">Välj Redigera **bredvid Användarnamn/E-postalias** **.**</span><span class="sxs-lookup"><span data-stu-id="0c504-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="0c504-163">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet 'EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="0c504-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0c504-164">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="0c504-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0c504-165">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="0c504-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0c504-166">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="0c504-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="0c504-167">Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.**</span><span class="sxs-lookup"><span data-stu-id="0c504-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="0c504-168">Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="0c504-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="0c504-169">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0c504-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c504-170">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="0c504-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="0c504-171">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="0c504-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="0c504-172">Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="0c504-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="0c504-173">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0c504-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="0c504-174">Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c504-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="0c504-175">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="0c504-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="0c504-176">Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="0c504-177">**När användaren svarar blir *Från-adressen* hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="0c504-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="0c504-178">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg.</span><span class="sxs-lookup"><span data-stu-id="0c504-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="0c504-179">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="0c504-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="0c504-180">Fick du "En parameter kan inte hittas som matchar parameternamnet EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="0c504-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="0c504-181">Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet EmailAddresses**" betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en.</span><span class="sxs-lookup"><span data-stu-id="0c504-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="0c504-182">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="0c504-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="0c504-183">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="0c504-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="0c504-184">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="0c504-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="0c504-185">Har du köpt prenumerationen från GoDaddy eller från en annan partner?</span><span class="sxs-lookup"><span data-stu-id="0c504-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="0c504-186">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="0c504-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="0c504-187">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="0c504-187">Related articles</span></span>

[<span data-ttu-id="0c504-188">Skicka e-post från en annan adress</span><span class="sxs-lookup"><span data-stu-id="0c504-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="0c504-189">Ändra ett användarnamn och en e-postadress</span><span class="sxs-lookup"><span data-stu-id="0c504-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

