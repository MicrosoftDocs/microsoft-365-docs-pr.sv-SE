---
title: Förstå faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma
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
- PPM_jmueller
search.appverid: MET150
description: Läs om hur faktureringsprofiler har stöd för fakturor.
ms.date: 04/02/2021
ms.openlocfilehash: 57786df370246c2b4fda556a9c48eb828db1cb4f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280793"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="6a420-103">Förstå faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="6a420-103">Understand billing profiles</span></span>

<span data-ttu-id="6a420-104">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du anpassa faktureringsprofilerna vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a420-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="6a420-105">Faktureringsprofiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="6a420-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="6a420-106">**Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="6a420-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="6a420-107">**Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring</span><span class="sxs-lookup"><span data-stu-id="6a420-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="6a420-108">**Kontaktinformation** &ndash; Faktureringsadress och kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="6a420-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="6a420-109">**Fakturainställningar** &ndash; Valuta baserat på landet för faktureringskontot, ett valfritt inköpsordernummer och alternativet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="6a420-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="6a420-110">**Behörigheter** &ndash; Behörigheter som gör att du kan ändra faktureringsprofil, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="6a420-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="6a420-111">Använd faktureringsprofiler för att styra dina köp och anpassa fakturan.</span><span class="sxs-lookup"><span data-stu-id="6a420-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="6a420-112">En månadsfaktura skapas för produkter som köpts med faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="6a420-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="6a420-113">Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och inställningen för e-postfaktura.</span><span class="sxs-lookup"><span data-stu-id="6a420-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="6a420-114">En faktureringsprofil skapas automatiskt för ditt faktureringskonto vid ditt första köp.</span><span class="sxs-lookup"><span data-stu-id="6a420-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="6a420-115">Du kan skapa faktureringsprofiler på <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">sidan Faktureringsprofiler</a> om du vill konfigurera fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a420-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="6a420-116">Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6a420-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="6a420-117">På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="6a420-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="6a420-118">Faktureringsprofilroller</span><span class="sxs-lookup"><span data-stu-id="6a420-118">Billing profile roles</span></span>

<span data-ttu-id="6a420-119">Roller i faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a420-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="6a420-120">Tilldela de här rollerna till användare som spårar, organiserar och betalar fakturor, t.ex. medlemmar i organisationens anskaffningsteam.</span><span class="sxs-lookup"><span data-stu-id="6a420-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="6a420-121">Roll</span><span class="sxs-lookup"><span data-stu-id="6a420-121">Role</span></span>                         | <span data-ttu-id="6a420-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6a420-122">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="6a420-123">Faktureringsprofilägare</span><span class="sxs-lookup"><span data-stu-id="6a420-123">Billing profile owner</span></span>        | <span data-ttu-id="6a420-124">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6a420-124">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="6a420-125">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6a420-125">Billing profile contributor</span></span>  | <span data-ttu-id="6a420-126">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6a420-126">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="6a420-127">Faktureringsprofilläsare</span><span class="sxs-lookup"><span data-stu-id="6a420-127">Billing profile reader</span></span>       | <span data-ttu-id="6a420-128">Skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6a420-128">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="6a420-129">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="6a420-129">Invoice manager</span></span>              | <span data-ttu-id="6a420-130">Visa och betala räkningar och har en skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6a420-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-billing-profiles"></a><span data-ttu-id="6a420-131">Visa faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="6a420-131">View billing profiles</span></span>

1. <span data-ttu-id="6a420-132">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="6a420-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="6a420-133">Välj **Faktureringsprofiler** och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="6a420-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="6a420-134">På fliken **Översikt** kan du redigera faktureringsprofilinformation och aktivera eller inaktivera fakturautskick via e-post.</span><span class="sxs-lookup"><span data-stu-id="6a420-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>
    - <span data-ttu-id="6a420-135">På fliken **Behörigheter** kan du tilldela roller till användare för att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a420-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>
    - <span data-ttu-id="6a420-136">På fliken **Azure-kreditsaldo** kan Azure-kunder se historik för transaktionssaldo för Azure-krediter som används av den faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="6a420-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>
    - <span data-ttu-id="6a420-137">På fliken **Azure-krediter** kan Azure-kunder se en lista över Azure-krediter som är kopplade till den faktureringsprofilen och deras utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="6a420-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a420-138">Om du inte har några Azure-krediter visas inte flikarna **Azure-kreditsaldo** **eller Azure-krediter.**</span><span class="sxs-lookup"><span data-stu-id="6a420-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="6a420-139">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="6a420-139">Need help?</span></span> <span data-ttu-id="6a420-140">Kontakta support</span><span class="sxs-lookup"><span data-stu-id="6a420-140">Contact support</span></span>

<span data-ttu-id="6a420-141">Om du har frågor eller behöver hjälp med dina Azure-avgifter kan <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">du skapa en supportbegäran med Azure-supporten.</a></span><span class="sxs-lookup"><span data-stu-id="6a420-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="6a420-142">Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 kan [du kontakta supporten för företagsprodukter.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="6a420-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](../../business-video/get-help-support.md).</span></span>
