---
title: Fas 3 Konfigurera AD FS-servrar med hög tillgänglighet.
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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Lär dig hur du skapar och konfigurerar AD FS-servrarna för en federerad extern tillgänglighet för Microsoft 365 i Microsoft Azure.
ms.openlocfilehash: bf8b52f4cd0dead0c264b71363fd5248397ae88d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694934"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Avancerad pool med hög tillgänglighet – steg 3: Konfigurera AD FS-servrar

I den här fasen av att distribuera hög tillgänglighet för Microsoft 365 federerad-verifikation i Azure Infrastructure Services skapar du en intern belastningsutjämnare och två AD FS-servrar.
  
Du måste slutföra den här fasen innan du går vidare till [steg 4: Konfigurera Webbprogramproxy](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>Skapa AD FS-serverns virtuella datorer i Azure

Använd följande block med PowerShell-kommandon för att skapa de virtuella datorerna för de två AD FS-servrarna. Den här PowerShell-kommandoraden använder värden från följande tabeller:
  
- Tabell M, för de virtuella datorerna
    
- Tabell R för dina resurs grupper
    
- Tabell V, för dina virtuella nätverks inställningar
    
- Tabell S, för under nätverk
    
- Tabell I, för statiska IP-adresser
    
- Tabell A, för dina tillgänglighets uppsättningar
    
Kom ihåg att du har definierat tabell M i [steg 2: Konfigurera domän kontrol Lanterna](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) och tabellerna R, V, S, i och A i [steg 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [komma igång med Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Först skapar du en intern högavvägning i Azure för de två AD FS-servrarna. Ange värden för variablerna och ta bort \< and > tecknen. När du har angett alla värden kör du det resulterande blocket vid kommando tolken i Azure PowerShell eller i PowerShell ISE.
  
> [!TIP]
> Använd den här [arbets boken för Microsoft Excel-konfiguration](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)om du vill skapa PowerShell-Kommandotolken som är klara att köra. 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

Skapa sedan de virtuella AD FS server-datorerna.
  
När du har angett alla värden kör du det resulterande blocket vid kommando tolken i Azure PowerShell eller i PowerShell ISE.
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> Eftersom de här virtuella datorerna är för ett intranät program är de inte tilldelad en offentlig IP-adress eller en DNS-domän namns etikett och är exponerad för Internet. Det innebär att du inte kan ansluta till dem från Azure-portalen. Alternativet **Anslut** är inte tillgängligt när du visar egenskaperna för den virtuella datorn. Använd anslutning till fjärr skrivbord eller ett annat fjärr skrivbord för att ansluta till den virtuella datorn via dess privata IP-adress eller intranät-DNS-namn.
  
Använd fjärr skrivbords klienten för varje virtuell dator och skapa en anslutning till fjärr skrivbord. Använd dess DNS-eller dator namn och autentiseringsuppgifterna för det lokala administratörs kontot.
  
För varje virtuell dator ansluter du dem till den relevanta AD DS-domänen (Active Directory Domain Services) med de här kommandona i Windows PowerShell-uppmaningen.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Här är konfigurationen som skapas när den här fasen har slutförts, med plats hållare för dator namn.
  
**Fas 3: AD FS-servrar och intern belastningsutjämnare för din höganvända federerad autentiseringsprocess i Azure**

![Fas 3 av den övergripande Microsoft 365-infrastrukturen för extern tillgänglighet i Azure med AD FS-servrarna](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Nästa steg

Använda [fas 4: Konfigurera Webbprogramproxy](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) för att fortsätta konfigurera arbets belastningen.
  
## <a name="see-also"></a>Se även

[Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Microsoft 365-miljö](federated-identity-for-your-microsoft-365-dev-test-environment.md)


