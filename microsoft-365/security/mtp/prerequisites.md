---
title: Förutsättningar för Microsoft Threat Protection
description: Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft Threat Protection
keywords: krav, krav, hårdvara, mjukvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844912"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Förutsättningar för Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

Lär dig mer om licensiering och andra krav för etablering och användning av [Microsoft Threat Protection](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Licenskrav
Alla dessa licenser ger dig tillgång till Microsoft Threat Protection-funktioner i Microsoft 365-säkerhetscenter utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5-säkerhet eller A5-säkerhet
- Windows 10 Enterprise E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender Avancerat skydd
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security
- Avancerat skydd mot Office 365 (plan 2)

> [!NOTE]
> Utvärderingslicenser för Office 365 ger för närvarande inte åtkomst till Microsoft Threat Protection.

Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Har du inte licens än? [Prova eller köp en Microsoft 365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Kontrollera dina befintliga licenser
Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser. Gå till **Billing**  >  **Faktureringslicenser i administrationscentret**.

>[!NOTE]
> Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation. Om du stöter på åtkomstproblem kontaktar du en global administratör.

## <a name="required-permissions"></a>Nödvändiga behörigheter
Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection. En lista över roller som krävs för att använda Microsoft Threat Protection och information om hur åtkomst till data regleras läser du om [hur du hanterar åtkomsten till Microsoft Threat Protection](mtp-permissions.md).

## <a name="browser-requirements"></a>Krav på webbläsare
Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Tillgänglighet till amerikanska GCC, GCC High och andra amerikanska statliga institutioner
Microsoft Threat Protection är för närvarande *inte* tillgängligt för:
- Moln för amerikanska myndigheter (GCC)
- Usa:s myndighets molnhög (GCC-hög)
- Usa:s försvarsdepartement
- Alla amerikanska statliga institutioner med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
- [Hantera åtkomst och behörigheter](mtp-permissions.md)
