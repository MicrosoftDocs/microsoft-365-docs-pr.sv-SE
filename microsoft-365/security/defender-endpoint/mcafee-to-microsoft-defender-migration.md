---
title: Migrera från McAfee till Microsoft Defender för Endpoint
description: Byt från McAfee till Microsoft Defender för Endpoint. Läs den här artikeln för en översikt.
keywords: migrering, Microsoft Defender för Slutpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538057"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migrera från McAfee till Microsoft Defender för Endpoint

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Om du planerar att byta från McAfee Endpoint Security (McAfee) till [Microsoft Defender](microsoft-defender-endpoint.md) för Endpoint (Microsoft Defender för Endpoint) är du på rätt plats. Använd den här artikeln som en guide.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Översikt över migrering från McAfee till Defender för Endpoint":::

När du gör bytet från McAfee till Defender för Endpoint börjar du med din McAfee-lösning i aktivt läge, konfigurerar Defender för Slutpunkt i passiv form, växlar till Defender för Slutpunkt och anger sedan att Defender ska vara aktivt läge och att McAfee ska tas bort.

## <a name="the-migration-process"></a>Migreringsprocessen

När du byter från McAfee till Microsoft Defender för Endpoint följer du en process som kan delas upp i tre faser: Förbereda, konfigurera och registrera. 

![Migreringsfaser – förbereda installationen](images/phase-diagrams/migration-phases.png)

|Fas |Beskrivning |
|--|--|
|[Förbereda migreringen](mcafee-to-microsoft-defender-prepare.md) |Under [**förberedelsefasen**](mcafee-to-microsoft-defender-prepare.md) uppdaterar du organisationens enheter, hämtar Microsoft Defender för Endpoint, planerar dina roller och behörigheter och ger åtkomst till Microsoft Defender Säkerhetscenter. Du kan också konfigurera din enhetsproxy och Internetinställningar för att aktivera kommunikation mellan din organisations enheter och Microsoft Defender för slutpunkt. |
|[Konfigurera Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-setup.md) |Under [**konfigurationsfasen**](mcafee-to-microsoft-defender-setup.md) kan du aktivera Microsoft Defender Antivirus det till passivt läge. Du kan också konfigurera & undantag för Microsoft Defender Antivirus och din befintliga lösning för slutpunktsskydd. Sedan kan du skapa grupper, samlingar och organisationsenheter för enheten. Slutligen konfigurerar du dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Gå till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-onboard.md) |Under [**onboardfasen**](mcafee-to-microsoft-defender-onboard.md) får du registrera dina enheter i Microsoft Defender för Endpoint, bekräfta att Microsoft Defender Antivirus körs i passiv form och kontrollera att dina slutpunkter kommunicerar med Defender för Endpoint. Avinstallera sedan McAfee och se till att Defender för Endpoint fungerar som det ska. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Vad ingår i Microsoft Defender för Slutpunkt?

I den här migreringsguiden fokuserar vi på nästa [generations](microsoft-defender-antivirus-in-windows-10.md) skydd [och](overview-endpoint-detection-response.md) identifiering och åtgärd på slutpunkt en startpunkt för att flytta till Microsoft Defender för Slutpunkt. Men Microsoft Defender för Endpoint innehåller mycket mer än antivirus- och slutpunktsskydd. Microsoft Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. I följande tabell sammanfattas funktioner i Microsoft Defender för Endpoint. 

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

**Vill du veta mer? Se [Microsoft Defender för Slutpunkt](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Nästa steg

- Fortsätt till [Förbereda för migreringen.](mcafee-to-microsoft-defender-prepare.md)
