---
title: Migrera från Symantec till Microsoft Defender för Endpoint
description: Få en översikt över hur du byter från Symantec till Microsoft Defender för Endpoint
keywords: migrering, windows defender avancerat skydd, atp, edr
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218830"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrera från Symantec till Microsoft Defender för Endpoint
Om du planerar att byta från Symantec Endpoint Protection (Symantec) till [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för Slutpunkt (Microsoft Defender för Slutpunkt) har du rätt plats. Använd den här artikeln som en guide.

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
|[Förbereda migreringen](symantec-to-microsoft-defender-atp-prepare.md) |Under **förberedelsefasen** får du Microsoft Defender för Endpoint, planerar dina roller och behörigheter och ger åtkomst till Microsoft Defender Säkerhetscenter. Du kan också konfigurera din enhetsproxy och Internetinställningar för att aktivera kommunikation mellan din organisations enheter och Microsoft Defender för slutpunkt. |
|[Konfigurera Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-setup.md) |Under **konfigurationsfasen** konfigurerar du inställningar och undantag för Microsoft Defender Antivirus, Microsoft Defender för Endpoint och Symantec Endpoint Protection. Du kan också skapa enhetsgrupper, samlingar och organisationsenheter. Slutligen konfigurerar du dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Gå till Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-onboard.md) |Under fasen **Onboard** onboardar du dina enheter till Microsoft Defender för Endpoint och kontrollerar att dessa enheter kommunicerar med Microsoft Defender för Endpoint. Sist avinstallerar du Symantec och ser till att skyddet via Microsoft Defender för Endpoint är i aktivt läge. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Vad ingår i Microsoft Defender för Slutpunkt?

I den här migreringsguiden fokuserar [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) vi på nästa [generations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) skydd och funktioner för identifiering av slutpunkt och svar som en utgångspunkt när vi flyttar över till Microsoft Defender för Slutpunkt. Men Microsoft Defender för Endpoint innehåller mycket mer än antivirus- och slutpunktsskydd. Microsoft Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. I följande tabell sammanfattas funktioner i Microsoft Defender för Endpoint. 

| Funktion/funktion | Beskrivning |
|---|---|
| [Hot & sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Hot & funktioner för sårbarhetshantering hjälper till att identifiera, bedöma och åtgärda svagheter mellan dina slutpunkter (t.ex. enheter). |
| [Minskning av attackytan](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Minskningsregler för attackytan hjälper till att skydda organisationens enheter och program från cyberhot och attacker. |
| [Nästa generations skydd](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Nästa generations skydd inkluderar Microsoft Defender Antivirus för att blockera hot och skadlig programvara. |
| [Identifiering och svar av slutpunkter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Funktioner för identifiering av slutpunkter och svar identifierar, undersöker och svarar på intrångsförsök och aktiva intrång.  |
| [Avancerad jakt](advanced-hunting-overview.md) | Med avancerade sökfunktioner kan ditt säkerhetsteam hitta indikatorer och enheter för kända eller potentiella hot. |
| [Blockering och inneslutning av beteende](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Funktioner för blockering och inneslutning hjälper till att identifiera och stoppa hot, baserat på deras beteende och processträd även när hoten har börjat körs. |
| [Automatiserad undersökning och åtgärder](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Med automatiska undersöknings- och svarsfunktioner undersöks aviseringar och åtgärder vidtas omedelbart för att lösa överträdelser. |
| [Service för hot efter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) hot (Microsoft Threat Experts) | Med tjänster för hotsäkerhet kan säkerhetsgrupper med övervakning och analys på expertnivå säkerställa att inga kritiska hot missas. |

**Vill du veta mer? Se [Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Nästa steg

- Fortsätt till [Förbereda för migreringen.](symantec-to-microsoft-defender-atp-prepare.md)
