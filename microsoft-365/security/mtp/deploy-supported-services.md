---
title: Distribuera tjänster som stöds av Microsoft 365 Defender
description: Läs mer om Microsofts säkerhetstjänster som kan integreras med Microsoft 365 Defender, deras licenskrav och distributionsprocedurer
keywords: distribuera, licenser, tjänster som stöds, etablering, konfiguration Microsoft Threat Protection, M365, licensberättigande, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, avancerat skydd mot hot, E5, A5, EMS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928968"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integrerar olika Microsoft-säkerhetstjänster för centraliserad identifiering, skydd och undersökningsfunktioner mot avancerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licenskrav, fördelarna och begränsningarna som är kopplade till distributionen av en eller flera tjänster samt länkar till hur du kan distribuera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Microsoft 365 E5-, E5-säkerhets-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger dig tillgång till följande tjänster som stöds och ger dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter. [Visa licenskrav](prerequisites.md#licensing-requirements)

| Tjänst som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender för Endpoint | Slutpunktsskyddssviten uppbyggd kring kraftfulla beteendesensorer, molnanalyser och hotinformation |
|Microsoft Defender för Office 365 | Avancerat skydd för dina appar och data i Office 365, inklusive e-post och andra samarbetsverktyg |
| Microsoft Defender for Identity | Försvara dig mot avancerade hot, komprometterade identiteter och skadliga insiders med korrelerade Active Directory-signaler |
| Microsoft Cloud App Security | Identifiera och bekämpa cyberhot i Microsofts och tredjepartsmolntjänster |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft 365 Defender ger bättre synlighet, korrelation och åtgärd när du distribuerar fler tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med fullständig distribution
För att få de fullständiga fördelarna med Microsoft 365 Defender rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras baserat på varningar och händelsesignaler från alla tillgängliga sensorer och tjänstespecifika analysfunktioner
- Spelböcker för automatisk undersökning och åtgärd (AIR) gäller för olika entitetstyper, inklusive enheter, postlådor och användarkonton
- Ett mer omfattande avancerat sökschema kan användas för händelse- och enhetsdata från enheter, postlådor och andra enheter

### <a name="limited-deployment-scenarios"></a>Begränsade distributionsscenarier
Varje tjänst som stöds som du distribuerar ger en extremt omfattande uppsättning rådata och korrelerad information. Även om begränsad distribution inte leder till att Microsoft 365 Defender-funktioner inaktiveras påverkas möjligheten att ge omfattande synlighet för slutpunkter, appar, data och identiteter. Samtidigt gäller alla åtgärdsfunktioner endast för enheter som kan hanteras av de tjänster som du har distribuerat.

I tabellen nedan visas hur varje tjänst som stöds ger ytterligare data, möjligheter att få ytterligare insyn genom att korrelera data och bättre funktioner för åtgärder och svar.

| Tjänst | Data (signaler & korrelerad information) | Åtgärdsomfång & svar |
| ------ | ------ | ------ |
| Microsoft Defender för Endpoint | - Slutpunktshändelser och rådata<br />- Identifieringar och varningar av slutpunkter, inklusive antivirus, EDR, minskning av attackytan<br />- Information om filer och andra enheter som observerats på slutpunkter | Slutpunkter |
|Microsoft Defender för Office 365 | - Delstater för e-post och postlåda samt rådata<br />- Identifiering av e-post, bifogade filer och länkar | - Postlådor<br />- Microsoft 365-konton |
| Microsoft Defender for Identity | - Active Directory-signaler, inklusive autentiseringshändelser<br />- Identitetsrelaterade identifieringar | Identiteter |
| Microsoft Cloud App Security | - Identifiering av icke-ctionerade molnappar och -tjänster (skugg-IT)<br />- Exponering av data för molnappar<br />- Hotaktivitet kopplad till molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Om du vill distribuera varje tjänst krävs det vanligtvis etablering till klientorganisationen och en inledande konfiguration. Se följande tabell för att förstå hur var och en av dessa tjänster distribueras.

| Tjänst | Etableringsinstruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender för Endpoint | [Distributionsguide för Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Se etableringsinstruktioner* |
|Microsoft Defender för Office 365 | *Ingen, etablerat med Office 365* | [Konfigurera principer för Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [Snabbstart: Skapa en Microsoft Defender för identitetsinstans](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Se etableringsinstruktioner* |
| Microsoft Cloud App Security | *Ingen* | [Snabbstart: Komma igång med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat de tjänster som stöds [aktiverar du Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
- [Översikt över Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Microsoft Defender för Office 365](../office-365-security/office-365-atp.md)
- [Översikt över säkerhet i Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
