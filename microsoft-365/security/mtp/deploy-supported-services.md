---
title: Distribuera tjänster som stöds av Microsoft Threat Protection
description: Lär dig mer om Microsofts säkerhetstjänster som kan integreras av Microsoft Threat Protection, deras licenskrav och distributionsprocedurer
keywords: distribuera, licenser, tjänster som stöds, etablering, konfiguration Microsoft Threat Protection, M365, licensberättigande, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, avancerat hotskydd, E5, A5, EMS
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
ms.openlocfilehash: 1441790bfa0c587c4abceb87eb1e4daae6e4d157
ms.sourcegitcommit: 09c3e2f3129c5e43cd8420cccd0676ff3a29a355
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521486"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integrerar olika Microsoft-säkerhetstjänster för att tillhandahålla centraliserade funktioner för identifiering, förebyggande och undersökning mot avancerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licenskrav, fördelar och begränsningar som är förknippade med distribution av en eller flera tjänster och länkar till hur du kan distribuera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger åtkomst till följande tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscentret. [Se licenskrav](prerequisites.md#licensing-requirements)

| Service som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender ATP | Slutpunktsskyddssvit byggd kring kraftfulla beteendesensorer, molnanalys och hotinformation |
| Office 365 ATP | Avancerat skydd för dina appar och data i Office 365, inklusive e-post och andra samarbetsverktyg |
| Azure ATP | Försvara dig mot avancerade hot, komprometterade identiteter och skadliga insiders med korrelerade Active Directory-signaler |
| Microsoft Cloud App Security | Identifiera och bekämpa cyberhot i dina Microsoft- och tredjepartsmolntjänster |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft Threat Protection ger bättre synlighet, korrelation och reparation när du distribuerar fler tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med full driftsättning
För att få de fullständiga fördelarna med Microsoft Threat Protection rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras baserat på varningar och händelsesignaler från alla tillgängliga sensorer och tjänstespecifika analysfunktioner
- Automatiska spelböcker för undersökning och reparation (AIR) gäller för olika entitetstyper, inklusive enheter, postlådor och användarkonton
- Ett mer omfattande avancerat jaktschema kan efterfrågas för händelse- och entitetsdata från enheter, postlådor och andra entiteter

### <a name="limited-deployment-scenarios"></a>Scenarier för begränsad distribution
Varje tjänst som stöds som du distribuerar ger en extremt rik uppsättning råsignaler samt korrelerad information. Begränsad distribution leder inte till att Microsoft Threat Protection-funktionen stängs av, men dess förmåga att ge omfattande synlighet över slutpunkter, appar, data och identiteter påverkas. Samtidigt gäller alla reparationsfunktioner endast för entiteter som kan hanteras av de tjänster som du har distribuerat.

I tabellen nedan visas hur varje tjänst som stöds tillhandahåller ytterligare data, möjligheter att få ytterligare insikt genom att korrelera data och bättre reparations- och svarsfunktioner.

| Tjänst | Data (signaler & korrelerad information) | Åtgärd & svarsomfång |
| ------ | ------ | ------ |
| Microsoft Defender ATP | - Slutpunktstillstånd och råa händelser<br />- Identifiering och varningar för slutpunkter, inklusive antivirus, EDR, minskning av angreppsytan<br />- Information om filer och andra enheter som observerats på slutpunkter | Slutpunkter |
| Office 365 ATP | - Post- och brevlåda och råa händelser<br />- E-post, bifogad fil och länk upptäckter | - Brevlådor<br />- Office 365-konton |
| Azure ATP | - Active Directory-signaler, inklusive autentiseringshändelser<br />- Identitetsrelaterade beteendeidentifieringar | Identiteter |
| Microsoft Cloud App Security | - Identifiering av osanktionerade molnappar och molntjänster (skugg-IT)<br />- Exponering av data till molnappar<br />- Hotaktivitet som är associerad med molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Distribuera varje tjänst kräver vanligtvis etablering till din klient organisation och någon inledande konfiguration. Se följande tabell för att förstå hur var och en av dessa tjänster distribueras.

| Tjänst | Etableringsinstruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Distributionsguide för Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Se etableringsinstruktioner* |
| Office 365 ATP | *Ingen, etablerad med Office 365* | [Konfigurera ATP-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snabbstart: Skapa din Azure ATP-instans](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Se etableringsinstruktioner* |
| Microsoft Cloud App Security | *Ingen* | [Snabbstart: Kom igång med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat de tjänster som stöds [aktiverar du Microsoft Threat Protection](mtp-enable.md).

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsofts hotskydd](microsoft-threat-protection.md)
- [Aktivera Microsoft Threat Protection](mtp-enable.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Office 365 ATP](../office-365-security/office-365-atp.md)
- [Översikt över Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
