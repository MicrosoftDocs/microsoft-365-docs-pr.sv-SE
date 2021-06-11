---
title: Schemalägga antivirussökningar med PowerShell
description: Schemalägga antivirussökningar med PowerShell
keywords: snabbsökning, fullständig sökning, antivirus, schema, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879773"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Schemalägga antivirussökningar med PowerShell

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med PowerShell-cmdlets. Mer information om hur du schemalägger skanningar och om genomsökningstyper finns i [Konfigurera schemalagda snabba eller Microsoft Defender Antivirus genomsökningar.](schedule-antivirus-scans.md) 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Använda PowerShell-cmdlets för att schemalägga skanningar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Mer information finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>PowerShell-cmdlets för att schemalägga genomsökningar när en slutpunkt inte används

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).

> [!NOTE]
> När du schemalägger genomsökningar efter tidpunkter när slutpunkter inte används, utnyttjar inte genomsökningar CPU-begränsningskonfigurationen och kommer att dra nytta av de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>PowerShell-cmdlets för att schemalägga genomsökningar för att slutföra åtgärder

Använd följande cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>PowerShell-cmdlets för att schemalägga dagliga genomsökningar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)


