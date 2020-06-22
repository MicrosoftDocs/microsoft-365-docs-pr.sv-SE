---
title: Ge behörigheter för postlådor åt en annan användare – administratörshjälp
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Lär dig hur du ger en användare rätt att komma åt en annan användares postlåda. Då kan användaren läsa e-postmeddelanden och skicka e-postmeddelanden från den andra användarens postlåda. '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780607"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="ed1b4-104">Ge behörigheter för postlådor åt en annan användare – administratörshjälp</span><span class="sxs-lookup"><span data-stu-id="ed1b4-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="ed1b4-105">Som administratör kanske du behöver ge vissa användare åtkomst till andra användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="ed1b4-106">Du kanske till exempel vill låta en assistent kunna skicka och läsa e-post från sin chefs postlåda eller ge någon av dina användare möjlighet att skicka e-post åt en annan användare.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="ed1b4-107">I det här avsnittet får du se hur du ska göra.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="ed1b4-108">Om du letar efter information om att skapa och hantera delade postlådor kan du läsa [Skapa en delad postlåda](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ed1b4-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="ed1b4-109">Vill du konfigurera behörigheter till postlådor?</span><span class="sxs-lookup"><span data-stu-id="ed1b4-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="ed1b4-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span></span> <span data-ttu-id="ed1b4-111">The articles below might give you the help you need to set up and use this feature:</span><span class="sxs-lookup"><span data-stu-id="ed1b4-111">The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="ed1b4-112">**Konfigurera behörigheterna:**</span><span class="sxs-lookup"><span data-stu-id="ed1b4-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="ed1b4-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span></span> <span data-ttu-id="ed1b4-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span></span> <span data-ttu-id="ed1b4-115">Refer to the following articles on how to set up each type of permissions:</span><span class="sxs-lookup"><span data-stu-id="ed1b4-115">Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="ed1b4-116">Läsa e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ed1b4-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="ed1b4-117">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ed1b4-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="ed1b4-118">Skicka e-post åt en annan användare</span><span class="sxs-lookup"><span data-stu-id="ed1b4-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="ed1b4-119">**Spridning av ändringar:**</span><span class="sxs-lookup"><span data-stu-id="ed1b4-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="ed1b4-120">När du har konfigurerat behörigheter kan det ta upp till 60 minuter innan ändringarna har spridits i systemet.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="ed1b4-121">**Hur du använder funktionen när behörigheter har konfigurerats:**</span><span class="sxs-lookup"><span data-stu-id="ed1b4-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="ed1b4-122">There are a few different ways you can access a mailbox once you've been given access.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-122">There are a few different ways you can access a mailbox once you've been given access.</span></span> <span data-ttu-id="ed1b4-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="ed1b4-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="ed1b4-124">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ed1b4-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ed1b4-125">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ed1b4-126">Välj namnet på användaren (från vilken du vill ge en sändningsbehörighet) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ed1b4-127">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="ed1b4-128">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="ed1b4-129">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="ed1b4-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ed1b4-131">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ed1b4-132">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ed1b4-133">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ed1b4-134">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ed1b4-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ed1b4-136">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ed1b4-137">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ed1b4-138">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ed1b4-139">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ed1b4-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="ed1b4-141">Läsa e-post i en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ed1b4-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ed1b4-142">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ed1b4-143">Välj namnet på användaren (vars postlåda ska vara tillåten att läsa) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ed1b4-144">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ed1b4-145">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="ed1b4-146">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="ed1b4-147">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ed1b4-148">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="ed1b4-149">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ed1b4-150">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ed1b4-151">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ed1b4-152">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ed1b4-153">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="ed1b4-154">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ed1b4-155">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ed1b4-156">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ed1b4-157">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="ed1b4-158">Skicka e-post för en annan användare</span><span class="sxs-lookup"><span data-stu-id="ed1b4-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ed1b4-159">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ed1b4-160">Välj namnet på användaren (från vilken du vill ge behörigheten **Skicka för**) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ed1b4-161">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ed1b4-162">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="ed1b4-163">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="ed1b4-164">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ed1b4-165">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ed1b4-166">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ed1b4-167">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ed1b4-168">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ed1b4-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ed1b4-170">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ed1b4-171">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ed1b4-172">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ed1b4-173">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ed1b4-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ed1b4-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="ed1b4-175">Skicka och läsa från Outlook och Outlook på webben för företag</span><span class="sxs-lookup"><span data-stu-id="ed1b4-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="ed1b4-176">Want to know how to send email from another user's mailbox?</span><span class="sxs-lookup"><span data-stu-id="ed1b4-176">Want to know how to send email from another user's mailbox?</span></span> <span data-ttu-id="ed1b4-177">Check out the following topics:</span><span class="sxs-lookup"><span data-stu-id="ed1b4-177">Check out the following topics:</span></span>
  
- [<span data-ttu-id="ed1b4-178">Hantera andra personers e-post- och kalenderobjekt</span><span class="sxs-lookup"><span data-stu-id="ed1b4-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="ed1b4-179">Skicka e-post från en annan person eller grupp</span><span class="sxs-lookup"><span data-stu-id="ed1b4-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
