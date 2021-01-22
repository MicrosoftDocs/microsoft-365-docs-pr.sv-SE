---
title: Förutsättningar för Microsoft 365 Defender
description: Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft 365 Defender
keywords: krav, förutsättningar, maskinvara, programvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930096"
---
# <a name="microsoft-365-defender-prerequisites"></a>Förutsättningar för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs mer om licensiering och andra krav för etablering och användning av [Microsoft 365 Defender.](microsoft-threat-protection.md)

## <a name="licensing-requirements"></a>Licenskrav
Alla dessa licenser ger dig tillgång till Microsoft 365 Defender-funktionerna i Microsoft 365 säkerhetscenter utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5- eller A5-säkerhet
- Windows 10 Enterprise, E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender för Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)

> [!NOTE]
> Utvärderingslicenser för Office 365 ger för närvarande inte åtkomst till Microsoft 365 Defender.

Mer information finns i [Microsoft 365 Enterprise-tjänstplaner.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Har du ingen licens ännu? [Prova eller köp en Microsoft 365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Kontrollera dina befintliga licenser
Gå till administrationscentret för Microsoft 365[(admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser. Gå till Faktureringslicenser i  >  **administrationscentret.**

>[!NOTE]
> Du måste vara antingen **faktureringsadministratör eller** **global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation. Kontakta en global administratör om du stöter på åtkomstproblem.

## <a name="required-permissions"></a>Behörighet som krävs
Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender. Läs om hantering av åtkomst till [Microsoft 365 Defender](mtp-permissions.md)för listan över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomst till data ska regleras.

## <a name="browser-requirements"></a>Webbläsarkrav
Access Microsoft 365 Defender i Microsoft 365 säkerhetscenter med hjälp av Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Tillgänglighet till US GCC, GCC High och andra amerikanska statliga myndigheter
För närvarande är Microsoft 365 Defender *inte* tillgänglig för:
- Us Government Community Cloud (GCC)
- US Government Community Cloud High (GCC High)
- USA:s försvar
- Alla amerikanska statliga institutioner med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
- [Hantera åtkomst och behörigheter](mtp-permissions.md)
