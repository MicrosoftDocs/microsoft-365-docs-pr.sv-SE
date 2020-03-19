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
ms.openlocfilehash: e43483afc9e17de9582b2998867b53cfff7d8492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812583"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="de171-103">Identitets- och enhetsåtkomst till testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de171-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="de171-104">*Den här testlabbsguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="de171-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="de171-105">[Konfigurationerna för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) är en uppsättning funktioner och villkorliga åtkomstprinciper som skyddar åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD), inklusive Office 365 och Microsoft Intune i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="de171-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="de171-106">Om du vill skapa en testmiljö som har följande principer:</span><span class="sxs-lookup"><span data-stu-id="de171-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="de171-107">Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:</span><span class="sxs-lookup"><span data-stu-id="de171-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="de171-108">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="de171-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="de171-109">Lösenordshash-synkronisering (PHS)</span><span class="sxs-lookup"><span data-stu-id="de171-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="de171-110">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="de171-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="de171-111">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och identitets- och enhetsskyddet i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="de171-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="de171-112">Se även</span><span class="sxs-lookup"><span data-stu-id="de171-112">See also</span></span>

[<span data-ttu-id="de171-113">Fler testlabbsguider för identitet</span><span class="sxs-lookup"><span data-stu-id="de171-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="de171-114">Fas 2: identitet</span><span class="sxs-lookup"><span data-stu-id="de171-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="de171-115">Testlabbsguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de171-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="de171-116">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="de171-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="de171-117">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="de171-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
