---
title: Distribution med ett annat MDM-system (Mobile Device Management) för Microsoft Defender ATP för Mac
description: Installera Microsoft Defender ATP för Mac på andra hanteringslösningar.
keywords: microsoft, defender, atp, mac, installation, distribuera, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 58e3b14dcb80db961f01b92f038ce4d32da7e2e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689713"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Distribution med ett annat MDM-system (Mobile Device Management) för Microsoft Defender för Slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Krav och systemkrav

Innan du börjar kan du gå [till huvudsidan för Microsoft Defender](microsoft-defender-endpoint-mac.md) för Slutpunkt på macOS för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.

## <a name="approach"></a>Metod

> [!CAUTION]
> För närvarande har Microsoft officiellt endast stöd för Intune och JAMF för distribution och hantering av Microsoft Defender för Endpoint på macOS. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges nedan.

Om din organisation använder en MDM-lösning (Mobile Device Management) som inte stöds officiellt betyder det inte att du inte kan distribuera eller köra Microsoft Defender för slutpunkt på macOS.

Microsoft Defender för Slutpunkt på macOS är inte beroende av några leverantörsspecifika funktioner. Den kan användas med alla MDM-lösningar som har stöd för följande funktioner:

- Distribuera en .pkg för macOS till hanterade enheter.
- Distribuera macOS-systemkonfigurationsprofiler till hanterade enheter.
- Kör ett godtyckligt administratörskonfigurerat verktyg/skript på hanterade enheter.

De flesta moderna MDM-lösningar innehåller dessa funktioner, men de kanske ser annorlunda ut.

Du kan distribuera Defender utan det sista kravet från ovanstående lista, men:

- Du kan inte samla in status på ett centraliserat sätt
- Om du bestämmer dig för att avinstallera Defender måste du logga in på klientenheten lokalt som administratör

## <a name="deployment"></a>Distribution

De flesta MDM-lösningar använder samma modell för hantering av macOS-enheter med liknande terminologi. Använd [JAMF-baserad distribution](mac-install-with-jamf.md) som mall.

### <a name="package"></a>Paket

Konfigurera distributionen av [ett programpaket som](mac-install-with-jamf.md)krävs med installationspaketet (wdav.pkg) som hämtats [från Microsoft Defender Säkerhetscenter.](mac-install-with-jamf.md)

Följ instruktionerna som är kopplade till din MDM-lösning för att distribuera paketet till ditt företag.

### <a name="license-settings"></a>Licensinställningar

Konfigurera en [systemkonfigurationsprofil](mac-install-with-jamf.md). Din MDM-lösning kan kalla den något liknande "Profil för anpassade inställningar", eftersom Microsoft Defender för Slutpunkt på macOS inte är en del av macOS.

Använd egenskapslistan, jamf/WindowsDefenderATPOnboarding.plist, som kan extraheras från ett onboarding-paket som laddas ned från [Microsoft Defender Säkerhetscenter.](mac-install-with-jamf.md)
Systemet kan ha stöd för en lista med godtyckliga egenskaper i XML-format. Du kan ladda upp filen jamf/WindowsDefenderATPOnboarding.plist som den är i så fall.
Du kan också kräva att du konverterar egenskapslistan till ett annat format först.

Vanligtvis har din anpassade profil ett ID, ett namn eller ett domänattribut. Du måste använda exakt "com.microsoft.wdav.atp" för det här värdet.
MDM använder den för att distribuera inställningsfilen till **/Bibliotek/Hanterade inställningar/com.microsoft.wdav.atp.plist** på en klientenhet, och Defender använder den här filen för inläsning av onboarding-informationen.

### <a name="kernel-extension-policy"></a>Kernel-tilläggspolicy

Konfigurera en KEXT- eller kernel-förlängningsprincip. Använd teamidentifierare **UBF8T346G9** för att tillåta kernel-tillägg som tillhandahålls av Microsoft.

> [!CAUTION]
> Om miljön består av Apple Silicon-enheter (M1) bör dessa datorer inte ta emot konfigurationsprofiler med KEXT-principer.
> Apple stöder inte KEXT på dessa datorer, distributionen av sådan profil skulle misslyckas på M1-datorer.

### <a name="system-extension-policy"></a>Princip för systemtillägg

Konfigurera en princip för systemtillägg. Använd **teamidentifierare UBF8T346G9** och godkänn följande paketidentifierare:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Fullständig princip för diskåtkomst

Bevilja fullständig diskåtkomst till följande komponenter:

- Microsoft Defender för Endpoint
    - Identifierare: `com.microsoft.wdav`
    - Identifierartyp: Paket-ID
    - Kodkrav: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender för Slutpunktssäkerhetstillägg
    - Identifierare: `com.microsoft.wdav.epsext`
    - Identifierartyp: Paket-ID
    - Kodkrav: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Princip för nätverkstillägg

Som en del av funktionerna Identifiering och svar av slutpunkt inspekterar Microsoft Defender för slutpunkt på macOS sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter-portalen. Med följande princip kan nätverkstillägget utföra de här funktionerna.

- Filtertyp: Plugin-program
- Identifierare för plugin-paket: `com.microsoft.wdav`
- Identifierare för filterleverantörspaket: `com.microsoft.wdav.netext`
- Filterdataleverantör angett krav: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Filteruttag: `true`

## <a name="check-installation-status"></a>Kontrollera installationsstatus

Kör [Microsoft Defender för Slutpunkt på](mac-install-with-jamf.md) en klientenhet för att kontrollera onboarding-statusen.
