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
ms.openlocfilehash: de739ca3c6a4ab305b575fa7e2f419d044d997a8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274977"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Vanliga misstag att undvika när man definierar undantag

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Du kan definiera en undantagslista för objekt som du inte vill Microsoft Defender Antivirus söka i. Sådana undantagna objekt kan innehålla hot som gör din enhet sårbar. 

I den här artikeln beskrivs några vanliga misstag som du bör undvika när du definierar undantag. 

Innan du definierar dina undantagslistor kan [du Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Utesluta vissa betrodda objekt

Vissa filer, filtyper, mappar eller processer ska inte uteslutas från genomsökning även om du litar på att de inte är skadliga. 

Definiera inte undantag för mappplatser, filnamnstillägg och processer som anges i följande tabell:

| Mappplatser | Filnamnstillägg | Processer |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

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
