---
title: Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)
description: Distribuera konfigurationspaketet på en VDI-enhet (Virtual Desktop Infrastructure) så att de introduceras till Microsoft Defender för slutpunktstjänsten.
keywords: konfigurera VDI-enhet (Virtual Desktop Infrastructure), vdi, enhetshantering, konfigurera Microsoft Defender för slutpunkt, slutpunkter
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
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843216"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- VDI-enheter (Virtual Desktop Infrastructure)
- Windows 10, Windows Server 2019 Windows Server 2008R2/2012R2/2016

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)

Defender för Endpoint har stöd för icke-fortlöpande registrering av VDI-sessioner. 


Det kan finnas associerade utmaningar vid registrering av VDE:er. Följande är vanliga utmaningar med det här scenariot:

- Direkt tidig registrering av korta sessioner, som måste introduceras till Defender för Endpoint innan den faktiska etableringen.
- Enhetsnamnet återanvänds vanligtvis för nya sessioner.

VDI-enheter kan visas i Defender för Endpoint-portalen som antingen:

- Enskild post för varje enhet.

  > [!NOTE]
  > I det här fallet måste *samma* enhetsnamn konfigureras när sessionen skapas, till exempel med en obevakad svarsfil.

- Flera poster för varje enhet – en för varje session.

Följande steg vägleder dig genom introduktionen av VDI-enheter och visar steg för enskilda och flera poster.

>[!WARNING]
> För miljöer där det finns konfigurationer med låg resurs kan VDI-startproceduren göra att Defender för Slutpunkts sensorbaserad hastighet går långsammare. 


### <a name="for-windows-10-or-windows-server-2019"></a>För Windows 10 eller Windows Server 2019

1.  Öppna filen för VDI-.zip *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding. Du kan också hämta paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)

    1.  I navigeringsfönstret väljer du **Inställningar**  >  **Onboarding**.

    1. Välj Windows 10 som operativsystem.

    1.  Välj  **VDI-onboardingskript för icke-beständiga slutpunkter i fältet Distributionsmetod.**

    1. Klicka **på Ladda ned** paket och spara .zip filen.

2. Kopiera filerna från mappen WindowsDefenderATPOnboardingPackage som extraherats från .zip-filen `golden/master` till bilden under sökvägen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

    1. Om du inte implementerar en enda post för varje enhet kopierar du WindowsDefenderATPOnboardingScript.cmd.

    1. Om du implementerar en enda post för varje enhet kopierar du både Onboard-NonPersistentMachine.ps1 och WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Om du inte ser mappen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` kan den vara dold. Du måste välja alternativet Visa **dolda filer och mappar i** Utforskaren.

3. Öppna ett fönster för redigeraren för lokala grupprinciper och gå **till**  >  **Datorkonfiguration Windows Inställningar** vid start  >  **av**  >  **skript.**

   > [!NOTE]
   > Domain Group Policy kan också användas för registrering av icke-beständiga VDI-enheter.

4. Beroende på vilken metod du vill implementera följer du lämpliga steg:

   - För enskild inmatning för varje enhet:
   
     Välj fliken **PowerShell-skript** och klicka sedan på Lägg till **(Windows** Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare). Navigera till onboarding PowerShell-skript `Onboard-NonPersistentMachine.ps1` . Du behöver inte ange den andra filen eftersom den utlöses automatiskt.
   
   - För flera poster för varje enhet:
   
     Välj fliken **Skript och** klicka sedan **på** Lägg till (Windows Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare). Navigera till bash-skriptet `WindowsDefenderATPOnboardingScript.cmd` onboarding.

5. Testa lösningen:

   1. Skapa en pool med en enhet.
      
   1. Logga in på enheten.
      
   1. Logga ut från enhet.

   1. Logga in på enhet med en annan användare.
      
   1. Beroende på vilken metod du vill implementera följer du lämpliga steg:
   
      - För enskild inmatning för varje enhet: 
    
        Markera bara en post i Microsoft Defender Säkerhetscenter.

      - För flera poster för varje enhet: 
       
        Kontrollera flera poster i Microsoft Defender Säkerhetscenter.

6. Klicka **på listan** Enheter i navigeringsfönstret.

7. Använd sökfunktionen genom att ange enhetens namn och välja **Enhet** som söktyp.


## <a name="for-downlevel-skus"></a>För nedåtnivå-SKU:er

> [!NOTE]
> Följande register är bara relevanta när syftet är att uppnå en "enskild post för varje enhet".

1. Ställ in registervärdet på:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    eller använda kommandorad:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Följ [server onboarding-processen](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016). 



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

1. När huvudbilden startats för onlineunderhåll eller korrigering kör du ett offboardingskript för att inaktivera Defender för Slutpunkts sensor. Mer information finns i [Offboard-enheter som använder ett lokalt skript.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

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
- [Introducera Windows 10 enheter med grupprincip](configure-endpoints-gp.md)
- [Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](configure-endpoints-mdm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](configure-endpoints-script.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
