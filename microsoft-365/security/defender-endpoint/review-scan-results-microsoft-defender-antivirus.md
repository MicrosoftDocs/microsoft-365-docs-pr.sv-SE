---
title: Granska resultaten för Microsoft Defender AV-skanningar
description: Granska resultatet av skanningar med hjälp Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhet appen
keywords: genomsökningsresultat, åtgärd, fullständig sökning, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275378"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Granska Microsoft Defender Antivirus genomsökningsresultat

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När en Microsoft Defender Antivirus är klar, oavsett [](run-scan-microsoft-defender-antivirus.md) om det är en sökning på begäran eller [schemalagd,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)spelas resultatet in och du kan visa resultaten. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Granska genomsökningsresultaten med Konfigurationshanteraren

Se [Hur du övervakar Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Använda PowerShell-cmdlets för att granska genomsökningsresultat

Följande cmdlet returnerar varje identifiering på slutpunkten. Om det finns flera identifieringar av samma hot listas varje identifiering separat, baserat på tiden för varje identifiering:

```PowerShell
Get-MpThreatDetection
```

![skärmbild av PowerShell-cmdlets och utdata](images/defender/wdav-get-mpthreatdetection.png)

Du kan ange `-ThreatID` för att begränsa utdata för att bara visa identifieringar för ett visst hot.

Om du vill lista identifieringar av hot, men kombinera identifieringar av samma hot till ett enda objekt, kan du använda följande cmdlet:

```PowerShell
Get-MpThreat
```

![skärmbild av PowerShell](images/defender/wdav-get-mpthreat.png)

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Granska Windows genom att använda WMI (Management Instruction)

Använd metoden [ **Get**  för MSFT_MpThreat och **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klasser.


## <a name="related-articles"></a>Relaterade artiklar

- [Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)