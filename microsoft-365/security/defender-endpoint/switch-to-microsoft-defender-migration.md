---
title: Göra bytet från skydd från andra slutpunkter än Microsoft Defender till Microsoft Defender för Slutpunkt
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
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2a2b78089486b432ebf9492de26396b2bb96f94d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593507"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Göra bytet från skydd från andra slutpunkter än Microsoft Defender till Microsoft Defender för Slutpunkt

Om du funderar på att byta från ditt icke-Microsoft-slutpunktsskydd till [Microsoft Defender](microsoft-defender-endpoint.md) för slutpunkt (Defender för slutpunkt) är du på rätt plats. Använd den här artikeln som en guide.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Översikt över hur du migrerar till Defender för Endpoint":::

När du byter till Defender för Slutpunkt börjar du med din lösning som inte är en Microsoft-lösning som fungerar i aktivt läge, konfigurerar Defender för Slutpunkt i passiv form, går in på Defender för Slutpunkt, ställer in Defender för Slutpunkt till aktivt läge och tar sedan bort lösningen som inte är Från Microsoft.

> [!TIP]
> - Om du använder McAfee Endpoint Security (McAfee), se [Migrera från McAfee till Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md).
> - Om du för närvarande använder Symantec Endpoint Protection (Symantec) se Migrera från [Symantec till Defender för Slutpunkt.](symantec-to-microsoft-defender-endpoint-migration.md)

## <a name="the-migration-process"></a>Migreringsprocessen

Processen för migrering till Defender för Slutpunkt kan delas upp i tre faser, enligt beskrivningen i följande tabell:

![Migreringsfaser – förbereda, konfigurera, registrera](images/phase-diagrams/migration-phases.png)

|Fas |Beskrivning |
|--|--|
|[Förbereda migreringen](switch-to-microsoft-defender-prepare.md) |Under [ **förberedelsefasen:**](switch-to-microsoft-defender-prepare.md) <p>1. Uppdatera organisationens enheter. <p>2. Skaffa Defender för Slutpunkt. <p>3. Planera dina roller och behörigheter och ge åtkomst till Microsoft Defender Säkerhetscenter. <p>4. Konfigurera din enhetsproxy och internetinställningar för att aktivera kommunikation mellan din organisations enheter och Defender för Slutpunkt. |
|[Konfigurera Defender för Slutpunkt](switch-to-microsoft-defender-setup.md) |Under [ **installationsfasen:**](switch-to-microsoft-defender-setup.md) <p>1. Aktivera/installera om Microsoft Defender Antivirus. <p>2. Konfigurera Defender för slutpunkt. <p>3. Lägg till Defender för Endpoint i undantagslistan för din befintliga lösning. <p>4. Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus. <p>5. Konfigurera enhetsgrupper, samlingar och organisationsenheter. <p>6. Konfigurera dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Onboard to Defender för Endpoint](switch-to-microsoft-defender-onboard.md) |Under [ **onboardfasen:**](switch-to-microsoft-defender-onboard.md) <p>1. Introducera dina enheter i Defender för Slutpunkt. <p>2. Kör ett identifieringstest. <p>3. Kontrollera att Microsoft Defender Antivirus körs i passiv form. <p>4. Hämta uppdateringar för Microsoft Defender Antivirus. <p>5. Avinstallera din befintliga lösning för slutpunktsskydd. <p>6. Kontrollera att Defender för Slutpunkt fungerar korrekt. |

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
