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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitets- och enhetsåtkomst till testmiljön för Microsoft 365

*Den här testlabbsguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

[Konfigurationerna för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) är en uppsättning funktioner och villkorliga åtkomstprinciper som skyddar åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD), inklusive Office 365 och Microsoft Intune i Microsoft 365 Enterprise.

Om du vill skapa en testmiljö som har följande principer:

1. Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:

  - [Endast molnet](cloud-only-prereqs-m365-test-environment.md)
  - [Lösenordshash-synkronisering (PHS)](phs-prereqs-m365-test-environment.md)
  - [Direktautentisering (PTA)](pta-prereqs-m365-test-environment.md)

2. Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och identitets- och enhetsskyddet i testmiljön.

## <a name="see-also"></a>Se även

[Fler testlabbsguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Fas 2: identitet](identity-infrastructure.md)

[Testlabbsguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
