---
title: Hantera köp via självbetjäning (administratörer)
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
description: Administratörer kan lära sig att hantera självbetjäning som görs av användare i organisationen.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920186"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="31a9d-103">Hantera självbetjäningsköp (administratörer)</span><span class="sxs-lookup"><span data-stu-id="31a9d-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="31a9d-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="31a9d-104">The admin center is changing.</span></span> <span data-ttu-id="31a9d-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="31a9d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="31a9d-106">Som administratör kan du se köp av självbetjäning som görs av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="31a9d-107">Du ser produktnamn, inköpare, prenumerationer köpta, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäning köp.</span><span class="sxs-lookup"><span data-stu-id="31a9d-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="31a9d-108">Om det krävs av din organisation kan du inaktivera självbetjäning för köp per produkt via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31a9d-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="31a9d-109">Du har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.</span><span class="sxs-lookup"><span data-stu-id="31a9d-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="31a9d-110">Du kan också ange om användarna i organisationen ska kunna göra självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="31a9d-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="31a9d-111">Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="31a9d-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="31a9d-112">Visa prenumerationer med självbetjäning</span><span class="sxs-lookup"><span data-stu-id="31a9d-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="31a9d-113">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="31a9d-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="31a9d-114">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="31a9d-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="31a9d-115">Om du vill visa mer information om en prenumeration väljer du en prenumeration i listan.</span><span class="sxs-lookup"><span data-stu-id="31a9d-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="31a9d-116">Visa vem som har licenser för en prenumeration med självbetjäning för köp av självbetjäning</span><span class="sxs-lookup"><span data-stu-id="31a9d-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="31a9d-117">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser.</a></span><span class="sxs-lookup"><span data-stu-id="31a9d-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="31a9d-118">Välj filterikonen och välj **sedan Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="31a9d-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="31a9d-119">Välj en produkt för att se licenser som är tilldelade till användare.</span><span class="sxs-lookup"><span data-stu-id="31a9d-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="31a9d-120">Om det finns flera köp för en produkt visas  den produkten bara en gång och i kolumnen Tillgängligt antal visas totalt för alla prenumerationer som har köpts för den produkten.</span><span class="sxs-lookup"><span data-stu-id="31a9d-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="31a9d-121">Listan **Användare** grupperas efter namnen på personer som har gjort självbetjäning för inköp.</span><span class="sxs-lookup"><span data-stu-id="31a9d-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="31a9d-122">Om du vill exportera en lista med användare med licenser för de här prenumerationerna väljer du de prenumerationer som du vill exportera och väljer sedan **Exportera användare.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="31a9d-123">Inaktivera eller aktivera självbetjäning för köp</span><span class="sxs-lookup"><span data-stu-id="31a9d-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="31a9d-124">Du kan inaktivera eller aktivera självbetjäning för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="31a9d-125">**Modulen MSCommerce** PowerShell innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning och för vilka produkter.</span><span class="sxs-lookup"><span data-stu-id="31a9d-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="31a9d-126">Du kan använda **modulen MSCommerce** PowerShell för att:</span><span class="sxs-lookup"><span data-stu-id="31a9d-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="31a9d-127">Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten</span><span class="sxs-lookup"><span data-stu-id="31a9d-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="31a9d-128">Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="31a9d-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="31a9d-129">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="31a9d-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="31a9d-130">Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="31a9d-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="31a9d-131">Centralisera licenser under en enda prenumeration</span><span class="sxs-lookup"><span data-stu-id="31a9d-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="31a9d-132">Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer genom befintliga avtal för användare som tilldelas till självbetjäning för köp via självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="31a9d-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="31a9d-133">När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare avbryter sina befintliga prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="31a9d-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="31a9d-134">I administrationscentret går du till sidan **Tjänster** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">för faktureringsköp.</a></span><span class="sxs-lookup"><span data-stu-id="31a9d-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="31a9d-135">Leta upp och välj den produkt du vill köpa och välj sedan **Köp**.</span><span class="sxs-lookup"><span data-stu-id="31a9d-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="31a9d-136">Genomför köpet i de återstående stegen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="31a9d-137">Följ stegen i Visa vem som har licenser för en [självbetjäning](#view-who-has-licenses-for-a-self-service-purchase-subscription) köpt prenumeration för att exportera en lista över användare att referera till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="31a9d-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="31a9d-138">Tilldela licenser till alla som har en licens för den andra prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="31a9d-139">Fullständiga steg finns i [Tilldela licenser till användare.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="31a9d-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="31a9d-140">Kontakta personen som köpte självköpsprenumerationen och be honom eller henne [att avbryta den.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="31a9d-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="31a9d-141">Ta över en prenumeration på självbetjäning för köp</span><span class="sxs-lookup"><span data-stu-id="31a9d-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="31a9d-142">Du kan ta över en prenumeration på självbetjäning som gjorts av en användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="31a9d-143">När du tar över en prenumeration på självbetjäning har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="31a9d-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="31a9d-144">Flytta användarna till en annan prenumeration och avbryt den ursprungliga prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="31a9d-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="31a9d-145">Avbryt prenumerationen på självbetjäning för köp och ta bort licenser från tilldelade användare.</span><span class="sxs-lookup"><span data-stu-id="31a9d-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="31a9d-146">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="31a9d-146">Move users to a different subscription</span></span>

<span data-ttu-id="31a9d-147">När du flyttar användare till en annan prenumeration avbryts den gamla prenumerationen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="31a9d-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="31a9d-148">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="31a9d-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="31a9d-149">Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.</span><span class="sxs-lookup"><span data-stu-id="31a9d-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="31a9d-150">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="31a9d-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="31a9d-151">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="31a9d-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="31a9d-152">Välj den prenumeration som du vill ta över.</span><span class="sxs-lookup"><span data-stu-id="31a9d-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="31a9d-153">Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="31a9d-154">Välj Flytta användare i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="31a9d-155">Välj den produkt som du vill flytta användarna till och välj sedan **Flytta användare.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="31a9d-156">Välj **Flytta användare i** rutan **Flytta användare till.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="31a9d-157">Flytten kan ta flera minuter.</span><span class="sxs-lookup"><span data-stu-id="31a9d-157">The move process might take several minutes.</span></span> <span data-ttu-id="31a9d-158">Stäng inte webbläsaren medan processen körs.</span><span class="sxs-lookup"><span data-stu-id="31a9d-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="31a9d-159">När flyttningsprocessen är klar stänger du **fönstret Flytta slutförd .**</span><span class="sxs-lookup"><span data-stu-id="31a9d-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="31a9d-160">På sidan prenumerationsinformation visas **prenumerationsstatusen** för den köpta självbetjäningsprenumerationen som **Borttagna.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="31a9d-161">Avbryta en prenumeration på köp via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="31a9d-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="31a9d-162">När du väljer att avbryta en prenumeration på självköp förlorar användare med licenser åtkomsten till produkten.</span><span class="sxs-lookup"><span data-stu-id="31a9d-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="31a9d-163">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="31a9d-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="31a9d-164">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="31a9d-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="31a9d-165">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="31a9d-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="31a9d-166">Välj den prenumeration du vill avsluta.</span><span class="sxs-lookup"><span data-stu-id="31a9d-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="31a9d-167">Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="31a9d-168">I den högra rutan väljer du **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="31a9d-169">Välj en orsak för att avsluta prenumerationen i listrutan och välj sedan **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="31a9d-170">I rutan **Vill du avbryta? väljer** du Avbryt **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="31a9d-171">Stäng det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="31a9d-171">Close the right pane.</span></span>
9. <span data-ttu-id="31a9d-172">På sidan prenumerationsinformation visas **prenumerationsstatusen** **Borttagna.**</span><span class="sxs-lookup"><span data-stu-id="31a9d-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="31a9d-173">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="31a9d-173">Need help?</span></span> <span data-ttu-id="31a9d-174">Kontakta oss.</span><span class="sxs-lookup"><span data-stu-id="31a9d-174">Contact us.</span></span>

<span data-ttu-id="31a9d-175">Vanliga frågor om självbetjäning för köp finns i Vanliga frågor [och svar om självbetjäning.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="31a9d-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="31a9d-176">Om du har frågor eller behöver hjälp med köp via självbetjäning kontaktar [du supporten.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="31a9d-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>