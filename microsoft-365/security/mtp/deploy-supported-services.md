---
title: Distribuera tjänster som stöds av Microsoft Threat Protection
description: Lär dig mer om Microsofts säkerhetstjänster som kan integreras av Microsoft Threat Protection, deras licenskrav och distributionsprocedurer
keywords: distribuera, licenser, tjänster som stöds, etablera, konfiguration Microsoft Threat Protection, M365, licensbehörighet, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, avancerat hotskydd, E5, A5, EMS
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
ms.openlocfilehash: c2798238f0e3cb10edab7f98bf096474a80fa006
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857481"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

**Gäller:**
- Skydd av Hot mot Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integrerar olika Microsoft-säkerhetstjänster för att tillhandahålla centraliserad identifiering, förebyggande och utredningsfunktioner mot sofistikerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licenskrav, fördelarna och begränsningarna i samband med distribution av en eller flera tjänster och länkar till hur du kan distribuera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Licens för Microsoft 365 E5, E5 Security, A5 eller A5 Security eller en giltig kombination av licenser ger åtkomst till följande tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365 security center. [Se licenskrav](prerequisites.md#licensing-requirements)

| Tjänst som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender ATP | Slutpunktsskyddssvit byggd kring kraftfulla beteendesensorer, molnanalys och hotinformation |
| Office 365 ATP | Avancerat skydd för dina appar och data i Office 365, inklusive e-post och andra samarbetsverktyg |
| Azure ATP | Skydda mot avancerade hot, komprometterade identiteter och skadliga insiders med hjälp av korrelerade Active Directory-signaler |
| Säkerhet för Microsoft Cloud-appar | Identifierar och bekämpar cyberhot i microsoft och molntjänster från tredje part |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft Threat Protection ger bättre synlighet, korrelation och reparation när du distribuerar tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med fullständig distribution
För att få fullständiga fördelar med Microsoft Threat Protection rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras baserat på varningar och händelsesignaler från alla tillgängliga sensorer och servicespecifika analysfunktioner
- Automatiska tv-spelböcker (Investigation and remediation) gäller för olika entitetstyper, inklusive enheter, postlådor och användarkonton
- Ett mer omfattande avancerat jaktschema kan efterfrågas för händelse- och entitetsdata från enheter, postlådor och andra entiteter

### <a name="limited-deployment-scenarios"></a>Begränsade distributionsscenarier
Varje tjänst som stöds som du distribuerar ger en extremt omfattande uppsättning råa signaler samt korrelerad information. Begränsad distribution gör det inte att Microsoftthreat Protection-funktionen inaktiverar, men dess möjlighet att ge omfattande synlighet över dina slutpunkter, appar, data och identiteter påverkas. Samtidigt gäller alla reparationsfunktioner endast för entiteter som kan hanteras av de tjänster som du har distribuerat.

I tabellen nedan visas hur varje tjänst som stöds tillhandahåller ytterligare data, möjligheter att få ytterligare insikt genom att korrelera data och bättre reparations- och svarsfunktioner.

| Tjänst | Data (signaler & korrelerad information) | Reparation & svarsomfattning |
| ------ | ------ | ------ |
| Microsoft Defender ATP | - Slutpunktstillstånd och råa händelser<br />- Slutpunktsidentifieringar och slutvarningar, inklusive antivirus, EDR, attackytreducering<br />- Information om filer och andra enheter som observerats på slutpunkter | Slutpunkter |
| Office 365 ATP | - Post- och brevlåda tillstånd och råa händelser<br />- E-post, bifogad fil och länk identifiering | - Brevlådor<br />- Office 365-konton |
| Azure ATP | - Active Directory-signaler, inklusive autentiseringshändelser<br />- Identitetsrelaterade beteendeidentifieringar | Identiteter |
| Säkerhet för Microsoft Cloud-appar | - Identifiering av osanktionerade molnappar & tjänster (skugg-IT)<br />- Exponering av data till molnappar<br />- Hotaktivitet associerade molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Distribuera varje tjänst kräver vanligtvis etablering till din klient och några inledande konfiguration. Se följande tabell för att förstå hur var och en av dessa tjänster distribueras.

| Tjänst | Etableringsinstruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Distributionsguide för Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Se etableringsinstruktioner* |
| Office 365 ATP | *Ingen, etablerad med Office 365* | [Konfigurera ATP-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snabbstart: Skapa din Azure ATP-instans](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Se etableringsinstruktioner* |
| Säkerhet för Microsoft Cloud-appar | *Ingen* | [Snabbstart: Komma igång med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat tjänsterna som stöds [aktiverar du Microsoft Threat Protection](mtp-enable.md).

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivera Microsoft Threat Protection](mtp-enable.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Office 365 ATP](../office-365-security/office-365-atp.md)
- [Översikt över Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP-översikt](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
