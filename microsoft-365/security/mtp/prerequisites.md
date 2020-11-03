---
title: Microsoft 365 Defender-förutsättningar
description: Läs mer om licensiering, maskinvaru-och program varu krav och andra konfigurations inställningar för Microsoft 365 Defender
keywords: krav, förutsättningar, maskin vara, program vara, webbläsare, MTP, M365, licens, E5, A5, EMS, Köp
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844782"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender-förutsättningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs mer om licensiering och andra krav för etablering och användning av [Microsoft 365 Defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Licens krav
Dessa licenser ger dig till gång till Microsoft 365 Defender-funktioner i Microsoft 365 säkerhets Center utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5 säkerhets-eller A5-säkerhet
- Windows 10 Enterprise, E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender för slut punkt
- Microsoft Defender för identitet 
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)

> [!NOTE]
> Utvärderings licenser för Office 365 ger för närvarande inte till gång till Microsoft 365 Defender.

Mer information finns [i Microsoft 365 Enterprise Service-abonnemangen](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Har du ingen licens än? [Prova eller köp en Microsoft 365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Kontrol lera befintliga licenser
Gå till administrations Center för Microsoft[admin.microsoft.com](https://admin.microsoft.com/)365 för att se dina befintliga licenser. Gå till **fakturerings** licenser i administrations centret  >  **Licenses**.

>[!NOTE]
> Du måste tilldelas antingen rollen **fakturerings administratör** eller **global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licens informationen. Om du stöter på problem kan du kontakta en global administratör.

## <a name="required-permissions"></a>Nödvändiga behörigheter
Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera Microsoft 365 Defender. En lista över de roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomst till data regleras finns i [Hantera åtkomst till Microsoft 365 Defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Webb läsar krav
Gå till Microsoft 365 Defender i Microsoft 365 säkerhets Center med Microsoft Edge, Internet Explorer 11 eller någon annan HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Till gång till GCC, GCC hög och andra statliga institutioner i USA
För närvarande är Microsoft 365 Defender *inte* tillgängligt för:
- Förenta staternas moln för samhälls SNMP (GCC)
- Förenta staternas offentliga gemenskaps moln (GCC hög)
- USA-försvar
- Alla amerikanska statliga institutioner med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
- [Hantera åtkomst och behörigheter](mtp-permissions.md)
