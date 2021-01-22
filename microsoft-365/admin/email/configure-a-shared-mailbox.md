---
title: Redigera inställningar för delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: När du har skapat en delad postlåda kan du konfigurera vissa inställningar för den delade postlådan, till exempel för vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamnet eller medlemmarna.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926612"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="43aac-104">Redigera inställningar för delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="43aac-105">När du har [skapat en delad postlåda](create-a-shared-mailbox.md)kan du konfigurera vissa inställningar för postlådeanvändarna, till exempel vidarebefordran av e-post och automatiska svar.</span><span class="sxs-lookup"><span data-stu-id="43aac-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="43aac-106">Senare kanske du vill ändra andra inställningar, till exempel postlådenamn, medlemmar eller medlemsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="43aac-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="43aac-107">Ändra namn eller e-postalias för en delad postlåda eller ändra den primära e-postadressen</span><span class="sxs-lookup"><span data-stu-id="43aac-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-108">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-109">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-110">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-111">Markera den delade postlådan som du vill redigera och välj sedan **Redigera** bredvid **Namn, E-post, E-postalias.**</span><span class="sxs-lookup"><span data-stu-id="43aac-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="43aac-112">Ange ett nytt namn eller lägg till ett annat alias.</span><span class="sxs-lookup"><span data-stu-id="43aac-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="43aac-113">Om du vill ändra den primära e-postadressen måste postlådan ha fler än ett e-postalias.</span><span class="sxs-lookup"><span data-stu-id="43aac-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="43aac-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="43aac-115">Vidarebefordra e-postmeddelanden som skickas till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="43aac-116">Du behöver inte tilldela den delade postlådan en licens för att vidarebefordra e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="43aac-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="43aac-117">Du kan vidarebefordra meddelandena till en giltig e-postadress eller distributionslista.</span><span class="sxs-lookup"><span data-stu-id="43aac-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-118">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-119">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-120">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-121">Markera den delade postlådan som du vill redigera och välj sedan Vidarebefordran av **e-post,** \> **redigera.**</span><span class="sxs-lookup"><span data-stu-id="43aac-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="43aac-122">Ställ in växlingsknappen **på På** och ange en e-postadress för att vidarebefordra meddelandena till.</span><span class="sxs-lookup"><span data-stu-id="43aac-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="43aac-123">Det kan vara vilken giltig e-postadress som helst.</span><span class="sxs-lookup"><span data-stu-id="43aac-123">It can be any valid email address.</span></span> <span data-ttu-id="43aac-124">Om du vill vidarebefordra till flera adresser måste du skapa en [distributionsgrupp](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) för adresserna och sedan ange namnet på gruppen i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="43aac-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="43aac-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="43aac-126">Skicka automatiska svar från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-127">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-128">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-129">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-130">Markera den delade postlådan som du vill redigera och välj **sedan Redigera** \> **autosvar.**</span><span class="sxs-lookup"><span data-stu-id="43aac-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="43aac-131">Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="43aac-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="43aac-132">Skriv ett meddelande till personer inom organisation.</span><span class="sxs-lookup"><span data-stu-id="43aac-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="43aac-133">Du endast lägga till text, inga bilder.</span><span class="sxs-lookup"><span data-stu-id="43aac-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="43aac-134">Om du även *vill* skicka ett svar till personer utanför organisationen markerar du kryssrutan, vem du vill ska få svaret och skriver texten.</span><span class="sxs-lookup"><span data-stu-id="43aac-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="43aac-135">Det går inte bara att skicka till personer utanför organisationen, men inte till personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="43aac-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="43aac-136">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="43aac-137">Tillåta alla att se skickad e-post (svaren)</span><span class="sxs-lookup"><span data-stu-id="43aac-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="43aac-p108">Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.</span><span class="sxs-lookup"><span data-stu-id="43aac-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="43aac-140">Om du vill att alla ska kunna se skickad e-post redigerar du inställningarna för den delade postlådan i administrationscentret och väljer **Redigera skickade** \> **objekt.**</span><span class="sxs-lookup"><span data-stu-id="43aac-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="43aac-141">Välj de appar som en delad postlåda kan använda för att komma åt e-post från Microsoft</span><span class="sxs-lookup"><span data-stu-id="43aac-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-142">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-143">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-144">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-145">Markera den delade postlådan som du vill redigera och välj sedan Redigera i **e-postprogram.** \> </span><span class="sxs-lookup"><span data-stu-id="43aac-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="43aac-146">Ställ in växlingsknappen **på På** för alla program som du vill att medlemmarna ska kunna använda för åtkomst till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="43aac-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="43aac-147">Ställ in växlingsknappen **på** Av för appar som du inte vill att de ska använda.</span><span class="sxs-lookup"><span data-stu-id="43aac-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="43aac-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="43aac-149">Sätta en delad postlåda i bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="43aac-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="43aac-150">Mer information om bevarande av juridiska skäl finns i [Skapa ett bevarande av juridiska skäl.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="43aac-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-151">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-152">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-153">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-154">Markera den delade postlådan som du vill redigera och välj sedan Bevarande **av juridiska** \> **skäl, Redigera.**</span><span class="sxs-lookup"><span data-stu-id="43aac-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="43aac-155">Ställ in växlingsknappen på **På.**</span><span class="sxs-lookup"><span data-stu-id="43aac-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="43aac-156">Du kan också ange en varaktighet, en anteckning om hållen och en URL med mer information.</span><span class="sxs-lookup"><span data-stu-id="43aac-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="43aac-157">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="43aac-158">Lägga till eller ta bort medlemmar</span><span class="sxs-lookup"><span data-stu-id="43aac-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-159">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-160">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-161">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-162">Markera den delade postlådan som du vill redigera och välj sedan **Redigera** \> **för medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="43aac-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="43aac-163">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="43aac-163">Do one of the following:</span></span>
   - <span data-ttu-id="43aac-164">Om du vill lägga till **medlemmar väljer du Lägg** till medlemmar, söker efter eller väljer en medlem att lägga till och väljer sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="43aac-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="43aac-165">Om du vill ta bort medlemmar använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer **sedan Spara.**</span><span class="sxs-lookup"><span data-stu-id="43aac-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="43aac-166">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="43aac-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="43aac-167">Lägga till eller ta bort behörigheter för medlemmar</span><span class="sxs-lookup"><span data-stu-id="43aac-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-168">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-169">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-170">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-171">Markera den delade postlådan som du vill redigera och välj sedan **Medlemmar** \> **Anpassa behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="43aac-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="43aac-172">Välj **Redigera** bredvid den behörighet som du vill ändra för en medlem.</span><span class="sxs-lookup"><span data-stu-id="43aac-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="43aac-173">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="43aac-173">Do one of the following:</span></span>
   - <span data-ttu-id="43aac-174">Om du vill ge den behörigheten till ytterligare en medlem väljer du Lägg till **behörigheter,** söker efter eller väljer en medlem att lägga till och väljer sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="43aac-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="43aac-175">Om du vill ta bort behörigheten för en medlem använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer **sedan Spara.**</span><span class="sxs-lookup"><span data-stu-id="43aac-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="43aac-176">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="43aac-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="43aac-177">Visa eller dölja en delad postlåda i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="43aac-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="43aac-178">Om du väljer att inte visa den delade postlådan i den globala adresslistan visas inte postlådan i organisationens adresslista, men den får fortfarande e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="43aac-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="43aac-179">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43aac-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="43aac-180">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="43aac-181">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="43aac-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="43aac-182">Markera den delade postlådan som du vill redigera och välj sedan **Visa i den globala adresslistan** \> **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="43aac-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="43aac-183">Ställ in växlingsknappen **på På** eller **Av.**</span><span class="sxs-lookup"><span data-stu-id="43aac-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="43aac-184">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="43aac-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="43aac-185">Om du döljer en delad postlåda från adresslistan går det inte att lägga till den dolda postlådan i den delade postlådan i deras Outlook-profil tills den delade postlådan visas igen i adresslistan.</span><span class="sxs-lookup"><span data-stu-id="43aac-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="43aac-186">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="43aac-186">Related articles</span></span>

[<span data-ttu-id="43aac-187">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="43aac-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="43aac-188">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="43aac-189">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="43aac-190">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="43aac-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="43aac-191">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="43aac-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
