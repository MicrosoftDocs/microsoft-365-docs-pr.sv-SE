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
ms.openlocfilehash: c9bd089843bcb620dc3feb8ec3e8f946cd739d17
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811497"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="d3783-104">Hantera faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="d3783-104">Manage billing profiles</span></span>
<span data-ttu-id="d3783-105">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med faktureringsprofilerna anpassa vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="d3783-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="d3783-106">Faktureringsprofiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="d3783-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="d3783-107">**Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="d3783-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="d3783-108">**Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring</span><span class="sxs-lookup"><span data-stu-id="d3783-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="d3783-109">**Kontaktuppgifter** &ndash; Faktureringsadress och ett kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="d3783-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="d3783-110">**Fakturainställningar** &ndash; Valuta baserat på faktureringskontots land, ett valfritt inköpsordernummer och möjlighet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="d3783-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="d3783-111">**Behörigheter** &ndash; behörigheter som gör att du kan ändra faktureringsprofil, lönefakturor eller använda betalningsmetoden i faktureringsprofilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="d3783-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="d3783-112">Använd faktureringsprofiler för att styra dina inköp och anpassa fakturan.</span><span class="sxs-lookup"><span data-stu-id="d3783-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="d3783-113">En månadsfaktura genereras för de produkter som köps med faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="d3783-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="d3783-114">Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och inställningen för e-postfaktura.</span><span class="sxs-lookup"><span data-stu-id="d3783-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="d3783-115">En faktureringsprofil skapas automatiskt för ditt faktureringskonto under ditt första köp.</span><span class="sxs-lookup"><span data-stu-id="d3783-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="d3783-116">Du kan skapa faktureringsprofiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a> för att ställa in fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="d3783-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="d3783-117">Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d3783-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="d3783-118">På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="d3783-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="d3783-119">Roller för faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-119">Billing profile roles</span></span>

<span data-ttu-id="d3783-120">Roller för faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="d3783-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="d3783-121">Tilldela dessa roller till användare som spårar, organiserar och betalar fakturor, till exempel medlemmar i anskaffningsteamet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d3783-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="d3783-122">Roll</span><span class="sxs-lookup"><span data-stu-id="d3783-122">Role</span></span>                          | <span data-ttu-id="d3783-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d3783-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="d3783-124">Ägare av faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-124">Billing profile owner</span></span>         | <span data-ttu-id="d3783-125">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="d3783-126">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-126">Billing profile contributor</span></span>   | <span data-ttu-id="d3783-127">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="d3783-128">Läsare av faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="d3783-128">Billing profile reader</span></span>        | <span data-ttu-id="d3783-129">Skrivskyddad vy över allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="d3783-130">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="d3783-130">Invoice manager</span></span>               | <span data-ttu-id="d3783-131">Visa och betala räkningar och har en skrivskyddad bild av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="d3783-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="d3783-132">Visa faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="d3783-132">View billing profiles</span></span>

1. <span data-ttu-id="d3783-133">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="d3783-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="d3783-134">Välj **Faktureringsprofiler**och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="d3783-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="d3783-135">På fliken **Översikt** kan du redigera information om faktureringsprofil och aktivera eller inaktivera skicka en faktura via e-post.</span><span class="sxs-lookup"><span data-stu-id="d3783-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="d3783-136">På fliken **Behörigheter** kan du tilldela roller till användare att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="d3783-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="d3783-137">På fliken **Azure-kreditsaldo** kan Azure-kunder se transaktionsbalanshistorik för Azure-krediter som används av faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="d3783-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="d3783-138">På fliken **Azure-krediter kan Azure-kunder** se en lista över Azure-krediter som är associerade med faktureringsprofilen och deras utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="d3783-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3783-139">Om du inte har några Azure-krediter visas inte flikarna **Azure-kreditsaldo** eller **Azure-krediter.**</span><span class="sxs-lookup"><span data-stu-id="d3783-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="d3783-140">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="d3783-140">Need help?</span></span> <span data-ttu-id="d3783-141">Kontakta supporten.</span><span class="sxs-lookup"><span data-stu-id="d3783-141">Contact support.</span></span>

<span data-ttu-id="d3783-142">Om du har frågor eller behöver hjälp med dina <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure-avgifter skapar du en supportbegäran med Azure-supporten</a>.</span><span class="sxs-lookup"><span data-stu-id="d3783-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="d3783-143">Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 administrationscenter [kontaktar du supporten för företagsprodukter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="d3783-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
