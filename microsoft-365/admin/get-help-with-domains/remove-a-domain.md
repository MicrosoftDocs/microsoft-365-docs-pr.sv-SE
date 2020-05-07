---
title: Ta bort en domän
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Lär dig hur du tar bort en gammal domän från Microsoft 365 och flyttar användare och grupper till en annan domän.
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140411"
---
# <a name="remove-a-domain"></a><span data-ttu-id="8f944-103">Ta bort en domän</span><span class="sxs-lookup"><span data-stu-id="8f944-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8f944-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8f944-104">The admin center is changing.</span></span> <span data-ttu-id="8f944-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8f944-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="8f944-106">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="8f944-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8f944-107">Tar du bort domänen för att du vill lägga till den i ett annat Microsoft 365-prenumerationsabonnemang?</span><span class="sxs-lookup"><span data-stu-id="8f944-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="8f944-108">Eller vill du avbryta din prenumeration?</span><span class="sxs-lookup"><span data-stu-id="8f944-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="8f944-109">Du kan [ändra ditt abonnemang eller din prenumeration](../../commerce/subscriptions/switch-to-a-different-plan.md) eller [avbryta prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="8f944-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="8f944-110">Steg 1: Flytta användare till en annan domän</span><span class="sxs-lookup"><span data-stu-id="8f944-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="8f944-111">Flytta användare</span><span class="sxs-lookup"><span data-stu-id="8f944-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8f944-112">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="8f944-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8f944-113">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a>.</span><span class="sxs-lookup"><span data-stu-id="8f944-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="8f944-114">Välj **Aktiva användare av** > **användare**.</span><span class="sxs-lookup"><span data-stu-id="8f944-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8f944-115">Markera rutorna bredvid namnen på alla användare som du vill flytta.</span><span class="sxs-lookup"><span data-stu-id="8f944-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8f944-116">Välj **Fler alternativ** (**...**), högst upp på sidan och välj sedan **Ändra domäner**.</span><span class="sxs-lookup"><span data-stu-id="8f944-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="8f944-117">Välj en annan domän i fönstret **Ändra domäner.**</span><span class="sxs-lookup"><span data-stu-id="8f944-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="8f944-p103">Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.</span><span class="sxs-lookup"><span data-stu-id="8f944-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8f944-120">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>.</span><span class="sxs-lookup"><span data-stu-id="8f944-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="8f944-121">Välj **Aktiva användare av** > **användare**.</span><span class="sxs-lookup"><span data-stu-id="8f944-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8f944-122">Markera rutorna bredvid namnen på alla användare som du vill flytta.</span><span class="sxs-lookup"><span data-stu-id="8f944-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8f944-123">Högst upp på sidan väljer du **Fler** > **redigeringsdomäner**.</span><span class="sxs-lookup"><span data-stu-id="8f944-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="8f944-124">Välj en annan domän i fönstret **Redigera domäner.**</span><span class="sxs-lookup"><span data-stu-id="8f944-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="8f944-p104">Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.</span><span class="sxs-lookup"><span data-stu-id="8f944-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8f944-127">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.</span><span class="sxs-lookup"><span data-stu-id="8f944-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="8f944-128">Välj **Aktiva användare av** > **användare**.</span><span class="sxs-lookup"><span data-stu-id="8f944-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8f944-129">Markera rutorna bredvid namnen på alla användare som du vill flytta.</span><span class="sxs-lookup"><span data-stu-id="8f944-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8f944-130">Högst upp på sidan väljer du **Fler** > **redigeringsdomäner**.</span><span class="sxs-lookup"><span data-stu-id="8f944-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="8f944-131">Välj en annan domän i fönstret **Redigera domäner.**</span><span class="sxs-lookup"><span data-stu-id="8f944-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="8f944-p105">Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.</span><span class="sxs-lookup"><span data-stu-id="8f944-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="8f944-134">Flytta dig själv</span><span class="sxs-lookup"><span data-stu-id="8f944-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8f944-135">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="8f944-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8f944-136">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.</span><span class="sxs-lookup"><span data-stu-id="8f944-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="8f944-137">Gå till **Aktiva användare** **för användare** \> och välj ditt konto i listan.</span><span class="sxs-lookup"><span data-stu-id="8f944-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="8f944-138">Välj **Hantera användarnamn**på fliken **Konto** och välj sedan en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="8f944-139">Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="8f944-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8f944-140">Logga in med den nya domänen och samma lösenord.</span><span class="sxs-lookup"><span data-stu-id="8f944-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8f944-141">Du kan också använda PowerShell för att flytta användare till en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8f944-142">Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information.</span><span class="sxs-lookup"><span data-stu-id="8f944-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8f944-143">Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8f944-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8f944-144">Gå till **Aktiva användare** **för användare** \> och välj ditt namn i listan.</span><span class="sxs-lookup"><span data-stu-id="8f944-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="8f944-145">I avsnittet **Användarnamn/E-post** väljer du **Redigera**och väljer sedan en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="8f944-146">Välj **Ange som primär** > **Spara** > **nära**.</span><span class="sxs-lookup"><span data-stu-id="8f944-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="8f944-147">Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="8f944-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8f944-148">Logga in med den nya domänen och samma lösenord.</span><span class="sxs-lookup"><span data-stu-id="8f944-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8f944-149">Du kan också använda PowerShell för att flytta användare till en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8f944-150">Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information.</span><span class="sxs-lookup"><span data-stu-id="8f944-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8f944-151">Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8f944-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8f944-152">Gå till **Aktiva användare** **för användare** \> och välj ditt namn i listan.</span><span class="sxs-lookup"><span data-stu-id="8f944-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="8f944-153">I avsnittet **Användarnamn/E-post** väljer du **Redigera**och väljer sedan en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="8f944-154">Välj **Ange som primär** > **Spara** > **nära**.</span><span class="sxs-lookup"><span data-stu-id="8f944-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="8f944-155">Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="8f944-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8f944-156">Logga in med den nya domänen och samma lösenord.</span><span class="sxs-lookup"><span data-stu-id="8f944-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8f944-157">Du kan också använda PowerShell för att flytta användare till en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8f944-158">Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information.</span><span class="sxs-lookup"><span data-stu-id="8f944-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8f944-159">Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8f944-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="8f944-160">Steg 2: Flytta användare till en annan domän</span><span class="sxs-lookup"><span data-stu-id="8f944-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8f944-161">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8f944-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="8f944-162">Markera gruppnamnet och välj sedan **Redigera**på fliken **Allmänt** under **E-postadress.**</span><span class="sxs-lookup"><span data-stu-id="8f944-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="8f944-163">Använd listrutan för att välja en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8f944-164">Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8f944-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8f944-165">Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.</span><span class="sxs-lookup"><span data-stu-id="8f944-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8f944-166">Gå till sidan **Gruppergrupper** > **i** <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="8f944-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="8f944-167">Markera gruppnamnet och välj sedan **Redigera bredvid** **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8f944-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="8f944-168">Använd listrutan för att välja en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8f944-169">Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8f944-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8f944-170">Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.</span><span class="sxs-lookup"><span data-stu-id="8f944-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8f944-171">Gå till sidan **Gruppergrupper** > **i** <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="8f944-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="8f944-172">Markera gruppnamnet och välj sedan **Redigera bredvid** **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8f944-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="8f944-173">Använd listrutan för att välja en annan domän.</span><span class="sxs-lookup"><span data-stu-id="8f944-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8f944-174">Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8f944-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8f944-175">Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.</span><span class="sxs-lookup"><span data-stu-id="8f944-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="8f944-176">Steg 3: Ta bort den gamla domänen</span><span class="sxs-lookup"><span data-stu-id="8f944-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8f944-177">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="8f944-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8f944-178">Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="8f944-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8f944-179">Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="8f944-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="8f944-180">På sidan **Domäner** väljer du den domän som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="8f944-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="8f944-181">Välj **Ta bort**i den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="8f944-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="8f944-182">Följ eventuella ytterligare uppmaningar och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8f944-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="8f944-183">Hur länge dröjer det innan en domän tas bort?</span><span class="sxs-lookup"><span data-stu-id="8f944-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="8f944-184">Det kan ta så lite som 5 minuter för Microsoft 365 att ta bort en domän om den inte refereras på många platser som säkerhetsgrupper, distributionslistor, användare och Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="8f944-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="8f944-185">Om det finns många referenser till domänen kan det ta flera timmar (ett dygn) innan domänen tas bort.</span><span class="sxs-lookup"><span data-stu-id="8f944-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="8f944-p113">Om du har hundratals eller tusentals användare använder du PowerShell och letar upp alla användare och flyttar dem till en annan domän. Annars kan det hända att några användare missas i gränssnittet och när du sedan försöker ta bort domänen så går det inte och du kommer inte att veta varför. Mer information finns i [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8f944-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="8f944-190">Vill du ha mer hjälp?</span><span class="sxs-lookup"><span data-stu-id="8f944-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8f944-191">Du kan inte ta bort domänen [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) från ditt konto.</span><span class="sxs-lookup"><span data-stu-id="8f944-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="8f944-p114">Fungerar det fortfarande inte? Domänen kan behöva tas bort manuellt. [Ring oss](../contact-support-for-business-products.md) så kan vi hjälpa dig med det!</span><span class="sxs-lookup"><span data-stu-id="8f944-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="8f944-195">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="8f944-195">Related articles</span></span>

[<span data-ttu-id="8f944-196">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="8f944-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="8f944-197">Få hjälp med Office 365-domäner</span><span class="sxs-lookup"><span data-stu-id="8f944-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="8f944-198">Byta till ett annat Microsoft 365 för företag-abonnemang</span><span class="sxs-lookup"><span data-stu-id="8f944-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="8f944-199">Avbryt prenumerationen</span><span class="sxs-lookup"><span data-stu-id="8f944-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
