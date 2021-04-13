---
title: Felsöka problem med kernel-tillägg i Microsoft Defender för Slutpunkt i macOS
description: Felsöka kernel-tilläggsproblem i Microsoft Defender för Slutpunkt i macOS.
keywords: microsoft, defender, atp, mac, kernel, tillägg
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 32a4819f7a607c69b4dbf45b3284b2f4ea66ffc4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689659"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a>Felsöka problem med kernel-tillägg i Microsoft Defender för Slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Slutpunkt på macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Den här artikeln innehåller information om hur du felsöker problem med kerneltillägget som installeras som en del av Microsoft Defender för slutpunkten i macOS.

Från och med macOS High Sierra (10.13) kräver macOS att alla kernel-tillägg uttryckligen godkänns innan de får köras på enheten.

Om du inte godkänna kernel-tillägget under distributionen/installationen av Microsoft Defender för Slutpunkt i macOS visas en banderoll i programmet där du uppmanas att aktivera det:

   ![Skärmbild som är inaktiverad av RTP](images/mdatp-32-main-app-fix.png)

Du kan också köra ```mdatp health``` . Den rapporterar om realtidsskydd är aktiverat men inte tillgängligt. Det här anger att kernel-tillägget inte är godkänt att köras på enheten.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

I följande avsnitt finns anvisningar om hur du kan åtgärda problemet, beroende på vilken metod du använde för att distribuera Microsoft Defender för slutpunkt i macOS.

## <a name="managed-deployment"></a>Hanterad distribution

Se anvisningarna som motsvarar det hanteringsverktyg som du använde för att distribuera produkten:

- [JAMF-baserad distribution](mac-install-with-jamf.md)
- [Microsoft Intune-baserad distribution](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Manuell distribution

Om mindre än 30 minuter har gått sedan produkten installerades går du till Säkerhet i **systeminställningar**& Sekretess, där du måste tillåta systemprogramvara från utvecklare  >  "Microsoft  Corporation".

Om du inte ser det här kommandotolken har det gått 30 minuter eller mer och kerneltillägget fortfarande inte har godkänts för att köras på enheten:

![Fönstret Säkerhet och sekretess efter skärmbild som har upphört att gälla](images/mdatp-33-securityprivacysettings-noprompt.png)

I det här fallet måste du utföra följande steg för att starta godkännandeflödet igen.

1. Försök installera drivrutinen i terminalen. Följande åtgärd kommer att misslyckas, eftersom kernel-tillägget inte godkänts för att köras på enheten. Men den utlöser godkännandeflödet igen.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Öppna **Systeminställningar**  >  **för & sekretess** på menyn. (Stäng det först om det öppnas.)

3. **Tillåt** systemprogramvara från utvecklare "Microsoft Corporation"

4. Installera drivrutinen igen i terminalen. Nu lyckas åtgärden:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    Banderollen ska försvinna från Defender-programmet ```mdatp health``` och bör nu rapportera att realtidsskydd både är aktiverat och tillgängligt:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
