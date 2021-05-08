---
title: Konfigurera Microsoft Defender Antivirus undantag på Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Servern innehåller automatiska undantag, baserat på serverroll. Du kan också lägga till anpassade undantag.
keywords: undantag, server, automatisk exkludering, automatisk, anpassad, genomsökning och Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274766"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="e28da-105">Konfigurera Microsoft Defender Antivirus undantag på Windows Server</span><span class="sxs-lookup"><span data-stu-id="e28da-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e28da-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e28da-106">**Applies to:**</span></span>

- [<span data-ttu-id="e28da-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e28da-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e28da-108">Microsoft Defender Antivirus på Windows Server 2016 och Windows Server 2019 automatiskt registrerar dig i vissa undantag, som definieras av din angivna serverroll.</span><span class="sxs-lookup"><span data-stu-id="e28da-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="e28da-109">Undantagen visas inte i de standard undantagslistor som visas i [Windows-säkerhet programmet](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="e28da-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e28da-110">Automatiska undantag gäller endast för RTP-skanning (Real-time protection).</span><span class="sxs-lookup"><span data-stu-id="e28da-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="e28da-111">Automatiska undantag respekteras inte vid en genomsökning av fullständiga/snabba eller på begäran.</span><span class="sxs-lookup"><span data-stu-id="e28da-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="e28da-112">Förutom serverrolldefinierade automatiska undantag kan du lägga till eller ta bort anpassade undantag.</span><span class="sxs-lookup"><span data-stu-id="e28da-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="e28da-113">Information om hur du gör det finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="e28da-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="e28da-114">Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="e28da-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-115">Konfigurera och validera undantag för filer som öppnas i processer</span><span class="sxs-lookup"><span data-stu-id="e28da-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="e28da-116">Några saker att tänka på</span><span class="sxs-lookup"><span data-stu-id="e28da-116">A few points to keep in mind</span></span>

<span data-ttu-id="e28da-117">Tänk på följande:</span><span class="sxs-lookup"><span data-stu-id="e28da-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="e28da-118">Anpassade undantag har företräde framför automatiska undantag.</span><span class="sxs-lookup"><span data-stu-id="e28da-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="e28da-119">Automatiska undantag gäller endast för RTP-skanning (Real-time protection).</span><span class="sxs-lookup"><span data-stu-id="e28da-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="e28da-120">Automatiska undantag respekteras inte vid en genomsökning av fullständiga/snabba eller på begäran.</span><span class="sxs-lookup"><span data-stu-id="e28da-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="e28da-121">Undantag för anpassade och dubbletter står inte i konflikt med automatiska undantag.</span><span class="sxs-lookup"><span data-stu-id="e28da-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="e28da-122">Microsoft Defender Antivirus använder DISM-verktygen (Deployment Image Servicing and Management) för att avgöra vilka roller som är installerade på datorn.</span><span class="sxs-lookup"><span data-stu-id="e28da-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="e28da-123">Välja bort automatiska undantag</span><span class="sxs-lookup"><span data-stu-id="e28da-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="e28da-124">I Windows Server 2016 och Windows Server 2019 exkluderar de fördefinierade undantagen som levereras av säkerhetsintelligensuppdateringar endast standardsökvägarna för en roll eller funktion.</span><span class="sxs-lookup"><span data-stu-id="e28da-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="e28da-125">Om du har installerat en roll eller funktion i en anpassad sökväg, eller om du manuellt vill styra uppsättningen undantag, måste du välja bort automatiska undantag som levereras i säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="e28da-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="e28da-126">Men kom ihåg att undantagen som levereras automatiskt är optimerade för Windows Server 2016- och 2019-roller.</span><span class="sxs-lookup"><span data-stu-id="e28da-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="e28da-127">Läs Rekommendationer för att definiera undantag innan du definierar dina [undantagslistor.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="e28da-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="e28da-128">Om du väljer bort automatiska undantag kan det påverka prestandan negativt eller resultera i skadade data.</span><span class="sxs-lookup"><span data-stu-id="e28da-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="e28da-129">Undantagen som levereras automatiskt optimeras för Windows Server 2016 och Windows Server 2019-roller.</span><span class="sxs-lookup"><span data-stu-id="e28da-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="e28da-130">Eftersom fördefinierade undantag bara exkluderar standardsökvägar måste du lägga till undantag manuellt med hjälp av informationen här om du flyttar NTDS och SYSVOL till en annan enhet eller sökväg som skiljer sig från den ursprungliga [sökvägen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="e28da-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="e28da-131">Du kan inaktivera automatiska undantagslistor med Grupprincip, PowerShell-cmdlets och WMI.</span><span class="sxs-lookup"><span data-stu-id="e28da-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="e28da-132">Använd grupprinciper för att inaktivera listan med automatiska undantag i Windows Server 2016 och Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e28da-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="e28da-133">Öppna konsolen Grupprinciphantering på datorn [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="e28da-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="e28da-134">Högerklicka på det grupprincipobjekt du vill konfigurera och klicka sedan på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="e28da-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="e28da-135">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** och klickar sedan på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="e28da-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="e28da-136">Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Undantag**.</span><span class="sxs-lookup"><span data-stu-id="e28da-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="e28da-137">Dubbelklicka på **Inaktivera automatiska undantag och** ställ in alternativet på **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="e28da-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="e28da-138">Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e28da-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="e28da-139">Använd PowerShell-cmdlets för att inaktivera listan över undantag automatiskt Windows Server 2016 och 2019</span><span class="sxs-lookup"><span data-stu-id="e28da-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="e28da-140">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e28da-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="e28da-141">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="e28da-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="e28da-142">[Använd PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="e28da-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="e28da-143">[Använd PowerShell med Microsoft Defender Antivirus](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="e28da-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="e28da-144">Använd Windows för hanteringsinstruktioner (WMI) för att inaktivera listan över automatiska undantag i Windows Server 2016 och Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e28da-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="e28da-145">Använd **metoden** Set för [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="e28da-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="e28da-146">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="e28da-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="e28da-147">Windows Defender WMIv2-API:er</span><span class="sxs-lookup"><span data-stu-id="e28da-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="e28da-148">Lista över automatiska undantag</span><span class="sxs-lookup"><span data-stu-id="e28da-148">List of automatic exclusions</span></span>

<span data-ttu-id="e28da-149">Följande avsnitt innehåller undantag som levereras med automatiska undantag för filsökvägar och filtyper.</span><span class="sxs-lookup"><span data-stu-id="e28da-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="e28da-150">Standard undantag för alla roller</span><span class="sxs-lookup"><span data-stu-id="e28da-150">Default exclusions for all roles</span></span>

<span data-ttu-id="e28da-151">Det här avsnittet innehåller standard undantag för alla Windows Server 2016 och 2019-roller.</span><span class="sxs-lookup"><span data-stu-id="e28da-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="e28da-152">Standardplatserna kan vara annorlunda än de som anges i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e28da-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="e28da-153">Windows "temp.edb"-filer</span><span class="sxs-lookup"><span data-stu-id="e28da-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="e28da-154">Windows Uppdatera filer eller automatiska uppdateringsfiler</span><span class="sxs-lookup"><span data-stu-id="e28da-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="e28da-155">Windows-säkerhet filer</span><span class="sxs-lookup"><span data-stu-id="e28da-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="e28da-156">Grupprincipfiler</span><span class="sxs-lookup"><span data-stu-id="e28da-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="e28da-157">WINS-filer</span><span class="sxs-lookup"><span data-stu-id="e28da-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="e28da-158">Undantag för File Replication Service (FRS)</span><span class="sxs-lookup"><span data-stu-id="e28da-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="e28da-159">Filer i FRS-arbetsmappen (File Replication Service).</span><span class="sxs-lookup"><span data-stu-id="e28da-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="e28da-160">Arbetsmappen FRS anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="e28da-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="e28da-161">FRS-databasloggfiler.</span><span class="sxs-lookup"><span data-stu-id="e28da-161">FRS Database log files.</span></span> <span data-ttu-id="e28da-162">Loggfilmappen för FRS-databasen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="e28da-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="e28da-163">Mellanlagringsmappen FRS.</span><span class="sxs-lookup"><span data-stu-id="e28da-163">The FRS staging folder.</span></span> <span data-ttu-id="e28da-164">Mellanlagringsmappen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="e28da-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="e28da-165">Förinstallera mappen FRS.</span><span class="sxs-lookup"><span data-stu-id="e28da-165">The FRS preinstall folder.</span></span> <span data-ttu-id="e28da-166">Den här mappen anges av mappen `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="e28da-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="e28da-167">The Distributed File System Replication (HURR) databas och arbetsmappar.</span><span class="sxs-lookup"><span data-stu-id="e28da-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="e28da-168">Dessa mappar anges av registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="e28da-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="e28da-169">Information om anpassade platser finns [i Välja bort automatiska undantag.](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="e28da-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="e28da-170">Undantag från processer</span><span class="sxs-lookup"><span data-stu-id="e28da-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="e28da-171">Hyper-V-undantag</span><span class="sxs-lookup"><span data-stu-id="e28da-171">Hyper-V exclusions</span></span>

<span data-ttu-id="e28da-172">I följande tabell visas undantag för filtyper, undantag för mappar och processkludering som levereras automatiskt när du installerar rollen Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="e28da-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="e28da-173">Undantag för filtyp</span><span class="sxs-lookup"><span data-stu-id="e28da-173">File type exclusions</span></span> |<span data-ttu-id="e28da-174">Undantag för mappar</span><span class="sxs-lookup"><span data-stu-id="e28da-174">Folder exclusions</span></span>  | <span data-ttu-id="e28da-175">Undantag från processer</span><span class="sxs-lookup"><span data-stu-id="e28da-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="e28da-176">SYSVOL-filer</span><span class="sxs-lookup"><span data-stu-id="e28da-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="e28da-177">Undantag för Active Directory</span><span class="sxs-lookup"><span data-stu-id="e28da-177">Active Directory exclusions</span></span>

<span data-ttu-id="e28da-178">Det här avsnittet innehåller en lista över undantag som levereras automatiskt när du installerar Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="e28da-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="e28da-179">NTDS-databasfiler</span><span class="sxs-lookup"><span data-stu-id="e28da-179">NTDS database files</span></span>

<span data-ttu-id="e28da-180">Databasfilerna anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="e28da-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="e28da-181">AD DS-transaktionsloggfilerna</span><span class="sxs-lookup"><span data-stu-id="e28da-181">The AD DS transaction log files</span></span>

<span data-ttu-id="e28da-182">Transaktionsloggfilerna anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="e28da-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="e28da-183">Ntds-arbetsmappen</span><span class="sxs-lookup"><span data-stu-id="e28da-183">The NTDS working folder</span></span>

<span data-ttu-id="e28da-184">Den här mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="e28da-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="e28da-185">Process undantas för AD DS- och AD DS-relaterade supportfiler</span><span class="sxs-lookup"><span data-stu-id="e28da-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="e28da-186">UNDANTAG för VAR OCH EN-server</span><span class="sxs-lookup"><span data-stu-id="e28da-186">DHCP Server exclusions</span></span>

<span data-ttu-id="e28da-187">Det här avsnittet innehåller en lista över undantag som levereras automatiskt när du installerar rollen TIDESERVER.</span><span class="sxs-lookup"><span data-stu-id="e28da-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="e28da-188">TIDSFILSFILplatserna anges av parametrarna *DatabasePath,LogiFilePath* och *BackupDatabasePath* i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="e28da-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="e28da-189">Undantag för DNS Server</span><span class="sxs-lookup"><span data-stu-id="e28da-189">DNS Server exclusions</span></span>

<span data-ttu-id="e28da-190">I det här avsnittet visas undantag för filer och mappar och undantag från processer som levereras automatiskt när du installerar DNS-serverrollen.</span><span class="sxs-lookup"><span data-stu-id="e28da-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="e28da-191">Undantag för filer och mappar för DNS-serverrollen</span><span class="sxs-lookup"><span data-stu-id="e28da-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="e28da-192">Process undantas för DNS Server-rollen</span><span class="sxs-lookup"><span data-stu-id="e28da-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="e28da-193">Undantag för Storage Fil- och Storage tjänster</span><span class="sxs-lookup"><span data-stu-id="e28da-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="e28da-194">Det här avsnittet innehåller undantag för filer och mappar som levereras automatiskt när du installerar rollen Arkiv Storage Tjänster.</span><span class="sxs-lookup"><span data-stu-id="e28da-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="e28da-195">Undantag som visas nedan inkluderar inte undantag för rollen Gruppering.</span><span class="sxs-lookup"><span data-stu-id="e28da-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="e28da-196">Undantag för Print Server</span><span class="sxs-lookup"><span data-stu-id="e28da-196">Print Server exclusions</span></span>

<span data-ttu-id="e28da-197">I det här avsnittet visas en lista över undantag för filtyper, undantag för mappar och processkludering som levereras automatiskt när du installerar rollen Skriv ut server.</span><span class="sxs-lookup"><span data-stu-id="e28da-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="e28da-198">Undantag för filtyp</span><span class="sxs-lookup"><span data-stu-id="e28da-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="e28da-199">Undantag för mappar</span><span class="sxs-lookup"><span data-stu-id="e28da-199">Folder exclusions</span></span>

<span data-ttu-id="e28da-200">Den här mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="e28da-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="e28da-201">Undantag från processer</span><span class="sxs-lookup"><span data-stu-id="e28da-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="e28da-202">Undantag för webbserver</span><span class="sxs-lookup"><span data-stu-id="e28da-202">Web Server exclusions</span></span>

<span data-ttu-id="e28da-203">Det här avsnittet innehåller en lista över undantag för mappar och processkludering som levereras automatiskt när du installerar webbserverrollen.</span><span class="sxs-lookup"><span data-stu-id="e28da-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="e28da-204">Undantag för mappar</span><span class="sxs-lookup"><span data-stu-id="e28da-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="e28da-205">Undantag från processer</span><span class="sxs-lookup"><span data-stu-id="e28da-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="e28da-206">Stänga av genomsökning av filer i mappen Sysvol\Sysvol eller mappen SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="e28da-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="e28da-207">Den aktuella platsen för eller mappen och alla undermappar är filsystemets mappmål för `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` replikuppsättningens rot.</span><span class="sxs-lookup"><span data-stu-id="e28da-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="e28da-208">I `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` mapparna och används som standard följande platser:</span><span class="sxs-lookup"><span data-stu-id="e28da-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="e28da-209">Sökvägen till den aktiva resursen refereras till av NETLOGON-resursen och kan fastställas av `SYSVOL` SysVol-värdenamnet i följande undernyckel: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="e28da-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="e28da-210">Undanta följande filer från den här mappen och alla dess undermappar:</span><span class="sxs-lookup"><span data-stu-id="e28da-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="e28da-211">Windows Server Update Services undantag</span><span class="sxs-lookup"><span data-stu-id="e28da-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="e28da-212">Det här avsnittet innehåller en lista över undantag för mappar som levereras automatiskt när du installerar Windows Server Update Services rollen (WSUS).</span><span class="sxs-lookup"><span data-stu-id="e28da-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="e28da-213">WSUS-mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="e28da-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="e28da-214">Se även</span><span class="sxs-lookup"><span data-stu-id="e28da-214">See also</span></span>

- [<span data-ttu-id="e28da-215">Konfigurera och validera undantag för Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="e28da-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-216">Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="e28da-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-217">Konfigurera och validera undantag för filer som öppnas i processer</span><span class="sxs-lookup"><span data-stu-id="e28da-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-218">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="e28da-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-219">Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder</span><span class="sxs-lookup"><span data-stu-id="e28da-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e28da-220">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="e28da-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)