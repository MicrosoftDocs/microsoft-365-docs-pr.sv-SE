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
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="9cf8b-104">Granska Microsoft Defender Antivirus genomsökningsresultat</span><span class="sxs-lookup"><span data-stu-id="9cf8b-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9cf8b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9cf8b-105">**Applies to:**</span></span>

- [<span data-ttu-id="9cf8b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9cf8b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9cf8b-107">När en Microsoft Defender Antivirus är klar, oavsett [](run-scan-microsoft-defender-antivirus.md) om det är en sökning på begäran eller [schemalagd,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)spelas resultatet in och du kan visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="9cf8b-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="9cf8b-108">Granska genomsökningsresultaten med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="9cf8b-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="9cf8b-109">Se [Hur du övervakar Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="9cf8b-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="9cf8b-110">Använda PowerShell-cmdlets för att granska genomsökningsresultat</span><span class="sxs-lookup"><span data-stu-id="9cf8b-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="9cf8b-111">Följande cmdlet returnerar varje identifiering på slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="9cf8b-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="9cf8b-112">Om det finns flera identifieringar av samma hot listas varje identifiering separat, baserat på tiden för varje identifiering:</span><span class="sxs-lookup"><span data-stu-id="9cf8b-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![skärmbild av PowerShell-cmdlets och utdata](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="9cf8b-114">Du kan ange `-ThreatID` för att begränsa utdata för att bara visa identifieringar för ett visst hot.</span><span class="sxs-lookup"><span data-stu-id="9cf8b-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="9cf8b-115">Om du vill lista identifieringar av hot, men kombinera identifieringar av samma hot till ett enda objekt, kan du använda följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9cf8b-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![skärmbild av PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="9cf8b-117">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9cf8b-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="9cf8b-118">Granska Windows genom att använda WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="9cf8b-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="9cf8b-119">Använd metoden [ **Get**  för MSFT_MpThreat och **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klasser.</span><span class="sxs-lookup"><span data-stu-id="9cf8b-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="9cf8b-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9cf8b-120">Related articles</span></span>

- [<span data-ttu-id="9cf8b-121">Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder</span><span class="sxs-lookup"><span data-stu-id="9cf8b-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9cf8b-122">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="9cf8b-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)