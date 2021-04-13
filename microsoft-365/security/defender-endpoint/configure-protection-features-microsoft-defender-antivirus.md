---
title: Aktivera och konfigurera funktioner för Antivirusskydd i Microsoft Defender
description: Aktivera beteendebaserad, heuristisk och realtidsskydd i Microsoft Defender AV.
keywords: heuristisk, maskininlärning, beteendeövervakare, realtidsskydd, alltid på, Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690877"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Konfigurera behavioruellt, heuristiskt och realtidsskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus använder flera olika metoder för att skydda hot:

- Molnskydd för omedelbar identifiering och blockering av nya och nya hot
- Ständigt skanna, med övervakning av fil- och processbeteenden och annan heuristik (kallas även "realtidsskydd")
- Särskilda skyddsuppdateringar baserade på maskininlärning, mänsklig och automatiserad analys av stora data samt ingående forskning om hotresistens

Du kan konfigurera hur Microsoft Defender Antivirus använder de här metoderna med Grupprincip, System Center Configuration Manage, PowerShell-cmdlets och Windows Management Instrumentation (WMI).

Det här avsnittet beskriver konfiguration för alltid-on-skanning, inklusive hur du identifierar och blockerar appar som anses osäkra, men inte kan identifieras som skadlig programvara.

Se [Använda nästa generationens Microsoft Defender Antivirus-tekniker via](cloud-protection-microsoft-defender-antivirus.md) moln levererat skydd för att aktivera och konfigurera moln levererat skydd för Microsoft Defender Antivirus.

## <a name="in-this-section"></a>I det här avsnittet

 Ämne | Beskrivning
---|---
[Identifiera och blockera potentiellt oönskade program](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Identifiera och blockera appar som kan vara oönskade i nätverket, till exempel reklamprogram, webbläsarrektatörer och verktygsfält och falska eller falska antivirusprogram
[Aktivera och konfigurera skyddsfunktioner i Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) | Aktivera och konfigurera realtidsskydd, heuristics och andra ständigt tillgängliga övervakningsfunktioner i Microsoft Defender Antivirus