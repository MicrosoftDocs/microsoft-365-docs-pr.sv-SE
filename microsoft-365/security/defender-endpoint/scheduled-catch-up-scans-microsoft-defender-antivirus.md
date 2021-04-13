---
title: Schemalägg vanliga snabba och fullständiga genomsökningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691304"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="fa677-104">Konfigurera schemalagda snabba eller fullständiga genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa677-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fa677-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fa677-105">**Applies to:**</span></span>

- [<span data-ttu-id="fa677-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fa677-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="fa677-107">Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter innan eventuella schemalagda genomsökningar görs.</span><span class="sxs-lookup"><span data-stu-id="fa677-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="fa677-108">Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="fa677-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="fa677-109">Förutom att alltid ha realtidsskydd och genomsökningar [på](run-scan-microsoft-defender-antivirus.md) begäran kan du också konfigurera regelbundna, schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="fa677-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="fa677-110">Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller om slutpunkten används.</span><span class="sxs-lookup"><span data-stu-id="fa677-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="fa677-111">Du kan också ange när särskilda genomsökningar ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="fa677-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="fa677-112">I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med Grupprincip, PowerShell-cmdlets och WMI.</span><span class="sxs-lookup"><span data-stu-id="fa677-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="fa677-113">Du kan också konfigurera genomsökningar av scheman med [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) eller Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="fa677-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="fa677-114">Så här konfigurerar du grupprincipinställningarna som beskrivs i den här artikeln</span><span class="sxs-lookup"><span data-stu-id="fa677-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="fa677-115">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="fa677-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="fa677-116">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="fa677-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="fa677-117">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="fa677-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="fa677-118">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus** och sedan den **plats** som anges i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="fa677-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="fa677-119">Dubbelklicka på den **principinställning** som anges i tabellen nedan och ange önskat alternativ.</span><span class="sxs-lookup"><span data-stu-id="fa677-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="fa677-120">Klicka **på OK** och upprepa för alla andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="fa677-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="fa677-121">Läs även Hantera [när skyddsuppdateringar ska laddas ned och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) och Förhindra eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fa677-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="fa677-122">Snabbsökning kontra fullständig sökning och anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="fa677-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="fa677-123">När du ställer in schemalagda genomsökningar kan du ställa in om skanningen ska vara en fullständig eller snabb genomsökning.</span><span class="sxs-lookup"><span data-stu-id="fa677-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="fa677-124">Med snabbsökningar kan du se alla platser där skadlig programvara registrerats, till exempel registernycklar och kända startmappar i Windows.</span><span class="sxs-lookup"><span data-stu-id="fa677-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="fa677-125">I kombination med ständigt realtidsskydd [–](configure-real-time-protection-microsoft-defender-antivirus.md) som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp – ger en snabb genomsökning stark täckning både för skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fa677-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="fa677-126">I de flesta fall innebär det att en snabb genomsökning är lämplig för att hitta skadlig programvara som inte hämtades med realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="fa677-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="fa677-127">En fullständig genomsökning kan vara användbar på slutpunkter som har stött på ett hot mot skadlig programvara för att identifiera om det finns inaktiva komponenter som kräver en mer omfattande rensning.</span><span class="sxs-lookup"><span data-stu-id="fa677-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="fa677-128">I den här instansen kanske du vill använda en fullständig genomsökning när du kör [en sökning på begäran.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fa677-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="fa677-129">Med en anpassad genomsökning kan du ange vilka filer och mappar som ska skannas, till exempel en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="fa677-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="fa677-130">Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="fa677-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="fa677-131">Konfigurera schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa677-131">Set up scheduled scans</span></span>

<span data-ttu-id="fa677-132">Schemalagda genomsökningar körs på den dag och den tid du anger.</span><span class="sxs-lookup"><span data-stu-id="fa677-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="fa677-133">Du kan använda Grupprincip, PowerShell och WMI för att konfigurera schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="fa677-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="fa677-134">Om en dator är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, som innebär att skanningen har stoppats innan den slutförts.</span><span class="sxs-lookup"><span data-stu-id="fa677-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="fa677-135">Microsoft Defender Antivirus kör en fullständig genomsökning vid nästa schemalagda tid.</span><span class="sxs-lookup"><span data-stu-id="fa677-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="fa677-136">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="fa677-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="fa677-137">Plats</span><span class="sxs-lookup"><span data-stu-id="fa677-137">Location</span></span> | <span data-ttu-id="fa677-138">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa677-138">Setting</span></span> | <span data-ttu-id="fa677-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa677-139">Description</span></span> | <span data-ttu-id="fa677-140">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa677-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa677-141">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-141">Scan</span></span> | <span data-ttu-id="fa677-142">Ange vilken skanningstyp som ska användas för en schemalagd sökning</span><span class="sxs-lookup"><span data-stu-id="fa677-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="fa677-143">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa677-143">Quick scan</span></span> |
|<span data-ttu-id="fa677-144">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-144">Scan</span></span> | <span data-ttu-id="fa677-145">Ange veckodagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa677-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="fa677-146">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="fa677-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="fa677-147">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa677-147">Never</span></span> |
|<span data-ttu-id="fa677-148">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-148">Scan</span></span> | <span data-ttu-id="fa677-149">Ange tid på dagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa677-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="fa677-150">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00).</span><span class="sxs-lookup"><span data-stu-id="fa677-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="fa677-151">02:00</span><span class="sxs-lookup"><span data-stu-id="fa677-151">2 a.m.</span></span> |
|<span data-ttu-id="fa677-152">Rot</span><span class="sxs-lookup"><span data-stu-id="fa677-152">Root</span></span> | <span data-ttu-id="fa677-153">Slumpmässigt schemalagda aktivitetstider</span><span class="sxs-lookup"><span data-stu-id="fa677-153">Randomize scheduled task times</span></span> |<span data-ttu-id="fa677-154">I Microsoft Defender Antivirus: Slumpa starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="fa677-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="fa677-155">I FEP/SSSON: slumpvis till ett intervall plus eller minus 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="fa677-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="fa677-156">Det kan vara användbart i VM- eller VDI-distributioner.</span><span class="sxs-lookup"><span data-stu-id="fa677-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="fa677-157">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa677-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="fa677-158">Använda PowerShell-cmdlets för att schemalägga skanningar</span><span class="sxs-lookup"><span data-stu-id="fa677-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="fa677-159">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa677-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="fa677-160">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa677-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="fa677-161">Schemalägga genomsökningar med Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="fa677-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="fa677-162">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa677-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="fa677-163">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="fa677-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="fa677-164">API:er för Windows Defender WMIv2</span><span class="sxs-lookup"><span data-stu-id="fa677-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="fa677-165">Starta schemalagda genomsökningar bara när slutpunkten inte används</span><span class="sxs-lookup"><span data-stu-id="fa677-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="fa677-166">Du kan ange att den schemalagda genomsökningen bara ska ske när slutpunkten är aktiverad men inte används med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa677-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="fa677-167">De här genomsökningarna respekterar inte konfigurationen av CPU-begränsning och utnyttjar de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="fa677-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="fa677-168">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="fa677-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="fa677-169">Plats</span><span class="sxs-lookup"><span data-stu-id="fa677-169">Location</span></span> | <span data-ttu-id="fa677-170">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa677-170">Setting</span></span> | <span data-ttu-id="fa677-171">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa677-171">Description</span></span> | <span data-ttu-id="fa677-172">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa677-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa677-173">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-173">Scan</span></span> | <span data-ttu-id="fa677-174">Starta den schemalagda genomsökningen bara när datorn är på, men inte använder</span><span class="sxs-lookup"><span data-stu-id="fa677-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="fa677-175">Schemalagda genomsökningar körs inte, om inte datorn är på men inte används</span><span class="sxs-lookup"><span data-stu-id="fa677-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="fa677-176">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa677-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="fa677-177">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="fa677-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="fa677-178">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa677-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="fa677-179">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa677-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="fa677-180">Använda Instruktionerna för Windows Management (WMI)</span><span class="sxs-lookup"><span data-stu-id="fa677-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="fa677-181">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa677-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="fa677-182">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="fa677-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="fa677-183">API:er för Windows Defender WMIv2</span><span class="sxs-lookup"><span data-stu-id="fa677-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="fa677-184">Konfigurera när fullständiga genomsökningar ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="fa677-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="fa677-185">Vissa hot kan kräva en fullständig genomsökning för att slutföra borttagning och åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fa677-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="fa677-186">Du kan schemalägga när de här genomsökningarna ska ske med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa677-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="fa677-187">Använd Grupprincip för att schemalägga genomsökningar som krävs för åtgärder</span><span class="sxs-lookup"><span data-stu-id="fa677-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="fa677-188">Plats</span><span class="sxs-lookup"><span data-stu-id="fa677-188">Location</span></span> | <span data-ttu-id="fa677-189">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa677-189">Setting</span></span> | <span data-ttu-id="fa677-190">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa677-190">Description</span></span> | <span data-ttu-id="fa677-191">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa677-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="fa677-192">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="fa677-192">Remediation</span></span> | <span data-ttu-id="fa677-193">Ange veckodagen då en schemalagd fullständig genomsökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa677-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="fa677-194">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="fa677-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="fa677-195">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa677-195">Never</span></span> |
|<span data-ttu-id="fa677-196">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="fa677-196">Remediation</span></span> | <span data-ttu-id="fa677-197">Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="fa677-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="fa677-198">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="fa677-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="fa677-199">02:00</span><span class="sxs-lookup"><span data-stu-id="fa677-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="fa677-200">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="fa677-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="fa677-201">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa677-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="fa677-202">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa677-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="fa677-203">Använda Instruktionerna för Windows Management (WMI)</span><span class="sxs-lookup"><span data-stu-id="fa677-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="fa677-204">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa677-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="fa677-205">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="fa677-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="fa677-206">API:er för Windows Defender WMIv2</span><span class="sxs-lookup"><span data-stu-id="fa677-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="fa677-207">Konfigurera dagliga snabbsökningar</span><span class="sxs-lookup"><span data-stu-id="fa677-207">Set up daily quick scans</span></span>

<span data-ttu-id="fa677-208">Du kan aktivera en daglig snabbsökning som kan köras utöver dina andra schemalagda genomsökningar med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa677-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="fa677-209">Använda grupprinciper för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa677-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="fa677-210">Plats</span><span class="sxs-lookup"><span data-stu-id="fa677-210">Location</span></span> | <span data-ttu-id="fa677-211">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa677-211">Setting</span></span> | <span data-ttu-id="fa677-212">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa677-212">Description</span></span> | <span data-ttu-id="fa677-213">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa677-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa677-214">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-214">Scan</span></span> | <span data-ttu-id="fa677-215">Ange tidsintervallet för att köra snabbsökningar per dag</span><span class="sxs-lookup"><span data-stu-id="fa677-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="fa677-216">Ange hur många timmar som ska förfluta före nästa snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa677-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="fa677-217">Om du till exempel vill köra varannan timme anger **du 2**, för en gång om dagen skriver du **24**.</span><span class="sxs-lookup"><span data-stu-id="fa677-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="fa677-218">Ange **0 för** att aldrig köra en daglig snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa677-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="fa677-219">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa677-219">Never</span></span> |
|<span data-ttu-id="fa677-220">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa677-220">Scan</span></span> | <span data-ttu-id="fa677-221">Ange tiden för en daglig snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa677-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="fa677-222">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="fa677-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="fa677-223">02:00</span><span class="sxs-lookup"><span data-stu-id="fa677-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="fa677-224">Använda PowerShell-cmdlets för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa677-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="fa677-225">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa677-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="fa677-226">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa677-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="fa677-227">Använd WMI (Windows Management Instruction) för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa677-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="fa677-228">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa677-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="fa677-229">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="fa677-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="fa677-230">API:er för Windows Defender WMIv2</span><span class="sxs-lookup"><span data-stu-id="fa677-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="fa677-231">Aktivera genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa677-231">Enable scans after protection updates</span></span>

<span data-ttu-id="fa677-232">Du kan tvinga fram en genomsökning efter varje [skyddsuppdatering](manage-protection-updates-microsoft-defender-antivirus.md) med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="fa677-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="fa677-233">Använda grupprinciper för att schemalägga genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa677-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="fa677-234">Plats</span><span class="sxs-lookup"><span data-stu-id="fa677-234">Location</span></span> | <span data-ttu-id="fa677-235">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa677-235">Setting</span></span> | <span data-ttu-id="fa677-236">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa677-236">Description</span></span> | <span data-ttu-id="fa677-237">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa677-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="fa677-238">Signaturuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa677-238">Signature updates</span></span> | <span data-ttu-id="fa677-239">Aktivera genomsökning efter säkerhetsintelligensuppdatering</span><span class="sxs-lookup"><span data-stu-id="fa677-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="fa677-240">En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned</span><span class="sxs-lookup"><span data-stu-id="fa677-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="fa677-241">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa677-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="fa677-242">Se även</span><span class="sxs-lookup"><span data-stu-id="fa677-242">See also</span></span>
- [<span data-ttu-id="fa677-243">Förhindra eller tillåta användare att lokalt ändra principinställningar</span><span class="sxs-lookup"><span data-stu-id="fa677-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa677-244">Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran</span><span class="sxs-lookup"><span data-stu-id="fa677-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa677-245">Konfigurera sökalternativ för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa677-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa677-246">Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer</span><span class="sxs-lookup"><span data-stu-id="fa677-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa677-247">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="fa677-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="fa677-248">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa677-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)