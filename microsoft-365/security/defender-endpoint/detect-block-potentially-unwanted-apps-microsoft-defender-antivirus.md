---
title: Blockera potentiellt oönskade program med Microsoft Defender Antivirus
description: Aktivera antivirusfunktionen för potentiellt oönskade program (PUA) för att blockera oönskad programvara som adware.
keywords: pua, aktivera, oönskad programvara, oönskade appar, adware, webbläsarverktygsfält, identifiera, blockera, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772383"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Identifiera och blockera potentiellt oönskade program

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

PUA (Potentially unwanted applications) är en kategori av program som kan göra att datorn körs långsamt, visa oväntade annonser eller, i värsta fall, installera andra program som kan vara oväntade eller oönskade. PUA anses inte vara ett virus, skadlig programvara eller någon annan typ av hot, men den kan utföra åtgärder på slutpunkter som negativt påverkar slutpunktens prestanda eller användning. Termen *PUA* kan också referera till ett program med dålig rykte, enligt Microsoft Defender för Endpoint, på grund av vissa typer av oönskat beteende.

Här är några exempel:

- **Reklamprogram** som visar annonser eller kampanjer, inklusive programvara som infogar annonser till webbsidor.
- **Sammanslagning av programvara** som ger möjlighet att installera annan programvara som inte har signerats digitalt av samma entitet. Dessutom programvara som erbjuder installation av annan programvara som räknas som PUA.
- **Undvikande programvara** som aktivt försöker undvika identifiering av säkerhetsprodukter, inklusive programvara som beter sig annorlunda i närvaro av säkerhetsprodukter.

> [!TIP]
> Fler exempel och en diskussion om de kriterier vi använder för att märka program för särskild uppmärksamhet från säkerhetsfunktioner finns i [Hur Microsoft identifierar skadlig programvara och potentiellt oönskade program](/windows/security/threat-protection/intelligence/criteria).

Potentiellt oönskade program kan öka risken att nätverket smittas med skadlig programvara, göra det svårare att identifiera skadlig programvara eller slösa IT-resurser på att städa upp dem. PUA-skydd stöds i Windows 10, Windows Server 2019 och Windows Server 2016. I Windows 10 (version 2004 och senare) blockerar Microsoft Defender Antivirus appar som anses vara PUA för företagsenheter (E5) som standard.

## <a name="microsoft-edge"></a>Microsoft Edge

Den [nya Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), som är Chromium-baserad, blockerar potentiellt oönskade programnedladdningar och associerade resurs-URL:er. Den här funktionen tillhandahålls via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Aktivera PUA-skydd i Chromium-baserad Microsoft Edge

Även om skydd mot potentiellt oönskat program i Microsoft Edge (Chromium-baserat, version 80.0.361.50) är inaktiverat som standard kan det enkelt aktiveras från webbläsaren.

1. Välj ellipsen i din Edge-webbläsaren och välj sedan **Inställningar**.

2. Välj **sekretess, sökning och tjänster**.

3. Under avsnittet **Säkerhet** aktiverar du **Blockera potentiellt oönskade program**.

