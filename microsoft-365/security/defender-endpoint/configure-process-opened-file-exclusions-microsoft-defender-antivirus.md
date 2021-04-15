---
title: Konfigurera undantag för filer som öppnas av specifika processer
description: Du kan utesluta filer från genomsökningar om de har öppnats genom en viss process.
keywords: Microsoft Defender Antivirus, process, undantag, filer, genomsökningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 94375bc843c6512616d49345bcc9e7f63899a708
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765089"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Konfigurera undantag för filer som öppnas av processer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan utesluta filer som har öppnats av specifika processer från genomsökningar för Microsoft Defender Antivirus. Se [Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) innan du definierar dina undantagslistor.

I den här artikeln beskrivs hur du konfigurerar undantagslistor. 

## <a name="examples-of-exclusions"></a>Exempel på undantag

|Exkludering | Exempel |
|---|---|
|Alla filer på datorn som öppnas i valfri process med ett visst filnamn | När `test.exe` du anger utesluts filer som öppnas av: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Alla filer på datorn som öppnas i valfri process i en särskild mapp | När `c:\test\sample\*` du anger utesluts filer som öppnas av:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Alla filer på datorn som öppnas av en viss process i en särskild mapp | Om `c:\test\process.exe` du anger utesluts filer som endast öppnas av `c:\test\process.exe` |


