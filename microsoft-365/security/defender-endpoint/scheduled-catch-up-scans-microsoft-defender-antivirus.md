---
title: Schemalägg vanliga snabba och fullständiga genomsökningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bfa616423fc0c097b9909df8abf5b9c414490383
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764093"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurera schemalagda snabba eller fullständiga genomsökningar för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter innan eventuella schemalagda genomsökningar görs. Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen. 

Förutom att alltid ha realtidsskydd och genomsökningar [på](run-scan-microsoft-defender-antivirus.md) begäran kan du också konfigurera regelbundna, schemalagda genomsökningar. 

Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller om slutpunkten används. Du kan också ange när särskilda genomsökningar ska slutföras.

I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med Grupprincip, PowerShell-cmdlets och WMI. Du kan också konfigurera genomsökningar av scheman med [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) eller Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Så här konfigurerar du grupprincipinställningarna som beskrivs i den här artikeln

1.  På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

3.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

4.  Klicka **på Administrativa mallar**.

5.  Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus** och sedan den **plats** som anges i tabellen nedan.

6. Dubbelklicka på den **principinställning** som anges i tabellen nedan och ange önskat alternativ. 

7. Klicka **på OK** och upprepa för alla andra inställningar.

Läs även Hantera [när skyddsuppdateringar ska laddas ned och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) och Förhindra eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Snabbsökning kontra fullständig sökning och anpassad sökning

När du ställer in schemalagda genomsökningar kan du ställa in om skanningen ska vara en fullständig eller snabb genomsökning.

Med snabbsökningar kan du se alla platser där skadlig programvara registrerats, till exempel registernycklar och kända startmappar i Windows. 

I kombination med ständigt realtidsskydd [–](configure-real-time-protection-microsoft-defender-antivirus.md) som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp – ger en snabb genomsökning stark täckning både för skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara.  

I de flesta fall innebär det att en snabb genomsökning är lämplig för att hitta skadlig programvara som inte hämtades med realtidsskydd.

En fullständig genomsökning kan vara användbar på slutpunkter som har stött på ett hot mot skadlig programvara för att identifiera om det finns inaktiva komponenter som kräver en mer omfattande rensning. I den här instansen kanske du vill använda en fullständig genomsökning när du kör [en sökning på begäran.](run-scan-microsoft-defender-antivirus.md)

Med en anpassad genomsökning kan du ange vilka filer och mappar som ska skannas, till exempel en USB-enhet. 

>[!NOTE]
>Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.

## <a name="set-up-scheduled-scans"></a>Konfigurera schemalagda genomsökningar

Schemalagda genomsökningar körs på den dag och den tid du anger. Du kan använda Grupprincip, PowerShell och WMI för att konfigurera schemalagda genomsökningar.

>[!NOTE]
>Om en dator är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, som innebär att skanningen har stoppats innan den slutförts. Microsoft Defender Antivirus kör en fullständig genomsökning vid nästa schemalagda tid.

### <a name="use-group-policy-to-schedule-scans"></a>Schemalägga genomsökningar med grupprinciper

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Ange vilken skanningstyp som ska användas för en schemalagd sökning | Snabbsökning |
|Skanna | Ange veckodagen då en schemalagd sökning ska köras | Ange den dag (eller aldrig) som ska köras. | Aldrig |
|Skanna | Ange tid på dagen då en schemalagd sökning ska köras | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00). | 02:00 |
|Rot | Slumpmässigt schemalagda aktivitetstider |I Microsoft Defender Antivirus: Slumpa starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar. <br>I FEP/SSSON: slumpvis till ett intervall plus eller minus 30 minuter. Det kan vara användbart i VM- eller VDI-distributioner. | Aktiverad |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Använda PowerShell-cmdlets för att schemalägga skanningar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Schemalägga genomsökningar med Windows Management Instruction (WMI)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Starta schemalagda genomsökningar bara när slutpunkten inte används

Du kan ange att den schemalagda genomsökningen bara ska ske när slutpunkten är aktiverad men inte används med Grupprincip, PowerShell eller WMI.

> [!NOTE]
> De här genomsökningarna respekterar inte konfigurationen av CPU-begränsning och utnyttjar de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.

### <a name="use-group-policy-to-schedule-scans"></a>Schemalägga genomsökningar med grupprinciper

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Starta den schemalagda genomsökningen bara när datorn är på, men inte använder | Schemalagda genomsökningar körs inte, om inte datorn är på men inte används | Aktiverad |

### <a name="use-powershell-cmdlets"></a>Använda PowerShell-cmdlets

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Använda Instruktionerna för Windows Management (WMI)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanOnlyIfIdleEnabled
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Konfigurera när fullständiga genomsökningar ska köras för att slutföra åtgärd

Vissa hot kan kräva en fullständig genomsökning för att slutföra borttagning och åtgärd. Du kan schemalägga när de här genomsökningarna ska ske med Grupprincip, PowerShell eller WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Använd Grupprincip för att schemalägga genomsökningar som krävs för åtgärder

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|---|---|---|---|
|Åtgärda | Ange veckodagen då en schemalagd fullständig genomsökning ska köras | Ange den dag (eller aldrig) som ska köras. | Aldrig |
|Åtgärda | Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00) | 02:00 |

### <a name="use-powershell-cmdlets"></a>Använda PowerShell-cmdlets

Använd följande cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Använda Instruktionerna för Windows Management (WMI)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Konfigurera dagliga snabbsökningar

Du kan aktivera en daglig snabbsökning som kan köras utöver dina andra schemalagda genomsökningar med Grupprincip, PowerShell eller WMI.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Använda grupprinciper för att schemalägga dagliga genomsökningar


|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Ange tidsintervallet för att köra snabbsökningar per dag | Ange hur många timmar som ska förfluta före nästa snabbsökning. Om du till exempel vill köra varannan timme anger **du 2**, för en gång om dagen skriver du **24**. Ange **0 för** att aldrig köra en daglig snabbsökning. | Aldrig |
|Skanna | Ange tiden för en daglig snabbsökning | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00) | 02:00 |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Använda PowerShell-cmdlets för att schemalägga dagliga genomsökningar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Använd WMI (Windows Management Instruction) för att schemalägga dagliga genomsökningar

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanScheduleQuickScanTime
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Aktivera genomsökningar efter skyddsuppdateringar

Du kan tvinga fram en genomsökning efter varje [skyddsuppdatering](manage-protection-updates-microsoft-defender-antivirus.md) med Grupprincip.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Använda grupprinciper för att schemalägga genomsökningar efter skyddsuppdateringar

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats)|
|:---|:---|:---|:---|
|Signaturuppdateringar | Aktivera genomsökning efter säkerhetsintelligensuppdatering | En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned | Aktiverad |

## <a name="see-also"></a>Se även
- [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera sökalternativ för Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)