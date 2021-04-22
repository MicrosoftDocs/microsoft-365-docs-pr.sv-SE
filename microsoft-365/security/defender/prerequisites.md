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
ms.openlocfilehash: 930a3de078d6d003241bb6fcd5df71bc9f301962
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935611"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender-krav

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs mer om licensiering och andra krav för etablering och användning av [Microsoft 365 Defender.](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>Licenskrav
Någon av dessa licenser ger dig tillgång till Microsoft 365 Defender-funktioner i Microsoft 365 säkerhetscenter utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5-säkerhet eller A5-säkerhet
- Windows 10 Enterprise E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender för Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)

Mer information finns i [Tjänstplaner för Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Har du inte licens ännu? [Prova eller köp en Microsoft 365-prenumeration](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Kontrollera dina befintliga licenser
Gå till administrationscentret för Microsoft 365[(admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser. Gå till Faktureringslicenser i  >  **administrationscentret.**

>[!NOTE]
> Du måste ha tilldelats rollen **Faktureringsadministratör** **eller Global** läsare i [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation. Kontakta en global administratör om du stöter på åtkomstproblem.

## <a name="required-permissions"></a>Behörighet som krävs
Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender. Listan över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomst till data är reglerade finns i hantera åtkomst till [Microsoft 365 Defender.](m365d-permissions.md)

## <a name="browser-requirements"></a>Webbläsarkrav
Access Microsoft 365 Defender i Microsoft 365 säkerhetscenter med hjälp av Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Tillgänglighet till us GCC, GCC High och andra amerikanska statliga myndigheter
Microsoft 365 Defender är för *närvarande inte* tillgänglig för:
- US Government Community Cloud (GCC)
- US Government Community Cloud High (GCC High)
- US Department of Defense
- Alla amerikanska statliga myndigheter med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsoft 365 Defender](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md)
- [Hantera åtkomst och behörigheter](m365d-permissions.md)
