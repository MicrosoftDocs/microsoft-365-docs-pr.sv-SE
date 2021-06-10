---
title: Hög tillgänglighet federerad autentisering Fas 3 Konfigurera AD FS-servrar
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
description: Lär dig hur du skapar och konfigurerar AD FS-servrar för federerad autentisering med hög tillgänglighet för Microsoft 365 i Microsoft Azure.
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909804"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Fas 3 med hög tillgänglighet för federerad autentisering: Konfigurera AD FS-servrar

I den här fasen av distributionen av hög tillgänglighet för Microsoft 365 federerad autentisering i Azure-infrastrukturtjänster skapar du en intern belastningsutjämnare och två AD FS-servrar.
  
Du måste slutföra den här fasen innan du går vidare [till Fas 4: Konfigurera proxyprogram .](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) Se [Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>Skapa AD FS-serverns virtuella datorer i Azure

Använd följande block med PowerShell-kommandon för att skapa virtuella datorer för de två AD FS-servrarna. I den här PowerShell-kommandouppsättningen används värden från följande tabeller:
  
- Tabell M, för virtuella datorer
    
- Tabell R, för resursgrupper
    
- Tabell V, för dina virtuella nätverksinställningar
    
- Tabell S, för dina undernät
    
- Tabell I, för statiska IP-adresser
    
- Tabell A, för dina tillgänglighetsuppsättningar
    
Kom ihåg att du definierade Tabell M i fas [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Konfigurera domänkontrollanter och tabell R, V, S, I och A i [fas 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Komma igång med Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Först skapar du en intern belastningsutjämning för Azure för de två AD FS-servrarna. Ange värden för variablerna och ta bort \< and > tecken. När du har angett alla korrekta värden kör du det resulterande blocket Azure PowerShell kommandotolken eller i PowerShell ISE.
  
> [!TIP]
> Om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på dina anpassade inställningar använder du den [här Microsoft Excel konfigurationsarbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

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

Skapa sedan virtuella AD FS-serverdatorer.
  
När du har angett alla korrekta värden kör du det resulterande blocket Azure PowerShell kommandotolken eller i PowerShell ISE.
  
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
> Eftersom dessa virtuella datorer är för ett intranätprogram, tilldelas de inte en offentlig IP-adress eller en DNS-domännamnsetikett och exponeras för Internet. Det innebär dock också att du inte kan ansluta till dem från Azure Portal. Alternativet **Anslut** inte tillgängligt när du visar egenskaperna för den virtuella datorn. Använd fjärrskrivbordsanslutningstillbehöret eller ett annat Fjärrskrivbord-verktyg för att ansluta till den virtuella datorn med dess privata IP-adress eller DNS-namn på intranätet.
  
Använd valfri fjärrskrivbordsklient för varje virtuell dator och skapa en anslutning för fjärrskrivbord. Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.
  
För varje virtuell dator ansluter du dem till rätt AD DS-domän (Active Directory Domain Services) med dessa kommandon Windows PowerShell meddelande.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Här är konfigurationen som är ett resultat av att den här fasen slutförts, med platshållardatornamn.
  
**Fas 3: AD FS-servrarna och den interna belastningsutjämnaren för er infrastruktur för federerad autentisering med hög tillgänglighet i Azure**

![Fas 3 av hög tillgänglighet Microsoft 365 infrastruktur för federerad autentisering i Azure med AD FS-servrarna](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Nästa steg

Använd [fas 4: Konfigurera proxyprogram för webbprogram för att fortsätta](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) konfigurera den här arbetsbelastningen.
  
## <a name="see-also"></a>Se även

[Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Microsoft 365 utvecklings-/testmiljö](federated-identity-for-your-microsoft-365-dev-test-environment.md)