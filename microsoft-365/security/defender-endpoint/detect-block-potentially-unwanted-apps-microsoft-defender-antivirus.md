---
title: Blockera potentiellt oönskade program med Microsoft Defender Antivirus
description: Aktivera den potentiellt oönskade antivirusfunktionen (PUA) för att blockera oönskad programvara som reklamprogram.
keywords: pua, aktivera, oönskad programvara, oönskade appar, reklamprogram, webbläsarverktygsfält, identifiera, blockera, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904016"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Identifiera och blockera potentiellt oönskade program

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Potentiellt oönskade program (PUA) är en kategori med programvara som kan få datorn att köras långsamt, visa oväntade annonser eller som i värsta fall kan installera annan programvara som kan vara oväntad eller oönskad. PUA betraktas inte som ett virus, skadlig kod eller någon annan typ av hot, men den kan utföra åtgärder på slutpunkter som negativt påverkar slutpunktens prestanda eller användning. Termen *PUA kan* också referera till ett program som har ett dåligt rykte, enligt Microsoft Defender för Endpoint, på grund av vissa typer av oönskat beteende.

Här är några exempel:

- **Reklamprogramvara** som visar annonser eller kampanjer, inklusive programvara som infogar annonser på webbsidor.
- **Sammanslagning av programvara** som ger möjlighet att installera annan programvara som inte har signerats digitalt av samma enhet. Dessutom programvara som ger möjlighet att installera annan programvara som är berättigad som PUA.
- **Programvara av** en programvara som aktivt försöker undvika identifiering av säkerhetsprodukter, bland annat programvara som beter sig på olika sätt i närvaro av säkerhetsprodukter.

> [!TIP]
> Fler exempel och en diskussion om de villkor vi använder för att märka program för särskild uppmärksamhet från säkerhetsfunktioner finns i Hur Microsoft identifierar skadlig programvara och potentiellt [oönskade program.](/windows/security/threat-protection/intelligence/criteria)

Potentiellt oönskade program kan öka risken för att nätverket smittas med faktisk skadlig programvara, göra att skadlig programvara blir svårare att identifiera eller slösa PÅ IT-resurser i att rensa dem. PUA-skydd stöds i Windows 10, Windows Server 2019 och Windows Server 2016. I Windows 10 (version 2004 och senare) blockerar Microsoft Defender Antivirus appar som betraktas som PUA för Enterprise-enheter (E5) som standard.

## <a name="microsoft-edge"></a>Microsoft Edge

Nya [Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)som är Chromium-baserad, blockerar potentiellt oönskade programnedladdningar och tillhörande resurs-URL:er. Den här funktionen tillhandahålls via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Aktivera PUA-skydd i Chromium-baserade Microsoft Edge

Även om potentiellt oönskat programskydd i Microsoft Edge (Chromium-baserad version 80.0.361.50) är inaktiverat som standard kan det enkelt aktiveras från webbläsaren.

1. Välj ellipsen i Edge-webbläsaren och välj sedan **Inställningar**.

2. Välj **Sekretess, sökning och tjänster.**

3. Aktivera Blockera **potentiellt** oönskade appar **under Säkerhet.**

