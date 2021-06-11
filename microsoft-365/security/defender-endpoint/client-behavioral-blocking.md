---
title: Beteendeblockering av klientdator
description: Klientbeteendeblockering är en del av funktioner för blockering och inneslutning i Microsoft Defender för slutpunkt
keywords: blockering av beteende, snabbt skydd, klientbeteende, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795964"
---
# <a name="client-behavioral-blocking"></a>Beteendeblockering av klientdator

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Översikt

Klientbeteendeblockering är en komponent i funktioner [för beteendeblockering](behavioral-blocking-containment.md) och inneslutning i Defender för Slutpunkt. När misstänkta beteenden identifieras på enheter (kallas även klienter eller slutpunkter) blockeras, kontrolleras och åtgärdas artefakter (till exempel filer eller program) automatiskt. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Moln- och klientskydd":::

Antivirusskyddet fungerar bäst när det paras ihop med molnskydd.

## <a name="how-client-behavioral-blocking-works"></a>Så här fungerar klientbeteendeblockering

[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) kan identifiera misstänkt beteende, skadlig kod, fillös och minnesintrång och mycket mer på en enhet. När misstänkta beteenden identifieras Microsoft Defender Antivirus och skickar de misstänkta beteendena och deras processträd till molnskyddstjänsten. Maskininlärning skiljer mellan skadliga program och bra beteenden inom millisekunder och klassificerar varje artefakt. I nästan realtid blockeras en artefakt på enheten när den visar sig vara skadlig. 

När ett misstänkt beteende identifieras genereras [en avisering](alerts-queue.md) och visas i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Klientbeteendeblockering är effektivt eftersom det inte bara hjälper till att förhindra att en attack startar, den kan också stoppa en attack som har börjat köras. Och med [blockering av feedbackslingan](feedback-loop-blocking.md) (en annan funktion för blockering och inneslutning) förhindras attacker på andra enheter i organisationen.

## <a name="behavior-based-detections"></a>Funktionsbaserade identifieringar

Beteendebaserade identifieringar namnges enligt [MITRE ATT-&CK-matrisen för företag.](https://attack.mitre.org/matrices/enterprise) Namngivningskonventionerna hjälper till att identifiera attackfasen där det skadliga beteendet har observerats:


|Taktik |   Namn på identifiering av hot |
|----|----|
|Inledande åtkomst | `Behavior:Win32/InitialAccess.*!ml` |
|Körning  | `Behavior:Win32/Execution.*!ml` |
|Beständighet    | `Behavior:Win32/Persistence.*!ml` |
|Eskalering av behörighet   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Defense Evasion    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Åtkomst till autentiseringsuppgifter  | `Behavior:Win32/CredentialAccess.*!ml` |
|Upptäckt  | `Behavior:Win32/Discovery.*!ml` |
|Lateral Movement | `Behavior:Win32/LateralMovement.*!ml` |
|Samling |   `Behavior:Win32/Collection.*!ml` |
|Kommando och kontroll | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltration   | `Behavior:Win32/Exfiltration.*!ml` |
|Påverkan | `Behavior:Win32/Impact.*!ml` |
|Ej kategoriserat  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Mer information om specifika hot finns i den senaste **[globala hotaktiviteten.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Konfigurera klientbeteendeblockering

Om din organisation använder Defender för Slutpunkt är klientbeteendeblockering aktiverat som standard. Om du däremot vill dra nytta av [](behavioral-blocking-containment.md)alla Defender för Slutpunkt-funktioner, inklusive blockering och inneslutning, ska du se till att följande funktioner i Defender för slutpunkt är aktiverade och konfigurerade:

- [Defender för slutpunktsbaslinjer](configure-machines-security-baseline.md)

- [Enheter som finns i Defender för Slutpunkt](onboard-configure.md)

- [EDR i blockläge](edr-in-block-mode.md)

- [Minskning av attackytan](attack-surface-reduction.md)

- [Nästa generations skydd](configure-microsoft-defender-antivirus-features.md) (antivirus, program mot skadlig programvara och andra skyddsfunktioner för hot)

