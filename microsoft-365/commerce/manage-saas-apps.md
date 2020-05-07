---
title: Hantera appar för programvara som en tjänst för din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Lär dig hur du aktiverar och hanterar appar från tredje part i Microsoft 365 administrationscenter.
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141194"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="58d76-103">Hantera appprenumerationer från tredje part för din organisation</span><span class="sxs-lookup"><span data-stu-id="58d76-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="58d76-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="58d76-104">The admin center is changing.</span></span> <span data-ttu-id="58d76-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="58d76-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="58d76-106">Du kan hantera licenser och fakturering för appar från tredje part i Microsoft 365-administrationscentret med förhandsgranskningsläge aktiverat.</span><span class="sxs-lookup"><span data-stu-id="58d76-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="58d76-107">Uppdaterade funktioner inkluderar förbättrad prenumerationshantering, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera räkningar.</span><span class="sxs-lookup"><span data-stu-id="58d76-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="58d76-108">Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform.</span><span class="sxs-lookup"><span data-stu-id="58d76-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="58d76-109">Detta gäller appar som kunder köper direkt eller från tredjepartsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="58d76-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="58d76-110">Så här skaffar du appar för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="58d76-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="58d76-111">Det finns några sätt att köpa appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="58d76-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="58d76-112">**Direktköp** – Kunder kan direkt köpa prenumerationer från [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)eller [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="58d76-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="58d76-113">**Partnerköp** – Arbeta med en partner via Partner Center för att köpa prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="58d76-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="58d76-114">**Microsoft-förslag** – Svara på ett förslag från Microsoft Sales som innehåller appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="58d76-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="58d76-115">När kunderna har köpt apparna och accepterat Microsofts kundavtal kan de hantera dem i Microsoft 365-administrationscentret eller Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="58d76-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="58d76-116">Appleverantörer säljer sina appar antingen till ett schablonbelopp eller genom att köpa licenser för användare.</span><span class="sxs-lookup"><span data-stu-id="58d76-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="58d76-117">**Schablonbelopp** – Även kallad platsbaserad prissättning, appar är prissatta med ett månads- eller årspris.</span><span class="sxs-lookup"><span data-stu-id="58d76-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="58d76-118">På appsidan visas licenskvantitet på Unlimited.</span><span class="sxs-lookup"><span data-stu-id="58d76-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="58d76-119">**Licenser** – Appar prissätts efter licens.</span><span class="sxs-lookup"><span data-stu-id="58d76-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="58d76-120">Kunder tilldelar licenser till varje användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="58d76-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="58d76-121">Regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="58d76-121">Supported regions</span></span>

<span data-ttu-id="58d76-122">Stöd för appar från tredje part är tillgängligt i följande regioner:</span><span class="sxs-lookup"><span data-stu-id="58d76-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="58d76-123">Argentina</span><span class="sxs-lookup"><span data-stu-id="58d76-123">Argentina</span></span>
- <span data-ttu-id="58d76-124">Australien</span><span class="sxs-lookup"><span data-stu-id="58d76-124">Australia</span></span>
- <span data-ttu-id="58d76-125">Kanada</span><span class="sxs-lookup"><span data-stu-id="58d76-125">Canada</span></span>
- <span data-ttu-id="58d76-126">Chile</span><span class="sxs-lookup"><span data-stu-id="58d76-126">Chile</span></span>
- <span data-ttu-id="58d76-127">Frankrike</span><span class="sxs-lookup"><span data-stu-id="58d76-127">France</span></span>
- <span data-ttu-id="58d76-128">Tyskland</span><span class="sxs-lookup"><span data-stu-id="58d76-128">Germany</span></span>
- <span data-ttu-id="58d76-129">Grekland</span><span class="sxs-lookup"><span data-stu-id="58d76-129">Greece</span></span>
- <span data-ttu-id="58d76-130">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="58d76-130">Puerto Rico</span></span>
- <span data-ttu-id="58d76-131">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="58d76-131">South Africa</span></span>
- <span data-ttu-id="58d76-132">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="58d76-132">United Kingdom</span></span>
- <span data-ttu-id="58d76-133">USA</span><span class="sxs-lookup"><span data-stu-id="58d76-133">United States</span></span>
- <span data-ttu-id="58d76-134">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="58d76-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="58d76-135">Aktivera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="58d76-135">Activate third-party apps</span></span>

<span data-ttu-id="58d76-136">Administratörer måste aktivera appar från tredje part innan de tilldelas användare.</span><span class="sxs-lookup"><span data-stu-id="58d76-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="58d76-137">Dessa appar aktiveras i tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="58d76-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="58d76-138">Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="58d76-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="58d76-139">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="58d76-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="58d76-140">Under **Inställningar & åtgärder**väljer du Hantera i **utgivarens portal**.</span><span class="sxs-lookup"><span data-stu-id="58d76-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="58d76-141">Du dirigeras till apputgivarens webbplats där du kan aktivera appen.</span><span class="sxs-lookup"><span data-stu-id="58d76-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="58d76-142">Hantera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="58d76-142">Manage third-party apps</span></span>

