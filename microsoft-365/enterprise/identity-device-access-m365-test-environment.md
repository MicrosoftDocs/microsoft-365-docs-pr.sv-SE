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
ms.openlocfilehash: e90c27edbf4ad5a78c337bf2488956ce82a1ec3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051324"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="44252-103">Identitets- och enhetsåtkomst till testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44252-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="44252-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="44252-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="44252-105">[Identitets- och enhetsåtkomstkonfigurationer](../security/defender-365-security/microsoft-365-policies-configurations.md) är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="44252-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="44252-106">Så här skapar du en testmiljö med vanliga konfigurationer för identitets- och enhetsåtkomst:</span><span class="sxs-lookup"><span data-stu-id="44252-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="44252-107">Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:</span><span class="sxs-lookup"><span data-stu-id="44252-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="44252-108">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="44252-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="44252-109">Synkronisering av lösenordshashar (PHS)</span><span class="sxs-lookup"><span data-stu-id="44252-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="44252-110">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="44252-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="44252-111">Använd [Vanliga principer för identitets-](../security/defender-365-security/identity-access-policies.md) och enhetsåtkomst för att konfigurera principer som bygger på de krav som är konfigurerade för testmiljön och utforska och verifiera skydd för identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="44252-111">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="44252-112">Se även</span><span class="sxs-lookup"><span data-stu-id="44252-112">See also</span></span>

[<span data-ttu-id="44252-113">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="44252-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="44252-114">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="44252-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="44252-115">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44252-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="44252-116">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44252-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="44252-117">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44252-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
