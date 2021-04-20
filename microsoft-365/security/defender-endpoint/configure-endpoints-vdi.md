---
title: Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)
description: Distribuera konfigurationspaketet på en VDI-enhet (Virtual Desktop Infrastructure) så att de introduceras till Microsoft Defender för slutpunktstjänsten.
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
ms.openlocfilehash: 1e970be7967e221c29017be804a98770a778654f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892799"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="669c8-104">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="669c8-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="669c8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="669c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="669c8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="669c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="669c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="669c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="669c8-108">VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="669c8-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="669c8-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="669c8-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="669c8-110">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="669c8-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="669c8-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="669c8-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="669c8-112">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="669c8-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="669c8-113">Defender för Endpoint har stöd för icke-fortlöpande registrering av VDI-sessioner.</span><span class="sxs-lookup"><span data-stu-id="669c8-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="669c8-114">Det kan finnas associerade utmaningar vid registrering av VDE:er.</span><span class="sxs-lookup"><span data-stu-id="669c8-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="669c8-115">Följande är vanliga utmaningar med det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="669c8-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="669c8-116">Direkt tidig registrering av korta sessioner, som måste introduceras till Defender för Endpoint innan den faktiska etableringen.</span><span class="sxs-lookup"><span data-stu-id="669c8-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="669c8-117">Enhetsnamnet återanvänds vanligtvis för nya sessioner.</span><span class="sxs-lookup"><span data-stu-id="669c8-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="669c8-118">VDI-enheter kan visas i Defender för Endpoint-portalen som antingen:</span><span class="sxs-lookup"><span data-stu-id="669c8-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="669c8-119">Enskild post för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="669c8-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="669c8-120">I det här fallet måste *samma* enhetsnamn konfigureras när sessionen skapas, till exempel med en obevakad svarsfil.</span><span class="sxs-lookup"><span data-stu-id="669c8-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="669c8-121">Flera poster för varje enhet – en för varje session.</span><span class="sxs-lookup"><span data-stu-id="669c8-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="669c8-122">Följande steg vägleder dig genom introduktionen av VDI-enheter och visar steg för enskilda och flera poster.</span><span class="sxs-lookup"><span data-stu-id="669c8-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="669c8-123">För miljöer där det finns konfigurationer med låg resurs kan VDI-startproceduren göra att Defender för Slutpunkts sensorbaserad hastighet går långsammare.</span><span class="sxs-lookup"><span data-stu-id="669c8-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="669c8-124">För Windows 10 eller Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="669c8-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="669c8-125">Öppna ZIP-filen för VDI-konfigurationspaket *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="669c8-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="669c8-126">Du kan också hämta paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="669c8-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="669c8-127">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="669c8-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="669c8-128">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="669c8-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="669c8-129">Välj  **VDI-onboardingskript för icke-beständiga slutpunkter i fältet Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="669c8-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="669c8-130">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="669c8-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="669c8-131">Kopiera filerna från mappen WindowsDefenderATPOnboardingPackage som extraherats från ZIP-filen `golden/master` till bilden under sökvägen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="669c8-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="669c8-132">Om du inte implementerar en enda post för varje enhet kopierar du WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="669c8-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="669c8-133">Om du implementerar en enda post för varje enhet kopierar du både Onboard-NonPersistentMachine.ps1 och WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="669c8-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="669c8-134">Om du inte ser mappen `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` kan den vara dold.</span><span class="sxs-lookup"><span data-stu-id="669c8-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="669c8-135">Du måste välja alternativet Visa **dolda filer och mappar i** Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="669c8-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="669c8-136">Öppna ett fönster för redigeraren för lokala grupprinciper och gå till **Datorkonfiguration**  >  **Windows-inställningar**  >  **Skriptstart.**  >  </span><span class="sxs-lookup"><span data-stu-id="669c8-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="669c8-137">Domain Group Policy kan också användas för registrering av icke-beständiga VDI-enheter.</span><span class="sxs-lookup"><span data-stu-id="669c8-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="669c8-138">Beroende på vilken metod du vill implementera följer du lämpliga steg:</span><span class="sxs-lookup"><span data-stu-id="669c8-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="669c8-139">För enskild inmatning för varje enhet:</span><span class="sxs-lookup"><span data-stu-id="669c8-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="669c8-140">Välj fliken **PowerShell-skript och** klicka sedan på Lägg till **(Utforskaren** öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="669c8-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="669c8-141">Navigera till onboarding PowerShell-skript `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="669c8-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="669c8-142">Du behöver inte ange den andra filen eftersom den utlöses automatiskt.</span><span class="sxs-lookup"><span data-stu-id="669c8-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="669c8-143">För flera poster för varje enhet:</span><span class="sxs-lookup"><span data-stu-id="669c8-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="669c8-144">Välj fliken **Skript och** klicka sedan på **Lägg till** (Utforskaren öppnas direkt i sökvägen där du kopierade onboarding-skriptet tidigare).</span><span class="sxs-lookup"><span data-stu-id="669c8-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="669c8-145">Navigera till bash-skriptet `WindowsDefenderATPOnboardingScript.cmd` onboarding.</span><span class="sxs-lookup"><span data-stu-id="669c8-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="669c8-146">Testa lösningen:</span><span class="sxs-lookup"><span data-stu-id="669c8-146">Test your solution:</span></span>

   1. <span data-ttu-id="669c8-147">Skapa en pool med en enhet.</span><span class="sxs-lookup"><span data-stu-id="669c8-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="669c8-148">Logga in på enheten.</span><span class="sxs-lookup"><span data-stu-id="669c8-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="669c8-149">Logga ut från enhet.</span><span class="sxs-lookup"><span data-stu-id="669c8-149">Logoff from device.</span></span>

   1. <span data-ttu-id="669c8-150">Logga in på enhet med en annan användare.</span><span class="sxs-lookup"><span data-stu-id="669c8-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="669c8-151">Beroende på vilken metod du vill implementera följer du lämpliga steg:</span><span class="sxs-lookup"><span data-stu-id="669c8-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="669c8-152">För enskild inmatning för varje enhet:</span><span class="sxs-lookup"><span data-stu-id="669c8-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="669c8-153">Kontrollera bara en post i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="669c8-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="669c8-154">För flera poster för varje enhet:</span><span class="sxs-lookup"><span data-stu-id="669c8-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="669c8-155">Kontrollera flera poster i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="669c8-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="669c8-156">Klicka **på listan** Enheter i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="669c8-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="669c8-157">Använd sökfunktionen genom att ange enhetens namn och välja **Enhet** som söktyp.</span><span class="sxs-lookup"><span data-stu-id="669c8-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="669c8-158">För nedåtnivå-SKU:er</span><span class="sxs-lookup"><span data-stu-id="669c8-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="669c8-159">Följande register är bara relevanta när syftet är att uppnå en "enskild post för varje enhet".</span><span class="sxs-lookup"><span data-stu-id="669c8-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="669c8-160">Ställ in registervärdet på:</span><span class="sxs-lookup"><span data-stu-id="669c8-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="669c8-161">eller använda kommandorad:</span><span class="sxs-lookup"><span data-stu-id="669c8-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="669c8-162">Följ [server onboarding-processen](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="669c8-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="669c8-163">Uppdatera icke-beständiga VDI-bilder (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="669c8-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="669c8-164">Vi rekommenderar att du använder offlineserviceverktyg för att korrigera gyllene/huvudbilder.</span><span class="sxs-lookup"><span data-stu-id="669c8-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="669c8-165">Du kan till exempel använda kommandona nedan för att installera en uppdatering medan bilden förblir offline:</span><span class="sxs-lookup"><span data-stu-id="669c8-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="669c8-166">Mer information om DISM-kommandon och offlineunderhåll finns i artiklarna nedan:</span><span class="sxs-lookup"><span data-stu-id="669c8-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="669c8-167">Ändra en Windows-bild med DISM</span><span class="sxs-lookup"><span data-stu-id="669c8-167">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="669c8-168">DISM Image Management Command-Line Options</span><span class="sxs-lookup"><span data-stu-id="669c8-168">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="669c8-169">Minska storleken på komponentlagret i en offline-Windows-bild</span><span class="sxs-lookup"><span data-stu-id="669c8-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="669c8-170">Om offlineunderhåll inte är ett möjligt alternativ för din icke-beständiga VDI-miljö bör du vidta följande steg för att säkerställa konsekvens och sensorhälsa:</span><span class="sxs-lookup"><span data-stu-id="669c8-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="669c8-171">När huvudbilden startats för onlineunderhåll eller korrigering kör du ett offboardingskript för att inaktivera Defender för Slutpunkts sensor.</span><span class="sxs-lookup"><span data-stu-id="669c8-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="669c8-172">Mer information finns i [Offboard-enheter som använder ett lokalt skript.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="669c8-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="669c8-173">Kontrollera att sensorn stoppas genom att köra kommandot nedan i ett CMD-fönster:</span><span class="sxs-lookup"><span data-stu-id="669c8-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="669c8-174">Tjänst för bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="669c8-174">Service the image as needed.</span></span>

4. <span data-ttu-id="669c8-175">Kör kommandona nedan med PsExec.exe (som kan laddas ned från för att rensa innehållet i cybermappen som sensorn kan ha ackumulerat https://download.sysinternals.com/files/PSTools.zip) sedan starten:</span><span class="sxs-lookup"><span data-stu-id="669c8-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="669c8-176">Omsälsa den gyllene bilden/originalbilden som vanligt.</span><span class="sxs-lookup"><span data-stu-id="669c8-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="669c8-177">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="669c8-177">Related topics</span></span>
- [<span data-ttu-id="669c8-178">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="669c8-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="669c8-179">Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="669c8-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="669c8-180">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="669c8-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="669c8-181">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="669c8-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="669c8-182">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="669c8-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
