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
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 6e5b79e447579631e4aa2eaf02352dc3fa6a8daa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074129"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Gör bytet från en lösning som inte är en Microsoft-slutpunkt till Microsoft Defender för Endpoint

Om du planerar att byta från en lösning som inte är en Microsoft-slutpunktsskyddslösning till [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt) är du på rätt plats. Använd den här artikeln som en guide.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Översikt över hur du migrerar till Defender för Endpoint":::

När du byter till Defender för Endpoint börjar du med din lösning som inte är En Microsoft-lösning i aktivt läge, konfigurerar Defender för Slutpunkt i passivt läge, går till Defender för Slutpunkt och ställer sedan in Defender för Slutpunkt på aktivt läge och tar bort lösningen som inte är Från Microsoft.

> [!TIP]
> - Om du använder McAfee Endpoint Security (McAfee), se [Migrera från McAfee till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md).
> - Om du använder Symantec Endpoint Protection (Symantec) går du till Migrera från [Symantec till Microsoft Defender för Slutpunkt.](symantec-to-microsoft-defender-atp-migration.md)

## <a name="the-migration-process"></a>Migreringsprocessen

När du byter till Microsoft Defender för Slutpunkt följer du en process som kan delas upp i tre faser, enligt beskrivningen i följande tabell:

![Migreringsfaser – förbereda, konfigurera, registrera](images/phase-diagrams/migration-phases.png)

|Fas |Beskrivning |
|--|--|
|[Förbereda migreringen](switch-to-microsoft-defender-prepare.md) |Under [ **förberedelsefasen**](switch-to-microsoft-defender-prepare.md)uppdaterar du organisationens enheter, hämtar Microsoft Defender för Slutpunkt, planerar dina roller och behörigheter och ger åtkomst till Microsoft Defender Säkerhetscenter. Du kan också konfigurera din enhetsproxy och Internetinställningar för att aktivera kommunikation mellan din organisations enheter och Microsoft Defender för slutpunkt. |
|[Konfigurera Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-setup.md) |Under [  konfigurationsfasen](switch-to-microsoft-defender-setup.md)aktiverar du Microsoft Defender Antivirus och kontrollerar att det är i passivt läge, och du konfigurerar inställningar &-undantag för Microsoft Defender Antivirus, Microsoft Defender för Slutpunkt och din befintliga lösning för slutpunktsskydd. Du kan också skapa enhetsgrupper, samlingar och organisationsenheter. Slutligen konfigurerar du dina riktlinjer för program mot skadlig programvara och inställningar för realtidsskydd.|
|[Gå till Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-onboard.md) |Under [ **onboardfasen**](switch-to-microsoft-defender-onboard.md)får du registrera dina enheter i Microsoft Defender för Endpoint och verifiera att dessa enheter kommunicerar med Microsoft Defender för Endpoint. Sist avinstallerar du din befintliga lösning för slutpunktsskydd och ser till att skyddet via Microsoft Defender Antivirus & Microsoft Defender för Slutpunkt är i aktivt läge. |

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

- Fortsätt till [Förbereda för migreringen.](switch-to-microsoft-defender-prepare.md)
