---
title: Vanliga frågor och svar när du aktiverar Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920496"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Vanliga frågor och svar när du aktiverar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs svar på de vanligaste frågorna om att aktivera [Microsoft 365 Defender](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribuera Support tjänster och Start Inställningar.

Instruktioner om hur du aktiverar tjänsten finns [i Aktivera Microsoft 365 Defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Jag har ingen Microsoft 365 E5-licens. Kan jag fortfarande använda Microsoft 365 Defender?

Kunder med följande icke-E5 licenser kan använda Microsoft 365 Defender:

- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)
 
En fullständig lista över licenser som stöds finns i [licensierings kraven](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Behöver jag installera eller distribuera något för att komma igång med Microsoft 365 Defender?

Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat. När du har aktiverat det kommer incident-, automatiserings-och jakt upplevelser att fungera inom omfattningen för de distribuerade produkterna. Om ingen av de här produkterna distribueras korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.

För att optimera din Microsoft 365 Defender-upplevelse rekommenderar vi att du distribuerar *alla* [Microsoft 365-säkerhetsprodukter och-tjänster](deploy-supported-services.md)som stöds.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Var är Microsoft 365 Defender och lagrar mina data?
Microsoft 365 Defender väljer automatiskt en optimal plats för data centret där konsoliderade data behandlas och lagras. Om du har Microsoft Defender för slut punkt väljer den platsen som används av Defender för slut punkten.

>[!NOTE]
>Microsoft Defender för slut punkt tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Defender. Microsoft 365 Defender tillhandahåller automatiskt samma EU-datacentertjänster för kunder som har etablerat Microsoft Defender för slut punkter på det här sättet. 

Data Center platsen visas innan och efter det att tjänsten har etablerats på inställnings sidan för Microsoft 365 Defender ( **inställningar > Microsoft 365 Defender** ). Om du föredrar att använda en annan data Center plats väljer du **behöver hjälp?** i Microsoft 365 säkerhets Center för att kontakta Microsofts support.

## <a name="where-can-i-access-microsoft-365-defender"></a>Var kan jag komma åt Microsoft 365 Defender?

Microsoft 365 Defender finns i Microsoft 365 säkerhets Center. Gå till säkerhets Center genom att bläddra till webb adressen [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att få åtkomst till Microsoft 365 Defender i Microsoft 365 säkerhets Center?

Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt Microsoft 365 Defender-funktioner och-data:

- Global administratör
- Säkerhetsadministratör
- Säkerhets ansvarig
- Global läsare
- Säkerhets läsare

>[!NOTE]
>Rollbaserad åtkomst kontroll inställningar i Microsoft Defender för slut punkten påverkar åtkomsten till data. Mer information finns i [Hantera åtkomst till Microsoft 365 Defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Vilken tidszon är Microsoft 365 Defender standard?
Som standard visar Microsoft 365 Defender tidsinformation i UTC-tidszonen. Du kan ändra den här inställningen för att använda din lokala tidszon. [Lär dig hur du ställer in tids zonen](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hur kan jag lära dig mer om nya funktioner och UI-uppdateringar för Microsoft 365 Defender?

Microsoft ger regelbundet information via de olika kanalerna, bland annat:

- [Meddelande Center](../../admin/manage/message-center.md) i administrations Center för Microsoft 365
- Blogposts i [microsofts 365 säkerhets &-kompatibilitet teknisk community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhands gransknings funktionerna](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft 365 Defender tillgängligt för AMERIKANSKt community-moln (GCC) eller GCC High?
För tillfället är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender](mtp-enable.md).
- [Licens krav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)
