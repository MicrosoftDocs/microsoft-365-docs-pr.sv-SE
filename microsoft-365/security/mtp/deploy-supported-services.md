---
title: Distribuera tjänster som stöds av Microsoft 365 Defender
description: Läs mer om Microsofts säkerhets tjänster som kan integreras i Microsoft 365 Defender, deras licensierings krav och distributions procedurer
keywords: distribuera, licenser, tjänster som stöds, etablering, konfiguration Microsoft Threat Protection, M365, licens kvalificering, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, Avancerat skydd, E5, A5, EMS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843930"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integrerar olika Microsoft-säkerhetstjänster för att tillhandahålla centraliserad identifiering, förebyggande funktioner och undersökningar mot avancerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licensierings krav, de fördelar och begränsningar som är förknippade med distributionen av en eller flera tjänster och länkar till hur du kan installera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser ger till gång till följande tjänster som kan användas för att använda Microsoft 365 Defender i Microsoft 365 säkerhets Center. [Se licensierings krav](prerequisites.md#licensing-requirements)

| Tjänst som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender för slut punkt | Endpoint Protection Suite byggd kring kraftfulla beteende sensorer, Cloud Analytics och Threat Intelligence |
|Microsoft Defender för Office 365 | Avancerat skydd för dina appar och data i Office 365, inklusive e-post och andra samarbets verktyg |
| Microsoft Defender för identitet | Försvara dig mot avancerade hot, komprometterade identiteter och skadligt med Interactive Directory-signaler |
| Microsoft Cloud App Security | Identifiera och bekämpa Cyberthreats i dina Microsoft-och tredjeparts moln tjänster |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft 365 Defender ger bättre synlighet,-korrelation och-reparation allteftersom du distribuerar fler tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med fullständig distribution
För att få de fullständiga fördelarna med Microsoft 365 Defender rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras utifrån aviseringar och händelse signaler från alla tillgängliga sensorer och tjänstespecifika analys funktioner
- Automatisk undersökning och reparation (AIR) playbooks gäller för olika entitetstyper, inklusive enheter, post lådor och användar konton
- Ett mer omfattande Avancerat schema för avancerad jakt kan tillfrågas om händelse-och enhets data från enheter, post lådor och andra enheter

### <a name="limited-deployment-scenarios"></a>Begränsade distributions scenarier
Varje tjänst som du distribuerar tillhandahåller en omfattande uppsättning råa signaler samt korrelerad information. Även om begränsad distribution inte gör att Microsoft 365 Defender-funktioner kan inaktive ras kan de ge omfattande synlighet för slut punkter, appar, data och identiteter. Samtidigt gäller alla eventuella reparations funktioner för enheter som kan hanteras av de tjänster som du har distribuerat.

Tabellen nedan visar hur de olika tjänsterna tillhandahåller ytterligare data, möjligheter att få ytterligare inblick genom att korrelera data och förbättra funktioner för reparation och svar.

| Tjänst | Data (signaler & korrelerad information) | Svars omfattning & |
| ------ | ------ | ------ |
| Microsoft Defender för slut punkt | -Slut punkts tillstånd och oberedda händelser<br />-Slut punkts identifiering och larm, inklusive antivirus, EDR, reducering av attack ytan<br />-Information om filer och andra enheter som observerats för slut punkter | Slut punkter |
|Microsoft Defender för Office 365 | -Mail-och post lådans tillstånd och RAW-händelser<br />-E-post, bilagor och länk identifiering | -Post lådor<br />-Microsoft 365-konton |
| Microsoft Defender för identitet | -Active Directory-signaler, inklusive autentiseringsreferenser<br />-Identifieringar av identitets relaterade beteenden | Identiteter |
| Microsoft Cloud App Security | -Identifiering av icke sanktionerade moln program och tjänster (skugga IT)<br />-Data exponering för molnappar<br />-Hot aktivitet kopplad till molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Distribution av varje tjänst kräver vanligt vis etablering av din klient organisation och viss inledande konfiguration. Se tabellen nedan för att förstå hur de här tjänsterna distribueras.

| Tjänst | Etablerings instruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender för slut punkt | [Distributions guide för Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Se etablerings instruktioner* |
|Microsoft Defender för Office 365 | *Ingen, etablerad med Office 365* | [Konfigurera Microsoft Defender för Office 365-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender för identitet | [Snabb start: skapa en Microsoft Defender för identitets instans](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Se etablerings instruktioner* |
| Microsoft Cloud App Security | *Ingen* | [Snabb start: komma igång med säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat tjänsterna [aktiverar du Microsoft 365 Defender](mtp-enable.md).

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
- [Översikt över Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Microsoft Defender för Office 365](../office-365-security/office-365-atp.md)
- [Säkerhets översikt för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender för identitets översikt](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
