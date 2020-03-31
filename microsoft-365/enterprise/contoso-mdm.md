---
title: Hantering av mobila enheter på Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ta reda på hur Contoso använder Microsoft Intune i Microsoft 365 Enterprise för att hantera enheter och apparna som körs på dem.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811813"
---
# <a name="mobile-device-management-for-contoso"></a>Hantering av mobila enheter på Contoso

Microsoft 365 Enterprise omfattar Intune och en uppsättning Azure-tjänster som stöder hantering av mobila enheter, appar och säkerhet.

Det är många på Contoso som använder mobila enheter i jobbet. En del av dem arbetar på något av Contosos kontor och andra har inget kontor. Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.

## <a name="plan"></a>Planera

När Contoso började analysera hanteringen av mobila enheter för Microsoft 365 Enterprise identifierades följande användningsfall för Intune:

- Skydda Exchange Online-e-post och data så att de kan nås på ett säkert sätt med mobila enheter
- Implementera ett BYOD-program (Bring Your Own Device) för Contosos anställda
- Dela ut företagsägda telefoner och delade surfplattor med begränsad användning till Contosos anställda

Contoso använder inte Intune för att:

- Ge anställda tillgång till Office 365 på ett säkert sätt från en ohanterad offentlig helskärmsenhet
- Skydda lokala e-postmeddelanden och data så att de kan användas på ett säkert sätt på mobila enheter, eftersom det inte längre finns lokala Microsoft Exchange-servrar.

## <a name="deploy"></a>Distribuera

Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:

- Intune har angetts som utfärdare av mobilenhetshantering och Intune används på Azure för att administrera innehåll och hantera enheterna
- Azure AD-grupper har skapats för enheter för registrering, och Intune-inställningar och enhetsbaserade principer för villkorsstyrd åtkomst har angetts

  Mer information finns i [Principer för villkorlig åtkomst](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Apples enhetsplattform har aktiverats för att stödja medarbetare med egen iPad, iMac och iPhone, och även företagsägda iPhone-telefoner
- Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter
- För enheter som inte är registrerade finns en uppsättning principer för hantering av mobila program (MAM) som kräver autentisering för åtkomst till Office 365-tjänster
- Intune-principer har skapats för att tillämpa:
  - Tillåtna appar
  - Enhetskryptering för att förhindra obehörig åtkomst
  - PIN-kod eller lösenord med sex siffror
  - En tidsgräns för inaktivitet
  - Antivirusskydd, skydd mot skadlig kod och signaturuppdateringar med Windows Defender på Windows 10-enheter
  - Automatiska uppdateringar för Windows 10-enheter som innehåller de senaste säkerhetsuppdateringarna
  - Push-överföring av certifikat till hanterade enheter
  - En tydlig åtskillnad mellan företagsdata och personliga data. Användare och administratörer kan selektivt rensa företagsdata från enheten medan personliga data, till exempel bilder, personliga e-postkonton och personliga filer, bevaras.

Efter distributionen registrerade Contoso datorer och företagsägda telefoner och surfplattor genom att lägga till dem i lämpliga Intune-enhetsgrupper, och Contoso distribuerade ett BYOD-program så att medarbetarna kunde registrera sina personliga enheter. De registrerade enheterna fick Intune-principer, vilket innebär att dessa enheter och tillhörande appar nu är hanterade och skyddade. För enheter som inte har registrerats används principer för hantering av mobila program (MAM) som anger vilka appar som är tillåtna.

Här är Contosos distributionsarkitektur för hantering av mobila enheter.

![Contosos distributionsarkitektur för hantering av mobila enheter.](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Nästa steg

[Lär dig](contoso-info-protect.md) hur Contoso använder funktioner för informationsskydd i Microsoft 365 Enterprise för att klassificera, identifiera och skydda viktiga digitala tillgångar i hela organisationen.

## <a name="see-also"></a>Se även

[Hantering av mobila enheter för Microsoft 365 Enterprise](mobility-infrastructure.md)

[Distributionsguide](deploy-microsoft-365-enterprise.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)

