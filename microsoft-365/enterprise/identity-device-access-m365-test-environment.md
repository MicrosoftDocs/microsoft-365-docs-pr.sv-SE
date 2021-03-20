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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907474"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitets- och enhetsåtkomst till testmiljön för Microsoft 365

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

[Identitets- och enhetsåtkomstkonfigurationer](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).

Så här skapar du en testmiljö med vanliga konfigurationer för identitets- och enhetsåtkomst:

1. Konfigurera testmiljön med nödvändiga identitets- och säkerhetsfunktioner baserat på ditt val av identitetsmodell och autentiseringsmetod:

  - [Endast molnet](cloud-only-prereqs-m365-test-environment.md)
  - [Synkronisering av lösenordshashar (PHS)](phs-prereqs-m365-test-environment.md)
  - [Direktautentisering (PTA)](pta-prereqs-m365-test-environment.md)

2. Använd [Vanliga principer för identitets-](../security/office-365-security/identity-access-policies.md) och enhetsåtkomst för att konfigurera principer som bygger på de krav som är konfigurerade för testmiljön och utforska och verifiera skydd för identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)