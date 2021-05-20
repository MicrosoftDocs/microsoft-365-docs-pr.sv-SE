---
title: Gör bytet från en lösning som inte är en Microsoft-slutpunkt till Microsoft Defender för Endpoint
description: Gå över till Microsoft Defender för Endpoint. Läs den här artikeln för en översikt.
keywords: migrering, windows defender avancerat slutpunktsskydd, för Slutpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538009"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Gör bytet från en lösning som inte är en Microsoft-slutpunkt till Microsoft Defender för Endpoint

Om du planerar att byta från en lösning som inte är en Microsoft-slutpunktsskyddslösning till [Microsoft Defender](microsoft-defender-endpoint.md) för slutpunkt (Defender för slutpunkt) är du på rätt plats. Använd den här artikeln som en guide.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Översikt över hur du migrerar till Defender för Endpoint":::

När du byter till Defender för Endpoint börjar du med din lösning som inte är En Microsoft-lösning i aktivt läge, konfigurerar Defender för Slutpunkt i passivt läge, går till Defender för Slutpunkt och ställer sedan in Defender för Slutpunkt på aktivt läge och tar bort lösningen som inte är Från Microsoft.

> [!TIP]
> - Om du använder McAfee Endpoint Security (McAfee), se [Migrera från McAfee till Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md).
> - Om du för närvarande använder Symantec Endpoint Protection (Symantec) se Migrera från [Symantec till Defender för Slutpunkt.](symantec-to-microsoft-defender-endpoint-migration.md)

## <a name="the-migration-process"></a>Migreringsprocessen

När du byter till Defender för Slutpunkt följer du en process som kan delas upp i tre faser, enligt beskrivningen i följande tabell:

![Migreringsfaser – förbereda, konfigurera, registrera](images/phase-diagrams/migration-phases.png)

|Fas |Beskrivning |
|--|--|
|[Förbereda migreringen](switch-to-microsoft-defender-prepare.md) |Under [ **förberedelsefasen**](switch-to-microsoft-defender-prepare.md)uppdaterar du organisationens enheter, hämtar Defender för Slutpunkt, planerar dina roller och behörigheter och ger åtkomst till Microsoft Defender Säkerhetscenter. Du kan också konfigurera din enhetsproxy och Internetinställningar för att aktivera kommunikation mellan din organisations enheter och Defender för slutpunkt. |
|[Konfigurera Defender för Slutpunkt](switch-to-microsoft-defender-setup.md) |Under [ **konfigurationsfasen** aktiverar](switch-to-microsoft-defender-setup.md)du Microsoft Defender Antivirus det till passivt läge. Du kan också konfigurera & undantag för Microsoft Defender Antivirus och din befintliga lösning för slutpunktsskydd. Sedan kan du skapa grupper, samlingar och organisationsenheter för enheten. Slutligen konfigurerar du dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Onboard to Defender för Endpoint](switch-to-microsoft-defender-onboard.md) |Under [ **onboardfasen**](switch-to-microsoft-defender-onboard.md)får du registrera dina enheter i Defender för Endpoint, bekräfta att Microsoft Defender Antivirus körs i passiv form och kontrollera att dina slutpunkter kommunicerar med Defender för Endpoint. Sedan avinstallerar du din befintliga lösning för slutpunktsskydd och kontrollerar att Defender för slutpunkt fungerar korrekt. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Vad ingår i Microsoft Defender för Slutpunkt?

I den här migreringsguiden fokuserar vi på nästa [generations](microsoft-defender-antivirus-in-windows-10.md) skydd [och identifiering och åtgärd på slutpunkt](overview-endpoint-detection-response.md) funktioner som en utgångspunkt för att flytta till Defender för Slutpunkt. Men Defender för Slutpunkt innehåller mycket mer än antivirus- och slutpunktsskydd. Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. I följande tabell sammanfattas funktioner i Defender för Endpoint. 

| Funktion/funktion | Beskrivning |
|---|---|
| [Hot och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md) | Hot & hantering av säkerhetsrisker funktioner hjälper till att identifiera, utvärdera och åtgärda svagheter mellan dina slutpunkter (t.ex. enheter). |
| [Minskning av attackytan](overview-attack-surface-reduction.md) | Minskningsregler för attackytan hjälper till att skydda organisationens enheter och program från cyberhot och attacker. |
| [Nästa generations skydd](microsoft-defender-antivirus-in-windows-10.md) | Nästa generations skydd inkluderar skydd Microsoft Defender Antivirus att blockera hot och skadlig programvara. |
| [Identifiering och svar för slutpunkt](overview-endpoint-detection-response.md) | Funktioner för identifiering av slutpunkter och svar identifierar, undersöker och svarar på intrångsförsök och aktiva intrång.  |
| [Avancerad jakt](advanced-hunting-overview.md) | Med avancerade sökfunktioner kan ditt säkerhetsteam hitta indikatorer och enheter för kända eller potentiella hot. |
| [Beteendeblockering och inneslutning](behavioral-blocking-containment.md) | Funktioner för blockering och inneslutning hjälper till att identifiera och stoppa hot, baserat på deras beteende och processträd även när hoten har börjat körs. |
| [Automatiserad undersökning och åtgärder](automated-investigations.md) | Med automatiska undersöknings- och svarsfunktioner undersöks aviseringar och åtgärder vidtas omedelbart för att lösa överträdelser. |
| [Hot-service](microsoft-threat-experts.md) (Microsoft Hotexperter) | Med tjänster för hotsäkerhet kan säkerhetsgrupper med övervakning och analys på expertnivå säkerställa att inga kritiska hot missas. |

**Vill du veta mer? Se [Defender för Slutpunkt](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Nästa steg

- Fortsätt till [Förbereda för migreringen.](switch-to-microsoft-defender-prepare.md)
