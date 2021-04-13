---
title: Installera Microsoft Defender Antivirus-uppdateringar efter vissa händelser
description: Hantera hur Microsoft Defender Antivirus tillämpar säkerhetsintelligensuppdateringar efter start eller tar emot rapporter om identifiering av molntjänster.
keywords: uppdateringar, skydd, tvinga uppdateringar, händelser, start, sök efter senaste, meddelanden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b9f09878c645d54aadca21fe01749a0e73939c5f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691046"
---
# <a name="manage-event-based-forced-updates"></a>Hantera händelsebaserade tvingade uppdateringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Med Microsoft Defender Antivirus kan du avgöra om uppdateringar ska (eller inte ska) ske efter vissa händelser, till exempel vid start eller när du har fått specifika rapporter från den molnleveransskyddstjänst.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Söka efter skyddsuppdateringar innan du kör en genomsökning

Du kan använda Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdlets och WMI för att tvinga Microsoft Defender Antivirus att kontrollera och ladda ned skyddsuppdateringar innan du kör en schemalagd genomsökning.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Använda Konfigurationshanteraren för att söka efter skyddsuppdateringar innan du kör en genomsökning

1. Öppna den programprincip du vill ändra på Microsoft Endpoint  Manager-konsolen (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till **Översikt**  >  **Endpoint Protection**  >  **Antimalware Policies**)

2. Gå till avsnittet **Schemalagda genomsökningar** och ställ in Sök efter de senaste **säkerhetsintelligensuppdateringarna innan du kör en genomsökning** på **Ja.**

3. Klicka på **OK**.

4. [Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Använda grupprinciper för att söka efter skyddsuppdateringar innan du kör en genomsökning

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **Scan**.

5. Dubbelklicka på Sök **efter de senaste definitionerna av virus och spionprogram innan du kör en schemalagd sökning** och ställ in alternativet **Aktiverad**.

6. Klicka på **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Använda PowerShell-cmdlets för att söka efter skyddsuppdateringar innan du kör en genomsökning

Använd följande cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Mer information finns i Använda [PowerShell-cmdlets för att konfigurera och köra cmdlets för Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender.](/powershell/module/defender/index)

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Använd WMI (Windows Management Instruction) för att söka efter skyddsuppdateringar innan du kör en genomsökning

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
CheckForSignaturesBeforeRunningScan
```

Mer information finns i [Windows Defender WMIv2 API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>Söka efter säkerhetsuppdateringar vid start

Du kan använda grupprinciper för att tvinga Microsoft Defender Antivirus att kontrollera och ladda ned skyddsuppdateringar när datorn startas.

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Security  >  **Intelligence-uppdateringar.**

5. Dubbelklicka på Sök **efter de senaste definitionerna av virus och spionprogram vid start** och ställ in alternativet **Aktiverad**. 

6. Klicka på **OK**.

Du kan också använda grupprinciper, PowerShell och WMI för att konfigurera Microsoft Defender Antivirus så att de söker efter uppdateringar vid start även när programmet inte körs.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Använda grupprinciper för att ladda ned uppdateringar när Microsoft Defender Antivirus inte finns

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren** går du till **Datorkonfiguration**.

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Security  >  **Intelligence-uppdateringar.**

5. Dubbelklicka på Initiera **säkerhetsintelligensuppdatering vid start** och ange alternativet **Aktiverad**.

6. Klicka på **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Använda PowerShell-cmdlets för att ladda ned uppdateringar när Microsoft Defender Antivirus inte finns

Använd följande cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Mer information finns i Använda [PowerShell-cmdlets för](use-powershell-cmdlets-microsoft-defender-antivirus.md) att hantera Microsoft Defender Antivirus- och [Defender-cmdlets](/powershell/module/defender/index) för mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Använd WMI (Windows Management Instruction) för att ladda ned uppdateringar när Microsoft Defender Antivirus inte finns

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Mer information finns i [Windows Defender WMIv2 API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Tillåt ad hoc-ändringar av skydd baserat på moln levererat skydd

Microsoft Defender AV kan göra ändringar i skyddet baserat på molnskydd. Sådana ändringar kan ske utanför de normala eller schemalagda skyddsuppdateringarna.

Om du har aktiverat molnskydd skickar Microsoft Defender AV filer som det är misstänkt mot Windows Defender-molnet. Om molntjänsten rapporterar att filen är skadlig och filen identifieras i en nyligen genomförd skyddsuppdatering kan du använda Grupprincip för att konfigurera Microsoft Defender AV så att den automatiskt får den uppdateringen. Andra viktiga skyddsuppdateringar kan också tillämpas.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Använda grupprinciper för att automatiskt ladda ned de senaste uppdateringarna baserat på moln levererat skydd

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Security  >  **Intelligence-uppdateringar.**

5. Dubbelklicka på Tillåt **säkerhetsintelligensuppdateringar i realtid baserat på rapporter till Microsoft MAPS** och ange alternativet **Aktiverad**. Klicka sedan på **OK**.

6. **Tillåt aviseringar att inaktivera definitionsbaserade rapporter till Microsoft MAPS** och ställ in alternativet **Aktiverad**. Klicka sedan på **OK**.
    
> [!NOTE]
> **Tillåt aviseringar att inaktivera definitioner baserade rapporter** gör att Microsoft MAPS kan inaktivera de definitioner som kallas för falska positiva rapporter. Du måste konfigurera datorn för att ansluta till Microsoft MAPS för att den här funktionen ska fungera.

## <a name="see-also"></a>Se även

- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för mobila enheter och virtuella maskiner (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)