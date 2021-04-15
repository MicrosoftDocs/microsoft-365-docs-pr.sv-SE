---
title: Tillämpa Av-skyddsuppdateringar för Microsoft Defender på inuella slutpunkter
description: Definiera när och hur uppdateringar ska tillämpas för slutpunkter som inte har uppdaterats på ett tag.
keywords: uppdateringar, skydd, inaktuella, gamla och inaktuella uppdateringar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 81c7fb2bb7cd20fea3f343097811078ed744c3eb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765377"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Hantera uppdateringar och sökningar i Microsoft Defender Antivirus efter in alla slutpunkter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Med Microsoft Defender Antivirus kan du definiera hur länge en slutpunkt kan undvika en uppdatering eller hur många genomsökningar den kan missa innan den krävs för att uppdatera och söka igenom sig själv. Det är särskilt användbart i miljöer där enheter inte ofta är anslutna till ett företags- eller externt nätverk eller enheter som inte används dagligen.

En anställd som använder en viss dator har till exempel en paus i tre dagar och loggar inte in på datorn under den tiden.

När användaren återgår till att arbeta och loggar in på sin dator kommer Microsoft Defender Antivirus omedelbart att söka efter och ladda ned de senaste skyddsuppdateringarna och köra en genomsökning.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Konfigurera uppdateringar av uppdateringsskydd för slutpunkter som inte har uppdaterats på ett tag

Om Microsoft Defender Antivirus inte har laddat ned skyddsuppdateringar under en viss period kan du konfigurera det så att den automatiskt kontrollerar och hämtar den senaste uppdateringen vid nästa inloggning. Det här är användbart om [du har inaktiverat automatiska uppdateringsnedladdningar vid start](manage-event-based-updates-microsoft-defender-antivirus.md)globalt.

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Använda Konfigurationshanteraren för att konfigurera uppdateringar av upp- och uppslagsskyddet

1.  Öppna den programprincip du vill ändra på Microsoft Endpoint  Manager-konsolen (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till **Översikt**  >  **Endpoint Protection**  >  **Antimalware Policies**)

