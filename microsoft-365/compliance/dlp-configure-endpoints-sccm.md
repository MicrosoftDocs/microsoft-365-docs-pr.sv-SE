---
title: Registrera Windows 10-enheter med konfigurationshanteraren
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Använd Konfigurationshanteraren för att distribuera konfigurationspaketet på enheter så att de introduceras till tjänsten.
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162760"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Registrera Windows 10-enheter med konfigurationshanteraren

**Gäller för:**

- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](./endpoint-dlp-learn-about.md)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboard-enheter som använder System Center Configuration Manager

1. Öppna konfigurationspaketet för Konfigurationshanteraren .zip *(DeviceComplianceOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding. Du kan också hämta paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)

2. I navigeringsfönstret väljer du **Inställningar**  >  **Onboarding**  >  **Onboarding för enheter.**

3. I fältet **Distributionsmetod** väljer du **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
 
4. Välj **Ladda ned** paket och spara .zip filen.

5. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med namnet *DeviceComplianceOnboardingScript.cmd*.

6. Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))

7. Välj en fördefinierad enhetssamling att distribuera paketet till.

> [!NOTE]
> Microsoft 365 Dataförlustskydd i slutpunkten stöder inte onboarding under fas [OOBE (Out-Box Experience).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Se till att användarna slutför OOBE när de har Windows installationen eller uppgraderingen.

>[!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
>
> Observera att det är möjligt att skapa en identifieringsregel i ett Configuration Manager-program för att kontinuerligt kontrollera om en enhet har introducerats. Ett program är en annan typ av objekt än ett paket och ett program.
> Om en enhet ännu inte är igång (på grund av att OOBE har slutförts eller av någon annan anledning) försöker Konfigurationshanteraren att registrera enheten igen tills regeln identifierar statusändringen.
> 
> Du kan åstadkomma detta genom att skapa en kontroll för identifieringsregel om registervärdet "OnboardingState" (av typen REG_DWORD) = 1.
> Registervärdet finns under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Mer information finns i Konfigurera [identifieringsmetoder i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Konfigurera exempelsamlingsinställningar

För varje enhet kan du ange ett konfigurationsvärde för att ange om exempel kan samlas in från enheten när en förfrågan görs via Microsoft Defender Säkerhetscenter att skicka en fil för djupanalys.

>[!NOTE]
>De här konfigurationsinställningarna görs vanligtvis via Konfigurationshanteraren. 

Du kan ange en regel för efterlevnad för konfigurationsobjektet i Konfigurationshanteraren om du vill ändra inställningen för exempelresursen på en enhet.

Den här regeln bör vara *ett konfigurationsobjekt* för efterlevnadsregel som anger värdet på en registernyckel på riktade enheter för att säkerställa att de är klagomål.

Konfigurationen anges via följande registernyckelpost:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Var:<br>
Nyckeltyp är en D-WORD. <br>
Möjliga värden är:
- 0 – tillåter inte exempeldelning från den här enheten
- 1 – tillåter delning av alla filtyper från den här enheten

Standardvärdet är 1 om registernyckeln inte finns.

Mer information om hur System Center Configuration Manager efterlevnad finns i Introduktion till efterlevnadsinställningar [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))


## <a name="other-recommended-configuration-settings"></a>Andra rekommenderade konfigurationsinställningar
Efter att du har introducerat enheter för tjänsten är det viktigt att du utnyttjar de skyddsfunktioner som ingår i tjänsten genom att aktivera dem med följande rekommenderade konfigurationsinställningar.

### <a name="device-collection-configuration"></a>Konfiguration av enhetssamling
Om du använder Endpoint Configuration Manager, version 2002 eller senare, kan du välja att bredda distributionen så att den omfattar servrar eller klienter på nednivå.


### <a name="next-generation-protection-configuration"></a>Nästa generations skyddskonfiguration

Följande konfigurationsinställningar rekommenderas:

**Skanna**

- Skanna flyttbara lagringsenheter, till exempel USB-enheter: Ja

**Realtidsskydd**

- Aktivera beteendeuppföljning: Ja
- Aktivera skydd mot potentiellt oönskade program vid nedladdning och före installationen: Ja

**Molnskyddstjänst**

- Molnskyddstjänsttyp: Avancerat medlemskap

**Minskning av attackytan** Konfigurera alla tillgängliga regler för granskning.

>[!NOTE]
> Att blockera dessa aktiviteter kan avbryta legitima affärsprocesser. Det bästa sättet är att ange allt som ska granskas, identifiera vilka som är säkra att aktivera och sedan aktivera inställningarna på slutpunkter som inte har falsk positiv identifiering.

**Nätverksskydd**

Innan du aktiverar nätverksskydd i gransknings- eller blockeringsläge bör du kontrollera att du har installerat uppdateringen för program mot skadlig kod som kan fås från [supportsidan.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Kontrollerad mappåtkomst**

Aktivera funktionen i granskningsläge i minst 30 dagar. Granska identifieringar och skapa en lista över program som får skriva i skyddade kataloger efter den här perioden.

Mer information finns i Utvärdera [reglerad mappåtkomst.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)


## <a name="offboard-devices-using-configuration-manager"></a>Offboard-enheter med Konfigurationshanteraren

Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketets namn.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Offboard-enheter som Microsoft Endpoint Configuration Manager current branch

Om du använder Microsoft Endpoint Configuration Manager current branch finns mer information [i Skapa en konfigurationsfil för offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboard-enheter med System Center 2012 R2 Configuration Manager

1. Hämta offboarding-paketet från [Microsofts efterlevnadscenter:](https://compliance.microsoft.com/)

2. I navigeringsfönstret väljer du **Inställningar**  >   **Avboarding av** >  **enheten.**

3. Välj Windows 10 som operativsystem.

4. I fältet **Distributionsmetod** väljer du **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
    
5. Välj **Ladda ned** paket och spara .zip filen.

6. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med *namnet DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

7. Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))

8. Välj en fördefinierad enhetssamling att distribuera paketet till.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.


## <a name="monitor-device-configuration"></a>Övervaka enhetskonfiguration

Om du använder en Microsoft Endpoint Configuration Manager gren använder du den inbyggda Microsoft Defender för slutpunkt-instrumentpanelen i konfigurationshanterarens konsol. Mer information finns i [Microsoft Defender Avancerat skydd - Bildskärm.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Om du använder konfigurationshanteraren System Center 2012 R2 består övervakning av två delar:

1. Bekräfta att konfigurationspaketet har distribuerats korrekt och körs (eller har körts) på enheterna i nätverket.

2. Kontrollera att enheterna är kompatibla med Microsoft 365 Endpoint-tjänsten för dataförlustskydd (det säkerställer att enheten kan slutföra onboarding-processen och kan fortsätta rapportera data till tjänsten).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Bekräfta att konfigurationspaketet har distribuerats korrekt

1. Klicka på Övervakning längst ned i **navigeringsfönstret** i konfigurationshanterarens konsol.

2. Välj **Översikt** och **sedan Distributioner.**

3. Välj på distributionen med paketets namn.

4. Granska statusindikatorerna under **Slutstatistik** och **Innehållsstatus.**

    Om distributionen misslyckades (enheter med **fel-** och krav **som** inte uppfylls eller **statusen Misslyckades)** kan du behöva felsöka enheterna. Mer information finns i Felsöka [problem Microsoft Defender Avancerat skydd-introduktion.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

    ![Konfigurationshanteraren visar en lyckad distribution utan fel](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Kontrollera att enheterna är kompatibla med Microsoft 365 ändpunktstjänst för dataförlustskydd

Du kan ange en regel för efterlevnad för konfigurationsobjekt i System Center 2012 R2 Configuration Manager för att övervaka distributionen.

> [!NOTE]
> Denna procedur och registerpost gäller för Endpoint DLP samt Advanced Threat Protection.

Den här regeln bör vara *ett konfigurationsobjekt som inte åtgärdar* konfigurationsobjekt för efterlevnadsregel som övervakar värdet för en registernyckel på riktade enheter.

Övervaka följande registernyckelpost:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Mer information finns i Introduktion [till inställningar för efterlevnad i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med grupprincip](dlp-configure-endpoints-gp.md)
- [Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](dlp-configure-endpoints-mdm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](dlp-configure-endpoints-script.md)
- [Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Felsöka Microsoft Defender Avancerat skydd onboarding-problem](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)