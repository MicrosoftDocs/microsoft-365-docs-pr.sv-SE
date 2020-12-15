---
title: Förstå fakturerings profiler
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
description: Lär dig hur fakturerings profiler stöder fakturor.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667783"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="2230a-103">Förstå fakturerings profiler</span><span class="sxs-lookup"><span data-stu-id="2230a-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2230a-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="2230a-104">The admin center is changing.</span></span> <span data-ttu-id="2230a-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="2230a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="2230a-106">För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med hjälp av fakturerings profiler anpassa vilka objekt som ska ingå på din faktura och hur du betalar dina fakturor.</span><span class="sxs-lookup"><span data-stu-id="2230a-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="2230a-107">Fakturerings profiler innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="2230a-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="2230a-108">**Fakturerings konto** &ndash; Namnet på kontot som profilen är relaterad till</span><span class="sxs-lookup"><span data-stu-id="2230a-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="2230a-109">**Betalnings metoder** &ndash; Kredit-eller betalkort, bank konton, check eller överföring</span><span class="sxs-lookup"><span data-stu-id="2230a-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="2230a-110">**Kontakt information** &ndash; Fakturerings adress och ett kontakt namn</span><span class="sxs-lookup"><span data-stu-id="2230a-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="2230a-111">**Faktura inställningar** &ndash; Valuta baserat på fakturerings kontots land, ett valfritt inköps order nummer och alternativet att ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="2230a-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="2230a-112">**Behörigheter** &ndash; för Behörigheter som gör att du kan ändra fakturerings profil, betala räkningar eller använda betalnings metoden i fakturerings profilen för att göra inköp</span><span class="sxs-lookup"><span data-stu-id="2230a-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="2230a-113">Använd betalnings profiler för att kontrol lera dina inköp och anpassa din faktura.</span><span class="sxs-lookup"><span data-stu-id="2230a-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="2230a-114">En månads faktura genereras för de produkter som köpts med fakturerings profilen.</span><span class="sxs-lookup"><span data-stu-id="2230a-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="2230a-115">Du kan anpassa fakturan, till exempel uppdatera inköps order numret och preferensen för e-post.</span><span class="sxs-lookup"><span data-stu-id="2230a-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="2230a-116">En fakturerings profil skapas automatiskt för ditt fakturerings konto under ditt första inköp.</span><span class="sxs-lookup"><span data-stu-id="2230a-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="2230a-117">Du kan skapa fakturerings profiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">faktura profiler</a> för att registrera fler fakturor.</span><span class="sxs-lookup"><span data-stu-id="2230a-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="2230a-118">Du kan till exempel använda olika fakturerings profiler när du gör inköp för varje avdelning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2230a-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="2230a-119">Vid nästa fakturerings datum får du en faktura för varje fakturerings profil.</span><span class="sxs-lookup"><span data-stu-id="2230a-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="2230a-120">Roller för fakturerings profiler</span><span class="sxs-lookup"><span data-stu-id="2230a-120">Billing profile roles</span></span>

<span data-ttu-id="2230a-121">Roller i fakturerings profiler har behörighet att kontrol lera inköp samt Visa och hantera fakturor.</span><span class="sxs-lookup"><span data-stu-id="2230a-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="2230a-122">Tilldela dessa roller till användare som spårar, strukturerar och betalar fakturor, till exempel medlemmar i anskaffnings gruppen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="2230a-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="2230a-123">Roll</span><span class="sxs-lookup"><span data-stu-id="2230a-123">Role</span></span>                          | <span data-ttu-id="2230a-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2230a-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="2230a-125">Ägare till fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-125">Billing profile owner</span></span>         | <span data-ttu-id="2230a-126">Hantera allt för en fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="2230a-127">Deltagare i fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-127">Billing profile contributor</span></span>   | <span data-ttu-id="2230a-128">Hantera allt utom behörigheter i en fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="2230a-129">Profil läsare</span><span class="sxs-lookup"><span data-stu-id="2230a-129">Billing profile reader</span></span>        | <span data-ttu-id="2230a-130">Skrivskyddad vy av allt i en fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="2230a-131">Faktura chef</span><span class="sxs-lookup"><span data-stu-id="2230a-131">Invoice manager</span></span>               | <span data-ttu-id="2230a-132">Visa och betala räkningar och har en skrivskyddad vy av allt i en fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="2230a-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="2230a-133">Visa fakturerings profiler</span><span class="sxs-lookup"><span data-stu-id="2230a-133">View billing profiles</span></span>

1. <span data-ttu-id="2230a-134">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.</span><span class="sxs-lookup"><span data-stu-id="2230a-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="2230a-135">Välj **betalnings profiler** och välj sedan en fakturerings profil i listan.</span><span class="sxs-lookup"><span data-stu-id="2230a-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="2230a-136">På fliken **Översikt** kan du redigera information om fakturerings profiler och aktivera eller inaktivera en faktura via e-post.</span><span class="sxs-lookup"><span data-stu-id="2230a-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="2230a-137">På fliken **behörigheter** kan du tilldela roller till användare för att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="2230a-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="2230a-138">På fliken för **Azure-saldot** kan Azure-kunder se historik för transaktions sal Don för de Azure-tillgodohavanden som används av den betalnings profilen.</span><span class="sxs-lookup"><span data-stu-id="2230a-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="2230a-139">På fliken **Azure-kredit** kan Azure-kunderna se en lista över de Azure-tillgodohavanden som är kopplade till fakturerings profilen och deras utgångs datum.</span><span class="sxs-lookup"><span data-stu-id="2230a-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2230a-140">Om du inte har något Azure-tillgodohavande visas inte flikarna för **Azure-saldo** eller **Azure** -kredit.</span><span class="sxs-lookup"><span data-stu-id="2230a-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="2230a-141">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="2230a-141">Need help?</span></span> <span data-ttu-id="2230a-142">Kontakta supporten.</span><span class="sxs-lookup"><span data-stu-id="2230a-142">Contact support.</span></span>

<span data-ttu-id="2230a-143">Om du har frågor eller behöver hjälp med dina Azure-avgifter kan du <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapa en supportbegäran med Azure-support</a>.</span><span class="sxs-lookup"><span data-stu-id="2230a-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="2230a-144">Om du har frågor eller behöver hjälp med din fakturerings profil i Microsoft 365 Admin Center kan du [kontakta supporten för företags produkter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="2230a-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
