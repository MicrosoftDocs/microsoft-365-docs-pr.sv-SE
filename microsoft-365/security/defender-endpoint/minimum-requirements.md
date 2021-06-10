---
title: Minimikraven för Microsoft Defender för Slutpunkt
description: Förstå licenskraven och kraven för onboarding-enheter för tjänsten
keywords: minimikrav, licensiering, jämförelsetabell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ccff6abcfcd1a2da32a8e1614a2de45afed69aef
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843004"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Minimikraven för Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


Det finns några minimikrav för onboarding-enheter i tjänsten. Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att hantera enheter i tjänsten.

> [!TIP]
> - Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Defender för Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen. Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

## <a name="licensing-requirements"></a>Licensieringskrav

Microsoft Defender för Endpoint kräver något av följande volymlicensieringserbjudanden från Microsoft:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) som innehåller Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Säkerhet
- Microsoft Defender för Endpoint

> [!NOTE]
> Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.
> Microsoft Defender för Endpoint kan också köpas från en microsoft Molnlösningsleverantör (CSP).
> Virtuella RDSH-maskiner kräver inte en separat Defender för Endpoint-licens.

Microsoft Defender för slutpunkt för servrar kräver något av följande licensalternativ:

- [Azure Säkerhetscenter med Azure Defender aktiverat](/azure/security-center/security-center-pricing)
- Microsoft Defender för slutpunkt för server (en per server som omfattas)

> [!NOTE]
> Kunder kan skaffa serverlicenser (en per operativsystemmiljö för servrar (OSE)) för Microsoft Defender för Endpoint för servrar om de har kombinerat minst 50 licenser för en eller flera av följande användarlicenser:
>
> * Microsoft Defender för Endpoint
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5-/A5-säkerhet

