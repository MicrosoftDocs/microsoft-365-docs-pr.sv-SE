---
title: Beteendeblockering av klientdator
description: Klientbeteendeblockering är en del av funktioner för blockering och inneslutning i Microsoft Defender för slutpunkt
keywords: blockering av beteende, snabbt skydd, klientbeteende, Microsoft Defender ATP
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
ms.openlocfilehash: 9fcff96b2583c6ef6bec05429ec50a71f3872e43
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587113"
---
# <a name="client-behavioral-blocking"></a>Beteendeblockering av klientdator

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Översikt

Klientbeteendeblockering är en komponent i funktioner [för beteendeblockering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) och inneslutning i Defender för Slutpunkt. När misstänkta beteenden identifieras på enheter (kallas även klienter eller slutpunkter) blockeras, kontrolleras och åtgärdas artefakter (till exempel filer eller program) automatiskt. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Moln- och klientskydd":::

Antivirusskyddet fungerar bäst när det paras ihop med molnskydd.

## <a name="how-client-behavioral-blocking-works"></a>Så här fungerar klientbeteendeblockering

[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kan identifiera misstänkt beteende, skadlig kod, fillösa och minnesattacker och mycket mer på en enhet. När misstänkta beteenden upptäcks övervakar Microsoft Defender Antivirus och skickar de misstänkta beteendena och deras processträd till molnskyddstjänsten. Maskininlärning skiljer mellan skadliga program och bra beteenden inom millisekunder och klassificerar varje artefakt. I nästan realtid blockeras en artefakt på enheten när den visar sig vara skadlig. 

När ett misstänkt beteende identifieras genereras [en avisering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) och visas i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Klientbeteendeblockering är effektivt eftersom det inte bara hjälper till att förhindra att en attack startar, den kan också stoppa en attack som har börjat köras. Och med [blockering av feedbackslingan](feedback-loop-blocking.md) (en annan funktion för blockering och inneslutning) förhindras attacker på andra enheter i organisationen.

## <a name="behavior-based-detections"></a>Funktionsbaserade identifieringar

Beteendebaserade identifieringar namnges enligt [MITRE ATT-&CK-matrisen för företag.](https://attack.mitre.org/matrices/enterprise) Namngivningskonventionerna hjälper till att identifiera attackfasen där det skadliga beteendet har observerats:


|Taktik |   Namn på identifiering av hot |
|----|----|
|Inledande åtkomst | Beteende:Win32/InitialAccess.*!ml |
|Körning  | Beteende:Win32/Execution.*!ml |
|Beständighet    | Beteende:Win32/Persistence.*!ml |
|Eskalering av behörighet   | Beteende:Win32/PrivilegeEscalation.*!ml |
|Defense Evasion    | Beteende:Win32/DefenseEvasion.*!ml |
|Åtkomst till autentiseringsuppgifter  | Beteende:Win32/CredentialAccess.*!ml |
|Upptäckt  | Beteende:Win32/Discovery.*!ml |
|Lateral Movement | Beteende:Win32/Movement.*!ml |
|Samling |   Beteende:Win32/Collection.*!ml |
|Kommando och kontroll | Beteende:Win32/CommandAndControl.*!ml |
|Exfiltration   | Beteende:Win32/Exfiltration.*!ml |
|Påverkan | Beteende:Win32/Impact.*!ml |
|Ej kategoriserat  | Beteende:Win32/Generic.*!ml |

> [!TIP]
> Mer information om specifika hot finns i den senaste **[globala hotaktiviteten.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Konfigurera klientbeteendeblockering

Om din organisation använder Defender för Slutpunkt är klientbeteendeblockering aktiverat som standard. Om du däremot vill dra nytta av [](behavioral-blocking-containment.md)alla Defender för Slutpunkt-funktioner, inklusive blockering och inneslutning, ska du se till att följande funktioner i Defender för slutpunkt är aktiverade och konfigurerade:

- [Defender för slutpunktsbaslinjer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Enheter som finns i Defender för Slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR i blockläge](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Minskning av attackytan](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Nästa generations skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Relaterade artiklar

- [Beteendeblockering och inneslutning](behavioral-blocking-containment.md)

- [Blockering av feedbackslinga](feedback-loop-blocking.md)

- [(Blogg) Beteendeblockering och inneslutning: Omvandla fiberoptisk till skydd](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Användbara Defender för Slutpunkt-resurser](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
