---
title: Vanliga frågor och svar när du slår på Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, initiala inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: Vanliga frågor och svar, vanliga frågor och svar, GCC, kom igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933439"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Vanliga frågor och svar när du slår på Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs svaren på de vanligaste frågorna om att aktivera [Microsoft 365 Defender](microsoft-365-defender.md), inklusive obligatoriska licenser och behörigheter, distribuera supporttjänster och initiala inställningar.

Anvisningar om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Jag har ingen Microsoft 365 E5-licens. Kan jag ändå använda Microsoft 365 Defender?

Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:

- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)
 
En fullständig lista över licenser som stöds [finns i licenskraven.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?

Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat. När du aktiverar den börjar incident-, automatiserings- och licenshanteringen fungera inom omfattningen för de distribuerade produkterna. Om ingen av dessa produkter har distribuerats korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.

Om du vill optimera dina Microsoft 365 Defender-upplevelser rekommenderar vi att du distribuerar alla säkerhetsprodukter och tjänster som [stöds av Microsoft 365.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Var bearbetas och lagras mina data i Microsoft 365 Defender?
Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras. Om du har Microsoft Defender för slutpunkt markeras samma plats som används av Defender för Slutpunkt.

>[!NOTE]
>Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma datacenter i EU för kunder som har etablerat Microsoft Defender för Endpoint på det här sättet. 

Platsen för datacenter visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (inställningar **> Microsoft 365 Defender).** Om du föredrar att använda en annan datacenterplats väljer du Behöver du **hjälp?** i säkerhetscentret i Microsoft 365 för att kontakta Microsofts support.

## <a name="where-can-i-access-microsoft-365-defender"></a>Var kan jag komma åt Microsoft 365 Defender?

Microsoft 365 Defender är tillgängligt i Microsoft 365 säkerhetscenter. Gå till säkerhetscentret genom att bläddra till URL:en [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att få tillgång till Microsoft 365 Defender i Microsoft 365 Säkerhetscenter?

Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt funktioner och data i Microsoft 365 Defender:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

>[!NOTE]
>Rollbaserade inställningar för åtkomstkontroll i Microsoft Defender för Slutpunkt påverkar åtkomsten till data. Mer information finns i hantera [åtkomst till Microsoft 365 Defender.](m365d-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Vilken tidszon används som standard i Microsoft 365 Defender?
Som standard visas tidsinformation i UTC-tidszonen i Microsoft 365 Defender. Du kan ändra den här inställningen om du vill använda din lokala tidszon. [Läs mer om hur du ställer in tidszon](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hur får jag veta mer om nya funktioner och uppdateringar av användargränssnittet i Microsoft 365 Defender?

Microsoft tillhandahåller regelbundet information genom de olika kanalerna, inklusive:

- Meddelandecenter [i](../../admin/manage/message-center.md) administrationscentret för Microsoft 365
- Blogginlägg i den tekniska [communityn för Säkerhet & Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste offentligt tillgängliga funktionerna genom att aktivera [förhandsgranskningsfunktioner.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft 365 Defender tillgänglig för amerikanska Government Community Cloud (GCC) eller GCC High?
För tillfället är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft 365 Defender](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md).
- [Licenskrav och andra krav](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)
