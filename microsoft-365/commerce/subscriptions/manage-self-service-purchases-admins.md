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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: Administratörer kan lära sig att hantera självbetjäning som görs av användare i organisationen.
ms.openlocfilehash: 59d64c047ddf4f33c2ef3277f3139f1b7692b891
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244998"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="a3c46-103">Hantera självbetjäningsköp (administratörer)</span><span class="sxs-lookup"><span data-stu-id="a3c46-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="a3c46-104">Som administratör kan du se köp av självbetjäning som görs av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="a3c46-105">Du ser produktnamn, inköpare, prenumerationer köpta, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäning köp.</span><span class="sxs-lookup"><span data-stu-id="a3c46-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="a3c46-106">Om det krävs av din organisation kan du inaktivera självbetjäning för köp per produkt via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3c46-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="a3c46-107">Du har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.</span><span class="sxs-lookup"><span data-stu-id="a3c46-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="a3c46-108">Du kan också ange om användarna i organisationen ska kunna göra självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="a3c46-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="a3c46-109">Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a3c46-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="a3c46-110">Visa prenumerationer med självbetjäning</span><span class="sxs-lookup"><span data-stu-id="a3c46-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a3c46-111">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="a3c46-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a3c46-112">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="a3c46-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a3c46-113">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="a3c46-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="a3c46-114">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="a3c46-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="a3c46-115">Om du vill visa mer information om en prenumeration väljer du en prenumeration i listan.</span><span class="sxs-lookup"><span data-stu-id="a3c46-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="a3c46-116">Visa vem som har licenser för en prenumeration med självbetjäning för köp av självbetjäning</span><span class="sxs-lookup"><span data-stu-id="a3c46-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="a3c46-117">Som administratör kan du inte tilldela eller ta bort licenser för en självbetjäningsprenumeration som köpts av en användare i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a3c46-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="a3c46-118">Du kan [ta över en självbetjäningsprenumeration](#take-over-a-self-service-purchase-subscription)och sedan tilldela eller ta bort licenser.</span><span class="sxs-lookup"><span data-stu-id="a3c46-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a3c46-119">Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3c46-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="a3c46-120">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3c46-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="a3c46-121">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenser</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a3c46-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="a3c46-122">Välj filterikonen och välj **sedan Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="a3c46-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="a3c46-123">Välj en produkt för att se licenser som är tilldelade till användare.</span><span class="sxs-lookup"><span data-stu-id="a3c46-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a3c46-124">Om det finns flera köp för en produkt visas  den produkten bara en gång och i kolumnen Tillgängligt antal visas totalt för alla prenumerationer som har köpts för den produkten.</span><span class="sxs-lookup"><span data-stu-id="a3c46-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="a3c46-125">Listan **Användare** grupperas efter namnen på personer som har gjort självbetjäning för inköp.</span><span class="sxs-lookup"><span data-stu-id="a3c46-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="a3c46-126">Om du vill exportera en lista med användare med licenser för de här prenumerationerna väljer du de prenumerationer som du vill exportera och väljer sedan **Exportera användare.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="a3c46-127">Inaktivera eller aktivera självbetjäning för köp</span><span class="sxs-lookup"><span data-stu-id="a3c46-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="a3c46-128">Du kan inaktivera eller aktivera självbetjäning för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="a3c46-129">**Modulen MSCommerce** PowerShell innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning och för vilka produkter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="a3c46-130">Du kan använda **modulen MSCommerce** PowerShell för att:</span><span class="sxs-lookup"><span data-stu-id="a3c46-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="a3c46-131">Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten</span><span class="sxs-lookup"><span data-stu-id="a3c46-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="a3c46-132">Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="a3c46-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="a3c46-133">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="a3c46-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="a3c46-134">Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a3c46-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="a3c46-135">Centralisera licenser under en enda prenumeration</span><span class="sxs-lookup"><span data-stu-id="a3c46-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="a3c46-136">Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer genom befintliga avtal för användare som tilldelas till självbetjäning för köp via självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="a3c46-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="a3c46-137">När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare avbryter sina befintliga prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="a3c46-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a3c46-138">I administrationscentret går du till sidan **Tjänster** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">för faktureringsköp.</a></span><span class="sxs-lookup"><span data-stu-id="a3c46-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a3c46-139">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringsköpstjänster.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a3c46-140">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringsköpstjänster.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="a3c46-141">Leta upp och välj den produkt du vill köpa och välj sedan **Köp**.</span><span class="sxs-lookup"><span data-stu-id="a3c46-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="a3c46-142">Genomför köpet i de återstående stegen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="a3c46-143">Följ stegen i Visa vem som har licenser för en [självbetjäning](#view-who-has-licenses-for-a-self-service-purchase-subscription) köpt prenumeration för att exportera en lista över användare att referera till i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="a3c46-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="a3c46-144">Tilldela licenser till alla som har en licens för den andra prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="a3c46-145">Fullständiga steg finns i [Tilldela licenser till användare.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="a3c46-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="a3c46-146">Kontakta personen som köpte självköpsprenumerationen och be honom eller henne [att avbryta den.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="a3c46-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="a3c46-147">Ta över en prenumeration på självbetjäning för köp</span><span class="sxs-lookup"><span data-stu-id="a3c46-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="a3c46-148">Du kan ta över en prenumeration på självbetjäning som gjorts av en användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="a3c46-149">När du tar över en prenumeration på självbetjäning har du två alternativ:</span><span class="sxs-lookup"><span data-stu-id="a3c46-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="a3c46-150">Flytta användarna till en annan prenumeration och avbryt den ursprungliga prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="a3c46-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="a3c46-151">Avbryt prenumerationen på självbetjäning för köp och ta bort licenser från tilldelade användare.</span><span class="sxs-lookup"><span data-stu-id="a3c46-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="a3c46-152">Flytta användare till en annan prenumeration</span><span class="sxs-lookup"><span data-stu-id="a3c46-152">Move users to a different subscription</span></span>

<span data-ttu-id="a3c46-153">När du flyttar användare till en annan prenumeration avbryts den gamla prenumerationen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="a3c46-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="a3c46-154">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="a3c46-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="a3c46-155">Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.</span><span class="sxs-lookup"><span data-stu-id="a3c46-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a3c46-156">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="a3c46-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a3c46-157">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a3c46-158">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="a3c46-159">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="a3c46-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="a3c46-160">Välj den prenumeration som du vill ta över.</span><span class="sxs-lookup"><span data-stu-id="a3c46-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="a3c46-161">Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="a3c46-162">Välj Flytta användare i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="a3c46-163">Välj den produkt som du vill flytta användarna till och välj sedan **Flytta användare.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="a3c46-164">Välj **Flytta användare i** rutan **Flytta användare till.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="a3c46-165">Flytten kan ta flera minuter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-165">The move process might take several minutes.</span></span> <span data-ttu-id="a3c46-166">Stäng inte webbläsaren medan processen körs.</span><span class="sxs-lookup"><span data-stu-id="a3c46-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="a3c46-167">När flyttningsprocessen är klar stänger du **fönstret Flytta slutförd .**</span><span class="sxs-lookup"><span data-stu-id="a3c46-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="a3c46-168">På sidan prenumerationsinformation visas **prenumerationsstatusen** för den köpta självbetjäningsprenumerationen som **Borttagna.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="a3c46-169">Avbryta en prenumeration på köp via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="a3c46-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="a3c46-170">När du väljer att avbryta en prenumeration på självköp förlorar användare med licenser åtkomsten till produkten.</span><span class="sxs-lookup"><span data-stu-id="a3c46-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="a3c46-171">Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="a3c46-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a3c46-172">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="a3c46-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a3c46-173">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a3c46-174">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.</span><span class="sxs-lookup"><span data-stu-id="a3c46-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="a3c46-175">På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="a3c46-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="a3c46-176">Välj den prenumeration du vill avsluta.</span><span class="sxs-lookup"><span data-stu-id="a3c46-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="a3c46-177">Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="a3c46-178">I den högra rutan väljer du **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="a3c46-179">Välj en orsak för att avsluta prenumerationen i listrutan och välj sedan **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="a3c46-180">I rutan **Vill du avbryta? väljer** du Avbryt **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="a3c46-181">Stäng det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="a3c46-181">Close the right pane.</span></span>
9. <span data-ttu-id="a3c46-182">På sidan prenumerationsinformation visas **prenumerationsstatusen** **Borttagna.**</span><span class="sxs-lookup"><span data-stu-id="a3c46-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="a3c46-183">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="a3c46-183">Need help?</span></span> <span data-ttu-id="a3c46-184">Kontakta oss.</span><span class="sxs-lookup"><span data-stu-id="a3c46-184">Contact us.</span></span>

<span data-ttu-id="a3c46-185">Vanliga frågor om självbetjäning för köp finns i Vanliga frågor [och svar om självbetjäning.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a3c46-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="a3c46-186">Om du har frågor eller behöver hjälp med köp via självbetjäning kontaktar [du supporten.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="a3c46-186">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>