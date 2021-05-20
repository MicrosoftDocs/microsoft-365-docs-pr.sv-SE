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
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Vanliga misstag att undvika när man definierar undantag

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Du kan definiera en undantagslista för objekt som du inte vill Microsoft Defender Antivirus söka i. Sådana undantagna objekt kan innehålla hot som gör din enhet sårbar. 

I den här artikeln beskrivs några vanliga misstag som du bör undvika när du definierar undantag. 

Innan du definierar dina undantagslistor kan [du Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Utesluta vissa betrodda objekt

Vissa filer, filtyper, mappar eller processer ska inte uteslutas från genomsökning även om du litar på att de inte är skadliga. 

Definiera inte undantag för mappplatser, filnamnstillägg och processer som listas i följande avsnitt:
- Mappplatser
- Filnamnstillägg
- Processer

### <a name="folder-locations"></a>Mappplatser

I allmänhet ska du inte definiera undantag för följande mappplatser:

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\ServiceAccount\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Observera följande undantag för SharePoint:** Gäller inte när du använder `C:\Users\Default\AppData\Local\Temp` [antivirusskydd på filnivå i SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

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

### <a name="file-extensions"></a>Filnamnstillägg

I allmänhet ska du inte definiera undantag för följande filnamnstillägg:

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

### <a name="processes"></a>Processer 

I allmänhet ska du inte definiera undantag för följande processer:

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
> Du kan välja att utesluta filtyper, till exempel , eller om miljön har en modern och uppdaterad programvara med strikt uppdateringspolicy för att hantera `.gif` `.jpg` eventuella `.jpeg` `.png` säkerhetsproblem.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Använda bara filnamnet i undantagslistan

En skadlig programvara kan ha samma namn som filen du litar på och vill utesluta från genomsökning. Undvik därför att utesluta eventuell skadlig programvara från genomsökning genom att använda en fullständigt kvalificerad sökväg till filen som du vill utesluta istället för att bara använda filnamnet. Om du till exempel vill utesluta `Filename.exe` från genomsökning använder du den fullständiga sökvägen till filen, till exempel `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Använda en enda undantagslista för flera serverarbetsbelastningar

Använd inte en enda undantagslista för att definiera undantag för flera serverarbetsbelastningar. Dela upp undantagen för olika program- eller tjänstarbetsbelastningar i flera undantagslistor. Exempel: Undantagslistan för din IIS Server-arbetsbelastning måste vara en annan än undantagslistan för SQL Server arbetsbelastningen.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Använda felaktiga miljövariabler som jokertecken i filnamn och mappsökväg eller undantagslistor för filnamnstillägg

Microsoft Defender Antivirus Tjänsten körs i systemsammanhang med hjälp av localSystem-kontot, vilket innebär att den hämtar information från systemmiljövariabeln och inte från användarmiljövariabeln. Användning av miljövariabler som jokertecken i undantagslistor begränsas till systemvariabler och de som gäller för processer som körs som ett NT AUTHORITY\SYSTEM-konto. Använd därför inte användarmiljövariabler som jokertecken när du lägger Microsoft Defender Antivirus undantag för mappar och processer. I tabellen under [Systemmiljövariabler finns](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) en fullständig lista över systemmiljövariabler.

Mer information om hur du använder jokertecken i [undantagslistor](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) finns i Använda jokertecken i filnamn och mappsökväg eller undantagslistor för tillägg.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera och validera undantag i Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag baserat på filtillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag för filer som öppnas i processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera Microsoft Defender Antivirus undantag på Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
