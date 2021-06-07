---
title: Schemalägg vanliga snabba och fullständiga skanningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789274"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurera schemalagda snabb- eller fullständiga genomsökningar för Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter före tiden för schemalagda sökningar. Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen. 

Förutom att alltid ha realtidsskydd och genomsökningar [på](run-scan-microsoft-defender-antivirus.md) begäran kan du också konfigurera regelbundna, schemalagda genomsökningar. 

Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller om slutpunkten används. Du kan också ange när särskilda genomsökningar ska slutföras.

I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med Grupprincip, PowerShell-cmdlets och WMI. Du kan också konfigurera schemasökningar med [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) eller [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Så här konfigurerar du grupprincipinställningarna som beskrivs i den här artikeln

1. Gå till Administrativa mallar för datorkonfiguration på hanteringsdatorn för grupprinciper i  >    >  **grupprincipredigeraren och klicka Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Genomsökning.**

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. Ange inställningar för grupprincipobjektet och välj sedan **OK.** 

4. Upprepa steg 1–4 för varje inställning du vill konfigurera.

5. Distribuera grupprincipobjektet som vanligt. Om du behöver hjälp med grupprincipobjekt kan du gå [till Skapa ett grupprincipobjekt.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

Läs även Hantera [när skyddsuppdateringar ska laddas ned och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) och Förhindra eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Snabbsökning kontra fullständig sökning och anpassad sökning

När du ställer in schemalagda genomsökningar kan du ställa in om skanningen ska vara en fullständig eller snabb genomsökning.


|Snabbsökning  |Fullständig sökning  | Anpassad sökning |
|---------|---------|---------|
|En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar. <p>I de flesta fall är en snabbsökning tillräcklig och rekommenderas för schemalagda genomsökningar. |En fullständig genomsökning påbörjas genom att köra en snabb genomsökning, och sedan fortsätter den med en sekventiell genomsökning av alla fasta diskmonter och flyttbara/nätverksenheter (om den fullständiga genomsökningen är konfigurerad att göra det). <p>En fullständig genomsökning kan ta några timmar eller dagar att slutföra, beroende på hur mycket och vilken typ av data som behöver skannas.<p>När den fullständiga genomsökningen är klar är ny säkerhetsinformation tillgänglig och en ny genomsökning krävs för att se till att inga andra hot identifieras med den nya säkerhetsintelligensen.   | En anpassad genomsökning är en snabbsökning som körs på de filer och mappar som du anger. Du kan till exempel välja att skanna en USB-enhet eller en särskild mapp på enhetens lokala enhet. <p> | 

>[!NOTE]
>Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Hur vet jag vilken skanningstyp jag ska välja?

Använd följande tabell för att välja en genomsökningstyp.


|Scenario  |Rekommenderad genomsökningstyp  |
|---------|---------|
|Du vill ställa in vanliga, schemalagda genomsökningar     | Snabbsökning <p>En snabb genomsökning kontrollerar processer, minne, profiler och vissa platser på enheten. I kombination [med realtidsskydd ger](configure-real-time-protection-microsoft-defender-antivirus.md)en snabb genomsökning stark täckning både för skadlig programvara som börjar med skadlig programvara på system- och kernel-nivå. Realtidsskydd granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp.         |
|Hot, till exempel skadlig kod, upptäcks på en enskild enhet     | Snabbsökning <p>I de flesta fall fångar och rensar en snabbsökning efter skadlig programvara.   |
|Du vill köra en [sökning på begäran](run-scan-microsoft-defender-antivirus.md)     | Snabbsökning       |
| Du vill kontrollera att en bärbar enhet, till exempel en USB-enhet, inte innehåller skadlig programvara | Anpassad sökning <p>Med en anpassad genomsökning kan du välja specifika platser, mappar eller filer och göra en snabbsökning. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Vad mer behöver jag veta om snabba och fullständiga skanningar?

- Skadliga filer kan lagras på platser som inte ingår i en snabbsökning. Skydd i realtid granskar emellertid alla filer som öppnas och stängs och alla filer som finns i mappar som en användare har åtkomst till. Kombinationen av realtidsskydd och en snabb genomsökning ger ett starkt skydd mot skadlig programvara.

- Skydd vid åtkomst med moln levererat [skydd](cloud-protection-microsoft-defender-antivirus.md) hjälper till att säkerställa att alla filer som används i systemet genomsöks med de senaste säkerhetsintelligens- och maskininlärningsmodellerna.

- När realtidsskyddet identifierar skadlig programvara och omfattningen av de berörda filerna inte fastställts först initierar Microsoft Defender Antivirus en fullständig genomsökning som en del av åtgärdsprocessen.

- En fullständig genomsökning kan identifiera skadliga filer som inte identifierats av andra genomsökningar, till exempel en snabbsökning. Men en fullständig genomsökning kan ta en stund och använda värdefulla systemresurser för att slutföra.

- Om en enhet är offline under en längre tid kan en fullständig genomsökning ta längre tid att slutföra. 

## <a name="set-up-scheduled-scans"></a>Konfigurera schemalagda genomsökningar

Schemalagda genomsökningar körs på den dag och den tid som du anger. Du kan använda Grupprincip, PowerShell och WMI för att konfigurera schemalagda genomsökningar.

> [!NOTE]
> Om en enhet är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, vilket innebär att skanningen stoppades innan den slutförddes. Microsoft Defender Antivirus en fullständig sökning vid nästa schemalagda tid.

### <a name="use-group-policy-to-schedule-scans"></a>Schemalägga genomsökningar med grupprinciper

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Ange vilken skanningstyp som ska användas för en schemalagd sökning | Snabbsökning |
|Skanna | Ange veckodagen då en schemalagd sökning ska köras | Ange den dag (eller aldrig) som ska köras. | Aldrig |
|Skanna | Ange tid på dagen då en schemalagd sökning ska köras | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00). | 02:00 |
|Rot | Slumpmässigt schemalagda aktivitetstider |I Microsoft Defender Antivirus kan du slumpmässigt lokalisera starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar. <p>I [S ÄR KAN](/mem/intune/protect/certificates-scep-configure)du slumpmässigt göra genomsökningarna med ett intervall plus eller minus 30 minuter. Det kan vara användbart i virtuella maskiner eller VDI-distributioner. | Aktiverad |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Använda PowerShell-cmdlets för att schemalägga skanningar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Mer information finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Schemalägga Windows med hjälp av WMI (Management Instruction)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi"></a>Använda Windows instruktionerna för hantering (WMI)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanOnlyIfIdleEnabled
```

Mer information om API:er och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Konfigurera när fullständiga genomsökningar ska köras för att slutföra åtgärd

Vissa hot kan kräva en fullständig genomsökning för att slutföra borttagning och åtgärd. Du kan ange när dessa genomsökningar ska ske med Grupprincip, PowerShell eller WMI.

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

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Använda Windows instruktionerna för hantering (WMI)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Schemalägga dagliga Windows med hjälp av WMI (Management Instruction)

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
ScanScheduleQuickScanTime
```

Mer information och tillåtna parametrar finns i Windows Defender [WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Aktivera genomsökningar efter skyddsuppdateringar

Du kan tvinga fram en genomsökning efter varje [skyddsuppdatering](manage-protection-updates-microsoft-defender-antivirus.md) med Grupprincip.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Använda grupprinciper för att schemalägga genomsökningar efter skyddsuppdateringar

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats)|
|:---|:---|:---|:---|
|Signaturuppdateringar | Aktivera genomsökning efter säkerhetsintelligensuppdatering | En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned | Aktiverad |

## <a name="see-also"></a>Se även

- [Förhindra eller tillåta användare att lokalt ändra principinställningar](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)