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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Intune i Microsoft 365 för företag för att hantera dess enheter och programmen som körs på dem.
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685848"
---
# <a name="mobile-device-management-for-contoso"></a>Hantering av mobila enheter på Contoso

Microsoft 365 för Enterprise inkluderar Intune och en uppsättning Azure-tjänster för att stödja mobil enhet och program hantering och säkerhet.

Det är många på Contoso som använder mobila enheter i jobbet. En del av dem arbetar på något av Contosos kontor och andra har inget kontor. Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.

## <a name="plan"></a>Planera

I och med att hantera mobila enheter för Microsoft 365 för företag, identifierade contoso följande Intune användnings fall:

- Skydda Exchange Online-e-post och data så att de kan nås på ett säkert sätt med mobila enheter
- Implementera ett BYOD-program (Bring Your Own Device) för Contosos anställda
- Dela ut företagsägda telefoner och delade surfplattor med begränsad användning till Contosos anställda

Contoso använder inte Intune för att:

- Tillåt anställda att säkert komma åt Microsoft 365 från en ohanterad offentlig kiosk
- Skydda lokala e-postmeddelanden och data så att de kan användas på ett säkert sätt på mobila enheter, eftersom det inte längre finns lokala Microsoft Exchange-servrar.

## <a name="deploy"></a>Distribuera

Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:

- Intune har angetts som utfärdare av mobilenhetshantering och Intune används på Azure för att administrera innehåll och hantera enheterna
- Azure AD-grupper har skapats för enheter för registrering, och Intune-inställningar och enhetsbaserade principer för villkorsstyrd åtkomst har angetts

  Mer information finns i [Principer för villkorlig åtkomst](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Apples enhetsplattform har aktiverats för att stödja medarbetare med egen iPad, iMac och iPhone, och även företagsägda iPhone-telefoner
- Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter
- För enheter som inte är registrerade, en uppsättning principer för MAM (Mobile Application Management) för att kräva åtkomst till Microsoft 365-tjänster
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

[Lär dig](contoso-info-protect.md) hur Contoso använder informations skydds funktionerna i Microsoft 365 för företag för att klassificera, identifiera och skydda viktiga digitala till gångar i sin organisation.

## <a name="see-also"></a>Se även

[Enhets hantering för Microsoft 365](device-management-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)

