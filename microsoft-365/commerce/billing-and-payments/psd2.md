---
title: Payment Services Directive 2 och Strong Customer Authentication för kommersiella kunder
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche
audience: Admin
ms.topic: article
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
description: Från och med den 14 september 2019 måste banker i de 31 länderna i europeiska ekonomiska samarbetsområdet verifiera identiteten på personen som gör ett onlineköp innan betalningen kan bearbetas."
keywords: payment services directive 2, strong customer authentication, multi-factor authentication
ms.date: 11/03/2020
ms.openlocfilehash: e687cac5bb1b7f1c88e9166993e29d437134e138
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280853"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="b4ed8-104">Payment Services Directive 2 och Strong Customer Authentication för kommersiella kunder</span><span class="sxs-lookup"><span data-stu-id="b4ed8-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="b4ed8-105">Från och med den 14 september 2019 måste banker i de 31 länderna i europeiska ekonomiska samarbetsområdet verifiera identiteten på personen som gör ett onlineköp innan betalningen kan bearbetas.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="b4ed8-106">Den här verifieringen kräver multifaktorautentisering för att säkerställa att dina onlineköp är säkra och skyddade.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="b4ed8-107">Datumet för den här verifieringskravet fördröjs i vissa länder.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="b4ed8-108">Mer information finns i [Microsofts vanliga frågor och svar om direktiv 2 för betalningstjänster och stark kundautentisering.](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)</span><span class="sxs-lookup"><span data-stu-id="b4ed8-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="b4ed8-109">När krävs multifaktorautentisering?</span><span class="sxs-lookup"><span data-stu-id="b4ed8-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="b4ed8-110">För närvarande gäller verifieringskrav för det här direktiv som använder multifaktorautentisering endast för kunder som använder kreditkort från banker i de 31 länderna i det europeiska ekonomiska samarbetsområdet.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="b4ed8-111">Ibland uppmanas kunder på grund av en åtgärd som de har vidta och ibland uppmanas de på grund av händelser med sina befintliga prenumerationer eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="b4ed8-112">Kundåtgärder</span><span class="sxs-lookup"><span data-stu-id="b4ed8-112">Customer Actions</span></span>

<span data-ttu-id="b4ed8-113">Din bank kan kräva verifiering via multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="b4ed8-114">Några exempel:</span><span class="sxs-lookup"><span data-stu-id="b4ed8-114">Some examples include:</span></span>

- <span data-ttu-id="b4ed8-115">Registrera dig för en ny prenumeration</span><span class="sxs-lookup"><span data-stu-id="b4ed8-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="b4ed8-116">Lägga till licenser i en prenumeration</span><span class="sxs-lookup"><span data-stu-id="b4ed8-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="b4ed8-117">Lägga till eller ersätta kreditkortet som används för att betala för en prenumeration eller tjänst</span><span class="sxs-lookup"><span data-stu-id="b4ed8-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="b4ed8-118">Lägga till eller ersätta ett kreditkort i en faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="b4ed8-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="b4ed8-119">Köpa appar</span><span class="sxs-lookup"><span data-stu-id="b4ed8-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="b4ed8-120">Livscykelhändelser för prenumerationer</span><span class="sxs-lookup"><span data-stu-id="b4ed8-120">Subscription lifecycle events</span></span>

<span data-ttu-id="b4ed8-121">Kostnader för återkommande betalningar kan misslyckas.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="b4ed8-122">Om de gör det får du ett e-postmeddelande med anvisningar om hur du följer dem.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="b4ed8-123">Du uppmanas att svara på verifieringsbegäran och göra din aktuella betalning.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="b4ed8-124">Behöver du mer hjälp?</span><span class="sxs-lookup"><span data-stu-id="b4ed8-124">Need more help?</span></span>

<span data-ttu-id="b4ed8-125">Ditt ekonomiska institution är den bästa kontakten för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="b4ed8-125">Your financial institution is the best contact for these scenarios:</span></span>

- <span data-ttu-id="b4ed8-126">Du har inte fått någon verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="b4ed8-127">Verifieringsprocessen fungerade inte när du skickade verifieringskoden.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="b4ed8-128">Du är osäker på om kontaktinformationen för ditt kreditkort stämmer.</span><span class="sxs-lookup"><span data-stu-id="b4ed8-128">You're not sure if the contact info for your credit card is correct.</span></span>
