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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Lär dig hur du ger en användare rätt att komma åt en annan användares postlåda. Då kan användaren läsa e-postmeddelanden och skicka e-postmeddelanden från den andra användarens postlåda. '
ms.openlocfilehash: 5a0677844e8503253561c57f926c9c4fadadd76d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617176"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="509c7-104">Ge behörigheter för postlådor åt en annan användare – administratörshjälp</span><span class="sxs-lookup"><span data-stu-id="509c7-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="509c7-105">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="509c7-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="509c7-106">Som administratör kanske du behöver ge vissa användare åtkomst till andra användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="509c7-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="509c7-107">Du kanske till exempel vill låta en assistent kunna skicka och läsa e-post från sin chefs postlåda eller ge någon av dina användare möjlighet att skicka e-post åt en annan användare.</span><span class="sxs-lookup"><span data-stu-id="509c7-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="509c7-108">I det här avsnittet får du se hur du ska göra.</span><span class="sxs-lookup"><span data-stu-id="509c7-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="509c7-109">Om du letar efter information om att skapa och hantera delade postlådor kan du läsa [Skapa en delad postlåda](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="509c7-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="509c7-110">Vill du konfigurera behörigheter till postlådor?</span><span class="sxs-lookup"><span data-stu-id="509c7-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="509c7-p103">Med behörigheter till postlådor kan du ge en annan användare läs-och skrivbehörighet till en postlåda. Artiklarna nedan kan hjälpa dig att konfigurera och använda den här funktionen:</span><span class="sxs-lookup"><span data-stu-id="509c7-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="509c7-113">**Konfigurera behörigheterna:**</span><span class="sxs-lookup"><span data-stu-id="509c7-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="509c7-p104">Det första steget för att ställa in behörigheter är att bestämma vilka åtgärder du vill att andra användare ska kunna vidta i en viss postlåda. Du kan tillåta en användare att läsa e-postmeddelanden från postlådan, skicka e-postmeddelanden för en annan användare och skicka e-postmeddelanden som om de skickades från postlådan. Se följande artiklar om hur du ställer in de olika typerna av behörighet:</span><span class="sxs-lookup"><span data-stu-id="509c7-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="509c7-117">Läsa e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="509c7-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="509c7-118">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="509c7-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="509c7-119">Skicka e-post åt en annan användare</span><span class="sxs-lookup"><span data-stu-id="509c7-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="509c7-120">**Spridning av ändringar:**</span><span class="sxs-lookup"><span data-stu-id="509c7-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="509c7-121">När du har konfigurerat behörigheter kan det ta upp till 60 minuter innan ändringarna har spridits i systemet.</span><span class="sxs-lookup"><span data-stu-id="509c7-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="509c7-122">**Hur du använder funktionen när behörigheter har konfigurerats:**</span><span class="sxs-lookup"><span data-stu-id="509c7-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="509c7-p105">Det finns några olika sätt att komma åt en postlåda när du har fått åtkomst. Mer information om detta finns i den här artikeln: [Tillgång till en annan persons postlåda](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="509c7-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="509c7-125">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="509c7-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="509c7-126">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="509c7-127">Välj namnet på användaren (från vilken du vill ge en sändningsbehörighet) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="509c7-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="509c7-128">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="509c7-129">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="509c7-130">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="509c7-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="509c7-131">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="509c7-132">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="509c7-133">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="509c7-134">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="509c7-135">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="509c7-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="509c7-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="509c7-137">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="509c7-138">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="509c7-139">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="509c7-140">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="509c7-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="509c7-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="509c7-142">Läsa e-post i en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="509c7-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="509c7-143">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="509c7-144">Välj namnet på användaren (vars postlåda ska vara tillåten att läsa) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="509c7-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="509c7-145">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="509c7-146">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="509c7-147">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="509c7-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="509c7-149">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="509c7-150">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="509c7-151">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="509c7-152">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="509c7-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="509c7-154">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="509c7-155">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="509c7-156">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="509c7-157">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="509c7-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="509c7-159">Skicka e-post för en annan användare</span><span class="sxs-lookup"><span data-stu-id="509c7-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="509c7-160">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="509c7-161">Välj namnet på användaren (från vilken du vill ge behörigheten **Skicka för**) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="509c7-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="509c7-162">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="509c7-163">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="509c7-164">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="509c7-165">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="509c7-166">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="509c7-167">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="509c7-168">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="509c7-169">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="509c7-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="509c7-171">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="509c7-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="509c7-172">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="509c7-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="509c7-173">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="509c7-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="509c7-174">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="509c7-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="509c7-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="509c7-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="509c7-176">Skicka och läsa från Outlook och Outlook på webben för företag</span><span class="sxs-lookup"><span data-stu-id="509c7-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="509c7-p106">Vill du veta hur du skickar e-post från en annan användares postlåda? Läs följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="509c7-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="509c7-179">Hantera andra personers e-post- och kalenderobjekt</span><span class="sxs-lookup"><span data-stu-id="509c7-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="509c7-180">Skicka e-post från en annan person eller grupp</span><span class="sxs-lookup"><span data-stu-id="509c7-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