> [!TIP]
> Om du kör Microsoft Edge (Chromium-baserat) kan du utforska URL-blockeringsfunktionen i PUA-skydd genom att testa den på någon av våra [Microsoft Defender SmartScreen-demosidor](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Blockera URL-adresser med Microsoft Defender SmartScreen

I den Chromium-baserade Edge-webbläsaren med PUA-skydd aktiverat skyddar Microsoft Defender SmartScreen dig från PUA-associerade URL-adresser.

Säkerhetsadministratörer kan [konfigurera](/DeployEdge/configure-microsoft-edge) hur Microsoft Edge och Microsoft Defender SmartScreen fungerar tillsammans för att skydda användargrupper från PUA-associerade URL:er. Det finns flera [grupprincipinställningar](/DeployEdge/microsoft-edge-policies#smartscreen-settings) som är uttryckligen tillgängliga för Microsoft Defender SmartScreen, inklusive en [för att blockera PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Dessutom kan administratörer [konfigurera Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) som helhet, och med hjälp av grupprincipinställningar, aktivera eller inaktivera Microsoft Defender SmartScreen.

Även om Microsoft Defender för Endpoint har en egen blockeringslista baserat på en datauppsättning som hanteras av Microsoft kan du anpassa listan baserat på egen information om hot. Om du [skapar och hanterar indikatorer](manage-indicators.md) i Microsoft Defender för Endpoint-portalen respekterar Microsoft Defender SmartScreen de nya inställningarna.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender Antivirus och PUA-skydd

Skyddsfunktionen för de potentiellt oönskade programmen i Microsoft Defender Antivirus kan identifiera och blockera PUA på slutpunkter i nätverket.

> [!NOTE]
> Den här funktionen finns för Windows 10, Windows Server 2019 och Windows Server 2016.

Microsoft Defender Antivirus blockerar identifierade PUA-filer och alla försök att hämta, flytta, köra eller installera dem. Blockerade PUA-filer flyttas sedan till karantän. När en PUA-fil identifieras på en slutpunkt skickar Microsoft Defender Antivirus ett meddelande till användaren ([om inte aviseringar har inaktiverats](configure-notifications-microsoft-defender-antivirus.md)) i samma format som andra hotidentifieringar. Meddelandet föregås av `PUA:` för att ange innehållet.

Meddelandet visas i den vanliga [-karantänlistan i Windows säkerhet-appen](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Konfigurera PUA-skydd i Microsoft Defender Antivirus

Du kan aktivera PUA-skydd med [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Grupprincip](/azure/active-directory-domain-services/manage-group-policy) eller via [PowerShell-cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).

Du kan också använda PUA-skydd i granskningsläge för att identifiera potentiellt oönskade program utan att blockera dem. Identifieringarna fångas i Windows-händelseloggen.

> [!TIP]
> Besök demowebbplatsen Microsoft Defender för Endpoint på [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) för att bekräfta att funktionen fungerar och se den i aktion.

PUA-skydd i granskningsläge är användbart om företaget utför en intern efterlevnadskontroll av programvarusäkerhet och du vill undvika falska positiva fel.

### <a name="use-intune-to-configure-pua-protection"></a>Använda Intune för att konfigurera PUA-skydd

För mer information läs [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure) och [Inställningar för enhetsbegränsning för Microsoft Defender i Windows 10 i Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Använda konfigurationshanteraren för att konfigurera PUA-skydd

PUA-skydd är aktiverat som standard i Microsoft Endpoint Manager (Current Branch).

För information om hur du konfigurerar Microsoft Endpoint Manager (Current Branch) läs [Hur du skapar och distribuerar principer för skadlig programvara: Schemalagda genomsökningsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).

Information om konfigurationshanteraren för System Center 2012 finns i [Hur du distribuerar skyddsprincip för potentiellt oönskad program för Endpoint i Konfigurationshanteraren](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> PUA-händelser som blockerats av Microsoft Defender Antivirus rapporteras i Windows Loggboken och inte i Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Använda Grupprincip för att konfigurera PUA-skydd

1. Hämta och installera [administrativa mallar (.admx) för Windows 10, oktober 2020 uppdatering (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.

3. Markera grupprincipobjektet du vill konfigurera och välj sedan **Redigera**.

4. I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

5. Expandera trädstrukturen till **Windows-komponenter** > **Microsoft Defender Antivirus**.

6. Dubbelklicka på **Konfigurera identifiering för potentiellt oönskade program**.

7. Välj **Aktivera** för att aktivera PUA-skydd.

8. I **Alternativ** väljer du **Blockera** för att blockera potentiellt oönskade program eller välj **Granskningsläge** för att testa hur inställningen fungerar i din miljö. Välj **OK**.

9. Distribuera grupprincipobjektet som vanligt.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Använda PowerShell-cmdlets för att konfigurera PUA-skydd

#### <a name="to-enable-pua-protection"></a>Så här aktiverar PUA-skydd.

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Att ställa in värdet för denna cmdlet till `Enabled` aktiverar funktionen om den har inaktiverats.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Så här ställer du in PUA-skydd till granskningsläge

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Inställningen av `AuditMode` identifierar PUA-program utan att blockera dem.

#### <a name="to-disable-pua-protection"></a>Så här inaktiverar du PUA-skydd.

Vi rekommenderar att du behåller PUA-skyddet aktiverat. Du kan dock inaktivera den med hjälp av följande cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Att ställa in värdet för denna cmdlet till `Disabled` aktiverar funktionen om den har inaktiverats.

Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Visa PUA-händelser med hjälp av PowerShell

PUA-händelser rapporteras i Windows Loggboken, men inte i Microsoft Endpoint Manager eller i Intune. Du kan också använda nämnda `Get-MpThreat` cmdlet för att visa hot som Microsoft Defender Antivirus hanterade. Här är ett exempel:

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

Du kan aktivera e-postaviseringar för att få e-post om PUA-identifieringar.

Gå till [Felsökningshändelse-ID:er](troubleshoot-microsoft-defender-antivirus.md) för mer information om hur du visar händelser för Microsoft Defender Antivirus. PUA-händelser registreras under händelse-ID **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Visa PUA-händelser med hjälp av avancerad jakt

Om du använder [Microsoft Defender för Endpoint](microsoft-defender-endpoint.md)kan du använda en avancerad sökfråga för att visa PUA-händelser. Här är en exempelfråga:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

Mer information om Avancerad jakt finns i [Hur du proaktivt jagar efter hot med Avancerad jakt](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Exkludera filer från PUA-skydd

Ibland blockeras en fil felaktigt av PUA-skydd eller så krävs en funktion i en PUA för att slutföra en aktivitet. I sådana fall kan en fil läggas till i en undantagslista.

Mer information finns i [Konfigurera och validera undantag baserat på filtillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Se även

- [Nästa generations skydd](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurera heuristiskt, beteende- och realtidsskydd](configure-protection-features-microsoft-defender-antivirus.md)