---
title: Använda kommandoraden för att hantera Microsoft Defender Antivirus
description: Kör Microsoft Defender Antivirus genomsökningar och konfigurera nästa generations skydd med ett dedikerat kommandoradsverktyg.
keywords: kör windows defender scan, kör antivirussökning från kommandoraden, kör windows defender scan från kommandoraden, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538909"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="7bcef-104">Konfigurera och Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="7bcef-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="7bcef-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7bcef-105">**Applies to:**</span></span>

- [<span data-ttu-id="7bcef-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7bcef-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7bcef-107">Du kan utföra Microsoft Defender Antivirus olika funktioner med det dedikerade kommandoradsverktyget **mpcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="7bcef-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="7bcef-108">Det här verktyget är användbart när du vill automatisera Microsoft Defender Antivirus använda.</span><span class="sxs-lookup"><span data-stu-id="7bcef-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="7bcef-109">Du hittar verktyget i `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="7bcef-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="7bcef-110">Du måste köra den från en kommandotolk.</span><span class="sxs-lookup"><span data-stu-id="7bcef-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="7bcef-111">Du kan behöva öppna en version på administratörsnivå av kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="7bcef-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="7bcef-112">När du söker efter **Kommandotolken** på Start-menyn väljer du **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="7bcef-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="7bcef-113">Om du kör en uppdaterad version av Microsoft Defender-plattformen körs `**MpCmdRun**` du från följande plats: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .</span><span class="sxs-lookup"><span data-stu-id="7bcef-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="7bcef-114">Mer information om program mot skadlig programvara finns Microsoft Defender Antivirus [uppdateringar och baslinjer.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7bcef-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="7bcef-115">Verktyget MpCmdRun använder följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7bcef-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="7bcef-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="7bcef-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="7bcef-117">Kommando</span><span class="sxs-lookup"><span data-stu-id="7bcef-117">Command</span></span>  | <span data-ttu-id="7bcef-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7bcef-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="7bcef-119">`-?`**eller**`-h`</span><span class="sxs-lookup"><span data-stu-id="7bcef-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="7bcef-120">Visar alla tillgängliga alternativ för det här verktyget</span><span class="sxs-lookup"><span data-stu-id="7bcef-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="7bcef-121">Söker efter skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7bcef-121">Scans for malicious software.</span></span> <span data-ttu-id="7bcef-122">Värdena för **ScanType** är:</span><span class="sxs-lookup"><span data-stu-id="7bcef-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="7bcef-123">**0** Standard, enligt din konfiguration</span><span class="sxs-lookup"><span data-stu-id="7bcef-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="7bcef-124">**-1** Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="7bcef-124">**-1** Quick scan</span></span><p><span data-ttu-id="7bcef-125">**-2** Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="7bcef-125">**-2** Full scan</span></span><p><span data-ttu-id="7bcef-126">**-3** Anpassad fil- och katalogsökning.</span><span class="sxs-lookup"><span data-stu-id="7bcef-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="7bcef-127">CpuThrottling respekterar den konfigurerade CPU-begränsningen från principen</span><span class="sxs-lookup"><span data-stu-id="7bcef-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="7bcef-128">Startar diagnostikspårning</span><span class="sxs-lookup"><span data-stu-id="7bcef-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="7bcef-129">Samlar in supportinformation.</span><span class="sxs-lookup"><span data-stu-id="7bcef-129">Collects support information.</span></span> <span data-ttu-id="7bcef-130">Se " insamling[av diagnostikdata](collect-diagnostic-data.md)"</span><span class="sxs-lookup"><span data-stu-id="7bcef-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="7bcef-131">Samma som `-GetFiles` , men matas ut till mappen Temporary DiagTrack</span><span class="sxs-lookup"><span data-stu-id="7bcef-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="7bcef-132">Återställer den installerade säkerhetsintelligensen till en tidigare säkerhetskopia eller till den ursprungliga standarduppsättningen</span><span class="sxs-lookup"><span data-stu-id="7bcef-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="7bcef-133">Tar bara bort den dynamiskt hämtade säkerhetsintelligensen</span><span class="sxs-lookup"><span data-stu-id="7bcef-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="7bcef-134">Återställer den tidigare installerade motorn</span><span class="sxs-lookup"><span data-stu-id="7bcef-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="7bcef-135">Söker efter nya säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7bcef-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="7bcef-136">Återställer eller visar objekt i karantän</span><span class="sxs-lookup"><span data-stu-id="7bcef-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="7bcef-137">Läser in dynamisk säkerhetsintelligens</span><span class="sxs-lookup"><span data-stu-id="7bcef-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="7bcef-138">Visar den inlästa dynamiska säkerhetsintelligensen</span><span class="sxs-lookup"><span data-stu-id="7bcef-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="7bcef-139">Tar bort dynamisk säkerhetsinformation</span><span class="sxs-lookup"><span data-stu-id="7bcef-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="7bcef-140">Kontrollerar om en sökväg är utesluten</span><span class="sxs-lookup"><span data-stu-id="7bcef-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="7bcef-141">Verifierar att nätverket kan kommunicera Microsoft Defender Antivirus molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="7bcef-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="7bcef-142">Det här kommandot fungerar bara i Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="7bcef-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="7bcef-143">Vanliga fel när du kör kommandon via mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="7bcef-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="7bcef-144">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="7bcef-144">Error message</span></span> | <span data-ttu-id="7bcef-145">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="7bcef-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="7bcef-146">Tjänsten Microsoft Defender Antivirus inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="7bcef-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="7bcef-147">Aktivera tjänsten och försök igen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="7bcef-148">**Obs!**  I Windows 10 1909 eller äldre, och Windows Server 2019 eller äldre, kallades tjänsten *för Windows Defender Antivirus* tjänst.</span><span class="sxs-lookup"><span data-stu-id="7bcef-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="7bcef-149">Du kör kommandot från `-ValidateMapsConnection` en dator som är Windows 10 version 1607 eller äldre, eller från Windows Server 2016 eller äldre.</span><span class="sxs-lookup"><span data-stu-id="7bcef-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="7bcef-150">Kör kommandot från en dator Windows 10 version 1703 eller senare, eller från Windows 2019 eller senare.</span><span class="sxs-lookup"><span data-stu-id="7bcef-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="7bcef-151">Verktyget måste köras från antingen: eller `%ProgramFiles%\Windows Defender` (om plattformsuppdateringarna är olika varje `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` månad, förutom i mars)</span><span class="sxs-lookup"><span data-stu-id="7bcef-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="7bcef-152">Inte tillräckligt med behörigheter.</span><span class="sxs-lookup"><span data-stu-id="7bcef-152">Not enough privileges.</span></span> <span data-ttu-id="7bcef-153">Använd kommandotolken (cmd.exe) som administratör.</span><span class="sxs-lookup"><span data-stu-id="7bcef-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="7bcef-154">Brandväggen blockerar anslutningen eller utför SSL-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="7bcef-155">Möjliga nätverksrelaterade problem, som problem med namnmatchning</span><span class="sxs-lookup"><span data-stu-id="7bcef-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="7bcef-156">Brandväggen blockerar anslutningen eller utför SSL-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="7bcef-157">Brandväggen blockerar anslutningen eller utför SSL-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="7bcef-158">Brandväggen blockerar anslutningen eller utför SSL-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7bcef-159">Se även</span><span class="sxs-lookup"><span data-stu-id="7bcef-159">See also</span></span>

- [<span data-ttu-id="7bcef-160">Konfigurera funktionerna i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7bcef-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="7bcef-161">Hantera Microsoft Defender Antivirus i företaget</span><span class="sxs-lookup"><span data-stu-id="7bcef-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7bcef-162">Referensavsnitt om hanterings- och konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="7bcef-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7bcef-163">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="7bcef-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)