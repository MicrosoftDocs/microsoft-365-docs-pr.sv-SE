---
title: Lägga till användare individuellt eller i grupp
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Lär dig hur du lägger till användare i Microsoft 365, en i taget eller flera användare samtidigt från en CSV-fil.
ms.openlocfilehash: af160b78317171bec98dcfa3d5877b53560f75a2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780667"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="06579-103">Lägga till användare individuellt eller i grupp</span><span class="sxs-lookup"><span data-stu-id="06579-103">Add users individually or in bulk</span></span>

<span data-ttu-id="06579-104">Personerna i teamet behöver var och en ett användarkonto innan de kan logga in och komma åt [Microsoft 365 för företag](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="06579-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="06579-105">Det enklaste sättet att lägga till användarkonton är att lägga till dem en i taget i Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="06579-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="06579-106">När du har gjort det här steget har användarna Microsoft 365-licenser, inloggningsuppgifter och Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="06579-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="06579-107">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="06579-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="06579-108">Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.</span><span class="sxs-lookup"><span data-stu-id="06579-108">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="06579-109">I fönstret **Konfigurera grunderna** fyller du i följande information och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="06579-109">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="06579-110">**Namn** Fyll i först, sist, visningsnamn och användarnamn.</span><span class="sxs-lookup"><span data-stu-id="06579-110">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="06579-111">**Domän** Om användarens användarnamn till exempel är Jakob och hans domän är contoso.com loggar han in på genom att skriva jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06579-111">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="06579-112">**Inställningar för lösenord** Välj att använda automatiskt genererat lösenord eller skapa ditt eget starka lösenord för användaren.</span><span class="sxs-lookup"><span data-stu-id="06579-112">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="06579-113">Användaren måste ändra sitt lösenord efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="06579-113">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="06579-114">Du kan också välja att **kräva att användaren ändrar sitt lösenord när de loggar in för första gången.**</span><span class="sxs-lookup"><span data-stu-id="06579-114">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="06579-115">Välj om du vill skicka lösenordet via e-post när användaren har lagts till.</span><span class="sxs-lookup"><span data-stu-id="06579-115">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="06579-116">I fönstret **Tilldela produktlicenser** väljer du platsen och lämplig licens för användaren.</span><span class="sxs-lookup"><span data-stu-id="06579-116">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="06579-117">Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser.</span><span class="sxs-lookup"><span data-stu-id="06579-117">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="06579-118">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="06579-118">Select **Next**.</span></span>

5. <span data-ttu-id="06579-119">På sidan **Valfria inställningar** expanderar du **Roller** om du vill göra den här användaren till administratör och expanderar **profilinformation** om du vill lägga till ytterligare information om användaren.</span><span class="sxs-lookup"><span data-stu-id="06579-119">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="06579-120">Välj **Nästa**, granska den nya användarens inställningar, gör de ändringar du vill och välj sedan **Slutför att lägga till**.</span><span class="sxs-lookup"><span data-stu-id="06579-120">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="06579-121">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="06579-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="06579-122">Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.</span><span class="sxs-lookup"><span data-stu-id="06579-122">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="06579-123">Fyll i följande information i fönstret **Nytt användar.**</span><span class="sxs-lookup"><span data-stu-id="06579-123">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="06579-124">Välj **Lägg till** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="06579-124">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="06579-125">**Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.</span><span class="sxs-lookup"><span data-stu-id="06579-125">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="06579-126">**Domän** Om användarens användarnamn till exempel är Jakob och hans domän är contoso.com loggar han in på genom att skriva jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06579-126">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="06579-127">**Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.</span><span class="sxs-lookup"><span data-stu-id="06579-127">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="06579-128">**Lösenord** Använd det automatiskt genererade lösenordet eller expandera det här avsnittet om du vill ange ett starkt lösenord för användaren.</span><span class="sxs-lookup"><span data-stu-id="06579-128">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="06579-129">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="06579-129">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="06579-130">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="06579-130">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="06579-131">**Roller** Expandera det här avsnittet om du vill göra användaren till administratör.</span><span class="sxs-lookup"><span data-stu-id="06579-131">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="06579-132">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="06579-132">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="06579-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="06579-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="06579-134">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="06579-134">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="06579-135">Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.</span><span class="sxs-lookup"><span data-stu-id="06579-135">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="06579-136">Fyll i följande information i fönstret **Nytt användar.**</span><span class="sxs-lookup"><span data-stu-id="06579-136">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="06579-137">Välj **Lägg till** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="06579-137">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="06579-138">**Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.</span><span class="sxs-lookup"><span data-stu-id="06579-138">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="06579-139">**Domän** Om användarens användarnamn till exempel är Jakob och hans domän är contoso.com loggar han in på genom att skriva jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06579-139">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="06579-140">**Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.</span><span class="sxs-lookup"><span data-stu-id="06579-140">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="06579-141">**Lösenord** Använd det automatiskt genererade lösenordet eller expandera det här avsnittet om du vill ange ett starkt lösenord för användaren.</span><span class="sxs-lookup"><span data-stu-id="06579-141">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="06579-142">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="06579-142">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="06579-143">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="06579-143">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="06579-144">**Roller** Expandera det här avsnittet om du vill göra användaren till administratör.</span><span class="sxs-lookup"><span data-stu-id="06579-144">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="06579-145">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="06579-145">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="06579-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="06579-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="06579-147">När du lägger till en användare får du ett e-postmeddelande från Microsoft Online Services-teamet.</span><span class="sxs-lookup"><span data-stu-id="06579-147">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="06579-148">E-postmeddelandet innehåller personens användar-ID och lösenord så att de kan logga in på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06579-148">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="06579-149">Du måste berätta för din nya användare om deras inloggningsinformation för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06579-149">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="06579-150">Använd din vanliga process för att förmedla nya lösenord.</span><span class="sxs-lookup"><span data-stu-id="06579-150">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="06579-151">Om du skapar användare genom att migrera e-postlådor måste du aktivera användarkonton genom att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="06579-151">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="06579-152">Om du inte tilldelar en licens till en användare inaktiveras postlådan efter en respitperiod på 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="06579-152">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="06579-153">Lär dig hur [du tilldelar licenser till användare](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) som använder Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="06579-153">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="06579-154">Video: Lägga till och hantera användare i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="06579-154">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="06579-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="06579-155">Next steps</span></span>

<span data-ttu-id="06579-156">Dela [snabbstartsguiden för anställda](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) med dina nya användare för att konfigurera t.ex. [Office på en PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och [Office-mobilappar](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="06579-156">Share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set things up, like [Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [Office mobile apps](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="06579-157">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="06579-157">Need help?</span></span>

<span data-ttu-id="06579-158">[Kontakta Microsoft 365 för företagssupport](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="06579-158">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="06579-159">Har du hundratals eller tusentals användare som ska läggas till?</span><span class="sxs-lookup"><span data-stu-id="06579-159">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="06579-160">Använd följande steg om du vill lägga till flera användare samtidigt:</span><span class="sxs-lookup"><span data-stu-id="06579-160">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="06579-161">**Lägga till användare i grupp med hjälp av ett kalkylblad.**</span><span class="sxs-lookup"><span data-stu-id="06579-161">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="06579-162">Se [Lägga till flera användare samtidigt](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="06579-162">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="06579-163">**Automatisera processen att lägga till och tilldela licenser.**</span><span class="sxs-lookup"><span data-stu-id="06579-163">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="06579-164">Se [Skapa användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="06579-164">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="06579-165">Välj det här alternativet om du redan vet hur du använder cmdlets i Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06579-165">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="06579-166">**Använder du ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="06579-166">**Using ActiveDirectory?**</span></span> <span data-ttu-id="06579-167">[Konfigurera katalogsynkronisering för Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="06579-167">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="06579-168">Använd verktyget Azure AD Connect för att kopiera Active Directory-användarkonton (och andra Active Directory-objekt) i Office 365.</span><span class="sxs-lookup"><span data-stu-id="06579-168">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="06579-169">Synkroniseringen lägger bara till användarkonton.</span><span class="sxs-lookup"><span data-stu-id="06579-169">The sync only adds the user accounts.</span></span> <span data-ttu-id="06579-170">Du behöver tilldela licenser till de synkroniserade användarna för att de ska kunna använda e-post och andra Office-program.</span><span class="sxs-lookup"><span data-stu-id="06579-170">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="06579-171">**Migrera från Exchange?**</span><span class="sxs-lookup"><span data-stu-id="06579-171">**Migrating from Exchange?**</span></span> <span data-ttu-id="06579-172">[Olika sätt att migrera flera e-postkonton till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="06579-172">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="06579-173">När du migrerar flera postlådor till Microsoft 365 med hjälp av antingen cutover, staged eller en hybrid Exchange-metod, lägger du till användare automatiskt som en del av migreringen.</span><span class="sxs-lookup"><span data-stu-id="06579-173">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="06579-174">Migreringen lägger bara till användarkonton.</span><span class="sxs-lookup"><span data-stu-id="06579-174">The migration only adds the user accounts.</span></span> <span data-ttu-id="06579-175">Du behöver tilldela licenser till användarna för att de ska kunna använda e-post och andra Office-program.</span><span class="sxs-lookup"><span data-stu-id="06579-175">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="06579-176">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="06579-176">Related articles</span></span>

[<span data-ttu-id="06579-177">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="06579-177">Assign licenses to users</span></span>](../manage/assign-licenses-to-users.md)

[<span data-ttu-id="06579-178">Lägga till en ny anställd i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06579-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="06579-179">Ta bort en användare från organisationen</span><span class="sxs-lookup"><span data-stu-id="06579-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="06579-180">Återställa en användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06579-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="06579-181">Lägg till flera användare samtidigt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06579-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

