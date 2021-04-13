---
title: Använda kommandoraden för att hantera Microsoft Defender Antivirus
description: Kör genomsökningar för Microsoft Defender Antivirus och konfigurera nästa generations skydd med ett dedikerat kommandoradsverktyg.
keywords: kör windows defender scan, kör antivirussökning från kommandoraden, kör windows defender scan från kommandoraden, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 2b20227ac27b90d142d263dfa4522aa41319b9d5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691086"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Konfigurera och hantera Microsoft Defender Antivirus mpcmdrun.exe ett kommandoradsverktyget

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan utföra olika Microsoft Defender Antivirus-funktioner med det dedikerade kommandoradsverktyget **mpcmdrun.exe**. Det här verktyget är användbart när du vill automatisera användningen av Microsoft Defender Antivirus. Du hittar verktyget i `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Du måste köra den från en kommandotolk.

> [!NOTE]
> Du kan behöva öppna en version på administratörsnivå av kommandotolken. När du söker efter **Kommandotolken** på Start-menyn väljer du **Kör som administratör**.
> Om du kör en uppdaterad version av Microsoft Defender-plattformen körs `**MpCmdRun**` du från följande plats: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

Verktyget har följande kommandon:

```console
MpCmdRun.exe [command] [-options]
```
Här är ett exempel:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Kommando  | Beskrivning   |
|:----|:----|
| `-?`**eller**`-h`   | Visar alla tillgängliga alternativ för det här verktyget |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Söker efter skadlig programvara. Värdena för **ScanType** är: **0** Standard, enligt din konfiguration, **-1** Snabbsökning, **-2** Fullständig genomsökning, **-3** Fil- och katalog anpassad sökning.  CpuThrottling respekterar den konfigurerade CPU-begränsningen från principen |
| `-Trace [-Grouping #] [-Level #]` | Startar diagnostikspårning |
| `-GetFiles [-SupportLogLocation <path>]` | Samlar in supportinformation. Se " insamling[av diagnostikdata](collect-diagnostic-data.md)"  |
| `-GetFilesDiagTrack`  | Samma som `-GetFiles` , men matas ut till mappen Temporary DiagTrack |
| `-RemoveDefinitions [-All]` | Återställer den installerade säkerhetsintelligensen till en tidigare säkerhetskopia eller till den ursprungliga standarduppsättningen |
| `-RemoveDefinitions [-DynamicSignatures]` | Tar bara bort den dynamiskt hämtade säkerhetsintelligensen |
| `-RemoveDefinitions [-Engine]` | Återställer den tidigare installerade motorn |
| `-SignatureUpdate [-UNC \| -MMPC]` | Söker efter nya säkerhetsintelligensuppdateringar |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Återställer eller visar objekt i karantän |
| `-AddDynamicSignature [-Path]` | Läser in dynamisk säkerhetsintelligens |
| `-ListAllDynamicSignatures` | Visar den inlästa dynamiska säkerhetsintelligensen |
| `-RemoveDynamicSignature [-SignatureSetID]` | Tar bort dynamisk säkerhetsinformation |
| `-CheckExclusion -path <path>` | Kontrollerar om en sökväg är utesluten |
| `-ValidateMapsConnection` | Verifierar att nätverket kan kommunicera med molntjänsten Microsoft Defender Antivirus. Det här kommandot fungerar bara i Windows 10, version 1703 eller senare.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Vanliga fel när du kör kommandon via mpcmdrun.exe 

|Felmeddelande | Möjlig orsak
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Antivirustjänsten Microsoft Defender är inaktiverad. Aktivera tjänsten och försök igen. <br>   **Obs!**  I Windows 10 1909 eller tidigare, och Windows Server 2019 eller äldre, kallades tjänsten Windows Defender Antivirus-tjänsten.|
| `0x80070667` | Du kör kommandot från en dator med `-ValidateMapsConnection` Windows 10 version 1607 eller äldre, eller Windows Server 2016 eller äldre. Kör kommandot från en dator med Windows 10 version 1703 eller senare, eller Windows Server 2019 eller senare.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Verktyget måste köras från antingen: eller `%ProgramFiles%\Windows Defender` (om plattformsuppdateringarna är olika varje `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` månad, förutom i mars)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Inte tillräckligt med behörigheter. Använd kommandotolken (cmd.exe) som administratör.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Möjliga nätverksrelaterade problem, som problem med namnmatchning|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |

## <a name="see-also"></a>Se även

- [Konfigurera funktioner för Microsoft Defender Antivirus](configure-microsoft-defender-antivirus-features.md)
- [Hantera Microsoft Defender Antivirus i ditt företag](configuration-management-reference-microsoft-defender-antivirus.md)
- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)