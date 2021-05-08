---
title: Köra och anpassa schemalagda genomsökningar och sökningar på begäran
description: Anpassa och starta Microsoft Defender Antivirus genomsökningar på slutpunkter i nätverket.
keywords: skanning, schemalägg, anpassa, undantag, exkludera filer, åtgärder, genomsökningsresultat, karantän, ta bort hot, snabbsökning, fullständig sökning, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286251"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar & åtgärd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda Grupprincip, PowerShell och Windows Management Instrumentation (WMI) för att konfigurera Microsoft Defender Antivirus genomsökningar. 

## <a name="in-this-section"></a>I det här avsnittet

| Artikel | Beskrivning |
|:---|:---|
|[Konfigurera och validera undantag för filer, mappar och processbaserade filer i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md) | Du kan utesluta filer (inklusive filer som ändrats av angivna processer) och mappar från sökningar på begäran, schemalagda genomsökningar och övervakning av skydd i realtid och sökning i realtid |
|[Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Du kan Microsoft Defender Antivirus att inkludera vissa typer av e-postlagringsfiler, kopierings- eller omparentpunkter och arkiverade filer (till exempel .zip) i genomsökningar. Du kan också aktivera filsökning i nätverket |
|[Konfigurera åtgärd för genomsökningar](configure-remediation-microsoft-defender-antivirus.md) | Konfigurera vad Microsoft Defender Antivirus ska göra när den upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen |
|[Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar |
|[Konfigurera och köra genomsökningar](run-scan-microsoft-defender-antivirus.md) | Köra och konfigurera genomsökningar på begäran med PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhet-appen |
|[Granska genomsökningsresultat](review-scan-results-microsoft-defender-antivirus.md) | Granska resultatet av skanningar med hjälp Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhet appen |