2.  Gå till avsnittet **Säkerhetsintelligensuppdateringar** och konfigurera följande inställningar:

    1. Ange **Tvinga en säkerhetsintelligensuppdatering om klientdatorn är offline för fler än två schemalagda uppdateringar i följd** till **Ja.**
    2. För  **Om Konfigurationshanteraren** används som källa för säkerhetsintelligensuppdateringar... anger du före vilka timmar skyddsuppdateringarna som levereras av Konfigurationshanteraren ska anses vara in datera. Det här leder till att nästa uppdateringsplats används, baserat på den definierade [reservkällordningen.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Klicka på **OK**.

4.  [Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Använda grupprinciper för att aktivera och konfigurera uppdateringsfunktionen

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > Signaturuppdateringar.**

5. Dubbelklicka på inställningen **Definiera det antal** dagar efter vilken en uppdatering av säkerhetsintelligens krävs och ange alternativet **Aktiverad.** Ange efter hur många dagar du vill att Microsoft Defender AV ska söka efter och hämta den senaste skyddsuppdateringen.

6. Klicka på **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Använda PowerShell-cmdlets för att konfigurera uppdateringar av uppslagsskyddet

Använd följande cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Använda Instruktionerna för Windows Management (WMI) för att konfigurera uppdateringar av skydd mot uppslag

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
SignatureUpdateCatchupInterval
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Ange antalet dagar innan skydd rapporteras som inställt

Du kan också ange hur många dagar efter vilket Microsoft Defender Antivirusskydd betraktas som gammalt eller in uppdaterat. Efter det angivna antalet dagar rapporterar klienten sig själv som in datera och visar ett fel för användaren av datorn. Det kan också orsaka att Microsoft Defender Antivirus försöker hämta en [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)uppdatering från andra källor (baserat på den definierade källordningen för reservkällor), till exempel när du använder MMPC som sekundär källa när du har angett WSUS eller Microsoft Update som den första källan.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Använda grupprincip för att ange antalet dagar innan skydd anses vara in uppdaterat

1.  På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

3.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

4.  Klicka **på Principer** och sedan på Administrativa **mallar.**

5.  Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > och** konfigurera följande inställningar:

    1.  Dubbelklicka på **Definiera antalet dagar innan definitioner av spionprogram anses vara inaktiva och** ställ in alternativet Aktiverad .  Ange efter hur många dagar som Microsoft Defender AV ska överväga att använda spionprogramssäkerhetsinformation.

    2. Klicka på **OK**.

    3.  Dubbelklicka på **Definiera antalet dagar innan virusdefinitioner anses vara inaktiva och** ange alternativet **Aktiverad.** Ange efter hur många dagar du vill att Microsoft Defender AV ska överväga att virussäkerhetsinformation är in datera.

    4. Klicka på **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Konfigurera snabbsökningar för slutpunkter som inte har sökts igenom på ett tag

Du kan ange antalet schemalagda genomsökningar i följd som kan missas innan Microsoft Defender Antivirus tvingar fram en genomsökning.

Processen för att aktivera den här funktionen är:

1. Konfigurera minst en schemalagd sökning (se [avsnittet Schemalägga genomsökningar).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Aktivera funktionen för genomsökning av uppläsning.
3. Definiera antalet genomsökningar som kan hoppas över innan en uppläsning sker.

Den här funktionen kan aktiveras för både fullständiga och snabba genomsökningar.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Använda grupprinciper för att aktivera och konfigurera genomsökningsfunktionen

1.  Se till att du har ställt in minst en schemalagd sökning.

2.  På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

3.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

4.  Klicka **på Principer** och sedan på Administrativa **mallar.**

5.  Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > Scan** och konfigurera följande inställningar:

    1.  Om du har ställt in schemalagda snabbsökningar dubbelklickar du på inställningen Aktivera snabbsökning för snabbsökning och ställer in alternativet **Aktiverad.**  
    2. Om du har ställt in schemalagda fullständiga  genomsökningar dubbelklickar du på inställningen Aktivera snabbsökning och ställer in alternativet **Aktiverad.** Klicka på **OK**.
    3. Dubbelklicka på inställningen Definiera antalet dagar efter vilket en uppläsningssökning **måste göras** och ställ in alternativet på **Aktiverad**. 
    4. Ange antalet genomsökningar som kan missas innan en genomsökning körs automatiskt när användaren nästa loggar in på datorn. Vilken typ av genomsökning som körs bestäms av Ange vilken genomsökningstyp som ska användas för en schemalagd sökning **(se** [avsnittet Schemalägg genomsökningar).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Klicka på **OK**.

> [!NOTE]
> Grupprincipinställningstiteln refererar till antalet dagar. Inställningen tillämpas dock på antalet genomsökningar (inte dagar) innan uppläsningen körs.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Använda PowerShell-cmdlets för att konfigurera genomsökningar för uppläsning

Använd följande cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att hantera Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Använd Instruktionerna för Windows Management (WMI) för att konfigurera genomsökningar för uppläsning

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Använda Konfigurationshanteraren för att konfigurera genomsökningar för uppläsning

1.  Öppna den programprincip du vill ändra på Microsoft Endpoint  Manager-konsolen (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till **Översikt**  >  **Endpoint Protection**  >  **Antimalware Policies**)

2.  Gå till avsnittet **Schemalagda genomsökningar** och Tvinga en genomsökning av den **valda genomsökningstypen om klientdatorn är offline...** till **Ja.** 

3. Klicka på **OK**.

4.  [Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="related-articles"></a>Relaterade artiklar

- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Hantera händelsebaserade tvingade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för mobila enheter och virtuella maskiner (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)