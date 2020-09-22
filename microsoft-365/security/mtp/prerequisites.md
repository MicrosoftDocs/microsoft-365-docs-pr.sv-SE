---
title: Förutsättningar för Microsoft Threat Protection
description: Läs mer om licensierings-, maskinvaru-och program varu krav och andra konfigurations inställningar för Microsoft Threat Protection
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
ms.openlocfilehash: 50ca606a6bef9cec528b6b0ef78142f050e37c51
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195497"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Förutsättningar för Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

Läs mer om licensiering och andra krav för etablering och användning av [Microsoft Threat Protection](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Licens krav
Dessa licenser ger dig till gång till Microsoft Threat Protection-funktioner i Microsoft 365 Security Center utan extra kostnad:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5 säkerhets-eller A5-säkerhet
- Windows 10 Enterprise, E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender Avancerat skydd
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security
- Office 365 Avancerat skydd (abonnemang 2)

> [!NOTE]
> Utvärderings licenser för Office 365 ger för närvarande inte till gång till skydd mot Microsoft-hotet.

Mer information finns [i Microsoft 365 Enterprise Service-abonnemangen](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Har du ingen licens än? [Prova eller köp en Microsoft 365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Kontrol lera befintliga licenser
Gå till administrations Center för Microsoft[admin.microsoft.com](https://admin.microsoft.com/)365 för att se dina befintliga licenser. Gå till **fakturerings**licenser i administrations centret  >  **Licenses**.

>[!NOTE]
> Du måste tilldelas antingen rollen **fakturerings administratör** eller **global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licens informationen. Om du stöter på problem kan du kontakta en global administratör.

## <a name="required-permissions"></a>Nödvändiga behörigheter
Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera skydd mot Microsoft Threat. En lista över de roller som krävs för att använda skydd mot Microsoft Threat och information om hur åtkomst till data regleras finns i [Hantera åtkomst till Microsoft Threat Protection](mtp-permissions.md).

## <a name="browser-requirements"></a>Webb läsar krav
Få åtkomst till Microsoft Threat Protection i Microsoft 365 Security Center med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Till gång till GCC, GCC hög och andra statliga institutioner i USA
För närvarande går det *inte* att:
- Förenta staternas moln för samhälls SNMP (GCC)
- Förenta staternas offentliga gemenskaps moln (GCC hög)
- USA-försvar
- Alla amerikanska statliga institutioner med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Microsoft Threat Protection-översikt](microsoft-threat-protection.md)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
- [Hantera åtkomst och behörigheter](mtp-permissions.md)
