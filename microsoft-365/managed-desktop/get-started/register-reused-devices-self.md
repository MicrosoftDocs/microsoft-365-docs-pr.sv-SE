---
title: Registrera befintliga enheter själv
description: Registrera återanvändda enheter du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445572"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="dcda6-104">Registrera befintliga enheter själv</span><span class="sxs-lookup"><span data-stu-id="dcda6-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="dcda6-105">I det här avsnittet beskrivs hur du återanvänder enheter du redan har och registrerar dem i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dcda6-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="dcda6-106">Om du arbetar med helt nya enheter följer du instruktionerna i Registrera [nya enheter i Microsoft Managed Desktop själv i](register-devices-self.md) stället.</span><span class="sxs-lookup"><span data-stu-id="dcda6-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="dcda6-107">Processen för partner beskrivs i Steg [för partner för att registrera enheter.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="dcda6-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="dcda6-108">Microsoft Managed Desktop kan arbeta med helt nya enheter eller återanvända enheter som du kanske redan har (vilket innebär att du måste animera dem igen).</span><span class="sxs-lookup"><span data-stu-id="dcda6-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="dcda6-109">Du kan registrera enheter med Microsoft Managed Desktop i Microsoft Endpoint Manager-portalen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="dcda6-110">Förbered dig för att registrera befintliga enheter</span><span class="sxs-lookup"><span data-stu-id="dcda6-110">Prepare to register existing devices</span></span>


<span data-ttu-id="dcda6-111">Så här registrerar du befintliga enheter:</span><span class="sxs-lookup"><span data-stu-id="dcda6-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="dcda6-112">Hämta maskinvaruhash för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="dcda6-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="dcda6-113">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="dcda6-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="dcda6-114">[Registrera enheterna i Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dcda6-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="dcda6-115">Kontrollera att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="dcda6-116">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="dcda6-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="dcda6-117">Hämta maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="dcda6-117">Obtain the hardware hash</span></span>

