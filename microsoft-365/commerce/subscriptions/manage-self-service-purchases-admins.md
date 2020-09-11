---
title: Hantera självbetjänings köp (administratörer)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Administratörer kan lära sig att hantera självbetjänings köp som görs av användare i organisationen.
ms.openlocfilehash: f10f525f8efc6bc63e2fa042c299a6d03c77d0cb
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430004"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="4b731-103">Hantera självbetjäningsköp (administratörer)</span><span class="sxs-lookup"><span data-stu-id="4b731-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4b731-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="4b731-104">The admin center is changing.</span></span> <span data-ttu-id="4b731-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4b731-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4b731-106">Som administratör kan du se självbetjänings köp som görs av personer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="4b731-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="4b731-107">Du ser produkt namn, köpar namn, köpta abonnemang, utgångs datum, inköps pris och tilldelade användare för varje själv service-inköp.</span><span class="sxs-lookup"><span data-stu-id="4b731-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="4b731-108">Om organisationen kräver det, kan du stänga av självbetjänings köp per produkt med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b731-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="4b731-109">Du har samma data hanterings-och åtkomst principer som gäller för produkter som köpts via eget köp eller centralt.</span><span class="sxs-lookup"><span data-stu-id="4b731-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="4b731-110">Du kan också kontrol lera om användare i din organisation kan göra självbetjänings köp.</span><span class="sxs-lookup"><span data-stu-id="4b731-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="4b731-111">Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4b731-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="4b731-112">Visa självbetjänings abonnemang</span><span class="sxs-lookup"><span data-stu-id="4b731-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="4b731-113">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="4b731-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="4b731-114">Bredvid **förfina resultat**väljer du **själv tjänst**i list rutan **Kontotyp** .</span><span class="sxs-lookup"><span data-stu-id="4b731-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>
3. <span data-ttu-id="4b731-115">Om du vill visa mer information om ett abonnemang väljer du en i listan.</span><span class="sxs-lookup"><span data-stu-id="4b731-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="4b731-116">Visa vem som har licenser för ett självbetjänings abonnemang</span><span class="sxs-lookup"><span data-stu-id="4b731-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="4b731-117">Gå till sidan för **fakturerings**licenser i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="4b731-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="4b731-118">Välj filter ikonen och välj sedan **själv service**.</span><span class="sxs-lookup"><span data-stu-id="4b731-118">Choose the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="4b731-119">Välj en produkt för att se licenser tilldelade till personer.</span><span class="sxs-lookup"><span data-stu-id="4b731-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4b731-120">Om det finns flera köp för en produkt visas produkten endast en gång och kolumnen **disponibelt antal** visar summan av alla abonnemang som har köpts för produkten.</span><span class="sxs-lookup"><span data-stu-id="4b731-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="4b731-121">Listan **användare** är grupperad efter namnen på personer som gjorde själv service inköp.</span><span class="sxs-lookup"><span data-stu-id="4b731-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="4b731-122">Om du vill exportera en lista över användare med licenser för dessa prenumerationer väljer du de abonnemang som du vill exportera och väljer sedan **exportera användare**.</span><span class="sxs-lookup"><span data-stu-id="4b731-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="4b731-123">Inaktivera eller aktivera självbetjänings köp</span><span class="sxs-lookup"><span data-stu-id="4b731-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="4b731-124">Du kan inaktivera eller aktivera självbetjänings köp för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4b731-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="4b731-125">**MSCommerce** PowerShell-modulen innehåller ett **PolicyID** parameter värde för **AllowSelfServicePurchase** där du kan kontrol lera om användare i din organisation kan göra självbetjänings köp och för vilka produkter.</span><span class="sxs-lookup"><span data-stu-id="4b731-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="4b731-126">Du kan använda **MSCommerce** PowerShell-modulen till att:</span><span class="sxs-lookup"><span data-stu-id="4b731-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="4b731-127">Visa standard tillståndet för parametervärdet för **AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten</span><span class="sxs-lookup"><span data-stu-id="4b731-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="4b731-128">Visa en lista över tillämpliga produkter och om självbetjänings inköp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="4b731-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="4b731-129">Visa eller ändra den aktuella inställningen för en viss produkt för att aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="4b731-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="4b731-130">Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4b731-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="4b731-131">Centralisera licenser under en enda prenumeration</span><span class="sxs-lookup"><span data-stu-id="4b731-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="4b731-132">Du kan tilldela befintliga licenser eller köpa ytterligare abonnemang genom befintliga avtal för användare tilldelade till självbetjänings köp.</span><span class="sxs-lookup"><span data-stu-id="4b731-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="4b731-133">När du har kopplat dessa licenser kan du begära att dessa inköpare annullerar sina befintliga abonnemang.</span><span class="sxs-lookup"><span data-stu-id="4b731-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="4b731-134">Logga in i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret</a> med ditt konto för global administratör eller fakturerings administratör.</span><span class="sxs-lookup"><span data-stu-id="4b731-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>
2. <span data-ttu-id="4b731-135">Gå till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Köp tjänster</a> .</span><span class="sxs-lookup"><span data-stu-id="4b731-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
3. <span data-ttu-id="4b731-136">Leta reda på och välj den produkt som du vill köpa och välj sedan **köp**.</span><span class="sxs-lookup"><span data-stu-id="4b731-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
4. <span data-ttu-id="4b731-137">Utför resten av stegen för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="4b731-137">Complete the remaining steps to complete your purchase.</span></span>
5. <span data-ttu-id="4b731-138">Följ stegen i [Visa vilka som har licenser för en självbetjänings prenumeration](#view-who-has-licenses-for-a-self-service-purchase-subscription) för att exportera en lista med användare som ska referera till i steg 6.</span><span class="sxs-lookup"><span data-stu-id="4b731-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>
6. <span data-ttu-id="4b731-139">Tilldela licenser till alla som har en licens i det andra abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="4b731-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="4b731-140">Fullständiga anvisningar finns i [tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="4b731-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
7. <span data-ttu-id="4b731-141">Kontakta den person som köpte självbetjänings abonnemanget och be dem att annullera det.</span><span class="sxs-lookup"><span data-stu-id="4b731-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="4b731-142">Ta över ett självbetjänings abonnemang</span><span class="sxs-lookup"><span data-stu-id="4b731-142">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="4b731-143">Du kan ta över ett abonnemang för självbetjäning som görs av en användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4b731-143">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="4b731-144">När du tar över ett själv service abonnemang har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="4b731-144">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="4b731-145">Flytta användarna till ett annat abonnemang och Avbryt det ursprungliga abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="4b731-145">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="4b731-146">Avbryt självbetjänings abonnemanget och ta bort licenser från tilldelade användare.</span><span class="sxs-lookup"><span data-stu-id="4b731-146">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="4b731-147">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="4b731-147">Move users to a different subscription</span></span>

<span data-ttu-id="4b731-148">När du flyttar användare till ett annat abonnemang avbryts det gamla abonnemanget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4b731-148">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="4b731-149">Den användare som ursprungligen köpte självbetjänings köpet får ett e-postmeddelande om att abonnemanget har annullerats.</span><span class="sxs-lookup"><span data-stu-id="4b731-149">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="4b731-150">Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.</span><span class="sxs-lookup"><span data-stu-id="4b731-150">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="4b731-151">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="4b731-151">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="4b731-152">På fliken **produkter** väljer du filter ikonen och sedan **själv service**.</span><span class="sxs-lookup"><span data-stu-id="4b731-152">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="4b731-153">Välj den prenumeration som du vill ta över.</span><span class="sxs-lookup"><span data-stu-id="4b731-153">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="4b731-154">På sidan prenumerations information i avsnittet **prenumerationer och inställningar** väljer du **ta kontroll för det här abonnemanget**.</span><span class="sxs-lookup"><span data-stu-id="4b731-154">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="4b731-155">I det högra fönstret väljer **du flytta användare**.</span><span class="sxs-lookup"><span data-stu-id="4b731-155">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="4b731-156">Välj den produkt som du vill flytta användarna till och välj sedan **flytta användare**.</span><span class="sxs-lookup"><span data-stu-id="4b731-156">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="4b731-157">I rutan **flytta användare till väljer du** **flytta användare**.</span><span class="sxs-lookup"><span data-stu-id="4b731-157">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="4b731-158">Det kan ta flera minuter att flytta.</span><span class="sxs-lookup"><span data-stu-id="4b731-158">The move process might take several minutes.</span></span> <span data-ttu-id="4b731-159">Stäng inte webbläsaren medan processen körs.</span><span class="sxs-lookup"><span data-stu-id="4b731-159">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="4b731-160">När flytt processen är klar stänger du **fönstret flytta slutfört**.</span><span class="sxs-lookup"><span data-stu-id="4b731-160">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="4b731-161">På sidan prenumerations information visas **prenumerations statusen** för det självbetjänings abonnemang som har **tagits bort**.</span><span class="sxs-lookup"><span data-stu-id="4b731-161">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="4b731-162">Avbryta ett självbetjänings abonnemang</span><span class="sxs-lookup"><span data-stu-id="4b731-162">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="4b731-163">När du väljer att avbryta ett abonnemang för självbetjäning, förlorar användare med licenser åtkomst till produkten.</span><span class="sxs-lookup"><span data-stu-id="4b731-163">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="4b731-164">Den användare som ursprungligen köpte självbetjänings köpet får ett e-postmeddelande om att abonnemanget har annullerats.</span><span class="sxs-lookup"><span data-stu-id="4b731-164">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="4b731-165">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="4b731-165">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="4b731-166">På fliken **produkter** väljer du filter ikonen och sedan **själv service**.</span><span class="sxs-lookup"><span data-stu-id="4b731-166">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="4b731-167">Välj den prenumeration som du vill avbryta.</span><span class="sxs-lookup"><span data-stu-id="4b731-167">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="4b731-168">På sidan prenumerations information i avsnittet **prenumerationer och inställningar** väljer du **ta kontroll för det här abonnemanget**.</span><span class="sxs-lookup"><span data-stu-id="4b731-168">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="4b731-169">I det högra fönstret väljer du **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="4b731-169">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="4b731-170">Välj en anledning till annulleringen i list rutan och välj sedan **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="4b731-170">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="4b731-171">I rutan **är du säker på att du vill avbryta?** väljer du **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="4b731-171">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="4b731-172">Stänga fönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="4b731-172">Close the right pane.</span></span>
9. <span data-ttu-id="4b731-173">På sidan prenumerations information visas **prenumerationens status** som **borttagen**.</span><span class="sxs-lookup"><span data-stu-id="4b731-173">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="4b731-174">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="4b731-174">Need help?</span></span> <span data-ttu-id="4b731-175">Kontakta oss.</span><span class="sxs-lookup"><span data-stu-id="4b731-175">Contact us.</span></span>

<span data-ttu-id="4b731-176">Vanliga frågor om självbetjänings köp finns i [vanliga frågor och svar om inköp](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4b731-176">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="4b731-177">Om du har frågor eller behöver hjälp med självbetjänings köp kan du [kontakta supporten](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="4b731-177">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>