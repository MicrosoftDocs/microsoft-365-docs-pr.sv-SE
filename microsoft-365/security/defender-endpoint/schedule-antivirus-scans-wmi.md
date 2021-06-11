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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="79ad4-104">Schemalägga antivirussökningar med hjälp Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="79ad4-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="79ad4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="79ad4-105">**Applies to:**</span></span>

- [<span data-ttu-id="79ad4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="79ad4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="79ad4-107">I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med WMI.</span><span class="sxs-lookup"><span data-stu-id="79ad4-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="79ad4-108">Mer information om hur du schemalägger skanningar och om genomsökningstyper finns i [Konfigurera schemalagda snabba eller Microsoft Defender Antivirus genomsökningar.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="79ad4-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="79ad4-109">Schemalägga Windows med hjälp av WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="79ad4-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="79ad4-110">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="79ad4-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="79ad4-111">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="79ad4-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="79ad4-112">WMI för schemaläggningssökningar när en slutpunkt inte används</span><span class="sxs-lookup"><span data-stu-id="79ad4-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="79ad4-113">Använd [metoden Set för MSFT_MpPreference för](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="79ad4-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="79ad4-114">Mer information om API:er och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="79ad4-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="79ad4-115">När du schemalägger genomsökningar efter tidpunkter när slutpunkter inte används, utnyttjar inte genomsökningar CPU-begränsningskonfigurationen och kommer att dra nytta av de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="79ad4-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="79ad4-116">WMI för att schemalägga genomsökningar för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="79ad4-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="79ad4-117">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="79ad4-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="79ad4-118">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="79ad4-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="79ad4-119">WMI för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="79ad4-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="79ad4-120">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="79ad4-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="79ad4-121">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="79ad4-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

