---
title: Hantera program vara som-as-service-program för din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Lär dig hur du aktiverar och hanterar program från tredje part i administrations centret för Microsoft 365.
ms.openlocfilehash: c1565f0edb2f78302c0186aa3bd89d1ff5a51e5c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638177"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="ac107-103">Hantera program abonnemang från tredje part för din organisation</span><span class="sxs-lookup"><span data-stu-id="ac107-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="ac107-104">Du kan hantera licenser och fakturering för program från tredje part i det nya administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac107-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="ac107-105">Uppdaterade funktioner omfattar förbättrad abonnemangs hantering, förbättrad åtkomst till fakturerings information och förbättrad flexibilitet för att hantera räkningar.</span><span class="sxs-lookup"><span data-stu-id="ac107-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="ac107-106">Abonnemangs hanteringen baseras på Microsofts uppdaterade Commerce-plattform.</span><span class="sxs-lookup"><span data-stu-id="ac107-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="ac107-107">Detta gäller program vara-as-service-program som kunder köper direkt eller från en tredjepartsleverantör.</span><span class="sxs-lookup"><span data-stu-id="ac107-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ac107-108">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="ac107-108">The admin center is changing.</span></span> <span data-ttu-id="ac107-109">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ac107-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ac107-110">Du kan hantera licenser och fakturering för program från tredje part i Microsoft 365 Admin Center med förhands gransknings läge aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ac107-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="ac107-111">Uppdaterade funktioner omfattar förbättrad abonnemangs hantering, förbättrad åtkomst till fakturerings information och förbättrad flexibilitet för att hantera räkningar.</span><span class="sxs-lookup"><span data-stu-id="ac107-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="ac107-112">Abonnemangs hanteringen baseras på Microsofts uppdaterade Commerce-plattform.</span><span class="sxs-lookup"><span data-stu-id="ac107-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="ac107-113">Det här gäller program vara-as-service-program som kunder köper direkt eller från tredje parts leverantör.</span><span class="sxs-lookup"><span data-stu-id="ac107-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="ac107-114">Skaffa program vara-as-service-appar</span><span class="sxs-lookup"><span data-stu-id="ac107-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="ac107-115">Det finns några sätt att köpa tredjepartsprogram.</span><span class="sxs-lookup"><span data-stu-id="ac107-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="ac107-116">**Direkt inköp** – kunderna kan köpa abonnemang direkt från [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)eller [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="ac107-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="ac107-117">**Partner köp** – arbeta med en partner via partner Center för att köpa prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ac107-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="ac107-118">**Microsoft-förslag** – svara på ett förslag från Microsoft Sales som innehåller appar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="ac107-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="ac107-119">När kunderna köper programmen och accepterar Microsofts kund avtal kan de hantera dem i Microsoft 365 Admin Center eller Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="ac107-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="ac107-120">Program leverantörer säljer sina appar antingen till en fast taxa eller genom att köpa licenser för användare.</span><span class="sxs-lookup"><span data-stu-id="ac107-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="ac107-121">**Fast ränta** – kallas även för platskod, och är pris värda med ett månatligt eller årligt pris.</span><span class="sxs-lookup"><span data-stu-id="ac107-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="ac107-122">På sidan app visas antalet licenser till obegränsat.</span><span class="sxs-lookup"><span data-stu-id="ac107-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="ac107-123">**Licenser** – appar är pris per licens.</span><span class="sxs-lookup"><span data-stu-id="ac107-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="ac107-124">Kunder tilldelar alla användare licenser till sina organisationer</span><span class="sxs-lookup"><span data-stu-id="ac107-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="ac107-125">Regioner som stöds</span><span class="sxs-lookup"><span data-stu-id="ac107-125">Supported regions</span></span>

<span data-ttu-id="ac107-126">Stöd för tredjepartsprogram i de här regionerna:</span><span class="sxs-lookup"><span data-stu-id="ac107-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="ac107-127">Argentina</span><span class="sxs-lookup"><span data-stu-id="ac107-127">Argentina</span></span>
- <span data-ttu-id="ac107-128">Australien</span><span class="sxs-lookup"><span data-stu-id="ac107-128">Australia</span></span>
- <span data-ttu-id="ac107-129">Kanada</span><span class="sxs-lookup"><span data-stu-id="ac107-129">Canada</span></span>
- <span data-ttu-id="ac107-130">Chile</span><span class="sxs-lookup"><span data-stu-id="ac107-130">Chile</span></span>
- <span data-ttu-id="ac107-131">Frankrike</span><span class="sxs-lookup"><span data-stu-id="ac107-131">France</span></span>
- <span data-ttu-id="ac107-132">Tyskland</span><span class="sxs-lookup"><span data-stu-id="ac107-132">Germany</span></span>
- <span data-ttu-id="ac107-133">Grekland</span><span class="sxs-lookup"><span data-stu-id="ac107-133">Greece</span></span>
- <span data-ttu-id="ac107-134">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="ac107-134">Puerto Rico</span></span>
- <span data-ttu-id="ac107-135">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="ac107-135">South Africa</span></span>
- <span data-ttu-id="ac107-136">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="ac107-136">United Kingdom</span></span>
- <span data-ttu-id="ac107-137">USA</span><span class="sxs-lookup"><span data-stu-id="ac107-137">United States</span></span>
- <span data-ttu-id="ac107-138">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="ac107-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="ac107-139">Aktivera tredjepartsprogram</span><span class="sxs-lookup"><span data-stu-id="ac107-139">Activate third-party apps</span></span>

<span data-ttu-id="ac107-140">Administratörer måste aktivera tredjepartsprogram innan de tilldelar dem till användarna.</span><span class="sxs-lookup"><span data-stu-id="ac107-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="ac107-141">Dessa appar är aktiverade i den tredje partens Portal.</span><span class="sxs-lookup"><span data-stu-id="ac107-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="ac107-142">Gå till sidan för **fakturering**av  >  **dina produkter**i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="ac107-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="ac107-143">Leta reda på och välj det program du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="ac107-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="ac107-144">Under **inställningar & åtgärder**väljer du **Hantera i Publisher-portalen**.</span><span class="sxs-lookup"><span data-stu-id="ac107-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="ac107-145">Du dirigeras till program utgivarens webbplats där du kan aktivera appen.</span><span class="sxs-lookup"><span data-stu-id="ac107-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="ac107-146">Hantera appar från tredje part</span><span class="sxs-lookup"><span data-stu-id="ac107-146">Manage third-party apps</span></span>

<span data-ttu-id="ac107-147">Administratörer hanterar tredjepartsprogram på två platser: Microsoft 365 Admin Center och tredjepartsprogram från tredje part.</span><span class="sxs-lookup"><span data-stu-id="ac107-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="ac107-148">Det här kan du göra på varje Portal.</span><span class="sxs-lookup"><span data-stu-id="ac107-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="ac107-149">Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac107-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="ac107-150">App Publisher-Portal</span><span class="sxs-lookup"><span data-stu-id="ac107-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="ac107-151">Ändra antal licenser</span><span class="sxs-lookup"><span data-stu-id="ac107-151">Change license quantity</span></span> <br> <span data-ttu-id="ac107-152">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="ac107-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="ac107-153">Hantera hur du betalar din faktura</span><span class="sxs-lookup"><span data-stu-id="ac107-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="ac107-154">Ändra betalnings metod (kredit kort)</span><span class="sxs-lookup"><span data-stu-id="ac107-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="ac107-155">Visa faktura</span><span class="sxs-lookup"><span data-stu-id="ac107-155">View invoice</span></span> <br> <span data-ttu-id="ac107-156">Avbryt program abonnemang</span><span class="sxs-lookup"><span data-stu-id="ac107-156">Cancel app subscription</span></span> | <span data-ttu-id="ac107-157">Konfigurera program (en gång för varje app)</span><span class="sxs-lookup"><span data-stu-id="ac107-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="ac107-158">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="ac107-158">Assign licenses to users</span></span> <br> <span data-ttu-id="ac107-159">Teknisk support</span><span class="sxs-lookup"><span data-stu-id="ac107-159">Technical support</span></span> |

<span data-ttu-id="ac107-160">När appen är aktive rad är den aktiv om den inte har annullerats, går ut eller om betalningen inte hålls aktuell.</span><span class="sxs-lookup"><span data-stu-id="ac107-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="ac107-161">Dessa händelser ändrar appens status till inaktive rad.</span><span class="sxs-lookup"><span data-stu-id="ac107-161">These events change the app status to disabled.</span></span> <span data-ttu-id="ac107-162">När ett program är inaktiverat går det inte att återaktivera det.</span><span class="sxs-lookup"><span data-stu-id="ac107-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="ac107-163">För att fortsätta använda appen kan du köpa en kopia av den.</span><span class="sxs-lookup"><span data-stu-id="ac107-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="ac107-164">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="ac107-164">Assign licenses</span></span>

<span data-ttu-id="ac107-165">Administratörer måste aktivera tredjepartsprogram innan de tilldelar dem till användarna.</span><span class="sxs-lookup"><span data-stu-id="ac107-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="ac107-166">De aktive ras i den tredje partens Portal.</span><span class="sxs-lookup"><span data-stu-id="ac107-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="ac107-167">På sidan app, under **inställningar & åtgärder**, väljer du länken för att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="ac107-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="ac107-168">Gå till sidan för **fakturering**av  >  **dina produkter**i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="ac107-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="ac107-169">Leta reda på och välj det program du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="ac107-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="ac107-170">Under **inställningar & åtgärder**väljer du länken som ska **hanteras i Publisher-portalen**.</span><span class="sxs-lookup"><span data-stu-id="ac107-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="ac107-171">Ändra antal licenser</span><span class="sxs-lookup"><span data-stu-id="ac107-171">Change license quantity</span></span>

<span data-ttu-id="ac107-172">Administratörer kan ändra antalet licenser som ägs av organisationen.</span><span class="sxs-lookup"><span data-stu-id="ac107-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="ac107-173">Detta gäller endast för appar som köpts med webbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="ac107-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="ac107-174">Gå till sidan för **fakturering**av  >  **dina produkter**i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="ac107-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="ac107-175">Leta reda på och välj det program du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="ac107-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="ac107-176">Välj **ändra antal licenser**.</span><span class="sxs-lookup"><span data-stu-id="ac107-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="ac107-177">Hantera betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="ac107-177">Manage payment methods</span></span>

<span data-ttu-id="ac107-178">Program vara-as-service-appar har tilldelats en fakturerings profil.</span><span class="sxs-lookup"><span data-stu-id="ac107-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="ac107-179">Med fakturerings profiler kan du anpassa vilka produkter som ingår i din faktura och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="ac107-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="ac107-180">De inkluderar:</span><span class="sxs-lookup"><span data-stu-id="ac107-180">They include:</span></span>

- <span data-ttu-id="ac107-181">**Betalnings sätt** – kredit kort eller kontroll/överföring</span><span class="sxs-lookup"><span data-stu-id="ac107-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="ac107-182">**Kontakt information** – fakturerings adress och ett kontakt namn</span><span class="sxs-lookup"><span data-stu-id="ac107-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="ac107-183">**Roller** – roller som gör att du kan ändra fakturerings profil, betala räkningar eller använda betalnings metoden i fakturerings profilen för att köpa.</span><span class="sxs-lookup"><span data-stu-id="ac107-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="ac107-184">Mer information om fakturerings profiler finns i [förstå fakturerings profiler](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="ac107-184">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="ac107-185">Ändra fakturerings profil för ett program-as-service-program</span><span class="sxs-lookup"><span data-stu-id="ac107-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="ac107-186">Gå till sidan för **fakturering**av  >  **dina produkter**i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="ac107-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="ac107-187">Leta reda på och välj det program du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="ac107-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="ac107-188">Välj **Redigera**bredvid **fakturerings profil**.</span><span class="sxs-lookup"><span data-stu-id="ac107-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="ac107-189">Mer information om fakturor finns i [förstå din faktura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="ac107-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="ac107-190">Avbryta ett abonnemang på en program-as-service-app</span><span class="sxs-lookup"><span data-stu-id="ac107-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="ac107-191">Du kan avbryta en program-och-service-app från program sidan.</span><span class="sxs-lookup"><span data-stu-id="ac107-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="ac107-192">Gå till sidan för **fakturering**av  >  **dina produkter**i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="ac107-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="ac107-193">Leta reda på och välj det program du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="ac107-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="ac107-194">Under **inställningar & åtgärder**väljer du **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="ac107-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>