<span data-ttu-id="58d76-143">Administratörer hanterar appar från tredje part på två platser: Microsoft 365 admincenter och tredjepartsappleverantörens portal.</span><span class="sxs-lookup"><span data-stu-id="58d76-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="58d76-144">Det här kan du göra i varje portal.</span><span class="sxs-lookup"><span data-stu-id="58d76-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="58d76-145">Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58d76-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="58d76-146">Portal för apputgivare</span><span class="sxs-lookup"><span data-stu-id="58d76-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="58d76-147">Ändra licenskvantitet</span><span class="sxs-lookup"><span data-stu-id="58d76-147">Change license quantity</span></span> <br> <span data-ttu-id="58d76-148">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="58d76-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="58d76-149">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="58d76-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="58d76-150">Ändra betalningsmetod (kreditkort)</span><span class="sxs-lookup"><span data-stu-id="58d76-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="58d76-151">Visa faktura</span><span class="sxs-lookup"><span data-stu-id="58d76-151">View invoice</span></span> <br> <span data-ttu-id="58d76-152">Avbryt appprenumeration</span><span class="sxs-lookup"><span data-stu-id="58d76-152">Cancel app subscription</span></span> | <span data-ttu-id="58d76-153">Konfigurera app (en gång för varje app)</span><span class="sxs-lookup"><span data-stu-id="58d76-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="58d76-154">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="58d76-154">Assign licenses to users</span></span> <br> <span data-ttu-id="58d76-155">Teknisk support</span><span class="sxs-lookup"><span data-stu-id="58d76-155">Technical support</span></span> |

<span data-ttu-id="58d76-156">När appen har aktiverats förblir den aktiv om den inte avbryts, upphör att gälla eller om betalningen inte hålls aktuell.</span><span class="sxs-lookup"><span data-stu-id="58d76-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="58d76-157">Dessa händelser ändrar appstatusen till inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="58d76-157">These events change the app status to disabled.</span></span> <span data-ttu-id="58d76-158">När en app har inaktiverats kan den inte återaktiveras.</span><span class="sxs-lookup"><span data-stu-id="58d76-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="58d76-159">Om du vill fortsätta använda appen köper du en annan kopia av den.</span><span class="sxs-lookup"><span data-stu-id="58d76-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="58d76-160">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="58d76-160">Assign licenses</span></span>

<span data-ttu-id="58d76-161">Administratörer måste aktivera appar från tredje part innan de tilldelas användarna.</span><span class="sxs-lookup"><span data-stu-id="58d76-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="58d76-162">De aktiveras i tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="58d76-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="58d76-163">Välj länken för att tilldela licenser under **Inställningar & åtgärder**på appsidan.</span><span class="sxs-lookup"><span data-stu-id="58d76-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="58d76-164">Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="58d76-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="58d76-165">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="58d76-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="58d76-166">Under **Inställningar & åtgärder**väljer du länken till Hantera i **utgivarens portal**.</span><span class="sxs-lookup"><span data-stu-id="58d76-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="58d76-167">Ändra licenskvantitet</span><span class="sxs-lookup"><span data-stu-id="58d76-167">Change license quantity</span></span>

<span data-ttu-id="58d76-168">Administratörer kan ändra antalet licenser som ägs av organisationen.</span><span class="sxs-lookup"><span data-stu-id="58d76-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="58d76-169">Detta gäller endast appar som köpts med platsbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="58d76-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="58d76-170">Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="58d76-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="58d76-171">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="58d76-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="58d76-172">Välj **Ändra licenskvantitet**.</span><span class="sxs-lookup"><span data-stu-id="58d76-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="58d76-173">Hantera betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="58d76-173">Manage payment methods</span></span>

<span data-ttu-id="58d76-174">Appar för programvara som en tjänst har var sin faktureringsprofil tilldelad.</span><span class="sxs-lookup"><span data-stu-id="58d76-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="58d76-175">Med faktureringsprofiler kan du anpassa vilka produkter som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="58d76-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="58d76-176">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="58d76-176">They include:</span></span>

- <span data-ttu-id="58d76-177">**Betalningsmetoder** – Kreditkort eller check/banköverföring</span><span class="sxs-lookup"><span data-stu-id="58d76-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="58d76-178">**Kontaktuppgifter** – Faktureringsadress och kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="58d76-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="58d76-179">**Roller** – Roller som gör att du kan ändra faktureringsprofilen, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp.</span><span class="sxs-lookup"><span data-stu-id="58d76-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="58d76-180">Mer information om faktureringsprofiler finns i [Förstå faktureringsprofiler](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="58d76-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="58d76-181">Ändra faktureringsprofilen för en prenumeration på app för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="58d76-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="58d76-182">Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="58d76-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="58d76-183">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="58d76-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="58d76-184">Välj Redigera **bredvid faktureringsprofil** **.**</span><span class="sxs-lookup"><span data-stu-id="58d76-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="58d76-185">Mer information om fakturor finns i [Förstå fakturan](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="58d76-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="58d76-186">Avbryta en prenumeration på app för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="58d76-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="58d76-187">Du kan avbryta en app som en tjänst från appsidan.</span><span class="sxs-lookup"><span data-stu-id="58d76-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="58d76-188">Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="58d76-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="58d76-189">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="58d76-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="58d76-190">Under **Inställningar & åtgärder**väljer du Avbryt **prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="58d76-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
