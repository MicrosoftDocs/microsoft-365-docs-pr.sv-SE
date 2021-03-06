---
title: Schemalägga Microsoft Defender Antivirus säkerhetsuppdateringar
description: Schemalägga dag, tid och intervall för när skyddsuppdateringar ska laddas ned
keywords: uppdateringar, säkerhetsbaslinjer, schemauppdateringar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: abb656586d6a7bd779b109fcad3c777016fef980
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926061"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Hantera schemat för när skyddsuppdateringar ska laddas ned och tillämpas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus kan du avgöra när den ska söka efter och ladda ned uppdateringar.

Du kan schemalägga uppdateringar för slutpunkterna genom att: 

- Ange veckodag för att söka efter skyddsuppdateringar 
- Ange intervallet som ska söka efter skyddsuppdateringar
- Ange tiden för att söka efter skyddsuppdateringar

Du kan också slumpmässigt ändra tidpunkterna när varje slutpunkt kontrollerar och laddar ned skyddsuppdateringar. Mer information [finns i avsnittet](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Schemalägga genomsökningar.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Använda Konfigurationshanteraren för att schemalägga skyddsuppdateringar

1.  Öppna den Microsoft Endpoint Manager programkonsol på datorn som du vill ändra  (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till Översikt Endpoint Protection Program mot skadlig  >    >  **programvara**)

2.  Gå till avsnittet **Säkerhetsintelligensuppdateringar.**

3. Så här kontrollerar och laddar du ned uppdateringar vid en viss tidpunkt:
      1. Ställ **in Sök Endpoint Protection säkerhetsintelligensuppdateringar med ett visst intervall...** till **0**.
      2. Ställ **in Sök Endpoint Protection säkerhetsintelligensuppdateringar varje dag...** till den tidpunkt då uppdateringarna ska kontrolleras.
      3
4. Om du vill söka efter och ladda ned uppdateringar kontinuerligt, ställ in Sök efter Endpoint Protection säkerhetsintelligensuppdateringar med ett visst **intervall...** på antalet timmar som ska ske mellan uppdateringarna.

5.  [Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="use-group-policy-to-schedule-protection-updates"></a>Använda grupprinciper för att schemalägga skyddsuppdateringar

> [!IMPORTANT]
> Som standard söker Microsoft Defender Antivirus uppdatering 15 minuter före tiden för schemalagda genomsökningar. Om du aktiverar de här inställningarna åsidosätts den standardinställningen.

1.  På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

3.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

4.  Klicka **på Principer** och sedan på Administrativa **mallar.**

5.  Expandera trädet så att **Windows delar**  >  **Microsoft Defender Antivirus signaturintelligensuppdateringar** och konfigurera följande  >   inställningar:

    1. Dubbelklicka på ange **dagen i veckan för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.** Ange veckodagen för att söka efter uppdateringar. Klicka på **OK**.
    2. Dubbelklicka på inställningen Ange **intervallet för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.** Ange antalet timmar mellan uppdateringarna. Klicka på **OK**.
    3. Dubbelklicka på inställningen **Ange tiden för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.** Ange när uppdateringarna ska kontrolleras. Tiden baseras på slutpunktens lokala tid. Klicka på **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Använda PowerShell-cmdlets för att schemalägga skyddsuppdateringar

Använd följande cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Använda Windows (WMI) för att schemalägga säkerhetsuppdateringar

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [Windows Defender WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Relaterade artiklar

- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Hantera händelsebaserade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för mobila enheter och virtuella datorer(VM)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)