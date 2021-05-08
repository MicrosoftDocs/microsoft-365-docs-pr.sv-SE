---
title: Hantera program som en tjänst för din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
search.appverid: MET150
description: Läs om hur du aktiverar och hanterar appar från tredje Microsoft 365 administrationscenter.
ms.date: 04/15/2021
ms.openlocfilehash: eece8154640dcdd55239511ed099abcdca39e807
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280529"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="a80cd-103">Hantera appprenumerationer från tredje part för din organisation</span><span class="sxs-lookup"><span data-stu-id="a80cd-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="a80cd-104">Du kan hantera licenser och fakturering för appar från tredje part i det nya Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a80cd-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="a80cd-105">De uppdaterade funktionerna omfattar förbättrad hantering av prenumerationer, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="a80cd-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="a80cd-106">Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform.</span><span class="sxs-lookup"><span data-stu-id="a80cd-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="a80cd-107">Det här gäller programvaror som en tjänst som kunder köper direkt eller från en tredjepartsleverantör.</span><span class="sxs-lookup"><span data-stu-id="a80cd-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

<span data-ttu-id="a80cd-108">Du kan hantera licenser och fakturering för appar från tredje Microsoft 365 administrationscentret med förhandsgranskningsläget aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a80cd-108">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="a80cd-109">De uppdaterade funktionerna omfattar förbättrad hantering av prenumerationer, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="a80cd-109">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="a80cd-110">Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform.</span><span class="sxs-lookup"><span data-stu-id="a80cd-110">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="a80cd-111">Det här gäller programvaror som en tjänst som kunder köper direkt eller från tredje part.</span><span class="sxs-lookup"><span data-stu-id="a80cd-111">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="a80cd-112">Så här hämtar du program för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="a80cd-112">How to get software-as-a-service apps</span></span>

