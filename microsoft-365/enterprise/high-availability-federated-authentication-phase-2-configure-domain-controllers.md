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
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Fas 2 för hög tillgänglighet för federerad autentisering: Konfigurera domänkontrollanter

I den här fasen av distributionen av hög tillgänglighet för Microsoft 365-federerad autentisering i Azure-infrastrukturtjänster konfigurerar du två domänkontrollanter och katalogsynkroniseringsservern i det virtuella Azure-nätverket. Klientwebbförfrågningar för autentisering kan sedan autentiseras i det virtuella Azure-nätverket, i stället för att skicka den autentiseringstrafiken via VPN-anslutningen mellan webbplatser till ditt lokala nätverk.
  
> [!NOTE]
> AD FS (Active Directory Federation Services) kan inte använda Azure Active Directory (Azure AD) som ersättning för AD DS-domänkontrollanter (Active Directory Domain Services). 
  
Du måste slutföra den här fasen innan du går vidare [till fas 3: Konfigurera AD FS-servrar](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Se [Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Skapa virtuella domänkontrollanter i Azure

Först måste du fylla  i namnkolumnen för den virtuella datorn i Tabell M och ändra storleken på den virtuella datorn efter behov i **kolumnen Minsta** storlek.
  
|**Objekt**|**Namn på virtuell dator**|**Galleribild**|**Storage typ**|**Minsta storlek**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![rad](../media/Common-Images/TableLine.png) (första domänkontrollanten, exempel DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![rad](../media/Common-Images/TableLine.png) (andra domänkontrollanten, till exempel DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![rad](../media/Common-Images/TableLine.png) (katalogsynkroniseringsserver, exempel DS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![rad](../media/Common-Images/TableLine.png) (första AD FS-servern, exempel ADFS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![rad](../media/Common-Images/TableLine.png) (andra AD FS-servern, exempel ADFS2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![rad](../media/Common-Images/TableLine.png) (first web application proxy server, example WEB1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![rad](../media/Common-Images/TableLine.png) (andra webbprogrammets proxyserver, exempel WEB2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabell M – virtuella datorer för federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure**
  
En fullständig lista över storlekar för virtuella maskiner finns i [Storlekar för virtuella datorer.](/azure/virtual-machines/virtual-machines-windows-sizes)
  
Följande Azure PowerShell skapar de virtuella maskinerna för de två domänkontrollanterna. Ange värden för variablerna och ta bort \< and > tecken. Observera att den Azure PowerShell kommandoblocket använder värden från följande tabeller:
  
- Tabell M, för virtuella datorer
    
- Tabell R, för resursgrupper
    
- Tabell V, för dina virtuella nätverksinställningar
    
- Tabell S, för dina undernät
    
- Tabell I, för statiska IP-adresser
    
- Tabell A, för dina tillgänglighetsuppsättningar
    
Kom ihåg att du definierade tabellerna R, V, S, I och A i [Steg 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Komma igång med Azure PowerShell](/powershell/azure/get-started-azureps). 
  
När du har angett alla korrekta värden kör du resultatblocket i Azure PowerShell-kommandotolken eller i PowerShell Integrated Script Environment (ISE) på den lokala datorn.
  
> [!TIP]
> Om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på dina anpassade inställningar använder du den [här Microsoft Excel konfigurationsarbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

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
> Eftersom dessa virtuella datorer är för ett intranätprogram, tilldelas de inte en offentlig IP-adress eller en DNS-domännamnsetikett och exponeras för Internet. Det innebär dock också att du inte kan ansluta till dem från Azure Portal. Alternativet **Anslut** inte tillgängligt när du visar egenskaperna för den virtuella datorn. Använd fjärrskrivbordsanslutningstillbehöret eller ett annat Fjärrskrivbord-verktyg för att ansluta till den virtuella datorn med dess privata IP-adress eller DNS-namn på intranätet.
  
## <a name="configure-the-first-domain-controller"></a>Konfigurera den första domänkontrollanten

Använd valfri fjärrskrivbordsklient och skapa en anslutning till fjärrskrivbordet till den första virtuella domänkontrollanten. Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.
  
Lägg sedan till den extra dataskivan på den första domänkontrollanten med det här kommandot Windows PowerShell kommandotolken på den första virtuella **domänkontrollanten:**
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Testa sedan den första domänkontrollantens anslutning till platser i organisationens nätverk med hjälp av **kommandot ping** för att pinga namn och IP-adresser för resurser i organisationens nätverk.
  
Den här proceduren säkerställer att DNS-namnmatchningen fungerar korrekt (att den virtuella datorn är korrekt konfigurerad med lokala DNS-servrar) och att paket kan skickas till och från det virtuella nätverket på plats. Om det här grundläggande testet misslyckas kontaktar du IT-avdelningen för att felsöka problem med DNS-namnmatchning och paketleverans.
  
Kör sedan följande Windows PowerShell i den första domänkontrollanten i kommandotolken:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

Du uppmanas att ange autentiseringsuppgifter för ett domänadministratörskonto. Datorn startas om.
  
## <a name="configure-the-second-domain-controller"></a>Konfigurera den andra domänkontrollanten

Använd valfri fjärrskrivbordsklient och skapa en anslutning till den andra virtuella domänkontrollanten. Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.
  
Därefter måste du lägga till den extra dataenheten på den andra domänkontrollanten med det här kommandot från en Windows PowerShell-kommandotolk på den andra virtuella **domänkontrollanten:**
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Kör sedan följande kommandon:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

Du uppmanas att ange autentiseringsuppgifter för ett domänadministratörskonto. Datorn startas om.
  
Därefter måste du uppdatera DNS-servrarna för ditt virtuella nätverk så att Azure tilldelar virtuella datorer IP-adresserna till de två nya domänkontrollanterna som ska användas som DNS-servrar. Fyll i variablerna och kör sedan de här kommandona från Windows PowerShell kommandotolken på den lokala datorn:
  
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

Observera att vi startar om de två domänkontrollanterna så att de inte konfigureras med de lokala DNS-servrarna som DNS-servrar. Eftersom de båda är DNS-servrar själva konfigurerades de automatiskt med de lokala DNS-servrarna som DNS-vidarebefordrare när de framhävdes till domänkontrollanter.
  
Nästa steg är att skapa en Active Directory-replikeringswebbplats för att säkerställa att servrar i det virtuella Azure-nätverket använder de lokala domänkontrollanterna. Anslut till någon av domänkontrollanterna med ett domänadministratörskonto och kör följande kommandon från en administratörsnivå Windows PowerShell fråga:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>Konfigurera katalogsynkroniseringsservern

Använd valfri fjärrskrivbordsklient och skapa en anslutning till den virtuella katalogsynkroniseringsservern. Använd DNS-namnet på intranätet och inloggningsuppgifterna för det lokala administratörskontot.
  
Anslut den sedan till rätt AD DS-domän med de här kommandona Windows PowerShell frågan.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Här är konfigurationen som är ett resultat av att den här fasen slutförts, med platshållardatornamn.
  
**Fas 2: Domänkontrollanterna och katalogsynkroniseringsservern för er infrastruktur för federerad autentisering med hög tillgänglighet i Azure**

![Fas 2 av hög tillgänglighet Microsoft 365 infrastruktur för federerad autentisering i Azure med domänkontrollanter](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Nästa steg

Använd [fas 3: Konfigurera AD FS-servrar för att](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) fortsätta konfigurera arbetsbelastningen.
  
## <a name="see-also"></a>Se även

[Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Microsoft 365 utvecklings-/testmiljö](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)