---
title: Granska resultaten för Microsoft Defender AV-skanningar
description: Granska resultatet av genomsökningar med hjälp av Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhetsappen
keywords: genomsökningsresultat, åtgärd, fullständig sökning, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691207"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Granska sökresultaten för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När en Microsoft Defender [Antivirus-sökning](run-scan-microsoft-defender-antivirus.md) är klar, oavsett om det är en sökning på begäran eller en schemalagd [sökning,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)registreras resultatet och du kan visa resultaten. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Granska genomsökningsresultaten med Konfigurationshanteraren

Se [Hur du övervakar slutpunktsskyddsstatus](/configmgr/protect/deploy-use/monitor-endpoint-protection).

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

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Använda WMI (Windows Management Instruction) för att granska genomsökningsresultat

Använd metoden [ **Get**  för MSFT_MpThreat och **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klasser.


## <a name="related-articles"></a>Relaterade artiklar

- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder i Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)