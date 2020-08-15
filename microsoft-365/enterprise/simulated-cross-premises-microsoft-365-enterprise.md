---
title: Simulerat virtuellt nätverk på flera platser i en Microsoft 365-testmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Sammanfattning: Skapa ett virtuellt nätverk för flera platser i Microsoft Azure som en Microsoft 365-testmiljö.'
ms.openlocfilehash: afbf294d0637c3454cedadec3268e74411a3c399
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685730"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Simulerat virtuellt nätverk på flera platser i en Microsoft 365-testmiljö

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

I den här artikeln beskrivs hur du använder Microsoft Azure för att skapa en simulerad, hybridbaserad molnmiljö med två virtuella Azure-nätverk. Här är konfigurationsresultatet. 
  
![Fas 3 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, där den virtuella DC2-datorn finns i XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Den simulerar en hybridbaserad Azure Iaas-produktionsmiljö i molnet och består av:
  
- Ett simulerat och förenklat lokalt nätverk som finns i ett virtuellt Azure-nätverk (det virtuella TestLab-nätverket).
    
- Ett simulerat, virtuellt nätverk för flera platser som lagras i Azure (XPrem).
    
- Ett virtuellt nätverk för peeringrelation mellan de två virtuella nätverken.
    
- En sekundär domänkontrollant i det virtuella XPrem-nätverket.
    
På så sätt får du en grund och en gemensam utgångspunkt från vilken du kan göra följande: 
  
- Utveckla och testa programmen i en simulerad, hybridbaserad Azure IaaS-molnmiljö.
    
- Skapa testkonfigurationer med datorer, där vissa ingår i det virtuella TestLab-nätverket och vissa i det virtuella XPrem-nätverket, för att simulera hybrid- och molnbaserade IT-arbetsbelastningar.
    
Konfigurationen av testmiljön består av tre huvudfaser:
  
1. Konfigurera det virtuella TestLab-nätverket.
    
2. Skapa det virtuella nätverket på flera platser.
    
3. Konfigurera DC2.
    
> [!NOTE]
> Konfigurationen kräver en betald Azure-prenumeration. 

Du kan använda den resulterande miljön för att testa funktionerna i [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/enterprise) med ytterligare [test labb guider](m365-enterprise-test-lab-guides.md) eller på egen hand.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Gå till [Microsoft 365 för Enterprise test laboratorie guide stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 för Enterprise Test Lab-guide.

## <a name="phase-1-configure-the-testlab-virtual-network"></a>Fas 1: Konfigurera det virtuella TestLab-nätverket.

Använd anvisningarna i **Fas 1** av [baskonfigurationen för det simulerade företaget](simulated-ent-base-configuration-microsoft-365-enterprise.md) för att konfigurera DC1-, APP1-och KLIENT1-datorerna i det virtuella Azure-nätverket med namnet TestLab.
  
Det här är den aktuella konfigurationen. 
  
![Baskonfiguration för simulerat företag i Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>Steg 2: Skapa det virtuella XPrem-nätverket

I den här fasen skapar och konfigurerar du det nya virtuella XPrem-nätverket och ansluter det sedan till det virtuella TestLab-nätverket med VNet-peering.
  
Starta först en Azure PowerShell-kommandotolk på din lokala dator.
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Kom igång med Azure PowerShell-cmdletar](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Logga in på ditt Azure-konto med det här kommandot.
  
```powershell
Connect-AzAccount
```

Hämta ditt prenumerationsnamn med det här kommandot.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Ange din Azure-prenumeration. Ersätt allt inom citattecknen, inklusive \< and >-tecknen med de rätta namnen.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Skapa sedan det virtuella XPrem-nätverket och skydda det med en nätverkssäkerhetsgrupp med dessa kommandon.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Nästa steg är att skapa ett virtuellt nätverk för peeringrelation mellan de virtuella TestLab- och XPrem-nätverken med dessa kommandon.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

Det här är den aktuella konfigurationen. 
  
![Fas 2 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, med det virtuella XPrem-nätverket och det virtuella nätverket för peeringrelation](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>Fas 3: Konfigurera DC2

I den här fasen skapar du den virtuella DC2-datorn i det virtuella XPrem-nätverket och konfigurerar den sedan som en replikeringsdomänkontrollant.
  
Börja med att skapa en virtuell dator för DC2. Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Anslut sedan till den nya, virtuella DC2-datorn från [Azure-portalen](https://portal.azure.com) med hjälp av den lokala administratörens kontonamn och lösenord.
  
Därefter konfigurerar du en Windows-brandväggsregel för att tillåta trafik för grundläggande anslutningstester. Kör de här kommandona i en Windows PowerShell-kommandotolk på DC2 på administratörsnivå. 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

Ping-kommandot ska resultera i fyra lyckade svar från IP-adressen 10.0.0.4. Det här är ett test av trafiken i det virtuella nätverket för peeringrelation. 
  
Lägg sedan till den extra datadisken som en ny volym med enhetsbokstaven F: med det här kommandot i Windows PowerShell-kommandotolken på DC2.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Därefter konfigurerar du DC2 som en replikeringsdomänkontrollant för domänen corp.contoso.com. Kör de här kommandona i Windows PowerShell-kommandotolken på DC2.
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

Observera att du uppmanas att ange både lösenordet CORP\\User1 och ett lösenord för återställningsläge för katalogtjänster, och att starta om DC2. 
  
När det virtuella XPrem-nätverket nu har en egen DNS-server (DC2) måste du konfigurera det virtuella XPrem-nätverket så att det använder DNS-servern. Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

Från Azure-portalen på din lokala dator ansluter du till DC1 med autentiseringsuppgifterna CORP\\User1. Om du vill konfigurera CORP-domänen så att datorerna och användarna använder den lokala domänkontrollanten för autentisering kör du dessa kommandon från en Windows PowerShell-kommandotolk på administratörsnivå på DC1.
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

Det här är den aktuella konfigurationen. 
  
![Fas 3 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, där den virtuella DC2-datorn finns i XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Din simulerade Azure-hybridmolnmiljö är nu redo att testas.
  
Nu kan du experimentera med fler funktioner i [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Nästa steg

Utforska dessa ytterligare uppsättningar testlabbguider:
  
- [Identitet](m365-enterprise-test-lab-guides.md#identity)
- [Hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Informationsskydd](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Snabbreferens

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
