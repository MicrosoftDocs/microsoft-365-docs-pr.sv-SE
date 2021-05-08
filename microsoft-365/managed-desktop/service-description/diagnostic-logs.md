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
# <a name="diagnostic-logs"></a>Diagnostikloggar

När vi felsöker ett problem på en enhet som hanteras av Microsoft Managed Desktop, oavsett om du har rapporterat eller en som identifieras av vår tjänst, kan vi behöva samla in vissa diagnostikloggar från enheten utan åtgärder från användaren. Vi samlar inte in något användargenererat innehåll eller information från användarkataloger. Vi samlar endast in diagnostik- och loggdata som rör enhetens hälsa och status.

Vi lagrar alla insamlade loggar i 28 dagar och tar sedan bort dem. Vi bearbetar alla loggar som samlas in från en enhet enligt våra [datahanteringsstandarder.](privacy-personal-data.md)

## <a name="data-collected"></a>Data som samlas in

Listan innehåller alla mappar, händelseloggar, körbara filer och registerplatser som Microsoft Managed Desktop kan samla in diagnostikloggar från. De faktiska data som samlas in är en delmängd av den här listan och beror på det identifierade problemet.

### <a name="registry-keys"></a>Registernycklar

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- HKLM \\ Software \\ Policies \\ Microsoft \\ WindowsStore
- HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch
- HKLM \\ SYSTEM \\ Setup
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows Advanced Threat Protection
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Authentication \\ LogonUI
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Internet Settings
- HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall
- \\ \\ HKLM-programvaruprinciper
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows Advanced Threat Protection
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Kommandon

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall show allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall show global
- %windir% \\ system32 \\netsh.exe lan visar profiler
- %windir% \\ system32 \\netsh.exe winhttp visa proxy
- %windir% \\ system32 \\netsh.exe wlan visa profiler
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /utförlig
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -mens -get
- Windows PowerShell-kommandon:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype bundle
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32-produkt \_
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Händelseloggar

- Program
- Microsoft-Windows-AppLocker/EXE och DLL
- Microsoft-Windows-AppLocker/MSI och skript
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Microsoft-Windows-Bitlocker/Bitlocker Management
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Installation
- System

### <a name="files"></a>Filer

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension-loggar \\ \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ loggar \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ servicing \\ sessions \\ActionList.xml
- %windir% \\ servicing \\ sessions \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt-loggar \\\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*