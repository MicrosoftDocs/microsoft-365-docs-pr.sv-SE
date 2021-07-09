---
title: Registrera Windows 10-enheter med konfigurationshanteraren
description: Använd Konfigurationshanteraren för att distribuera konfigurationspaketet på enheter så att enheter kan kommas in i tjänsten.
keywords: onboard devices using sccm, device management, configure Microsoft Defender for Endpoint devices
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
ms.topic: article
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d7c319e37fb804ee4dac3b6bff402942bbc2fa79
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339664"
---
# <a name="onboard-the-windows-10-devices-using-configuration-manager"></a>Få igång Windows 10 med konfigurationshanteraren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager current branch
- System Center 2012 R2 Configuration Manager

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Klientoperativsystemet som stöds

Beroende på vilken version av Konfigurationshanteraren du kör kan följande klientoperativsystemet registreras:

#### <a name="configuration-manager-version-1910-and-prior"></a>Konfigurationshanteraren version 1910 och tidigare

- Klienter som kör Windows 10 

#### <a name="configuration-manager-version-2002-and-later"></a>Konfigurationshanteraren version 2002 och senare

Från och med Konfigurationshanteraren version 2002 kan du registrera följande operativsystem:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016, version 1803 eller senare
- Windows Server 2019

>[!NOTE]
>Mer information om hur du onboardar Windows Server 2012 R2, Windows Server 2016 och Windows Server 2019 finns i [Onboard Windows-servrar.](configure-server-endpoints.md)



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboard-enheter som använder System Center Configuration Manager


