---
title: Köra och anpassa schemalagda genomsökningar och sökningar på begäran
description: Anpassa och starta Microsoft Defender Antivirus genomsökningar på slutpunkter i nätverket.
keywords: skanning, schemalägg, anpassa, undantag, exkludera filer, åtgärder, genomsökningsresultat, karantän, ta bort hot, snabbsökning, fullständig sökning, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275282"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="5bac1-104">Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder</span><span class="sxs-lookup"><span data-stu-id="5bac1-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5bac1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5bac1-105">**Applies to:**</span></span>

- [<span data-ttu-id="5bac1-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bac1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5bac1-107">Du kan använda Grupprincip, PowerShell och Windows Management Instrumentation (WMI) för att konfigurera Microsoft Defender Antivirus genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="5bac1-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="5bac1-108">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="5bac1-108">In this section</span></span>

<span data-ttu-id="5bac1-109">Ämne</span><span class="sxs-lookup"><span data-stu-id="5bac1-109">Topic</span></span> | <span data-ttu-id="5bac1-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5bac1-110">Description</span></span>
---|---
[<span data-ttu-id="5bac1-111">Konfigurera och validera undantag för filer, mappar och processbaserade filer i Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="5bac1-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-112">Du kan utesluta filer (inklusive filer som ändrats av angivna processer) och mappar från sökningar på begäran, schemalagda genomsökningar och övervakning av skydd i realtid och sökning i realtid</span><span class="sxs-lookup"><span data-stu-id="5bac1-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="5bac1-113">Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="5bac1-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-114">Du kan Microsoft Defender Antivirus att inkludera vissa typer av e-postlagringsfiler, kopierings- eller omparentpunkter och arkiverade filer (till exempel .zip) i genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="5bac1-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="5bac1-115">Du kan också aktivera filsökning i nätverket</span><span class="sxs-lookup"><span data-stu-id="5bac1-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="5bac1-116">Konfigurera åtgärd för genomsökningar</span><span class="sxs-lookup"><span data-stu-id="5bac1-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-117">Konfigurera vad Microsoft Defender Antivirus ska göra när den upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen</span><span class="sxs-lookup"><span data-stu-id="5bac1-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="5bac1-118">Konfigurera schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="5bac1-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-119">Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar</span><span class="sxs-lookup"><span data-stu-id="5bac1-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="5bac1-120">Konfigurera och köra genomsökningar</span><span class="sxs-lookup"><span data-stu-id="5bac1-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-121">Köra och konfigurera genomsökningar på begäran med PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhet-appen</span><span class="sxs-lookup"><span data-stu-id="5bac1-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="5bac1-122">Granska genomsökningsresultat</span><span class="sxs-lookup"><span data-stu-id="5bac1-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="5bac1-123">Granska resultatet av skanningar med hjälp Microsoft Endpoint Configuration Manager, Microsoft Intune eller Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="5bac1-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>