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
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069434"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Minimikraven för Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Det finns några minimikrav för onboarding-enheter i tjänsten. Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att hantera enheter i tjänsten.

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).

> [!TIP]
> - Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Defender för Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen. Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

## <a name="licensing-requirements"></a>Licenskrav
Microsoft Defender för Endpoint kräver något av följande volymlicensieringserbjudanden från Microsoft:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) som inkluderar Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 – säkerhet
- Microsoft 365 A5 – säkerhet
- Microsoft Defender för Endpoint

> [!NOTE]
> Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.
> Microsoft Defender för Endpoint kan också köpas från en leverantör av molnlösningar (CSP).

Microsoft Defender för slutpunkt för servrar kräver något av följande licensalternativ:

- [Azure Säkerhetscenter med Azure Defender aktiverat](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender för slutpunkt för server (en per server som omfattas)

> [!NOTE]
> Kunder kan skaffa serverlicenser (en per operativsystemmiljö för servrar (OSE)) för Microsoft Defender för Endpoint för servrar om de har kombinerat minst 50 licenser för en eller flera av följande användarlicenser:
>
> * Microsoft Defender för Endpoint
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 – säkerhet

Detaljerad licensinformation finns på webbplatsen [med produktvillkor och du](https://www.microsoft.com/licensing/terms/) kan arbeta med ditt kontoteam för att få mer information om villkoren.

Mer information om de många olika funktionerna i Windows 10-versioner finns i [Jämför Windows 10-utgåvor.](https://www.microsoft.com/windowsforbusiness/compare)

En detaljerad jämförelsetabell för den kommersiella jämförelsen av Windows 10-versioner finns i [JÄMFÖRELSEn AV PDF-format.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Webbläsarkrav
Åtkomst till Defender för Slutpunkt görs via en webbläsare med stöd för följande webbläsare:

- Microsoft Edge
- Internet Explorer version 11
- Google Chrome

> [!NOTE]
> Andra webbläsare kanske fungerar, men de nämnda webbläsarna är de som stöds.


## <a name="hardware-and-software-requirements"></a>Maskin- och programvarukrav

### <a name="supported-windows-versions"></a>Windows-versioner som stöds
- Windows 7 SP1 Enterprise[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, version 1803 eller senare
  - Windows Server 2019
- Windows Virtual Desktop

Enheter i nätverket måste köras på någon av dessa versioner.

Maskinvarukraven för Defender för Endpoint på enheter är samma för de versioner som stöds.

> [!NOTE]
> Datorer som kör mobila versioner av Windows (till exempel Windows CE och Windows 10 Mobile) stöds inte.
>
> Virtuella datorer med Windows 10 Enterprise 2016 LTSB kan stöta på prestandaproblem om de körs på virtualiseringsplattformar som inte är microsoft.
>
> För virtuella miljöer rekommenderar vi att du använder Windows 10 Enterprise LTSC 2019 eller senare.


### <a name="other-supported-operating-systems"></a>Andra operativsystem som stöds
- Android
- Linux
- macOS

> [!NOTE]
> Du måste känna till exakt vilka Linux-distributioner och versioner av Android och macOS som är kompatibla med Defender för Endpoint för att integreringen ska fungera.



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

**Använd kommandoraden för att kontrollera starttypen för Windows 10-diagnostikdatatjänsten:**

1. Öppna en upphöjd kommandoradsfråga på enheten:

   1.  Gå till **Start** och skriv **cmd**.

   1.  Högerklicka på **Kommandotolk** och välj **Kör som administratör.**

2. Ange följande kommando och tryck på **Retur:**

   ```console
   sc qc diagtrack
   ```

   Om tjänsten är aktiverad bör resultatet se ut som på följande skärmbild:

   ![Resultatet av sc-frågekommandot för diagtrack](images/windefatp-sc-qc-diagtrack.png)


Du måste ange att tjänsten ska startas automatiskt om tjänsten START_TYPE **är** inställd på **AUTO_START**.


**Använd kommandoraden för att ställa in Windows 10-diagnostikdatatjänsten så att den startas automatiskt:**

1.  Öppna en upphöjd kommandoradsfråga i slutpunkten:

    1. Gå till **Start** och skriv **cmd**.

    1. Högerklicka på **Kommandotolk** och välj **Kör som administratör.**

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

Defender för slutpunkts sensor kan använda en daglig genomsnittlig bandbredd på 5 MB för att kommunicera med Defender för Endpoint-molntjänsten och rapportera cyberdata. One-off-aktiviteter, till exempel filuppladdningar och insamling av undersökningspaket, ingår inte i den här dagliga genomsnittliga bandbredden.

Mer information om ytterligare proxykonfigurationsinställningar finns i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)

Innan du börjar använda enheter måste diagnostikdatatjänsten vara aktiverad. Tjänsten är aktiverad som standard i Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Krav för konfiguration av Microsoft Defender Antivirus
Defender för slutpunktsagenten är beroende av microsoft Defender Antiviruss möjlighet att söka igenom filer och ge information om dem.

Konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett om Microsoft Defender Antivirus är det aktiva program mot skadlig programvara eller inte. Mer information finns i Hantera [uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Om Microsoft Defender Antivirus inte är den aktiva skadlig programvara i organisationen och du använder Defender för slutpunktstjänsten, aktiveras Microsoft Defender Antivirus som passiv form.

Om din organisation har inaktiverat Microsoft Defender Antivirus genom grupprinciper eller andra metoder måste enheter som är onboarded uteslutas från den här grupprincipen.

Om du onboarding-servrar och Microsoft Defender Antivirus inte är det aktiva program mot skadlig programvara på servrarna måste du antingen konfigurera Microsoft Defender Antivirus för att gå på passiv form eller avinstallera det. Konfigurationen är beroende av serverversionen. Mer information finns i Kompatibilitet [för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> Din vanliga grupprincip gäller inte för skydd mot manipulering, och ändringar i inställningarna för Microsoft Defender Antivirus ignoreras när Skydd mot manipulering är på.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Drivrutinen Microsoft Defender Antivirus Early Launch Antimalware (ELAM) är aktiverad
Om du kör Microsoft Defender Antivirus som primärt program mot skadlig programvara på dina enheter kan Defender för Slutpunkt-agenten registrera sig.

Om du kör en tredjepartsklient för program mot skadlig programvara och använder mobila enhetshanteringslösningar eller Microsoft Endpoint Manager (current branch) måste du se till att Microsoft Defender Antivirus ELAM-drivrutinen är aktiverad. Mer information finns i Se [till att Microsoft Defender Antivirus inte är inaktiverat enligt policy.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>Relaterade ämnen
- [Konfigurera Microsoft Defender för distribution av Slutpunkt](production-deployment.md)
- [Onboard-enheter](onboard-configure.md)
