---
title: Hög tillgänglighet, federerad autentisering – fas 4 Konfigurera proxyprogram för webbprogram
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
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 'Sammanfattning: Konfigurera webbprogrammets proxyservrar för hög tillgänglighet federerad autentisering för Microsoft 365 i Microsoft Azure.'
ms.openlocfilehash: 95d73d05f2eef087e606df14db180b24c69d5932
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929078"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>Fas 4 för hög tillgänglighet för federerad autentisering: Konfigurera proxyprogram för webbprogram

I den här fasen av distributionen av hög tillgänglighet för Microsoft 365-federerad autentisering i Azure-infrastrukturtjänster skapar du en intern belastningsutjämnare och två AD FS-servrar.
  
Du måste slutföra den här fasen innan du går vidare [till steg 5: Konfigurera federerad autentisering för Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) Se [Distribuera hög tillgänglighet federerad autentisering för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>Skapa belastningsutjämaren mot Internet i Azure

Du måste skapa en belastningsutjämnare på Internet så att Azure distribuerar inkommande klientautentiseringstrafik från Internet jämnt mellan de två proxyservrarna för webbprogram.
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Komma igång med Azure PowerShell.](/powershell/azure/get-started-azureps) 
  
När du har angett värden för plats- och resursgrupper kör du det resulterande blocket i Azure PowerShell-kommandotolken eller i PowerShell ISE.
  
> [!TIP]
> Använd den här arbetsboken för Microsoft Excel-konfiguration om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på [dina egna inställningar.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

Om du vill visa den offentliga IP-adressen som är kopplad till din Internet-belastningsutjämnare kör du följande kommandon i Azure PowerShell-kommandotolken på den lokala datorn:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>Bestäm FQDN för federationstjänsten och skapa DNS-poster

Du måste ta reda på DNS-namnet för att kunna identifiera federationstjänstens namn på Internet. Azure AD Connect konfigurerar Microsoft 365 med det här namnet i fas 5, som blir en del av URL-adressen som Microsoft 365 skickar till anslutande klienter för att få en säkerhetstoken. Ett exempel är fs.contoso.com (fs står för federationstjänst).
  
När du har federationstjänstens FDQN skapar du en offentlig DNS-domän En post för federationstjänstens FDQN som löser den offentliga IP-adressen för Azure Internet-belastningsutjämnaren.
  
|**Name**|**Type (typ)**|**TTL**|**Värde**|
|:-----|:-----|:-----|:-----|
|federationstjänst FDQN  <br/> |A  <br/> |3600  <br/> |offentlig IP-adress för Azure-belastningsutjämaren (visas av **kommandot Write-Host** i föregående avsnitt) <br/> |
   
Här är ett exempel:
  
|**Name**|**Type (typ)**|**TTL**|**Värde**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
Lägg sedan till en DNS-adresspost i organisationens privata DNS-namnområde som löser federationstjänstens FQDN till den privata IP-adressen som tilldelats den interna belastningsutjämaren för AD FS-servrarna (tabell I, objekt 4, värdekolumnen).
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>Skapa webbprogramproxyserverns virtuella datorer i Azure

Använd följande block med Azure PowerShell-kommandon för att skapa virtuella datorer för de två proxyservrarna för webbprogram. 
  
Observera att följande Azure PowerShell-kommandouppsättningar använder värden från följande tabeller:
  
- Tabell M, för virtuella datorer
    
- Tabell R, för resursgrupper
    
- Tabell V, för dina virtuella nätverksinställningar
    
- Tabell S, för dina undernät
    
- Tabell I, för statiska IP-adresser
    
- Tabell A, för dina tillgänglighetsuppsättningar
    
Kom ihåg att du definierade Tabell M i fas [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Konfigurera domänkontrollanter och tabell R, V, S, I och A i [fas 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
När du har angett alla värden kör du det resulterande blocket i Azure PowerShell-kommandotolken eller i PowerShell ISE.
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Eftersom dessa virtuella datorer är för ett intranätprogram, tilldelas de inte en offentlig IP-adress eller en DNS-domännamnsetikett och exponeras för Internet. Det innebär dock också att du inte kan ansluta till dem från Azure Portal. Alternativet **Anslut** är inte tillgängligt när du visar egenskaperna för den virtuella datorn. Använd Fjärrskrivbordanslutningstillbehör eller ett annat Fjärrskrivbord-verktyg för att ansluta till den virtuella datorn med dess privata IP-adress eller DNS-namn på intranätet och det lokala administratörskontots autentiseringsuppgifter.
  
Här är konfigurationen som är ett resultat av att den här fasen slutförts, med platshållardatornamn.
  
**Fas 4: Proxyservrarna för internetbaserad belastningsutjämning och webbprogram för din hög tillgänglighetsinfrastruktur för federerad autentisering i Azure**

![Fas 4 av Hög tillgänglighet : Microsoft 365-infrastruktur för federerad autentisering i Azure med proxyservrarna för webbprogram](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>Nästa steg

Använd [fas 5: Konfigurera federerad autentisering för Microsoft 365 för att](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) fortsätta konfigurera arbetsbelastningen.
  
## <a name="see-also"></a>Se även

[Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Utvecklings-/testmiljö för Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)