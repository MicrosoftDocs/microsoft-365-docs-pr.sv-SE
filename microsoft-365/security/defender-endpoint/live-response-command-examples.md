---
title: Kommandoexempel för livesvar
description: Lär dig hur du kör grundläggande eller avancerade livesvarskommandon för Microsoft Defender för Endpoint och se exempel på hur det används.
keywords: exempel, kommando, cli, remote, shell, connection, live, response, real-time, kommando, skript, åtgärda, leta, exportera, logga, släppa, ladda ned, fil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 389d9ad4a3e5fc876e7bded89389202e95bfda45
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879126"
---
# <a name="live-response-command-examples"></a>Kommandoexempel för livesvar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Läs mer om vanliga kommandon som används i live-svar och se exempel på hur de vanligtvis används.

Beroende på vilken roll du har beviljats kan du köra grundläggande eller avancerade kommandon för livesvar. Mer information om grundläggande och avancerade kommandon finns i Undersöka [enheter på enheter med live-svar.](live-response.md)


## <a name="analyze"></a>analysera 

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>anslutningar

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a>filinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> Följande filtyper kan **inte laddas** ned med det här kommandot inifrån Live Response:
>
> * [Separera punktfiler](/windows/desktop/fileio/reparse-points/)
> * [Sparsamta filer](/windows/desktop/fileio/sparse-files/)
> * Tomma filer
> * Virtuella filer eller filer som inte finns helt lokalt
>
> De här **filtyperna** stöds av [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)
>
> Använd PowerShell som ett alternativ om du har problem med det här kommandot inifrån Live Response.

## <a name="processes"></a>processer
```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a>putfile

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a>register

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>åtgärda

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a>kör

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> För långvariga kommandon som '**run**' eller '**getfile**' kanske du vill använda symbolen ' ' i slutet av kommandot för att utföra den **&** åtgärden i bakgrunden.
> Det gör att du kan fortsätta att undersöka datorn och återgå till bakgrundskommandot när du är klar med '**fg**' [basic-kommandot](live-response.md#basic-commands).
>
## <a name="scheduledtask"></a>scheduledtask

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a>ångra

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```


## <a name="library"></a>bibliotek

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```
