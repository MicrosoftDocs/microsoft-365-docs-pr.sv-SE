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
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651134"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b96a1-104">Vad är nytt i Microsoft Defender för Endpoint på Linux</span><span class="sxs-lookup"><span data-stu-id="b96a1-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="b96a1-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="b96a1-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="b96a1-106">Från och med den här versionen kommer hot som upptäckts under sökning på begäran av antivirus som utlöses via kommandoradsklienten att åtgärdas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b96a1-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="b96a1-107">Hot som upptäckts vid genomsökningar som utlösts via användargränssnittet kräver fortfarande manuell åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b96a1-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="b96a1-108">`mdatp diagnostic real-time-protection-statistics` stöder nu ytterligare två växlar:</span><span class="sxs-lookup"><span data-stu-id="b96a1-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="b96a1-109">`--sort`: Sorterar resultatet fallande efter totalt antal genomsökta filer</span><span class="sxs-lookup"><span data-stu-id="b96a1-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="b96a1-110">`--top N`: visar de översta N-resultaten (fungerar bara om `--sort` anges också)</span><span class="sxs-lookup"><span data-stu-id="b96a1-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="b96a1-111">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="b96a1-112">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="b96a1-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="b96a1-113">Microsoft Defender för slutpunkt i Linux är nu tillgängligt i förhandsversion för kunder inom myndigheter i USA.</span><span class="sxs-lookup"><span data-stu-id="b96a1-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="b96a1-114">Mer information finns i [Microsoft Defender för slutpunkt för kunder inom amerikanska myndigheter.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="b96a1-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="b96a1-115">Åtgärdat ett problem där användningen av Microsoft Defender för slutpunkt på Linux på system med IT-filsystem leder till att operativsystemet hänger sig</span><span class="sxs-lookup"><span data-stu-id="b96a1-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="b96a1-116">Prestandaförbättringar & andra felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="b96a1-117">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="b96a1-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="b96a1-118">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="b96a1-119">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="b96a1-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="b96a1-120">Prestandaförbättringar för situationer där en hel fästpunkt läggs till i undantagslistan för antivirus.</span><span class="sxs-lookup"><span data-stu-id="b96a1-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="b96a1-121">Före den här versionen bearbetades filaktivitet från fästpunkten fortfarande av produkten.</span><span class="sxs-lookup"><span data-stu-id="b96a1-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="b96a1-122">Från och med den här versionen utelämnas filaktivitet för undantagna fästpunkter, vilket leder till bättre produktprestanda</span><span class="sxs-lookup"><span data-stu-id="b96a1-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="b96a1-123">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="b96a1-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="b96a1-124">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="b96a1-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="b96a1-125">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="b96a1-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="b96a1-126">101.18.53</span></span>

- <span data-ttu-id="b96a1-127">Identifiering och åtgärd på slutpunkt för Linux är nu [tillgängligt i allmänhet](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="b96a1-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="b96a1-128">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="b96a1-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="b96a1-129">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="b96a1-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="b96a1-130">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="b96a1-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="b96a1-131">101.12.99</span></span>

- <span data-ttu-id="b96a1-132">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="b96a1-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="b96a1-133">101.04.76</span></span>

- <span data-ttu-id="b96a1-134">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="b96a1-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="b96a1-135">101.03.48</span></span>

- <span data-ttu-id="b96a1-136">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="b96a1-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="b96a1-137">101.02.55</span></span>

- <span data-ttu-id="b96a1-138">Åtgärdat ett problem där produkten ibland inte startar efter en omstart/uppgradering</span><span class="sxs-lookup"><span data-stu-id="b96a1-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="b96a1-139">Åtgärdat ett problem där proxyinställningarna inte beständiga under produktuppgraderingar</span><span class="sxs-lookup"><span data-stu-id="b96a1-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="b96a1-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="b96a1-140">101.00.75</span></span>

- <span data-ttu-id="b96a1-141">Lade till stöd för följande filsystemtyper: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` och `vfat`</span><span class="sxs-lookup"><span data-stu-id="b96a1-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="b96a1-142">Ny syntax för [kommandoradsverktyget](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="b96a1-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="b96a1-143">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="b96a1-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="b96a1-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="b96a1-145">När du uppgraderar det installerade paketet från en tidigare produktversion än 100.90.70 kan uppdateringen misslyckas på Red Hat-baserade distributions- och SLES-distributioner.</span><span class="sxs-lookup"><span data-stu-id="b96a1-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="b96a1-146">Det beror på en stor förändring i en filsökväg.</span><span class="sxs-lookup"><span data-stu-id="b96a1-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="b96a1-147">En tillfällig lösning är att ta bort det äldre paketet och sedan installera det nyare.</span><span class="sxs-lookup"><span data-stu-id="b96a1-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="b96a1-148">Det här problemet finns inte i nyare versioner.</span><span class="sxs-lookup"><span data-stu-id="b96a1-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="b96a1-149">Undantag [från antivirus har nu stöd för jokertecken](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="b96a1-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="b96a1-150">Möjligheten att felsöka [prestandaproblem med](linux-support-perf.md) kommandoradsverktyget `mdatp` har lagts till</span><span class="sxs-lookup"><span data-stu-id="b96a1-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="b96a1-151">Förbättringar för att göra paketinstallationen robustare</span><span class="sxs-lookup"><span data-stu-id="b96a1-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="b96a1-152">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="b96a1-152">Performance improvements & bug fixes</span></span>
