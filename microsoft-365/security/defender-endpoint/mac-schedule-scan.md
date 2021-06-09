---
title: Schemalägga genomsökningar med Microsoft Defender för Slutpunkt i macOS
description: Lär dig hur du schemalägger en automatisk genomsökningstid för Microsoft Defender för Slutpunkt i macOS för att bättre skydda organisationens tillgångar.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, genomsökningar, antivirus
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
ms.openlocfilehash: a93ea3427c72eb5529715b92cb18d01462493cc6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842860"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="07cdd-104">Schemasökningar med Microsoft Defender för Slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="07cdd-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07cdd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07cdd-105">**Applies to:**</span></span>
- [<span data-ttu-id="07cdd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="07cdd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="07cdd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07cdd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07cdd-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="07cdd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07cdd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="07cdd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="07cdd-110">Du kan starta en sökning med hot när som helst med Microsoft Defender för Endpoint, men ditt företag kan ha nytta av schemalagda eller tidsade genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="07cdd-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="07cdd-111">Du kan till exempel schemalägga en genomsökning så att den körs i början av varje arbetsdag eller vecka.</span><span class="sxs-lookup"><span data-stu-id="07cdd-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="07cdd-112">Schemalägga en genomsökning *med startad*</span><span class="sxs-lookup"><span data-stu-id="07cdd-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="07cdd-113">Du kan skapa ett skanningsschema med det *startad* daemon på en macOS-enhet.</span><span class="sxs-lookup"><span data-stu-id="07cdd-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="07cdd-114">Följande kod visar det schema du behöver använda för att schemalägga en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="07cdd-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="07cdd-115">Öppna en textredigerare och använd det här exemplet som en guide för din egen schemalagda genomsökningsfil.</span><span class="sxs-lookup"><span data-stu-id="07cdd-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="07cdd-116">Mer information om filformatet *.plist* som används här finns i [Listfiler för informationsegenskap](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) på den officiella Apple-utvecklarwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="07cdd-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="07cdd-117">Spara filen som *com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="07cdd-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="07cdd-118">Om du vill köra en fullständig genomsökning i stället för en snabbsökning kan du ändra rad 12, och använda alternativet i stället för (dvs. ) och spara filen som `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* i stället för *com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="07cdd-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="07cdd-119">Öppna **terminalen**.</span><span class="sxs-lookup"><span data-stu-id="07cdd-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="07cdd-120">Ange följande kommandon för att läsa in filen:</span><span class="sxs-lookup"><span data-stu-id="07cdd-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="07cdd-121">Den schemalagda genomsökningen kommer att köras vid det datum, den tid och den frekvens som du har definierat i p-listan.</span><span class="sxs-lookup"><span data-stu-id="07cdd-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="07cdd-122">I exemplet körs skanningen vid 02:00 varje fredag.</span><span class="sxs-lookup"><span data-stu-id="07cdd-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="07cdd-123">Värdet `Weekday` för använder ett `StartCalendarInterval` heltal för att ange den femte dagen i veckan eller fredag.</span><span class="sxs-lookup"><span data-stu-id="07cdd-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="07cdd-124">Agenter som körs med *lansering körs* inte vid den schemalagda tiden medan enheten är i viloläge.</span><span class="sxs-lookup"><span data-stu-id="07cdd-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="07cdd-125">De körs i stället när enheten återgår till viloläge.</span><span class="sxs-lookup"><span data-stu-id="07cdd-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="07cdd-126">Om enheten är avstängd körs skanningen vid nästa schemalagda genomsökningstid.</span><span class="sxs-lookup"><span data-stu-id="07cdd-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="07cdd-127">Schemalägga en genomsökning med Intune</span><span class="sxs-lookup"><span data-stu-id="07cdd-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="07cdd-128">Du kan också schemalägga skanningar med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="07cdd-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="07cdd-129">Den [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) skript som finns i Skript för [Microsoft Defender](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) för Slutpunkt finns kvar när enheten återgår från viloläge.</span><span class="sxs-lookup"><span data-stu-id="07cdd-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="07cdd-130">Mer detaljerade anvisningar om hur du använder det här skriptet i ditt företag finns i Använda skript på macOS-enheter i [Intune.](/mem/intune/apps/macos-shell-scripts)</span><span class="sxs-lookup"><span data-stu-id="07cdd-130">See [Use shell scripts on macOS devices in Intune](/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
