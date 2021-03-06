---
title: Aktivera och konfigurera Microsoft Defender Antivirus skyddsfunktioner
description: Aktivera beteendebaserad, heuristisk och realtidsskydd i Microsoft Defender AV.
keywords: heuristisk, maskininlärning, beteendeövervakare, realtidsskydd, alltid på, Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925569"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Konfigurera skydd för beteende, heuristisk och realtid


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus flera metoder för att skydda hot:

- Molnskydd för omedelbar identifiering och blockering av nya och nya hot
- Ständigt skanna, med övervakning av fil- och processbeteenden och annan heuristik (kallas även "realtidsskydd")
- Särskilda skyddsuppdateringar baserade på maskininlärning, mänsklig och automatiserad analys av stora data samt ingående forskning om hotresistens

Du kan konfigurera Microsoft Defender Antivirus hur de här metoderna används med Grupprincip, System Center Configuration Manage, PowerShell-cmdlets och Windows Management Instrumentation (WMI).

Det här avsnittet beskriver konfiguration för alltid-on-skanning, inklusive hur du identifierar och blockerar appar som anses osäkra, men inte kan identifieras som skadlig programvara.

Se [Använda nästa generationens Microsoft Defender Antivirus-teknik via](cloud-protection-microsoft-defender-antivirus.md) moln levererat skydd för att aktivera och konfigurera Microsoft Defender Antivirus moln levererat skydd.

## <a name="in-this-section"></a>I det här avsnittet

 Ämne | Beskrivning
---|---
[Identifiera och blockera potentiellt oönskade program](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Identifiera och blockera appar som kan vara oönskade i nätverket, till exempel reklamprogram, webbläsarrektatörer och verktygsfält och falska eller falska antivirusprogram
[Aktivera och Microsoft Defender Antivirus funktioner för skydd](configure-real-time-protection-microsoft-defender-antivirus.md) | Aktivera och konfigurera realtidsskydd, heuristics och andra funktioner för Microsoft Defender Antivirus övervakning
