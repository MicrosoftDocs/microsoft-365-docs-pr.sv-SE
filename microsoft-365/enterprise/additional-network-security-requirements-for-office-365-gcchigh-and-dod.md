---
title: Ytterligare nätverkssäkerhetskrav för Office 365 GCC Hög och DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Sammanfattning: Office 365 GCC Hög och DoD har ytterligare nätverksäkerhetskrav'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926565"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="37bd2-103">Ytterligare nätverkssäkerhetskrav för Office 365 GCC High and DOD</span><span class="sxs-lookup"><span data-stu-id="37bd2-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="37bd2-104">*Den här artikeln gäller för Office 365 GCC, Office 365 DOD, Microsoft 365 GCC Hög och Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="37bd2-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="37bd2-105">Office 365 GCC Hög och DOD är säkra molnmiljöer för att uppfylla behoven hos myndigheter i USA och dess leverantörer och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="37bd2-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="37bd2-106">De här molnmiljöerna har ytterligare nätverksbegränsningar för vilka externa slutpunkter tjänsterna har tillåtelse att komma åt.</span><span class="sxs-lookup"><span data-stu-id="37bd2-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="37bd2-107">GCC Kunder med hög behörighet och DOD som planerar att använda externa identiteter eller hybrid-samexistens kan kräva att Microsoft tillåter inkommande och/eller utgående åtkomst till dina befintliga lokala distributioner.</span><span class="sxs-lookup"><span data-stu-id="37bd2-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="37bd2-108">Några exempel på sådana aktiviteter är:</span><span class="sxs-lookup"><span data-stu-id="37bd2-108">Examples of these activities include:</span></span>

* <span data-ttu-id="37bd2-109">Användning av externa identiteter (med Active Directory Federation Services eller liknande STS)</span><span class="sxs-lookup"><span data-stu-id="37bd2-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="37bd2-110">Hybridexistens med lokal distribution Exchange Server eller Skype för företag hybriddistribution</span><span class="sxs-lookup"><span data-stu-id="37bd2-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="37bd2-111">Migrering av befintligt användarinnehåll från ett lokalt system</span><span class="sxs-lookup"><span data-stu-id="37bd2-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="37bd2-112">Om du vill tillåta att tjänsten kommunicerar  med dina lokala slutpunkter måste du skicka ett e-postmeddelande Office 365 teknik för nätverksändringar.</span><span class="sxs-lookup"><span data-stu-id="37bd2-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="37bd2-113">Alla begäranden har ett **serviceavtal på tre** veckor och kan inte underlättas på grund av de säkerhets- och efterlevnadskontroller och distributionsförlopp som krävs.</span><span class="sxs-lookup"><span data-stu-id="37bd2-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="37bd2-114">Detta inkluderar första onboarding nätverksbegäranden samt eventuella ändringar när du har migrerat till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="37bd2-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="37bd2-115">Kontrollera att nätverksteamen känner till tidslinjen och tar med den i planeringscyklerna.</span><span class="sxs-lookup"><span data-stu-id="37bd2-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="37bd2-116">Skicka ett [e-postmeddelande Office 365 för myndigheter Allow-List förfrågningar](mailto:o365gwlt@microsoft.com) med följande information:</span><span class="sxs-lookup"><span data-stu-id="37bd2-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="37bd2-117">**Till:** [Office 365 för myndigheter Allow-List Förfrågningar](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="37bd2-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="37bd2-118">**Från:** En innehavaradministratör – skicka e-postmeddelandet **måste** matcha en global administratörskontakt i klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="37bd2-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="37bd2-119">**E-postämne:** Office 365 GCC hög nätverksbegäran – contoso.onmicrosoft.us (ersätt med ditt klientnamn)</span><span class="sxs-lookup"><span data-stu-id="37bd2-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="37bd2-120">Brödtexten i meddelandet ska innehålla följande data:</span><span class="sxs-lookup"><span data-stu-id="37bd2-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="37bd2-121">Namnet på din Microsoft Online Services-klient (till exempel contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="37bd2-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="37bd2-122">En e-postdistributionslista som Microsoft kommunicerar med för den kommunikation som är relaterad till nätverksändringar och/eller uppföljning för ogiltiga undernät</span><span class="sxs-lookup"><span data-stu-id="37bd2-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="37bd2-123">Ange om du planerar Microsoft Teams att använda hybridexistens med dina lokala distributioner</span><span class="sxs-lookup"><span data-stu-id="37bd2-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="37bd2-124">Externt tillgängligt URL-adresssystem (till exempel sts.contoso.com) och IP-adressintervall i CIDR-notation (till exempel.</span><span class="sxs-lookup"><span data-stu-id="37bd2-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="37bd2-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="37bd2-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="37bd2-126">URL och IP-adressintervall för lokal PKI-certifikatåterkallningslista i CIDR-notation</span><span class="sxs-lookup"><span data-stu-id="37bd2-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="37bd2-127">Externt tillgängligt URL- och IP-adressintervall för Exchange Server lokal distribution i CIDR-notation</span><span class="sxs-lookup"><span data-stu-id="37bd2-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="37bd2-128">Externt tillgängligt URL- och IP-adressintervall för Skype för företag lokal distribution i CIDR-notation</span><span class="sxs-lookup"><span data-stu-id="37bd2-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="37bd2-129">Av säkerhetsskäl och efterlevnadsskäl bör du tänka på följande begränsningar för din begäran:</span><span class="sxs-lookup"><span data-stu-id="37bd2-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="37bd2-130">Det finns en fyra undernätsbegränsning per klientorganisation</span><span class="sxs-lookup"><span data-stu-id="37bd2-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="37bd2-131">Undernät måste vara i CIDR-notation (till exempel 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="37bd2-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="37bd2-132">Undernätsområden kan inte vara större än /24</span><span class="sxs-lookup"><span data-stu-id="37bd2-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="37bd2-133">Vi **kan** inte ta emot förfrågningar om att tillåta åtkomst till kommersiella molntjänster (Office 365, Google G-Suite, Amazon Web Services osv.)</span><span class="sxs-lookup"><span data-stu-id="37bd2-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="37bd2-134">När din begäran har tagits emot och godkänts av Microsoft finns det ett treveckors SLA för implementering och kan inte genomföras.</span><span class="sxs-lookup"><span data-stu-id="37bd2-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="37bd2-135">Du får en första bekräftelse när vi har fått din begäran och en slutgiltig bekräftelse när den har slutförts.</span><span class="sxs-lookup"><span data-stu-id="37bd2-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
