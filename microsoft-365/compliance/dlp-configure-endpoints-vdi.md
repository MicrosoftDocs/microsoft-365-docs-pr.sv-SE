---
title: Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)
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
description: Distribuera konfigurationspaketet på en VDI-enhet (Virtual Desktop Infrastructure) så att de introduceras till Microsoft 365 För att förhindra dataförlust.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162008"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)

**Gäller för:**
- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](./endpoint-dlp-learn-about.md)

- VDI-enheter (Virtual Desktop Infrastructure)

>[!WARNING]
> Microsoft 365 Stöd för dataförlustskydd för slutpunkter för Windows virtuella skrivbordet har stöd för scenarier med enstaka sessioner. Scenarier med flera sessioner på Windows virtuellt skrivbord stöds för närvarande inte.

## <a name="onboard-vdi-devices"></a>Introducera VDI-enheter

Microsoft 365 Skydd mot dataförlust i slutpunkten stöder icke-fortlöpande VDI-sessionsindelning. 

>[!Note]
>Om du vill registrera icke-beständiga VDI-sessioner måste VDI-enheter Windows 10 1809 eller senare.

Det kan finnas associerade utmaningar vid registrering av VDE:er. Följande är vanliga utmaningar med det här scenariot:

- Direkt snabb registrering av korta sessioner, som måste introduceras till Microsoft 365 skydd mot dataförlust innan den faktiska etableringen.
- Enhetsnamnet återanvänds vanligtvis för nya sessioner.

VDI-enheter kan visas i Microsoft 365 kompatibilitetscenter som antingen:

- Enskild post för varje enhet.  
Observera att i det här fallet *måste samma* enhetsnamn konfigureras när sessionen skapas, till exempel med en obevakad svarsfil.
- Flera poster för varje enhet – en för varje session.

Följande steg vägleder dig genom introduktionen av VDI-enheter och visar steg för enskilda och flera poster.

>[!WARNING]
> För miljöer där det finns konfigurationer för låga resurser kan VDI-startproceduren göra att Microsoft 365 det går långsamt att registrera dataförlustskydd i slutpunkten. 

1.  Öppna filen för VDI-.zip *(DeviceCompliancePackage.zip)* som du laddade ned från guiden för service onboarding.

2.  I navigeringsfönstret väljer du **Inställningar**  >  **Onboarding**  >  **Onboarding för enheter.**

3. Välj  **VDI-onboardingskript för icke-beständiga slutpunkter i fältet Distributionsmetod.**

5. Klicka **på Ladda ned** paket och spara .zip filen.

6. Kopiera filerna från mappen DeviceCompliancePackage som extraheras från .zip-filen till `golden/master` bilden under sökvägen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Om du inte implementerar en enskild post för varje enhet kopierar du DeviceComplianceOnboardingScript.cmd.

8. Om du implementerar en enskild post för varje enhet kopierar du både Onboard-NonPersistentMachine.ps1 och DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Om du inte ser mappen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` kan den vara dold. Du måste välja alternativet Visa **dolda filer och mappar i** Utforskaren.

9. Öppna ett fönster för redigeraren för lokala grupprinciper och gå **till**  >  **Datorkonfiguration Windows Inställningar** vid start  >  **av**  >  **skript.**

   > [!NOTE]
   > Domain Group Policy kan också användas för registrering av icke-beständiga VDI-enheter.

4. Beroende på vilken metod du vill implementera följer du lämpliga steg:

   **För enskild inmatning för varje enhet**
   
   Välj fliken **PowerShell-skript** och klicka sedan på Lägg till **(Windows** Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare). Navigera till onboarding PowerShell-skript `Onboard-NonPersistentMachine.ps1` .
   
   **För flera poster för varje enhet:**
   
   Välj fliken **Skript och** klicka sedan **på** Lägg till (Windows Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare). Navigera till bash-skriptet `DeviceComplianceOnboardingScript.cmd` onboarding.

5. Testa lösningen:

   1. Skapa en pool med en enhet.
      
   1. Logga in på enheten.
      
   1. Logga ut från enhet.

   1. Logga in på enhet med en annan användare.
      
   1. **För enskild post för varje enhet:** Kontrollera bara en post i Microsoft Defender Säkerhetscenter.<br>
      **För flera poster för varje enhet:** Kontrollera flera poster i Microsoft Defender Säkerhetscenter.

6. Klicka **på listan** Enheter i navigeringsfönstret.

7. Använd sökfunktionen genom att ange enhetens namn och välja **Enhet** som söktyp.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Uppdatera icke-beständiga VDI-bilder (Virtual Desktop Infrastructure)
Vi rekommenderar att du använder offlineserviceverktyg för att korrigera gyllene/huvudbilder.<br>
Du kan till exempel använda kommandona nedan för att installera en uppdatering medan bilden förblir offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Mer information om DISM-kommandon och offlineunderhåll finns i artiklarna nedan:
- [Ändra en Windows bild med DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM Image Management Command-Line Options](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Minska storleken på komponentarkivet i en offline-Windows bild](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Om offlineunderhåll inte är ett möjligt alternativ för din icke-beständiga VDI-miljö bör du vidta följande steg för att säkerställa konsekvens och sensorhälsa:

1. När huvudbilden har startats för onlineunderhåll eller korrigering kör du ett offboardingskript för att stänga av Microsoft 365 sensor för dataförlustskydd. Mer information finns i [Offboard-enheter som använder ett lokalt skript.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Kontrollera att sensorn stoppas genom att köra kommandot nedan i ett CMD-fönster:

   ```console
   sc query sense
   ```

3. Tjänst för bilden efter behov.

4. Kör kommandona nedan med PsExec.exe (som kan laddas ned från för att rensa innehållet i cybermappen som sensorn kan ha ackumulerat https://download.sysinternals.com/files/PSTools.zip) sedan starten:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Omsälsa den gyllene bilden/originalbilden som vanligt.

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med grupprincip](dlp-configure-endpoints-gp.md)
- [Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](dlp-configure-endpoints-mdm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](dlp-configure-endpoints-script.md)
- [Felsöka Microsoft Defender Avancerat skydd onboarding-problem](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)