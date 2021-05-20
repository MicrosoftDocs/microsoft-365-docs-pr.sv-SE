---
title: Vanliga frågor och svar när du slår Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, initiala inställningar och andra produkter och tjänster som är relaterade till att aktivera Microsoft 365 Defender
keywords: Vanliga frågor, vanliga frågor, GCC, komma igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, obligatorisk behörighet, licensbehörighet, inställningssida
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572771"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Vanliga frågor och svar när du slår Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs svar på de vanligaste frågorna om hur du [slår på Microsoft 365 Defender](microsoft-365-defender.md), inklusive nödvändiga licenser och behörigheter, distribution av supporttjänster och inledande inställningar.

Instruktioner om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Jag har inget Microsoft 365 E5 körkort. Kan jag fortfarande använda Microsoft 365 Defender?

Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:

- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Försvarare för Office 365 (Plan 2)
 
En fullständig lista över licenser som stöds [finns i licenskraven](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?

Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365 som du redan har distribuerat. När du har aktiverat den kommer incident-, automatiserings- och jaktupplevelser att börja fungera inom ramen för de distribuerade produkterna. Om ingen av dessa produkter distribueras korrekt Microsoft 365 Defender inga data och kan inte vidta några åtgärder.

För att optimera Microsoft 365 Defender-upplevelser rekommenderar vi att du *distribuerar alla* [Microsoft 365 som stöds av säkerhetsprodukter och säkerhetstjänster](deploy-supported-services.md).

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Var bearbetar Microsoft 365 Defender och lagrar mina data?
Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras. Om du har Microsoft Defender för slutpunkt väljer den samma plats som Används av Defender för Slutpunkt.

>[!NOTE]
>Microsoft Defender for Endpoint-bestämmelser i EU-datacenter (EU) när de aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma EU-datacenter för kunder som har etablerat Microsoft Defender för Slutpunkt på detta sätt. 

Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (**Inställningar > Microsoft 365 Defender**). Om du föredrar att använda en annan datacenterplats väljer du Behöver **du hjälp i** Microsoft 365 säkerhetscenter för att kontakta Microsoft-supporten.

## <a name="where-can-i-access-microsoft-365-defender"></a>Var kommer jag åt Microsoft 365 Defender?

Microsoft 365 Defender finns i Microsoft 365 säkerhetscenter. Om du vill gå till säkerhetscentret bläddrar du till URL:en [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att komma Microsoft 365 Defender Microsoft 365 säkerhetscenter?

Konton som tilldelats följande Azure Active Directory (Azure AD) kan komma åt Microsoft 365 Defender-funktioner och -data:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

>[!NOTE]
>Rollbaserade åtkomstkontrollinställningar i Microsoft Defender för slutpunkt påverkar åtkomsten till data. Mer information finns i om hur [du hanterar åtkomst Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Vilken tidszon Microsoft 365 Defender som standard?
Som standard visar Microsoft 365 Defender tidsinformation i UTC-tidszonen. Du kan ändra den här inställningen så att den använder din lokala tidszon. [Lär dig mer om hur du ställer in tidszonen](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hur kan jag lära mig mer om Microsoft 365 Defender-funktionen och uppdateringar av användargränssnittet?

Microsoft tillhandahåller regelbundet information via de olika kanalerna, inklusive:

- Meddelandecentret [i](../../admin/manage/message-center.md) Microsoft 365 administrationscenter
- Blogginlägg i Microsoft 365 [säkerhets& teknikgemenskap för regelefterlevnad](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste offentligt tillgängliga upplevelserna genom att aktivera [förhandsgranskningsfunktioner](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft 365 Defender tillgängligt för US Government Community Cloud (GCC) eller GCC High?
För närvarande är det inte tillgängligt.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft 365 Översikt över Defender](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md).
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)
