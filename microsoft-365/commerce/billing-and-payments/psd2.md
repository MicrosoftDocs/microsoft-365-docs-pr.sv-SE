---
title: Betal tjänster, direktiv 2 och grundlig kundpool för kommersiella kunder
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Från och med den 14 september 2019 måste bankerna i det Europeiska ekonomiska samarbetsområdet verifiera identiteten hos den person som gör ett online-köp innan betalningen kan behandlas.
keywords: betal tjänster, direktiv 2, stark kundpool, multifaktorautentisering
ms.openlocfilehash: fc8784949cdacea10957660c99795b4ade0f9f7a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638429"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="3740e-104">Betal tjänster, direktiv 2 och grundlig kundpool för kommersiella kunder</span><span class="sxs-lookup"><span data-stu-id="3740e-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="3740e-105">Från och med den 14 september 2019 måste bankerna i det Europeiska ekonomiska samarbetsområdet verifiera identiteten hos den person som gör ett online-köp innan betalningen kan behandlas.</span><span class="sxs-lookup"><span data-stu-id="3740e-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="3740e-106">Denna verifiering kräver multifaktorautentisering för att säkerställa att dina inköp online är säkra och skyddade.</span><span class="sxs-lookup"><span data-stu-id="3740e-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="3740e-107">Datumet för det här verifierings kravet kommer att senareläggas för vissa länder.</span><span class="sxs-lookup"><span data-stu-id="3740e-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="3740e-108">Mer information finns i [Microsoft vanliga frågor och svar om betal tjänster, direktiv 2 och grundlig kundpool](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="3740e-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="3740e-109">När krävs multifaktorautentisering?</span><span class="sxs-lookup"><span data-stu-id="3740e-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="3740e-110">För närvarande gäller verifierings kraven för det här direktivet med multifaktorautentisering endast för kunder som använder kredit kort från banker i Europeiska ekonomiska samarbetsområdet.</span><span class="sxs-lookup"><span data-stu-id="3740e-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="3740e-111">Ibland uppmanas kunder på grund av en åtgärd som de vidtog och ibland uppmanas de på grund av händelser med sina befintliga abonnemang eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="3740e-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="3740e-112">Kund åtgärder</span><span class="sxs-lookup"><span data-stu-id="3740e-112">Customer Actions</span></span>

<span data-ttu-id="3740e-113">Din bank kan kräva verifiering genom multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="3740e-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="3740e-114">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="3740e-114">Some examples include:</span></span>
- <span data-ttu-id="3740e-115">Registrera dig för ett nytt abonnemang</span><span class="sxs-lookup"><span data-stu-id="3740e-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="3740e-116">Lägga till licenser i en prenumeration</span><span class="sxs-lookup"><span data-stu-id="3740e-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="3740e-117">Lägga till eller ersätta kredit kortet som används för att betala för ett abonnemang eller en tjänst</span><span class="sxs-lookup"><span data-stu-id="3740e-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="3740e-118">Lägga till eller ersätta ett kredit kort i en fakturerings profil</span><span class="sxs-lookup"><span data-stu-id="3740e-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="3740e-119">Köpa appar</span><span class="sxs-lookup"><span data-stu-id="3740e-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="3740e-120">Abonnemangs livs cykel händelser</span><span class="sxs-lookup"><span data-stu-id="3740e-120">Subscription lifecycle events</span></span>

<span data-ttu-id="3740e-121">Avgifter för återkommande betalningar kan Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="3740e-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="3740e-122">Om de gör det får du ett e-postmeddelande med instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3740e-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="3740e-123">Du uppmanas att svara på verifierings förfrågan och göra din nuvarande betalning.</span><span class="sxs-lookup"><span data-stu-id="3740e-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="3740e-124">Behöver du mer hjälp?</span><span class="sxs-lookup"><span data-stu-id="3740e-124">Need more help?</span></span>

<span data-ttu-id="3740e-125">Ditt finans institut är den bästa kontakten för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="3740e-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="3740e-126">Du fick ingen verifierings kod.</span><span class="sxs-lookup"><span data-stu-id="3740e-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="3740e-127">Verifierings processen fungerade inte när du skickade verifierings koden.</span><span class="sxs-lookup"><span data-stu-id="3740e-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="3740e-128">Du är osäker på om kontakt informationen för ditt kredit kort är korrekt.</span><span class="sxs-lookup"><span data-stu-id="3740e-128">You're not sure if the contact info for your credit card is correct.</span></span>
