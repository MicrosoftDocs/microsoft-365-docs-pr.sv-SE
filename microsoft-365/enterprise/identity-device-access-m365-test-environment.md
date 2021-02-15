---
title: Identitets- och enhetsåtkomst till testmiljön för Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233734"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a8e00-103">Identitets- och enhetsåtkomst till testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8e00-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a8e00-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företags testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="a8e00-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a8e00-105">[Konfigurationer för identitets-](../security/office-365-security/microsoft-365-policies-configurations.md) och enhetsåtkomst är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a8e00-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="a8e00-106">Så här skapar du en testmiljö som har de vanligaste konfigurationerna för identitets- och enhetsåtkomst:</span><span class="sxs-lookup"><span data-stu-id="a8e00-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="a8e00-107">Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:</span><span class="sxs-lookup"><span data-stu-id="a8e00-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="a8e00-108">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="a8e00-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="a8e00-109">Synkronisering av lösenordshashar (PHS)</span><span class="sxs-lookup"><span data-stu-id="a8e00-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="a8e00-110">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="a8e00-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="a8e00-111">Använd [principer för common identity and device access](identity-access-policies.md) till att konfigurera principerna som bygger på de krav som är konfigurerade för testmiljön och utforska och verifiera skydd för identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="a8e00-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8e00-112">Se även</span><span class="sxs-lookup"><span data-stu-id="a8e00-112">See also</span></span>

[<span data-ttu-id="a8e00-113">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="a8e00-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="a8e00-114">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="a8e00-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="a8e00-115">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a8e00-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8e00-116">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a8e00-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a8e00-117">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a8e00-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
