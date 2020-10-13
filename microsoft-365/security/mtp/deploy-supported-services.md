---
title: Distribuera tjänster som stöds av Microsoft Threat Protection
description: Lär dig mer om Microsofts säkerhets tjänster som kan integreras med Microsoft Threat Protection, deras licensierings krav och distributions förfaranden
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
ms.openlocfilehash: 4e4036e1a1ee0ccf807dc5299b9842911f140478
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430817"
---
# <a name="deploy-supported-services"></a>Distribuera tjänster som stöds

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integrerar olika Microsoft-säkerhetstjänster för att tillhandahålla centraliserad identifiering, förebyggande och utredning för avancerade attacker. I den här artikeln beskrivs de tjänster som stöds, deras licensierings krav, de fördelar och begränsningar som är förknippade med distributionen av en eller flera tjänster och länkar till hur du kan installera dem individuellt.

## <a name="supported-services"></a>Tjänster som stöds
En Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser ger till gång till följande tjänster som kan användas för att du ska kunna använda Microsoft Threat Protection i Microsoft 365 säkerhets Center. [Se licensierings krav](prerequisites.md#licensing-requirements)

| Tjänst som stöds | Beskrivning |
| ------ | ------ |
| Microsoft Defender Avancerat skydd | Endpoint Protection Suite byggd kring kraftfulla beteende sensorer, Cloud Analytics och Threat Intelligence |
| Skaffa Office 365 ATP | Avancerat skydd för dina appar och data i Office 365, inklusive e-post och andra samarbets verktyg |
| Azure ATP | Försvara dig mot avancerade hot, komprometterade identiteter och skadligt med Interactive Directory-signaler |
| Microsoft Cloud App Security | Identifiera och bekämpa Cyberthreats i dina Microsoft-och tredjeparts moln tjänster |

## <a name="deployed-services-and-functionality"></a>Distribuerade tjänster och funktioner
Microsoft Threat Protection ger bättre synlighet, korrelation och reparation allteftersom du distribuerar fler tjänster som stöds.

### <a name="benefits-of-full-deployment"></a>Fördelar med fullständig distribution
För att få de fullständiga fördelarna med Microsoft Threat Protection rekommenderar vi att du distribuerar alla tjänster som stöds. Här är några av de viktigaste fördelarna med fullständig distribution:
- Incidenter identifieras och korreleras utifrån aviseringar och händelse signaler från alla tillgängliga sensorer och tjänstespecifika analys funktioner
- Automatisk undersökning och reparation (AIR) playbooks gäller för olika entitetstyper, inklusive enheter, post lådor och användar konton
- Ett mer omfattande Avancerat schema för avancerad jakt kan tillfrågas om händelse-och enhets data från enheter, post lådor och andra enheter

### <a name="limited-deployment-scenarios"></a>Begränsade distributions scenarier
Varje tjänst som du distribuerar tillhandahåller en omfattande uppsättning råa signaler samt korrelerad information. Även om begränsad distribution inte gör att Microsoft Threat Protection-funktioner inaktive ras kan de ge fullständig insyn i slut punkter, appar, data och identiteter påverkas. Samtidigt gäller alla eventuella reparations funktioner för enheter som kan hanteras av de tjänster som du har distribuerat.

Tabellen nedan visar hur de olika tjänsterna tillhandahåller ytterligare data, möjligheter att få ytterligare inblick genom att korrelera data och förbättra funktioner för reparation och svar.

| Tjänst | Data (signaler & korrelerad information) | Svars omfattning & |
| ------ | ------ | ------ |
| Microsoft Defender Avancerat skydd | -Slut punkts tillstånd och oberedda händelser<br />-Slut punkts identifiering och larm, inklusive antivirus, EDR, reducering av attack ytan<br />-Information om filer och andra enheter som observerats för slut punkter | Slut punkter |
| Skaffa Office 365 ATP | -Mail-och post lådans tillstånd och RAW-händelser<br />-E-post, bilagor och länk identifiering | -Post lådor<br />-Microsoft 365-konton |
| Azure ATP | -Active Directory-signaler, inklusive autentiseringsreferenser<br />-Identifieringar av identitets relaterade beteenden | Identiteter |
| Microsoft Cloud App Security | -Identifiering av icke sanktionerade moln program och tjänster (skugga IT)<br />-Data exponering för molnappar<br />-Hot aktivitet kopplad till molnappar | Molnappar |

## <a name="deploy-the-services"></a>Distribuera tjänsterna
Distribution av varje tjänst kräver vanligt vis etablering av din klient organisation och viss inledande konfiguration. Se tabellen nedan för att förstå hur de här tjänsterna distribueras.

| Tjänst | Etablerings instruktioner | Inledande konfiguration |
| ------ | ------ | ------ |
| Microsoft Defender Avancerat skydd | [Distributions guide för Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Se etablerings instruktioner* |
| Skaffa Office 365 ATP | *Ingen, etablerad med Office 365* | [Konfigurera ATP-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Snabb start: skapa din Azure ATP-instans](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Se etablerings instruktioner* |
| Microsoft Cloud App Security | *Ingen* | [Snabb start: komma igång med säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

När du har distribuerat de tjänster som stöds [aktiverar du skydd mot Microsoft Threat](mtp-enable.md).

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Threat Protection-översikt](microsoft-threat-protection.md)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP-översikt](../office-365-security/office-365-atp.md)
- [Säkerhets översikt för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
