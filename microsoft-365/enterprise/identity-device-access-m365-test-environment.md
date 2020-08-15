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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst.
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685860"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4fa6b-103">Identitets- och enhetsåtkomst till testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4fa6b-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4fa6b-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="4fa6b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4fa6b-105">[Konfigurationer för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md) är en uppsättning funktioner och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4fa6b-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="4fa6b-106">Om du vill skapa en testmiljö som har följande principer:</span><span class="sxs-lookup"><span data-stu-id="4fa6b-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="4fa6b-107">Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:</span><span class="sxs-lookup"><span data-stu-id="4fa6b-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="4fa6b-108">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="4fa6b-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="4fa6b-109">Lösenordshash-synkronisering (PHS)</span><span class="sxs-lookup"><span data-stu-id="4fa6b-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="4fa6b-110">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="4fa6b-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="4fa6b-111">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och identitets- och enhetsskyddet i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fa6b-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fa6b-112">Se även</span><span class="sxs-lookup"><span data-stu-id="4fa6b-112">See also</span></span>

[<span data-ttu-id="4fa6b-113">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="4fa6b-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="4fa6b-114">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="4fa6b-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="4fa6b-115">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4fa6b-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4fa6b-116">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4fa6b-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4fa6b-117">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="4fa6b-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
