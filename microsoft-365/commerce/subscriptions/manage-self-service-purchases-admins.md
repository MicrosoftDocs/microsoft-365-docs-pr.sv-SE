---
title: Hantera självbetjäningsköp (administratörer)
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
search.appverid:
- MET150
description: Administratörer kan lära sig att hantera självbetjäningsköp som görs av användare i organisationen.
ms.openlocfilehash: 991dc87c40f41a6cbd2f1c08d4bc72bbb34d28f1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141156"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="f30a2-103">Hantera självbetjäningsköp (administratörer)</span><span class="sxs-lookup"><span data-stu-id="f30a2-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f30a2-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="f30a2-104">The admin center is changing.</span></span> <span data-ttu-id="f30a2-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f30a2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f30a2-106">Som administratör kan du se självbetjäningsköp som görs av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f30a2-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="f30a2-107">Du kan se produkten, köparens namn, köpta prenumerationer, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="f30a2-107">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="f30a2-108">Om det behövs för din organisation kan du inaktivera självbetjäningsköp per produkt via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f30a2-108">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="f30a2-109">Du har samma datahanterings- och åtkomstpolicyer över produkter som köpts via självbetjäningsköp eller centralt.</span><span class="sxs-lookup"><span data-stu-id="f30a2-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="f30a2-110">Du kan också styra om användare i organisationen kan göra självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="f30a2-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="f30a2-111">Mer information finns i [Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f30a2-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="f30a2-112">Visa självbetjäningsprenumerationer</span><span class="sxs-lookup"><span data-stu-id="f30a2-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="f30a2-113">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="f30a2-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="f30a2-114">Välj **Självbetjäning**i listrutan **Kontotyp** bredvid **Förfina**resultat .</span><span class="sxs-lookup"><span data-stu-id="f30a2-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="f30a2-115">Om du vill visa mer information om en prenumeration väljer du en i listan.</span><span class="sxs-lookup"><span data-stu-id="f30a2-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="f30a2-116">Visa vem som har licenser för en självbetjäningsköpsprenumeration</span><span class="sxs-lookup"><span data-stu-id="f30a2-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="f30a2-117">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="f30a2-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="f30a2-118">Välj filterikonen och välj sedan **Självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="f30a2-118">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="f30a2-119">Välj en produkt om du vill visa licenser som tilldelats personer.</span><span class="sxs-lookup"><span data-stu-id="f30a2-119">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f30a2-120">Om det finns flera inköp för en produkt visas den produkten bara en gång och kolumnen **Tillgänglig kvantitet** visar summan av alla prenumerationer som köpts för den produkten.</span><span class="sxs-lookup"><span data-stu-id="f30a2-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="f30a2-121">**Listan Användare** grupperas efter namnen på personer som gjort självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="f30a2-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="f30a2-122">Om du vill exportera en lista över användare med licenser för dessa prenumerationer väljer du de prenumerationer som du vill exportera och väljer sedan **Exportera användare**.</span><span class="sxs-lookup"><span data-stu-id="f30a2-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="f30a2-123">Inaktivera eller aktivera självbetjäningsköp</span><span class="sxs-lookup"><span data-stu-id="f30a2-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="f30a2-124">Du kan inaktivera eller aktivera självbetjäningsköp för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f30a2-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="f30a2-125">**MSCommerce** PowerShell-modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som låter dig styra om användare i organisationen kan göra självbetjäningsköp och för vilka produkter.</span><span class="sxs-lookup"><span data-stu-id="f30a2-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="f30a2-126">Du kan använda **MSCommerce** PowerShell-modulen för att:</span><span class="sxs-lookup"><span data-stu-id="f30a2-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="f30a2-127">Visa standardtillståndet för parametervärdet &mdash; Tillåt **självtjänstköpa** om det är aktiverat eller inaktiverat av produkten</span><span class="sxs-lookup"><span data-stu-id="f30a2-127">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="f30a2-128">Visa en lista över tillämpliga produkter och om självbetjäningsköp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="f30a2-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="f30a2-129">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="f30a2-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="f30a2-130">Mer information finns i [Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f30a2-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="f30a2-131">Centralisera licenser under en enda prenumeration</span><span class="sxs-lookup"><span data-stu-id="f30a2-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="f30a2-132">Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer via befintliga avtal för användare som tilldelats självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="f30a2-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="f30a2-133">När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare säger upp sina befintliga prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="f30a2-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="f30a2-134">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a> med ditt globala administratörs- eller faktureringsadministratörskonto.</span><span class="sxs-lookup"><span data-stu-id="f30a2-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="f30a2-135">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Faktureringsköpstjänster.</a> **Billing**</span><span class="sxs-lookup"><span data-stu-id="f30a2-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="f30a2-136">Hitta och välj den produkt som du vill köpa och välj sedan **Köp.**</span><span class="sxs-lookup"><span data-stu-id="f30a2-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="f30a2-137">Slutför de återstående stegen för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="f30a2-137">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="f30a2-138">Följ stegen i [Visa vem som har licenser för en självbetjäningsköpt prenumeration för](#view-who-has-licenses-for-a-self-service-purchase-subscription) att exportera en lista över användare som ska referera till i steg 6.</span><span class="sxs-lookup"><span data-stu-id="f30a2-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="f30a2-139">Tilldela licenser till alla som har en licens i den andra prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="f30a2-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="f30a2-140">Fullständiga steg finns i [Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="f30a2-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="f30a2-141">Kontakta personen som köpte självbetjäningsköpsprenumerationen och be dem att avbryta den.</span><span class="sxs-lookup"><span data-stu-id="f30a2-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="f30a2-142">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="f30a2-142">Need help?</span></span> <span data-ttu-id="f30a2-143">Kontakta oss.</span><span class="sxs-lookup"><span data-stu-id="f30a2-143">Contact us.</span></span>

<span data-ttu-id="f30a2-144">Vanliga frågor om självbetjäningsköp finns i [Vanliga frågor om självbetjäningsköp](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="f30a2-144">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="f30a2-145">Om du har frågor eller behöver hjälp med självbetjäningsköp [kontaktar du supporten](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f30a2-145">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
