---
title: Vad är nytt i Microsoft Defender för Endpoint på Linux
description: Lista över större ändringar för Microsoft Defender för Endpoint i Linux.
keywords: microsoft, defender, Microsoft Defender för Endpoint, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 21eaf1c0e0d3f61bb5798c8a4de6fe8f97ce4a0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538801"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="d5b40-104">Vad är nytt i Microsoft Defender för Endpoint på Linux</span><span class="sxs-lookup"><span data-stu-id="d5b40-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="d5b40-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="d5b40-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="d5b40-106">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-106">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="d5b40-107">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="d5b40-107">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="d5b40-108">Microsoft Defender för slutpunkt i Linux är nu tillgängligt i förhandsversion för kunder inom myndigheter i USA.</span><span class="sxs-lookup"><span data-stu-id="d5b40-108">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="d5b40-109">Mer information finns i [Microsoft Defender för slutpunkt för kunder inom amerikanska myndigheter.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="d5b40-109">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="d5b40-110">Åtgärdat ett problem där användningen av Microsoft Defender för slutpunkt på Linux på system med IT-filsystem leder till att operativsystemet hänger sig</span><span class="sxs-lookup"><span data-stu-id="d5b40-110">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="d5b40-111">Prestandaförbättringar & andra felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-111">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="d5b40-112">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="d5b40-112">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="d5b40-113">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-113">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="d5b40-114">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="d5b40-114">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="d5b40-115">Prestandaförbättringar för situationer där en hel fästpunkt läggs till i undantagslistan för antivirus.</span><span class="sxs-lookup"><span data-stu-id="d5b40-115">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="d5b40-116">Före den här versionen bearbetades filaktivitet från fästpunkten fortfarande av produkten.</span><span class="sxs-lookup"><span data-stu-id="d5b40-116">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="d5b40-117">Från och med den här versionen utelämnas filaktivitet för undantagna fästpunkter, vilket leder till bättre produktprestanda</span><span class="sxs-lookup"><span data-stu-id="d5b40-117">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="d5b40-118">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="d5b40-118">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="d5b40-119">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="d5b40-119">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="d5b40-120">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-120">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="d5b40-121">101.18.53</span><span class="sxs-lookup"><span data-stu-id="d5b40-121">101.18.53</span></span>

- <span data-ttu-id="d5b40-122">Identifiering och åtgärd på slutpunkt för Linux är nu [tillgängligt i allmänhet](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="d5b40-122">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="d5b40-123">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="d5b40-123">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="d5b40-124">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="d5b40-124">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="d5b40-125">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-125">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="d5b40-126">101.12.99</span><span class="sxs-lookup"><span data-stu-id="d5b40-126">101.12.99</span></span>

- <span data-ttu-id="d5b40-127">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-127">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="d5b40-128">101.04.76</span><span class="sxs-lookup"><span data-stu-id="d5b40-128">101.04.76</span></span>

- <span data-ttu-id="d5b40-129">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-129">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="d5b40-130">101.03.48</span><span class="sxs-lookup"><span data-stu-id="d5b40-130">101.03.48</span></span>

- <span data-ttu-id="d5b40-131">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-131">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="d5b40-132">101.02.55</span><span class="sxs-lookup"><span data-stu-id="d5b40-132">101.02.55</span></span>

- <span data-ttu-id="d5b40-133">Åtgärdat ett problem där produkten ibland inte startar efter en omstart/uppgradering</span><span class="sxs-lookup"><span data-stu-id="d5b40-133">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="d5b40-134">Åtgärdat ett problem där proxyinställningarna inte beständiga under produktuppgraderingar</span><span class="sxs-lookup"><span data-stu-id="d5b40-134">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="d5b40-135">101.00.75</span><span class="sxs-lookup"><span data-stu-id="d5b40-135">101.00.75</span></span>

- <span data-ttu-id="d5b40-136">Lade till stöd för följande filsystemtyper: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` och `vfat`</span><span class="sxs-lookup"><span data-stu-id="d5b40-136">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="d5b40-137">Ny syntax för [kommandoradsverktyget](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="d5b40-137">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="d5b40-138">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-138">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="d5b40-139">100.90.70</span><span class="sxs-lookup"><span data-stu-id="d5b40-139">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="d5b40-140">När du uppgraderar det installerade paketet från en tidigare produktversion än 100.90.70 kan uppdateringen misslyckas på Red Hat-baserade distributions- och SLES-distributioner.</span><span class="sxs-lookup"><span data-stu-id="d5b40-140">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="d5b40-141">Det beror på en stor förändring i en filsökväg.</span><span class="sxs-lookup"><span data-stu-id="d5b40-141">This is because of a major change in a file path.</span></span> <span data-ttu-id="d5b40-142">En tillfällig lösning är att ta bort det äldre paketet och sedan installera det nyare.</span><span class="sxs-lookup"><span data-stu-id="d5b40-142">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="d5b40-143">Det här problemet finns inte i nyare versioner.</span><span class="sxs-lookup"><span data-stu-id="d5b40-143">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="d5b40-144">Undantag [från antivirus har nu stöd för jokertecken](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="d5b40-144">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="d5b40-145">Möjligheten att felsöka [prestandaproblem med](linux-support-perf.md) kommandoradsverktyget `mdatp` har lagts till</span><span class="sxs-lookup"><span data-stu-id="d5b40-145">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="d5b40-146">Förbättringar för att göra paketinstallationen robustare</span><span class="sxs-lookup"><span data-stu-id="d5b40-146">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="d5b40-147">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="d5b40-147">Performance improvements & bug fixes</span></span>
