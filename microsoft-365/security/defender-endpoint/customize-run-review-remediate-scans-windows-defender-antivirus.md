---
title: Köra och anpassa schemalagda genomsökningar och sökningar på begäran
description: Anpassa och initiera sökning i Microsoft Defender Antivirus på slutpunkter i nätverket.
keywords: sökning, schemalägg, anpassa, undantag, exkludera filer, åtgärder, genomsökningsresultat, karantän, ta bort hot, snabbsökning, fullständig sökning, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5f8e5606b01186e31a58f6d506b5898f20b63511
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690796"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Anpassa, initiera och granska resultatet av genomsökningarna av Microsoft Defender Antivirus & åtgärd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda Grupprincip, PowerShell och WMI (Windows Management Instrumentation) för att konfigurera genomsökningar för Microsoft Defender Antivirus. 

## <a name="in-this-section"></a>I det här avsnittet

| Artikel | Beskrivning |
|:---|:---|
|[Konfigurera och validera undantag för filer, mappar och processer i Genomsökningar för Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md) | Du kan utesluta filer (inklusive filer som ändrats av angivna processer) och mappar från sökningar på begäran, schemalagda genomsökningar och övervakning av skydd i realtid och sökning i realtid |
|[Konfigurera sökalternativ för Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Du kan konfigurera Microsoft Defender Antivirus så att vissa typer av e-postlagringsfiler, kopierings- ellerparpareringspunkter och arkiverade filer (till exempel ZIP-filer) ingår i genomsökningar. Du kan också aktivera filsökning i nätverket |
|[Konfigurera åtgärd för genomsökningar](configure-remediation-microsoft-defender-antivirus.md) | Konfigurera vad Microsoft Defender Antivirus ska göra när programmet upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen |
|[Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar |
|[Konfigurera och köra genomsökningar](run-scan-microsoft-defender-antivirus.md) | Köra och konfigurera genomsökningar på begäran med Hjälp av PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhetsappen |
|[Granska genomsökningsresultat](review-scan-results-microsoft-defender-antivirus.md) | Granska resultatet av genomsökningar med hjälp av Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhetsappen |