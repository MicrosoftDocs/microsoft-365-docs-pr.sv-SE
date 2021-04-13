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
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a><span data-ttu-id="30832-104">Anpassa, initiera och granska resultatet av genomsökningarna av Microsoft Defender Antivirus & åtgärd</span><span class="sxs-lookup"><span data-stu-id="30832-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans & remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="30832-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="30832-105">**Applies to:**</span></span>

- [<span data-ttu-id="30832-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="30832-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="30832-107">Du kan använda Grupprincip, PowerShell och WMI (Windows Management Instrumentation) för att konfigurera genomsökningar för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="30832-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="30832-108">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="30832-108">In this section</span></span>

| <span data-ttu-id="30832-109">Artikel</span><span class="sxs-lookup"><span data-stu-id="30832-109">Article</span></span> | <span data-ttu-id="30832-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="30832-110">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="30832-111">Konfigurera och validera undantag för filer, mappar och processer i Genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="30832-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-112">Du kan utesluta filer (inklusive filer som ändrats av angivna processer) och mappar från sökningar på begäran, schemalagda genomsökningar och övervakning av skydd i realtid och sökning i realtid</span><span class="sxs-lookup"><span data-stu-id="30832-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span> |
|[<span data-ttu-id="30832-113">Konfigurera sökalternativ för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="30832-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-114">Du kan konfigurera Microsoft Defender Antivirus så att vissa typer av e-postlagringsfiler, kopierings- ellerparpareringspunkter och arkiverade filer (till exempel ZIP-filer) ingår i genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="30832-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="30832-115">Du kan också aktivera filsökning i nätverket</span><span class="sxs-lookup"><span data-stu-id="30832-115">You can also enable network file scanning</span></span> |
|[<span data-ttu-id="30832-116">Konfigurera åtgärd för genomsökningar</span><span class="sxs-lookup"><span data-stu-id="30832-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-117">Konfigurera vad Microsoft Defender Antivirus ska göra när programmet upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen</span><span class="sxs-lookup"><span data-stu-id="30832-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span> |
|[<span data-ttu-id="30832-118">Konfigurera schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="30832-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-119">Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar</span><span class="sxs-lookup"><span data-stu-id="30832-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span> |
|[<span data-ttu-id="30832-120">Konfigurera och köra genomsökningar</span><span class="sxs-lookup"><span data-stu-id="30832-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-121">Köra och konfigurera genomsökningar på begäran med Hjälp av PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhetsappen</span><span class="sxs-lookup"><span data-stu-id="30832-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span> |
|[<span data-ttu-id="30832-122">Granska genomsökningsresultat</span><span class="sxs-lookup"><span data-stu-id="30832-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="30832-123">Granska resultatet av genomsökningar med hjälp av Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhetsappen</span><span class="sxs-lookup"><span data-stu-id="30832-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span> |