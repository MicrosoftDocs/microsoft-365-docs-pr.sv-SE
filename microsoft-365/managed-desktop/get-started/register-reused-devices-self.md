---
title: Registrera befintliga enheter själv
description: Registrera återanvända enheter du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840521"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="c8fb1-103">Registrera befintliga enheter själv</span><span class="sxs-lookup"><span data-stu-id="c8fb1-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="c8fb1-104">I det här avsnittet beskrivs anvisningar för hur du återanvändar enheter som du redan har och registrerar dem på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c8fb1-105">Om du arbetar med helt nya enheter följer du anvisningarna i [registrera nya enheter på Microsoft Managed Desktop](register-devices-self.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="c8fb1-106">Processen för partners är dokumenterad i [steg för att partners ska kunna registrera enheter](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="c8fb1-107">Microsoft Managed Desktop kan fungera med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (som kräver att du skriver ut dem igen).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="c8fb1-108">Du kan registrera enheter med Microsoft Managed Desktop i Microsoft Endpoint Manager-portalen.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="c8fb1-109">Förbereda att registrera befintliga enheter</span><span class="sxs-lookup"><span data-stu-id="c8fb1-109">Prepare to register existing devices</span></span>


<span data-ttu-id="c8fb1-110">Följ de här stegen för att registrera befintliga enheter:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="c8fb1-111">Skaffa maskinvaru-hashvärdet för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="c8fb1-112">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="c8fb1-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="c8fb1-113">[Registrera enheterna på Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="c8fb1-114">Kontrol lera att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="c8fb1-115">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="c8fb1-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="c8fb1-116">Skaffa maskinvaru-hashvärdet</span><span class="sxs-lookup"><span data-stu-id="c8fb1-116">Obtain the hardware hash</span></span>

