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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Läs om hur faktureringsprofiler stöder fakturor.
keywords: faktureringsprofil, fakturor, avgifter, hanterade avgifter
ms.openlocfilehash: 64f0f6bf456b1251a2db49aa9c2f7473cb7c885b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401780"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="6cfa5-104">Hantera faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="6cfa5-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6cfa5-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-105">The admin center is changing.</span></span> <span data-ttu-id="6cfa5-106">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6cfa5-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6cfa5-107">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med faktureringsprofiler anpassa vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="6cfa5-108">Faktureringsprofiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="6cfa5-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="6cfa5-109">**Faktureringskonto** &ndash; Namnet på det faktureringskonto som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="6cfa5-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="6cfa5-110">**Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring</span><span class="sxs-lookup"><span data-stu-id="6cfa5-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="6cfa5-111">**Kontaktuppgifter** &ndash; Faktureringsadress och ett kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="6cfa5-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="6cfa5-112">**Inställningar för** &ndash; faktura Valuta baserat på faktureringskontots land, ett valfritt inköpsordernummer och möjlighet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="6cfa5-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="6cfa5-113">**Behörigheter** &ndash; Behörigheter som gör att du kan ändra faktureringsprofilen, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="6cfa5-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="6cfa5-114">Använd faktureringsprofiler för att styra dina inköp och anpassa fakturan.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="6cfa5-115">En månadsfaktura genereras för de produkter som köpts med faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="6cfa5-116">Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och e-fakturainställningarna.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="6cfa5-117">En faktureringsprofil skapas automatiskt för ditt faktureringskonto under ditt första köp.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="6cfa5-118">Du kan skapa faktureringsprofiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a> för att ställa in fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="6cfa5-119">Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="6cfa5-120">På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="6cfa5-121">Faktureringsprofilroller</span><span class="sxs-lookup"><span data-stu-id="6cfa5-121">Billing profile roles</span></span>

<span data-ttu-id="6cfa5-122">Roller på faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="6cfa5-123">Tilldela dessa roller till användare som spårar, organiserar och betalar fakturor, till exempel medlemmar i anskaffningsteamet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="6cfa5-124">Roll</span><span class="sxs-lookup"><span data-stu-id="6cfa5-124">Role</span></span>                          | <span data-ttu-id="6cfa5-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6cfa5-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="6cfa5-126">Ägare av faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-126">Billing profile owner</span></span>         | <span data-ttu-id="6cfa5-127">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="6cfa5-128">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-128">Billing profile contributor</span></span>   | <span data-ttu-id="6cfa5-129">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="6cfa5-130">Läsare av faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-130">Billing profile reader</span></span>        | <span data-ttu-id="6cfa5-131">Skrivskyddad vy över allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="6cfa5-132">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="6cfa5-132">Invoice manager</span></span>               | <span data-ttu-id="6cfa5-133">Visa och betala räkningar och har en skrivskyddad vy över allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6cfa5-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="6cfa5-134">Visa faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="6cfa5-134">View billing profiles</span></span>

1. <span data-ttu-id="6cfa5-135">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="6cfa5-136">Välj **Faktureringsprofiler**och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="6cfa5-137">På fliken **Översikt** kan du redigera information om faktureringsprofilen och aktivera eller inaktivera att skicka en faktura via e-post.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="6cfa5-138">På fliken **Behörigheter** kan du tilldela användare roller att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="6cfa5-139">På fliken **Azure-kreditsaldo** kan Azure-kunder se transaktionssaldohistorik för De Azure-krediter som används av faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="6cfa5-140">På fliken **Azure-krediter** kan Azure-kunder se en lista över Azure-krediter som är associerade med faktureringsprofilen och deras utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cfa5-141">Om du inte har några Azure-krediter visas inte **flikarna Azure-kreditsaldo** eller **Azure-krediter.**</span><span class="sxs-lookup"><span data-stu-id="6cfa5-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="6cfa5-142">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="6cfa5-142">Need help?</span></span> <span data-ttu-id="6cfa5-143">Kontakta supporten.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-143">Contact support.</span></span>

<span data-ttu-id="6cfa5-144">Om du har frågor eller behöver hjälp med dina Azure-avgifter <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapar du en supportbegäran med Azure-support</a>.</span><span class="sxs-lookup"><span data-stu-id="6cfa5-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="6cfa5-145">Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365-administrationscentret [kontaktar du supporten för företagsprodukter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="6cfa5-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
