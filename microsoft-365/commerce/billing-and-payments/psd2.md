---
title: Betalningstjänstdirektiv 2 och stark kundautentisering för kommersiella kunder
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Från och med den 14 september 2019 måste banker i de 31 länderna i Europeiska ekonomiska samarbetsområdet kontrollera identiteten på den person som gör ett onlineköp innan betalningen kan behandlas.
keywords: betalningstjänstdirektiv 2, stark kundautentisering, multifaktorautentisering
ms.openlocfilehash: 571664736ac4c6e825398a076597bf4b69ec31a8
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402220"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="6e1e4-104">Betalningstjänstdirektiv 2 och stark kundautentisering för kommersiella kunder</span><span class="sxs-lookup"><span data-stu-id="6e1e4-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="6e1e4-105">Från och med den 14 september 2019 måste banker i de 31 länderna i Europeiska ekonomiska samarbetsområdet kontrollera identiteten på den person som gör ett onlineköp innan betalningen kan behandlas.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="6e1e4-106">Den här verifieringen kräver multifaktorautentisering för att säkerställa att dina onlineköp är säkra och skyddade.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="6e1e4-107">Datumet för detta kontrollkrav kommer att försenas för vissa länder.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="6e1e4-108">Mer information finns i [Microsofts vanliga frågor och svar om betalningstjänstdirektiv 2 och stark kundautentisering](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="6e1e4-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="6e1e4-109">När krävs multifaktorautentisering?</span><span class="sxs-lookup"><span data-stu-id="6e1e4-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="6e1e4-110">För närvarande gäller kontrollkrav för detta direktiv med multifaktorautentisering endast för kunder som använder kreditkort från banker i de 31 länderna i Europeiska ekonomiska samarbetsområdet.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="6e1e4-111">Ibland tillfrågas kunder på grund av en åtgärd som de vidtog, och ibland uppmanas de på grund av händelser med sina befintliga prenumerationer eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="6e1e4-112">Kundens åtgärder</span><span class="sxs-lookup"><span data-stu-id="6e1e4-112">Customer Actions</span></span>

<span data-ttu-id="6e1e4-113">Din bank kan kräva verifiering genom multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="6e1e4-114">Några exempel är:</span><span class="sxs-lookup"><span data-stu-id="6e1e4-114">Some examples include:</span></span>
- <span data-ttu-id="6e1e4-115">Registrera dig för en ny prenumeration</span><span class="sxs-lookup"><span data-stu-id="6e1e4-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="6e1e4-116">Lägga till licenser i en prenumeration</span><span class="sxs-lookup"><span data-stu-id="6e1e4-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="6e1e4-117">Lägga till eller byta ut kreditkortet som används för att betala för en prenumeration eller tjänst</span><span class="sxs-lookup"><span data-stu-id="6e1e4-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="6e1e4-118">Lägga till eller ersätta ett kreditkort i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="6e1e4-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="6e1e4-119">Köpa appar</span><span class="sxs-lookup"><span data-stu-id="6e1e4-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="6e1e4-120">Livscykelhändelser för prenumeration</span><span class="sxs-lookup"><span data-stu-id="6e1e4-120">Subscription lifecycle events</span></span>

<span data-ttu-id="6e1e4-121">Avgifter för återkommande betalningar kan misslyckas.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="6e1e4-122">Om de gör det får du ett e-postmeddelande med instruktioner att följa.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="6e1e4-123">Du uppmanas att svara på verifieringsbegäran och göra din aktuella betalning.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="6e1e4-124">Behöver du mer hjälp?</span><span class="sxs-lookup"><span data-stu-id="6e1e4-124">Need more help?</span></span>

<span data-ttu-id="6e1e4-125">Din finansiella institution är den bästa kontakten för dessa scenarier:</span><span class="sxs-lookup"><span data-stu-id="6e1e4-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="6e1e4-126">Du fick ingen verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="6e1e4-127">Verifieringsprocessen fungerade inte när du skickade verifieringskoden.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="6e1e4-128">Du är osäker på om kontaktinformationen för ditt kreditkort är korrekt.</span><span class="sxs-lookup"><span data-stu-id="6e1e4-128">You're not sure if the contact info for your credit card is correct.</span></span>
