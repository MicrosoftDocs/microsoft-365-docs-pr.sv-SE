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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, kopplat till ditt Microsoft 365 för företag-konto. '
ms.openlocfilehash: a44271cdbf52136e61702697a960cc3cbcd8119d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471007"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="4f7c3-103">Lägga till ytterligare ett e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="4f7c3-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="4f7c3-104">Den här artikeln är för Microsoft 365-administratörer som har företagsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="4f7c3-105">Den är inte avsedd för hemanvändare.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-105">It's not for home users.</span></span>
  
<span data-ttu-id="4f7c3-106">En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som användaren tilldelades när kontot skapades.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="4f7c3-107">När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="4f7c3-108">De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företag-konto.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="4f7c3-109">Dessa ytterligare adresser kallas alias.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="4f7c3-110">Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också ta emot e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="4f7c3-111">Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="4f7c3-112">Du kan skapa upp till 400 alias för en användare.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="4f7c3-113">Inga ytterligare avgifter eller licenser tillkommer.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="4f7c3-114">Om du vill att flera personer ska hantera e-post som skickas till en enskild e-postadress, info@NodPublishers.com eller sales@NodPublishers.com, kan du skapa en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="4f7c3-115">Mer information finns i Skapa [en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="4f7c3-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="4f7c3-116">Lägga till e-postalias för en användare</span><span class="sxs-lookup"><span data-stu-id="4f7c3-116">Add email aliases to a user</span></span>
<span data-ttu-id="4f7c3-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="4f7c3-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="4f7c3-118">Du måste ha [administratörsbehörighet för](../add-users/about-admin-roles.md) att göra detta.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4f7c3-119">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4f7c3-120">På sidan **Aktiva användare** väljer du den användare som > **hantera e-postalias**.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="4f7c3-121">Du ser inte det här alternativet om personen inte har någon tilldelad licens.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="4f7c3-122">Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="4f7c3-123">Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4f7c3-124">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4f7c3-125">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4f7c3-126">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="4f7c3-127">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4f7c3-128">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4f7c3-129">Om du vill lägga till ett annat domännamn i listan går du [till Lägga till en domän i Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="4f7c3-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="4f7c3-130">När du är klar väljer du **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="4f7c3-131">Vänta 24 timmar på att de nya alias aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="4f7c3-132">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4f7c3-133">Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4f7c3-134">**När användaren svarar kommer den adress som det *primära e-postaliaset*  att vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-134">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4f7c3-135">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4f7c3-136">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-136">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="4f7c3-137">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="4f7c3-138">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="4f7c3-139">Bredvid **Användarnamn/E-postalias** väljer du **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="4f7c3-140">Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4f7c3-141">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4f7c3-142">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4f7c3-143">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="4f7c3-144">I textrutan under **Alias skriver du** den första delen av det nya e-postaliaset.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="4f7c3-145">Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="4f7c3-146">Välj sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4f7c3-147">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4f7c3-148">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4f7c3-149">Om du vill lägga till ett annat domännamn i listan går du [till Lägga till en domän i Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="4f7c3-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="4f7c3-150">Välj Spara när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="4f7c3-151">Vänta 24 timmar på att de nya alias aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="4f7c3-152">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4f7c3-153">Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4f7c3-154">**När användaren svarar kommer den adress som det *primära e-postaliaset*  att vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-154">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4f7c3-155">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4f7c3-156">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-156">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4f7c3-157">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="4f7c3-158">På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="4f7c3-159">Bredvid **Användarnamn/E-postalias** väljer du **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="4f7c3-160">Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4f7c3-161">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4f7c3-162">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4f7c3-163">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="4f7c3-164">I textrutan under **Alias skriver du** den första delen av det nya e-postaliaset.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="4f7c3-165">Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="4f7c3-166">Välj sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4f7c3-167">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4f7c3-168">E-postaliaset måste sluta med en domän från listrutan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4f7c3-169">Om du vill lägga till ett annat domännamn i listan går du [till Lägga till en domän i Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="4f7c3-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="4f7c3-170">Välj Spara när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="4f7c3-171">Vänta 24 timmar på att de nya alias aliasen ska fyllas i i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="4f7c3-172">Användaren har nu en primär adress och ett alias.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4f7c3-173">Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4f7c3-174">**När användaren svarar kommer den adress som det *primära e-postaliaset*  att vara hennes primära e-postalias.**</span><span class="sxs-lookup"><span data-stu-id="4f7c3-174">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4f7c3-175">Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4f7c3-176">När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-176">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="4f7c3-177">Fick du meddelandet "Det hittades ingen parameter som matchar parameternamnet E-postadresser"?</span><span class="sxs-lookup"><span data-stu-id="4f7c3-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="4f7c3-178">Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet E-postadresser**" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4f7c3-179">Konfigurationen kan ta upp till 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4f7c3-180">Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4f7c3-181">Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="4f7c3-182">Har du köpt prenumerationen från GoDaddy eller från en annan partner?</span><span class="sxs-lookup"><span data-stu-id="4f7c3-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="4f7c3-183">Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.</span><span class="sxs-lookup"><span data-stu-id="4f7c3-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4f7c3-184">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4f7c3-184">Related articles</span></span>

[<span data-ttu-id="4f7c3-185">Skicka e-post från en annan adress</span><span class="sxs-lookup"><span data-stu-id="4f7c3-185">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="4f7c3-186">Ändra ett användarnamn och en e-postadress</span><span class="sxs-lookup"><span data-stu-id="4f7c3-186">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
