---
title: Fas 2 Konfigurera domänkontrollanter för hög tillgänglighet fas 2
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: Sammanfattning Konfigurera domänkontrollanter och katalogsynkroniseringsserver för federerad autentisering med hög tillgänglighet för Microsoft 365 i Microsoft Azure.
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909816"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="308d0-103">Fas 2 för hög tillgänglighet för federerad autentisering: Konfigurera domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="308d0-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="308d0-104">I den här fasen av distributionen av hög tillgänglighet för Microsoft 365-federerad autentisering i Azure-infrastrukturtjänster konfigurerar du två domänkontrollanter och katalogsynkroniseringsservern i det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="308d0-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="308d0-105">Klientwebbförfrågningar för autentisering kan sedan autentiseras i det virtuella Azure-nätverket, i stället för att skicka den autentiseringstrafiken via VPN-anslutningen mellan webbplatser till ditt lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="308d0-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="308d0-106">AD FS (Active Directory Federation Services) kan inte använda Azure Active Directory (Azure AD) som ersättning för AD DS-domänkontrollanter (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="308d0-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="308d0-107">Du måste slutföra den här fasen innan du går vidare [till fas 3: Konfigurera AD FS-servrar](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="308d0-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="308d0-108">Se [Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="308d0-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="308d0-109">Skapa virtuella domänkontrollanter i Azure</span><span class="sxs-lookup"><span data-stu-id="308d0-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="308d0-110">Först måste du fylla  i namnkolumnen för den virtuella datorn i Tabell M och ändra storleken på den virtuella datorn efter behov i **kolumnen Minsta** storlek.</span><span class="sxs-lookup"><span data-stu-id="308d0-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="308d0-111">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="308d0-111">**Item**</span></span>|<span data-ttu-id="308d0-112">**Namn på virtuell dator**</span><span class="sxs-lookup"><span data-stu-id="308d0-112">**Virtual machine name**</span></span>|<span data-ttu-id="308d0-113">**Galleribild**</span><span class="sxs-lookup"><span data-stu-id="308d0-113">**Gallery image**</span></span>|<span data-ttu-id="308d0-114">**Storage typ**</span><span class="sxs-lookup"><span data-stu-id="308d0-114">**Storage type**</span></span>|<span data-ttu-id="308d0-115">**Minsta storlek**</span><span class="sxs-lookup"><span data-stu-id="308d0-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="308d0-116">1.</span><span class="sxs-lookup"><span data-stu-id="308d0-116">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-118">(första domänkontrollanten, exempel DC1)</span><span class="sxs-lookup"><span data-stu-id="308d0-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="308d0-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-122">2.</span><span class="sxs-lookup"><span data-stu-id="308d0-122">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-124">(andra domänkontrollanten, till exempel DC2)</span><span class="sxs-lookup"><span data-stu-id="308d0-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="308d0-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-128">3.</span><span class="sxs-lookup"><span data-stu-id="308d0-128">3.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-130">(katalogsynkroniseringsserver, exempel DS1)</span><span class="sxs-lookup"><span data-stu-id="308d0-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="308d0-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-134">4.</span><span class="sxs-lookup"><span data-stu-id="308d0-134">4.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-136">(första AD FS-servern, exempel ADFS1)</span><span class="sxs-lookup"><span data-stu-id="308d0-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="308d0-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-140">5.</span><span class="sxs-lookup"><span data-stu-id="308d0-140">5.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-142">(andra AD FS-servern, exempel ADFS2)</span><span class="sxs-lookup"><span data-stu-id="308d0-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="308d0-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-146">6.</span><span class="sxs-lookup"><span data-stu-id="308d0-146">6.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-148">(first web application proxy server, example WEB1)</span><span class="sxs-lookup"><span data-stu-id="308d0-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="308d0-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="308d0-152">7.</span><span class="sxs-lookup"><span data-stu-id="308d0-152">7.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <span data-ttu-id="308d0-154">(andra webbprogrammets proxyserver, exempel WEB2)</span><span class="sxs-lookup"><span data-stu-id="308d0-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="308d0-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="308d0-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="308d0-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="308d0-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="308d0-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="308d0-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="308d0-158">**Tabell M – virtuella datorer för federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure**</span><span class="sxs-lookup"><span data-stu-id="308d0-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="308d0-159">En fullständig lista över storlekar för virtuella maskiner finns i [Storlekar för virtuella datorer.](/azure/virtual-machines/virtual-machines-windows-sizes)</span><span class="sxs-lookup"><span data-stu-id="308d0-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="308d0-160">Följande Azure PowerShell skapar de virtuella maskinerna för de två domänkontrollanterna.</span><span class="sxs-lookup"><span data-stu-id="308d0-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="308d0-161">Ange värden för variablerna och ta bort \< and > tecken.</span><span class="sxs-lookup"><span data-stu-id="308d0-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="308d0-162">Observera att den Azure PowerShell kommandoblocket använder värden från följande tabeller:</span><span class="sxs-lookup"><span data-stu-id="308d0-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="308d0-163">Tabell M, för virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="308d0-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="308d0-164">Tabell R, för resursgrupper</span><span class="sxs-lookup"><span data-stu-id="308d0-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="308d0-165">Tabell V, för dina virtuella nätverksinställningar</span><span class="sxs-lookup"><span data-stu-id="308d0-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="308d0-166">Tabell S, för dina undernät</span><span class="sxs-lookup"><span data-stu-id="308d0-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="308d0-167">Tabell I, för statiska IP-adresser</span><span class="sxs-lookup"><span data-stu-id="308d0-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="308d0-168">Tabell A, för dina tillgänglighetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="308d0-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="308d0-169">Kom ihåg att du definierade tabellerna R, V, S, I och A i [Steg 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="308d0-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="308d0-170">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="308d0-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="308d0-171">Se [Komma igång med Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="308d0-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="308d0-172">När du har angett alla korrekta värden kör du resultatblocket i Azure PowerShell-kommandotolken eller i PowerShell Integrated Script Environment (ISE) på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="308d0-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="308d0-173">Om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på dina anpassade inställningar använder du den [här Microsoft Excel konfigurationsarbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="308d0-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="308d0-174">Eftersom dessa virtuella datorer är för ett intranätprogram, tilldelas de inte en offentlig IP-adress eller en DNS-domännamnsetikett och exponeras för Internet.</span><span class="sxs-lookup"><span data-stu-id="308d0-174">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="308d0-175">Det innebär dock också att du inte kan ansluta till dem från Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="308d0-175">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="308d0-176">Alternativet **Anslut** inte tillgängligt när du visar egenskaperna för den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="308d0-176">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="308d0-177">Använd fjärrskrivbordsanslutningstillbehöret eller ett annat Fjärrskrivbord-verktyg för att ansluta till den virtuella datorn med dess privata IP-adress eller DNS-namn på intranätet.</span><span class="sxs-lookup"><span data-stu-id="308d0-177">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="308d0-178">Konfigurera den första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="308d0-178">Configure the first domain controller</span></span>

<span data-ttu-id="308d0-179">Använd valfri fjärrskrivbordsklient och skapa en anslutning till fjärrskrivbordet till den första virtuella domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="308d0-179">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine.</span></span> <span data-ttu-id="308d0-180">Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="308d0-180">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="308d0-181">Lägg sedan till den extra dataskivan på den första domänkontrollanten med det här kommandot Windows PowerShell kommandotolken på den första virtuella **domänkontrollanten:**</span><span class="sxs-lookup"><span data-stu-id="308d0-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="308d0-182">Testa sedan den första domänkontrollantens anslutning till platser i organisationens nätverk med hjälp av **kommandot ping** för att pinga namn och IP-adresser för resurser i organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="308d0-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="308d0-183">Den här proceduren säkerställer att DNS-namnmatchningen fungerar korrekt (att den virtuella datorn är korrekt konfigurerad med lokala DNS-servrar) och att paket kan skickas till och från det virtuella nätverket på plats.</span><span class="sxs-lookup"><span data-stu-id="308d0-183">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network.</span></span> <span data-ttu-id="308d0-184">Om det här grundläggande testet misslyckas kontaktar du IT-avdelningen för att felsöka problem med DNS-namnmatchning och paketleverans.</span><span class="sxs-lookup"><span data-stu-id="308d0-184">If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="308d0-185">Kör sedan följande Windows PowerShell i den första domänkontrollanten i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="308d0-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="308d0-186">Du uppmanas att ange autentiseringsuppgifter för ett domänadministratörskonto.</span><span class="sxs-lookup"><span data-stu-id="308d0-186">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="308d0-187">Datorn startas om.</span><span class="sxs-lookup"><span data-stu-id="308d0-187">The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="308d0-188">Konfigurera den andra domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="308d0-188">Configure the second domain controller</span></span>

<span data-ttu-id="308d0-189">Använd valfri fjärrskrivbordsklient och skapa en anslutning till den andra virtuella domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="308d0-189">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine.</span></span> <span data-ttu-id="308d0-190">Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="308d0-190">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="308d0-191">Därefter måste du lägga till den extra dataenheten på den andra domänkontrollanten med det här kommandot från en Windows PowerShell-kommandotolk på den andra virtuella **domänkontrollanten:**</span><span class="sxs-lookup"><span data-stu-id="308d0-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="308d0-192">Kör sedan följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="308d0-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="308d0-193">Du uppmanas att ange autentiseringsuppgifter för ett domänadministratörskonto.</span><span class="sxs-lookup"><span data-stu-id="308d0-193">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="308d0-194">Datorn startas om.</span><span class="sxs-lookup"><span data-stu-id="308d0-194">The computer will restart.</span></span>
  
<span data-ttu-id="308d0-195">Därefter måste du uppdatera DNS-servrarna för ditt virtuella nätverk så att Azure tilldelar virtuella datorer IP-adresserna till de två nya domänkontrollanterna som ska användas som DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="308d0-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="308d0-196">Fyll i variablerna och kör sedan de här kommandona från Windows PowerShell kommandotolken på den lokala datorn:</span><span class="sxs-lookup"><span data-stu-id="308d0-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

<span data-ttu-id="308d0-197">Observera att vi startar om de två domänkontrollanterna så att de inte konfigureras med de lokala DNS-servrarna som DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="308d0-197">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers.</span></span> <span data-ttu-id="308d0-198">Eftersom de båda är DNS-servrar själva konfigurerades de automatiskt med de lokala DNS-servrarna som DNS-vidarebefordrare när de framhävdes till domänkontrollanter.</span><span class="sxs-lookup"><span data-stu-id="308d0-198">Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="308d0-199">Nästa steg är att skapa en Active Directory-replikeringswebbplats för att säkerställa att servrar i det virtuella Azure-nätverket använder de lokala domänkontrollanterna.</span><span class="sxs-lookup"><span data-stu-id="308d0-199">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers.</span></span> <span data-ttu-id="308d0-200">Anslut till någon av domänkontrollanterna med ett domänadministratörskonto och kör följande kommandon från en administratörsnivå Windows PowerShell fråga:</span><span class="sxs-lookup"><span data-stu-id="308d0-200">Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="308d0-201">Konfigurera katalogsynkroniseringsservern</span><span class="sxs-lookup"><span data-stu-id="308d0-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="308d0-202">Använd valfri fjärrskrivbordsklient och skapa en anslutning till den virtuella katalogsynkroniseringsservern.</span><span class="sxs-lookup"><span data-stu-id="308d0-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="308d0-203">Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="308d0-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="308d0-204">Anslut den sedan till rätt AD DS-domän med de här kommandona Windows PowerShell frågan.</span><span class="sxs-lookup"><span data-stu-id="308d0-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="308d0-205">Här är konfigurationen som är ett resultat av att den här fasen slutförts, med platshållardatornamn.</span><span class="sxs-lookup"><span data-stu-id="308d0-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="308d0-206">**Fas 2: Domänkontrollanterna och katalogsynkroniseringsservern för er infrastruktur för federerad autentisering med hög tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="308d0-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Fas 2 av hög tillgänglighet Microsoft 365 infrastruktur för federerad autentisering i Azure med domänkontrollanter](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="308d0-208">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="308d0-208">Next step</span></span>

<span data-ttu-id="308d0-209">Använd [fas 3: Konfigurera AD FS-servrar för att](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) fortsätta konfigurera arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="308d0-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="308d0-210">Se även</span><span class="sxs-lookup"><span data-stu-id="308d0-210">See Also</span></span>

[<span data-ttu-id="308d0-211">Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="308d0-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="308d0-212">Federerad identitet för din Microsoft 365 utvecklings-/testmiljö</span><span class="sxs-lookup"><span data-stu-id="308d0-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="308d0-213">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="308d0-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)