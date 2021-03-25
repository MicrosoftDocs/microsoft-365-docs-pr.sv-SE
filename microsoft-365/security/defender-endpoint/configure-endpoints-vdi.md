---
title: Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)
description: Distribuera konfigurationspaketet på en VDI-enhet (Virtual Desktop Infrastructure) så att de introduceras till Tjänsten Microsoft Defender ATP.
keywords: konfigurera VDI-enhet (Virtual Desktop Infrastructure), vdi, enhetshantering, konfigurera Windows ATP-slutpunkter, konfigurera Microsoft Defender för slutpunktsslutpunkter
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
ms.openlocfilehash: 167db9b5da841528e95f167b3af6a840b6c71eb4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165567"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="35743-104">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="35743-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35743-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="35743-105">**Applies to:**</span></span>
- [<span data-ttu-id="35743-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="35743-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35743-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35743-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="35743-108">VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="35743-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="35743-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="35743-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="35743-110">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="35743-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="35743-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="35743-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="35743-112">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="35743-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="35743-113">Defender för Endpoint har stöd för icke-fortlöpande registrering av VDI-sessioner.</span><span class="sxs-lookup"><span data-stu-id="35743-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="35743-114">Det kan finnas associerade utmaningar vid registrering av VDE:er.</span><span class="sxs-lookup"><span data-stu-id="35743-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="35743-115">Följande är vanliga utmaningar med det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="35743-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="35743-116">Direkt tidig registrering av korta sessioner, som måste introduceras till Defender för Endpoint innan den faktiska etableringen.</span><span class="sxs-lookup"><span data-stu-id="35743-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="35743-117">Enhetsnamnet återanvänds vanligtvis för nya sessioner.</span><span class="sxs-lookup"><span data-stu-id="35743-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="35743-118">VDI-enheter kan visas i Defender för Endpoint-portalen som antingen:</span><span class="sxs-lookup"><span data-stu-id="35743-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="35743-119">Enskild post för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="35743-119">Single entry for each device.</span></span>  
<span data-ttu-id="35743-120">Observera att i det här fallet *måste samma* enhetsnamn konfigureras när sessionen skapas, till exempel med en obevakad svarsfil.</span><span class="sxs-lookup"><span data-stu-id="35743-120">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="35743-121">Flera poster för varje enhet – en för varje session.</span><span class="sxs-lookup"><span data-stu-id="35743-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="35743-122">Följande steg vägleder dig genom introduktionen av VDI-enheter och visar steg för enskilda och flera poster.</span><span class="sxs-lookup"><span data-stu-id="35743-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="35743-123">För miljöer där det finns konfigurationer med låg resurs kan VDI-startproceduren göra att Defender för Slutpunkts sensorbaserad hastighet går långsammare.</span><span class="sxs-lookup"><span data-stu-id="35743-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="35743-124">För Windows 10 eller Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="35743-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="35743-125">Öppna ZIP-filen för VDI-konfigurationspaket *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="35743-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="35743-126">Du kan också hämta paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="35743-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="35743-127">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="35743-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="35743-128">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="35743-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="35743-129">Välj  **VDI-onboardingskript för icke-beständiga slutpunkter i fältet Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="35743-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="35743-130">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="35743-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="35743-131">Kopiera filerna från mappen WindowsDefenderATPOnboardingPackage som extraherats från ZIP-filen `golden/master` till bilden under sökvägen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="35743-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="35743-132">Om du inte implementerar en enda post för varje enhet kopierar du WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="35743-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="35743-133">Om du implementerar en enda post för varje enhet kopierar du både Onboard-NonPersistentMachine.ps1 och WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="35743-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35743-134">Om du inte ser mappen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` kan den vara dold.</span><span class="sxs-lookup"><span data-stu-id="35743-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="35743-135">Du måste välja alternativet Visa **dolda filer och mappar i** Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="35743-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="35743-136">Öppna ett fönster för redigeraren för lokala grupprinciper och gå till **Datorkonfiguration**  >  **Windows-inställningar**  >  **Skriptstart.**  >  </span><span class="sxs-lookup"><span data-stu-id="35743-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="35743-137">Domain Group Policy kan också användas för registrering av icke-beständiga VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="35743-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="35743-138">Beroende på vilken metod du vill implementera följer du lämpliga steg:</span><span class="sxs-lookup"><span data-stu-id="35743-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span> <br>
   <span data-ttu-id="35743-139">**För enskild inmatning för varje enhet:**</span><span class="sxs-lookup"><span data-stu-id="35743-139">**For single entry for each device**:</span></span><br>
   
   <span data-ttu-id="35743-140">Välj fliken **PowerShell-skript och** klicka sedan på Lägg till **(Utforskaren** öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="35743-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="35743-141">Navigera till onboarding PowerShell-skript `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="35743-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="35743-142">**För flera poster för varje enhet:**</span><span class="sxs-lookup"><span data-stu-id="35743-142">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="35743-143">Välj fliken **Skript och** klicka sedan på **Lägg till** (Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="35743-143">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="35743-144">Navigera till bash-skriptet `WindowsDefenderATPOnboardingScript.cmd` onboarding.</span><span class="sxs-lookup"><span data-stu-id="35743-144">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="35743-145">Testa lösningen:</span><span class="sxs-lookup"><span data-stu-id="35743-145">Test your solution:</span></span>

   1. <span data-ttu-id="35743-146">Skapa en pool med en enhet.</span><span class="sxs-lookup"><span data-stu-id="35743-146">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="35743-147">Logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="35743-147">Logon to device.</span></span>
      
   1. <span data-ttu-id="35743-148">Logga ut från enhet.</span><span class="sxs-lookup"><span data-stu-id="35743-148">Logoff from device.</span></span>

   1. <span data-ttu-id="35743-149">Logga in på enhet med en annan användare.</span><span class="sxs-lookup"><span data-stu-id="35743-149">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="35743-150">**För enskild post för varje enhet:** Kontrollera bara en post i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="35743-150">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="35743-151">**Flera poster för varje enhet:** Kontrollera flera poster i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="35743-151">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="35743-152">Klicka **på listan** Enheter i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="35743-152">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="35743-153">Använd sökfunktionen genom att ange enhetens namn och välja **Enhet** som söktyp.</span><span class="sxs-lookup"><span data-stu-id="35743-153">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="35743-154">För nedåtnivå-SKU:er</span><span class="sxs-lookup"><span data-stu-id="35743-154">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="35743-155">Följande register är bara relevanta när syftet är att uppnå en "enskild post för varje enhet".</span><span class="sxs-lookup"><span data-stu-id="35743-155">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="35743-156">Ställ in registervärdet på:</span><span class="sxs-lookup"><span data-stu-id="35743-156">Set registry value to:</span></span>

    ```reg
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="35743-157">eller använda kommandorad:</span><span class="sxs-lookup"><span data-stu-id="35743-157">or using command line:</span></span>

    ```
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="35743-158">Följ [server onboarding-processen](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="35743-158">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="35743-159">Uppdatera icke-beständiga VDI-bilder (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="35743-159">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="35743-160">Vi rekommenderar att du använder offlineserviceverktyg för att korrigera gyllene/huvudbilder.</span><span class="sxs-lookup"><span data-stu-id="35743-160">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="35743-161">Du kan till exempel använda kommandona nedan för att installera en uppdatering medan bilden förblir offline:</span><span class="sxs-lookup"><span data-stu-id="35743-161">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="35743-162">Mer information om DISM-kommandon och offlineunderhåll finns i artiklarna nedan:</span><span class="sxs-lookup"><span data-stu-id="35743-162">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="35743-163">Ändra en Windows-bild med DISM</span><span class="sxs-lookup"><span data-stu-id="35743-163">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="35743-164">DISM Image Management Command-Line Options</span><span class="sxs-lookup"><span data-stu-id="35743-164">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="35743-165">Minska storleken på komponentlagret i en offline-Windows-bild</span><span class="sxs-lookup"><span data-stu-id="35743-165">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="35743-166">Om offlineunderhåll inte är ett möjligt alternativ för din icke-beständiga VDI-miljö bör du vidta följande steg för att säkerställa konsekvens och sensorhälsa:</span><span class="sxs-lookup"><span data-stu-id="35743-166">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="35743-167">När huvudbilden startats för onlineunderhåll eller korrigering kör du ett offboardingskript för att inaktivera Defender för Slutpunkts sensor.</span><span class="sxs-lookup"><span data-stu-id="35743-167">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="35743-168">Mer information finns i [Offboard-enheter som använder ett lokalt skript.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="35743-168">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="35743-169">Kontrollera att sensorn stoppas genom att köra kommandot nedan i ett CMD-fönster:</span><span class="sxs-lookup"><span data-stu-id="35743-169">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="35743-170">Tjänst för bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="35743-170">Service the image as needed.</span></span>

4. <span data-ttu-id="35743-171">Kör kommandona nedan med PsExec.exe (som kan laddas ned från för att rensa innehållet i cybermappen som sensorn kan ha ackumulerat https://download.sysinternals.com/files/PSTools.zip) sedan starten:</span><span class="sxs-lookup"><span data-stu-id="35743-171">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="35743-172">Omsälsa den gyllene bilden/originalbilden som vanligt.</span><span class="sxs-lookup"><span data-stu-id="35743-172">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35743-173">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="35743-173">Related topics</span></span>
- [<span data-ttu-id="35743-174">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="35743-174">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="35743-175">Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="35743-175">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="35743-176">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="35743-176">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="35743-177">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="35743-177">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="35743-178">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35743-178">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
