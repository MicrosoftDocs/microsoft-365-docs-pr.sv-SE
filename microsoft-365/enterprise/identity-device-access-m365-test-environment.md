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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitets- och enhetsåtkomst till testmiljön för Microsoft 365

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

[Identitets- och enhetsåtkomstkonfigurationer](../security/defender-365-security/microsoft-365-policies-configurations.md) är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).

Så här skapar du en testmiljö med vanliga konfigurationer för identitets- och enhetsåtkomst:

1. Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:

  - [Endast molnet](cloud-only-prereqs-m365-test-environment.md)
  - [Synkronisering av lösenordshashar (PHS)](phs-prereqs-m365-test-environment.md)
  - [Direktautentisering (PTA)](pta-prereqs-m365-test-environment.md)

2. Använd [Vanliga principer för identitets-](../security/defender-365-security/identity-access-policies.md) och enhetsåtkomst för att konfigurera principer som bygger på de krav som är konfigurerade för testmiljön och utforska och verifiera skydd för identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)
