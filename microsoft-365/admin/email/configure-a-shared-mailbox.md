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
search.appverid:
- BCS160
- MET150
- MOE150
description: När du har skapat en delad postlåda behöver du konfigurera vissa inställningar för den, till exempel vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamnet eller medlemmarna.
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243978"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="1b3cf-104">Redigera inställningar för delad postlåda</span><span class="sxs-lookup"><span data-stu-id="1b3cf-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="1b3cf-105">När du har [skapat en delad](create-a-shared-mailbox.md)postlåda behöver du konfigurera vissa inställningar för postlådans användare, till exempel vidarebefordran av e-post och autosvar.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="1b3cf-106">Senare kanske du vill ändra andra inställningar, till exempel postlådenamn, medlemmar eller medlemsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="1b3cf-107">Ändra namn eller e-postalias för en delad postlåda eller ändra den primära e-postadressen</span><span class="sxs-lookup"><span data-stu-id="1b3cf-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="1b3cf-108">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-109">Markera den delade postlådan som du vill redigera och välj sedan **Redigera** bredvid **Namn, E-post, E-postalias**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="1b3cf-110">Ange ett nytt namn eller lägg till ett annat alias.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="1b3cf-111">Om du vill ändra den primära e-postadressen måste postlådan ha flera e-postalias.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="1b3cf-112">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="1b3cf-113">Vidarebefordra e-postmeddelanden som skickas till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="1b3cf-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="1b3cf-114">Du behöver inte tilldela en licens till den delade postlådan för att vidarebefordra e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="1b3cf-115">Du kan vidarebefordra meddelandena till en giltig e-postadress eller distributionslista.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="1b3cf-116">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-117">Markera den delade postlådan som du vill redigera och välj sedan Vidarebefordran av **e-post** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="1b3cf-118">Ställ in växlingsknappen på **På** och ange en e-postadress att vidarebefordra meddelandena till.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="1b3cf-119">Det kan vara vilken giltig e-postadress som helst.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-119">It can be any valid email address.</span></span> <span data-ttu-id="1b3cf-120">Om du vill vidarebefordra till flera adresser måste du skapa en [distributionsgrupp](/office365/admin/setup/create-distribution-lists) för adresserna och sedan ange namnet på gruppen i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="1b3cf-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="1b3cf-122">Skicka automatiska svar från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="1b3cf-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="1b3cf-123">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-124">Markera den delade postlådan som du vill redigera och välj sedan **Redigera** \> **autosvar.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="1b3cf-125">Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="1b3cf-p106">Skriv ett meddelande till personer inom organisation. Du endast lägga till text, inga bilder.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="1b3cf-128">Om du även *vill* skicka ett svar till personer utanför organisationen markerar du kryssrutan, vem du vill ska få svaret och skriver texten.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="1b3cf-129">Det går inte bara att skicka till personer utanför organisationen, men inte till personer inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="1b3cf-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="1b3cf-131">Tillåta alla att se skickad e-post (svaren)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="1b3cf-p108">Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="1b3cf-134">Om du vill att alla ska kunna se skickade e-postmeddelanden redigerar du inställningarna för den delade postlådan i administrationscentret och **väljer Redigera skickade** \> **objekt.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="1b3cf-135">Välj de appar som en delad postlåda kan använda för att komma åt e-post från Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b3cf-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="1b3cf-136">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-137">Markera den delade postlådan som du vill redigera och välj sedan **E-postprogram** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="1b3cf-138">Ställ in växlingsknappen **på På** för alla appar som du vill att medlemmarna ska kunna använda för att komma åt den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="1b3cf-139">Ställ in växlingsknappen **på** Av för appar som du inte vill att de ska använda.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="1b3cf-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="1b3cf-141">Sätta en delad postlåda i bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="1b3cf-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="1b3cf-142">Mer information om bevarande av juridiska skäl finns i [Skapa ett bevarande av juridiska skäl.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="1b3cf-143">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-144">Markera den delade postlådan du vill redigera och välj sedan Bevarande av juridiska **skäl** \> **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="1b3cf-145">Ställ in växlingsknappen på **På**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="1b3cf-146">Alternativt kan du ange en varaktighet, en anteckning om kvart i kommentaren och en URL med mer information.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="1b3cf-147">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="1b3cf-148">Lägga till eller ta bort medlemmar</span><span class="sxs-lookup"><span data-stu-id="1b3cf-148">Add or remove members</span></span>

1. <span data-ttu-id="1b3cf-149">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-150">Välj den delade postlådan som du vill redigera och välj sedan **Medlemmar** \> **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="1b3cf-151">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="1b3cf-151">Do one of the following:</span></span>
   - <span data-ttu-id="1b3cf-152">Om du vill lägga till medlemmar **väljer du Lägg till** medlemmar , söker efter eller väljer en medlem att lägga till och väljer sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="1b3cf-153">Om du vill ta bort medlemmar använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="1b3cf-154">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="1b3cf-155">Lägga till eller ta bort behörigheter för medlemmar</span><span class="sxs-lookup"><span data-stu-id="1b3cf-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="1b3cf-156">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-157">Markera den delade postlådan som du vill redigera och välj sedan **Medlemmar** \> **Anpassa behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="1b3cf-158">Välj **Redigera** bredvid den behörighet som du vill ändra för en medlem.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="1b3cf-159">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="1b3cf-159">Do one of the following:</span></span>
   - <span data-ttu-id="1b3cf-160">Om du vill ge behörighet till ytterligare en medlem väljer du **Lägg** till behörigheter , söker efter eller väljer en medlem att lägga till och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="1b3cf-161">Om du vill ta bort behörigheten från en medlem använder du sökrutan för att söka efter medlemmen om det **behövs,** väljer **X** bredvid medlemmens namn och väljer sedan Spara .</span><span class="sxs-lookup"><span data-stu-id="1b3cf-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="1b3cf-162">Välj **Spara** igen.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="1b3cf-163">Visa eller dölja en delad postlåda i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="1b3cf-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="1b3cf-164">Om du väljer att inte visa den delade postlådan i den globala adresslistan visas inte postlådan i organisationens adresslista, men den får fortfarande e-post som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="1b3cf-165">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="1b3cf-166">Markera den delade postlådan som du vill redigera och välj sedan **Visa i den globala adresslistan** \> **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="1b3cf-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="1b3cf-167">Ställ in växlingsknappen på **På**  eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="1b3cf-168">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1b3cf-169">Om du döljer en delad postlåda från adresslistan blir det omöjligt för nya medlemmar i delade postlådor att lägga till den dolda postlådan i sin Outlook-profil tills den delade postlådan visas igen i adresslistan.</span><span class="sxs-lookup"><span data-stu-id="1b3cf-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="1b3cf-170">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="1b3cf-170">Related content</span></span>

<span data-ttu-id="1b3cf-171">[Om delade postlådor](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="1b3cf-172">[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="1b3cf-173">[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="1b3cf-174">[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="1b3cf-175">[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1b3cf-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>