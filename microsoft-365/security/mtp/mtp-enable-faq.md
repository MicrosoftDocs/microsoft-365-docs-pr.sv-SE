---
title: Vanliga frågor och svar när du aktiverar skydd mot Microsoft Threat
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft Threat Protection
keywords: Vanliga frågor, FAQ, GCC, kom igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, data plats, nödvändiga behörigheter, licens kvalificering, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198845"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Vanliga frågor och svar när du aktiverar skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

Läs svar på de vanligaste frågorna om att aktivera skydd mot [Microsoft Threat](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribuera Support tjänster och Start Inställningar.

Instruktioner om hur du aktiverar tjänsten finns i [Aktivera skydd mot Microsoft hot](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Jag har ingen Microsoft 365 E5-licens. Kan jag fortfarande använda skydd mot Microsoft Threat?

Kunder med följande icke-E5 licenser kan använda Microsoft Threat Protection:

- Microsoft Defender Avancerat skydd
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Office 365 Avancerat skydd (abonnemang 2)
 
En fullständig lista över licenser som stöds finns i [licensierings kraven](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Behöver jag installera eller distribuera något för att komma igång med Microsoft Threat Protection?

Nej, Microsoft Threat Protection konsoliderar data från säkerhets tjänsterna för Microsoft 365 som du redan har distribuerat. När du har aktiverat det kommer incident-, automatiserings-och jakt upplevelser att fungera inom omfattningen för de distribuerade produkterna. Om ingen av de här produkterna distribueras korrekt visas inga data och det går inte att vidta någon åtgärd.

För att optimera skyddet mot Microsoft Threat Protection rekommenderar vi att du distribuerar *alla* [Microsoft 365-säkerhetsprodukter och-tjänster](deploy-supported-services.md)som stöds.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Var finns Microsoft Threat Protection och lagrar mina data?
Microsoft Threat Protection väljer automatiskt en optimal plats för data centret där konsoliderade data behandlas och lagras. Om du har Microsoft Defender ATP väljer den den plats som används av Microsoft Defender ATP.

>[!NOTE]
>Microsoft Defender ATP tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Security Center. Microsoft Threat Protection tillhandahåller automatiskt samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet. 

Data Center platsen visas innan och efter det att tjänsten har etablerats på inställnings sidan för Microsoft Threat Protection (**inställningar > skydd mot Microsoft hotet**). Om du föredrar att använda en annan data Center plats väljer du **behöver hjälp?** i Microsoft 365 säkerhets Center för att kontakta Microsofts support.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Var kan jag få åtkomst till Microsoft Threat Protection?

Microsoft Threat Protection är tillgängligt i säkerhets Center för Microsoft 365. Gå till säkerhets Center genom att bläddra till webb adressen [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att få åtkomst till Microsoft Threat Protection i Microsoft 365 säkerhets Center?

Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt funktioner och data för Microsoft Threat Protection:

- Global administratör
- Säkerhetsadministratör
- Säkerhets ansvarig
- Global läsare
- Säkerhets läsare

>[!NOTE]
>Rollbaserad åtkomst kontroll inställningar i Microsoft Defender ATP påverkar till gång till data. Mer information finns i om [att hantera åtkomst till Microsoft Threat Protection](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Vilken tidszon används som standard i tids zonen?
Som standard visas tidsinformation i tids zonen för UTC. Du kan ändra den här inställningen för att använda din lokala tidszon. [Lär dig hur du ställer in tids zonen](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Hur kan jag lära dig mer om nya funktioner I Microsoft Threat Protection och UI-uppdateringar?

Microsoft ger regelbundet information via de olika kanalerna, bland annat:

- [Meddelande Center](../../admin/manage/message-center.md) i administrations Center för Microsoft 365
- Blogposts i [microsofts 365 säkerhets &-kompatibilitet teknisk community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhands gransknings funktionerna](preview.md).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Finns Microsoft Threat Protection för AMERIKANSKt community-moln (GCC) eller GCC High?
För tillfället är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Threat Protection-översikt](microsoft-threat-protection.md)
- [Aktivera skydd mot Microsoft Threat](mtp-enable.md).
- [Licens krav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhands gransknings funktioner](preview.md)
