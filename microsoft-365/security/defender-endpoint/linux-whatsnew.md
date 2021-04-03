---
title: Vad är nytt i Microsoft Defender för Endpoint för Linux
description: Lista över större ändringar för Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581008"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4ae80-104">Vad är nytt i Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="4ae80-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="4ae80-105">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="4ae80-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="4ae80-106">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="4ae80-107">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="4ae80-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="4ae80-108">Prestandaförbättringar för situationer där en hel fästpunkt läggs till i undantagslistan för antivirus.</span><span class="sxs-lookup"><span data-stu-id="4ae80-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="4ae80-109">Före den här versionen bearbetades filaktivitet från fästpunkten fortfarande av produkten.</span><span class="sxs-lookup"><span data-stu-id="4ae80-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="4ae80-110">Från och med den här versionen utelämnas filaktivitet för undantagna fästpunkter, vilket leder till bättre produktprestanda</span><span class="sxs-lookup"><span data-stu-id="4ae80-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="4ae80-111">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="4ae80-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="4ae80-112">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="4ae80-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="4ae80-113">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="4ae80-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="4ae80-114">101.18.53</span></span>

- <span data-ttu-id="4ae80-115">EDR för Linux är nu [tillgängligt i allmänhet](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="4ae80-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="4ae80-116">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="4ae80-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="4ae80-117">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="4ae80-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="4ae80-118">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="4ae80-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="4ae80-119">101.12.99</span></span>

- <span data-ttu-id="4ae80-120">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="4ae80-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="4ae80-121">101.04.76</span></span>

- <span data-ttu-id="4ae80-122">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="4ae80-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="4ae80-123">101.03.48</span></span>

- <span data-ttu-id="4ae80-124">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="4ae80-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="4ae80-125">101.02.55</span></span>

- <span data-ttu-id="4ae80-126">Åtgärdat ett problem där produkten ibland inte startar efter en omstart/uppgradering</span><span class="sxs-lookup"><span data-stu-id="4ae80-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="4ae80-127">Åtgärdat ett problem där proxyinställningarna inte beständiga under produktuppgraderingar</span><span class="sxs-lookup"><span data-stu-id="4ae80-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="4ae80-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="4ae80-128">101.00.75</span></span>

- <span data-ttu-id="4ae80-129">Lade till stöd för följande filsystemtyper: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` och `vfat`</span><span class="sxs-lookup"><span data-stu-id="4ae80-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="4ae80-130">Ny syntax för [kommandoradsverktyget](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="4ae80-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="4ae80-131">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="4ae80-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="4ae80-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="4ae80-133">När du uppgraderar det installerade paketet från en tidigare produktversion än 100.90.70 kan uppdateringen misslyckas på Red Hat-baserade distributions- och SLES-distributioner.</span><span class="sxs-lookup"><span data-stu-id="4ae80-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="4ae80-134">Det beror på en stor förändring i en filsökväg.</span><span class="sxs-lookup"><span data-stu-id="4ae80-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="4ae80-135">En tillfällig lösning är att ta bort det äldre paketet och sedan installera det nyare.</span><span class="sxs-lookup"><span data-stu-id="4ae80-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="4ae80-136">Det här problemet finns inte i nyare versioner.</span><span class="sxs-lookup"><span data-stu-id="4ae80-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="4ae80-137">Undantag [från antivirus har nu stöd för jokertecken](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="4ae80-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="4ae80-138">Möjligheten att felsöka [prestandaproblem med](linux-support-perf.md) kommandoradsverktyget `mdatp` har lagts till</span><span class="sxs-lookup"><span data-stu-id="4ae80-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="4ae80-139">Förbättringar för att göra paketinstallationen robustare</span><span class="sxs-lookup"><span data-stu-id="4ae80-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="4ae80-140">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="4ae80-140">Performance improvements & bug fixes</span></span>