<span data-ttu-id="c8fb1-117">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="c8fb1-118">Du har fyra alternativ för att få informationen från enheter som du redan använder:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="c8fb1-119">Be din OEM-leverantör om den autopilot registrerings filen som kommer att innehålla maskinvaru-hashar.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="c8fb1-120">Samla in information i [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="c8fb1-121">Kör ett Windows PowerShell-skript – antingen via [Active Directory](#active-directory-powershell-script-method) eller [manuellt](#manual-powershell-script-method) på varje enhet – och samla in resultatet i en fil.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="c8fb1-122">Starta varje enhet, men Slutför inte installations upplevelsen för Windows--och [samla in hash-värden på ett löstagbart minne](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="c8fb1-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c8fb1-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="c8fb1-124">Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvaru-hashar från befintliga enheter som du vill registrera med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8fb1-125">Alla enheter som ska få den här informationen för måste ha Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="c8fb1-126">Om du har uppfyllt alla dessa krav kan du börja samla in informationen genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="c8fb1-127">I Configuration Manager-konsolen väljer du **övervakning**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="c8fb1-128">Expandera noden **rapportering** i arbets ytan övervakning, expandera **rapporter** och välj **maskin varan-General-** noden.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="c8fb1-129">Kör informationen i rapporten, **Windows autopilot-enhet** och visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="c8fb1-130">I rapport visnings programmet väljer du ikonen **Exportera** och väljer alternativet **CSV (kommaavgränsad)** .</span><span class="sxs-lookup"><span data-stu-id="c8fb1-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="c8fb1-131">När du har sparat filen måste du filtrera resultaten till de enheter som du planerar att registrera med Microsoft Managed Desktop och överföra data till Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="c8fb1-132">Öppna Microsoft slut punkts hanteraren och gå till menyn **enheter** och leta efter Microsoft Managed Desktop och välj **enheter**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="c8fb1-133">Välj **+ registrera enheter**, som öppnar ett flyg-i för att registrera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="c8fb1-134">Mer information finns i [registrera enheter med hjälp av administrations portalen](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="c8fb1-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="c8fb1-135">PowerShell-skriptfil för Active Directory</span><span class="sxs-lookup"><span data-stu-id="c8fb1-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="c8fb1-136">I en Active Directory-miljö kan du använda `Get-WindowsAutoPilotInfo` PowerShell-cmdleten för att fjärrsamla in informationen från enheter i Active Directory-grupper med WinRM.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="c8fb1-137">Du kan också använda `Get-AD Computer` cmdleten och få filtrerade resultat för ett visst maskin varu modell namn som ingår i katalogen.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="c8fb1-138">Innan du fortsätter måste du först bekräfta dessa förutsättningar och sedan gå vidare med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="c8fb1-139">WinRM är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-139">WinRM is enabled.</span></span>
- <span data-ttu-id="c8fb1-140">De enheter som du vill registrera är aktiva i nätverket (det vill säga att de inte kopplas bort eller inaktive RAS).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="c8fb1-141">Kontrol lera att du har en parameter för inloggnings uppgifter som har behörighet att köra på enheterna.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="c8fb1-142">Kontrol lera att Windows-brandväggen tillåter åtkomst till WMI.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="c8fb1-143">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="c8fb1-144">Öppna kontroll panelen i **Windows Defender-brandväggen** och välj **Tillåt en app eller funktion via Windows Defender-brandväggen**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="c8fb1-145">Sök efter **WMI (Windows Management Instrumentation)** i listan, aktivera både **privat och offentlig** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="c8fb1-146">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="c8fb1-147">Kör *något* av följande skript:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="c8fb1-148">Åtkomst till alla kataloger där det finns poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="c8fb1-149">Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="c8fb1-150">Observera att det kan ta några timmar att ta bort alla.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="c8fb1-151">Access Management Services där det finns poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="c8fb1-152">Ta bort poster för varje enhet från *alla* hanterings tjänster, inklusive Microsoft Endpoint Configuration Manager, Microsoft Intune och Windows autopilot.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="c8fb1-153">Observera att det kan ta några timmar att ta bort alla.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="c8fb1-154">Nu kan du fortsätta med att [registrera enheter](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="c8fb1-155">Metod för manuell PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="c8fb1-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="c8fb1-156">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c8fb1-157">Använda `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="c8fb1-158">Använda `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="c8fb1-159">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="c8fb1-160">Flash-enhet, metod</span><span class="sxs-lookup"><span data-stu-id="c8fb1-160">Flash drive method</span></span>

1. <span data-ttu-id="c8fb1-161">På en annan enhet än den du registrerar kan du sätta in en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="c8fb1-162">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="c8fb1-163">Använda `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="c8fb1-164">Slå på den enhet du registrerar, men *Starta inte installations upplevelsen*.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="c8fb1-165">Om du råkar starta installations upplevelsen måste du återställa eller återanvända enheten.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="c8fb1-166">Sätt in USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="c8fb1-167">Öppna en PowerShell-kommandotolk med administrativa rättigheter och kör den sedan `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="c8fb1-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="c8fb1-168">Använda `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="c8fb1-169">Använda `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="c8fb1-170">Ta bort USB-enheten och stäng sedan av enheten genom att köra `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="c8fb1-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="c8fb1-171">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="c8fb1-172">Koppla inte på den enhet du registrerar igen förrän du har registrerat dig.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="c8fb1-173">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="c8fb1-173">Merge hash data</span></span>

<span data-ttu-id="c8fb1-174">Om du har samlat in maskinvaru-hash-data med de manuella PowerShell-eller Flash-enhets metoderna måste du nu använda data i CSV-filerna i en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="c8fb1-175">Här följer ett exempel på PowerShell-skript som gör det enkelt:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="c8fb1-176">Med hash-data som kopplats till en CSV-fil kan du fortsätta att [Registrera enheterna](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="c8fb1-177">Registrera enheter med hjälp av administrations portalen</span><span class="sxs-lookup"><span data-stu-id="c8fb1-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="c8fb1-178">I [Microsoft slut punkts hanteraren](https://endpoint.microsoft.com/)väljer du **enheter** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="c8fb1-179">Leta efter avsnittet Microsoft Managed Desktop på menyn och välj **enheter**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="c8fb1-180">I arbets ytan Microsoft Managed Station ära datorer väljer du **+ registrera enheter**, som öppnar ett flyg program för att registrera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="c8fb1-181">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-181">Follow these steps:</span></span>

1. <span data-ttu-id="c8fb1-182">Ange en sökväg till CSV-filen som du skapade tidigare i **fil överföring**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="c8fb1-183">Välj **registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-183">Select **Register devices**.</span></span> <span data-ttu-id="c8fb1-184">Systemet lägger till enheter i listan med enheter i **bladet enheter**, markerade som **registrering väntar**.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="c8fb1-185">Registreringen tar vanligt vis mindre än 10 minuter och när enheten lyckas visas den som **klar för användarna** , vilket betyder att det är klart och väntar på att en användare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="c8fb1-186">Du kan övervaka förloppet av enhets registrering på huvud sidan.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="c8fb1-187">Möjliga tillstånd rapporterade att inkludera:</span><span class="sxs-lookup"><span data-stu-id="c8fb1-187">Possible states reported there include:</span></span>

| <span data-ttu-id="c8fb1-188">Sessionsläget</span><span class="sxs-lookup"><span data-stu-id="c8fb1-188">State</span></span> | <span data-ttu-id="c8fb1-189">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8fb1-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="c8fb1-190">Registrering väntar</span><span class="sxs-lookup"><span data-stu-id="c8fb1-190">Registration Pending</span></span> | <span data-ttu-id="c8fb1-191">Registreringen är inte klar ännu.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-191">Registration is not done yet.</span></span> <span data-ttu-id="c8fb1-192">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-192">Check back later.</span></span> |
| <span data-ttu-id="c8fb1-193">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="c8fb1-193">Registration failed</span></span> | <span data-ttu-id="c8fb1-194">Det gick inte att genomföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-194">Registration could not be completed.</span></span> <span data-ttu-id="c8fb1-195">Mer information finns i [fel sökning av enhets registrering](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="c8fb1-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="c8fb1-196">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="c8fb1-196">Ready for user</span></span> | <span data-ttu-id="c8fb1-197">Registreringen lyckades och enheten är nu klar att levereras till användaren.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="c8fb1-198">Microsoft Managed Desktop vägleder dem genom den första konfigurationen, så du behöver inte göra några fler förberedelser.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="c8fb1-199">Aktiva</span><span class="sxs-lookup"><span data-stu-id="c8fb1-199">Active</span></span> | <span data-ttu-id="c8fb1-200">Enheten har levererats till användaren och har registrerats hos din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="c8fb1-201">Detta indikerar också att de ofta använder enheten.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="c8fb1-202">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="c8fb1-202">Inactive</span></span> | <span data-ttu-id="c8fb1-203">Enheten har levererats till användaren och har registrerats hos din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="c8fb1-204">De har emellertid inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="c8fb1-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="c8fb1-205">Felsöka registrering av enheter</span><span class="sxs-lookup"><span data-stu-id="c8fb1-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="c8fb1-206">Fel meddelande</span><span class="sxs-lookup"><span data-stu-id="c8fb1-206">Error message</span></span> | <span data-ttu-id="c8fb1-207">Information</span><span class="sxs-lookup"><span data-stu-id="c8fb1-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="c8fb1-208">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="c8fb1-208">Device not found</span></span> | <span data-ttu-id="c8fb1-209">Det gick inte att registrera den här enheten eftersom vi inte kunde hitta en träff för den medföljande tillverkaren, modellen eller serie numret.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="c8fb1-210">Bekräfta dessa värden med din enhets leverantör.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="c8fb1-211">Maskinvaru-hashvärdet är inte giltigt</span><span class="sxs-lookup"><span data-stu-id="c8fb1-211">Hardware hash not valid</span></span> | <span data-ttu-id="c8fb1-212">Den maskinvaru-hash som du har angett för enheten är inte korrekt formaterad.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="c8fb1-213">Dubbel kontrol lera maskinvaru-hashvärdet och skicka sedan igen.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="c8fb1-214">Enheten är redan registrerad</span><span class="sxs-lookup"><span data-stu-id="c8fb1-214">Device already registered</span></span> | <span data-ttu-id="c8fb1-215">Enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-215">This device is already registered to your organization.</span></span> <span data-ttu-id="c8fb1-216">Ingen ytterligare åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-216">No further action required.</span></span> |
| <span data-ttu-id="c8fb1-217">Enhet som ägs av en annan organisation</span><span class="sxs-lookup"><span data-stu-id="c8fb1-217">Device claimed by another organization</span></span> | <span data-ttu-id="c8fb1-218">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="c8fb1-219">Hör med din enhets leverantör.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="c8fb1-220">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="c8fb1-220">Unexpected error</span></span> | <span data-ttu-id="c8fb1-221">Begäran kunde inte behandlas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="c8fb1-222">Kontakta supporten och ange begäran-ID: <requestId></span><span class="sxs-lookup"><span data-stu-id="c8fb1-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="c8fb1-223">Kontrol lera bilden</span><span class="sxs-lookup"><span data-stu-id="c8fb1-223">Check the image</span></span>

<span data-ttu-id="c8fb1-224">Om din enhet kommer från en Microsoft Managed Desktop partner-leverantör ska bilden vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="c8fb1-225">Du är också välkommen att lägga till din egen image om du vill.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="c8fb1-226">För att komma igång kontaktar du den Microsoft-representant du arbetar med och ger dig en plats och anvisningar för hur du kan använda bilden.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="c8fb1-227">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="c8fb1-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8fb1-228">Innan du lämnar in enheten till din användare bör du kontrol lera att du har skaffat [rätt licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="c8fb1-229">Om alla licenser tillämpas kan du [få användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå igenom installations upplevelsen i Windows.</span><span class="sxs-lookup"><span data-stu-id="c8fb1-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