När du lägger till en process i undantagslistan för processen söker Microsoft Defender Antivirus inte igenom filer som öppnas i den processen, oavsett var filerna finns. Själva processen genomsöks dock om den inte också har lagts till i [filens undantagslista.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Undantagen gäller endast [för realtidsskydd](configure-real-time-protection-microsoft-defender-antivirus.md)och övervakning. De gäller inte för schemalagda genomsökningar eller sökningar på begäran.

Ändringar som görs med Grupprincip för **undantagslistorna visas** i listorna i [Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md) Ändringar som görs i **Windows-säkerhetsappen visas emellertid inte** i listorna grupprinciper.

Du kan lägga till, ta bort och granska listorna för undantag i Grupprincip, Microsoft Endpoint Configuration Manager, Microsoft Intune och med Windows-säkerhetsappen, och du kan använda jokertecken för att ytterligare anpassa listorna.

Du kan också använda PowerShell-cmdlets och WMI för att konfigurera undantagslistorna, inklusive att granska listorna.

Som standard sammanfogas lokala ändringar som gjorts i listorna (av användare med administratörsbehörighet, ändringar som görs med PowerShell och WMI) med listorna som definierade (och distribuerade) av Grupprincip, Configuration Manager eller Intune. Grupprinciplistorna har företräde vid konflikter.

Du kan [konfigurera hur lokalt och globalt definierade undantagslistor slås samman så](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) att lokala ändringar åsidosätter inställningar för hanterad distribution.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Konfigurera listan över undantag för filer som öppnas av angivna processer

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd Microsoft Intune för att utesluta filer som har öppnats av angivna processer från genomsökningar

Mer information finns i Konfigurera inställningar för enhetsbegränsningar i [Microsoft Intune](/intune/device-restrictions-configure) och Microsoft Defender Antivirus för [Windows 10 i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd Microsoft Endpoint Manager för att utesluta filer som har öppnats av angivna processer från genomsökningar

Se [Hur du skapar och distribuerar principer för program mot skadlig programvara: Undantagsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) för information om hur du konfigurerar Microsoft Endpoint Manager (current branch).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd grupprinciper för att utesluta filer som har öppnats av angivna processer från genomsökningar

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > Undantag**.

4. Dubbelklicka på **Undantag för process** och lägg till undantagen:

    1. Ställ in alternativet som **Aktiverat**.
    2. I avsnittet **Alternativ** klickar du på **Visa...**.
    3. Ange varje process på en egen rad under **kolumnen Värdenamn.** Se exempeltabellen för de olika typerna av undantag för processer.  Ange **0** i **kolumnen Värde** för alla processer.

5. Klicka på **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd PowerShell-cmdlets för att utesluta filer som har öppnats av angivna processer från genomsökningar

Om du använder PowerShell för att lägga till eller ta bort undantag för filer som har öppnats i processer krävs en kombination av tre cmdlets med `-ExclusionProcess` parametern. Cmdletarna finns i [Defender-modulen.](/powershell/module/defender/)

Formatet för cmdletarna är:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Följande tillåts \<cmdlet> som:

|Konfigurationsåtgärd | PowerShell-cmdlet |
|---|---|
|Skapa eller skriva över listan | `Set-MpPreference` |
|Lägg till i listan | `Add-MpPreference` |
|Ta bort objekt från listan | `Remove-MpPreference` |

>[!IMPORTANT]
>Om du har skapat en lista med eller skriver du över den befintliga listan med hjälp av `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdleten igen.

Följande kodavsnitt skulle till exempel göra att Microsoft Defender AV-genomsökningar utesluter alla filer som öppnas i den angivna processen:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Hantera antivirus med PowerShell-cmdlets och [Microsoft Defender Antivirus-cmdlets.](/powershell/module/defender)

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd WMI (Windows Management Instruction) för att utesluta filer som har öppnats av angivna processer från genomsökningar

Använd metoderna [ **Ange,** **Lägg** till **och Ta** bort **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) klassen för följande egenskaper:

```WMI
ExclusionProcess
```

Användandet av **Set**, **Add** och **Remove kan** jämföras med deras motsvarigheter i PowerShell: , `Set-MpPreference` och `Add-MpPreference` `Remove-MpPreference` .

Mer information och tillåtna parametrar finns i [Windows Defender WMIv2 API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Använd Windows-säkerhetsappen för att utesluta filer som har öppnats av angivna processer från genomsökningar

Anvisningar [finns i Lägga till undantag i Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Använda jokertecken i undantagslistan för processer

Användningen av jokertecken i processens undantagslista skiljer sig från användningen i andra undantagslistor.

I synnerhet kan du inte använda jokertecknet ( ) och asterisken ( ) kan bara användas i slutet av `?` `*` en fullständig sökväg. Du kan fortfarande använda miljövariabler (till exempel `%ALLUSERSPROFILE%` ) som jokertecken när du definierar objekt i undantagslistan för processen.

I följande tabell beskrivs hur jokertecken kan användas i processens undantagslista:

|Jokertecken | Exempel på användning | Exempelmatchning |
|:---|:---|:---|
|`*` (asterisk) <br/><br/> Ersätter valbara antal tecken | `C:\MyData\*` | Alla filer som öppnas av `C:\MyData\file.exe` |
|Miljövariabler <br/><br/> Den definierade variabeln fylls i som en sökväg när undantaget beräknas | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Alla filer som öppnas av `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Granska listan över undantag

Du kan hämta objekten i undantagslistan med MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)eller [Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)

Om du använder PowerShell kan du hämta listan på två sätt:

- Hämta status för alla inställningar för Microsoft Defender Antivirus. Var och en av listorna visas på separata rader, men objekten i varje lista kombineras på samma rad.
- Skriv statusen för alla inställningar till en variabel och använd den variabeln för att bara anropa den specifika listan som du är intresserad av. Varje användning av `Add-MpPreference` skrivs till en ny rad.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validera undantagslistan med hjälp av MpCmdRun

Om du vill kontrollera undantag med det [dedikerade kommandoradsverktyget mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)använder du följande kommando:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Om du vill kontrollera undantag med MpCmdRun krävs Microsoft Defender Antivirus ANTIVIRUS version 4.18.1812.3 (utgiven i december 2018) eller senare.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Granska listan över undantag bredvid alla andra inställningar för Microsoft Defender Antivirus med hjälp av PowerShell

Använd följande cmdlet:

```PowerShell
Get-MpPreference
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender)

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Hämta en specifik undantagslista med hjälp av PowerShell

Använd följande kodavsnitt (ange varje rad som ett separat kommando). ersätt **WDAVprefs med** den etikett som du vill namnge variabeln:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender)

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera och validera undantag i genomsökningar för Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera undantag för Microsoft Defender Antivirus på Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Vanliga misstag att undvika när du definierar undantag](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder i Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)