<span data-ttu-id="dcda6-118">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash.</span><span class="sxs-lookup"><span data-stu-id="dcda6-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="dcda6-119">Du har fyra alternativ för att hämta den här informationen från enheter som du redan använder:</span><span class="sxs-lookup"><span data-stu-id="dcda6-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="dcda6-120">Be din OEM-leverantör om AutoPilot-registreringsfilen, som innehåller maskinvaru-hashfilerna.</span><span class="sxs-lookup"><span data-stu-id="dcda6-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="dcda6-121">Samla in information i [Konfigurationshanteraren för Microsoft Endpoint](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="dcda6-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="dcda6-122">Kör ett Windows PowerShell-skript – antingen med hjälp av [Active Directory](#active-directory-powershell-script-method) eller manuellt på varje enhet – och samla in resultaten i en fil. [](#manual-powershell-script-method)</span><span class="sxs-lookup"><span data-stu-id="dcda6-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="dcda6-123">Starta varje enhet– men slutför inte Windows-installationen – och samla in hashtaggarna på ett [flyttbart flash-minne.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="dcda6-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dcda6-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dcda6-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="dcda6-125">Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvarushashar från befintliga enheter som du vill registrera i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dcda6-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcda6-126">Alla enheter som du vill få den här informationen till måste köra Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="dcda6-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="dcda6-127">Om du har uppfyllt alla krav är du redo att samla in informationen genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="dcda6-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="dcda6-128">Välj Övervakning i konfigurationshanterarens **konsol.**</span><span class="sxs-lookup"><span data-stu-id="dcda6-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="dcda6-129">På arbetsytan Övervakning expanderar du **noden Rapportering,** **expanderar Rapporter** och väljer **noden Maskinvara –** Allmänt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="dcda6-130">Kör rapporten Windows **Autopilot-enhetsinformation** och visa resultatet.</span><span class="sxs-lookup"><span data-stu-id="dcda6-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="dcda6-131">I rapportvisaren väljer du **ikonen Exportera** och sedan **CSV-alternativet (kommaavgränsad).**</span><span class="sxs-lookup"><span data-stu-id="dcda6-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="dcda6-132">När du har sparat filen måste du filtrera resultaten till bara de enheter som du planerar att registrera dig på Microsoft Managed Desktop och ladda upp data till Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dcda6-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="dcda6-133">Öppna Microsoft Endpoint Manager och gå till menyn **Enheter,** leta sedan efter avsnittet Microsoft Managed Desktop och välj **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="dcda6-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="dcda6-134">Välj **+ Registrera enheter** så öppnas en flygblads för att registrera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="dcda6-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="dcda6-135">Mer information [finns i Registrera enheter med hjälp av](#register-devices-by-using-the-admin-portal) administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="dcda6-136">PowerShell-skriptmetod för Active Directory</span><span class="sxs-lookup"><span data-stu-id="dcda6-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="dcda6-137">I en Active Directory-miljö kan du använda PowerShell-cmdleten för att fjärr samla in information från enheter i `Get-WindowsAutoPilotInfo` Active Directory-grupper med hjälp av WinRM.</span><span class="sxs-lookup"><span data-stu-id="dcda6-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="dcda6-138">Du kan också använda `Get-AD Computer` cmdleten och få filtrerade resultat för ett specifikt namn på maskinvarumodellen som ingår i katalogen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="dcda6-139">Innan du fortsätter bekräftar du först dessa krav och fortsätter sedan med stegen:</span><span class="sxs-lookup"><span data-stu-id="dcda6-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="dcda6-140">WinRM är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="dcda6-140">WinRM is enabled.</span></span>
- <span data-ttu-id="dcda6-141">De enheter du vill registrera är aktiva i nätverket (det vill säga att de inte är frånkopplade eller inaktiverade).</span><span class="sxs-lookup"><span data-stu-id="dcda6-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="dcda6-142">Kontrollera att du har en parameter för domänbehörigheter för autentiseringsuppgifter som kan köras via fjärrstyrning på enheterna.</span><span class="sxs-lookup"><span data-stu-id="dcda6-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="dcda6-143">Kontrollera att Windows-brandväggen tillåter åtkomst till WMI.</span><span class="sxs-lookup"><span data-stu-id="dcda6-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="dcda6-144">Det gör du genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="dcda6-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="dcda6-145">Öppna Kontrollpanelen **för Windows Defender-brandväggen** och välj **Tillåt en app eller funktion i Windows Defender-brandväggen.**</span><span class="sxs-lookup"><span data-stu-id="dcda6-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="dcda6-146">Leta **reda på Windows Management Instrumentation (WMI)** i listan, aktivera både privat och **offentlig** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="dcda6-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="dcda6-147">Öppna en PowerShell-fråga med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="dcda6-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="dcda6-148">Kör *något av* följande skript:</span><span class="sxs-lookup"><span data-stu-id="dcda6-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="dcda6-149">Öppna alla kataloger där det kan finnas poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="dcda6-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="dcda6-150">Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dcda6-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="dcda6-151">Observera att borttagningen kan ta några timmar att bearbeta helt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="dcda6-152">Åtkomsthanteringstjänster där det kan finnas poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="dcda6-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="dcda6-153">Ta bort poster för varje enhet från *alla* hanteringstjänster, inklusive Konfigurationshanteraren för Microsoft Slutpunkt, Microsoft Intune och Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="dcda6-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="dcda6-154">Observera att borttagningen kan ta några timmar att bearbeta helt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="dcda6-155">Nu kan du fortsätta att [registrera enheter](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dcda6-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="dcda6-156">Manuell PowerShell-skriptmetod</span><span class="sxs-lookup"><span data-stu-id="dcda6-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="dcda6-157">Öppna en PowerShell-fråga med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="dcda6-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="dcda6-158">Kör `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="dcda6-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="dcda6-159">Kör `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dcda6-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="dcda6-160">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="dcda6-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="dcda6-161">Flash-enhetsmetod</span><span class="sxs-lookup"><span data-stu-id="dcda6-161">Flash drive method</span></span>

1. <span data-ttu-id="dcda6-162">Sätt i en USB-enhet på en annan enhet än den som du registrerar.</span><span class="sxs-lookup"><span data-stu-id="dcda6-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="dcda6-163">Öppna en PowerShell-fråga med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="dcda6-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="dcda6-164">Kör `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="dcda6-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="dcda6-165">Slå på enheten som du registrerar, *men starta inte konfigurationen.*</span><span class="sxs-lookup"><span data-stu-id="dcda6-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="dcda6-166">Om du startar konfigurationen av misstag måste du återställa eller animera enheten.</span><span class="sxs-lookup"><span data-stu-id="dcda6-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="dcda6-167">Sätt i USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="dcda6-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="dcda6-168">Öppna en PowerShell-fråga med administrativa rättigheter och kör sedan `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="dcda6-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="dcda6-169">Kör `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="dcda6-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="dcda6-170">Kör `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dcda6-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="dcda6-171">Ta bort USB-enheten och stäng sedan av enheten genom att köra `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="dcda6-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="dcda6-172">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="dcda6-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="dcda6-173">Ström inte på enheten som du registrerar igen förrän du har slutfört registreringen för den.</span><span class="sxs-lookup"><span data-stu-id="dcda6-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="dcda6-174">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="dcda6-174">Merge hash data</span></span>

<span data-ttu-id="dcda6-175">Om du har samlat in maskinvaruhashdata med de manuella PowerShell- eller flash-metoderna måste du nu ha data i CSV-filerna kombinerade i en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="dcda6-176">Här är ett PowerShell-exempelskript som gör det enkelt:</span><span class="sxs-lookup"><span data-stu-id="dcda6-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="dcda6-177">Med hash-data kopplade till en CSV-fil kan du nu fortsätta att [registrera enheterna](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dcda6-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="dcda6-178">Registrera enheter med hjälp av administrationsportalen</span><span class="sxs-lookup"><span data-stu-id="dcda6-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="dcda6-179">I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)väljer du **Enheter** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dcda6-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="dcda6-180">Titta efter avsnittet Microsoft Managed Desktop på menyn och välj **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="dcda6-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="dcda6-181">På arbetsytan Microsoft Hanterade skrivbordsenheter väljer du **+ Registrera-enheter,** som gör att du kan registrera nya enheter.</span><span class="sxs-lookup"><span data-stu-id="dcda6-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="dcda6-182">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="dcda6-182">Follow these steps:</span></span>

