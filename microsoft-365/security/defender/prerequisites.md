---
title: Microsoft 365 Defender-krav
description: Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft 365 Defender
keywords: krav, krav, maskinvara, programvara, webbläsare, Microsoft 365 Defender, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259409"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender-krav

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs mer om licensiering och andra krav för etablering och användning [av Microsoft 365 Defender](microsoft-365-defender.md).

## <a name="licensing-requirements"></a>Licenskrav
Någon av dessa licenser ger dig tillgång Microsoft 365 Defender-funktioner Microsoft 365 säkerhetscenter utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E3 med Microsoft 365 E5 Security tillägg
- Microsoft 365 A3 med Microsoft 365 tillägg för A5-säkerhet
- Windows 10 Enterprise E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender för Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)

Mer information finns [i Microsoft 365 Enterprise tjänstplaner.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Har du inte licens ännu? [Prova eller köp en Microsoft 365-prenumeration](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Kontrollera dina befintliga licenser
Gå till Microsoft 365 (i[admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser. Gå till Faktureringslicenser i  >  **administrationscentret.**

>[!NOTE]
> Du måste ha tilldelats rollen **Faktureringsadministratör** **eller Global** läsare i [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation. Kontakta en global administratör om du stöter på åtkomstproblem.

## <a name="required-permissions"></a>Behörighet som krävs
Du måste vara **global administratör eller** **säkerhetsadministratör i Azure Active Directory** kunna aktivera Microsoft 365 Defender. Den lista över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomsten till data är reglerade finns i hantera åtkomst till [Microsoft 365 Defender.](m365d-permissions.md)

## <a name="browser-requirements"></a>Webbläsarkrav
Access Microsoft 365 Defender i säkerhetscentret i Microsoft 365 via Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Tillgänglighet för amerikanska GCC, GCC hög och andra amerikanska statliga myndigheter
För närvarande Microsoft 365 Defender *inte* tillgänglig för:
- Us Government Community Cloud (GCC)
- Us Government Community Cloud High (GCC High)
- US Department of Defense
- Alla amerikanska statliga myndigheter med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Microsoft 365 Defender-översikt](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md)
- [Hantera åtkomst och behörigheter](m365d-permissions.md)
