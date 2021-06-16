---
title: Vanliga misstag att undvika när man definierar undantag
description: Undvik vanliga misstag när du definierar undantag för Microsoft Defender Antivirus genomsökningar.
keywords: undantag, filer, tillägg, filtyp, mappnamn, filnamn, genomsökningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950137"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="5001b-104">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="5001b-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="5001b-105">Du kan definiera en undantagslista för objekt som du inte vill Microsoft Defender Antivirus söka i.</span><span class="sxs-lookup"><span data-stu-id="5001b-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="5001b-106">Sådana undantagna objekt kan innehålla hot som gör din enhet sårbar.</span><span class="sxs-lookup"><span data-stu-id="5001b-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="5001b-107">I den här artikeln beskrivs några vanliga misstag som du bör undvika när du definierar undantag.</span><span class="sxs-lookup"><span data-stu-id="5001b-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="5001b-108">Innan du definierar dina undantagslistor kan [du Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span><span class="sxs-lookup"><span data-stu-id="5001b-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="5001b-109">Utesluta vissa betrodda objekt</span><span class="sxs-lookup"><span data-stu-id="5001b-109">Excluding certain trusted items</span></span>

<span data-ttu-id="5001b-110">Vissa filer, filtyper, mappar eller processer ska inte uteslutas från genomsökning även om du litar på att de inte är skadliga.</span><span class="sxs-lookup"><span data-stu-id="5001b-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="5001b-111">Definiera inte undantag för mappplatser, filnamnstillägg och processer som listas i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="5001b-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="5001b-112">Mappplatser</span><span class="sxs-lookup"><span data-stu-id="5001b-112">Folder locations</span></span>
- <span data-ttu-id="5001b-113">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="5001b-113">File extensions</span></span>
- <span data-ttu-id="5001b-114">Processer</span><span class="sxs-lookup"><span data-stu-id="5001b-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="5001b-115">Mappplatser</span><span class="sxs-lookup"><span data-stu-id="5001b-115">Folder locations</span></span>

<span data-ttu-id="5001b-116">I allmänhet ska du inte definiera undantag för följande mappplatser:</span><span class="sxs-lookup"><span data-stu-id="5001b-116">In general, do not define exclusions for the following folder locations:</span></span>

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

<span data-ttu-id="5001b-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\ServiceAccount\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="5001b-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="5001b-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\Default\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="5001b-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a><span data-ttu-id="5001b-119">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="5001b-119">File extensions</span></span>

<span data-ttu-id="5001b-120">I allmänhet ska du inte definiera undantag för följande filnamnstillägg:</span><span class="sxs-lookup"><span data-stu-id="5001b-120">In general, do not define exclusions for the following file extensions:</span></span>

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a><span data-ttu-id="5001b-121">Processer</span><span class="sxs-lookup"><span data-stu-id="5001b-121">Processes</span></span> 

<span data-ttu-id="5001b-122">I allmänhet ska du inte definiera undantag för följande processer:</span><span class="sxs-lookup"><span data-stu-id="5001b-122">In general, do not define exclusions for the following processes:</span></span>

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> <span data-ttu-id="5001b-123">Du kan välja att utesluta filtyper, till exempel , eller om miljön har en modern och uppdaterad programvara med strikt uppdateringspolicy för att hantera `.gif` `.jpg` eventuella `.jpeg` `.png` säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="5001b-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="5001b-124">Använda bara filnamnet i undantagslistan</span><span class="sxs-lookup"><span data-stu-id="5001b-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="5001b-125">En skadlig programvara kan ha samma namn som filen du litar på och vill utesluta från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="5001b-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="5001b-126">Undvik därför att utesluta eventuell skadlig programvara från genomsökning genom att använda en fullständigt kvalificerad sökväg till filen som du vill utesluta istället för att bara använda filnamnet.</span><span class="sxs-lookup"><span data-stu-id="5001b-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="5001b-127">Om du till exempel vill utesluta `Filename.exe` från genomsökning använder du den fullständiga sökvägen till filen, till exempel `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="5001b-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="5001b-128">Använda en enda undantagslista för flera serverarbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="5001b-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="5001b-129">Använd inte en enda undantagslista för att definiera undantag för flera serverarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="5001b-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="5001b-130">Dela upp undantagen för olika program- eller tjänstarbetsbelastningar i flera undantagslistor.</span><span class="sxs-lookup"><span data-stu-id="5001b-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="5001b-131">Exempel: Undantagslistan för din IIS Server-arbetsbelastning måste vara en annan än undantagslistan för SQL Server arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="5001b-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="5001b-132">Använda felaktiga miljövariabler som jokertecken i filnamn och mappsökväg eller undantagslistor för filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="5001b-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="5001b-133">Microsoft Defender Antivirus Tjänsten körs i systemsammanhang med hjälp av localSystem-kontot, vilket innebär att den hämtar information från systemmiljövariabeln och inte från användarmiljövariabeln.</span><span class="sxs-lookup"><span data-stu-id="5001b-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="5001b-134">Användning av miljövariabler som jokertecken i undantagslistor begränsas till systemvariabler och de som gäller för processer som körs som ett NT AUTHORITY\SYSTEM-konto.</span><span class="sxs-lookup"><span data-stu-id="5001b-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="5001b-135">Använd därför inte användarmiljövariabler som jokertecken när du lägger Microsoft Defender Antivirus undantag för mappar och processer.</span><span class="sxs-lookup"><span data-stu-id="5001b-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="5001b-136">I tabellen under [Systemmiljövariabler finns](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) en fullständig lista över systemmiljövariabler.</span><span class="sxs-lookup"><span data-stu-id="5001b-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="5001b-137">Mer information om hur du använder jokertecken i [undantagslistor](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) finns i Använda jokertecken i filnamn och mappsökväg eller undantagslistor för tillägg.</span><span class="sxs-lookup"><span data-stu-id="5001b-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

