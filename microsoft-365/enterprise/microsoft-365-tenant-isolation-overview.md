---
title: Tenant Isolation i Microsoft 365
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
description: Den här artikeln innehåller en sammanfattning av hur Microsoft tillämpar innehavarisolering i molntjänster som Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194655"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="75205-103">Tenant Isolation i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75205-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="75205-104">En av de främsta fördelarna med molnbaserad databehandling är konceptet med en delad, gemensam infrastruktur över flera kunder samtidigt, vilket leder till att många kunder blir större.</span><span class="sxs-lookup"><span data-stu-id="75205-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="75205-105">Det här begreppet kallas *för flera innehavare.*</span><span class="sxs-lookup"><span data-stu-id="75205-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="75205-106">Microsoft arbetar kontinuerligt för att säkerställa att arkitekturer för flera innehavare i våra molntjänster har stöd för säkerhet på företagsnivå, konfidentialitet, sekretess, integritet och tillgänglighetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="75205-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="75205-107">Microsofts molntjänster har utformats utifrån antagandet [](https://www.microsoft.com/securityengineering/sdl/)att alla innehavare potentiellt är aktuella för alla andra klientorganisationen och vi har implementerat säkerhetsåtgärder för att förhindra att en klientorganisations säkerhet eller tjänst påverkar säkerheten eller tjänsten hos en annan klientorganisation, eller att få åtkomst till innehållet i en annan klientorganisation. [](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="75205-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="75205-108">De två primära målen med att behålla innehavarisolering i en miljö med flera klientorganisationen är:</span><span class="sxs-lookup"><span data-stu-id="75205-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="75205-109">Förhindra läckage av, eller obehörig åtkomst till, kundinnehåll i flera klientorganisationen. och</span><span class="sxs-lookup"><span data-stu-id="75205-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="75205-110">Förhindra att en klientorganisations åtgärder påverkar tjänsten för en annan klientorganisation negativt</span><span class="sxs-lookup"><span data-stu-id="75205-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="75205-111">Flera olika former av skydd har implementerats i hela Microsoft 365 för att förhindra att kunder komprometteras Microsoft 365-tjänster eller -program eller få obehörig åtkomst till informationen från andra klientprogram eller till Microsoft 365-systemet, inklusive:</span><span class="sxs-lookup"><span data-stu-id="75205-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="75205-112">Logisk avgränsning av kundinnehållet i varje klientorganisation för Microsoft 365 tjänster kan åstadkommas Azure Active Directory auktorisering och rollbaserad åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="75205-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="75205-113">SharePoint Online tillhandahåller mekanismer för dataisolering på lagringsnivån.</span><span class="sxs-lookup"><span data-stu-id="75205-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="75205-114">Microsoft använder fysisk säkerhet, bakgrundskontroller och en flerlagerskrypteringsstrategi för att skydda kundinnehållets konfidentialitet och integritet.</span><span class="sxs-lookup"><span data-stu-id="75205-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="75205-115">Alla Microsoft 365 har biometriska åtkomstkontroller, med mest krav på palmutskrifter för att få fysisk åtkomst.</span><span class="sxs-lookup"><span data-stu-id="75205-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="75205-116">Dessutom krävs alla USA-baserade Microsoft-anställda för att genomföra en standardbakgrundskontroll som en del av anställningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="75205-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="75205-117">Mer information om de kontroller som används för administrativ åtkomst i Microsoft 365 finns i [Microsoft 365 Administrationsåtkomstkontroller.](/compliance/assurance/assurance-administrative-access-controls-overview)</span><span class="sxs-lookup"><span data-stu-id="75205-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).</span></span>
- <span data-ttu-id="75205-118">Microsoft 365 använder tjänstebaserade tekniker som krypterar kundinnehåll vid vila och överföring, inklusive BitLocker, kryptering per fil, TLS (Transport Layer Security) och IPsec (Internet Protocol Security).</span><span class="sxs-lookup"><span data-stu-id="75205-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="75205-119">Specifik information om kryptering i Microsoft 365 finns i [Datakrypteringsteknik i Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75205-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="75205-120">Tillsammans tillhandahåller de ovan listade skydden robusta logiska avgränsningskontroller som tillhandahåller skydd mot hot och åtgärder som motsvarar det som tillhandahålls av fysisk avgränsning.</span><span class="sxs-lookup"><span data-stu-id="75205-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="75205-121">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="75205-121">Related Links</span></span>

- [<span data-ttu-id="75205-122">Isolering och åtkomstkontroll i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="75205-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="75205-123">Klientisolering i Office Graph och Delve</span><span class="sxs-lookup"><span data-stu-id="75205-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="75205-124">Innehavarisolering i Microsoft 365 sökning</span><span class="sxs-lookup"><span data-stu-id="75205-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="75205-125">Resursgränser</span><span class="sxs-lookup"><span data-stu-id="75205-125">Resource Limits</span></span>](/compliance/assurance/assurance-resource-limits)
- [<span data-ttu-id="75205-126">Övervaka och testa klientorganisations begränsningar</span><span class="sxs-lookup"><span data-stu-id="75205-126">Monitoring and Testing Tenant Boundaries</span></span>](/compliance/assurance/assurance-monitoring-and-testing)
- [<span data-ttu-id="75205-127">Isolerings- och åtkomstkontroll i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75205-127">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)