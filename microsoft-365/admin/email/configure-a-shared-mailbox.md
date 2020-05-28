---
title: Konfigurera en delad postlåda
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: När du har skapat en delad postlåda bör du konfigurera vissa inställningar för användarna, till exempel vidarebefordran av e-post och autosvar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamnet eller medlemmarna.
ms.openlocfilehash: 7c88ffa3276f40ea983f9060658f4e4091e36280
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400154"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="23830-104">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-104">Configure a shared mailbox</span></span>

<span data-ttu-id="23830-105">När du har [skapat en delad postlåda](create-a-shared-mailbox.md)bör du konfigurera vissa inställningar för postlådeanvändarna, till exempel vidarebefordran av e-post och autosvar.</span><span class="sxs-lookup"><span data-stu-id="23830-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="23830-106">Senare kanske du vill ändra andra inställningar, till exempel postlådenamn, medlemmar eller medlemsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="23830-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="23830-107">Ändra namn eller e-postalias för en delad postlåda eller ändra den primära e-postadressen</span><span class="sxs-lookup"><span data-stu-id="23830-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-108">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-109">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-110">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-111">Markera den delade postlåda som du vill redigera och välj sedan **Redigera bredvid** **Namn, E-post, E-postalias**.</span><span class="sxs-lookup"><span data-stu-id="23830-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="23830-112">Ange ett nytt namn eller lägg till ett annat alias.</span><span class="sxs-lookup"><span data-stu-id="23830-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="23830-113">Om du vill ändra den primära e-postadressen måste postlådan ha mer än ett e-postalias.</span><span class="sxs-lookup"><span data-stu-id="23830-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="23830-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="23830-115">Vidarebefordra e-postmeddelanden som skickas till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="23830-116">Du behöver inte tilldela en licens till den delade postlådan för att vidarebefordra e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="23830-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="23830-117">Du kan vidarebefordra meddelandena till en giltig e-postadress eller distributionslista.</span><span class="sxs-lookup"><span data-stu-id="23830-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-118">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-119">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-120">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-121">Markera den delade postlåda som du vill redigera och välj sedan Redigera redigera **Email forwarding** \> **e-post.**</span><span class="sxs-lookup"><span data-stu-id="23830-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="23830-122">Ställ in växlingsknappen **på På**och ange en e-postadress att vidarebefordra meddelandena till.</span><span class="sxs-lookup"><span data-stu-id="23830-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="23830-123">Det kan vara vilken giltig e-postadress som helst.</span><span class="sxs-lookup"><span data-stu-id="23830-123">It can be any valid email address.</span></span> <span data-ttu-id="23830-124">Om du vill vidarebefordra till flera adresser måste du [skapa en distributionsgrupp](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) för adresserna och sedan ange namnet på gruppen i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="23830-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="23830-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="23830-126">Skicka automatiska svar från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-127">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-128">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-129">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-130">Markera den delade postlåda som du vill redigera och välj sedan **Redigera autosvar** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="23830-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="23830-131">Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="23830-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="23830-132">Skriv ett meddelande till personer inom organisation.</span><span class="sxs-lookup"><span data-stu-id="23830-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="23830-133">Du endast lägga till text, inga bilder.</span><span class="sxs-lookup"><span data-stu-id="23830-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="23830-134">Om du *också* vill skicka ett svar till personer utanför organisationen markerar du kryssrutan, vem du vill få svaret och skriver texten.</span><span class="sxs-lookup"><span data-stu-id="23830-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="23830-135">Det finns inget sätt att bara skicka till personer utanför organisationen, men inte till personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="23830-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="23830-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="23830-137">Tillåta alla att se skickad e-post (svaren)</span><span class="sxs-lookup"><span data-stu-id="23830-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="23830-p108">Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.</span><span class="sxs-lookup"><span data-stu-id="23830-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="23830-140">Om du vill att alla ska kunna se det skickade e-postmeddelandet redigerar du inställningarna för den delade postlådan i administrationscentret och väljer Redigera **skickade objekt** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="23830-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="23830-141">Välj de appar som en delad postlåda kan använda för att komma åt Microsoft-e-post</span><span class="sxs-lookup"><span data-stu-id="23830-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-142">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-143">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-144">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-145">Markera den delade postlåda som du vill redigera och välj sedan **Redigera e-postappar** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="23830-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="23830-146">Ställ in växlingsknappen på **På** för alla appar som du vill att medlemmar ska kunna använda för att komma åt den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="23830-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="23830-147">Ställ in växlingsknappen på **Av** för alla appar som du inte vill att de ska använda.</span><span class="sxs-lookup"><span data-stu-id="23830-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="23830-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="23830-149">Spärra en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="23830-150">Mer information om bevarande av rättstvister finns i [Skapa en bevarande av rättstvister](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="23830-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-151">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-152">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-153">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-154">Markera den delade postlåda som du vill redigera och välj sedan **Spärr för juridiska skäl** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="23830-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="23830-155">Ställ in växlingsknappen **på På**.</span><span class="sxs-lookup"><span data-stu-id="23830-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="23830-156">Du kan också ange en varaktighet, en anteckning om spärren och en URL med mer information.</span><span class="sxs-lookup"><span data-stu-id="23830-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="23830-157">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="23830-158">Lägga till eller ta bort medlemmar</span><span class="sxs-lookup"><span data-stu-id="23830-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-159">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-160">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-161">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-162">Markera den delade postlåda som du vill redigera och välj sedan **Medlemmar** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="23830-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="23830-163">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="23830-163">Do one of the following:</span></span>
   - <span data-ttu-id="23830-164">Om du vill lägga till medlemmar väljer du **Lägg till medlemmar,** söker efter eller väljer en medlem att lägga till och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="23830-165">Om du vill ta bort medlemmar använder du sökrutan för att söka efter medlemmen om det behövs, markerar **X** bredvid medlemmens namn och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="23830-166">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="23830-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="23830-167">Lägga till eller ta bort behörigheter för medlemmar</span><span class="sxs-lookup"><span data-stu-id="23830-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-168">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-169">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-170">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-171">Markera den delade postlåda som du vill redigera och välj sedan **Behörigheter för Medlemmar** \> **anpassa .**</span><span class="sxs-lookup"><span data-stu-id="23830-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="23830-172">Välj **Redigera** bredvid den behörighet som du vill ändra för en medlem.</span><span class="sxs-lookup"><span data-stu-id="23830-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="23830-173">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="23830-173">Do one of the following:</span></span>
   - <span data-ttu-id="23830-174">Om du vill ge den behörigheten till ytterligare en medlem väljer du **Lägg till behörigheter**, söker efter eller väljer en medlem att lägga till och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="23830-175">Om du vill ta bort behörigheten från en medlem använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="23830-176">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="23830-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="23830-177">Visa eller dölja en delad postlåda i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="23830-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="23830-178">Om du väljer att inte visa den delade postlådan i den globala adresslistan visas inte postlådan i organisationens adresslista, men den får fortfarande e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="23830-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23830-179">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="23830-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="23830-180">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23830-181">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="23830-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="23830-182">Markera den delade postlåda som du vill redigera och välj sedan **Visa i den globala adresslistan** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="23830-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="23830-183">Ställ in växlingsknappen **på På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="23830-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="23830-184">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="23830-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="23830-185">Om du döljer en delad postlåda från adresslistan blir det omöjligt för nya medlemmar i delad postlåda att lägga till den dolda postlådan i sin Outlook-profil tills den delade postlådan visas igen i adresslistan.</span><span class="sxs-lookup"><span data-stu-id="23830-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="23830-186">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="23830-186">Related articles</span></span>

[<span data-ttu-id="23830-187">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="23830-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="23830-188">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="23830-189">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="23830-190">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="23830-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="23830-191">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="23830-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
