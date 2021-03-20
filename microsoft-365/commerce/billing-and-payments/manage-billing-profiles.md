---
title: Förstå faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- Commerce
search.appverid:
- MET150
description: Läs om hur faktureringsprofiler har stöd för fakturor.
ms.openlocfilehash: 2f56b9a3edbbbe14927df64bed8b699a68826c9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911872"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="8137e-103">Förstå faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="8137e-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8137e-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8137e-104">The admin center is changing.</span></span> <span data-ttu-id="8137e-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8137e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8137e-106">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du anpassa faktureringsprofilerna vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="8137e-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="8137e-107">Faktureringsprofiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="8137e-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="8137e-108">**Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="8137e-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="8137e-109">**Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring</span><span class="sxs-lookup"><span data-stu-id="8137e-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="8137e-110">**Kontaktinformation** &ndash; Faktureringsadress och kontaktnamn</span><span class="sxs-lookup"><span data-stu-id="8137e-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="8137e-111">**Fakturainställningar** &ndash; Valuta baserat på landet för faktureringskontot, ett valfritt inköpsordernummer och alternativet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="8137e-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="8137e-112">**Behörigheter** &ndash; Behörigheter som gör att du kan ändra faktureringsprofil, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="8137e-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="8137e-113">Använd faktureringsprofiler för att styra dina köp och anpassa fakturan.</span><span class="sxs-lookup"><span data-stu-id="8137e-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="8137e-114">En månadsfaktura skapas för produkter som köpts med faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="8137e-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="8137e-115">Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och inställningen för e-postfaktura.</span><span class="sxs-lookup"><span data-stu-id="8137e-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="8137e-116">En faktureringsprofil skapas automatiskt för ditt faktureringskonto vid ditt första köp.</span><span class="sxs-lookup"><span data-stu-id="8137e-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="8137e-117">Du kan skapa faktureringsprofiler på <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">sidan Faktureringsprofiler</a> om du vill konfigurera fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="8137e-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="8137e-118">Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8137e-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="8137e-119">På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="8137e-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="8137e-120">Faktureringsprofilroller</span><span class="sxs-lookup"><span data-stu-id="8137e-120">Billing profile roles</span></span>

<span data-ttu-id="8137e-121">Roller i faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="8137e-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="8137e-122">Tilldela de här rollerna till användare som spårar, organiserar och betalar fakturor, t.ex. medlemmar i organisationens anskaffningsteam.</span><span class="sxs-lookup"><span data-stu-id="8137e-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="8137e-123">Roll</span><span class="sxs-lookup"><span data-stu-id="8137e-123">Role</span></span>                          | <span data-ttu-id="8137e-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8137e-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="8137e-125">Faktureringsprofilägare</span><span class="sxs-lookup"><span data-stu-id="8137e-125">Billing profile owner</span></span>         | <span data-ttu-id="8137e-126">Hantera allt för en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="8137e-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="8137e-127">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="8137e-127">Billing profile contributor</span></span>   | <span data-ttu-id="8137e-128">Hantera allt utom behörigheter i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="8137e-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="8137e-129">Faktureringsprofilläsare</span><span class="sxs-lookup"><span data-stu-id="8137e-129">Billing profile reader</span></span>        | <span data-ttu-id="8137e-130">Skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="8137e-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="8137e-131">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="8137e-131">Invoice manager</span></span>               | <span data-ttu-id="8137e-132">Visa och betala räkningar och har en skrivskyddad vy av allt i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="8137e-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="8137e-133">Visa faktureringsprofiler</span><span class="sxs-lookup"><span data-stu-id="8137e-133">View billing profiles</span></span>

1. <span data-ttu-id="8137e-134">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="8137e-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="8137e-135">Välj **Faktureringsprofiler** och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="8137e-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="8137e-136">På fliken **Översikt** kan du redigera faktureringsprofilinformation och aktivera eller inaktivera fakturautskick via e-post.</span><span class="sxs-lookup"><span data-stu-id="8137e-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="8137e-137">På fliken **Behörigheter** kan du tilldela roller till användare för att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="8137e-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="8137e-138">På fliken **Azure-kreditsaldo** kan Azure-kunder se historik för transaktionssaldo för Azure-krediter som används av den faktureringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="8137e-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="8137e-139">På fliken **Azure-krediter** kan Azure-kunder se en lista över Azure-krediter som är kopplade till den faktureringsprofilen och deras utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="8137e-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8137e-140">Om du inte har några Azure-krediter visas inte flikarna **Azure-kreditsaldo** **eller Azure-krediter.**</span><span class="sxs-lookup"><span data-stu-id="8137e-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="8137e-141">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="8137e-141">Need help?</span></span> <span data-ttu-id="8137e-142">Kontakta supporten.</span><span class="sxs-lookup"><span data-stu-id="8137e-142">Contact support.</span></span>

<span data-ttu-id="8137e-143">Om du har frågor eller behöver hjälp med dina Azure-avgifter kan <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">du skapa en supportbegäran med Azure-supporten.</a></span><span class="sxs-lookup"><span data-stu-id="8137e-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="8137e-144">Om du har frågor eller behöver hjälp med din faktureringsprofil i administrationscentret för Microsoft 365 [kontaktar du supporten för företagsprodukter.](/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="8137e-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>