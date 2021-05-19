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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Ge en användare rätt att få åtkomst till en annan användares postlåda, så att användaren kan läsa och skicka e-postmeddelanden från den andra användarens postlåda.
ms.openlocfilehash: 3514be02f2ef82b727edfcf86c0bd3f6b8515510
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535968"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="af86e-103">Ge behörigheter för postlådor åt en annan användare – administratörshjälp</span><span class="sxs-lookup"><span data-stu-id="af86e-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="af86e-104">Som administratör kanske du behöver ge vissa användare åtkomst till andra användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="af86e-104">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="af86e-105">Du kanske till exempel vill låta en assistent kunna skicka och läsa e-post från sin chefs postlåda eller ge någon av dina användare möjlighet att skicka e-post åt en annan användare.</span><span class="sxs-lookup"><span data-stu-id="af86e-105">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="af86e-106">I det här avsnittet får du se hur du ska göra.</span><span class="sxs-lookup"><span data-stu-id="af86e-106">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="af86e-107">Om du letar efter information om att skapa och hantera delade postlådor kan du läsa [Skapa en delad postlåda](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="af86e-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="af86e-108">Vill du konfigurera behörigheter till postlådor?</span><span class="sxs-lookup"><span data-stu-id="af86e-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="af86e-p102">Med behörigheter till postlådor kan du ge en annan användare läs-och skrivbehörighet till en postlåda. Artiklarna nedan kan hjälpa dig att konfigurera och använda den här funktionen:</span><span class="sxs-lookup"><span data-stu-id="af86e-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="af86e-111">**Konfigurera behörigheterna:**</span><span class="sxs-lookup"><span data-stu-id="af86e-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="af86e-p103">Det första steget för att ställa in behörigheter är att bestämma vilka åtgärder du vill att andra användare ska kunna vidta i en viss postlåda. Du kan tillåta en användare att läsa e-postmeddelanden från postlådan, skicka e-postmeddelanden för en annan användare och skicka e-postmeddelanden som om de skickades från postlådan. Se följande artiklar om hur du ställer in de olika typerna av behörighet:</span><span class="sxs-lookup"><span data-stu-id="af86e-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="af86e-115">Läsa e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="af86e-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="af86e-116">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="af86e-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="af86e-117">Skicka e-post åt en annan användare</span><span class="sxs-lookup"><span data-stu-id="af86e-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="af86e-118">**Spridning av ändringar:**</span><span class="sxs-lookup"><span data-stu-id="af86e-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="af86e-119">När du har konfigurerat behörigheter kan det ta upp till 60 minuter innan ändringarna har spridits i systemet.</span><span class="sxs-lookup"><span data-stu-id="af86e-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="af86e-120">**Hur du använder funktionen när behörigheter har konfigurerats:**</span><span class="sxs-lookup"><span data-stu-id="af86e-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="af86e-p104">Det finns några olika sätt att komma åt en postlåda när du har fått åtkomst. Mer information om detta finns i den här artikeln: [Tillgång till en annan persons postlåda](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="af86e-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="af86e-123">Behörigheterna kan bara konfigureras i den aktuella organisationens klient organisation.</span><span class="sxs-lookup"><span data-stu-id="af86e-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="af86e-124">Det är inte möjligt att ställa in brevlådesbehörigheter hos uthyresanvändare.</span><span class="sxs-lookup"><span data-stu-id="af86e-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="af86e-125">Skicka e-post från en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="af86e-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af86e-126">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="af86e-127">Välj namnet på användaren (från vilken du vill ge en sändningsbehörighet) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="af86e-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="af86e-128">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="af86e-129">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="af86e-130">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="af86e-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="af86e-131">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af86e-132">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="af86e-133">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="af86e-134">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="af86e-135">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="af86e-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="af86e-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af86e-137">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="af86e-138">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="af86e-139">Bredvid **Skicka som** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="af86e-140">Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som.</span><span class="sxs-lookup"><span data-stu-id="af86e-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="af86e-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="af86e-142">Läsa e-post i en annan användares postlåda</span><span class="sxs-lookup"><span data-stu-id="af86e-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af86e-143">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="af86e-144">Välj namnet på användaren (vars postlåda ska vara tillåten att läsa) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="af86e-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="af86e-145">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="af86e-146">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="af86e-147">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="af86e-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="af86e-149">**Läsa** och **hantera** behörigheter kallas **full åtkomstbehörighet** när de beviljas i Exchange-administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="af86e-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="af86e-150">Fullständig åtkomst ger inte behörighet att **skicka som** eller **skicka för** behörigheter.</span><span class="sxs-lookup"><span data-stu-id="af86e-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af86e-151">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="af86e-152">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="af86e-153">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="af86e-154">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="af86e-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af86e-156">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="af86e-157">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="af86e-158">Bredvid **Läs och hantera** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="af86e-159">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="af86e-160">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="af86e-161">Skicka e-post för en annan användare</span><span class="sxs-lookup"><span data-stu-id="af86e-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af86e-162">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="af86e-163">Välj namnet på användaren (från vilken du vill ge behörigheten **Skicka för**) för att öppna fönstret Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="af86e-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="af86e-164">På fliken **E-post** väljer du **Hantera postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="af86e-165">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="af86e-166">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="af86e-167">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af86e-168">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="af86e-169">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="af86e-170">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="af86e-171">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="af86e-172">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af86e-173">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="af86e-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="af86e-174">Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="af86e-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="af86e-175">Bredvid **Skicka för** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="af86e-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="af86e-176">Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.</span><span class="sxs-lookup"><span data-stu-id="af86e-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="af86e-177">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af86e-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="af86e-178">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="af86e-178">Related content</span></span>
  
<span data-ttu-id="af86e-179">[Hantera andra personers e-post- och kalenderobjekt](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (artikel)</span><span class="sxs-lookup"><span data-stu-id="af86e-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>
    
<span data-ttu-id="af86e-180">[Skicka e-post från en annan person eller grupp](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="af86e-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>

<span data-ttu-id="af86e-181">[Ändra användarnamn och e-postadress](../add-users/change-a-user-name-and-email-address.md) (video)</span><span class="sxs-lookup"><span data-stu-id="af86e-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

