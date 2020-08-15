---
title: Steg 2 Konfigurera domän kontrol Lanterna för extern tillgänglighet
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
description: 'Sammanfattning: Konfigurera domän kontrol Lanterna och synkroniseringstjänst för extern tillgänglighet för Microsoft 365 i Microsoft Azure.'
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694707"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="45a2f-103">Mellanliggande federerad autentiseringsläge med hög tillgänglighet: Konfigurera domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="45a2f-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="45a2f-104">I den här fasen av att distribuera hög tillgänglighet för Microsoft 365 federerad-verifikation i Azure Infrastructure Services konfigurerar du två domänkontrollanter och katalogpartitionen i Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="45a2f-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="45a2f-105">Klient webb förfrågningar för autentisering kan sedan autentiseras i Azure Virtual Network i stället för att skicka verifierings trafiken via plats-till-plats-anslutningen till det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="45a2f-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45a2f-106">Active Directory Federation Services (AD FS) kan inte använda Azure Active Directory (Azure AD) som ersättning för AD DS-domänkontrollanter (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="45a2f-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="45a2f-107">Du måste slutföra den här fasen innan du går vidare till [steg 3: Konfigurera AD FS-servrar](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="45a2f-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="45a2f-108">Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="45a2f-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="45a2f-109">Skapa virtuella dator datorer i Azure</span><span class="sxs-lookup"><span data-stu-id="45a2f-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="45a2f-110">Först måste du fylla i kolumnen Namn på **virtuell dator** för tabell M och ändra storlek på virtuell dator på det sätt som behövs i kolumnen **minsta storlek** .</span><span class="sxs-lookup"><span data-stu-id="45a2f-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="45a2f-111">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="45a2f-111">**Item**</span></span>|<span data-ttu-id="45a2f-112">**Namn på virtuell dator**</span><span class="sxs-lookup"><span data-stu-id="45a2f-112">**Virtual machine name**</span></span>|<span data-ttu-id="45a2f-113">**Bild av galleriet**</span><span class="sxs-lookup"><span data-stu-id="45a2f-113">**Gallery image**</span></span>|<span data-ttu-id="45a2f-114">**Lagrings typ**</span><span class="sxs-lookup"><span data-stu-id="45a2f-114">**Storage type**</span></span>|<span data-ttu-id="45a2f-115">**Minsta storlek**</span><span class="sxs-lookup"><span data-stu-id="45a2f-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45a2f-116">1.</span><span class="sxs-lookup"><span data-stu-id="45a2f-116">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-118">(första domänkontrollanten, exempel DC1)</span><span class="sxs-lookup"><span data-stu-id="45a2f-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="45a2f-119">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-122">2.</span><span class="sxs-lookup"><span data-stu-id="45a2f-122">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-124">(andra domänkontrollant, exempel DC2)</span><span class="sxs-lookup"><span data-stu-id="45a2f-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="45a2f-125">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-128">3.</span><span class="sxs-lookup"><span data-stu-id="45a2f-128">3.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-130">(katalog synkroniseringstjänst, exempel DS1)</span><span class="sxs-lookup"><span data-stu-id="45a2f-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="45a2f-131">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-134">4.</span><span class="sxs-lookup"><span data-stu-id="45a2f-134">4.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-136">(första AD FS-server, exempel ADFS1)</span><span class="sxs-lookup"><span data-stu-id="45a2f-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="45a2f-137">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-140">5.</span><span class="sxs-lookup"><span data-stu-id="45a2f-140">5.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-142">(AD FS-server, exempel ADFS2)</span><span class="sxs-lookup"><span data-stu-id="45a2f-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="45a2f-143">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-146">18.6.</span><span class="sxs-lookup"><span data-stu-id="45a2f-146">6.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-148">(första Webbprogramproxy, till exempel WEB1)</span><span class="sxs-lookup"><span data-stu-id="45a2f-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="45a2f-149">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="45a2f-152">borttagning.</span><span class="sxs-lookup"><span data-stu-id="45a2f-152">7.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <span data-ttu-id="45a2f-154">(andra Webbprogramproxy, till exempel WEB2)</span><span class="sxs-lookup"><span data-stu-id="45a2f-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="45a2f-155">Windows Server 2016 Data Center</span><span class="sxs-lookup"><span data-stu-id="45a2f-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="45a2f-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="45a2f-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="45a2f-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="45a2f-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="45a2f-158">**Tabell M – virtuella maskiner för federerad åtkomst för hög tillgänglighet för Microsoft 365 i Azure**</span><span class="sxs-lookup"><span data-stu-id="45a2f-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="45a2f-159">En fullständig lista över storlek på virtuell dator finns i [storlekar för virtuella datorer](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).</span><span class="sxs-lookup"><span data-stu-id="45a2f-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="45a2f-160">Följande kommando block för Azure PowerShell skapar de virtuella datorerna för de två domän kontrol Lanterna.</span><span class="sxs-lookup"><span data-stu-id="45a2f-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="45a2f-161">Ange värden för variablerna och ta bort \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="45a2f-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="45a2f-162">Observera att det här kommando blocket för Azure PowerShell använder värden från följande tabeller:</span><span class="sxs-lookup"><span data-stu-id="45a2f-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="45a2f-163">Tabell M, för de virtuella datorerna</span><span class="sxs-lookup"><span data-stu-id="45a2f-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="45a2f-164">Tabell R för dina resurs grupper</span><span class="sxs-lookup"><span data-stu-id="45a2f-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="45a2f-165">Tabell V, för dina virtuella nätverks inställningar</span><span class="sxs-lookup"><span data-stu-id="45a2f-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="45a2f-166">Tabell S, för under nätverk</span><span class="sxs-lookup"><span data-stu-id="45a2f-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="45a2f-167">Tabell I, för statiska IP-adresser</span><span class="sxs-lookup"><span data-stu-id="45a2f-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="45a2f-168">Tabell A, för dina tillgänglighets uppsättningar</span><span class="sxs-lookup"><span data-stu-id="45a2f-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="45a2f-169">Kom ihåg att du har definierat tabeller R, V, S, I och en i [steg 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="45a2f-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="45a2f-170">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45a2f-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="45a2f-171">Se [komma igång med Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="45a2f-171">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="45a2f-172">När du har angett alla korrekta värden kör du det resulterande blocket i Azure PowerShell-uppmaningen eller i PowerShell-integreringen (Integrated script Environment) på din dator.</span><span class="sxs-lookup"><span data-stu-id="45a2f-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="45a2f-173">Använd den här [arbets boken för Microsoft Excel-konfiguration](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)om du vill skapa PowerShell-Kommandotolken som är klara att köra.</span><span class="sxs-lookup"><span data-stu-id="45a2f-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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
> <span data-ttu-id="45a2f-174">Eftersom de här virtuella datorerna är för ett intranät program är de inte tilldelad en offentlig IP-adress eller en DNS-domän namns etikett och är exponerad för Internet.</span><span class="sxs-lookup"><span data-stu-id="45a2f-174">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="45a2f-175">Det innebär att du inte kan ansluta till dem från Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="45a2f-175">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="45a2f-176">Alternativet **Anslut** är inte tillgängligt när du visar egenskaperna för den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="45a2f-176">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="45a2f-177">Använd anslutning till fjärr skrivbord eller ett annat fjärr skrivbord för att ansluta till den virtuella datorn via dess privata IP-adress eller intranät-DNS-namn.</span><span class="sxs-lookup"><span data-stu-id="45a2f-177">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="45a2f-178">Konfigurera den första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="45a2f-178">Configure the first domain controller</span></span>

<span data-ttu-id="45a2f-179">Använd fjärr skrivbords klienten som du väljer och skapa en fjärr skrivbords anslutning till den första virtuella domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="45a2f-179">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine.</span></span> <span data-ttu-id="45a2f-180">Använd dess DNS-eller dator namn och autentiseringsuppgifterna för det lokala administratörs kontot.</span><span class="sxs-lookup"><span data-stu-id="45a2f-180">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="45a2f-181">Lägg sedan till den extra data disken till den första domänkontrollanten med det här kommandot från en Windows PowerShell-kommandotolk **på den första domänkontrollantens virtuella dator**:</span><span class="sxs-lookup"><span data-stu-id="45a2f-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="45a2f-182">Testa sedan den första domänkontrollantens anslutnings barhet till platserna i organisationens nätverk genom att använda **ping** -kommandot för att skicka ping till namn och IP-adresser till resurser i organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="45a2f-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="45a2f-183">Den här proceduren ser till att DNS-namnmatchning fungerar som de ska (att den virtuella datorn är korrekt konfigurerad med lokala DNS-servrar) och att paket kan skickas till och från det lokala virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="45a2f-183">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network.</span></span> <span data-ttu-id="45a2f-184">Om det inte fungerar kan du kontakta IT-avdelningen för att felsöka problem med DNS-namnmatchning och paket leverans.</span><span class="sxs-lookup"><span data-stu-id="45a2f-184">If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="45a2f-185">Gå sedan till kommando tolken för Windows PowerShell på den första domänkontrollanten och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="45a2f-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="45a2f-186">Du uppmanas att ange autentiseringsuppgifter för ett domän administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="45a2f-186">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="45a2f-187">Datorn startas om.</span><span class="sxs-lookup"><span data-stu-id="45a2f-187">The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="45a2f-188">Konfigurera den andra domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="45a2f-188">Configure the second domain controller</span></span>

<span data-ttu-id="45a2f-189">Använd fjärr skrivbords klienten som du väljer och skapa en fjärr skrivbords anslutning till den andra domänkontrollantens virtuella dator.</span><span class="sxs-lookup"><span data-stu-id="45a2f-189">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine.</span></span> <span data-ttu-id="45a2f-190">Använd dess DNS-eller dator namn och autentiseringsuppgifterna för det lokala administratörs kontot.</span><span class="sxs-lookup"><span data-stu-id="45a2f-190">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="45a2f-191">Sedan måste du lägga till den extra data disken till den andra domänkontrollanten med det här kommandot från en Windows PowerShell-kommandotolk **på den andra domänkontrollantens virtuella dator**:</span><span class="sxs-lookup"><span data-stu-id="45a2f-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="45a2f-192">Kör sedan följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="45a2f-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="45a2f-193">Du uppmanas att ange autentiseringsuppgifter för ett domän administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="45a2f-193">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="45a2f-194">Datorn startas om.</span><span class="sxs-lookup"><span data-stu-id="45a2f-194">The computer will restart.</span></span>
  
<span data-ttu-id="45a2f-195">Sedan måste du uppdatera DNS-servrarna för det virtuella nätverket så att Azure tilldelar virtuella datorer IP-adresserna för de två nya domän kontrol Lanterna att använda som DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="45a2f-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="45a2f-196">Fyll i variablerna och kör de här kommandona från en Windows PowerShell-kommandotolk på din lokala dator:</span><span class="sxs-lookup"><span data-stu-id="45a2f-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
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

<span data-ttu-id="45a2f-197">Observera att vi startar om de två domän kontrol Lanterna så att de inte är konfigurerade med lokala DNS-servrar som DNS-servrar.</span><span class="sxs-lookup"><span data-stu-id="45a2f-197">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers.</span></span> <span data-ttu-id="45a2f-198">Eftersom de båda är DNS-servrar konfigurerade de automatiskt med lokala DNS-servrar som DNS-vidarebefordrare när de uppgraderades till domänkontrollanter.</span><span class="sxs-lookup"><span data-stu-id="45a2f-198">Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="45a2f-199">Nu måste vi skapa en Active Directory-replikeringsgrupp för att säkerställa att servrar i det virtuella Azure-nätverket använder de lokala domän kontrol Lanterna.</span><span class="sxs-lookup"><span data-stu-id="45a2f-199">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers.</span></span> <span data-ttu-id="45a2f-200">Anslut till domänkontrollant med domän administratörs konto och kör följande kommandon från en Windows PowerShell-kommandotolk på administratörs nivå:</span><span class="sxs-lookup"><span data-stu-id="45a2f-200">Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="45a2f-201">Konfigurera katalogpartitionen för servrar</span><span class="sxs-lookup"><span data-stu-id="45a2f-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="45a2f-202">Använd fjärr skrivbords klienten som du väljer och skapa en fjärr skrivbords anslutning till den virtuella datorn för den synkroniserade servern.</span><span class="sxs-lookup"><span data-stu-id="45a2f-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="45a2f-203">Använd dess DNS-eller dator namn och autentiseringsuppgifterna för det lokala administratörs kontot.</span><span class="sxs-lookup"><span data-stu-id="45a2f-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="45a2f-204">Gå sedan till den relevanta AD DS-domänen med de här kommandona i Windows PowerShell-uppmaningen.</span><span class="sxs-lookup"><span data-stu-id="45a2f-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="45a2f-205">Här är konfigurationen som skapas när den här fasen har slutförts, med plats hållare för dator namn.</span><span class="sxs-lookup"><span data-stu-id="45a2f-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="45a2f-206">**Fas 2: domän kontrol Lanterna och synkroniseringstjänst för extern tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="45a2f-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Fas 2 av den övergripande Microsoft 365-infrastrukturen för extern tillgänglighet i Azure med domänkontrollanter](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="45a2f-208">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="45a2f-208">Next step</span></span>

<span data-ttu-id="45a2f-209">Använda [fas 3: Konfigurera AD FS-servrar](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) för att fortsätta konfigurera arbets belastningen.</span><span class="sxs-lookup"><span data-stu-id="45a2f-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45a2f-210">Se även</span><span class="sxs-lookup"><span data-stu-id="45a2f-210">See Also</span></span>

[<span data-ttu-id="45a2f-211">Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="45a2f-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="45a2f-212">Federerad identitet för din Microsoft 365-miljö</span><span class="sxs-lookup"><span data-stu-id="45a2f-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="45a2f-213">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="45a2f-213">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)


