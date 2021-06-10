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
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e6b71-103">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="e6b71-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="e6b71-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e6b71-104">**Applies to:**</span></span>
- [<span data-ttu-id="e6b71-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="e6b71-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="e6b71-106">VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e6b71-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="e6b71-107">Microsoft 365 Stöd för dataförlustskydd för slutpunkter för Windows virtuella skrivbordet har stöd för scenarier med enstaka sessioner.</span><span class="sxs-lookup"><span data-stu-id="e6b71-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="e6b71-108">Scenarier med flera sessioner på Windows virtuellt skrivbord stöds för närvarande inte.</span><span class="sxs-lookup"><span data-stu-id="e6b71-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="e6b71-109">Introducera VDI-enheter</span><span class="sxs-lookup"><span data-stu-id="e6b71-109">Onboard VDI devices</span></span>

<span data-ttu-id="e6b71-110">Microsoft 365 Skydd mot dataförlust i slutpunkten stöder icke-fortlöpande VDI-sessionsindelning.</span><span class="sxs-lookup"><span data-stu-id="e6b71-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="e6b71-111">Om du vill registrera icke-beständiga VDI-sessioner måste VDI-enheter Windows 10 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="e6b71-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="e6b71-112">Det kan finnas associerade utmaningar vid registrering av VDE:er.</span><span class="sxs-lookup"><span data-stu-id="e6b71-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="e6b71-113">Följande är vanliga utmaningar med det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="e6b71-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="e6b71-114">Direkt snabb registrering av korta sessioner, som måste introduceras till Microsoft 365 skydd mot dataförlust innan den faktiska etableringen.</span><span class="sxs-lookup"><span data-stu-id="e6b71-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="e6b71-115">Enhetsnamnet återanvänds vanligtvis för nya sessioner.</span><span class="sxs-lookup"><span data-stu-id="e6b71-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="e6b71-116">VDI-enheter kan visas i Microsoft 365 kompatibilitetscenter som antingen:</span><span class="sxs-lookup"><span data-stu-id="e6b71-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="e6b71-117">Enskild post för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="e6b71-117">Single entry for each device.</span></span>  
<span data-ttu-id="e6b71-118">Observera att i det här fallet *måste samma* enhetsnamn konfigureras när sessionen skapas, till exempel med en obevakad svarsfil.</span><span class="sxs-lookup"><span data-stu-id="e6b71-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="e6b71-119">Flera poster för varje enhet – en för varje session.</span><span class="sxs-lookup"><span data-stu-id="e6b71-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="e6b71-120">Följande steg vägleder dig genom introduktionen av VDI-enheter och visar steg för enskilda och flera poster.</span><span class="sxs-lookup"><span data-stu-id="e6b71-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="e6b71-121">För miljöer där det finns konfigurationer för låga resurser kan VDI-startproceduren göra att Microsoft 365 det går långsamt att registrera dataförlustskydd i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="e6b71-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="e6b71-122">Öppna filen för VDI-.zip *(DeviceCompliancePackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="e6b71-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="e6b71-123">I navigeringsfönstret väljer du **Inställningar**  >  **Onboarding**  >  **Onboarding för enheter.**</span><span class="sxs-lookup"><span data-stu-id="e6b71-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="e6b71-124">Välj  **VDI-onboardingskript för icke-beständiga slutpunkter i fältet Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="e6b71-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="e6b71-125">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="e6b71-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="e6b71-126">Kopiera filerna från mappen DeviceCompliancePackage som extraheras från .zip-filen till `golden/master` bilden under sökvägen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="e6b71-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="e6b71-127">Om du inte implementerar en enskild post för varje enhet kopierar du DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e6b71-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="e6b71-128">Om du implementerar en enskild post för varje enhet kopierar du både Onboard-NonPersistentMachine.ps1 och DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e6b71-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6b71-129">Om du inte ser mappen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` kan den vara dold.</span><span class="sxs-lookup"><span data-stu-id="e6b71-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="e6b71-130">Du måste välja alternativet Visa **dolda filer och mappar i** Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="e6b71-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="e6b71-131">Öppna ett fönster för redigeraren för lokala grupprinciper och gå **till**  >  **Datorkonfiguration Windows Inställningar** vid start  >  **av**  >  **skript.**</span><span class="sxs-lookup"><span data-stu-id="e6b71-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6b71-132">Domain Group Policy kan också användas för registrering av icke-beständiga VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="e6b71-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="e6b71-133">Beroende på vilken metod du vill implementera följer du lämpliga steg:</span><span class="sxs-lookup"><span data-stu-id="e6b71-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="e6b71-134">**För enskild inmatning för varje enhet**</span><span class="sxs-lookup"><span data-stu-id="e6b71-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="e6b71-135">Välj fliken **PowerShell-skript** och klicka sedan på Lägg till **(Windows** Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="e6b71-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e6b71-136">Navigera till onboarding PowerShell-skript `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e6b71-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="e6b71-137">**För flera poster för varje enhet:**</span><span class="sxs-lookup"><span data-stu-id="e6b71-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="e6b71-138">Välj fliken **Skript och** klicka sedan **på** Lägg till (Windows Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="e6b71-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e6b71-139">Navigera till bash-skriptet `DeviceComplianceOnboardingScript.cmd` onboarding.</span><span class="sxs-lookup"><span data-stu-id="e6b71-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="e6b71-140">Testa lösningen:</span><span class="sxs-lookup"><span data-stu-id="e6b71-140">Test your solution:</span></span>

   1. <span data-ttu-id="e6b71-141">Skapa en pool med en enhet.</span><span class="sxs-lookup"><span data-stu-id="e6b71-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="e6b71-142">Logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="e6b71-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="e6b71-143">Logga ut från enhet.</span><span class="sxs-lookup"><span data-stu-id="e6b71-143">Logoff from device.</span></span>

   1. <span data-ttu-id="e6b71-144">Logga in på enhet med en annan användare.</span><span class="sxs-lookup"><span data-stu-id="e6b71-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="e6b71-145">**För enskild post för varje enhet:** Kontrollera bara en post i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="e6b71-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="e6b71-146">**För flera poster för varje enhet:** Kontrollera flera poster i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="e6b71-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="e6b71-147">Klicka **på listan** Enheter i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e6b71-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="e6b71-148">Använd sökfunktionen genom att ange enhetens namn och välja **Enhet** som söktyp.</span><span class="sxs-lookup"><span data-stu-id="e6b71-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="e6b71-149">Uppdatera icke-beständiga VDI-bilder (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e6b71-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="e6b71-150">Vi rekommenderar att du använder offlineserviceverktyg för att korrigera gyllene/huvudbilder.</span><span class="sxs-lookup"><span data-stu-id="e6b71-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="e6b71-151">Du kan till exempel använda kommandona nedan för att installera en uppdatering medan bilden förblir offline:</span><span class="sxs-lookup"><span data-stu-id="e6b71-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="e6b71-152">Mer information om DISM-kommandon och offlineunderhåll finns i artiklarna nedan:</span><span class="sxs-lookup"><span data-stu-id="e6b71-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="e6b71-153">Ändra en Windows bild med DISM</span><span class="sxs-lookup"><span data-stu-id="e6b71-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="e6b71-154">DISM Image Management Command-Line Options</span><span class="sxs-lookup"><span data-stu-id="e6b71-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="e6b71-155">Minska storleken på komponentarkivet i en offline-Windows bild</span><span class="sxs-lookup"><span data-stu-id="e6b71-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="e6b71-156">Om offlineunderhåll inte är ett möjligt alternativ för din icke-beständiga VDI-miljö bör du vidta följande steg för att säkerställa konsekvens och sensorhälsa:</span><span class="sxs-lookup"><span data-stu-id="e6b71-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="e6b71-157">När huvudbilden har startats för onlineunderhåll eller korrigering kör du ett offboardingskript för att stänga av Microsoft 365 sensor för dataförlustskydd.</span><span class="sxs-lookup"><span data-stu-id="e6b71-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="e6b71-158">Mer information finns i [Offboard-enheter som använder ett lokalt skript.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="e6b71-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="e6b71-159">Kontrollera att sensorn stoppas genom att köra kommandot nedan i ett CMD-fönster:</span><span class="sxs-lookup"><span data-stu-id="e6b71-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="e6b71-160">Tjänst för bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="e6b71-160">Service the image as needed.</span></span>

4. <span data-ttu-id="e6b71-161">Kör kommandona nedan med PsExec.exe (som kan laddas ned från för att rensa innehållet i cybermappen som sensorn kan ha ackumulerat https://download.sysinternals.com/files/PSTools.zip) sedan starten:</span><span class="sxs-lookup"><span data-stu-id="e6b71-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="e6b71-162">Omsälsa den gyllene bilden/originalbilden som vanligt.</span><span class="sxs-lookup"><span data-stu-id="e6b71-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6b71-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e6b71-163">Related topics</span></span>
- [<span data-ttu-id="e6b71-164">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="e6b71-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="e6b71-165">Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6b71-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="e6b71-166">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="e6b71-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="e6b71-167">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="e6b71-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="e6b71-168">Felsöka Microsoft Defender Avancerat skydd onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="e6b71-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)