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
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Lär dig hur du aktiverar och hanterar appar från tredje part i Microsoft 365 administrationscenter.
ms.openlocfilehash: c8d2764dfa7795707712cbd9ce212f78c4d43d45
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429996"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="34af2-103">Hantera appprenumerationer från tredje part för din organisation</span><span class="sxs-lookup"><span data-stu-id="34af2-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="34af2-104">Du kan hantera licenser och fakturering för appar från tredje part i det nya administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34af2-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="34af2-105">Uppdaterade funktioner inkluderar förbättrad prenumerationshantering, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera räkningar.</span><span class="sxs-lookup"><span data-stu-id="34af2-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="34af2-106">Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform.</span><span class="sxs-lookup"><span data-stu-id="34af2-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="34af2-107">Detta gäller appar som kunder köper direkt eller från en tredjepartsleverantör.</span><span class="sxs-lookup"><span data-stu-id="34af2-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="34af2-108">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="34af2-108">The admin center is changing.</span></span> <span data-ttu-id="34af2-109">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="34af2-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="34af2-110">Du kan hantera licenser och fakturering för appar från tredje part i Microsoft 365-administrationscentret med förhandsgranskningsläge aktiverat.</span><span class="sxs-lookup"><span data-stu-id="34af2-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="34af2-111">Uppdaterade funktioner inkluderar förbättrad prenumerationshantering, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera räkningar.</span><span class="sxs-lookup"><span data-stu-id="34af2-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="34af2-112">Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform.</span><span class="sxs-lookup"><span data-stu-id="34af2-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="34af2-113">Detta gäller för appar som en tjänst som kunder köper direkt eller från tredjepartsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="34af2-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="34af2-114">Så här skaffar du appar för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="34af2-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="34af2-115">Det finns några sätt att köpa appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="34af2-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="34af2-116">**Direktköp** – Kunder kan direkt köpa prenumerationer från [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)eller [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="34af2-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="34af2-117">**Partnerköp** – Arbeta med en partner via Partner Center för att köpa prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="34af2-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="34af2-118">**Microsoft-förslag** – Svara på ett förslag från Microsoft Sales som innehåller appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="34af2-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="34af2-119">När kunderna har köpt apparna och accepterat Microsofts kundavtal kan de hantera dem i Microsoft 365-administrationscentret eller Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="34af2-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="34af2-120">Appleverantörer säljer sina appar antingen till ett schablonbelopp eller genom att köpa licenser för användare.</span><span class="sxs-lookup"><span data-stu-id="34af2-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="34af2-121">**Schablonbelopp** – Även kallad webbplatsbaserad prissättning, appar är prissatta med ett månads- eller årspris.</span><span class="sxs-lookup"><span data-stu-id="34af2-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="34af2-122">På appsidan visas licenskvantitet på Unlimited.</span><span class="sxs-lookup"><span data-stu-id="34af2-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="34af2-123">**Licenser** – Appar prissätts efter licens.</span><span class="sxs-lookup"><span data-stu-id="34af2-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="34af2-124">Kunder tilldelar licenser till varje användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="34af2-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="34af2-125">Regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="34af2-125">Supported regions</span></span>

<span data-ttu-id="34af2-126">Stöd för appar från tredje part är tillgängligt i följande regioner:</span><span class="sxs-lookup"><span data-stu-id="34af2-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="34af2-127">Argentina</span><span class="sxs-lookup"><span data-stu-id="34af2-127">Argentina</span></span>
- <span data-ttu-id="34af2-128">Australien</span><span class="sxs-lookup"><span data-stu-id="34af2-128">Australia</span></span>
- <span data-ttu-id="34af2-129">Kanada</span><span class="sxs-lookup"><span data-stu-id="34af2-129">Canada</span></span>
- <span data-ttu-id="34af2-130">Chile</span><span class="sxs-lookup"><span data-stu-id="34af2-130">Chile</span></span>
- <span data-ttu-id="34af2-131">Frankrike</span><span class="sxs-lookup"><span data-stu-id="34af2-131">France</span></span>
- <span data-ttu-id="34af2-132">Tyskland</span><span class="sxs-lookup"><span data-stu-id="34af2-132">Germany</span></span>
- <span data-ttu-id="34af2-133">Grekland</span><span class="sxs-lookup"><span data-stu-id="34af2-133">Greece</span></span>
- <span data-ttu-id="34af2-134">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="34af2-134">Puerto Rico</span></span>
- <span data-ttu-id="34af2-135">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="34af2-135">South Africa</span></span>
- <span data-ttu-id="34af2-136">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="34af2-136">United Kingdom</span></span>
- <span data-ttu-id="34af2-137">USA</span><span class="sxs-lookup"><span data-stu-id="34af2-137">United States</span></span>
- <span data-ttu-id="34af2-138">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="34af2-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="34af2-139">Aktivera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="34af2-139">Activate third-party apps</span></span>

<span data-ttu-id="34af2-140">Administratörer måste aktivera appar från tredje part innan de tilldelas användare.</span><span class="sxs-lookup"><span data-stu-id="34af2-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="34af2-141">Dessa appar aktiveras i tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="34af2-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="34af2-142">Gå till sidan **Billing**  >  **Faktureringsappar**i administrationscentret.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a></span><span class="sxs-lookup"><span data-stu-id="34af2-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="34af2-143">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="34af2-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="34af2-144">Under **Inställningar & åtgärder**väljer du Hantera i **utgivarens portal**.</span><span class="sxs-lookup"><span data-stu-id="34af2-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="34af2-145">Du dirigeras till apputgivarens webbplats där du kan aktivera appen.</span><span class="sxs-lookup"><span data-stu-id="34af2-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="34af2-146">Hantera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="34af2-146">Manage third-party apps</span></span>

<span data-ttu-id="34af2-147">Administratörer hanterar appar från tredje part på två platser: Microsoft 365 admincenter och tredjepartsappleverantörens portal.</span><span class="sxs-lookup"><span data-stu-id="34af2-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="34af2-148">Det här kan du göra i varje portal.</span><span class="sxs-lookup"><span data-stu-id="34af2-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="34af2-149">Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34af2-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="34af2-150">Portal för apputgivare</span><span class="sxs-lookup"><span data-stu-id="34af2-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="34af2-151">Ändra licenskvantitet</span><span class="sxs-lookup"><span data-stu-id="34af2-151">Change license quantity</span></span> <br> <span data-ttu-id="34af2-152">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="34af2-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="34af2-153">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="34af2-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="34af2-154">Ändra betalningsmetod (kreditkort)</span><span class="sxs-lookup"><span data-stu-id="34af2-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="34af2-155">Visa faktura</span><span class="sxs-lookup"><span data-stu-id="34af2-155">View invoice</span></span> <br> <span data-ttu-id="34af2-156">Avbryt appprenumeration</span><span class="sxs-lookup"><span data-stu-id="34af2-156">Cancel app subscription</span></span> | <span data-ttu-id="34af2-157">Konfigurera app (en gång för varje app)</span><span class="sxs-lookup"><span data-stu-id="34af2-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="34af2-158">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="34af2-158">Assign licenses to users</span></span> <br> <span data-ttu-id="34af2-159">Teknisk support</span><span class="sxs-lookup"><span data-stu-id="34af2-159">Technical support</span></span> |

<span data-ttu-id="34af2-160">När appen har aktiverats förblir den aktiv om den inte har avbrutits, upphör att gälla eller om betalningen inte hålls aktuell.</span><span class="sxs-lookup"><span data-stu-id="34af2-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="34af2-161">Dessa händelser ändrar appstatusen till inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="34af2-161">These events change the app status to disabled.</span></span> <span data-ttu-id="34af2-162">När en app har inaktiverats kan den inte återaktiveras.</span><span class="sxs-lookup"><span data-stu-id="34af2-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="34af2-163">Om du vill fortsätta använda appen köper du en annan kopia av den.</span><span class="sxs-lookup"><span data-stu-id="34af2-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="34af2-164">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="34af2-164">Assign licenses</span></span>

<span data-ttu-id="34af2-165">Administratörer måste aktivera appar från tredje part innan de tilldelas användarna.</span><span class="sxs-lookup"><span data-stu-id="34af2-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="34af2-166">De aktiveras i tredjepartsutgivarens portal.</span><span class="sxs-lookup"><span data-stu-id="34af2-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="34af2-167">Välj länken för att tilldela licenser under **Inställningar & åtgärder**på appsidan.</span><span class="sxs-lookup"><span data-stu-id="34af2-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="34af2-168">Gå till sidan **Billing**  >  **Faktureringsappar**i administrationscentret.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a></span><span class="sxs-lookup"><span data-stu-id="34af2-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="34af2-169">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="34af2-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="34af2-170">Under **Inställningar & åtgärder**väljer du länken till Hantera i **utgivarens portal**.</span><span class="sxs-lookup"><span data-stu-id="34af2-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="34af2-171">Ändra licenskvantitet</span><span class="sxs-lookup"><span data-stu-id="34af2-171">Change license quantity</span></span>

<span data-ttu-id="34af2-172">Administratörer kan ändra antalet licenser som ägs av organisationen.</span><span class="sxs-lookup"><span data-stu-id="34af2-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="34af2-173">Detta gäller endast appar som köpts med platsbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="34af2-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="34af2-174">Gå till sidan **Billing**  >  **Faktureringsappar**i administrationscentret.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a></span><span class="sxs-lookup"><span data-stu-id="34af2-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="34af2-175">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="34af2-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="34af2-176">Välj **Ändra licenskvantitet**.</span><span class="sxs-lookup"><span data-stu-id="34af2-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="34af2-177">Hantera betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="34af2-177">Manage payment methods</span></span>

<span data-ttu-id="34af2-178">Appar för programvara som en tjänst har var sin faktureringsprofil tilldelad.</span><span class="sxs-lookup"><span data-stu-id="34af2-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="34af2-179">Med faktureringsprofiler kan du anpassa vilka produkter som ingår i fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="34af2-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="34af2-180">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="34af2-180">They include:</span></span>

- <span data-ttu-id="34af2-181">**Betalningsmetoder** – Kreditkort eller check/banköverföring</span><span class="sxs-lookup"><span data-stu-id="34af2-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="34af2-182">**Kontaktuppgifter** – Faktureringsadress och kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="34af2-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="34af2-183">**Roller** – Roller som gör att du kan ändra faktureringsprofilen, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp.</span><span class="sxs-lookup"><span data-stu-id="34af2-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="34af2-184">Mer information om faktureringsprofiler finns i [Förstå faktureringsprofiler](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="34af2-184">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="34af2-185">Ändra faktureringsprofilen för en appprenumeration för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="34af2-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="34af2-186">Gå till sidan **Billing**  >  **Faktureringsappar**i administrationscentret.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a></span><span class="sxs-lookup"><span data-stu-id="34af2-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="34af2-187">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="34af2-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="34af2-188">Välj Redigera **bredvid faktureringsprofil** **.**</span><span class="sxs-lookup"><span data-stu-id="34af2-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="34af2-189">Mer information om fakturor finns i [Förstå din faktura eller faktura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="34af2-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="34af2-190">Avbryta en prenumeration på app för programvara som en tjänst</span><span class="sxs-lookup"><span data-stu-id="34af2-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="34af2-191">Du kan avbryta en app som en tjänst från appsidan.</span><span class="sxs-lookup"><span data-stu-id="34af2-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="34af2-192">Gå till sidan **Billing**  >  **Faktureringsappar**i administrationscentret.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a></span><span class="sxs-lookup"><span data-stu-id="34af2-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="34af2-193">Hitta och välj den app du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="34af2-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="34af2-194">Under **Inställningar & åtgärder**väljer du Avbryt **prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="34af2-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>