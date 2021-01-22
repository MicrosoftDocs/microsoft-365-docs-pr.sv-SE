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
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med hjälp av Office365.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926648"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="ad440-103">Konfigurera vidarebefordran av e-post i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad440-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ad440-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="ad440-104">The admin center is changing.</span></span> <span data-ttu-id="ad440-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ad440-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="ad440-106">Som administratör för en organisation kanske du behöver konfigurera vidarebefordran av e-post för en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="ad440-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="ad440-107">Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad440-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad440-108">Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="ad440-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="ad440-109">Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="ad440-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="ad440-110">Konfigurera vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="ad440-110">Configure email forwarding</span></span>

<span data-ttu-id="ad440-111">Innan du konfigurerar vidarebefordran av e-post bör du observera följande:</span><span class="sxs-lookup"><span data-stu-id="ad440-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="ad440-112">När du har angett vidarebefordran av **e-post** vidarebefordras bara nya  *e-postmeddelanden*  som skickas till från postlådan.</span><span class="sxs-lookup"><span data-stu-id="ad440-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="ad440-113">Vidarebefordran av e-post kräver  *att från-kontot*  har en licens.</span><span class="sxs-lookup"><span data-stu-id="ad440-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="ad440-114">Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ad440-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="ad440-115">På det sättet kan flera personer komma åt den.</span><span class="sxs-lookup"><span data-stu-id="ad440-115">This way several people can access it.</span></span> <span data-ttu-id="ad440-116">En delad postlåda kan dock inte vara större än 50 GB.</span><span class="sxs-lookup"><span data-stu-id="ad440-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="ad440-117">Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att kunna göra följande.</span><span class="sxs-lookup"><span data-stu-id="ad440-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="ad440-118">Mer information finns i avsnittet om [administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ad440-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ad440-119">Gå till sidan Användare aktiva användare **i** \> **[administrationscentret.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="ad440-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="ad440-120">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="ad440-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="ad440-121">Välj Hantera **vidarebefordran av** e-post **på fliken E-post.**</span><span class="sxs-lookup"><span data-stu-id="ad440-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="ad440-122">På sidan för vidarebefordran av e-post väljer du Vidarebefordra alla e-postmeddelanden som skickats till den här postlådan, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ad440-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="ad440-123">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ad440-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="ad440-124">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ad440-124">Select **Save changes**.</span></span>

    <span data-ttu-id="ad440-125">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook som vidarebefordrar till adresserna.</span><span class="sxs-lookup"><span data-stu-id="ad440-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="ad440-126">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="ad440-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="ad440-127">Du kan också skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [i](add-user-or-contact-to-distribution-list.md)administrationscentret, lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan enligt anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ad440-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="ad440-128">Ta inte bort kontot för användaren som vidarebefordrar e-post till eller ta bort användarens licens.</span><span class="sxs-lookup"><span data-stu-id="ad440-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="ad440-129">Om du gör det avbryts vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="ad440-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ad440-130">Gå till sidan Användare aktiva användare **i** \> **[administrationscentret.](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="ad440-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="ad440-131">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="ad440-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="ad440-132">Expandera **e-postinställningarna** och välj Redigera i avsnittet **Vidarebefordran** av e-post. </span><span class="sxs-lookup"><span data-stu-id="ad440-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="ad440-133">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på **På,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ad440-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="ad440-134">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ad440-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="ad440-135">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ad440-135">Select **Save**.</span></span>

   <span data-ttu-id="ad440-136">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook som vidarebefordrar till adresserna.</span><span class="sxs-lookup"><span data-stu-id="ad440-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="ad440-137">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="ad440-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="ad440-138">Du kan också skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [i](add-user-or-contact-to-distribution-list.md)administrationscentret, lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan enligt anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ad440-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="ad440-139">Ta inte bort kontot för användaren som vidarebefordrar e-post till eller ta bort användarens licens.</span><span class="sxs-lookup"><span data-stu-id="ad440-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="ad440-140">Om du gör det avbryts vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="ad440-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ad440-141">Gå till sidan Användare aktiva användare **i** \> **[administrationscentret.](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="ad440-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="ad440-142">Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.</span><span class="sxs-lookup"><span data-stu-id="ad440-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="ad440-143">Expandera **e-postinställningarna** och välj Redigera i avsnittet **Vidarebefordran** av e-post. </span><span class="sxs-lookup"><span data-stu-id="ad440-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="ad440-144">På sidan för vidarebefordran av e-post ställer du in växlingsknappen på **På,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ad440-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="ad440-145">Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ad440-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="ad440-146">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ad440-146">Select **Save**.</span></span>

   <span data-ttu-id="ad440-147">**Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook som vidarebefordrar till adresserna.</span><span class="sxs-lookup"><span data-stu-id="ad440-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="ad440-148">Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="ad440-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="ad440-149">Du kan också skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [i](add-user-or-contact-to-distribution-list.md)administrationscentret, lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan enligt anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ad440-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="ad440-150">Ta inte bort kontot för den användare som vidarebefordrar e-post till eller ta bort användarens licens.</span><span class="sxs-lookup"><span data-stu-id="ad440-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="ad440-151">Om du gör det avbryts vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="ad440-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