[![Bild av PDF-filen som visar de olika distributionssökvägarna](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Läs PDF- [eller](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om du vill se de olika sökvägarna i distributionen av Microsoft Defender för Slutpunkt. 



1. Öppna konfigurationspaketet för Konfigurationshanteraren .zip *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding. Du kan också hämta paketet från [Microsoft 365 Defender portal:](https://security.microsoft.com/)

    1. I navigeringsfönstret väljer du **Inställningar**  >  **Endpoints**  >  **Device Management**  >  **Onboarding**.
    
    1. Välj Windows 10 som operativsystem.

    1. I fältet **Distributionsmetod** väljer du **System Center Configuration Manager 2012/2012 R2/1511/1602.**
    
    1. Välj **Ladda ned** paket och spara .zip filen.

2. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med namnet *WindowsDefenderATPOnboardingScript.cmd*.

3. Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Välj en fördefinierad enhetssamling att distribuera paketet till.

> [!NOTE]
> Defender för Endpoint har inte stöd för onboarding under fas [OOBE (Out-Box Experience).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Se till att användarna slutför OOBE när de har Windows installationen eller uppgraderingen.

>[!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunkt-enhet](run-detection-test.md).
>
> Observera att det är möjligt att skapa en identifieringsregel i ett Configuration Manager-program för att kontinuerligt kontrollera om en enhet har introducerats. Ett program är en annan typ av objekt än ett paket och ett program.
> Om en enhet ännu inte är igång (på grund av att OOBE har slutförts eller av någon annan anledning) försöker Konfigurationshanteraren att registrera enheten igen tills regeln identifierar statusändringen.
> 
> Du kan åstadkomma detta genom att skapa en kontroll för identifieringsregel om registervärdet "OnboardingState" (av typen REG_DWORD) = 1.
> Registervärdet finns under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Mer information finns i Konfigurera [identifieringsmetoder i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Konfigurera exempelsamlingsinställningar

För varje enhet kan du ange ett konfigurationsvärde för att ange om exempel kan samlas in från enheten när en förfrågan görs via Microsoft 365 Defender för att skicka in en fil för djupanalys.

>[!NOTE]
>De här konfigurationsinställningarna görs vanligtvis via Konfigurationshanteraren.

Du kan ange en regel för efterlevnad för konfigurationsobjektet i Konfigurationshanteraren om du vill ändra inställningen för exempelresursen på en enhet.

Den här regeln bör vara *ett konfigurationsobjekt* för efterlevnadsregel som anger värdet på en registernyckel på riktade enheter för att säkerställa att de är klagomål.

Konfigurationen anges via följande registernyckelpost:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Var:<br>
Nyckeltyp är en D-WORD. <br>
Möjliga värden är:
- 0 – tillåter inte exempeldelning från den här enheten
- 1 – tillåter delning av alla filtyper från den här enheten

Standardvärdet är 1 om registernyckeln inte finns.

Mer information om hur System Center Configuration Manager efterlevnad finns i Introduktion till efterlevnadsinställningar [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>Andra rekommenderade konfigurationsinställningar
Efter att du har introducerat enheter för tjänsten är det viktigt att du utnyttjar de skyddsfunktioner som ingår i tjänsten genom att aktivera dem med följande rekommenderade konfigurationsinställningar.

### <a name="device-collection-configuration"></a>Konfiguration av enhetssamling
Om du använder Endpoint Configuration Manager, version 2002 eller senare, kan du välja att bredda distributionen så att den omfattar servrar eller klienter på nednivå.


### <a name="next-generation-protection-configuration"></a>Nästa generations skyddskonfiguration
Följande konfigurationsinställningar rekommenderas:

**Skanna** <br>
- Skanna flyttbara lagringsenheter, till exempel USB-enheter: Ja

**Realtidsskydd** <br>
- Aktivera beteendeuppföljning: Ja
- Aktivera skydd mot potentiellt oönskade program vid nedladdning och före installationen: Ja

**Molnskyddstjänst**
- Molnskyddstjänsttyp: Avancerat medlemskap

**Minskning av attackytan** Konfigurera alla tillgängliga regler för granskning.

>[!NOTE]
> Att blockera dessa aktiviteter kan avbryta legitima affärsprocesser. Det bästa sättet är att ange allt som ska granskas, identifiera vilka som är säkra att aktivera och sedan aktivera inställningarna på slutpunkter som inte har falsk positiv identifiering.


**Nätverksskydd** <br>
Innan du aktiverar nätverksskydd i gransknings- eller blockeringsläge bör du kontrollera att du har installerat uppdateringen för program mot skadlig kod som kan fås från [supportsidan.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Kontrollerad mappåtkomst**<br>
Aktivera funktionen i granskningsläge i minst 30 dagar. Granska identifieringar och skapa en lista över program som får skriva i skyddade kataloger efter den här perioden.

Mer information finns i Utvärdera [reglerad mappåtkomst.](evaluate-controlled-folder-access.md)


## <a name="offboard-devices-using-configuration-manager"></a>Offboard-enheter med Konfigurationshanteraren

Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketets namn.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Offboard-enheter som Microsoft Endpoint Manager current branch

Om du använder Microsoft Endpoint Manager current branch, se [Skapa en konfigurationsfil för offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboard-enheter med System Center 2012 R2 Configuration Manager

1. Hämta offboarding-paketet från [Microsoft 365 Defender portalen:](https://security.microsoft.com/)

    1. I navigeringsfönstret väljer du **Inställningar**  >  **Ändpunkter**  >  **Enhetshantering**  >   **Offboarding**.

    1. Välj Windows 10 som operativsystem.

    1. I fältet **Distributionsmetod** väljer du **System Center Configuration Manager 2012/2012 R2/1511/1602.**
    
    1. Välj **Ladda ned** paket och spara .zip filen.

2. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med *namnet WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Välj en fördefinierad enhetssamling att distribuera paketet till.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.


## <a name="monitor-device-configuration"></a>Övervaka enhetskonfiguration

Om du använder en Microsoft Endpoint Manager gren använder du den inbyggda Defender för slutpunkt-instrumentpanelen i konfigurationshanterarens konsol. Mer information finns i [Defender för slutpunkt – bildskärm.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Om du använder konfigurationshanteraren System Center 2012 R2 består övervakning av två delar:

1. Bekräfta att konfigurationspaketet har distribuerats korrekt och körs (eller har körts) på enheterna i nätverket.

2. Kontrollera att enheterna är kompatibla med Defender för Slutpunkt-tjänsten (detta säkerställer att enheten kan slutföra onboarding-processen och kan fortsätta att rapportera data till tjänsten).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Bekräfta att konfigurationspaketet har distribuerats korrekt

1. Klicka på Övervakning längst ned i **navigeringsfönstret** i konfigurationshanterarens konsol.

2. Välj **Översikt** och **sedan Distributioner.**

3. Välj på distributionen med paketets namn.

4. Granska statusindikatorerna under **Slutstatistik** och **Innehållsstatus.**

    Om distributionen misslyckades (enheter med **fel-** och krav **som** inte uppfylls eller **statusen Misslyckades)** kan du behöva felsöka enheterna. Mer information finns i Felsöka [problem med Microsoft Defender för slutpunkts onboarding.](troubleshoot-onboarding.md)

    ![Konfigurationshanteraren visar en lyckad distribution utan fel](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Kontrollera att enheterna är kompatibla med Microsoft Defender för slutpunktstjänsten

Du kan ange en regel för efterlevnad för konfigurationsobjekt i System Center 2012 R2 Configuration Manager för att övervaka distributionen.

Den här regeln bör vara *ett konfigurationsobjekt som inte åtgärdar* konfigurationsobjekt för efterlevnadsregel som övervakar värdet för en registernyckel på riktade enheter.

Övervaka följande registernyckelpost:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Mer information finns i Introduktion [till inställningar för efterlevnad i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med grupprincip](configure-endpoints-gp.md)
- [Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](configure-endpoints-mdm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](configure-endpoints-script.md)
- [Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](configure-endpoints-vdi.md)
- [Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet](run-detection-test.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
