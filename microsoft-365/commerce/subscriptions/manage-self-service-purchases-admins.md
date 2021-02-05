---
title: Hantera självbetjäning för köp (administratörer)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Administratörer kan lära sig hur de hanterar självbetjäning som görs av användare i organisationen.
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114699"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="030e5-103">Hantera självbetjäningsköp (administratörer)</span><span class="sxs-lookup"><span data-stu-id="030e5-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="030e5-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="030e5-104">The admin center is changing.</span></span> <span data-ttu-id="030e5-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="030e5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="030e5-106">Som administratör kan du se självbetjäning som gjorts av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="030e5-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="030e5-107">Du ser produktnamnet, inköparens namn, prenumerationer som köpts, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="030e5-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="030e5-108">Om det krävs av din organisation kan du inaktivera självbetjäning för köp per produkt via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="030e5-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="030e5-109">Du har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.</span><span class="sxs-lookup"><span data-stu-id="030e5-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="030e5-110">Du kan också styra om användarna i organisationen ska kunna göra självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="030e5-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="030e5-111">Mer information finns i [Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="030e5-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="030e5-112">Visa prenumerationer med självbetjäning</span><span class="sxs-lookup"><span data-stu-id="030e5-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="030e5-113">Gå till sidan Fakturering för dina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produkter i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="030e5-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="030e5-114">Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**</span><span class="sxs-lookup"><span data-stu-id="030e5-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="030e5-115">Om du vill visa mer information om en prenumeration väljer du en prenumeration i listan.</span><span class="sxs-lookup"><span data-stu-id="030e5-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="030e5-116">Visa vem som har licenser för en prenumeration på självbetjäning</span><span class="sxs-lookup"><span data-stu-id="030e5-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="030e5-117">Gå till sidan Faktureringslicenser **i**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="030e5-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="030e5-118">Välj filterikonen och välj sedan **Självbetjäning.**</span><span class="sxs-lookup"><span data-stu-id="030e5-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="030e5-119">Välj en produkt om du vill se licenser tilldelade till användare.</span><span class="sxs-lookup"><span data-stu-id="030e5-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="030e5-120">Om det finns flera köp för en produkt visas  den produkten bara en gång och i kolumnen Tillgängligt antal visas totalt för alla prenumerationer som har köpts för den produkten.</span><span class="sxs-lookup"><span data-stu-id="030e5-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="030e5-121">**Användarlistan** är grupperad efter namnen på personer som har gjort självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="030e5-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="030e5-122">Om du vill exportera en lista med användare med licenser för dessa prenumerationer väljer du de prenumerationer du vill exportera och väljer sedan **Exportera användare.**</span><span class="sxs-lookup"><span data-stu-id="030e5-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="030e5-123">Inaktivera eller aktivera självbetjäning för köp</span><span class="sxs-lookup"><span data-stu-id="030e5-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="030e5-124">Du kan inaktivera eller aktivera självbetjäning för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="030e5-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="030e5-125">**MsCommerce** PowerShell-modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra självbetjäningsköp och för vilka produkter.</span><span class="sxs-lookup"><span data-stu-id="030e5-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="030e5-126">Du kan använda **MSCommerce** PowerShell-modulen för att:</span><span class="sxs-lookup"><span data-stu-id="030e5-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="030e5-127">Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten</span><span class="sxs-lookup"><span data-stu-id="030e5-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="030e5-128">Visa en lista över tillämpliga produkter och om självbetjäning för köp har aktiverats eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="030e5-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="030e5-129">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="030e5-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="030e5-130">Mer information finns i [Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="030e5-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="030e5-131">Centralisera licenser under en enda prenumeration</span><span class="sxs-lookup"><span data-stu-id="030e5-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="030e5-132">Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer genom befintliga avtal för användare som tilldelats till självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="030e5-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="030e5-133">När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare avbryter sina befintliga prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="030e5-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="030e5-134">Gå till sidan För **faktureringsköp** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="030e5-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="030e5-135">Leta upp och välj den produkt du vill köpa och välj sedan **Köp.**</span><span class="sxs-lookup"><span data-stu-id="030e5-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="030e5-136">Slutför de återstående stegen för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="030e5-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="030e5-137">Följ stegen i [Visa vem som har licenser](#view-who-has-licenses-for-a-self-service-purchase-subscription) för en självbetjänad prenumeration för att exportera en lista med användare som du vill referera till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="030e5-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="030e5-138">Tilldela licenser till alla som har en licens för den andra prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="030e5-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="030e5-139">Fullständiga steg finns i [Tilldela licenser till användare.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="030e5-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="030e5-140">Kontakta personen som köpte prenumerationen på självbetjäning och be [honom/henne att avbryta den.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="030e5-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="030e5-141">Ta över en prenumeration på självbetjäning</span><span class="sxs-lookup"><span data-stu-id="030e5-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="030e5-142">Du kan ta över en prenumeration på självbetjäning som gjorts av en användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="030e5-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="030e5-143">När du tar över en prenumeration på självbetjäning har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="030e5-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="030e5-144">Flytta användarna till en annan prenumeration och avbryt den ursprungliga prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="030e5-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="030e5-145">Avbryt självbetjäningsprenumerationen och ta bort licenser från tilldelade användare.</span><span class="sxs-lookup"><span data-stu-id="030e5-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="030e5-146">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="030e5-146">Move users to a different subscription</span></span>

<span data-ttu-id="030e5-147">När du flyttar användare till en annan prenumeration avbryts den gamla prenumerationen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="030e5-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="030e5-148">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="030e5-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="030e5-149">Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.</span><span class="sxs-lookup"><span data-stu-id="030e5-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="030e5-150">Gå till sidan Fakturering för dina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produkter i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="030e5-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="030e5-151">Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**</span><span class="sxs-lookup"><span data-stu-id="030e5-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="030e5-152">Välj den prenumeration du vill ta över.</span><span class="sxs-lookup"><span data-stu-id="030e5-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="030e5-153">Välj Ta kontroll över den här prenumerationen **i avsnittet** Prenumerationer och inställningar på **sidan Prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="030e5-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="030e5-154">Välj Flytta användare i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="030e5-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="030e5-155">Markera den produkt som du vill flytta användarna till och välj sedan **Flytta användare.**</span><span class="sxs-lookup"><span data-stu-id="030e5-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="030e5-156">Välj **Flytta användare i** rutan Flytta **användare till.**</span><span class="sxs-lookup"><span data-stu-id="030e5-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="030e5-157">Flyttningsprocessen kan ta flera minuter.</span><span class="sxs-lookup"><span data-stu-id="030e5-157">The move process might take several minutes.</span></span> <span data-ttu-id="030e5-158">Stäng inte webbläsaren medan processen körs.</span><span class="sxs-lookup"><span data-stu-id="030e5-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="030e5-159">Stäng den slutförda rutan Flytta när **flyttningsprocessen är klar.**</span><span class="sxs-lookup"><span data-stu-id="030e5-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="030e5-160">Prenumerationsstatusen för **självbetjäning** köpta prenumerationer visas som Borttagna på **sidan prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="030e5-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="030e5-161">Avbryta en prenumeration på självbetjäning</span><span class="sxs-lookup"><span data-stu-id="030e5-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="030e5-162">När du väljer att avbryta en prenumeration på självbetjäning förlorar användare med licenser åtkomsten till produkten.</span><span class="sxs-lookup"><span data-stu-id="030e5-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="030e5-163">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="030e5-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="030e5-164">Gå till sidan Fakturering för dina produkter  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="030e5-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="030e5-165">Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**</span><span class="sxs-lookup"><span data-stu-id="030e5-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="030e5-166">Välj den prenumeration som du vill avbryta.</span><span class="sxs-lookup"><span data-stu-id="030e5-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="030e5-167">Välj Ta kontroll över den här prenumerationen **i avsnittet** Prenumerationer och inställningar på **sidan Prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="030e5-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="030e5-168">I den högra rutan väljer du **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="030e5-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="030e5-169">Välj en orsak till att du avslutar prenumerationen i listrutan och välj sedan **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="030e5-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="030e5-170">I rutan **Vill du avbryta? väljer** du Avbryt **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="030e5-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="030e5-171">Stäng det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="030e5-171">Close the right pane.</span></span>
9. <span data-ttu-id="030e5-172">Prenumerationsstatus visas som **Borttagna** på sidan **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="030e5-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="030e5-173">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="030e5-173">Need help?</span></span> <span data-ttu-id="030e5-174">Kontakta oss.</span><span class="sxs-lookup"><span data-stu-id="030e5-174">Contact us.</span></span>

<span data-ttu-id="030e5-175">Vanliga frågor om självbetjäning för köp finns i Vanliga frågor och svar [om självbetjäning.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="030e5-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="030e5-176">Om du har frågor eller behöver hjälp med självbetjäning kan [du kontakta support.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="030e5-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>