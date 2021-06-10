---
title: Förstå faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Läs om hur faktureringsprofiler har stöd för fakturor.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537337"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="ad7c1-103">Förstå faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="ad7c1-103">Understand billing profiles</span></span>

<span data-ttu-id="ad7c1-104">En faktureringsprofil innehåller ett betalningssätt, faktureringsinformation och andra fakturainställningar, till exempel inköpsordernummer och fakturainställning via e-post.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="ad7c1-105">Du använder en faktureringsprofil för att betala för de produkter som du köper från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="ad7c1-106">En faktureringsprofil skapas automatiskt när en användare gör ett självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="ad7c1-107">Varje faktureringsprofil faktureras separat.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ad7c1-108">Faktureringsprofiler är inte tillgängliga för kunder som köper produkter  och tjänster från Microsoft.com eller på sidan Köptjänster Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="ad7c1-109">Vad är faktureringsprofilroller?</span><span class="sxs-lookup"><span data-stu-id="ad7c1-109">What are billing profile roles?</span></span>

<span data-ttu-id="ad7c1-110">Roller i faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="ad7c1-111">Tilldela de här rollerna till användare som spårar, organiserar och betalar fakturor.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="ad7c1-112">Till exempel medlemmar i organisationens inköpsteam.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="ad7c1-113">Roll</span><span class="sxs-lookup"><span data-stu-id="ad7c1-113">Role</span></span>                         | <span data-ttu-id="ad7c1-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad7c1-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="ad7c1-115">Faktureringsprofilägare</span><span class="sxs-lookup"><span data-stu-id="ad7c1-115">Billing profile owner</span></span>        | <span data-ttu-id="ad7c1-116">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="ad7c1-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="ad7c1-117">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="ad7c1-117">Billing profile contributor</span></span>  | <span data-ttu-id="ad7c1-118">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="ad7c1-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="ad7c1-119">Faktureringsprofilläsare</span><span class="sxs-lookup"><span data-stu-id="ad7c1-119">Billing profile reader</span></span>       | <span data-ttu-id="ad7c1-120">Skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="ad7c1-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="ad7c1-121">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="ad7c1-121">Invoice manager</span></span>              | <span data-ttu-id="ad7c1-122">Visa och betala räkningar och har en skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="ad7c1-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="ad7c1-123">Visa mina faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="ad7c1-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="ad7c1-124">Om du följer de här stegen och listan med faktureringsprofiler är tom innebär det att du inte har en faktureringsprofil och kan inte använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="ad7c1-125">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="ad7c1-126">Välj fliken **Faktureringsprofil** och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="ad7c1-127">Varje faktureringsprofil innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="ad7c1-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="ad7c1-128">**Namn och status för faktureringsprofilen** &ndash; Det unika namnet på faktureringsprofilen och om faktureringsprofilen är aktiv eller inaktiverad för köp.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="ad7c1-129">**Fakturainställningar** &ndash; Valuta baserat på landet för faktureringskontot, information om fakturafrekvens och datum, alternativet att ta emot fakturor som e-postbilagor och valfritt fält för inköpsordernummer</span><span class="sxs-lookup"><span data-stu-id="ad7c1-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="ad7c1-130">**Betalningsmetoder** &ndash; Visar den primära betalningsmetoden och den eventuella betalningsmetoden för profilen</span><span class="sxs-lookup"><span data-stu-id="ad7c1-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="ad7c1-131">**Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="ad7c1-132">Mer information om faktureringskonton finns i [Förstå faktureringskonton.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ad7c1-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="ad7c1-133">**Kontaktinformation** &ndash; Faktureringsadress och kontaktnamn och e-postadress</span><span class="sxs-lookup"><span data-stu-id="ad7c1-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="ad7c1-134">**Faktureringsprofilroller** &ndash; En lista över personer som har tilldelats en av faktureringsprofilrollerna för att göra saker för den profilen.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="ad7c1-135">Du kan till exempel betala fakturor, lägga till ett inköpsordernummer eller ersätta den betalningsmetod som används för att göra inköp.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ad7c1-136">Du kan bara tilldela faktureringsprofilroller till användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad7c1-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="ad7c1-137">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="ad7c1-137">Need help?</span></span> <span data-ttu-id="ad7c1-138">Kontakta support</span><span class="sxs-lookup"><span data-stu-id="ad7c1-138">Contact support</span></span>

<span data-ttu-id="ad7c1-139">Om du har frågor eller behöver hjälp med dina Azure-avgifter kan <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">du skapa en supportbegäran med Azure-supporten.</a></span><span class="sxs-lookup"><span data-stu-id="ad7c1-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="ad7c1-140">Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 kan [du kontakta support.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="ad7c1-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="ad7c1-141">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="ad7c1-141">Related content</span></span>

<span data-ttu-id="ad7c1-142">[Så här betalar du för prenumerationen med en faktureringsprofil](pay-for-subscription-billing-profile.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ad7c1-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="ad7c1-143">[Förstå faktureringskonton](../manage-billing-accounts.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ad7c1-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="ad7c1-144">[Hantera betalningsmetoder](manage-payment-methods.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ad7c1-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
