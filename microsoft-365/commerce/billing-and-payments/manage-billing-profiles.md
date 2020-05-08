---
title: Hantera faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Läs om hur faktureringsprofiler stöder fakturor.
keywords: faktureringsprofil, fakturor, avgifter, hanterade avgifter
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140896"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="77a8d-104">Hantera faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="77a8d-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="77a8d-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="77a8d-105">The admin center is changing.</span></span> <span data-ttu-id="77a8d-106">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="77a8d-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="77a8d-107">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med faktureringsprofiler anpassa vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="77a8d-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="77a8d-108">Faktureringsprofiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="77a8d-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="77a8d-109">**Faktureringskonto** &ndash; Namn på det faktureringskonto som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="77a8d-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="77a8d-110">**Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring</span><span class="sxs-lookup"><span data-stu-id="77a8d-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="77a8d-111">**Kontaktuppgifter** &ndash; Faktureringsadress och ett kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="77a8d-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="77a8d-112">**Fakturainställningar** &ndash; Valuta baserat på faktureringskontots land, ett valfritt inköpsordernummer och alternativet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="77a8d-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="77a8d-113">**Behörigheter** &ndash; Behörigheter som gör att du kan ändra faktureringsprofilen, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="77a8d-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="77a8d-114">Använd faktureringsprofiler för att styra dina inköp och anpassa fakturan.</span><span class="sxs-lookup"><span data-stu-id="77a8d-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="77a8d-115">En månadsfaktura genereras för de produkter som köpts med faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="77a8d-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="77a8d-116">Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och e-fakturainställningarna.</span><span class="sxs-lookup"><span data-stu-id="77a8d-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="77a8d-117">En faktureringsprofil skapas automatiskt för ditt faktureringskonto under ditt första köp.</span><span class="sxs-lookup"><span data-stu-id="77a8d-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="77a8d-118">Du kan skapa faktureringsprofiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a> för att ställa in fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="77a8d-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="77a8d-119">Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="77a8d-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="77a8d-120">På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="77a8d-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="77a8d-121">Faktureringsprofilroller</span><span class="sxs-lookup"><span data-stu-id="77a8d-121">Billing profile roles</span></span>

<span data-ttu-id="77a8d-122">Roller på faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="77a8d-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="77a8d-123">Tilldela dessa roller till användare som spårar, organiserar och betalar fakturor, till exempel medlemmar i anskaffningsteamet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="77a8d-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="77a8d-124">Roll</span><span class="sxs-lookup"><span data-stu-id="77a8d-124">Role</span></span>                          | <span data-ttu-id="77a8d-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="77a8d-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="77a8d-126">Ägare av faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-126">Billing profile owner</span></span>         | <span data-ttu-id="77a8d-127">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="77a8d-128">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-128">Billing profile contributor</span></span>   | <span data-ttu-id="77a8d-129">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="77a8d-130">Läsare av faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-130">Billing profile reader</span></span>        | <span data-ttu-id="77a8d-131">Skrivskyddad vy över allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="77a8d-132">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="77a8d-132">Invoice manager</span></span>               | <span data-ttu-id="77a8d-133">Visa och betala räkningar och har en skrivskyddad vy över allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="77a8d-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="77a8d-134">Visa faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="77a8d-134">View billing profiles</span></span>

1. <span data-ttu-id="77a8d-135">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="77a8d-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="77a8d-136">Välj **Faktureringsprofiler**och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="77a8d-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="77a8d-137">På fliken **Översikt** kan du redigera information om faktureringsprofilen och aktivera eller inaktivera att skicka en faktura via e-post.</span><span class="sxs-lookup"><span data-stu-id="77a8d-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="77a8d-138">På fliken **Behörigheter** kan du tilldela användare roller att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="77a8d-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="77a8d-139">På fliken **Azure-kreditsaldo** kan Azure-kunder se transaktionssaldohistorik för De Azure-krediter som används av faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="77a8d-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="77a8d-140">På fliken **Azure-krediter** kan Azure-kunder se en lista över Azure-krediter som är associerade med faktureringsprofilen och deras utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="77a8d-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77a8d-141">Om du inte har några Azure-krediter visas inte **flikarna Azure-kreditsaldo** eller **Azure-krediter.**</span><span class="sxs-lookup"><span data-stu-id="77a8d-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="77a8d-142">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="77a8d-142">Need help?</span></span> <span data-ttu-id="77a8d-143">Kontakta supporten.</span><span class="sxs-lookup"><span data-stu-id="77a8d-143">Contact support.</span></span>

<span data-ttu-id="77a8d-144">Om du har frågor eller behöver hjälp med dina Azure-avgifter <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapar du en supportbegäran med Azure-support</a>.</span><span class="sxs-lookup"><span data-stu-id="77a8d-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="77a8d-145">Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365-administrationscentret [kontaktar du supporten för företagsprodukter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="77a8d-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
