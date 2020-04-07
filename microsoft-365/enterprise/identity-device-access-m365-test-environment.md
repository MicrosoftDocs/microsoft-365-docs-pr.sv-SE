---
title: Identitets- och enhetsåtkomst till testmiljön för Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst.
ms.openlocfilehash: 45749140698553a75df50ed1111cdbfc8eb15684
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153744"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8f363-103">Identitets- och enhetsåtkomst till testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f363-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8f363-104">*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="8f363-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8f363-105">[Konfigurationerna för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) är en uppsättning funktioner och principer för villkorsstyrd åtkomst som skyddar åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD), inklusive Office 365 och Microsoft Intune i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8f363-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and Conditional Access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="8f363-106">Om du vill skapa en testmiljö som har följande principer:</span><span class="sxs-lookup"><span data-stu-id="8f363-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="8f363-107">Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:</span><span class="sxs-lookup"><span data-stu-id="8f363-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="8f363-108">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="8f363-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8f363-109">Lösenordshash-synkronisering (PHS)</span><span class="sxs-lookup"><span data-stu-id="8f363-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8f363-110">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="8f363-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="8f363-111">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och identitets- och enhetsskyddet i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="8f363-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f363-112">Se även</span><span class="sxs-lookup"><span data-stu-id="8f363-112">See also</span></span>

[<span data-ttu-id="8f363-113">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="8f363-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="8f363-114">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="8f363-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8f363-115">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8f363-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8f363-116">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8f363-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8f363-117">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="8f363-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
