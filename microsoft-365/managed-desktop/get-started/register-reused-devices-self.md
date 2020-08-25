---
title: Registrera befintliga enheter själv
description: Registrera åter användnings bara enheter du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9ff0e76448df183ac5c34c5832155e0b135d313
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46869001"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="6a6c8-103">Registrera befintliga enheter själv</span><span class="sxs-lookup"><span data-stu-id="6a6c8-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="6a6c8-104">I det här avsnittet beskrivs vad du kan göra för att återanvända enheter som du redan har och registrera dem på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="6a6c8-105">Om du arbetar med helt nya enheter följer du anvisningarna i [registrera nya enheter på Microsoft Managed Desktop](register-devices-self.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="6a6c8-106">Processen för partners är dokumenterad i [steg för att partners ska kunna registrera enheter](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="6a6c8-107">Microsoft Managed Desktop kan fungera med helt nya enheter eller kan du återanvända enheter som du kanske redan har (som kräver att du skriver ut dem igen).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="6a6c8-108">Du kan registrera enheter på Microsoft Managed Desktop admin-portalen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="6a6c8-109">Förbereda att registrera befintliga enheter</span><span class="sxs-lookup"><span data-stu-id="6a6c8-109">Prepare to register existing devices</span></span>


<span data-ttu-id="6a6c8-110">Följ de här stegen för att registrera befintliga enheter:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="6a6c8-111">Skaffa maskinvaru-hashvärdet för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="6a6c8-112">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="6a6c8-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="6a6c8-113">[Registrera enheterna på Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="6a6c8-114">Kontrol lera att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="6a6c8-115">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="6a6c8-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="6a6c8-116">Skaffa maskinvaru-hashvärdet</span><span class="sxs-lookup"><span data-stu-id="6a6c8-116">Obtain the hardware hash</span></span>

<span data-ttu-id="6a6c8-117">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="6a6c8-118">Du har fyra alternativ för att få informationen från enheter som du redan använder:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="6a6c8-119">Be din OEM-leverantör om den autopilot registrerings filen som kommer att innehålla maskinvaru-hashar.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="6a6c8-120">Samla in information i [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="6a6c8-121">Kör ett Windows PowerShell-skript – antingen via [Active Directory](#active-directory-powershell-script-method) eller [manuellt](#manual-powershell-script-method) på varje enhet – och samla in resultatet i en fil.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="6a6c8-122">Starta varje enhet, men Slutför inte installations upplevelsen för Windows--och [samla in hash-värden på ett löstagbart minne](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="6a6c8-123">Microsoft konfigurationshanterare för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6a6c8-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="6a6c8-124">Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvaru-hashar från befintliga enheter som du vill registrera med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a6c8-125">Alla enheter som ska få den här informationen för måste ha Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="6a6c8-126">Om du har uppfyllt alla dessa krav kan du börja samla in informationen genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="6a6c8-127">I Configuration Manager-konsolen väljer du **övervakning**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="6a6c8-128">Expandera noden **rapportering** i arbets ytan övervakning, expandera **rapporter**och välj **maskin varan-General-** noden.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="6a6c8-129">Kör informationen i rapporten, **Windows autopilot-enhet**och visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="6a6c8-130">I rapport visnings programmet väljer du ikonen **Exportera** och väljer alternativet **CSV (kommaavgränsad)** .</span><span class="sxs-lookup"><span data-stu-id="6a6c8-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="6a6c8-131">När du har sparat filen måste du filtrera resultat efter de enheter som du planerar att registrera med Microsoft Managed Desktop och överföra data till [administrations portalen](https://aka.ms/mmdportal)för Microsoft Managed Desktop, välja **enheter** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="6a6c8-132">Välj **+ registrera enheter**; infarten öppnas:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="6a6c8-133">Mer information finns i [registrera enheter med hjälp av administrations portalen](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="6a6c8-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="6a6c8-134">PowerShell-skriptfil för Active Directory</span><span class="sxs-lookup"><span data-stu-id="6a6c8-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="6a6c8-135">I en Active Directory-miljö kan du använda `Get-WindowsAutoPilotInfo` PowerShell-cmdleten för att fjärrsamla in informationen från enheter i Active Directory-grupper med WinRM.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="6a6c8-136">Du kan också använda `Get-AD Computer` cmdleten och få filtrerade resultat för vissa maskin varu modell namn som finns i katalogen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="6a6c8-137">För att göra detta måste du först bekräfta dessa krav och sedan gå vidare med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="6a6c8-138">WinRM är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-138">WinRM is enabled.</span></span>
- <span data-ttu-id="6a6c8-139">De enheter som du vill registrera är aktiva i nätverket (det vill säga att de inte kopplas bort eller inaktive RAS).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="6a6c8-140">Kontrol lera att du har en parameter för inloggnings uppgifter som har behörighet att köra på enheterna.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="6a6c8-141">Kontrol lera att Windows-brandväggen tillåter åtkomst till WMI.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="6a6c8-142">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="6a6c8-143">Öppna kontroll panelen i **Windows Defender-brandväggen** och välj **Tillåt en app eller funktion via Windows Defender-brandväggen**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="6a6c8-144">Sök efter **WMI (Windows Management Instrumentation)** i listan, aktivera både **privat och offentlig**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="6a6c8-145">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="6a6c8-146">Kör *något* av följande skript:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="6a6c8-147">Åtkomst till alla kataloger där det finns poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="6a6c8-148">Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="6a6c8-149">Tänk på att borttagningen kan ta några timmar innan du slutför processen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="6a6c8-150">Access Management Services där det finns poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="6a6c8-151">Ta bort poster för varje enhet från *alla* hanterings tjänster, inklusive Microsoft Endpoint Configuration Manager, Microsoft Intune och Windows autopilot.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="6a6c8-152">Tänk på att borttagningen kan ta några timmar innan du slutför processen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="6a6c8-153">Nu kan du fortsätta med att [registrera enheter](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="6a6c8-154">Metod för manuell PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="6a6c8-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="6a6c8-155">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="6a6c8-156">Använda `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="6a6c8-157">Använda `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="6a6c8-158">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="6a6c8-159">Flash-enhet, metod</span><span class="sxs-lookup"><span data-stu-id="6a6c8-159">Flash drive method</span></span>

1. <span data-ttu-id="6a6c8-160">På en annan enhet än den du registrerar kan du sätta in en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="6a6c8-161">Öppna en PowerShell-kommandotolk med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="6a6c8-162">Använda `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="6a6c8-163">Slå på den enhet du registrerar, men *Starta inte installations upplevelsen*.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="6a6c8-164">Om du råkar starta installations upplevelsen måste du återställa eller återanvända enheten.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="6a6c8-165">Sätt in USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="6a6c8-166">Öppna en PowerShell-kommandotolk med administrativa rättigheter och kör den sedan `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="6a6c8-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="6a6c8-167">Använda `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="6a6c8-168">Använda `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="6a6c8-169">Ta bort USB-enheten och stäng sedan av enheten genom att köra `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="6a6c8-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="6a6c8-170">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="6a6c8-171">Koppla inte på den enhet du registrerar igen förrän du har registrerat dig.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="6a6c8-172">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="6a6c8-172">Merge hash data</span></span>

<span data-ttu-id="6a6c8-173">Om du har samlat in maskinvaru-hash-data med de manuella PowerShell-eller Flash-enhets metoderna måste du nu använda data i CSV-filerna i en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="6a6c8-174">Här är ett exempel på PowerShell-skript som gör det enkelt:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="6a6c8-175">Med hash-data som kopplats till en CSV-fil kan du fortsätta att [Registrera enheterna](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="6a6c8-176">Registrera enheter med hjälp av administrations portalen</span><span class="sxs-lookup"><span data-stu-id="6a6c8-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="6a6c8-177">Välj **enheter** i det vänstra navigerings fönstret på portalen Microsoft Managed Desktop [admin](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="6a6c8-178">Välj **+ registrera enheter**; infarten öppnas:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="6a6c8-179">[![Flyg in när du har valt registrera enheter, visar enheter med kolumner för tilldelade användare, serie nummer, status, senaste datum och ålder](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="6a6c8-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="6a6c8-180">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-180">Follow these steps:</span></span>

1. <span data-ttu-id="6a6c8-181">Ange en sökväg till CSV-filen som du skapade tidigare i **fil överföring**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="6a6c8-182">Välj **registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-182">Select **Register devices**.</span></span> <span data-ttu-id="6a6c8-183">Systemet lägger till enheter i listan med enheter i **bladet enheter**, markerade som **AutopilotRegistrationRequested**.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="6a6c8-184">Registreringen tar vanligt vis mindre än 10 minuter och när enheten lyckas visas den som **klar för användarna** , vilket betyder att det är klart och väntar på att en användare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="6a6c8-185">Du kan övervaka förloppet av enhets registreringen på huvud sidan för **hanterade skriv bord i Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="6a6c8-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="6a6c8-186">Möjliga tillstånd rapporterade att inkludera:</span><span class="sxs-lookup"><span data-stu-id="6a6c8-186">Possible states reported there include:</span></span>

| <span data-ttu-id="6a6c8-187">Sessionsläget</span><span class="sxs-lookup"><span data-stu-id="6a6c8-187">State</span></span> | <span data-ttu-id="6a6c8-188">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6a6c8-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="6a6c8-189">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="6a6c8-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="6a6c8-190">Registreringen är inte klar ännu.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-190">Registration is not done yet.</span></span> <span data-ttu-id="6a6c8-191">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-191">Check back later.</span></span> |
| <span data-ttu-id="6a6c8-192">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="6a6c8-192">Registration failed</span></span> | <span data-ttu-id="6a6c8-193">Det gick inte att genomföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-193">Registration could not be completed.</span></span> <span data-ttu-id="6a6c8-194">Mer information finns i [fel sökning av enhets registrering](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="6a6c8-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="6a6c8-195">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="6a6c8-195">Ready for user</span></span> | <span data-ttu-id="6a6c8-196">Registreringen lyckades och enheten är nu klar att levereras till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-196">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="6a6c8-197">Microsoft Managed Desktop vägleder dem genom första gången, vilket innebär att du inte behöver göra några fler förberedelser.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="6a6c8-198">Aktiva</span><span class="sxs-lookup"><span data-stu-id="6a6c8-198">Active</span></span> | <span data-ttu-id="6a6c8-199">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-199">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="6a6c8-200">Detta indikerar också att de ofta använder enheten.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="6a6c8-201">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="6a6c8-201">Inactive</span></span> | <span data-ttu-id="6a6c8-202">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-202">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="6a6c8-203">De har emellertid inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="6a6c8-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="6a6c8-204">Felsöka registrering av enheter</span><span class="sxs-lookup"><span data-stu-id="6a6c8-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="6a6c8-205">Fel meddelande</span><span class="sxs-lookup"><span data-stu-id="6a6c8-205">Error message</span></span> | <span data-ttu-id="6a6c8-206">Information</span><span class="sxs-lookup"><span data-stu-id="6a6c8-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="6a6c8-207">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="6a6c8-207">Device not found</span></span> | <span data-ttu-id="6a6c8-208">Det gick inte att registrera den här enheten eftersom vi inte kunde hitta en träff för den medföljande tillverkaren, modellen eller serie numret.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="6a6c8-209">Bekräfta dessa värden med din enhets leverantör.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="6a6c8-210">Maskinvaru-hashvärdet är inte giltigt</span><span class="sxs-lookup"><span data-stu-id="6a6c8-210">Hardware hash not valid</span></span> | <span data-ttu-id="6a6c8-211">Den maskinvaru-hash som du har angett för enheten är inte korrekt formaterad.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="6a6c8-212">Dubbel kontrol lera maskinvaru-hashvärdet och skicka sedan igen.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="6a6c8-213">Enheten är redan registrerad</span><span class="sxs-lookup"><span data-stu-id="6a6c8-213">Device already registered</span></span> | <span data-ttu-id="6a6c8-214">Enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-214">This device is already registered to your organization.</span></span> <span data-ttu-id="6a6c8-215">Ingen ytterligare åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-215">No further action required.</span></span> |
| <span data-ttu-id="6a6c8-216">Enhet som ägs av en annan organisation</span><span class="sxs-lookup"><span data-stu-id="6a6c8-216">Device claimed by another organization</span></span> | <span data-ttu-id="6a6c8-217">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="6a6c8-218">Hör med din enhets leverantör.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="6a6c8-219">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="6a6c8-219">Unexpected error</span></span> | <span data-ttu-id="6a6c8-220">Begäran kunde inte behandlas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="6a6c8-221">Kontakta supporten och ange begäran-ID: <requestId></span><span class="sxs-lookup"><span data-stu-id="6a6c8-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="6a6c8-222">Kontrol lera bilden</span><span class="sxs-lookup"><span data-stu-id="6a6c8-222">Check the image</span></span>

<span data-ttu-id="6a6c8-223">Om din enhet kommer från en Microsoft Managed Desktop partner-leverantör ska bilden vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="6a6c8-224">Du är också välkommen att lägga till din egen image om du vill.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="6a6c8-225">För att komma igång kontaktar du den Microsoft-representant du arbetar med och ger dig en plats och anvisningar för hur du kan använda bilden.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="6a6c8-226">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="6a6c8-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a6c8-227">Innan du lämnar in enheten till din användare bör du kontrol lera att du har skaffat [rätt licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="6a6c8-228">Om alla licenser tillämpas kan du [få användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå igenom installations upplevelsen i Windows.</span><span class="sxs-lookup"><span data-stu-id="6a6c8-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









