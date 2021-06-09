---
title: Hantering av mobila enheter på Contoso
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Intune i Microsoft 365 för företag för att hantera dess enheter och program som körs på dem.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754003"
---
# <a name="mobile-device-management-for-contoso"></a>Hantering av mobila enheter på Contoso

Microsoft 365 för företag inkluderar Intune och en uppsättning Azure-tjänster som stöder hantering och säkerhet för mobila enheter och program.

Contoso har många anställda med mobilaktiverad personal. Vissa har kontor i Contoso-platser och vissa har inga kontor. Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.

## <a name="plan"></a>Planera

Contoso har identifierat följande Intune-användningsfall för hantering av mobila enheter Microsoft 365 för företag:

- Skydda Exchange Online e-post och data så att de kan nås säkert av mobila enheter.
- Implementera ett BYOD-program (bring-your-own-device) för Contoso-anställda.
- Utfärda telefoner som ägs av organisationen och delade surfplattor med begränsad användning till Contoso-anställda.

Contoso använder inte Intune för att:

- Tillåt anställda att på ett säkert sätt Microsoft 365 från en ohanterad offentlig kiosk.
- Skydda lokal e-post och data så att de kan nås säkert av mobila enheter, eftersom det inte finns några Microsoft Exchange lokala servrar.

## <a name="deploy"></a>Distribuera

Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:

- Ange Intune som MDM-myndighet (Mobile Device Management) och använd Intune i Azure för att administrera innehåll och hantera enheter
- Skapat Azure Active Directory (Azure AD) för enheter för registrering och Intune-inställningar och enhetsbaserade villkorsstyrda åtkomstprinciper

  Mer information finns i [Contosos villkorsstyrda åtkomstpolicyer.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)

- Apple-enhetsplattformen aktiverades för att ge stöd för anställda med iPad, iMacs och iPhone samt företagsägda iPhone
- Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter
- För enheter som inte är registrerade har implementerat en uppsättning principer för hantering av mobilprogram (MAM) för att kräva autentisering för åtkomst till Microsoft 365-tjänster
- Intune-principer har skapats för att tillämpa:
  - Tillåtna appar.
  - Enhetskryptering för att förhindra obehörig åtkomst.
  - En sexsiffrig PIN-kod eller ett lösenord.
  - En tidsgräns för inaktivitet.
  - Skydd mot antivirusprogram och skadlig programvara samt signaturuppdateringar med Windows Defender på Windows 10 enheter.
  - Automatiska uppdateringar på Windows 10 enheter som innehåller de senaste säkerhetsuppdateringarna.
  - Trycker på certifikat till hanterade enheter.
  - En tydlig åtskillnad mellan företagsdata och personliga data. Användare och administratörer kan selektivt rensa företagsdata från enheten medan personliga data, till exempel bilder, personliga e-postkonton och personliga filer, bevaras.

Contoso registrerade distribuerade datorer och företagsägda smartphones och handdatorer genom att lägga till dem i lämpliga Intune-enhetsgrupper. De upprättade även ett BYOD-program för anställda för att registrera sina personliga enheter. Registrerade enheter får Intune-principer, vilket resulterar i hanterade och skyddade enheter och deras program. Enheter som inte är registrerade har principer för hantering av mobilprogram (MAM) som anger tillåtna program.

Här är distributionsarkitekturen för hantering av mobila enheter i Contoso.

![Distributionsinfrastrukturen för hantering av mobila enheter i Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder funktionerna för [informationsskydd](contoso-info-protect.md) i Microsoft 365 för företag för att klassificera, identifiera och skydda viktiga digitala tillgångar i organisationen.

## <a name="see-also"></a>Se även

[Enhetshantering för Microsoft 365](device-management-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)

