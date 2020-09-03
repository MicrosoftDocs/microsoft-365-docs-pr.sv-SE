---
title: Klient isolering i Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Den här artikeln innehåller en sammanfattning av hur Microsoft tillämpar klient isolering i moln tjänster som Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7aca35fc61d03e94225375fcf67970e13dd691c9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332694"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="4947f-103">Klient isolering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4947f-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="4947f-104">En av de främsta fördelarna med Cloud Computing är begreppet gemensam, gemensam infrastruktur för många kunder samtidigt, vilket leder till stor drifts för delar.</span><span class="sxs-lookup"><span data-stu-id="4947f-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="4947f-105">Det här konceptet kallas för *flera organisationer*.</span><span class="sxs-lookup"><span data-stu-id="4947f-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="4947f-106">Microsoft arbetar kontinuerligt för att säkerställa att multi-Tenant-arkitekturer i våra moln tjänster har stöd för säkerhet, konfidentialitet, integritet, integritet och tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="4947f-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="4947f-107">Baserat på de betydande investeringar och erfarenhet som samlats in från [tillförlitliga datorer](https://www.microsoft.com/trust-center) och [livs cykeln för säkerhets utveckling](https://www.microsoft.com/securityengineering/sdl/)har Microsofts moln tjänster utformats med antagandet att alla klient organisationer kan vara farliga för alla andra klient organisationer, och vi har implementerat säkerhets åtgärder för att förhindra att en klient organisation påverkar säkerheten eller tjänsten hos en annan klient organisation eller åtkomst till innehållet i en annan klient organisation.</span><span class="sxs-lookup"><span data-stu-id="4947f-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="4947f-108">Två primära mål för underhåll av klient isolering i en miljö med flera innehavare är:</span><span class="sxs-lookup"><span data-stu-id="4947f-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="4947f-109">Förhindra läckage av eller obehörig åtkomst till kund innehåll mellan klient organisationer; och</span><span class="sxs-lookup"><span data-stu-id="4947f-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="4947f-110">Förhindra att en klient organisations åtgärder påverkar tjänsten för en annan klient organisation negativt</span><span class="sxs-lookup"><span data-stu-id="4947f-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="4947f-111">Flera former av skydd har implementerats i Microsoft 365 för att förhindra att kunder kan kompromissa med Microsoft 365-tjänster och-program eller skaffa obehörig åtkomst till information om andra klient organisationer eller Microsoft 365-systemet, inklusive:</span><span class="sxs-lookup"><span data-stu-id="4947f-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="4947f-112">Logisk isolering av kund innehåll inom varje klient organisation för Microsoft 365-tjänster uppnås genom Azure Active Directory-auktorisering och rollbaserad åtkomst kontroll.</span><span class="sxs-lookup"><span data-stu-id="4947f-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="4947f-113">I SharePoint Online finns mekanismer för data isolering på lagrings nivån.</span><span class="sxs-lookup"><span data-stu-id="4947f-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="4947f-114">Microsoft använder rigorös fysisk säkerhet, bakgrunds gallrings och en kryptering med flera nivåer för att skydda konfidentialitet och integritet hos kund innehåll.</span><span class="sxs-lookup"><span data-stu-id="4947f-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="4947f-115">Alla Microsoft 365-datacenter har till gång till bio metriska kontroller, med de flesta krav på att en hand dator får fysisk åtkomst.</span><span class="sxs-lookup"><span data-stu-id="4947f-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="4947f-116">Dessutom måste alla amerikanska Microsoft-anställda genomföra en vanlig bakgrunds kontroll som en del av anslags processen.</span><span class="sxs-lookup"><span data-stu-id="4947f-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="4947f-117">Mer information om de kontroller som används för administrativ åtkomst i Microsoft 365 finns i [microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4947f-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="4947f-118">I Microsoft 365 används teknikbaserade tekniker som krypterar kund innehåll på rest och under överföring, inklusive BitLocker, kryptering för alla filer, TLS (Transport Layer Security) och IPsec (Internet Protocol Security).</span><span class="sxs-lookup"><span data-stu-id="4947f-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="4947f-119">Specifik information om kryptering i Microsoft 365 finns i [data krypterings teknologier i microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="4947f-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span>

<span data-ttu-id="4947f-120">Tillsammans ger de ovanstående skydden robusta logiska isolerings kontroller som skyddar mot hotets skydd och mildrande ämnen.</span><span class="sxs-lookup"><span data-stu-id="4947f-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="4947f-121">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="4947f-121">Related Links</span></span>

- [<span data-ttu-id="4947f-122">Isolering och åtkomstkontroll i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4947f-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="4947f-123">Klientisolering i Office Graph och Delve</span><span class="sxs-lookup"><span data-stu-id="4947f-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="4947f-124">Klient isolering i Microsoft 365 search</span><span class="sxs-lookup"><span data-stu-id="4947f-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="4947f-125">Klient isolering i Office 365 Video</span><span class="sxs-lookup"><span data-stu-id="4947f-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="4947f-126">Resursgränser</span><span class="sxs-lookup"><span data-stu-id="4947f-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="4947f-127">Övervaka och testa klientorganisations begränsningar</span><span class="sxs-lookup"><span data-stu-id="4947f-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="4947f-128">Isolering och åtkomst kontroll i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4947f-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
