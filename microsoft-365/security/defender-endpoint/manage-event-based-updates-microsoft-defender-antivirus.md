---
title: Använda Microsoft Defender Antivirus uppdateringar efter vissa händelser
description: Hantera hur Microsoft Defender Antivirus tillämpar säkerhetsintelligensuppdateringar efter start eller ta emot rapporter om identifiering av molnleverans.
keywords: uppdateringar, skydd, tvinga uppdateringar, händelser, start, sök efter senaste, meddelanden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274706"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="b791e-104">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="b791e-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b791e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b791e-105">**Applies to:**</span></span>

- [<span data-ttu-id="b791e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b791e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b791e-107">Microsoft Defender Antivirus kan du avgöra om uppdateringar ska (eller inte ska) ske efter vissa händelser, till exempel vid start eller när specifika rapporter tas emot från den molnleveransskyddstjänst.</span><span class="sxs-lookup"><span data-stu-id="b791e-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b791e-108">Söka efter skyddsuppdateringar innan du kör en genomsökning</span><span class="sxs-lookup"><span data-stu-id="b791e-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="b791e-109">Du kan använda Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdlets och WMI för att tvinga Microsoft Defender Antivirus att kontrollera och ladda ned skyddsuppdateringar innan du kör en schemalagd genomsökning.</span><span class="sxs-lookup"><span data-stu-id="b791e-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b791e-110">Använda Konfigurationshanteraren för att söka efter skyddsuppdateringar innan du kör en genomsökning</span><span class="sxs-lookup"><span data-stu-id="b791e-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="b791e-111">Öppna den Microsoft Endpoint Manager programkonsol på datorn som du vill ändra  (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till Översikt Endpoint Protection Program mot skadlig  >    >  **programvara**)</span><span class="sxs-lookup"><span data-stu-id="b791e-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="b791e-112">Gå till avsnittet **Schemalagda genomsökningar** och ställ in Sök efter de senaste **säkerhetsintelligensuppdateringarna innan du kör en genomsökning** på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="b791e-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="b791e-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-113">Click **OK**.</span></span>

4. <span data-ttu-id="b791e-114">[Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="b791e-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b791e-115">Använda grupprinciper för att söka efter skyddsuppdateringar innan du kör en genomsökning</span><span class="sxs-lookup"><span data-stu-id="b791e-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="b791e-116">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="b791e-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b791e-117">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791e-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b791e-118">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b791e-119">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Sök**.</span><span class="sxs-lookup"><span data-stu-id="b791e-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="b791e-120">Dubbelklicka på Sök **efter de senaste definitionerna av virus och spionprogram innan du kör en schemalagd sökning** och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="b791e-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="b791e-121">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b791e-122">Använda PowerShell-cmdlets för att söka efter skyddsuppdateringar innan du kör en genomsökning</span><span class="sxs-lookup"><span data-stu-id="b791e-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="b791e-123">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b791e-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="b791e-124">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="b791e-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="b791e-125">Använd Windows för hanteringsinstruktioner (WMI) för att söka efter skyddsuppdateringar innan du kör en genomsökning</span><span class="sxs-lookup"><span data-stu-id="b791e-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="b791e-126">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="b791e-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="b791e-127">Mer information finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b791e-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="b791e-128">Söka efter säkerhetsuppdateringar vid start</span><span class="sxs-lookup"><span data-stu-id="b791e-128">Check for protection updates on startup</span></span>

<span data-ttu-id="b791e-129">Du kan använda grupprinciper för att tvinga Microsoft Defender Antivirus att kontrollera och hämta skyddsuppdateringar när datorn startas.</span><span class="sxs-lookup"><span data-stu-id="b791e-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="b791e-130">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="b791e-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b791e-131">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791e-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b791e-132">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b791e-133">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Säkerhetsintelligensuppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b791e-134">Dubbelklicka på Sök **efter de senaste definitionerna av virus och spionprogram vid start** och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="b791e-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="b791e-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-135">Click **OK**.</span></span>

<span data-ttu-id="b791e-136">Du kan också använda Grupprincip, PowerShell eller WMI för att konfigurera Microsoft Defender Antivirus att söka efter uppdateringar vid start även när den inte körs.</span><span class="sxs-lookup"><span data-stu-id="b791e-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b791e-137">Använda grupprincip för att ladda ned uppdateringar Microsoft Defender Antivirus inte finns</span><span class="sxs-lookup"><span data-stu-id="b791e-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="b791e-138">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="b791e-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b791e-139">Med **grupprinciphanteringsredigeraren** går du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791e-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b791e-140">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b791e-141">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Säkerhetsintelligensuppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b791e-142">Dubbelklicka på Initiera **säkerhetsintelligensuppdatering vid start** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="b791e-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="b791e-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b791e-144">Använda PowerShell-cmdlets för att ladda ned Microsoft Defender Antivirus uppdateringar som inte Microsoft Defender Antivirus finns</span><span class="sxs-lookup"><span data-stu-id="b791e-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="b791e-145">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b791e-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="b791e-146">Mer information finns i Använda [PowerShell-cmdlets för](use-powershell-cmdlets-microsoft-defender-antivirus.md) att hantera Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/index) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b791e-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="b791e-147">Använd Windows Instruktionerna för hantering (WMI) för att ladda ned uppdateringar Microsoft Defender Antivirus inte finns</span><span class="sxs-lookup"><span data-stu-id="b791e-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="b791e-148">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="b791e-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="b791e-149">Mer information finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b791e-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="b791e-150">Tillåt ad hoc-ändringar av skydd baserat på moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="b791e-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="b791e-151">Microsoft Defender AV kan göra ändringar i skyddet baserat på molnskydd.</span><span class="sxs-lookup"><span data-stu-id="b791e-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="b791e-152">Sådana ändringar kan ske utanför de normala eller schemalagda skyddsuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="b791e-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="b791e-153">Om du har aktiverat molnskydd skickar Microsoft Defender AV filer som verkar misstänkt mot Windows Defender molnet.</span><span class="sxs-lookup"><span data-stu-id="b791e-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="b791e-154">Om molntjänsten rapporterar att filen är skadlig och filen identifieras i en nyligen genomförd skyddsuppdatering kan du använda Grupprincip för att konfigurera Microsoft Defender AV så att den automatiskt får den uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="b791e-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="b791e-155">Andra viktiga skyddsuppdateringar kan också tillämpas.</span><span class="sxs-lookup"><span data-stu-id="b791e-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="b791e-156">Använda grupprinciper för att automatiskt ladda ned de senaste uppdateringarna baserat på moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="b791e-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="b791e-157">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="b791e-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b791e-158">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b791e-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b791e-159">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b791e-160">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Säkerhetsintelligensuppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="b791e-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="b791e-161">Dubbelklicka på Tillåt **säkerhetsintelligensuppdateringar i realtid baserat på rapporter till Microsoft MAPS** och ange alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="b791e-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="b791e-162">Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-162">Then click **OK**.</span></span>

6. <span data-ttu-id="b791e-163">**Tillåt aviseringar att inaktivera definitionsbaserade rapporter till Microsoft MAPS** och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="b791e-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="b791e-164">Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b791e-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b791e-165">**Tillåt aviseringar att inaktivera definitioner baserade rapporter** gör att Microsoft MAPS kan inaktivera de definitioner som kallas för falska positiva rapporter.</span><span class="sxs-lookup"><span data-stu-id="b791e-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="b791e-166">Du måste konfigurera datorn för att ansluta till Microsoft MAPS för att den här funktionen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="b791e-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b791e-167">Se även</span><span class="sxs-lookup"><span data-stu-id="b791e-167">See also</span></span>

- [<span data-ttu-id="b791e-168">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b791e-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b791e-169">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="b791e-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b791e-170">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="b791e-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b791e-171">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="b791e-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b791e-172">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="b791e-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b791e-173">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="b791e-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)