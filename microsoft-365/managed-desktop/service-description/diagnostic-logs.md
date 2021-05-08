---
title: Diagnostikloggar
description: Loggar som kan samlas in från enheter under felsökning och hur de lagras
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272901"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="adea2-104">Diagnostikloggar</span><span class="sxs-lookup"><span data-stu-id="adea2-104">Diagnostic logs</span></span>

<span data-ttu-id="adea2-105">När vi felsöker ett problem på en enhet som hanteras av Microsoft Managed Desktop, oavsett om du har rapporterat eller en som identifieras av vår tjänst, kan vi behöva samla in vissa diagnostikloggar från enheten utan åtgärder från användaren.</span><span class="sxs-lookup"><span data-stu-id="adea2-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="adea2-106">Vi samlar inte in något användargenererat innehåll eller information från användarkataloger.</span><span class="sxs-lookup"><span data-stu-id="adea2-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="adea2-107">Vi samlar endast in diagnostik- och loggdata som rör enhetens hälsa och status.</span><span class="sxs-lookup"><span data-stu-id="adea2-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="adea2-108">Vi lagrar alla insamlade loggar i 28 dagar och tar sedan bort dem.</span><span class="sxs-lookup"><span data-stu-id="adea2-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="adea2-109">Vi bearbetar alla loggar som samlas in från en enhet enligt våra [datahanteringsstandarder.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="adea2-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="adea2-110">Data som samlas in</span><span class="sxs-lookup"><span data-stu-id="adea2-110">Data collected</span></span>

<span data-ttu-id="adea2-111">Listan innehåller alla mappar, händelseloggar, körbara filer och registerplatser som Microsoft Managed Desktop kan samla in diagnostikloggar från.</span><span class="sxs-lookup"><span data-stu-id="adea2-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="adea2-112">De faktiska data som samlas in är en delmängd av den här listan och beror på det identifierade problemet.</span><span class="sxs-lookup"><span data-stu-id="adea2-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="adea2-113">Registernycklar</span><span class="sxs-lookup"><span data-stu-id="adea2-113">Registry keys</span></span>

- <span data-ttu-id="adea2-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="adea2-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="adea2-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="adea2-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="adea2-116">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="adea2-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="adea2-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="adea2-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="adea2-118">HKLM \\ Software \\ Policies \\ Microsoft \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="adea2-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="adea2-119">HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="adea2-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="adea2-120">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="adea2-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="adea2-121">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="adea2-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="adea2-122">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="adea2-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="adea2-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="adea2-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="adea2-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="adea2-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="adea2-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="adea2-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="adea2-126">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="adea2-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="adea2-127">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="adea2-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="adea2-128">HKLM \\ SYSTEM \\ Setup</span><span class="sxs-lookup"><span data-stu-id="adea2-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="adea2-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="adea2-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="adea2-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="adea2-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="adea2-131">HKLM \\ SOFTWARE \\ Microsoft \\ Windows Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="adea2-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="adea2-132">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Authentication \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="adea2-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="adea2-133">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Internet Settings</span><span class="sxs-lookup"><span data-stu-id="adea2-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="adea2-134">HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="adea2-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="adea2-135">\\ \\ HKLM-programvaruprinciper</span><span class="sxs-lookup"><span data-stu-id="adea2-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="adea2-136">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="adea2-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="adea2-137">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="adea2-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="adea2-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="adea2-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="adea2-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="adea2-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="adea2-140">Kommandon</span><span class="sxs-lookup"><span data-stu-id="adea2-140">Commands</span></span>

- <span data-ttu-id="adea2-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="adea2-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="adea2-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="adea2-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="adea2-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="adea2-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="adea2-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="adea2-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="adea2-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="adea2-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="adea2-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="adea2-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="adea2-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="adea2-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="adea2-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="adea2-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="adea2-149">%windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="adea2-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="adea2-150">%windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="adea2-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="adea2-151">%windir% \\ system32 \\netsh.exe lan visar profiler</span><span class="sxs-lookup"><span data-stu-id="adea2-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="adea2-152">%windir% \\ system32 \\netsh.exe winhttp visa proxy</span><span class="sxs-lookup"><span data-stu-id="adea2-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="adea2-153">%windir% \\ system32 \\netsh.exe wlan visa profiler</span><span class="sxs-lookup"><span data-stu-id="adea2-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="adea2-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="adea2-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="adea2-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="adea2-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="adea2-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="adea2-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="adea2-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="adea2-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="adea2-158">bitsadmin /list /allusers /utförlig</span><span class="sxs-lookup"><span data-stu-id="adea2-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="adea2-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="adea2-159">fltMC.exe</span></span>
- <span data-ttu-id="adea2-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="adea2-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="adea2-161">manage-bde -mens -get</span><span class="sxs-lookup"><span data-stu-id="adea2-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="adea2-162">Windows PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="adea2-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="adea2-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="adea2-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="adea2-164">Get-appxpackage -packagetype bundle</span><span class="sxs-lookup"><span data-stu-id="adea2-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="adea2-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="adea2-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="adea2-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="adea2-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="adea2-167">Get-WmiObject -Class win32-produkt \_</span><span class="sxs-lookup"><span data-stu-id="adea2-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="adea2-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="adea2-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="adea2-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="adea2-169">Get-Service</span></span>
    - <span data-ttu-id="adea2-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="adea2-170">Get-Process</span></span>
    - <span data-ttu-id="adea2-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="adea2-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="adea2-172">Händelseloggar</span><span class="sxs-lookup"><span data-stu-id="adea2-172">Event logs</span></span>

- <span data-ttu-id="adea2-173">Program</span><span class="sxs-lookup"><span data-stu-id="adea2-173">Application</span></span>
- <span data-ttu-id="adea2-174">Microsoft-Windows-AppLocker/EXE och DLL</span><span class="sxs-lookup"><span data-stu-id="adea2-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="adea2-175">Microsoft-Windows-AppLocker/MSI och skript</span><span class="sxs-lookup"><span data-stu-id="adea2-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="adea2-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="adea2-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="adea2-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="adea2-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="adea2-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span><span class="sxs-lookup"><span data-stu-id="adea2-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="adea2-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="adea2-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="adea2-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="adea2-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="adea2-181">Installation</span><span class="sxs-lookup"><span data-stu-id="adea2-181">Setup</span></span>
- <span data-ttu-id="adea2-182">System</span><span class="sxs-lookup"><span data-stu-id="adea2-182">System</span></span>

### <a name="files"></a><span data-ttu-id="adea2-183">Filer</span><span class="sxs-lookup"><span data-stu-id="adea2-183">Files</span></span>

- <span data-ttu-id="adea2-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="adea2-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="adea2-185">%ProgramData% \\ Microsoft \\ IntuneManagementExtension-loggar \\ \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="adea2-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="adea2-186">%ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="adea2-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="adea2-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="adea2-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="adea2-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="adea2-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="adea2-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="adea2-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="adea2-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="adea2-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="adea2-191">%windir% \\ loggar \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="adea2-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="adea2-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="adea2-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="adea2-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="adea2-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="adea2-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="adea2-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="adea2-195">%windir% \\ servicing \\ sessions \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="adea2-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="adea2-196">%windir% \\ servicing \\ sessions \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="adea2-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="adea2-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="adea2-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="adea2-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="adea2-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="adea2-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="adea2-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="adea2-200">%SystemRoot% \\ System32 \\ Winevt-loggar </span><span class="sxs-lookup"><span data-stu-id="adea2-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\\\
- <span data-ttu-id="adea2-201">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="adea2-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="adea2-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="adea2-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="adea2-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="adea2-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="adea2-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="adea2-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="adea2-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="adea2-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>