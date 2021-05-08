---
title: Schemalägg vanliga snabba och fullständiga skanningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245906"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="fa124-104">Konfigurera schemalagda snabb- eller fullständiga genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa124-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="fa124-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fa124-105">**Applies to:**</span></span>

- [<span data-ttu-id="fa124-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fa124-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="fa124-107">Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter före tiden för schemalagda sökningar.</span><span class="sxs-lookup"><span data-stu-id="fa124-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="fa124-108">Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="fa124-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="fa124-109">Förutom att alltid ha realtidsskydd och genomsökningar [på](run-scan-microsoft-defender-antivirus.md) begäran kan du också konfigurera regelbundna, schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="fa124-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="fa124-110">Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller om slutpunkten används.</span><span class="sxs-lookup"><span data-stu-id="fa124-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="fa124-111">Du kan också ange när särskilda genomsökningar ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="fa124-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="fa124-112">I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med Grupprincip, PowerShell-cmdlets och WMI.</span><span class="sxs-lookup"><span data-stu-id="fa124-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="fa124-113">Du kan också konfigurera schemasökningar med [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) eller [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="fa124-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="fa124-114">Så här konfigurerar du grupprincipinställningarna som beskrivs i den här artikeln</span><span class="sxs-lookup"><span data-stu-id="fa124-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="fa124-115">Gå till Administrativa mallar för datorkonfiguration på hanteringsdatorn för grupprinciper i  >    >  **grupprincipredigeraren och klicka Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Genomsökning.**</span><span class="sxs-lookup"><span data-stu-id="fa124-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="fa124-116">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="fa124-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="fa124-117">Ange inställningar för grupprincipobjektet och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="fa124-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="fa124-118">Upprepa steg 1–4 för varje inställning du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="fa124-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="fa124-119">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="fa124-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="fa124-120">Om du behöver hjälp med grupprincipobjekt kan du gå [till Skapa ett grupprincipobjekt.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="fa124-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="fa124-121">Läs även Hantera [när skyddsuppdateringar ska laddas ned och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) och Förhindra eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fa124-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="fa124-122">Snabbsökning kontra fullständig sökning och anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="fa124-123">När du ställer in schemalagda genomsökningar kan du ställa in om skanningen ska vara en fullständig eller snabb genomsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="fa124-124">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa124-124">Quick scan</span></span>  |<span data-ttu-id="fa124-125">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-125">Full scan</span></span>  | <span data-ttu-id="fa124-126">Anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fa124-127">En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar.</span><span class="sxs-lookup"><span data-stu-id="fa124-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="fa124-128">I de flesta fall är en snabbsökning tillräcklig och rekommenderas för schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="fa124-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="fa124-129">En fullständig genomsökning påbörjas genom att köra en snabb genomsökning, och sedan fortsätter den med en sekventiell genomsökning av alla fasta diskmonter och flyttbara/nätverksenheter (om den fullständiga genomsökningen är konfigurerad att göra det).</span><span class="sxs-lookup"><span data-stu-id="fa124-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="fa124-130">En fullständig genomsökning kan ta några timmar eller dagar att slutföra, beroende på hur mycket och vilken typ av data som behöver skannas.</span><span class="sxs-lookup"><span data-stu-id="fa124-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="fa124-131">När den fullständiga genomsökningen är klar är ny säkerhetsinformation tillgänglig och en ny genomsökning krävs för att se till att inga andra hot identifieras med den nya säkerhetsintelligensen.</span><span class="sxs-lookup"><span data-stu-id="fa124-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="fa124-132">En anpassad genomsökning är en snabbsökning som körs på de filer och mappar som du anger.</span><span class="sxs-lookup"><span data-stu-id="fa124-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="fa124-133">Du kan till exempel välja att skanna en USB-enhet eller en särskild mapp på enhetens lokala enhet.</span><span class="sxs-lookup"><span data-stu-id="fa124-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="fa124-134">Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="fa124-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="fa124-135">Hur vet jag vilken skanningstyp jag ska välja?</span><span class="sxs-lookup"><span data-stu-id="fa124-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="fa124-136">Använd följande tabell för att välja en genomsökningstyp.</span><span class="sxs-lookup"><span data-stu-id="fa124-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="fa124-137">Scenario</span><span class="sxs-lookup"><span data-stu-id="fa124-137">Scenario</span></span>  |<span data-ttu-id="fa124-138">Rekommenderad genomsökningstyp</span><span class="sxs-lookup"><span data-stu-id="fa124-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="fa124-139">Du vill ställa in vanliga, schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa124-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="fa124-140">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa124-140">Quick scan</span></span> <p><span data-ttu-id="fa124-141">En snabb genomsökning kontrollerar processer, minne, profiler och vissa platser på enheten.</span><span class="sxs-lookup"><span data-stu-id="fa124-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="fa124-142">I kombination [med realtidsskydd ger](configure-real-time-protection-microsoft-defender-antivirus.md)en snabb genomsökning stark täckning både för skadlig programvara som börjar med skadlig programvara på system- och kernel-nivå.</span><span class="sxs-lookup"><span data-stu-id="fa124-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="fa124-143">Realtidsskydd granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp.</span><span class="sxs-lookup"><span data-stu-id="fa124-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="fa124-144">Hot, till exempel skadlig kod, upptäcks på en enhet</span><span class="sxs-lookup"><span data-stu-id="fa124-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="fa124-145">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-145">Full scan</span></span> <p><span data-ttu-id="fa124-146">En fullständig genomsökning kan hjälpa dig att se om det finns inaktiva komponenter som kräver en mer omfattande rensning.</span><span class="sxs-lookup"><span data-stu-id="fa124-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="fa124-147">Du vill köra en [sökning på begäran](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fa124-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="fa124-148">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-148">Full scan</span></span>  <p><span data-ttu-id="fa124-149">En fullständig genomsökning tittar på alla filer på enhetens hårddisk, inklusive filer som är inaktuella, arkiverade och inte används dagligen.</span><span class="sxs-lookup"><span data-stu-id="fa124-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="fa124-150">Du vill kontrollera att en bärbar enhet, till exempel en USB-enhet, inte innehåller skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="fa124-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="fa124-151">Anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-151">Custom scan</span></span> <p><span data-ttu-id="fa124-152">Med en anpassad genomsökning kan du välja specifika platser, mappar eller filer och göra en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="fa124-153">Vad mer behöver jag veta om snabba och fullständiga skanningar?</span><span class="sxs-lookup"><span data-stu-id="fa124-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="fa124-154">Skadliga filer kan lagras på platser som inte ingår i en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="fa124-155">Skydd i realtid granskar emellertid alla filer som öppnas och stängs och alla filer som finns i mappar som en användare har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="fa124-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="fa124-156">Kombinationen av realtidsskydd och en snabb genomsökning ger ett starkt skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fa124-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="fa124-157">Skydd vid åtkomst med moln levererat [skydd](cloud-protection-microsoft-defender-antivirus.md) hjälper till att säkerställa att alla filer som används i systemet genomsöks med de senaste säkerhetsintelligens- och maskininlärningsmodellerna.</span><span class="sxs-lookup"><span data-stu-id="fa124-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="fa124-158">När realtidsskyddet identifierar skadlig programvara och omfattningen av de berörda filerna inte fastställts först initierar Microsoft Defender Antivirus en fullständig genomsökning som en del av åtgärdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="fa124-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="fa124-159">En fullständig genomsökning kan identifiera skadliga filer som inte identifierats av andra genomsökningar, till exempel en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="fa124-160">Men en fullständig genomsökning kan ta en stund och använda värdefulla systemresurser för att slutföra.</span><span class="sxs-lookup"><span data-stu-id="fa124-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="fa124-161">Om en enhet är offline under en längre tid kan en fullständig genomsökning ta längre tid att slutföra.</span><span class="sxs-lookup"><span data-stu-id="fa124-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="fa124-162">Konfigurera schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa124-162">Set up scheduled scans</span></span>

<span data-ttu-id="fa124-163">Schemalagda genomsökningar körs på den dag och den tid som du anger.</span><span class="sxs-lookup"><span data-stu-id="fa124-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="fa124-164">Du kan använda Grupprincip, PowerShell och WMI för att konfigurera schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="fa124-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="fa124-165">Om en enhet är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, vilket innebär att skanningen stoppades innan den slutförddes.</span><span class="sxs-lookup"><span data-stu-id="fa124-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="fa124-166">Microsoft Defender Antivirus en fullständig sökning vid nästa schemalagda tid.</span><span class="sxs-lookup"><span data-stu-id="fa124-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="fa124-167">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="fa124-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="fa124-168">Plats</span><span class="sxs-lookup"><span data-stu-id="fa124-168">Location</span></span> | <span data-ttu-id="fa124-169">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa124-169">Setting</span></span> | <span data-ttu-id="fa124-170">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa124-170">Description</span></span> | <span data-ttu-id="fa124-171">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa124-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa124-172">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-172">Scan</span></span> | <span data-ttu-id="fa124-173">Ange vilken skanningstyp som ska användas för en schemalagd sökning</span><span class="sxs-lookup"><span data-stu-id="fa124-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="fa124-174">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa124-174">Quick scan</span></span> |
|<span data-ttu-id="fa124-175">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-175">Scan</span></span> | <span data-ttu-id="fa124-176">Ange veckodagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa124-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="fa124-177">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="fa124-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="fa124-178">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa124-178">Never</span></span> |
|<span data-ttu-id="fa124-179">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-179">Scan</span></span> | <span data-ttu-id="fa124-180">Ange tid på dagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa124-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="fa124-181">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00).</span><span class="sxs-lookup"><span data-stu-id="fa124-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="fa124-182">02:00</span><span class="sxs-lookup"><span data-stu-id="fa124-182">2 a.m.</span></span> |
|<span data-ttu-id="fa124-183">Rot</span><span class="sxs-lookup"><span data-stu-id="fa124-183">Root</span></span> | <span data-ttu-id="fa124-184">Slumpmässigt schemalagda aktivitetstider</span><span class="sxs-lookup"><span data-stu-id="fa124-184">Randomize scheduled task times</span></span> |<span data-ttu-id="fa124-185">I Microsoft Defender Antivirus kan du slumpmässigt lokalisera starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="fa124-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="fa124-186">I [S ÄR KAN](/mem/intune/protect/certificates-scep-configure)du slumpmässigt göra genomsökningarna med ett intervall plus eller minus 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="fa124-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="fa124-187">Det kan vara användbart i virtuella maskiner eller VDI-distributioner.</span><span class="sxs-lookup"><span data-stu-id="fa124-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="fa124-188">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa124-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="fa124-189">Använda PowerShell-cmdlets för att schemalägga skanningar</span><span class="sxs-lookup"><span data-stu-id="fa124-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="fa124-190">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa124-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="fa124-191">Mer information finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="fa124-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="fa124-192">Schemalägga Windows med hjälp av WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="fa124-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="fa124-193">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa124-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="fa124-194">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fa124-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="fa124-195">Starta schemalagda genomsökningar bara när slutpunkten inte används</span><span class="sxs-lookup"><span data-stu-id="fa124-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="fa124-196">Du kan ange att den schemalagda genomsökningen bara ska ske när slutpunkten är aktiverad men inte används med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa124-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="fa124-197">De här genomsökningarna respekterar inte konfigurationen av CPU-begränsning och utnyttjar de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="fa124-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="fa124-198">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="fa124-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="fa124-199">Plats</span><span class="sxs-lookup"><span data-stu-id="fa124-199">Location</span></span> | <span data-ttu-id="fa124-200">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa124-200">Setting</span></span> | <span data-ttu-id="fa124-201">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa124-201">Description</span></span> | <span data-ttu-id="fa124-202">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa124-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa124-203">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-203">Scan</span></span> | <span data-ttu-id="fa124-204">Starta den schemalagda genomsökningen bara när datorn är på, men inte använder</span><span class="sxs-lookup"><span data-stu-id="fa124-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="fa124-205">Schemalagda genomsökningar körs inte, om inte datorn är på men inte används</span><span class="sxs-lookup"><span data-stu-id="fa124-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="fa124-206">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa124-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="fa124-207">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="fa124-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="fa124-208">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa124-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="fa124-209">Mer information finns i Använda [PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa124-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="fa124-210">Använda Windows instruktionerna för hantering (WMI)</span><span class="sxs-lookup"><span data-stu-id="fa124-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="fa124-211">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa124-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="fa124-212">Mer information om API:er och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fa124-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="fa124-213">Konfigurera när fullständiga genomsökningar ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="fa124-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="fa124-214">Vissa hot kan kräva en fullständig genomsökning för att slutföra borttagning och åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fa124-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="fa124-215">Du kan ange när dessa genomsökningar ska ske med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa124-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="fa124-216">Använd Grupprincip för att schemalägga genomsökningar som krävs för åtgärder</span><span class="sxs-lookup"><span data-stu-id="fa124-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="fa124-217">Plats</span><span class="sxs-lookup"><span data-stu-id="fa124-217">Location</span></span> | <span data-ttu-id="fa124-218">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa124-218">Setting</span></span> | <span data-ttu-id="fa124-219">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa124-219">Description</span></span> | <span data-ttu-id="fa124-220">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa124-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="fa124-221">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="fa124-221">Remediation</span></span> | <span data-ttu-id="fa124-222">Ange veckodagen då en schemalagd fullständig genomsökning ska köras</span><span class="sxs-lookup"><span data-stu-id="fa124-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="fa124-223">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="fa124-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="fa124-224">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa124-224">Never</span></span> |
|<span data-ttu-id="fa124-225">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="fa124-225">Remediation</span></span> | <span data-ttu-id="fa124-226">Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="fa124-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="fa124-227">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="fa124-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="fa124-228">02:00</span><span class="sxs-lookup"><span data-stu-id="fa124-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="fa124-229">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="fa124-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="fa124-230">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa124-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="fa124-231">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="fa124-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="fa124-232">Använda Windows instruktionerna för hantering (WMI)</span><span class="sxs-lookup"><span data-stu-id="fa124-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="fa124-233">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa124-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="fa124-234">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fa124-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="fa124-235">Konfigurera dagliga snabbsökningar</span><span class="sxs-lookup"><span data-stu-id="fa124-235">Set up daily quick scans</span></span>

<span data-ttu-id="fa124-236">Du kan aktivera en daglig snabbsökning som kan köras utöver dina andra schemalagda genomsökningar med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="fa124-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="fa124-237">Använda grupprinciper för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa124-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="fa124-238">Plats</span><span class="sxs-lookup"><span data-stu-id="fa124-238">Location</span></span> | <span data-ttu-id="fa124-239">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa124-239">Setting</span></span> | <span data-ttu-id="fa124-240">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa124-240">Description</span></span> | <span data-ttu-id="fa124-241">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa124-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fa124-242">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-242">Scan</span></span> | <span data-ttu-id="fa124-243">Ange tidsintervallet för att köra snabbsökningar per dag</span><span class="sxs-lookup"><span data-stu-id="fa124-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="fa124-244">Ange hur många timmar som ska förfluta före nästa snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="fa124-245">Om du till exempel vill köra varannan timme anger **du 2**, för en gång om dagen skriver du **24**.</span><span class="sxs-lookup"><span data-stu-id="fa124-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="fa124-246">Ange **0 för** att aldrig köra en daglig snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="fa124-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="fa124-247">Aldrig</span><span class="sxs-lookup"><span data-stu-id="fa124-247">Never</span></span> |
|<span data-ttu-id="fa124-248">Skanna</span><span class="sxs-lookup"><span data-stu-id="fa124-248">Scan</span></span> | <span data-ttu-id="fa124-249">Ange tiden för en daglig snabbsökning</span><span class="sxs-lookup"><span data-stu-id="fa124-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="fa124-250">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="fa124-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="fa124-251">02:00</span><span class="sxs-lookup"><span data-stu-id="fa124-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="fa124-252">Använda PowerShell-cmdlets för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="fa124-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="fa124-253">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fa124-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="fa124-254">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fa124-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="fa124-255">Schemalägga dagliga Windows med hjälp av WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="fa124-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="fa124-256">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="fa124-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="fa124-257">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fa124-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="fa124-258">Aktivera genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa124-258">Enable scans after protection updates</span></span>

<span data-ttu-id="fa124-259">Du kan tvinga fram en genomsökning efter varje [skyddsuppdatering](manage-protection-updates-microsoft-defender-antivirus.md) med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="fa124-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="fa124-260">Använda grupprinciper för att schemalägga genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa124-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="fa124-261">Plats</span><span class="sxs-lookup"><span data-stu-id="fa124-261">Location</span></span> | <span data-ttu-id="fa124-262">Inställning</span><span class="sxs-lookup"><span data-stu-id="fa124-262">Setting</span></span> | <span data-ttu-id="fa124-263">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fa124-263">Description</span></span> | <span data-ttu-id="fa124-264">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="fa124-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="fa124-265">Signaturuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fa124-265">Signature updates</span></span> | <span data-ttu-id="fa124-266">Aktivera genomsökning efter säkerhetsintelligensuppdatering</span><span class="sxs-lookup"><span data-stu-id="fa124-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="fa124-267">En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned</span><span class="sxs-lookup"><span data-stu-id="fa124-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="fa124-268">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="fa124-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="fa124-269">Se även</span><span class="sxs-lookup"><span data-stu-id="fa124-269">See also</span></span>

- [<span data-ttu-id="fa124-270">Förhindra eller tillåta användare att lokalt ändra principinställningar</span><span class="sxs-lookup"><span data-stu-id="fa124-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa124-271">Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa124-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa124-272">Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa124-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa124-273">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="fa124-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fa124-274">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="fa124-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="fa124-275">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa124-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)