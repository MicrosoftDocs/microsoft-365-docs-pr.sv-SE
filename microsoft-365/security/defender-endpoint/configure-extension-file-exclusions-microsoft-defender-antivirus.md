---
title: Konfigurera och validera undantag baserat på tillägg, namn eller plats
description: Undanta filer Microsoft Defender Antivirus genomsökningar baserat på deras filnamnstillägg, filnamn eller plats.
keywords: undantag, filer, tillägg, filtyp, mappnamn, filnamn, genomsökningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 71df43639a719acb9436f64deba6b6c5cc9317f5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924285"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="1422d-104">Konfigurera och validera undantag baserat på filtillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="1422d-104">Configure and validate exclusions based on file extension and folder location</span></span>



<span data-ttu-id="1422d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1422d-105">**Applies to:**</span></span>

- [<span data-ttu-id="1422d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1422d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="1422d-107">Microsoft Defender Antivirus undantag gäller inte för andra Microsoft Defender-funktioner för Slutpunktsfunktioner, till exempel [identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) [ASR-regler (attack surface reduction)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)och [reglerad mappåtkomst.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="1422d-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="1422d-108">Filer som du undantar med de metoder som beskrivs i den här artikeln kan fortfarande utlösa Identifiering och åtgärd på slutpunkt aviseringar och andra identifieringar.</span><span class="sxs-lookup"><span data-stu-id="1422d-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="1422d-109">Om du vill utesluta filer allmänt lägger du till dem i anpassade indikatorer i Microsoft Defender [för Slutpunkt.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="1422d-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="1422d-110">Undantagslistor</span><span class="sxs-lookup"><span data-stu-id="1422d-110">Exclusion lists</span></span>

<span data-ttu-id="1422d-111">Du kan utesluta vissa filer från Microsoft Defender Antivirus genomsökningar genom att ändra undantagslistor.</span><span class="sxs-lookup"><span data-stu-id="1422d-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="1422d-112">**I allmänhet ska du inte behöva tillämpa undantag.**</span><span class="sxs-lookup"><span data-stu-id="1422d-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="1422d-113">Microsoft Defender Antivirus omfattar många automatiska undantag baserade på kända operativsystemsbeteenden och vanliga hanteringsfiler, till exempel de som används i företagshantering, databashantering och andra företagsscenarier och situationer.</span><span class="sxs-lookup"><span data-stu-id="1422d-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="1422d-114">Undantag gäller även pua-identifieringar som kan vara oönskade.</span><span class="sxs-lookup"><span data-stu-id="1422d-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="1422d-115">Automatiska undantag gäller endast för Windows Server 2016 och högre.</span><span class="sxs-lookup"><span data-stu-id="1422d-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="1422d-116">Undantagen visas inte i Windows-säkerhet och i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1422d-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="1422d-117">I den här artikeln beskrivs hur du konfigurerar undantagslistor för filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="1422d-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="1422d-118">Läs Rekommendationer för att definiera undantag innan du definierar dina [undantagslistor.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="1422d-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="1422d-119">Exkludering</span><span class="sxs-lookup"><span data-stu-id="1422d-119">Exclusion</span></span> | <span data-ttu-id="1422d-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="1422d-120">Examples</span></span> | <span data-ttu-id="1422d-121">Undantagslista</span><span class="sxs-lookup"><span data-stu-id="1422d-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="1422d-122">Alla filer med ett specifikt filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-122">Any file with a specific extension</span></span> | <span data-ttu-id="1422d-123">Alla filer med det angivna tillägget, var som helst på datorn.</span><span class="sxs-lookup"><span data-stu-id="1422d-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="1422d-124">Giltig syntax: `.test` och `test`</span><span class="sxs-lookup"><span data-stu-id="1422d-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="1422d-125">Undantag för tillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-125">Extension exclusions</span></span> |
|<span data-ttu-id="1422d-126">En fil under en särskild mapp</span><span class="sxs-lookup"><span data-stu-id="1422d-126">Any file under a specific folder</span></span> | <span data-ttu-id="1422d-127">Alla filer under `c:\test\sample` mappen</span><span class="sxs-lookup"><span data-stu-id="1422d-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="1422d-128">Undantag för filer och mappar</span><span class="sxs-lookup"><span data-stu-id="1422d-128">File and folder exclusions</span></span> |
| <span data-ttu-id="1422d-129">En viss fil i en särskild mapp</span><span class="sxs-lookup"><span data-stu-id="1422d-129">A specific file in a specific folder</span></span> | <span data-ttu-id="1422d-130">Endast `c:\sample\sample.test` filen</span><span class="sxs-lookup"><span data-stu-id="1422d-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="1422d-131">Undantag för filer och mappar</span><span class="sxs-lookup"><span data-stu-id="1422d-131">File and folder exclusions</span></span> |
| <span data-ttu-id="1422d-132">En specifik process</span><span class="sxs-lookup"><span data-stu-id="1422d-132">A specific process</span></span> | <span data-ttu-id="1422d-133">Den körbara filen `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="1422d-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="1422d-134">Undantag för filer och mappar</span><span class="sxs-lookup"><span data-stu-id="1422d-134">File and folder exclusions</span></span> |

<span data-ttu-id="1422d-135">Undantagslistor har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="1422d-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="1422d-136">Undantag för mappar gäller för alla filer och mappar under den mappen, såvida inte undermappen är en omparsningspunkt.</span><span class="sxs-lookup"><span data-stu-id="1422d-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="1422d-137">Undermappar med uppslagspunkt måste uteslutas separat.</span><span class="sxs-lookup"><span data-stu-id="1422d-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="1422d-138">Filnamnstillägg gäller för alla filnamn med det definierade filnamnstillägget om en sökväg eller mapp inte definierats.</span><span class="sxs-lookup"><span data-stu-id="1422d-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="1422d-139">Om du använder jokertecken som asterisk ( \* ) ändras hur undantagsreglerna tolkas.</span><span class="sxs-lookup"><span data-stu-id="1422d-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="1422d-140">Viktig information om hur jokertecken fungerar finns i avsnittet Använda jokertecken i filnamn och mappsökväg eller [undantagslistor](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) för tillägg.</span><span class="sxs-lookup"><span data-stu-id="1422d-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="1422d-141">Du kan inte utesluta mappade nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="1422d-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="1422d-142">Du måste ange den faktiska nätverkssökvägen.</span><span class="sxs-lookup"><span data-stu-id="1422d-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="1422d-143">Mappar som är upp till två punkter som skapas när Microsoft Defender Antivirus-tjänsten startas och som har lagts till i undantagslistan inkluderas inte.</span><span class="sxs-lookup"><span data-stu-id="1422d-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="1422d-144">Du måste starta om tjänsten (genom att starta om Windows) för att nyaparspunkter ska identifieras som ett giltigt undantagsmål.</span><span class="sxs-lookup"><span data-stu-id="1422d-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="1422d-145">Information om hur du utesluter filer som öppnas i en viss process finns i Konfigurera och validera [undantag för filer som öppnas med processer.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1422d-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1422d-146">Undantagen gäller för [schemalagda genomsökningar,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [skanningar på](run-scan-microsoft-defender-antivirus.md)begäran och [realtidsskydd.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1422d-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1422d-147">Ändringar av undantagslistor som görs **med Grupprincip visas** i listorna i Windows-säkerhet [program.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1422d-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="1422d-148">Ändringar som Windows-säkerhet visas **inte** i grupprinciplistorna.</span><span class="sxs-lookup"><span data-stu-id="1422d-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="1422d-149">Som standard kommer lokala ändringar som görs i listorna (av användare med administratörsbehörighet, inklusive ändringar som görs med PowerShell och WMI) att slås ihop med listorna som definierats (och distribuerats) av Grupprincip, Konfigurationshanteraren eller Intune.</span><span class="sxs-lookup"><span data-stu-id="1422d-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="1422d-150">Grupprinciplistorna har företräde när det uppstår konflikter.</span><span class="sxs-lookup"><span data-stu-id="1422d-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="1422d-151">Du kan [konfigurera hur lokalt och globalt definierade undantagslistor slås samman så](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) att lokala ändringar åsidosätter inställningar för hanterad distribution.</span><span class="sxs-lookup"><span data-stu-id="1422d-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="1422d-152">Konfigurera listan över undantag baserat på mappnamn eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-153">Använda Intune för att konfigurera undantag för filnamn, mapp eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="1422d-154">Se följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="1422d-154">See the following articles:</span></span>
- [<span data-ttu-id="1422d-155">Konfigurera inställningar för enhetsbegränsning i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1422d-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="1422d-156">Microsoft Defender Antivirus för enhetsbegränsningar för Windows 10 i Intune</span><span class="sxs-lookup"><span data-stu-id="1422d-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-157">Använda Konfigurationshanteraren för att konfigurera undantag för filnamn, mapp eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="1422d-158">Se [Skapa och distribuera principer för program mot skadlig programvara: Undantagsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) för information om konfigurering av Microsoft Endpoint Manager (current branch).</span><span class="sxs-lookup"><span data-stu-id="1422d-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-159">Använda grupprinciper för att konfigurera undantag för mappar eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="1422d-160">Om du anger en fullständigt kvalificerad sökväg till en fil utesluts endast den filen.</span><span class="sxs-lookup"><span data-stu-id="1422d-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="1422d-161">Om en mapp definieras i undantaget utesluts alla filer och undermappar under den mappen.</span><span class="sxs-lookup"><span data-stu-id="1422d-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="1422d-162">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="1422d-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="1422d-163">I **redigeraren för hantering av grupprinciper** går **du till Datorkonfiguration** och **väljer Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="1422d-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="1422d-164">Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Undantag**.</span><span class="sxs-lookup"><span data-stu-id="1422d-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="1422d-165">Öppna inställningen **för undantag av** sökvägar för redigering och lägg till undantagen.</span><span class="sxs-lookup"><span data-stu-id="1422d-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="1422d-166">Ställ in alternativet som **Aktiverat**.</span><span class="sxs-lookup"><span data-stu-id="1422d-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="1422d-167">Klicka på **Visa** under **Alternativ.**</span><span class="sxs-lookup"><span data-stu-id="1422d-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="1422d-168">Ange varje mapp på en egen rad under **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="1422d-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="1422d-169">Om du anger en fil ska du kontrollera att du anger en fullständigt kvalificerad sökväg till filen, inklusive enhetsbokstaven, mappsökvägen, filnamn och filnamnstillägg.</span><span class="sxs-lookup"><span data-stu-id="1422d-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="1422d-170">Ange **0** i **kolumnen** Värde.</span><span class="sxs-lookup"><span data-stu-id="1422d-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="1422d-171">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1422d-171">Choose **OK**.</span></span>

6. <span data-ttu-id="1422d-172">Öppna inställningen **för undantag av filnamnstillägg** för redigering och lägg till undantagen.</span><span class="sxs-lookup"><span data-stu-id="1422d-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="1422d-173">Ställ in alternativet som **Aktiverat**.</span><span class="sxs-lookup"><span data-stu-id="1422d-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="1422d-174">Under avsnittet **Alternativ** väljer du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="1422d-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="1422d-175">Ange varje filnamnstillägg på en egen rad under **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="1422d-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="1422d-176">Ange **0** i **kolumnen** Värde.</span><span class="sxs-lookup"><span data-stu-id="1422d-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="1422d-177">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1422d-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-178">Använda PowerShell-cmdlets för att konfigurera undantag för filnamn, mapp eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="1422d-179">Användning av PowerShell för att lägga till eller ta bort undantag för filer baserat på filtillägget, platsen eller filnamnet kräver en kombination av tre cmdlets och lämplig undantagslistparameter.</span><span class="sxs-lookup"><span data-stu-id="1422d-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="1422d-180">Cmdletarna finns i [Defender-modulen.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="1422d-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="1422d-181">Formatet för cmdletarna är följande:</span><span class="sxs-lookup"><span data-stu-id="1422d-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="1422d-182">Följande tillåts `<cmdlet>` som:</span><span class="sxs-lookup"><span data-stu-id="1422d-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="1422d-183">Konfigurationsåtgärd</span><span class="sxs-lookup"><span data-stu-id="1422d-183">Configuration action</span></span> | <span data-ttu-id="1422d-184">PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="1422d-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="1422d-185">Skapa eller skriva över listan</span><span class="sxs-lookup"><span data-stu-id="1422d-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="1422d-186">Lägg till i listan</span><span class="sxs-lookup"><span data-stu-id="1422d-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="1422d-187">Ta bort objekt från listan</span><span class="sxs-lookup"><span data-stu-id="1422d-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="1422d-188">Följande tillåts `<exclusion list>` som:</span><span class="sxs-lookup"><span data-stu-id="1422d-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="1422d-189">Exkluderingstyp</span><span class="sxs-lookup"><span data-stu-id="1422d-189">Exclusion type</span></span> | <span data-ttu-id="1422d-190">PowerShell-parameter</span><span class="sxs-lookup"><span data-stu-id="1422d-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="1422d-191">Alla filer med ett angivet filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="1422d-192">Alla filer under en mapp (inklusive filer i undermappar) eller en viss fil</span><span class="sxs-lookup"><span data-stu-id="1422d-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="1422d-193">Om du har skapat en lista med eller skriver du över den befintliga listan med hjälp av `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdleten igen.</span><span class="sxs-lookup"><span data-stu-id="1422d-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="1422d-194">Följande kodavsnitt skulle till exempel orsaka att Microsoft Defender Antivirus för att utesluta alla filer med `.test` filtillägget:</span><span class="sxs-lookup"><span data-stu-id="1422d-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="1422d-195">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="1422d-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-196">Använd Windows för hanteringsinstruktioner (WMI) för att konfigurera undantag för filnamn, mapp eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="1422d-197">Använd metoderna [ **Ange,** **Lägg** till **och Ta** bort **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) klassen för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="1422d-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="1422d-198">Användandet av **Set**, **Add** och **Remove kan** jämföras med deras motsvarigheter i PowerShell: , `Set-MpPreference` och `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="1422d-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="1422d-199">Mer information finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="1422d-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="1422d-200">Använda Windows-säkerhet-appen för att konfigurera undantag för filnamn, mapp eller filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="1422d-201">Anvisningar [finns i Lägga till undantag Windows-säkerhet appen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1422d-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="1422d-202">Använda jokertecken i filnamnet och i undantagslistorna för mappar och filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="1422d-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="1422d-203">Du kan använda asterisken, frågetecken eller miljövariabler (till exempel ) som jokertecken när du definierar objekt i undantagslistan för filnamnet eller `*` `?` `%ALLUSERSPROFILE%` sökvägen till mappen.</span><span class="sxs-lookup"><span data-stu-id="1422d-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="1422d-204">Hur dessa jokertecken tolkas skiljer sig från den vanliga användningen i andra appar och språk.</span><span class="sxs-lookup"><span data-stu-id="1422d-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="1422d-205">Läs det här avsnittet för att förstå deras specifika begränsningar.</span><span class="sxs-lookup"><span data-stu-id="1422d-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1422d-206">Det finns viktiga begränsningar och användningsscenarier för dessa jokertecken:</span><span class="sxs-lookup"><span data-stu-id="1422d-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="1422d-207">Miljövariabel användning begränsas till maskinvariabler och de som gäller för processer som körs som ett NT AUTHORITY\SYSTEM-konto.</span><span class="sxs-lookup"><span data-stu-id="1422d-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="1422d-208">Du kan inte använda ett jokertecken i stället för en enhetsbeteckning.</span><span class="sxs-lookup"><span data-stu-id="1422d-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="1422d-209">En asterisk `*` i ett undantag från mappar gäller för en enskild mapp.</span><span class="sxs-lookup"><span data-stu-id="1422d-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="1422d-210">Använd flera instanser av för `\*\` att ange flera kapslade mappar med ospecificerade namn.</span><span class="sxs-lookup"><span data-stu-id="1422d-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="1422d-211">I följande tabell beskrivs hur jokertecken kan användas och några exempel.</span><span class="sxs-lookup"><span data-stu-id="1422d-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="1422d-212">Jokertecken</span><span class="sxs-lookup"><span data-stu-id="1422d-212">Wildcard</span></span>  |<span data-ttu-id="1422d-213">Exempel</span><span class="sxs-lookup"><span data-stu-id="1422d-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="1422d-214">`*` (asterisk)</span><span class="sxs-lookup"><span data-stu-id="1422d-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="1422d-215">I **filnamns- och filnamnstillägg ersätter** asterisken valt många tecken och gäller endast filer i den senaste mappen som definierats i argumentet.</span><span class="sxs-lookup"><span data-stu-id="1422d-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="1422d-216">I **mapp undantas** ersätter asterisken en enskild mapp.</span><span class="sxs-lookup"><span data-stu-id="1422d-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="1422d-217">Använd flera `*` med mappsnedstreck för `\` att ange flera kapslade mappar.</span><span class="sxs-lookup"><span data-stu-id="1422d-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="1422d-218">När antalet jokertecken och namngivna mappar har matchats, inkluderas även alla undermappar.</span><span class="sxs-lookup"><span data-stu-id="1422d-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="1422d-219">`C:\MyData\*.txt` inkluderar `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="1422d-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="1422d-220">`C:\somepath\*\Data` inkluderar alla filer `C:\somepath\Archives\Data` i och dess undermappar och `C:\somepath\Authorized\Data` dess undermappar</span><span class="sxs-lookup"><span data-stu-id="1422d-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="1422d-221">`C:\Serv\*\*\Backup` inkluderar alla filer `C:\Serv\Primary\Denied\Backup` i och dess undermappar `C:\Serv\Secondary\Allowed\Backup` och dess undermappar</span><span class="sxs-lookup"><span data-stu-id="1422d-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="1422d-222">`?` (frågetecken)</span><span class="sxs-lookup"><span data-stu-id="1422d-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="1422d-223">I **filnamns- och filnamnstillägg ersätter** frågetecknet ett enda tecken och gäller endast filer i den senaste mappen som definierats i argumentet.</span><span class="sxs-lookup"><span data-stu-id="1422d-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="1422d-224">I **mapp undantas** ersätter frågetecknet ett enda tecken i ett mappnamn.</span><span class="sxs-lookup"><span data-stu-id="1422d-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="1422d-225">När antalet jokertecken och namngivna mappar har matchats, inkluderas även alla undermappar.</span><span class="sxs-lookup"><span data-stu-id="1422d-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="1422d-226">`C:\MyData\my?.zip` inkluderar `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="1422d-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="1422d-227">`C:\somepath\?\Data` inkluderar alla filer `C:\somepath\P\Data` i och dess undermappar</span><span class="sxs-lookup"><span data-stu-id="1422d-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="1422d-228">`C:\somepath\test0?\Data` skulle inkludera alla filer i `C:\somepath\test01\Data` och dess undermappar</span><span class="sxs-lookup"><span data-stu-id="1422d-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="1422d-229">Miljövariabler</span><span class="sxs-lookup"><span data-stu-id="1422d-229">Environment variables</span></span> <p> <span data-ttu-id="1422d-230">Den definierade variabeln fylls i som en sökväg när undantaget beräknas.</span><span class="sxs-lookup"><span data-stu-id="1422d-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="1422d-231">`%ALLUSERSPROFILE%\CustomLogFiles` skulle inkludera `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="1422d-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="1422d-232">Om du blandar ett argument för filexkludering med ett argument för undantag för mappar stannar reglerna vid argumentet fil i den matchande mappen och söker inte efter filmatchningar i någon undermapp.</span><span class="sxs-lookup"><span data-stu-id="1422d-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="1422d-233">Du kan till exempel utesluta alla filer som börjar med "datum" i mapparna `c:\data\final\marked` och genom att använda `c:\data\review\marked` regelargumentet `c:\data\*\marked\date*` .</span><span class="sxs-lookup"><span data-stu-id="1422d-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="1422d-234">Det här argumentet matchar dock inte filer i undermappar under `c:\data\final\marked` eller `c:\data\review\marked` .</span><span class="sxs-lookup"><span data-stu-id="1422d-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="1422d-235">Systemmiljövariabler</span><span class="sxs-lookup"><span data-stu-id="1422d-235">System environment variables</span></span>

<span data-ttu-id="1422d-236">I följande tabell visas och beskrivs systemkontomiljövariablerna.</span><span class="sxs-lookup"><span data-stu-id="1422d-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="1422d-237">Den här systemmiljövariabeln...</span><span class="sxs-lookup"><span data-stu-id="1422d-237">This system environment variable...</span></span> | <span data-ttu-id="1422d-238">Omdirigerar till den här</span><span class="sxs-lookup"><span data-stu-id="1422d-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="1422d-239">C:\ProgramData\Start Menu\Programs</span><span class="sxs-lookup"><span data-stu-id="1422d-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="1422d-240">Granska listan över undantag</span><span class="sxs-lookup"><span data-stu-id="1422d-240">Review the list of exclusions</span></span>

<span data-ttu-id="1422d-241">Du kan hämta objekten i undantagslistan på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="1422d-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="1422d-242">Intune</span><span class="sxs-lookup"><span data-stu-id="1422d-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="1422d-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1422d-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="1422d-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="1422d-244">MpCmdRun</span></span>
- <span data-ttu-id="1422d-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1422d-245">PowerShell</span></span>
- [<span data-ttu-id="1422d-246">Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="1422d-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="1422d-247">Ändringar av undantagslistor som görs **med Grupprincip visas** i listorna i Windows-säkerhet [program.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1422d-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="1422d-248">Ändringar som Windows-säkerhet visas **inte** i grupprinciplistorna.</span><span class="sxs-lookup"><span data-stu-id="1422d-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="1422d-249">Om du använder PowerShell kan du hämta listan på två sätt:</span><span class="sxs-lookup"><span data-stu-id="1422d-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="1422d-250">Hämta status för alla Microsoft Defender Antivirus inställningar.</span><span class="sxs-lookup"><span data-stu-id="1422d-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="1422d-251">Varje lista visas på separata rader, men objekten i varje lista kombineras på samma rad.</span><span class="sxs-lookup"><span data-stu-id="1422d-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="1422d-252">Skriv statusen för alla inställningar till en variabel och använd den variabeln för att bara anropa den specifika listan som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="1422d-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="1422d-253">Varje användning av `Add-MpPreference` skrivs till en ny rad.</span><span class="sxs-lookup"><span data-stu-id="1422d-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="1422d-254">Validera undantagslistan med hjälp av MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="1422d-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="1422d-255">Om du vill kontrollera undantag med det [dedikerade kommandoradsverktyget mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)använder du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1422d-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="1422d-256">Kontroll av undantag med MpCmdRun kräver Microsoft Defender Antivirus CAMP version 4.18.1812.3 (utgiven i december 2018) eller senare.</span><span class="sxs-lookup"><span data-stu-id="1422d-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="1422d-257">Granska listan över undantag tillsammans med alla andra alternativ Microsoft Defender Antivirus med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="1422d-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="1422d-258">Använd följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1422d-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="1422d-259">I följande exempel är de poster som finns `ExclusionExtension` i listan markerade:</span><span class="sxs-lookup"><span data-stu-id="1422d-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![PowerShell-utdata för Get-MpPreference med undantagslistan tillsammans med andra inställningar](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="1422d-261">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="1422d-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="1422d-262">Hämta en specifik undantagslista med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="1422d-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="1422d-263">Använd följande kodavsnitt (ange varje rad som ett separat kommando). ersätt **WDAVprefs med** den etikett som du vill namnge variabeln:</span><span class="sxs-lookup"><span data-stu-id="1422d-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="1422d-264">I följande exempel är listan uppdelad i nya rader för varje användning av `Add-MpPreference` cmdleten:</span><span class="sxs-lookup"><span data-stu-id="1422d-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![PowerShell-utdata som bara visar posterna i undantagslistan](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="1422d-266">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="1422d-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="1422d-267">Validera undantagslistor med EICAR-testfilen</span><span class="sxs-lookup"><span data-stu-id="1422d-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="1422d-268">Du kan verifiera att undantagslistorna fungerar genom att använda PowerShell med `Invoke-WebRequest` antingen cmdleten eller .NET WebClient-klassen för att hämta en testfil.</span><span class="sxs-lookup"><span data-stu-id="1422d-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="1422d-269">I följande PowerShell-avsnitt ersätter *dutest.txt* med en fil som överensstämmer med dina undantagsregler.</span><span class="sxs-lookup"><span data-stu-id="1422d-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="1422d-270">Om du till exempel har utelämnat `.testing` tillägget ersätter du `test.txt` med `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="1422d-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="1422d-271">Om du testar en sökväg bör du kontrollera att du kör cmdleten inom den sökvägen.</span><span class="sxs-lookup"><span data-stu-id="1422d-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="1422d-272">Om Microsoft Defender Antivirus rapporterar skadlig programvara fungerar inte regeln.</span><span class="sxs-lookup"><span data-stu-id="1422d-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="1422d-273">Om det inte finns någon rapport om skadlig programvara och den hämtade filen finns fungerar undantaget.</span><span class="sxs-lookup"><span data-stu-id="1422d-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="1422d-274">Du kan öppna filen för att bekräfta att innehållet är detsamma som det som beskrivs på [EICAR-testfilens webbplats](http://www.eicar.org/86-0-Intended-use.html).</span><span class="sxs-lookup"><span data-stu-id="1422d-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="1422d-275">Du kan också använda följande PowerShell-kod som anropar .NET WebClient-klassen för att ladda ned testfilen – precis som med cmdleten – och ersättac:\test.txtmed en fil som överensstämmer med den regel som du `Invoke-WebRequest` validerar: </span><span class="sxs-lookup"><span data-stu-id="1422d-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="1422d-276">Om du inte har tillgång till Internet kan du skapa en egen EICAR-testfil genom att skriva EICAR-strängen till en ny textfil med följande PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="1422d-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="1422d-277">Du kan också kopiera strängen till en tom textfil och försöka spara den med filnamnet eller i mappen som du försöker utelämna.</span><span class="sxs-lookup"><span data-stu-id="1422d-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1422d-278">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1422d-278">Related topics</span></span>

- [<span data-ttu-id="1422d-279">Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="1422d-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1422d-280">Konfigurera och validera undantag för filer som öppnas i processer</span><span class="sxs-lookup"><span data-stu-id="1422d-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1422d-281">Konfigurera Microsoft Defender Antivirus undantag på Windows Server</span><span class="sxs-lookup"><span data-stu-id="1422d-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1422d-282">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="1422d-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
