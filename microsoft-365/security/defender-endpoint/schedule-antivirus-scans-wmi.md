---
title: Schemalägga antivirussökningar med hjälp Windows Management Instrumentation
description: Schemalägga antivirussökningar med WMI
keywords: snabbsökning, fullständig sökning, WMI, schema, antivirus
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879772"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Schemalägga antivirussökningar med hjälp Windows Management Instrumentation (WMI)

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med WMI. Mer information om hur du schemalägger skanningar och om genomsökningstyper finns i [Konfigurera schemalagda snabba eller Microsoft Defender Antivirus genomsökningar.](schedule-antivirus-scans.md) 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Schemalägga Windows med hjälp av WMI (Management Instruction)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI för schemaläggningssökningar när en slutpunkt inte används

Använd [metoden Set för MSFT_MpPreference för](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) följande egenskaper:

```WMI
ScanOnlyIfIdleEnabled
```

Mer information om API:er och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> När du schemalägger genomsökningar efter tidpunkter när slutpunkter inte används, utnyttjar inte genomsökningar CPU-begränsningskonfigurationen och kommer att dra nytta av de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI för att schemalägga genomsökningar för att slutföra åtgärd

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-daily-scans"></a>WMI för att schemalägga dagliga genomsökningar

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanScheduleQuickScanTime
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

