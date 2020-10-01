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
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327813"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitets- och enhetsåtkomst till testmiljön för Microsoft 365

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

[Konfigurationer för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md) är en uppsättning funktioner och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster som är integrerade med Azure Active Directory (Azure AD).

Så här skapar du en test miljö med vanliga konfigurationer för identitets-och enhets åtkomst:

1. Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:

  - [Endast molnet](cloud-only-prereqs-m365-test-environment.md)
  - [Lösenordssynkronisering för lösen ord (PHS)](phs-prereqs-m365-test-environment.md)
  - [Direktautentisering (PTA)](pta-prereqs-m365-test-environment.md)

2. Använd [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md) för att konfigurera de principer som bygger på kraven som har kon figurer ATS för test miljön och undersöka och verifiera skydd för identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