Detaljerad licensinformation finns på webbplatsen [med produktvillkor och du](https://www.microsoft.com/licensing/terms/) kan arbeta med ditt kontoteam för att få mer information om villkoren.

Mer information om matrisen med funktioner i Windows 10- och versionerna finns [i Jämför Windows 10-utgåvor.](https://www.microsoft.com/windowsforbusiness/compare)

En detaljerad jämförelsetabell över en Windows 10 kommersiell utgåva jämförelse, se [jämförelsen PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).

## <a name="browser-requirements"></a>Webbläsarkrav

Åtkomst till Defender för Slutpunkt görs via en webbläsare med stöd för följande webbläsare:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Andra webbläsare kanske fungerar, men de nämnda webbläsarna är de som stöds.


## <a name="hardware-and-software-requirements"></a>Maskin- och programvarukrav

### <a name="supported-windows-versions"></a>Stöds Windows versioner

- Windows 7 SP1 Enterprise[(kräver ESU för support.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1 Pro ([kräver ESU för stöd](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (eller senare)](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, version 1803 eller senare
  - Windows Server 2019
- Windows Virtual Desktop

Enheter i nätverket måste köras på någon av dessa versioner.

Maskinvarukraven för Defender för Endpoint på enheter är samma för de versioner som stöds.

> [!NOTE]
> Datorer med mobila versioner av Windows (till exempel Windows CE och Windows 10 Mobile) stöds inte.
>
> Virtuella datorer som kör Windows 10 Enterprise 2016 LTSB kan stöta på prestandaproblem om de körs på virtualiseringsplattformar som inte är microsoft.
>
> För virtuella miljöer rekommenderar vi att du Windows 10 Enterprise LTSC 2019 eller senare.


### <a name="other-supported-operating-systems"></a>Andra operativsystem som stöds

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Du måste bekräfta att Linux-distributionerna och versionerna av Android, iOS och macOS är kompatibla med Defender för Endpoint för att integreringen ska fungera.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Krav för nätverks- och datalagring och konfiguration

När du kör onboardingguiden för första gången måste du välja var microsoft Defender för slutpunktsrelaterad information ska lagras: i EUROPEISKA UNIONEN, Storbritannien eller i USA-datacentret.

> [!NOTE]
> - Du kan inte ändra datalagringsplatsen efter den första installationen.
> - Läs [Microsoft Defender för slutpunktens datalagring och sekretess för](data-storage-privacy.md) mer information om var och hur Microsoft lagrar dina data.


### <a name="diagnostic-data-settings"></a>Inställningar för diagnostikdata

> [!NOTE]
> Microsoft Defender för Endpoint kräver ingen specifik diagnostiknivå så länge den är aktiverad.

Kontrollera att tjänsten för diagnostikdata är aktiverad på alla enheter i organisationen.
Den här tjänsten är aktiverad som standard. Det är bra att kontrollera att du får sensordata från dem.

**Använd kommandoraden för att kontrollera Windows 10 av tjänstens starttyp för diagnostikdata:**

1. Öppna en upphöjd kommandoradsfråga på enheten:

   1.  Gå till **Start** och skriv **cmd**.

   1.  Högerklicka på **Kommandotolken** och välj **Kör som administratör**.

2. Ange följande kommando och tryck på **Retur:**

   ```console
   sc qc diagtrack
   ```

   Om tjänsten är aktiverad bör resultatet se ut som på följande skärmbild:

   ![Resultatet av sc-frågekommandot för diagtrack](images/windefatp-sc-qc-diagtrack.png)


Du måste ange att tjänsten ska startas automatiskt om tjänsten START_TYPE **är** inställd på **AUTO_START**.


**Använd kommandoraden för att ställa in Windows 10 för diagnostikdata att starta automatiskt:**

1.  Öppna en upphöjd kommandoradsfråga i slutpunkten:

    1. Gå till **Start** och skriv **cmd**.

    1. Högerklicka på **Kommandotolken** och välj **Kör som administratör**.

2.  Ange följande kommando och tryck på **Retur:**

    ```console
    sc config diagtrack start=auto
    ```

3.  Ett meddelande om att det har lyckats visas. Verifiera ändringen genom att ange följande kommando och tryck på **Retur:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Internetanslutning

Internetanslutningen på enheter krävs antingen direkt eller via proxy.

Defender för slutpunkts sensor kan använda en daglig genomsnittlig bandbredd på 5 MB för att kommunicera med Defender för Endpoint-molntjänsten och rapportera cyberdata. En-off-aktiviteter, till exempel filuppladdningar och insamling av undersökningspaket, tas inte med i den här dagliga genomsnittliga bandbredden.

Mer information om ytterligare proxykonfigurationsinställningar finns i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)

Innan du börjar använda enheter måste diagnostikdatatjänsten vara aktiverad. Tjänsten är som standard aktiverad i Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender Antivirus konfigurationskrav

Defender för slutpunktsagenten är beroende av hur Microsoft Defender Antivirus kan söka igenom filer och ge information om dem.

Konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett Microsoft Defender Antivirus är den aktiva program mot skadlig programvara eller inte. Mer information finns i Hantera [uppdateringar Microsoft Defender Antivirus använda baslinjer.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Om Microsoft Defender Antivirus inte är det aktiva program mot skadlig programvara i organisationen och du använder Defender för slutpunktstjänsten Microsoft Defender Antivirus inaktivt läge.

Om din organisation har inaktiverat Microsoft Defender Antivirus grupprincip eller andra metoder måste enheter som är onboarded uteslutas från den här grupprincipen.

Om du onboarding servers och Microsoft Defender Antivirus inte är det aktiva program mot skadlig programvara på dina servrar måste Microsoft Defender Antivirus antingen konfigureras för att gå i passiv form eller avinstalleras. Konfigurationen är beroende av serverversionen. Mer information finns i [Microsoft Defender Antivirus kompatibilitet](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

> [!NOTE]
> Din vanliga grupprincip gäller inte för skydd mot manipulering, och ändringar i Microsoft Defender Antivirus-inställningarna ignoreras när Skydd mot manipulering är på.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Antivirus ELAM-drivrutin (Early Launch Antimalware) är aktiverad

Om du kör Microsoft Defender Antivirus som primärt program mot skadlig programvara på dina enheter kan Defender för Endpoint-agenten registrera sig.

Om du kör en tredjepartsklient för program mot skadlig programvara och använder mobila enhetshanteringslösningar eller Microsoft Endpoint Manager (current branch) måste du se till att Microsoft Defender Antivirus ELAM-drivrutinen är aktiverad. Mer information finns i Se [till att Microsoft Defender Antivirus inaktiveras av principen.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>Relaterade ämnen

- [Konfigurera Microsoft Defender för distribution av Slutpunkt](production-deployment.md)
- [Onboard-enheter](onboard-configure.md)
