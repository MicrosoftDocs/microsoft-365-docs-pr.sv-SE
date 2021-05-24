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
ms.openlocfilehash: eb72204211a8eff929c024fbcede66dfe1f4b879
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635492"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="45091-103">Konfigurera vidarebefordran av e-post i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45091-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="45091-104">Som administratör för en organisation kanske du behöver konfigurera vidarebefordran av e-post för en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="45091-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="45091-105">Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="45091-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45091-106">Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="45091-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="45091-107">Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="45091-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="45091-108">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="45091-108">Configure email forwarding</span></span>

<span data-ttu-id="45091-109">Innan du konfigurerar vidarebefordran av e-post ska du observera följande:</span><span class="sxs-lookup"><span data-stu-id="45091-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="45091-110">När du har ställt in vidarebefordran av e-post **vidarebefordras** bara nya  *e-postmeddelanden*  som skickas till från postlådan.</span><span class="sxs-lookup"><span data-stu-id="45091-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="45091-111">Vidarebefordran av e-post kräver  *att från-kontot*  har en licens.</span><span class="sxs-lookup"><span data-stu-id="45091-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="45091-112">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="45091-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="45091-113">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="45091-113">This way several people can access it.</span></span> <span data-ttu-id="45091-114">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="45091-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="45091-115">Du måste vara Exchange administratör eller global administratör i Microsoft 365 kunna göra det här.</span><span class="sxs-lookup"><span data-stu-id="45091-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="45091-116">Mer information finns i avsnittet Om [administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="45091-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="45091-117">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=834822)** användare.</span><span class="sxs-lookup"><span data-stu-id="45091-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="45091-118">Välj namnet på den användare vars e-post du vill vidarebefordra och öppna sedan egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="45091-118">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="45091-119">På fliken **E-post** väljer du Hantera **vidarebefordran av e-post**.</span><span class="sxs-lookup"><span data-stu-id="45091-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="45091-120">På sidan för vidarebefordran av e-post väljer du Vidarebefordra alla e-postmeddelanden som skickats till den här postlådan **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="45091-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="45091-121">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="45091-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="45091-122">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="45091-122">Select **Save changes**.</span></span>

    <span data-ttu-id="45091-123">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="45091-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="45091-124">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="45091-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="45091-125">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="45091-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="45091-126">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="45091-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="45091-127">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="45091-127">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="45091-128">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=847686)** användare.</span><span class="sxs-lookup"><span data-stu-id="45091-128">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="45091-129">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="45091-129">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="45091-130">Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**</span><span class="sxs-lookup"><span data-stu-id="45091-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="45091-131">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="45091-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="45091-132">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="45091-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="45091-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="45091-133">Select **Save**.</span></span>

   <span data-ttu-id="45091-134">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="45091-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="45091-135">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="45091-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="45091-136">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="45091-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="45091-137">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="45091-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="45091-138">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="45091-138">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="45091-139">I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=850628)** användare.</span><span class="sxs-lookup"><span data-stu-id="45091-139">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="45091-140">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="45091-140">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="45091-141">Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**</span><span class="sxs-lookup"><span data-stu-id="45091-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="45091-142">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="45091-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="45091-143">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="45091-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="45091-144">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="45091-144">Select **Save**.</span></span>

   <span data-ttu-id="45091-145">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook att vidarebefordra till adresserna.</span><span class="sxs-lookup"><span data-stu-id="45091-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="45091-146">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="45091-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="45091-147">I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="45091-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="45091-148">Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!</span><span class="sxs-lookup"><span data-stu-id="45091-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="45091-149">Om du gör det stoppas vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="45091-149">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="45091-150">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="45091-150">Related content</span></span> 

<span data-ttu-id="45091-151">[Skapa en delad postlåda](../email/create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45091-151">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="45091-152">[Skicka e-post från en annan adress](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45091-152">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="45091-153">[Ändra ett användarnamn och en e-postadress](../add-users/change-a-user-name-and-email-address.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45091-153">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

