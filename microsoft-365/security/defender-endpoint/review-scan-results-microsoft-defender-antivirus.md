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
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007639"
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

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="skärmbild av PowerShell-cmdlets och utdata":::

Du kan ange `-ThreatID` för att begränsa utdata för att bara visa identifieringar för ett visst hot.

Om du vill lista identifieringar av hot, men kombinera identifieringar av samma hot till ett enda objekt, kan du använda följande cmdlet:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell-kod":::

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Granska Windows genom att använda WMI (Management Instruction)

Använd metoden [ **Get**  för MSFT_MpThreat och **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klasser.


## <a name="related-articles"></a>Relaterade artiklar

- [Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)