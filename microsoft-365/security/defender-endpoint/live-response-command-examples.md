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
ms.openlocfilehash: f08f20753a1f0926abbbce01fe97f20ef1c07f2c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689097"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="85c5d-104">Kommandoexempel för livesvar</span><span class="sxs-lookup"><span data-stu-id="85c5d-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="85c5d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="85c5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="85c5d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="85c5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="85c5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85c5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="85c5d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="85c5d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85c5d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="85c5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="85c5d-110">Läs mer om vanliga kommandon som används i live-svar och se exempel på hur de vanligtvis används.</span><span class="sxs-lookup"><span data-stu-id="85c5d-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="85c5d-111">Beroende på vilken roll du har beviljats kan du köra grundläggande eller avancerade kommandon för livesvar.</span><span class="sxs-lookup"><span data-stu-id="85c5d-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="85c5d-112">Mer information om grundläggande och avancerade kommandon finns i Undersöka [enheter på enheter med live-svar.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="85c5d-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="85c5d-113">analysera</span><span class="sxs-lookup"><span data-stu-id="85c5d-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="85c5d-114">anslutningar</span><span class="sxs-lookup"><span data-stu-id="85c5d-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="85c5d-115">dir</span><span class="sxs-lookup"><span data-stu-id="85c5d-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="85c5d-116">filinfo</span><span class="sxs-lookup"><span data-stu-id="85c5d-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="85c5d-117">findfile</span><span class="sxs-lookup"><span data-stu-id="85c5d-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="85c5d-118">getfile</span><span class="sxs-lookup"><span data-stu-id="85c5d-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="85c5d-119">Följande filtyper kan **inte laddas** ned med det här kommandot inifrån Live Response:</span><span class="sxs-lookup"><span data-stu-id="85c5d-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="85c5d-120">Separera punktfiler</span><span class="sxs-lookup"><span data-stu-id="85c5d-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="85c5d-121">Sparsamta filer</span><span class="sxs-lookup"><span data-stu-id="85c5d-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="85c5d-122">Tomma filer</span><span class="sxs-lookup"><span data-stu-id="85c5d-122">Empty files</span></span>
> * <span data-ttu-id="85c5d-123">Virtuella filer eller filer som inte finns helt lokalt</span><span class="sxs-lookup"><span data-stu-id="85c5d-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="85c5d-124">De här **filtyperna** stöds av [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="85c5d-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="85c5d-125">Använd PowerShell som ett alternativ om du har problem med det här kommandot inifrån Live Response.</span><span class="sxs-lookup"><span data-stu-id="85c5d-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="85c5d-126">processer</span><span class="sxs-lookup"><span data-stu-id="85c5d-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="85c5d-127">putfile</span><span class="sxs-lookup"><span data-stu-id="85c5d-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="85c5d-128">register</span><span class="sxs-lookup"><span data-stu-id="85c5d-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="85c5d-129">åtgärda</span><span class="sxs-lookup"><span data-stu-id="85c5d-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="85c5d-130">kör</span><span class="sxs-lookup"><span data-stu-id="85c5d-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="85c5d-131">För långvariga kommandon som '**run**' eller '**getfile**' kanske du vill använda symbolen ' ' i slutet av kommandot för att utföra den **&** åtgärden i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="85c5d-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="85c5d-132">Det gör att du kan fortsätta att undersöka datorn och återgå till bakgrundskommandot när du är klar med '**fg**' [basic-kommandot](live-response.md#basic-commands).</span><span class="sxs-lookup"><span data-stu-id="85c5d-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="85c5d-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="85c5d-133">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="85c5d-134">ångra</span><span class="sxs-lookup"><span data-stu-id="85c5d-134">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

