---
title: Vanliga frågor och svar när du Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, initiala inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: vanliga frågor och svar, vanliga frågor och svar, GCC, komma igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285991"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Vanliga frågor och svar när du Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs svaren på de vanligaste frågorna om hur du [Microsoft 365 Defender](microsoft-365-defender.md), inklusive obligatoriska licenser och behörigheter, distribuera supporttjänster och initiala inställningar.

Anvisningar om hur du aktiverar tjänsten finns [i Aktivera Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Jag har ingen licens Microsoft 365 E5 licens. Kan jag ändå använda Microsoft 365 Defender?

Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:

- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)

En fullständig lista över licenser som stöds [finns i licenskraven.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?

Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365 säkerhetstjänster som du redan har distribuerat. När du aktiverar den börjar incident-, automatiserings- och licenshanteringen fungera inom omfattningen för de distribuerade produkterna. Om ingen av dessa produkter har distribuerats korrekt Microsoft 365 Defender inga data och kan inte vidta någon åtgärd.

Vi rekommenderar att Microsoft 365 Defender alla säkerhetsprodukter  och tjänster som stöds [för Microsoft 365 Microsoft 365 Defender du optimerar upplevelsen.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Var bearbetas Microsoft 365 Defender lagra mina data?

Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras. Om du har Microsoft Defender för slutpunkt markeras samma plats som används av Defender för Slutpunkt.

>[!NOTE]
>Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender tillhandahålla automatiskt i samma datacenter i EU för kunder som har etablerat Microsoft Defender för Endpoint på det här sättet.

Platsen för datacentret visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (**Inställningar > Microsoft 365 Defender**). Om du föredrar att använda en annan datacenterplats väljer du Behöver du **hjälp?** på Microsoft 365 för att kontakta Microsofts support.

## <a name="where-can-i-access-microsoft-365-defender"></a>Var kan jag komma åt Microsoft 365 Defender?

Microsoft 365 Defender är tillgänglig i Microsoft 365 säkerhetscenter. Gå till säkerhetscentret genom att bläddra till URL:en <https://security.microsoft.com> .

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att komma Microsoft 365 Defender i Microsoft 365 säkerhetscenter?

Konton som tilldelats följande Azure Active Directory (Azure AD)-roller kan komma Microsoft 365 Defender funktioner och data:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

> [!NOTE]
> Rollbaserade inställningar för åtkomstkontroll i Microsoft Defender för Slutpunkt påverkar åtkomsten till data. Mer information finns i hantera [åtkomst till Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Vilken tidszon används Microsoft 365 Defender standard?

Som standard Microsoft 365 Defender tidsinformation i UTC-tidszonen. Du kan ändra den här inställningen om du vill använda din lokala tidszon. [Läs mer om hur du ställer in tidszon](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hur kan jag läsa mer om Microsoft 365 Defender funktioner och uppdateringar av användargränssnittet?

Microsoft tillhandahåller regelbundet information genom de olika kanalerna, inklusive:

- [Meddelandecentret](../../admin/manage/message-center.md) i Administrationscenter för Microsoft 365
- Blogginlägg i den tekniska [Microsoft 365 för & säkerhet och efterlevnad](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste offentligt tillgängliga funktionerna genom att aktivera [förhandsgranskningsfunktioner.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft 365 Defender tillgängligt för amerikanska Government Community Cloud (GCC) eller GCC Hög?

För tillfället är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft 365 Defender översikt](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md).
- [Licenskrav och andra krav](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)
