---
title: Felsöka prestandaproblem för Microsoft Defender för slutpunkt i macOS
description: Felsöka prestandaproblem i Microsoft Defender för slutpunkt i macOS.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, prestanda
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4ebb360bc606845bfd3f80f31082c836b896477
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694263"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ceedb-104">Felsöka prestandaproblem för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="ceedb-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ceedb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ceedb-105">**Applies to:**</span></span>

- [<span data-ttu-id="ceedb-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="ceedb-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="ceedb-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ceedb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ceedb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceedb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ceedb-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ceedb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ceedb-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ceedb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ceedb-111">Det här avsnittet innehåller några allmänna steg som kan användas för att begränsa prestandaproblem som rör Microsoft Defender för slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="ceedb-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="ceedb-112">Realtidsskydd (RTP) är en funktion i Microsoft Defender för Endpoint på macOS som kontinuerligt övervakar och skyddar din enhet mot hot.</span><span class="sxs-lookup"><span data-stu-id="ceedb-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="ceedb-113">Den består av fil- och processövervakning och annan heuristics.</span><span class="sxs-lookup"><span data-stu-id="ceedb-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="ceedb-114">Beroende på vilka program du kör och enhetens egenskaper kan du uppleva underoptimal prestanda när du kör Microsoft Defender för Endpoint på macOS.</span><span class="sxs-lookup"><span data-stu-id="ceedb-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="ceedb-115">Särskilt program eller systemprocesser som har åtkomst till många resurser under ett kort tidspann kan leda till prestandaproblem i Microsoft Defender för slutpunkten i macOS.</span><span class="sxs-lookup"><span data-stu-id="ceedb-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="ceedb-116">Följande steg kan användas för att felsöka och minimera dessa problem:</span><span class="sxs-lookup"><span data-stu-id="ceedb-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="ceedb-117">Inaktivera realtidsskyddet med någon av följande metoder och se om prestandan förbättras.</span><span class="sxs-lookup"><span data-stu-id="ceedb-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="ceedb-118">Den här metoden begränsar om Microsoft Defender för Slutpunkt på macOS bidrar till prestandaproblemen.</span><span class="sxs-lookup"><span data-stu-id="ceedb-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="ceedb-119">Om din enhet inte hanteras av din organisation kan realtidsskydd inaktiveras med något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="ceedb-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="ceedb-120">Från användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="ceedb-120">From the user interface.</span></span> <span data-ttu-id="ceedb-121">Öppna Microsoft Defender för slutpunkt i macOS och gå till **Hantera inställningar.**</span><span class="sxs-lookup"><span data-stu-id="ceedb-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![Skärmbild på Hantera realtidsskydd](images/mdatp-36-rtp.png)

    - <span data-ttu-id="ceedb-123">Från terminalen.</span><span class="sxs-lookup"><span data-stu-id="ceedb-123">From the Terminal.</span></span> <span data-ttu-id="ceedb-124">Av säkerhetsskäl kräver den här åtgärden höjd.</span><span class="sxs-lookup"><span data-stu-id="ceedb-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="ceedb-125">Om enheten hanteras av din organisation kan realtidsskydd inaktiveras av administratören genom att följa anvisningarna i Ange inställningar för Microsoft Defender för [slutpunkt i macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="ceedb-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="ceedb-126">Om prestandaproblemet kvarstår när realtidsskyddet är inaktiverat kan problemets ursprung vara den identifiering och åtgärd på slutpunkt komponenten.</span><span class="sxs-lookup"><span data-stu-id="ceedb-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="ceedb-127">I så fall kan du kontakta kundsupport för ytterligare instruktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ceedb-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="ceedb-128">Öppna Finder och gå **till**  >  **Programverktyg.**</span><span class="sxs-lookup"><span data-stu-id="ceedb-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="ceedb-129">Öppna **Aktivitetsrapporter** och analysera vilka program som använder resurserna på ditt system.</span><span class="sxs-lookup"><span data-stu-id="ceedb-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="ceedb-130">Vanliga exempel är programuppdateringsprogram och kompilatorer.</span><span class="sxs-lookup"><span data-stu-id="ceedb-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="ceedb-131">Om du vill hitta de program som utlöser flest genomsökningar kan du använda statistik i realtid som har samlats av Defender för Slutpunkt på Mac.</span><span class="sxs-lookup"><span data-stu-id="ceedb-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="ceedb-132">Den här funktionen är tillgänglig i version 100.90.70 eller senare.</span><span class="sxs-lookup"><span data-stu-id="ceedb-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="ceedb-133">Den här funktionen är aktiverad som standard på **Dogpat-** **och InsiderFast-kanalerna.**</span><span class="sxs-lookup"><span data-stu-id="ceedb-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="ceedb-134">Om du använder en annan uppdateringskanal kan den här funktionen aktiveras från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="ceedb-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="ceedb-135">Den här funktionen kräver realtidsskydd för att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="ceedb-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="ceedb-136">Om du vill kontrollera statusen för realtidsskyddet kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ceedb-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="ceedb-137">Kontrollera att **real_time_protection_enabled** stämmer.</span><span class="sxs-lookup"><span data-stu-id="ceedb-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="ceedb-138">Annars kör du följande kommando för att aktivera det:</span><span class="sxs-lookup"><span data-stu-id="ceedb-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="ceedb-139">Om du vill samla in aktuell statistik kör du:</span><span class="sxs-lookup"><span data-stu-id="ceedb-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > <span data-ttu-id="ceedb-140">Med **hjälp av --output-json** (observera det dubbla strecket) ser du till att utdataformatet är klart för tolkning.</span><span class="sxs-lookup"><span data-stu-id="ceedb-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="ceedb-141">Utdata från det här kommandot visar alla processer och deras associerade genomsökningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="ceedb-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="ceedb-142">Ladda ned exemplet Python-parser på Mac-systemet high_cpu_parser.py med kommandot:</span><span class="sxs-lookup"><span data-stu-id="ceedb-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="ceedb-143">Utdata för det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="ceedb-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="ceedb-144">Skriv sedan följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="ceedb-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="ceedb-145">Utdata från ovanstående är en lista över de mest deltagare som har prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="ceedb-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="ceedb-146">Den första kolumnen är PID (processidentifierare), den andra är namnet på processen och den sista kolumnen är antalet skannade filer, sorterade efter påverkan.</span><span class="sxs-lookup"><span data-stu-id="ceedb-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="ceedb-147">Till exempel ser utdata för kommandot ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="ceedb-147">For example, the output of the command will be something like the below:</span></span>

      ```output
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

      <span data-ttu-id="ceedb-148">Om du vill förbättra prestandan för Defender för slutpunkt på Mac letar du reda på den med det högsta numret under raden Totalt antal genomsökta filer och lägger till ett undantag för det.</span><span class="sxs-lookup"><span data-stu-id="ceedb-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="ceedb-149">Mer information finns i [Konfigurera och validera undantag för Defender för Endpoint på Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="ceedb-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="ceedb-150">Programmet lagrar statistik i minnet och håller bara reda på filaktiviteten sedan den startades och realtidsskyddet aktiverades.</span><span class="sxs-lookup"><span data-stu-id="ceedb-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="ceedb-151">Processer som startats tidigare eller under perioder där realtidsskydd var inaktiverat räknas inte.</span><span class="sxs-lookup"><span data-stu-id="ceedb-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="ceedb-152">Dessutom räknas bara händelser som utlöste genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="ceedb-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="ceedb-153">Konfigurera Microsoft Defender för slutpunkt på macOS med undantag för de processer eller diskutrymmen som bidrar till prestandaproblemen och återaktivera realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="ceedb-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="ceedb-154">Mer [information finns i Konfigurera och validera undantag för Microsoft Defender för slutpunkt på macOS.](mac-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="ceedb-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
