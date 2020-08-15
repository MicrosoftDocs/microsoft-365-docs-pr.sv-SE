---
title: Ytterligare nätverks säkerhets krav för Office 365 GCC High and DoD
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
description: 'Sammanfattning: Office 365 GCC High and DoD har ytterligare nätverks säkerhets krav'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694609"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="1ca5d-103">Ytterligare nätverks säkerhets krav för Office 365 GCC High and DOD</span><span class="sxs-lookup"><span data-stu-id="1ca5d-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="1ca5d-104">*Den här artikeln gäller Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High och Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="1ca5d-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="1ca5d-105">Office 365 GCC High and DOD är säkra moln miljöer för att uppfylla behoven hos Förenta staternas regering och dess leverantörer och entreprenörer.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="1ca5d-106">Dessa moln miljöer har ytterligare nätverks begränsningar för vilka externa slut punkter som tjänsterna tillåts komma åt.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="1ca5d-107">GCC hög och DOD kund planering för att använda federerade identiteter eller hybrid samexistens kan kräva att Microsoft tillåter inkommande och/eller utgående åtkomst till dina befintliga lokala distributioner.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="1ca5d-108">Här är några exempel på dessa aktiviteter:</span><span class="sxs-lookup"><span data-stu-id="1ca5d-108">Examples of these activities include:</span></span>

* <span data-ttu-id="1ca5d-109">Användning av federerade identiteter (med Active Directory Federation Services eller ett likartat stöd för STS)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="1ca5d-110">Hybrid samexistens med en lokal Exchange-Server eller Skype för företag-distribution</span><span class="sxs-lookup"><span data-stu-id="1ca5d-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="1ca5d-111">Migrering av befintliga användar innehåll från ett lokalt system</span><span class="sxs-lookup"><span data-stu-id="1ca5d-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="1ca5d-112">För att tjänsten ska kunna kommunicera med dina lokala slut punkter **måste** du skicka ett e-postmeddelande till Office 365 Engineering för nätverks ändringar.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="1ca5d-113">Alla begär Anden har en **tre veckors** SLA och kan inte påskyndas på grund av de kontroll-och distributions ledningar som krävs.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="1ca5d-114">Detta inkluderar inledande nätverks förfrågningar samt eventuella ändringar efter att du har migrerat till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="1ca5d-115">Se till att nätverks teamen är medvetna om tids linjen och inkludera den i deras planerings cyklar.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="1ca5d-116">Skicka ett e-postmeddelande till [Office 365 statligt Lägg](mailto:o365gwlt@microsoft.com) med följande information:</span><span class="sxs-lookup"><span data-stu-id="1ca5d-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="1ca5d-117">**Till**: [Office 365 statligt Lägg](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="1ca5d-118">**Från**: en klient organisations administratör – e-postmeddelandet **måste** matcha en global administratörs kontakt i klient organisationen</span><span class="sxs-lookup"><span data-stu-id="1ca5d-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="1ca5d-119">**E-postadress ämne**: Office 365 gcc High Network Request-contoso.onmicrosoft.us (Byt ut mot klient organisationens namn)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="1ca5d-120">Bröd texten i meddelandet bör innehålla följande data:</span><span class="sxs-lookup"><span data-stu-id="1ca5d-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="1ca5d-121">Ditt klient namn för Microsoft Online Services (till exempel contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="1ca5d-122">En distributions lista för e-post som Microsoft kommunicerar med för pågående kommunikation relaterade till nätverks ändringar och/eller uppföljning för ogiltiga undernät</span><span class="sxs-lookup"><span data-stu-id="1ca5d-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="1ca5d-123">Ange om du planerar att använda Microsoft Teams hybrid Co-existens med lokala distributioner</span><span class="sxs-lookup"><span data-stu-id="1ca5d-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="1ca5d-124">Externt identitets system (till exempel sts.contoso.com) och IP-adressintervall i CIDR-notation (t. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="1ca5d-125">Lista med URL-adresser och IP-adressintervall för den lokala PKI-certifikat i CIDR-notation</span><span class="sxs-lookup"><span data-stu-id="1ca5d-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="1ca5d-126">Externt tillgängliga URL-adresser och IP-adressintervall för en Exchange Server-lokal distribution i CIDR-notering</span><span class="sxs-lookup"><span data-stu-id="1ca5d-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="1ca5d-127">Externt tillgängliga URL-adresser och IP-adressintervall för en lokal distribution av Skype för företag i CIDR-notering</span><span class="sxs-lookup"><span data-stu-id="1ca5d-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="1ca5d-128">Av säkerhets-och kontroll skäl bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="1ca5d-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="1ca5d-129">Det finns fyra begränsningar för undernät per klient organisation</span><span class="sxs-lookup"><span data-stu-id="1ca5d-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="1ca5d-130">Undernät måste vara i CIDR-notation (till exempel 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="1ca5d-131">Under nätets intervall får inte vara större än/24</span><span class="sxs-lookup"><span data-stu-id="1ca5d-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="1ca5d-132">Vi **kan inte** hantera begär Anden om att tillåta åtkomst till kommersiella moln tjänster (kommersiella Office 365, Google G-Suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="1ca5d-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="1ca5d-133">När din begäran har tagits emot och godkänts av Microsoft är det ett tre veckors SLA för implementering och kan inte påskyndas.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="1ca5d-134">Du får en första bekräftelse när vi har tagit emot din begäran och en slutgiltig bekräftelse när den har genomförts.</span><span class="sxs-lookup"><span data-stu-id="1ca5d-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
