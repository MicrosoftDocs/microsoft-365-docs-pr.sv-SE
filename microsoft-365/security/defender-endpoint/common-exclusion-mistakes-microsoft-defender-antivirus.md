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
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538069"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="76856-104">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="76856-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76856-105">Du kan definiera en undantagslista för objekt som du inte vill Microsoft Defender Antivirus söka i.</span><span class="sxs-lookup"><span data-stu-id="76856-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="76856-106">Sådana undantagna objekt kan innehålla hot som gör din enhet sårbar.</span><span class="sxs-lookup"><span data-stu-id="76856-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="76856-107">I den här artikeln beskrivs några vanliga misstag som du bör undvika när du definierar undantag.</span><span class="sxs-lookup"><span data-stu-id="76856-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="76856-108">Innan du definierar dina undantagslistor kan [du Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span><span class="sxs-lookup"><span data-stu-id="76856-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="76856-109">Utesluta vissa betrodda objekt</span><span class="sxs-lookup"><span data-stu-id="76856-109">Excluding certain trusted items</span></span>

<span data-ttu-id="76856-110">Vissa filer, filtyper, mappar eller processer ska inte uteslutas från genomsökning även om du litar på att de inte är skadliga.</span><span class="sxs-lookup"><span data-stu-id="76856-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="76856-111">Definiera inte undantag för mappplatser, filnamnstillägg och processer som listas i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="76856-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="76856-112">Mappplatser</span><span class="sxs-lookup"><span data-stu-id="76856-112">Folder locations</span></span>
- <span data-ttu-id="76856-113">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="76856-113">File extensions</span></span>
- <span data-ttu-id="76856-114">Processer</span><span class="sxs-lookup"><span data-stu-id="76856-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="76856-115">Mappplatser</span><span class="sxs-lookup"><span data-stu-id="76856-115">Folder locations</span></span>

<span data-ttu-id="76856-116">I allmänhet ska du inte definiera undantag för följande mappplatser:</span><span class="sxs-lookup"><span data-stu-id="76856-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="76856-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\ServiceAccount\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="76856-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="76856-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\Default\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="76856-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="76856-119">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="76856-119">File extensions</span></span>

<span data-ttu-id="76856-120">I allmänhet ska du inte definiera undantag för följande filnamnstillägg:</span><span class="sxs-lookup"><span data-stu-id="76856-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="76856-121">Processer</span><span class="sxs-lookup"><span data-stu-id="76856-121">Processes</span></span> 

<span data-ttu-id="76856-122">I allmänhet ska du inte definiera undantag för följande processer:</span><span class="sxs-lookup"><span data-stu-id="76856-122">In general, do not define exclusions for the following processes:</span></span>

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
> <span data-ttu-id="76856-123">Du kan välja att utesluta filtyper, till exempel , eller om miljön har en modern och uppdaterad programvara med strikt uppdateringspolicy för att hantera `.gif` `.jpg` eventuella `.jpeg` `.png` säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="76856-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="76856-124">Använda bara filnamnet i undantagslistan</span><span class="sxs-lookup"><span data-stu-id="76856-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="76856-125">En skadlig programvara kan ha samma namn som filen du litar på och vill utesluta från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="76856-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="76856-126">Undvik därför att utesluta eventuell skadlig programvara från genomsökning genom att använda en fullständigt kvalificerad sökväg till filen som du vill utesluta istället för att bara använda filnamnet.</span><span class="sxs-lookup"><span data-stu-id="76856-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="76856-127">Om du till exempel vill utesluta `Filename.exe` från genomsökning använder du den fullständiga sökvägen till filen, till exempel `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="76856-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="76856-128">Använda en enda undantagslista för flera serverarbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="76856-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="76856-129">Använd inte en enda undantagslista för att definiera undantag för flera serverarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="76856-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="76856-130">Dela upp undantagen för olika program- eller tjänstarbetsbelastningar i flera undantagslistor.</span><span class="sxs-lookup"><span data-stu-id="76856-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="76856-131">Exempel: Undantagslistan för din IIS Server-arbetsbelastning måste vara en annan än undantagslistan för SQL Server arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="76856-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="76856-132">Använda felaktiga miljövariabler som jokertecken i filnamn och mappsökväg eller undantagslistor för filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="76856-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="76856-133">Microsoft Defender Antivirus Tjänsten körs i systemsammanhang med hjälp av localSystem-kontot, vilket innebär att den hämtar information från systemmiljövariabeln och inte från användarmiljövariabeln.</span><span class="sxs-lookup"><span data-stu-id="76856-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="76856-134">Användning av miljövariabler som jokertecken i undantagslistor begränsas till systemvariabler och de som gäller för processer som körs som ett NT AUTHORITY\SYSTEM-konto.</span><span class="sxs-lookup"><span data-stu-id="76856-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="76856-135">Använd därför inte användarmiljövariabler som jokertecken när du lägger Microsoft Defender Antivirus undantag för mappar och processer.</span><span class="sxs-lookup"><span data-stu-id="76856-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="76856-136">I tabellen under [Systemmiljövariabler finns](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) en fullständig lista över systemmiljövariabler.</span><span class="sxs-lookup"><span data-stu-id="76856-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="76856-137">Mer information om hur du använder jokertecken i [undantagslistor](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) finns i Använda jokertecken i filnamn och mappsökväg eller undantagslistor för tillägg.</span><span class="sxs-lookup"><span data-stu-id="76856-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="76856-138">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="76856-138">Related articles</span></span>

- [<span data-ttu-id="76856-139">Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="76856-139">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="76856-140">Konfigurera och validera undantag baserat på filtillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="76856-140">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="76856-141">Konfigurera och validera undantag för filer som öppnas i processer</span><span class="sxs-lookup"><span data-stu-id="76856-141">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="76856-142">Konfigurera Microsoft Defender Antivirus undantag på Windows Server</span><span class="sxs-lookup"><span data-stu-id="76856-142">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