1. <span data-ttu-id="dcda6-183">Ange **en sökväg** till CSV-filen du skapade tidigare i Filuppladdning.</span><span class="sxs-lookup"><span data-stu-id="dcda6-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="dcda6-184">Välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="dcda6-184">Select **Register devices**.</span></span> <span data-ttu-id="dcda6-185">Systemet lägger till enheterna i din lista med enheter i bladet **Enheter**, markerade som **Väntar på registrering.**</span><span class="sxs-lookup"><span data-stu-id="dcda6-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="dcda6-186">Registrering tar vanligtvis mindre än 10 minuter och  när enheten lyckas visas den som Redo för användare. Det innebär att den är redo att börja använda och väntar på att användaren ska börja använda den.</span><span class="sxs-lookup"><span data-stu-id="dcda6-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="dcda6-187">Du kan övervaka förloppet för enhetsregistreringen på huvudsidan.</span><span class="sxs-lookup"><span data-stu-id="dcda6-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="dcda6-188">Möjliga delstater som rapporterats där är:</span><span class="sxs-lookup"><span data-stu-id="dcda6-188">Possible states reported there include:</span></span>

| <span data-ttu-id="dcda6-189">Delstat</span><span class="sxs-lookup"><span data-stu-id="dcda6-189">State</span></span> | <span data-ttu-id="dcda6-190">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dcda6-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="dcda6-191">Registrering väntar</span><span class="sxs-lookup"><span data-stu-id="dcda6-191">Registration Pending</span></span> | <span data-ttu-id="dcda6-192">Registreringen är inte klar än.</span><span class="sxs-lookup"><span data-stu-id="dcda6-192">Registration is not done yet.</span></span> <span data-ttu-id="dcda6-193">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="dcda6-193">Check back later.</span></span> |
| <span data-ttu-id="dcda6-194">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="dcda6-194">Registration failed</span></span> | <span data-ttu-id="dcda6-195">Registreringen kunde inte slutföras.</span><span class="sxs-lookup"><span data-stu-id="dcda6-195">Registration could not be completed.</span></span> <span data-ttu-id="dcda6-196">Mer information [finns i Felsökning av](#troubleshooting-device-registration) enhetsregistrering.</span><span class="sxs-lookup"><span data-stu-id="dcda6-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="dcda6-197">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="dcda6-197">Ready for user</span></span> | <span data-ttu-id="dcda6-198">Registreringen har lyckats och enheten är nu redo att levereras till användaren.</span><span class="sxs-lookup"><span data-stu-id="dcda6-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="dcda6-199">Microsoft Managed Desktop vägleder dem genom första gången, så du behöver inte göra ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="dcda6-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="dcda6-200">Aktiv</span><span class="sxs-lookup"><span data-stu-id="dcda6-200">Active</span></span> | <span data-ttu-id="dcda6-201">Enheten har levererats till användaren och de har registrerats i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="dcda6-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="dcda6-202">Det här betyder också att de regelbundet använder enheten.</span><span class="sxs-lookup"><span data-stu-id="dcda6-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="dcda6-203">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="dcda6-203">Inactive</span></span> | <span data-ttu-id="dcda6-204">Enheten har levererats till användaren och de har registrerats i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="dcda6-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="dcda6-205">Men de har inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="dcda6-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="dcda6-206">Felsökning av enhetsregistrering</span><span class="sxs-lookup"><span data-stu-id="dcda6-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="dcda6-207">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="dcda6-207">Error message</span></span> | <span data-ttu-id="dcda6-208">Information</span><span class="sxs-lookup"><span data-stu-id="dcda6-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="dcda6-209">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="dcda6-209">Device not found</span></span> | <span data-ttu-id="dcda6-210">Det gick inte att registrera den här enheten eftersom det inte gick att hitta en matchning för den angivna tillverkaren, modellen eller serienumret.</span><span class="sxs-lookup"><span data-stu-id="dcda6-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="dcda6-211">Bekräfta dessa värden med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="dcda6-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="dcda6-212">Maskinvaruhash inte giltig</span><span class="sxs-lookup"><span data-stu-id="dcda6-212">Hardware hash not valid</span></span> | <span data-ttu-id="dcda6-213">Den maskinvaru-hash du angav för den här enheten är inte korrekt formaterad.</span><span class="sxs-lookup"><span data-stu-id="dcda6-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="dcda6-214">Dubbelkolla maskinvaruhashen och skicka in igen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="dcda6-215">Enheten är redan registrerad</span><span class="sxs-lookup"><span data-stu-id="dcda6-215">Device already registered</span></span> | <span data-ttu-id="dcda6-216">Den här enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dcda6-216">This device is already registered to your organization.</span></span> <span data-ttu-id="dcda6-217">Inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="dcda6-217">No further action required.</span></span> |
| <span data-ttu-id="dcda6-218">Enhet som påstås av en annan organisation</span><span class="sxs-lookup"><span data-stu-id="dcda6-218">Device claimed by another organization</span></span> | <span data-ttu-id="dcda6-219">Den här enheten har redan blivit anspråksad av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="dcda6-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="dcda6-220">Kontrollera med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="dcda6-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="dcda6-221">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="dcda6-221">Unexpected error</span></span> | <span data-ttu-id="dcda6-222">Det gick inte att behandla din begäran automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="dcda6-223">Kontakta supporten och ange ditt begärande-ID: <requestId></span><span class="sxs-lookup"><span data-stu-id="dcda6-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="dcda6-224">Kontrollera bilden</span><span class="sxs-lookup"><span data-stu-id="dcda6-224">Check the image</span></span>

<span data-ttu-id="dcda6-225">Om enheten kommer från en Microsoft Managed Desktop-partnerleverantör ska bilden vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="dcda6-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="dcda6-226">Du får också gärna använda bilden på egen hand om du föredrar det.</span><span class="sxs-lookup"><span data-stu-id="dcda6-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="dcda6-227">Kontakta microsofts representant som du arbetar med för att komma igång och informera dig om var och hur du använder bilden.</span><span class="sxs-lookup"><span data-stu-id="dcda6-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="dcda6-228">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="dcda6-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcda6-229">Innan du lämnar över enheten till användaren kontrollerar du att du har skaffat och [tillämpat lämpliga licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="dcda6-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="dcda6-230">Om alla licenser används kan [](get-started-devices.md)du förbereda användarna för att använda enheter och sedan starta enheten och gå vidare via Windows-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="dcda6-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