> [!TIP]
> Om du kör Microsoft Edge (Chromium-baserad) kan du tryggt utforska funktionen för URL-blockering av PUA-skydd genom att testa den på en av våra [Microsoft Defender SmartScreen-demosidor.](https://demo.smartscreen.msft.net/)

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Blockera URL-adresser med Microsoft Defender SmartScreen

I Chromium-baserad Edge med PUA-skydd aktiverat skyddar Microsoft Defender SmartScreen dig från PUA-associerade URL:er.

Säkerhetsadministratörer kan [konfigurera hur](/DeployEdge/configure-microsoft-edge) Microsoft Edge och Microsoft Defender SmartScreen samarbetar för att skydda grupper av användare från PUA-associerade URL:er. Det finns flera [grupprincipinställningar för](/DeployEdge/microsoft-edge-policies#smartscreen-settings) Microsoft Defender SmartScreen tillgängliga, bland annat en [för att blockera PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) Dessutom kan administratörer konfigurera [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) som en helhet, med grupprincipinställningar för att aktivera eller inaktivera Microsoft Defender SmartScreen.

Även om Microsoft Defender för Endpoint har en egen blockeringslista baserat på en datauppsättning som hanteras av Microsoft kan du anpassa den här listan baserat på din egen information om hot. Om du [skapar och hanterar indikatorer](manage-indicators.md) i Microsoft Defender för slutpunktsportalen respekterar Microsoft Defender SmartScreen de nya inställningarna.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender Antivirus- och PUA-skydd

Skyddsfunktionen för potentiellt oönskade program (PUA) i Microsoft Defender Antivirus kan identifiera och blockera PUA på slutpunkter i nätverket.

> [!NOTE]
> Den här funktionen är tillgänglig i Windows 10, Windows Server 2019 och Windows Server 2016.

Microsoft Defender Antivirus blockerar identifierade PUA-filer och alla försök att ladda ned, flytta, köra eller installera dem. Blockerade PUA-filer flyttas sedan till karantän. När en PUA-fil identifieras på en slutpunkt skickar Microsoft Defender Antivirus ett meddelande till användaren[(om](configure-notifications-microsoft-defender-antivirus.md)inte meddelanden har inaktiverats) i samma format som andra identifieringar av hot. Meddelandet föregås av för `PUA:` att ange dess innehåll.

Meddelandet visas i den vanliga [karantänlistan i Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Konfigurera PUA-skydd i Microsoft Defender Antivirus

Du kan aktivera PUA-skydd [med Microsoft Intune-,](/mem/intune/protect/device-protect)Microsoft Endpoint Configuration [Manager-, Grupprincip-](/azure/active-directory-domain-services/manage-group-policy)eller via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps) [](/mem/configmgr/protect/deploy-use/endpoint-protection)

Du kan också använda PUA-skydd i granskningsläge för att identifiera potentiellt oönskade program utan att blockera dem. Identifieringarna fångas i Händelseloggen i Windows.

> [!TIP]
> Besök demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) du vill bekräfta att funktionen fungerar och se hur den fungerar.

PUA-skydd i granskningsläge är användbart om ditt företag genomför en intern säkerhetskontroll av programvarans efterlevnad och du vill undvika falska positiva resultat.

### <a name="use-intune-to-configure-pua-protection"></a>Använda Intune för att konfigurera PUA-skydd

Mer information finns i Konfigurera inställningar för enhetsbegränsningar i [Microsoft Intune](/intune/device-restrictions-configure) och Microsoft Defender Antivirus för [Windows 10 i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Konfigurera PUA-skydd med Konfigurationshanteraren

PUA-skydd är aktiverat som standard i Microsoft Endpoint Manager (Current Branch).

Mer [information om hur du konfigurerar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) Microsoft Endpoint Manager (Current Branch).

Information om System Center 2012 Configuration Manager finns i Distribuera potentiellt oönskad programskyddsprincip för [slutpunktsskydd i Konfigurationshanteraren.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)

> [!NOTE]
> PUA-händelser som blockerats av Microsoft Defender Antivirus rapporteras i Windows loggboken och inte i Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Använda grupprincip för att konfigurera PUA-skydd

1. Ladda ned och [installera administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Öppna konsolen Grupprinciphantering på datorn [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

3. Markera det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

4. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

5. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus.**

6. Dubbelklicka på Konfigurera **identifiering för potentiellt oönskade program.**

7. Välj **Aktiverad för** att aktivera PUA-skydd.

8. Välj **Blockera** för att **blockera potentiellt** oönskade program i Alternativ eller välj **Granskningsläge** för att testa hur inställningen fungerar i din miljö. Välj **OK**.

9. Distribuera grupprincipobjektet som vanligt.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Använda PowerShell-cmdlets för att konfigurera PUA-skydd

#### <a name="to-enable-pua-protection"></a>Aktivera PUA-skydd

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Om du anger värdet för den här cmdleten `Enabled` aktiverar du funktionen om den har inaktiverats.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Så här ställer du in PUA-skydd till granskningsläge

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Inställningen `AuditMode` identifierar PUA:er utan att blockera dem.

#### <a name="to-disable-pua-protection"></a>Inaktivera PUA-skydd

Vi rekommenderar att du behåller PUA-skydd aktiverat. Du kan dock inaktivera det med hjälp av följande cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Om du anger värdet för den här cmdleten `Disabled` inaktiveras funktionen om den är aktiverad.

Mer information finns i Använda [PowerShell-cmdlets för att konfigurera och köra cmdlets för Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender.](/powershell/module/defender/index)

## <a name="view-pua-events-using-powershell"></a>Visa PUA-händelser med hjälp av PowerShell

PUA-händelser rapporteras i Windows loggboken, men inte i Microsoft Endpoint Manager eller i Intune. Du kan också använda `Get-MpThreat` cmdleten för att visa hot som Microsoft Defender Antivirus hanterat. Här är ett exempel:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>Få e-postaviseringar om PUA-identifieringar

Du kan aktivera e-postaviseringar för att ta emot e-post om PUA-identifieringar.

Mer [information om hur du visar antivirushändelser](troubleshoot-microsoft-defender-antivirus.md) i Microsoft Defender finns i Felsöka händelse-IDn. PUA-händelser registreras under händelse-ID **1160.**

## <a name="view-pua-events-using-advanced-hunting"></a>Visa PUA-händelser med avancerad sökning

Om du använder [Microsoft Defender för Slutpunkt kan du använda](microsoft-defender-endpoint.md)en avancerad fråga för att visa PUA-händelser. Här är en exempelfråga:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Mer information om avancerad sökning finns i [Proaktivt sök efter hot med avancerad sökning.](advanced-hunting-overview.md)

## <a name="exclude-files-from-pua-protection"></a>Undanta filer från PUA-skydd

Ibland är en fil felaktigt blockerad av PUA-skydd eller så krävs en funktion i en PUA för att slutföra en aktivitet. I sådana fall kan en fil läggas till i en undantagslista.

Mer information finns i [Konfigurera och validera undantag baserat på filtillägg och mappplats.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>Se även

- [Nästa generations skydd](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurera skydd för beteende, heuristisk och realtid](configure-protection-features-microsoft-defender-antivirus.md)