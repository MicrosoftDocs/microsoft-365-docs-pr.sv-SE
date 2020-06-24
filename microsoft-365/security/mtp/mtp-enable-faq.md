---
title: Vanliga frågor och svar när du aktiverar Microsoft Threat Protection
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft Threat Protection
keywords: vanliga frågor, vanliga frågor, GCC, komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssida
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845088"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Vanliga frågor och svar när du aktiverar Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

Läs svar på de vanligaste frågorna om hur du aktiverar [Microsoft Threat Protection](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribution av supporttjänster och inledande inställningar.

Instruktioner om hur du aktiverar tjänsten [finns i Aktivera Microsoft Threat Protection](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Jag har ingen Microsoft 365 E5-licens. Kan jag fortfarande använda Microsoft Threat Protection?

Kunder med följande licenser som inte är E5 kan använda Microsoft Threat Protection:

- Microsoft Defender Avancerat skydd
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Avancerat skydd mot Office 365 (plan 2)
 
En fullständig lista över licenser som stöds [finns i licenskraven](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Måste jag installera eller distribuera något för att börja använda Microsoft Threat Protection?

Nej, Microsoft Threat Protection konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat. När du slår på den kommer incident-, automatiserings- och jaktupplevelser att börja arbeta inom ramen för de distribuerade produkterna. Om ingen av dessa produkter har distribuerats korrekt visas inga data i Microsofts hotskydd och kan inte vidta några åtgärder.

För att optimera dina Microsoft Threat Protection-upplevelser rekommenderar vi att du distribuerar *alla* [microsoft 365-säkerhetsprodukter och -tjänster som](deploy-supported-services.md)stöds .

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Var bearbetar och lagrar Microsoft Threat Protection mina data?
Microsoft Threat Protection väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras. Om du har Microsoft Defender ATP väljer den samma plats som används av Microsoft Defender ATP.

>[!NOTE]
>Microsoft Defender ATP etablerar automatiskt bestämmelser i EU-datacenter när de aktiveras via Azure Security Center. Microsoft Threat Protection etableras automatiskt i samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet. 

Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft Threat Protection (**Inställningar > Microsoft Threat Protection**). Om du föredrar att använda en annan datacenterplats väljer du **Behöver du hjälp?**

## <a name="where-can-i-access-microsoft-threat-protection"></a>Var kan jag komma åt Microsoft Threat Protection?

Microsoft Threat Protection finns i Microsoft 365 security center. Om du vill gå till säkerhetscentret bläddrar du till webbadressen [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Vilka behörigheter behöver jag för att komma åt Microsoft Threat Protection i Microsoft 365-säkerhetscenter?

Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt Microsoft Threat Protection-funktioner och data:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

>[!NOTE]
>Rollbaserade åtkomstkontrollinställningar i Microsoft Defender ATP påverkar åtkomsten till data. Mer information finns i om [hur du hanterar åtkomst till Microsoft Threat Protection](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Vilken tidszon standard för Microsoft Threat Protection?
Som standard visar Microsoft Threat Protection tidsinformation i UTC-tidszonen. Du kan ändra den här inställningen om du vill använda den lokala tidszonen. [Läs mer om hur du ställer in tidszonen](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Hur lär jag mig mer om nya Microsoft Threat Protection-funktioner och uppdateringar av användargränssnittet?

Microsoft tillhandahåller regelbundet information via de olika kanalerna, inklusive:

- [Administrationscentret](../../admin/manage/message-center.md) för Meddelanden i Microsoft 365
- Blogginlägg i [Microsoft 365-säkerhets- & teknikcommunity för efterlevnad](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhandsgranskningsfunktioner](preview.md).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft Threat Protection tillgängligt för GCC (US Government Community Cloud) eller GCC High?
För närvarande är den inte tillgänglig.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivera Microsoft Threat Protection](mtp-enable.md).
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Aktivera förhandsgranskningsfunktioner](preview.md)