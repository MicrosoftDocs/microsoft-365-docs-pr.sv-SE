---
title: Använda kommandoraden för att hantera Microsoft Defender Antivirus
description: Kör Microsoft Defender Antivirus genomsökningar och konfigurera nästa generations skydd med ett dedikerat kommandoradsverktyg.
keywords: kör windows defender scan, kör antivirussökning från kommandoraden, kör windows defender scan från kommandoraden, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289421"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Konfigurera och Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan utföra olika funktioner Microsoft Defender Antivirus dedikerat kommandoradsverktyg i **mpcmdrun.exe**. Det här verktyget är användbart när du vill automatisera Microsoft Defender Antivirus uppgifter. Du hittar verktyget i `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Kör det från en kommandotolk.

> [!TIP]
> Du kan behöva öppna en version på administratörsnivå av kommandotolken. När du söker efter **Kommandotolken** i Start-menyn väljer du **Kör som administratör**. Om du kör en uppdaterad version av Microsoft Defender-plattformen körs `MpCmdRun` du från följande plats: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Mer information om program mot skadlig programvara finns Microsoft Defender Antivirus [uppdateringar och baslinjer.](manage-updates-baselines-microsoft-defender-antivirus.md)

Verktyget MpCmdRun använder följande syntax:

```console
MpCmdRun.exe [command] [-options]
```

Här är ett exempel:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

I vårt exempel startar MpCmdRun-verktyget en fullständig antivirussökning på enheten.

## <a name="commands"></a>Kommandon

| Kommando  | Beskrivning   |
|:----|:----|
| `-?` **eller** `-h`   | Visar alla tillgängliga alternativ för verktyget MpCmdRun |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Söker efter skadlig programvara. Värdena för **ScanType** är:<p>**0** Standard, enligt din konfiguration<p>**1** Snabbsökning<p>**2** Fullständig sökning<p>**3 Anpassad** sökning i arkiv och katalog.<p>CpuThrottling körs enligt principkonfigurationer |
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
| `-ValidateMapsConnection` | Verifierar att nätverket kan kommunicera Microsoft Defender Antivirus molntjänsten. Det här kommandot fungerar bara i Windows 10, version 1703 eller senare.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Vanliga fel när du kör kommandon via mpcmdrun.exe 

I följande tabell visas vanliga fel som kan uppstå när du använder verktyget MpCmdRun.

|Felmeddelande | Möjlig orsak |
|:----|:----|
| **ValidateMapsConnection failed (800106BA)** **eller 0x800106BA** | Tjänsten Microsoft Defender Antivirus inaktiveras. Aktivera tjänsten och försök igen. Om du behöver hjälp med att återaktivera Microsoft Defender Antivirus se [Installera om/aktivera Microsoft Defender Antivirus dina slutpunkter.](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)<p> **Tips!** Windows 10 1909 eller tidigare, och Windows Server 2019 eller tidigare, kallades tjänsten *för Windows Defender Antivirus.* |
| **0x80070667** | Du kör kommandot från `-ValidateMapsConnection` en dator som är Windows 10 version 1607 eller äldre, eller från Windows Server 2016 eller äldre. Kör kommandot från en dator Windows 10 version 1703 eller senare, eller från Windows 2019 eller senare.|
| **MpCmdRun kan inte identifieras som ett internt eller externt kommando, operabelt program eller en batchfil.** | Verktyget måste köras från antingen eller `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (om plattformsuppdateringarna är olika `2012.4-0` varje månad, förutom i mars)|
| **ValidateMapsConnection kunde inte upprätta en anslutning till KARTOR (hr=80070005 httpcode=450)** | Det här kommandot försöktes med otillräckliga behörigheter. Använd kommandotolken (cmd.exe) som administratör.|
| **ValidateMapsConnection kunde inte upprätta en anslutning till KARTOR (hr=80070006 httpcode=451)** | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| **ValidateMapsConnection kunde inte upprätta en anslutning till KARTOR (hr=80004005 httpcode=450)** | Möjliga nätverksrelaterade problem, som problem med namnmatchning|
| **ValidateMapsConnection kunde inte upprätta en anslutning till MAPS (hr=0x80508015** | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| **ValidateMapsConnection kunde inte upprätta en anslutning till MAPS (hr=800722F0D** | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |
| **ValidateMapsConnection kunde inte upprätta en anslutning till MAPS (hr=80072EE7 httpcode=451)** | Brandväggen blockerar anslutningen eller utför SSL-kontrollen. |

## <a name="see-also"></a>Se även

- [Konfigurera funktionerna i Microsoft Defender Antivirus](configure-microsoft-defender-antivirus-features.md)
- [Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md)
- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
