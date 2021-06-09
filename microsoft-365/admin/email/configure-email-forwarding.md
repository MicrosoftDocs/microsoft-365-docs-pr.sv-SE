---
title: Konfigurera vidarebefordran av e-post
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som Microsoft 365 en användarpostlåda till en annan postlåda i eller utanför organisationen.
ms.openlocfilehash: dfea738f5d786b6e476dd02dc92fd0aef452d62f
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730144"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="6722f-103">Konfigurera vidarebefordran av e-post i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6722f-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="6722f-104">Som administratör för en organisation kanske du behöver konfigurera vidarebefordran av e-post för en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="6722f-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="6722f-105">Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="6722f-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6722f-106">Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="6722f-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="6722f-107">Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="6722f-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="6722f-108">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="6722f-108">Configure email forwarding</span></span>

<span data-ttu-id="6722f-109">Innan du konfigurerar vidarebefordran av e-post ska du observera följande:</span><span class="sxs-lookup"><span data-stu-id="6722f-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="6722f-110">Tillåt att automatiskt vidarebefordrade meddelanden skickas till personer på fjärrdomänen.</span><span class="sxs-lookup"><span data-stu-id="6722f-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="6722f-111">Mer [information finns i Hantera](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) fjärrdomäner.</span><span class="sxs-lookup"><span data-stu-id="6722f-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="6722f-112">När du har ställt in vidarebefordran av e-post **vidarebefordras** bara nya  *e-postmeddelanden*  som skickas till från postlådan.</span><span class="sxs-lookup"><span data-stu-id="6722f-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="6722f-113">Vidarebefordran av e-post kräver  *att från-kontot*  har en licens.</span><span class="sxs-lookup"><span data-stu-id="6722f-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="6722f-114">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6722f-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="6722f-115">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="6722f-115">This way several people can access it.</span></span> <span data-ttu-id="6722f-116">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="6722f-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="6722f-117">Du måste vara Exchange administratör eller global administratör i Microsoft 365 kunna göra det här.</span><span class="sxs-lookup"><span data-stu-id="6722f-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="6722f-118">Mer information finns i avsnittet Om [administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6722f-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="6722f-119">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=834822)** användare.</span><span class="sxs-lookup"><span data-stu-id="6722f-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="6722f-120">Välj namnet på den användare vars e-post du vill vidarebefordra och öppna sedan egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="6722f-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="6722f-121">På fliken **E-post** väljer du Hantera **vidarebefordran av e-post**.</span><span class="sxs-lookup"><span data-stu-id="6722f-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="6722f-122">På sidan för vidarebefordran av e-post väljer du Vidarebefordra alla e-postmeddelanden som skickats till den här postlådan **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6722f-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="6722f-123">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="6722f-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="6722f-124">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="6722f-124">Select **Save changes**.</span></span>

    <span data-ttu-id="6722f-125">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="6722f-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="6722f-126">Öppna **Outlook**  >    >   **Hemregler >** Välj **Hantera regler och & aviseringar**</span><span class="sxs-lookup"><span data-stu-id="6722f-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="6722f-127">Välj **Ny regel Välj** Använd regel för meddelanden som jag tar  >  **emot** nästan längst ned i listan och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6722f-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="6722f-128">Klicka **på** Ja när du tillfrågas Om den här regeln tillämpas på alla meddelanden du får.</span><span class="sxs-lookup"><span data-stu-id="6722f-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="6722f-129">I nästa lista väljer du åtgärderna **omdirigerar den till personer eller offentlig grupp** och slutar bearbeta fler **regler**</span><span class="sxs-lookup"><span data-stu-id="6722f-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="6722f-130">Klicka på den **understrukna frasen personer eller** offentlig grupp i den nedre delen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="6722f-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="6722f-131">Skriv **e-postadressen** du vill vidarebefordra e-post till i fältet Till och klicka sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="6722f-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="6722f-132">Välj **Slutför**</span><span class="sxs-lookup"><span data-stu-id="6722f-132">Select **Finish**</span></span>
    

     <span data-ttu-id="6722f-133">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6722f-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="6722f-134">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="6722f-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="6722f-135">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="6722f-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6722f-136">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=847686)** användare.</span><span class="sxs-lookup"><span data-stu-id="6722f-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="6722f-137">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="6722f-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="6722f-138">Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**</span><span class="sxs-lookup"><span data-stu-id="6722f-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="6722f-139">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6722f-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="6722f-140">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="6722f-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="6722f-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6722f-141">Select **Save**.</span></span>

   <span data-ttu-id="6722f-142">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="6722f-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="6722f-143">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="6722f-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="6722f-144">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6722f-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="6722f-145">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="6722f-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="6722f-146">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="6722f-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6722f-147">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=850628)** användare.</span><span class="sxs-lookup"><span data-stu-id="6722f-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="6722f-148">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="6722f-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="6722f-149">Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**</span><span class="sxs-lookup"><span data-stu-id="6722f-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="6722f-150">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6722f-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="6722f-151">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="6722f-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="6722f-152">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6722f-152">Select **Save**.</span></span>

   <span data-ttu-id="6722f-153">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="6722f-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="6722f-154">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="6722f-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="6722f-155">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6722f-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="6722f-156">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="6722f-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="6722f-157">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="6722f-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="6722f-158">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="6722f-158">Related content</span></span> 

<span data-ttu-id="6722f-159">[Skapa en delad postlåda](../email/create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6722f-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6722f-160">[Skicka e-post från en annan adress](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6722f-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="6722f-161">[Ändra ett användarnamn och en e-postadress](../add-users/change-a-user-name-and-email-address.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6722f-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
