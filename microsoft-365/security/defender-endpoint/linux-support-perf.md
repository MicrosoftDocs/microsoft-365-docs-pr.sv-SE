---
title: Felsöka prestandaproblem för Microsoft Defender för Endpoint i Linux
description: Felsöka prestandaproblem i Microsoft Defender för Slutpunkt i Linux.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, prestanda
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 998d8c500613ffa9fc6d790535e555ff9503f590
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281023"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="1d20c-104">Felsöka prestandaproblem för Microsoft Defender för Endpoint i Linux</span><span class="sxs-lookup"><span data-stu-id="1d20c-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d20c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1d20c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d20c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d20c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d20c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d20c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="1d20c-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1d20c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1d20c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1d20c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1d20c-110">Den här artikeln innehåller några allmänna steg som kan användas för att begränsa prestandaproblem relaterade till Defender för Slutpunkt på Linux.</span><span class="sxs-lookup"><span data-stu-id="1d20c-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="1d20c-111">Realtidsskydd (RTP) är en funktion i Defender för Endpoint på Linux som kontinuerligt övervakar och skyddar din enhet mot hot.</span><span class="sxs-lookup"><span data-stu-id="1d20c-111">Real-time protection (RTP) is a feature of Defender for Endpoint on Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="1d20c-112">Den består av fil- och processövervakning och annan heuristics.</span><span class="sxs-lookup"><span data-stu-id="1d20c-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="1d20c-113">Beroende på vilka program du kör och enhetens egenskaper kan du uppleva underoptimal prestanda när du kör Defender för Endpoint på Linux.</span><span class="sxs-lookup"><span data-stu-id="1d20c-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint on Linux.</span></span> <span data-ttu-id="1d20c-114">Särskilt program eller systemprocesser som har tillgång till många resurser under ett kort tidspann kan leda till prestandaproblem i Defender för Endpoint på Linux.</span><span class="sxs-lookup"><span data-stu-id="1d20c-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="1d20c-115">Kontrollera att **andra säkerhetsprodukter inte körs på** enheten innan du startar.</span><span class="sxs-lookup"><span data-stu-id="1d20c-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="1d20c-116">Flera säkerhetsprodukter kan vara i konflikt med och påverka värdprestandan.</span><span class="sxs-lookup"><span data-stu-id="1d20c-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="1d20c-117">Följande steg kan användas för att felsöka och minimera dessa problem:</span><span class="sxs-lookup"><span data-stu-id="1d20c-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="1d20c-118">Inaktivera realtidsskyddet med någon av följande metoder och se om prestandan förbättras.</span><span class="sxs-lookup"><span data-stu-id="1d20c-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="1d20c-119">Den här metoden begränsar huruvida Defender för Endpoint på Linux bidrar till prestandaproblemen.</span><span class="sxs-lookup"><span data-stu-id="1d20c-119">This approach helps narrow down whether Defender for Endpoint on Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="1d20c-120">Om din enhet inte hanteras av din organisation kan realtidsskydd inaktiveras från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="1d20c-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="1d20c-121">Om din enhet hanteras av din organisation kan realtidsskydd inaktiveras av administratören genom att följa anvisningarna i Ange inställningar för Defender för [slutpunkt i Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="1d20c-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="1d20c-122">Om prestandaproblemet kvarstår när realtidsskyddet är inaktiverat kan problemets ursprung vara den identifiering och åtgärd på slutpunkt komponenten.</span><span class="sxs-lookup"><span data-stu-id="1d20c-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="1d20c-123">I så fall kan du kontakta kundsupport för ytterligare instruktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1d20c-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="1d20c-124">Du kan använda statistik i realtid som har samlats av Defender för Endpoint på Linux för att hitta de program som utlöser flest genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="1d20c-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d20c-125">Den här funktionen är tillgänglig i version 100.90.70 eller senare.</span><span class="sxs-lookup"><span data-stu-id="1d20c-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="1d20c-126">Den här funktionen är aktiverad som standard för `Dogfood` alla `InsiderFast` kanaler och.</span><span class="sxs-lookup"><span data-stu-id="1d20c-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="1d20c-127">Om du använder en annan uppdateringskanal kan den här funktionen aktiveras från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="1d20c-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="1d20c-128">Den här funktionen kräver realtidsskydd för att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="1d20c-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="1d20c-129">Om du vill kontrollera statusen för realtidsskyddet kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1d20c-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="1d20c-130">Kontrollera att `real_time_protection_enabled` posten är `true` .</span><span class="sxs-lookup"><span data-stu-id="1d20c-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="1d20c-131">Annars kör du följande kommando för att aktivera det:</span><span class="sxs-lookup"><span data-stu-id="1d20c-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="1d20c-132">Om du vill samla in aktuell statistik kör du:</span><span class="sxs-lookup"><span data-stu-id="1d20c-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="1d20c-133">Om ```--output json``` du använder (observera det dubbla strecket) ser du till att utdataformatet är klart för tolkning.</span><span class="sxs-lookup"><span data-stu-id="1d20c-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="1d20c-134">Utdata från det här kommandot visar alla processer och deras associerade genomsökningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="1d20c-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="1d20c-135">Ladda ned ett exempel på Python-parser high_cpu_parser.py på ditt **Linux-system** med kommandot:</span><span class="sxs-lookup"><span data-stu-id="1d20c-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="1d20c-136">Utdata för det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="1d20c-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="1d20c-137">Skriv sedan följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="1d20c-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="1d20c-138">Utdata från ovanstående är en lista över de mest deltagare som har prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="1d20c-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="1d20c-139">Den första kolumnen är PID (processidentifierare), den andra är namnet på processen och den sista kolumnen är antalet skannade filer, sorterade efter påverkan.</span><span class="sxs-lookup"><span data-stu-id="1d20c-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="1d20c-140">Till exempel ser utdata för kommandot ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="1d20c-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="1d20c-141">Om du vill förbättra prestandan för Defender för Endpoint i Linux letar du reda på den som har det högsta talet under raden och lägger `Total files scanned` till ett undantag för det.</span><span class="sxs-lookup"><span data-stu-id="1d20c-141">To improve the performance of Defender for Endpoint on Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="1d20c-142">Mer information finns i [Konfigurera och validera undantag för Defender för Endpoint på Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="1d20c-142">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="1d20c-143">Programmet lagrar statistik i minnet och håller bara reda på filaktiviteten sedan den startades och realtidsskyddet aktiverades.</span><span class="sxs-lookup"><span data-stu-id="1d20c-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="1d20c-144">Processer som startats tidigare eller under perioder där realtidsskydd var inaktiverat räknas inte.</span><span class="sxs-lookup"><span data-stu-id="1d20c-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="1d20c-145">Dessutom räknas bara händelser som utlöste genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="1d20c-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="1d20c-146">Konfigurera Microsoft Defender för slutpunkt på Linux med undantag för de processer eller diskutrymmen som bidrar till prestandaproblemen och återaktivera realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="1d20c-146">Configure Microsoft Defender for Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="1d20c-147">Mer information finns i [Konfigurera och validera undantag för Microsoft Defender för Endpoint på Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="1d20c-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d20c-148">Se även</span><span class="sxs-lookup"><span data-stu-id="1d20c-148">See also</span></span>
- [<span data-ttu-id="1d20c-149">Undersöka problem med agenthälsa</span><span class="sxs-lookup"><span data-stu-id="1d20c-149">Investigate agent health issues</span></span>](health-status.md)