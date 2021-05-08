---
title: Schemalägg vanliga snabba och fullständiga skanningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274694"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="0b9cf-104">Konfigurera schemalagda snabb- eller fullständiga genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b9cf-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="0b9cf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0b9cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b9cf-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b9cf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="0b9cf-107">Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter före tiden för schemalagda sökningar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="0b9cf-108">Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="0b9cf-109">Förutom att alltid ha realtidsskydd och genomsökningar [på](run-scan-microsoft-defender-antivirus.md) begäran kan du också konfigurera regelbundna, schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="0b9cf-110">Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller om slutpunkten används.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="0b9cf-111">Du kan också ange när särskilda genomsökningar ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="0b9cf-112">I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med Grupprincip, PowerShell-cmdlets och WMI.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="0b9cf-113">Du kan också konfigurera schemasökningar med [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) eller [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="0b9cf-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="0b9cf-114">Så här konfigurerar du grupprincipinställningarna som beskrivs i den här artikeln</span><span class="sxs-lookup"><span data-stu-id="0b9cf-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="0b9cf-115">Gå till Administrativa mallar för datorkonfiguration på hanteringsdatorn för grupprinciper i  >    >  **grupprincipredigeraren och klicka Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Genomsökning.**</span><span class="sxs-lookup"><span data-stu-id="0b9cf-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="0b9cf-116">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="0b9cf-117">Ange inställningar för grupprincipobjektet och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="0b9cf-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="0b9cf-118">Upprepa steg 1–4 för varje inställning du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="0b9cf-119">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="0b9cf-120">Om du behöver hjälp med grupprincipobjekt kan du gå [till Skapa ett grupprincipobjekt.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="0b9cf-121">Läs även Hantera [när skyddsuppdateringar ska laddas ned och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) och Förhindra eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="0b9cf-122">Snabbsökning kontra fullständig sökning och anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="0b9cf-123">När du ställer in schemalagda genomsökningar kan du ställa in om skanningen ska vara en fullständig eller snabb genomsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="0b9cf-124">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-124">Quick scan</span></span>  |<span data-ttu-id="0b9cf-125">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-125">Full scan</span></span>  | <span data-ttu-id="0b9cf-126">Anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0b9cf-127">En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="0b9cf-128">I de flesta fall är en snabbsökning tillräcklig och rekommenderas för schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="0b9cf-129">En fullständig genomsökning påbörjas genom att köra en snabb genomsökning, och sedan fortsätter den med en sekventiell genomsökning av alla fasta diskmonter och flyttbara/nätverksenheter (om den fullständiga genomsökningen är konfigurerad att göra det).</span><span class="sxs-lookup"><span data-stu-id="0b9cf-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="0b9cf-130">En fullständig genomsökning kan ta några timmar eller dagar att slutföra, beroende på hur mycket och vilken typ av data som behöver skannas.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="0b9cf-131">När den fullständiga genomsökningen är klar är ny säkerhetsinformation tillgänglig och en ny genomsökning krävs för att se till att inga andra hot identifieras med den nya säkerhetsintelligensen.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="0b9cf-132">En anpassad genomsökning är en snabbsökning som körs på de filer och mappar som du anger.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="0b9cf-133">Du kan till exempel välja att skanna en USB-enhet eller en särskild mapp på enhetens lokala enhet.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="0b9cf-134">Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="0b9cf-135">Hur vet jag vilken skanningstyp jag ska välja?</span><span class="sxs-lookup"><span data-stu-id="0b9cf-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="0b9cf-136">Använd följande tabell för att välja en genomsökningstyp.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="0b9cf-137">Scenario</span><span class="sxs-lookup"><span data-stu-id="0b9cf-137">Scenario</span></span>  |<span data-ttu-id="0b9cf-138">Rekommenderad genomsökningstyp</span><span class="sxs-lookup"><span data-stu-id="0b9cf-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="0b9cf-139">Du vill ställa in vanliga, schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="0b9cf-140">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-140">Quick scan</span></span> <p><span data-ttu-id="0b9cf-141">En snabb genomsökning kontrollerar processer, minne, profiler och vissa platser på enheten.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="0b9cf-142">I kombination [med realtidsskydd ger](configure-real-time-protection-microsoft-defender-antivirus.md)en snabb genomsökning stark täckning både för skadlig programvara som börjar med skadlig programvara på system- och kernel-nivå.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="0b9cf-143">Realtidsskydd granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="0b9cf-144">Hot, till exempel skadlig kod, upptäcks på en enhet</span><span class="sxs-lookup"><span data-stu-id="0b9cf-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="0b9cf-145">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-145">Full scan</span></span> <p><span data-ttu-id="0b9cf-146">En fullständig genomsökning kan hjälpa dig att se om det finns inaktiva komponenter som kräver en mer omfattande rensning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="0b9cf-147">Du vill köra en [sökning på begäran](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="0b9cf-148">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-148">Full scan</span></span>  <p><span data-ttu-id="0b9cf-149">En fullständig genomsökning tittar på alla filer på enhetens hårddisk, inklusive filer som är inaktuella, arkiverade och inte används dagligen.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="0b9cf-150">Du vill kontrollera att en bärbar enhet, till exempel en USB-enhet, inte innehåller skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="0b9cf-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="0b9cf-151">Anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-151">Custom scan</span></span> <p><span data-ttu-id="0b9cf-152">Med en anpassad genomsökning kan du välja specifika platser, mappar eller filer och göra en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="0b9cf-153">Vad mer behöver jag veta om snabba och fullständiga skanningar?</span><span class="sxs-lookup"><span data-stu-id="0b9cf-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="0b9cf-154">Skadliga filer kan lagras på platser som inte ingår i en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="0b9cf-155">Skydd i realtid granskar emellertid alla filer som öppnas och stängs och alla filer som finns i mappar som en användare har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="0b9cf-156">Kombinationen av realtidsskydd och en snabb genomsökning ger ett starkt skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="0b9cf-157">Skydd vid åtkomst med moln levererat [skydd](cloud-protection-microsoft-defender-antivirus.md) hjälper till att säkerställa att alla filer som används i systemet genomsöks med de senaste säkerhetsintelligens- och maskininlärningsmodellerna.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="0b9cf-158">När realtidsskyddet identifierar skadlig programvara och omfattningen av de berörda filerna inte fastställts först initierar Microsoft Defender Antivirus en fullständig genomsökning som en del av åtgärdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="0b9cf-159">En fullständig genomsökning kan identifiera skadliga filer som inte identifierats av andra genomsökningar, till exempel en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="0b9cf-160">Men en fullständig genomsökning kan ta en stund och använda värdefulla systemresurser för att slutföra.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="0b9cf-161">Om en enhet är offline under en längre tid kan en fullständig genomsökning ta längre tid att slutföra.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="0b9cf-162">Konfigurera schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-162">Set up scheduled scans</span></span>

<span data-ttu-id="0b9cf-163">Schemalagda genomsökningar körs på den dag och den tid som du anger.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="0b9cf-164">Du kan använda Grupprincip, PowerShell och WMI för att konfigurera schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9cf-165">Om en enhet är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, vilket innebär att skanningen stoppades innan den slutförddes.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="0b9cf-166">Microsoft Defender Antivirus en fullständig sökning vid nästa schemalagda tid.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="0b9cf-167">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="0b9cf-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="0b9cf-168">Plats</span><span class="sxs-lookup"><span data-stu-id="0b9cf-168">Location</span></span> | <span data-ttu-id="0b9cf-169">Inställning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-169">Setting</span></span> | <span data-ttu-id="0b9cf-170">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-170">Description</span></span> | <span data-ttu-id="0b9cf-171">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="0b9cf-172">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-172">Scan</span></span> | <span data-ttu-id="0b9cf-173">Ange vilken skanningstyp som ska användas för en schemalagd sökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="0b9cf-174">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-174">Quick scan</span></span> |
|<span data-ttu-id="0b9cf-175">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-175">Scan</span></span> | <span data-ttu-id="0b9cf-176">Ange veckodagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="0b9cf-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="0b9cf-177">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="0b9cf-178">Aldrig</span><span class="sxs-lookup"><span data-stu-id="0b9cf-178">Never</span></span> |
|<span data-ttu-id="0b9cf-179">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-179">Scan</span></span> | <span data-ttu-id="0b9cf-180">Ange tid på dagen då en schemalagd sökning ska köras</span><span class="sxs-lookup"><span data-stu-id="0b9cf-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="0b9cf-181">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00).</span><span class="sxs-lookup"><span data-stu-id="0b9cf-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="0b9cf-182">02:00</span><span class="sxs-lookup"><span data-stu-id="0b9cf-182">2 a.m.</span></span> |
|<span data-ttu-id="0b9cf-183">Rot</span><span class="sxs-lookup"><span data-stu-id="0b9cf-183">Root</span></span> | <span data-ttu-id="0b9cf-184">Slumpmässigt schemalagda aktivitetstider</span><span class="sxs-lookup"><span data-stu-id="0b9cf-184">Randomize scheduled task times</span></span> |<span data-ttu-id="0b9cf-185">I Microsoft Defender Antivirus kan du slumpmässigt lokalisera starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="0b9cf-186">I [S ÄR KAN](/mem/intune/protect/certificates-scep-configure)du slumpmässigt göra genomsökningarna med ett intervall plus eller minus 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="0b9cf-187">Det kan vara användbart i virtuella maskiner eller VDI-distributioner.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="0b9cf-188">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="0b9cf-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="0b9cf-189">Använda PowerShell-cmdlets för att schemalägga skanningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="0b9cf-190">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="0b9cf-191">Mer information finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="0b9cf-192">Schemalägga Windows med hjälp av WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="0b9cf-193">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="0b9cf-194">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="0b9cf-195">Starta schemalagda genomsökningar bara när slutpunkten inte används</span><span class="sxs-lookup"><span data-stu-id="0b9cf-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="0b9cf-196">Du kan ange att den schemalagda genomsökningen bara ska ske när slutpunkten är aktiverad men inte används med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9cf-197">De här genomsökningarna respekterar inte konfigurationen av CPU-begränsning och utnyttjar de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="0b9cf-198">Schemalägga genomsökningar med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="0b9cf-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="0b9cf-199">Plats</span><span class="sxs-lookup"><span data-stu-id="0b9cf-199">Location</span></span> | <span data-ttu-id="0b9cf-200">Inställning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-200">Setting</span></span> | <span data-ttu-id="0b9cf-201">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-201">Description</span></span> | <span data-ttu-id="0b9cf-202">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="0b9cf-203">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-203">Scan</span></span> | <span data-ttu-id="0b9cf-204">Starta den schemalagda genomsökningen bara när datorn är på, men inte använder</span><span class="sxs-lookup"><span data-stu-id="0b9cf-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="0b9cf-205">Schemalagda genomsökningar körs inte, om inte datorn är på men inte används</span><span class="sxs-lookup"><span data-stu-id="0b9cf-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="0b9cf-206">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="0b9cf-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="0b9cf-207">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b9cf-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="0b9cf-208">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="0b9cf-209">Mer information finns i Använda [PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="0b9cf-210">Använda Windows instruktionerna för hantering (WMI)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="0b9cf-211">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="0b9cf-212">Mer information om API:er och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="0b9cf-213">Konfigurera när fullständiga genomsökningar ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="0b9cf-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="0b9cf-214">Vissa hot kan kräva en fullständig genomsökning för att slutföra borttagning och åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="0b9cf-215">Du kan ange när dessa genomsökningar ska ske med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="0b9cf-216">Använd Grupprincip för att schemalägga genomsökningar som krävs för åtgärder</span><span class="sxs-lookup"><span data-stu-id="0b9cf-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="0b9cf-217">Plats</span><span class="sxs-lookup"><span data-stu-id="0b9cf-217">Location</span></span> | <span data-ttu-id="0b9cf-218">Inställning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-218">Setting</span></span> | <span data-ttu-id="0b9cf-219">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-219">Description</span></span> | <span data-ttu-id="0b9cf-220">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="0b9cf-221">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="0b9cf-221">Remediation</span></span> | <span data-ttu-id="0b9cf-222">Ange veckodagen då en schemalagd fullständig genomsökning ska köras</span><span class="sxs-lookup"><span data-stu-id="0b9cf-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="0b9cf-223">Ange den dag (eller aldrig) som ska köras.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="0b9cf-224">Aldrig</span><span class="sxs-lookup"><span data-stu-id="0b9cf-224">Never</span></span> |
|<span data-ttu-id="0b9cf-225">Åtgärda</span><span class="sxs-lookup"><span data-stu-id="0b9cf-225">Remediation</span></span> | <span data-ttu-id="0b9cf-226">Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="0b9cf-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="0b9cf-227">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="0b9cf-228">02:00</span><span class="sxs-lookup"><span data-stu-id="0b9cf-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="0b9cf-229">Använda PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b9cf-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="0b9cf-230">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="0b9cf-231">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="0b9cf-232">Använda Windows instruktionerna för hantering (WMI)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="0b9cf-233">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="0b9cf-234">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="0b9cf-235">Konfigurera dagliga snabbsökningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-235">Set up daily quick scans</span></span>

<span data-ttu-id="0b9cf-236">Du kan aktivera en daglig snabbsökning som kan köras utöver dina andra schemalagda genomsökningar med Grupprincip, PowerShell eller WMI.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="0b9cf-237">Använda grupprinciper för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="0b9cf-238">Plats</span><span class="sxs-lookup"><span data-stu-id="0b9cf-238">Location</span></span> | <span data-ttu-id="0b9cf-239">Inställning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-239">Setting</span></span> | <span data-ttu-id="0b9cf-240">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-240">Description</span></span> | <span data-ttu-id="0b9cf-241">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="0b9cf-242">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-242">Scan</span></span> | <span data-ttu-id="0b9cf-243">Ange tidsintervallet för att köra snabbsökningar per dag</span><span class="sxs-lookup"><span data-stu-id="0b9cf-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="0b9cf-244">Ange hur många timmar som ska förfluta före nästa snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="0b9cf-245">Om du till exempel vill köra varannan timme anger **du 2**, för en gång om dagen skriver du **24**.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="0b9cf-246">Ange **0 för** att aldrig köra en daglig snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="0b9cf-247">Aldrig</span><span class="sxs-lookup"><span data-stu-id="0b9cf-247">Never</span></span> |
|<span data-ttu-id="0b9cf-248">Skanna</span><span class="sxs-lookup"><span data-stu-id="0b9cf-248">Scan</span></span> | <span data-ttu-id="0b9cf-249">Ange tiden för en daglig snabbsökning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="0b9cf-250">Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="0b9cf-251">02:00</span><span class="sxs-lookup"><span data-stu-id="0b9cf-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="0b9cf-252">Använda PowerShell-cmdlets för att schemalägga dagliga genomsökningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="0b9cf-253">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="0b9cf-254">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="0b9cf-255">Schemalägga dagliga Windows med hjälp av WMI (Management Instruction)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="0b9cf-256">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0b9cf-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="0b9cf-257">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="0b9cf-258">Aktivera genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-258">Enable scans after protection updates</span></span>

<span data-ttu-id="0b9cf-259">Du kan tvinga fram en genomsökning efter varje [skyddsuppdatering](manage-protection-updates-microsoft-defender-antivirus.md) med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="0b9cf-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="0b9cf-260">Använda grupprinciper för att schemalägga genomsökningar efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="0b9cf-261">Plats</span><span class="sxs-lookup"><span data-stu-id="0b9cf-261">Location</span></span> | <span data-ttu-id="0b9cf-262">Inställning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-262">Setting</span></span> | <span data-ttu-id="0b9cf-263">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b9cf-263">Description</span></span> | <span data-ttu-id="0b9cf-264">Standardinställning (om den inte konfigurerats)</span><span class="sxs-lookup"><span data-stu-id="0b9cf-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="0b9cf-265">Signaturuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-265">Signature updates</span></span> | <span data-ttu-id="0b9cf-266">Aktivera genomsökning efter säkerhetsintelligensuppdatering</span><span class="sxs-lookup"><span data-stu-id="0b9cf-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="0b9cf-267">En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned</span><span class="sxs-lookup"><span data-stu-id="0b9cf-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="0b9cf-268">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="0b9cf-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="0b9cf-269">Se även</span><span class="sxs-lookup"><span data-stu-id="0b9cf-269">See also</span></span>

- [<span data-ttu-id="0b9cf-270">Förhindra eller tillåta användare att lokalt ändra principinställningar</span><span class="sxs-lookup"><span data-stu-id="0b9cf-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b9cf-271">Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b9cf-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b9cf-272">Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b9cf-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b9cf-273">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="0b9cf-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b9cf-274">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="0b9cf-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="0b9cf-275">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="0b9cf-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)