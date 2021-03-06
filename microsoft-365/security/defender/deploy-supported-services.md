---
title: Distribuera tjänster som stöds av Microsoft 365 Defender
description: Läs mer om Microsofts säkerhetstjänster som kan integreras med Microsoft 365 Defender, deras licenskrav och distributionsprocedurer
keywords: distribuera, licenser, tjänster som stöds, etablering, konfiguration Microsoft 365 Defender, M365, licensberättigande, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App Security, MCAS, E5, A5, EMS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935683"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) integrerar olika Microsoft-säkerhetstjänster för centraliserad identifiering, skydd och undersökningsfunktioner mot avancerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licenskrav, fördelarna och begränsningarna som är kopplade till distributionen av en eller flera tjänster samt länkar till hur du kan distribuera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Microsoft 365 E5, E5-säkerhet, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger tillgång till följande tjänster som stöds och ger dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter. [Se licenskrav](prerequisites.md#licensing-requirements)

| Tjänst som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender för Endpoint | Slutpunktsskyddssvit som är uppbyggd kring kraftfulla funktionsintelligenser, molnanalyser och hotinformation |
|Microsoft Defender för Office 365 | Avancerat skydd för appar och data i Office 365, inklusive e-post och andra samarbetsverktyg |
| Microsoft Defender for Identity | Försvara sig mot avancerade hot, komprometterade identiteter och skadliga insiders med korrelerade Active Directory-signaler |
| Microsoft Cloud App Security | Identifiera och bekämpa cyberhot med Microsofts och tredjepartsmolntjänster |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft 365 Defender ger bättre synlighet, korrelation och åtgärd när du distribuerar fler tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med fullständig distribution
För att få de fullständiga fördelarna Microsoft 365 Defender rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras baserat på varningar och händelsesignaler från alla tillgängliga sensorer och tjänstespecifika analysfunktioner
- Spelböcker för automatiserad undersökning och åtgärd (AIR) gäller för olika entitetstyper, inklusive enheter, postlådor och användarkonton
- Ett mer omfattande, avancerat sökschema kan tillfrågas om händelse- och enhetsdata från enheter, postlådor och andra enheter

### <a name="limited-deployment-scenarios"></a>Scenarier för begränsad distribution
Varje tjänst som stöds som du distribuerar ger en extremt omfattande uppsättning rådata och korrelerad information. Även om begränsad distribution inte Microsoft 365 att Defender-funktionen inaktiveras påverkas dess möjlighet att ge omfattande synlighet över slutpunkter, appar, data och identiteter. Samtidigt gäller eventuella åtgärdsfunktioner bara för enheter som kan hanteras av de tjänster som du har distribuerat.

I tabellen nedan visas hur varje tjänst som stöds ger ytterligare data, möjligheter att få ytterligare insikter genom att korrelera data och bättre funktioner för åtgärder och svar.

| Tjänst | Data (signaler & korrelerad information) | Åtgärd & svarsomfång |
| ------ | ------ | ------ |
| Microsoft Defender för Endpoint | - Slutpunktsstater och rådata<br />- Identifieringar och varningar av slutpunkter, inklusive antivirusprogram, Identifiering och åtgärd på slutpunkt, minskning av attackytan<br />- Information om filer och andra enheter som observerats i slutpunkter | Slutpunkter |
|Microsoft Defender för Office 365 | - Delstater för e-post och postlåda samt obearbetade händelser<br />- Identifiering av e-post, bifogade filer och länkar | - Postlådor<br />- Microsoft 365 konton |
| Microsoft Defender for Identity | - Active Directory-signaler, inklusive autentiseringshändelser<br />- Identitetsrelaterad identifiering av beteende | Identiteter |
| Microsoft Cloud App Security | - Identifiering av olästa molnappar och -tjänster (skugg-IT)<br />- Exponering av data i molnappar<br />- Hotaktivitet kopplad till molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Distribution av varje tjänst kräver vanligtvis etablering till klientorganisationen och en del inledande konfiguration. Se följande tabell för att förstå hur var och en av dessa tjänster distribueras.

| Tjänst | Etableringsinstruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender för Endpoint | [Distributionsguide för Microsoft Defender för slutpunkt](../defender-endpoint/deployment-phases.md) | *Se etableringsinstruktioner* |
|Microsoft Defender för Office 365 | *Ingen, tillhandahålls med Office 365* | [Konfigurera principer för Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [Snabbstart: Skapa din Microsoft Defender för identitetsinstans](/azure-advanced-threat-protection/install-atp-step1) | *Se etableringsinstruktioner* |
| Microsoft Cloud App Security | *Inga* | [Snabbstart: Komma igång med Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat de tjänster som stöds [aktiverar du Microsoft 365 Defender.](m365d-enable.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft 365 Defender-översikt](microsoft-365-defender.md)
- [Aktivera Microsoft 365 Defender](m365d-enable.md)
- [Översikt över Microsoft Defender för slutpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Översikt över Microsoft Defender Office 365 Microsoft Defender](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security översikt](/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Microsoft Defender för identitet](/azure-advanced-threat-protection/what-is-atp)
