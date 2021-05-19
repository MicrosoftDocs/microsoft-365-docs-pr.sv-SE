---
title: Migrera från Symantec till Microsoft Defender för Endpoint
description: Få en översikt över hur du byter från Symantec till Microsoft Defender för Endpoint
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530904"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrera från Symantec till Microsoft Defender för Endpoint
Om du planerar att byta från Symantec Endpoint Protection (Symantec) till [Microsoft Defender](microsoft-defender-endpoint.md) för Endpoint (Microsoft Defender för Endpoint) är du på rätt plats. Använd den här artikeln som en guide.

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Översikt över migrering från Symantec till Defender för Endpoint":::

När du byter från Symantec till Defender för Endpoint börjar du med din Symantec-lösning i aktivt läge, konfigurerar Defender för Slutpunkt i passivt läge, växlar till Defender för slutpunkt och ställer sedan in Defender för Endpoint på aktivt läge och tar bort Symantec.

## <a name="the-migration-process"></a>Migreringsprocessen

När du byter från Symantec till Microsoft Defender för Endpoint följer du en process som kan delas upp i tre faser enligt beskrivningen i följande tabell:

![Migreringsfaser – förbereda, konfigurera, registrera](images/phase-diagrams/migration-phases.png)

|Fas |Beskrivning |
|--|--|
|[Förbereda migreringen](symantec-to-microsoft-defender-atp-prepare.md) |Under **förberedelsefasen** uppdaterar du organisationens enheter, hämtar Microsoft Defender för Endpoint, planerar dina roller och behörigheter och ger åtkomst till Microsoft Defender Säkerhetscenter. Du kan också konfigurera din enhetsproxy och Internetinställningar för att aktivera kommunikation mellan din organisations enheter och Defender för slutpunkt. |
|[Konfigurera Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-setup.md) |Under **konfigurationsfasen** kan du aktivera Microsoft Defender Antivirus det till passivt läge. Du kan även konfigurera & undantag för Microsoft Defender Antivirus och Symantec Endpoint Protection. Sedan kan du skapa grupper, samlingar och organisationsenheter för enheten. Slutligen konfigurerar du dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Gå till Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-onboard.md) |Under  onboardfasen får du registrera dina enheter i Microsoft Defender för Endpoint, bekräfta att Microsfot Defender Antivirus körs i passiv form och kontrollera att dina slutpunkter kommunicerar med Defender för Endpoint. Avinstallera sedan Symantec och kontrollera att Defender för Endpoint fungerar som det ska. |

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

- Fortsätt till [Förbereda för migreringen.](symantec-to-microsoft-defender-atp-prepare.md)
