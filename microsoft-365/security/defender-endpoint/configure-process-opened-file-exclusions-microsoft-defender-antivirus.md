---
title: Konfigurera undantag för filer som öppnas av specifika processer
description: Du kan utesluta filer från genomsökningar om de har öppnats genom en viss process.
keywords: Microsoft Defender Antivirus, process, undantag, filer, genomsökningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 0470f4f03ba5fd6fc768a1e652f51b8c44207107
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925561"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="8b188-104">Konfigurera undantag för filer som öppnas av processer</span><span class="sxs-lookup"><span data-stu-id="8b188-104">Configure exclusions for files opened by processes</span></span>


<span data-ttu-id="8b188-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b188-105">**Applies to:**</span></span>

- [<span data-ttu-id="8b188-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b188-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8b188-107">Du kan utesluta filer som har öppnats av specifika processer från Microsoft Defender Antivirus genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="8b188-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="8b188-108">Läs Rekommendationer för att definiera undantag innan du definierar dina [undantagslistor.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="8b188-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="8b188-109">I den här artikeln beskrivs hur du konfigurerar undantagslistor.</span><span class="sxs-lookup"><span data-stu-id="8b188-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="8b188-110">Exempel på undantag</span><span class="sxs-lookup"><span data-stu-id="8b188-110">Examples of exclusions</span></span>

|<span data-ttu-id="8b188-111">Exkludering</span><span class="sxs-lookup"><span data-stu-id="8b188-111">Exclusion</span></span> | <span data-ttu-id="8b188-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="8b188-112">Example</span></span> |
|---|---|
|<span data-ttu-id="8b188-113">Alla filer på datorn som öppnas i valfri process med ett visst filnamn</span><span class="sxs-lookup"><span data-stu-id="8b188-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="8b188-114">När `test.exe` du anger utesluts filer som öppnas av:</span><span class="sxs-lookup"><span data-stu-id="8b188-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="8b188-115">Alla filer på datorn som öppnas i valfri process i en särskild mapp</span><span class="sxs-lookup"><span data-stu-id="8b188-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="8b188-116">När `c:\test\sample\*` du anger utesluts filer som öppnas av:</span><span class="sxs-lookup"><span data-stu-id="8b188-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="8b188-117">Alla filer på datorn som öppnas av en viss process i en särskild mapp</span><span class="sxs-lookup"><span data-stu-id="8b188-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="8b188-118">Om `c:\test\process.exe` du anger utesluts filer som endast öppnas av `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="8b188-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="8b188-119">När du lägger till en process i undantagslistan för processen Microsoft Defender Antivirus inte genomsöka filer som öppnas i den processen, oavsett var filerna finns.</span><span class="sxs-lookup"><span data-stu-id="8b188-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="8b188-120">Själva processen genomsöks dock om den inte också har lagts till i [filens undantagslista.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8b188-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8b188-121">Undantagen gäller endast [för realtidsskydd](configure-real-time-protection-microsoft-defender-antivirus.md)och övervakning.</span><span class="sxs-lookup"><span data-stu-id="8b188-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="8b188-122">De gäller inte för schemalagda genomsökningar eller sökningar på begäran.</span><span class="sxs-lookup"><span data-stu-id="8b188-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="8b188-123">Ändringar som görs med Grupprincip för **undantagslistorna visas** i listorna i [Windows-säkerhet program](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8b188-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="8b188-124">Men ändringar som görs i **Windows-säkerhet-programmet visas inte** i listorna grupprinciper.</span><span class="sxs-lookup"><span data-stu-id="8b188-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="8b188-125">Du kan lägga till, ta bort och granska listorna för undantag i Grupprincip, Microsoft Endpoint Configuration Manager, Microsoft Intune och med Windows-säkerhet-appen, och du kan använda jokertecken för att ytterligare anpassa listorna.</span><span class="sxs-lookup"><span data-stu-id="8b188-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="8b188-126">Du kan också använda PowerShell-cmdlets och WMI för att konfigurera undantagslistorna, inklusive att granska listorna.</span><span class="sxs-lookup"><span data-stu-id="8b188-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="8b188-127">Som standard sammanfogas lokala ändringar som gjorts i listorna (av användare med administratörsbehörighet, ändringar som görs med PowerShell och WMI) med listorna som definierade (och distribuerade) av Grupprincip, Configuration Manager eller Intune.</span><span class="sxs-lookup"><span data-stu-id="8b188-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="8b188-128">Grupprinciplistorna har företräde vid konflikter.</span><span class="sxs-lookup"><span data-stu-id="8b188-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="8b188-129">Du kan [konfigurera hur lokalt och globalt definierade undantagslistor slås samman så](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) att lokala ändringar åsidosätter inställningar för hanterad distribution.</span><span class="sxs-lookup"><span data-stu-id="8b188-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="8b188-130">Konfigurera listan över undantag för filer som öppnas av angivna processer</span><span class="sxs-lookup"><span data-stu-id="8b188-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-131">Använda Microsoft Intune för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="8b188-132">För mer information läs [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure) och [Inställningar för enhetsbegränsning för Microsoft Defender i Windows 10 i Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="8b188-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-133">Använda Microsoft Endpoint Manager för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="8b188-134">Se [Skapa och distribuera principer för program mot skadlig programvara: Undantagsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) för information om konfigurering av Microsoft Endpoint Manager (current branch).</span><span class="sxs-lookup"><span data-stu-id="8b188-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-135">Använd grupprinciper för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="8b188-136">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="8b188-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8b188-137">I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="8b188-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="8b188-138">Expandera trädet och visa **Windows komponenter > Microsoft Defender Antivirus > Undantag**.</span><span class="sxs-lookup"><span data-stu-id="8b188-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="8b188-139">Dubbelklicka på **Undantag för process** och lägg till undantagen:</span><span class="sxs-lookup"><span data-stu-id="8b188-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="8b188-140">Ställ in alternativet som **Aktiverat**.</span><span class="sxs-lookup"><span data-stu-id="8b188-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="8b188-141">I avsnittet **Alternativ** klickar du på **Visa...**.</span><span class="sxs-lookup"><span data-stu-id="8b188-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="8b188-142">Ange varje process på en egen rad under **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="8b188-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="8b188-143">Se exempeltabellen för de olika typerna av undantag för processer.</span><span class="sxs-lookup"><span data-stu-id="8b188-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="8b188-144">Ange **0** i **kolumnen Värde** för alla processer.</span><span class="sxs-lookup"><span data-stu-id="8b188-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="8b188-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b188-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-146">Använd PowerShell-cmdlets för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="8b188-147">Om du använder PowerShell för att lägga till eller ta bort undantag för filer som har öppnats i processer krävs en kombination av tre cmdlets med `-ExclusionProcess` parametern.</span><span class="sxs-lookup"><span data-stu-id="8b188-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="8b188-148">Cmdletarna finns i [Defender-modulen.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="8b188-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="8b188-149">Formatet för cmdletarna är:</span><span class="sxs-lookup"><span data-stu-id="8b188-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="8b188-150">Följande tillåts \<cmdlet> som:</span><span class="sxs-lookup"><span data-stu-id="8b188-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="8b188-151">Konfigurationsåtgärd</span><span class="sxs-lookup"><span data-stu-id="8b188-151">Configuration action</span></span> | <span data-ttu-id="8b188-152">PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="8b188-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="8b188-153">Skapa eller skriva över listan</span><span class="sxs-lookup"><span data-stu-id="8b188-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="8b188-154">Lägg till i listan</span><span class="sxs-lookup"><span data-stu-id="8b188-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="8b188-155">Ta bort objekt från listan</span><span class="sxs-lookup"><span data-stu-id="8b188-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="8b188-156">Om du har skapat en lista med eller skriver du över den befintliga listan med hjälp av `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdleten igen.</span><span class="sxs-lookup"><span data-stu-id="8b188-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="8b188-157">Följande kodavsnitt skulle till exempel göra att Microsoft Defender AV-genomsökningar utesluter alla filer som öppnas i den angivna processen:</span><span class="sxs-lookup"><span data-stu-id="8b188-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="8b188-158">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Hantera antivirus med PowerShell-cmdlets [och Microsoft Defender Antivirus-cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="8b188-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-159">Använd Windows för hanteringsinstruktioner (WMI) för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="8b188-160">Använd metoderna [ **Ange,** **Lägg** till **och Ta** bort **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) klassen för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="8b188-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="8b188-161">Användandet av **Set**, **Add** och **Remove kan** jämföras med deras motsvarigheter i PowerShell: , `Set-MpPreference` och `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="8b188-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="8b188-162">Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="8b188-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="8b188-163">Använd Windows-säkerhet för att utesluta filer som har öppnats av angivna processer från genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="8b188-164">Anvisningar [finns i Lägga till undantag Windows-säkerhet appen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8b188-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="8b188-165">Använda jokertecken i undantagslistan för processer</span><span class="sxs-lookup"><span data-stu-id="8b188-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="8b188-166">Användningen av jokertecken i processens undantagslista skiljer sig från användningen i andra undantagslistor.</span><span class="sxs-lookup"><span data-stu-id="8b188-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="8b188-167">I synnerhet kan du inte använda jokertecknet ( ) och asterisken ( ) kan bara användas i slutet av `?` `*` en fullständig sökväg.</span><span class="sxs-lookup"><span data-stu-id="8b188-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="8b188-168">Du kan fortfarande använda miljövariabler (till exempel `%ALLUSERSPROFILE%` ) som jokertecken när du definierar objekt i undantagslistan för processen.</span><span class="sxs-lookup"><span data-stu-id="8b188-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="8b188-169">I följande tabell beskrivs hur jokertecken kan användas i processens undantagslista:</span><span class="sxs-lookup"><span data-stu-id="8b188-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="8b188-170">Jokertecken</span><span class="sxs-lookup"><span data-stu-id="8b188-170">Wildcard</span></span> | <span data-ttu-id="8b188-171">Exempel på användning</span><span class="sxs-lookup"><span data-stu-id="8b188-171">Example use</span></span> | <span data-ttu-id="8b188-172">Exempelmatchning</span><span class="sxs-lookup"><span data-stu-id="8b188-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="8b188-173">`*` (asterisk)</span><span class="sxs-lookup"><span data-stu-id="8b188-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="8b188-174">Ersätter valbara antal tecken</span><span class="sxs-lookup"><span data-stu-id="8b188-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="8b188-175">Alla filer som öppnas av `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="8b188-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="8b188-176">Miljövariabler</span><span class="sxs-lookup"><span data-stu-id="8b188-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="8b188-177">Den definierade variabeln fylls i som en sökväg när undantaget beräknas</span><span class="sxs-lookup"><span data-stu-id="8b188-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="8b188-178">Alla filer som öppnas av `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="8b188-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="8b188-179">Granska listan över undantag</span><span class="sxs-lookup"><span data-stu-id="8b188-179">Review the list of exclusions</span></span>

<span data-ttu-id="8b188-180">Du kan hämta objekten i undantagslistan med MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure) [eller Windows-säkerhet-appen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8b188-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="8b188-181">Om du använder PowerShell kan du hämta listan på två sätt:</span><span class="sxs-lookup"><span data-stu-id="8b188-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="8b188-182">Hämta status för alla Microsoft Defender Antivirus inställningar.</span><span class="sxs-lookup"><span data-stu-id="8b188-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="8b188-183">Var och en av listorna visas på separata rader, men objekten i varje lista kombineras på samma rad.</span><span class="sxs-lookup"><span data-stu-id="8b188-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="8b188-184">Skriv statusen för alla inställningar till en variabel och använd den variabeln för att bara anropa den specifika listan som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="8b188-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="8b188-185">Varje användning av `Add-MpPreference` skrivs till en ny rad.</span><span class="sxs-lookup"><span data-stu-id="8b188-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="8b188-186">Validera undantagslistan med hjälp av MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="8b188-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="8b188-187">Om du vill kontrollera undantag med det [dedikerade kommandoradsverktyget mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)använder du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8b188-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="8b188-188">Kontroll av undantag med MpCmdRun kräver Microsoft Defender Antivirus CAMP version 4.18.1812.3 (utgiven i december 2018) eller senare.</span><span class="sxs-lookup"><span data-stu-id="8b188-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="8b188-189">Granska listan över undantag tillsammans med alla andra alternativ Microsoft Defender Antivirus med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b188-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="8b188-190">Använd följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8b188-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="8b188-191">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8b188-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="8b188-192">Hämta en specifik undantagslista med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b188-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="8b188-193">Använd följande kodavsnitt (ange varje rad som ett separat kommando). ersätt **WDAVprefs med** den etikett som du vill namnge variabeln:</span><span class="sxs-lookup"><span data-stu-id="8b188-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="8b188-194">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8b188-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8b188-195">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="8b188-195">Related articles</span></span>

- [<span data-ttu-id="8b188-196">Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="8b188-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8b188-197">Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="8b188-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8b188-198">Konfigurera Microsoft Defender Antivirus undantag på Windows Server</span><span class="sxs-lookup"><span data-stu-id="8b188-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8b188-199">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="8b188-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8b188-200">Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder</span><span class="sxs-lookup"><span data-stu-id="8b188-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8b188-201">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="8b188-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
