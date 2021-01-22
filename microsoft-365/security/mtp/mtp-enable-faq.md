---
title: Vanliga frågor och svar om att aktivera Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: vanliga frågor och svar, vanliga frågor och svar, GCC, komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930192"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Vanliga frågor och svar när du slår på Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Läs svaren på de vanligaste frågorna om att aktivera [Microsoft 365 Defender,](microsoft-threat-protection.md)inklusive obligatoriska licenser och behörigheter, distribution av supporttjänster och initiala inställningar.

Anvisningar om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender.](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Jag har ingen Microsoft 365 E5-licens. Kan jag ändå använda Microsoft 365 Defender?

Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:

- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender för Office 365 (abonnemang 2)
 
En fullständig lista över licenser som stöds [finns i licenskraven.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?

Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat. När du aktiverar den börjar incident- och automatiserings- och fiskeupplevelserna fungera inom de distribuerade produkterna. Om ingen av dessa produkter distribueras korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.

Om du vill optimera dina Microsoft 365 Defender-upplevelser rekommenderar vi att du distribuerar alla säkerhetsprodukter och tjänster som stöds [av Microsoft 365.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Var bearbetar och lagrar Microsoft 365 Defender mina data?
Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras. Om du har Microsoft Defender för slutpunkten markeras samma plats som används av Defender för Endpoint.

>[!NOTE]
>Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma DATACENTER i EU för kunder som har etablerat Microsoft Defender för Slutpunkt på det här sättet. 

Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (inställningar **> Microsoft 365 Defender).** Om du föredrar att använda en annan datacenterplats väljer du Behöver du **hjälp?** I säkerhetscentret i Microsoft 365 kontaktar du Microsoft Support.

## <a name="where-can-i-access-microsoft-365-defender"></a>Var får jag tillgång till Microsoft 365 Defender?

Microsoft 365 Defender är tillgängligt i Microsoft 365 säkerhetscenter. Gå till säkerhetscentret genom att bläddra till [https://security.microsoft.com](https://security.microsoft.com) URL:en.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att få åtkomst till Microsoft 365 Defender i Microsoft 365 Säkerhetscenter?

Konton som tilldelats följande Azure Active Directory-roller (AD) har åtkomst till funktioner och data i Microsoft 365 Defender:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

>[!NOTE]
>Rollbaserade inställningar för åtkomstkontroll i Microsoft Defender för Slutpunkt påverkar åtkomsten till data. Mer information finns i artikeln om hur [du hanterar åtkomst till Microsoft 365 Defender.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Vilken tidszon används som standard i Microsoft 365 Defender?
Som standard visar Microsoft 365 Defender tidsinformation i tidszonen UTC. Du kan ändra den här inställningen om du vill använda din lokala tidszon. [Läs mer om hur du ställer in tidszon](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hur får jag veta mer om de nya funktions- och gränssnittsuppdateringarna för Microsoft 365 Defender?

Microsoft tillhandahåller regelbundet information genom de olika kanalerna, inklusive:

- Meddelandecenter [i](../../admin/manage/message-center.md) administrationscentret för Microsoft 365
- Blogginlägg i Microsoft [365 Security & tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste offentligt tillgängliga funktionerna genom att aktivera [förhandsgranskningsfunktioner.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft 365 Defender tillgängligt för GCC (Government Community Cloud) eller GCC High?
För tillfället är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender.](mtp-enable.md)
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)
