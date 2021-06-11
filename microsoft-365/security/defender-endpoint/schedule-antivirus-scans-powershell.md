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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="7868a-104">Schemalägga antivirussökningar med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7868a-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="7868a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7868a-105">**Applies to:**</span></span>

- [<span data-ttu-id="7868a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7868a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7868a-107">I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7868a-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="7868a-108">Mer information om hur du schemalägger skanningar och om genomsökningstyper finns i [Konfigurera schemalagda snabba eller Microsoft Defender Antivirus genomsökningar.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="7868a-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="7868a-109">Använda PowerShell-cmdlets för att schemalägga skanningar</span><span class="sxs-lookup"><span data-stu-id="7868a-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="7868a-110">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7868a-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="7868a-111">Mer information finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="7868a-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="7868a-112">PowerShell-cmdlets för att schemalägga genomsökningar när en slutpunkt inte används</span><span class="sxs-lookup"><span data-stu-id="7868a-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="7868a-113">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7868a-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="7868a-114">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="7868a-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="7868a-115">När du schemalägger genomsökningar efter tidpunkter när slutpunkter inte används, utnyttjar inte genomsökningar CPU-begränsningskonfigurationen och kommer att dra nytta av de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7868a-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="7868a-116">PowerShell-cmdlets för att schemalägga genomsökningar för att slutföra åtgärder</span><span class="sxs-lookup"><span data-stu-id="7868a-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="7868a-117">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7868a-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="7868a-118">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="7868a-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="7868a-119">PowerShell-cmdlets för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="7868a-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="7868a-120">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7868a-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="7868a-121">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="7868a-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