<span data-ttu-id="a80cd-113">Det finns några olika sätt att köpa appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="a80cd-113">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="a80cd-114">**Direktköp** – kunder kan köpa prenumerationer direkt från [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)eller [AppSource.](https://appsource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a80cd-114">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://appsource.microsoft.com/).</span></span>
- <span data-ttu-id="a80cd-115">**Partnerköp** – arbeta med en partner via Partner Center för att köpa prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="a80cd-115">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="a80cd-116">**Microsoft-förslag** – svara på ett förslag från Microsoft Sales som innehåller appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="a80cd-116">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="a80cd-117">När kunder köper apparna och godkänner Microsofts kundavtal kan de hantera dem Microsoft 365 administrationscenter eller Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="a80cd-117">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="a80cd-118">Appleverantörer säljer sina appar antingen till ett fast pris eller genom att köpa licenser till användare.</span><span class="sxs-lookup"><span data-stu-id="a80cd-118">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="a80cd-119">**Fast kostnad** – även kallat webbplatsbaserat pris, appar kostar pris med ett pris per månad eller år.</span><span class="sxs-lookup"><span data-stu-id="a80cd-119">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="a80cd-120">På programsidan visas antal licenser under Obegränsat.</span><span class="sxs-lookup"><span data-stu-id="a80cd-120">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="a80cd-121">**Licenser** – appar kostar per licens.</span><span class="sxs-lookup"><span data-stu-id="a80cd-121">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="a80cd-122">Kunder tilldelar licenser till varje användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="a80cd-122">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="a80cd-123">Regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="a80cd-123">Supported regions</span></span>

<span data-ttu-id="a80cd-124">Stöd för appar från tredje part finns i följande regioner:</span><span class="sxs-lookup"><span data-stu-id="a80cd-124">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="a80cd-125">Argentina</span><span class="sxs-lookup"><span data-stu-id="a80cd-125">Argentina</span></span>
- <span data-ttu-id="a80cd-126">Australien</span><span class="sxs-lookup"><span data-stu-id="a80cd-126">Australia</span></span>
- <span data-ttu-id="a80cd-127">Kanada</span><span class="sxs-lookup"><span data-stu-id="a80cd-127">Canada</span></span>
- <span data-ttu-id="a80cd-128">Chile</span><span class="sxs-lookup"><span data-stu-id="a80cd-128">Chile</span></span>
- <span data-ttu-id="a80cd-129">Frankrike</span><span class="sxs-lookup"><span data-stu-id="a80cd-129">France</span></span>
- <span data-ttu-id="a80cd-130">Tyskland</span><span class="sxs-lookup"><span data-stu-id="a80cd-130">Germany</span></span>
- <span data-ttu-id="a80cd-131">Grekland</span><span class="sxs-lookup"><span data-stu-id="a80cd-131">Greece</span></span>
- <span data-ttu-id="a80cd-132">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="a80cd-132">Puerto Rico</span></span>
- <span data-ttu-id="a80cd-133">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="a80cd-133">South Africa</span></span>
- <span data-ttu-id="a80cd-134">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="a80cd-134">United Kingdom</span></span>
- <span data-ttu-id="a80cd-135">USA</span><span class="sxs-lookup"><span data-stu-id="a80cd-135">United States</span></span>
- <span data-ttu-id="a80cd-136">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="a80cd-136">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="a80cd-137">Aktivera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="a80cd-137">Activate third-party apps</span></span>

<span data-ttu-id="a80cd-138">Administratörer måste aktivera appar från tredje part innan de tilldelas till användare.</span><span class="sxs-lookup"><span data-stu-id="a80cd-138">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="a80cd-139">De här apparna aktiveras i tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="a80cd-139">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="a80cd-140">I administrationscentret går du till sidan  >  **Fakturering dina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">produktappar.</a></span><span class="sxs-lookup"><span data-stu-id="a80cd-140">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a80cd-141">Leta upp och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="a80cd-141">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a80cd-142">Under **Inställningar & åtgärder** väljer **du Hantera i Publishers portal**.</span><span class="sxs-lookup"><span data-stu-id="a80cd-142">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="a80cd-143">Du dirigeras till apputgivarens webbplats där du kan aktivera appen.</span><span class="sxs-lookup"><span data-stu-id="a80cd-143">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="a80cd-144">Hantera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="a80cd-144">Manage third-party apps</span></span>

<span data-ttu-id="a80cd-145">Administratörer hanterar appar från tredje part på två platser: Microsoft 365 administrationscenter och den tredje leverantörens appleverantörs portal.</span><span class="sxs-lookup"><span data-stu-id="a80cd-145">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="a80cd-146">Det här kan du göra i varje portal.</span><span class="sxs-lookup"><span data-stu-id="a80cd-146">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="a80cd-147">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a80cd-147">Microsoft 365 admin center</span></span> | <span data-ttu-id="a80cd-148">Apputgivarportalen</span><span class="sxs-lookup"><span data-stu-id="a80cd-148">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="a80cd-149">Ändra antal licenser</span><span class="sxs-lookup"><span data-stu-id="a80cd-149">Change license quantity</span></span> <br> <span data-ttu-id="a80cd-150">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="a80cd-150">Manage how you pay your bill</span></span> <br> <span data-ttu-id="a80cd-151">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="a80cd-151">Manage how you pay your bill</span></span> <br> <span data-ttu-id="a80cd-152">Ändra betalningsmetod (kreditkort)</span><span class="sxs-lookup"><span data-stu-id="a80cd-152">Change payment method (credit card)</span></span> <br> <span data-ttu-id="a80cd-153">Visa faktura</span><span class="sxs-lookup"><span data-stu-id="a80cd-153">View invoice</span></span> <br> <span data-ttu-id="a80cd-154">Avbryt appprenumeration</span><span class="sxs-lookup"><span data-stu-id="a80cd-154">Cancel app subscription</span></span> | <span data-ttu-id="a80cd-155">Konfigurera appen (en gång för varje app)</span><span class="sxs-lookup"><span data-stu-id="a80cd-155">Set up app (once for each app)</span></span> <br> <span data-ttu-id="a80cd-156">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="a80cd-156">Assign licenses to users</span></span> <br> <span data-ttu-id="a80cd-157">Teknisk support</span><span class="sxs-lookup"><span data-stu-id="a80cd-157">Technical support</span></span> |

<span data-ttu-id="a80cd-158">När appen har aktiverats förblir den aktiv om den inte har avbrutits, upphört att gälla eller om betalningen inte hålls aktuell.</span><span class="sxs-lookup"><span data-stu-id="a80cd-158">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="a80cd-159">Dessa händelser ändrar appens status till inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="a80cd-159">These events change the app status to disabled.</span></span> <span data-ttu-id="a80cd-160">När en app är inaktiverad kan den inte återaktiveras.</span><span class="sxs-lookup"><span data-stu-id="a80cd-160">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="a80cd-161">Om du vill fortsätta använda appen köper du en ny kopia av den.</span><span class="sxs-lookup"><span data-stu-id="a80cd-161">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="a80cd-162">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="a80cd-162">Assign licenses</span></span>

<span data-ttu-id="a80cd-163">Administratörer måste aktivera appar från tredje part innan de tilldelas till användare.</span><span class="sxs-lookup"><span data-stu-id="a80cd-163">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="a80cd-164">De aktiveras på tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="a80cd-164">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="a80cd-165">Välj länken för att **tilldela Inställningar & åtgärder** på appsidan.</span><span class="sxs-lookup"><span data-stu-id="a80cd-165">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="a80cd-166">I administrationscentret går du till sidan  >  **Fakturering dina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">produktappar.</a></span><span class="sxs-lookup"><span data-stu-id="a80cd-166">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a80cd-167">Leta upp och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="a80cd-167">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a80cd-168">Under **Inställningar & åtgärder** väljer du länken Hantera i **Publisher-portalen**.</span><span class="sxs-lookup"><span data-stu-id="a80cd-168">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="a80cd-169">Ändra antal licenser</span><span class="sxs-lookup"><span data-stu-id="a80cd-169">Change license quantity</span></span>

<span data-ttu-id="a80cd-170">Administratörer kan ändra antalet licenser som ägs av organisationen.</span><span class="sxs-lookup"><span data-stu-id="a80cd-170">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="a80cd-171">Det här gäller endast för appar som köpts med platsbaserat pris.</span><span class="sxs-lookup"><span data-stu-id="a80cd-171">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="a80cd-172">I administrationscentret går du till sidan  >  **Fakturering dina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">produktappar.</a></span><span class="sxs-lookup"><span data-stu-id="a80cd-172">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a80cd-173">Leta upp och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="a80cd-173">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a80cd-174">Välj **Ändra antal licenser.**</span><span class="sxs-lookup"><span data-stu-id="a80cd-174">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="a80cd-175">Hantera betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="a80cd-175">Manage payment methods</span></span>

<span data-ttu-id="a80cd-176">Programvaror som en tjänst har var och en tilldelad faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="a80cd-176">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="a80cd-177">Med faktureringsprofiler kan du anpassa vilka produkter som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="a80cd-177">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="a80cd-178">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="a80cd-178">They include:</span></span>

- <span data-ttu-id="a80cd-179">**Betalningsmetoder** – kreditkort eller check-/banköverföring</span><span class="sxs-lookup"><span data-stu-id="a80cd-179">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="a80cd-180">**Kontaktinformation** – faktureringsadress och kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="a80cd-180">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="a80cd-181">**Roller** – Roller där du kan ändra faktureringsprofil, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp.</span><span class="sxs-lookup"><span data-stu-id="a80cd-181">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="a80cd-182">Mer information om faktureringsprofiler finns i [Förstå faktureringsprofiler](/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="a80cd-182">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="a80cd-183">Ändra faktureringsprofilen för en programprenumeration av en programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="a80cd-183">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="a80cd-184">I administrationscentret går du till sidan  >  **Fakturering dina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">produktappar.</a></span><span class="sxs-lookup"><span data-stu-id="a80cd-184">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a80cd-185">Leta upp och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="a80cd-185">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a80cd-186">Bredvid **Faktureringsprofil väljer** du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="a80cd-186">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="a80cd-187">Mer information om fakturor finns i [Förstå din faktura.](billing-and-payments/understand-your-invoice.md)</span><span class="sxs-lookup"><span data-stu-id="a80cd-187">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="a80cd-188">Avbryta en prenumeration på en programvara som en tjänst-app</span><span class="sxs-lookup"><span data-stu-id="a80cd-188">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="a80cd-189">Du kan avbryta en programapp som en tjänst från appsidan.</span><span class="sxs-lookup"><span data-stu-id="a80cd-189">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="a80cd-190">I administrationscentret går du till sidan  >  **Fakturering dina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">produktappar.</a></span><span class="sxs-lookup"><span data-stu-id="a80cd-190">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a80cd-191">Leta upp och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="a80cd-191">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a80cd-192">Under **Inställningar & väljer** du **Avbryt prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="a80cd-192">Under **Settings & actions**, select **Cancel subscription**.</span></span>
