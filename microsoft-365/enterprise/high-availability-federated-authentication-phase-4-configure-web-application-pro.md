---
title: Avancerad pool med hög tillgänglighet steg 4 Konfigurera Webbprogramproxy
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
description: 'Sammanfattning: Konfigurera Webbprogramproxy för din högprioriterade federerad inloggningsautentisering för Microsoft 365 i Microsoft Azure.'
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694705"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="62eb7-103">Federerad pool med hög tillgänglighet – steg 4: Konfigurera Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="62eb7-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="62eb7-104">I den här fasen av att distribuera hög tillgänglighet för Microsoft 365 federerad-verifikation i Azure Infrastructure Services skapar du en intern belastningsutjämnare och två AD FS-servrar.</span><span class="sxs-lookup"><span data-stu-id="62eb7-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="62eb7-105">Du måste slutföra den här fasen innan du går vidare till [steg 5: Konfigurera federerad auktorisering för Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="62eb7-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="62eb7-106">Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="62eb7-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="62eb7-107">Skapa Internet Facing belastningsutjämnare i Azure</span><span class="sxs-lookup"><span data-stu-id="62eb7-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="62eb7-108">Du måste skapa en Internetbaserad belastnings utjämning så att Azure distribuerar trafiken för inkommande klientautentisering från Internet jämnt bland de två webbprogramproxy.</span><span class="sxs-lookup"><span data-stu-id="62eb7-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62eb7-109">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62eb7-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="62eb7-110">Se [komma igång med Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="62eb7-110">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="62eb7-111">När du har angett plats-och resurs grupp värden kör du det resulterande blocket vid kommando tolken i Azure PowerShell eller i PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="62eb7-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="62eb7-112">Använd den här [arbets boken för Microsoft Excel-konfiguration](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)om du vill skapa PowerShell-Kommandotolken som är klara att köra.</span><span class="sxs-lookup"><span data-stu-id="62eb7-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="62eb7-113">Kör de här kommandona i Azure PowerShell-Kommandotolken på din lokala dator för att visa den offentliga IP-adressen som är tilldelad till din Internet-anslutning.</span><span class="sxs-lookup"><span data-stu-id="62eb7-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="62eb7-114">Fastställ FQDN-namn för Federations tjänsten och skapa DNS-poster</span><span class="sxs-lookup"><span data-stu-id="62eb7-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="62eb7-115">Du måste kontrol lera DNS-namnet för att identifiera ditt Federations tjänst namn på Internet.</span><span class="sxs-lookup"><span data-stu-id="62eb7-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="62eb7-116">Azure AD Connect konfigurerar Microsoft 365 med det här namnet i steg 5, som kommer att bli en del av URL-adressen som Microsoft 365 skickar till att ansluta klienter för att få en säkerhetstoken.</span><span class="sxs-lookup"><span data-stu-id="62eb7-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="62eb7-117">Ett exempel är fs.contoso.com (FS står för Federations tjänsten).</span><span class="sxs-lookup"><span data-stu-id="62eb7-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="62eb7-118">När du har en FDQN för Federations tjänsten skapar du en offentlig DNS-domän A-FDQN som matchas till den offentliga IP-adressen för Azure Internet-load-belastningsutjämnaren.</span><span class="sxs-lookup"><span data-stu-id="62eb7-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="62eb7-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="62eb7-119">**Name**</span></span>|<span data-ttu-id="62eb7-120">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="62eb7-120">**Type**</span></span>|<span data-ttu-id="62eb7-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62eb7-121">**TTL**</span></span>|<span data-ttu-id="62eb7-122">**Värde**</span><span class="sxs-lookup"><span data-stu-id="62eb7-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62eb7-123">Federations tjänstens FDQN</span><span class="sxs-lookup"><span data-stu-id="62eb7-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="62eb7-124">Kallas</span><span class="sxs-lookup"><span data-stu-id="62eb7-124">A</span></span>  <br/> |<span data-ttu-id="62eb7-125">3600</span><span class="sxs-lookup"><span data-stu-id="62eb7-125">3600</span></span>  <br/> |<span data-ttu-id="62eb7-126">offentlig IP-adress för Azure Internet-Facing belastningsutjämnare (visas i kommandot **Write-Host** i föregående avsnitt)</span><span class="sxs-lookup"><span data-stu-id="62eb7-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="62eb7-127">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="62eb7-127">Here is an example:</span></span>
  
|<span data-ttu-id="62eb7-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="62eb7-128">**Name**</span></span>|<span data-ttu-id="62eb7-129">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="62eb7-129">**Type**</span></span>|<span data-ttu-id="62eb7-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="62eb7-130">**TTL**</span></span>|<span data-ttu-id="62eb7-131">**Värde**</span><span class="sxs-lookup"><span data-stu-id="62eb7-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62eb7-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="62eb7-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="62eb7-133">Kallas</span><span class="sxs-lookup"><span data-stu-id="62eb7-133">A</span></span>  <br/> |<span data-ttu-id="62eb7-134">3600</span><span class="sxs-lookup"><span data-stu-id="62eb7-134">3600</span></span>  <br/> |<span data-ttu-id="62eb7-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="62eb7-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="62eb7-136">Lägg sedan till en DNS-postadress i organisationens privata DNS-namnområde som matchar den interna belastningsutjämnaren för AD FS-servrarna (tabell I, item 4, värde Column)...</span><span class="sxs-lookup"><span data-stu-id="62eb7-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="62eb7-137">Skapa Web Application Proxy Server-virtuella datorer i Azure</span><span class="sxs-lookup"><span data-stu-id="62eb7-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="62eb7-138">Använd följande block med Azure PowerShell-kommandon för att skapa virtuella datorer för de två webbprogramproxy.</span><span class="sxs-lookup"><span data-stu-id="62eb7-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="62eb7-139">Observera att följande Azure PowerShell-kommando ställer in värden från följande tabeller:</span><span class="sxs-lookup"><span data-stu-id="62eb7-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="62eb7-140">Tabell M, för de virtuella datorerna</span><span class="sxs-lookup"><span data-stu-id="62eb7-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="62eb7-141">Tabell R för dina resurs grupper</span><span class="sxs-lookup"><span data-stu-id="62eb7-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="62eb7-142">Tabell V, för dina virtuella nätverks inställningar</span><span class="sxs-lookup"><span data-stu-id="62eb7-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="62eb7-143">Tabell S, för under nätverk</span><span class="sxs-lookup"><span data-stu-id="62eb7-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="62eb7-144">Tabell I, för statiska IP-adresser</span><span class="sxs-lookup"><span data-stu-id="62eb7-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="62eb7-145">Tabell A, för dina tillgänglighets uppsättningar</span><span class="sxs-lookup"><span data-stu-id="62eb7-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="62eb7-146">Kom ihåg att du har definierat tabell M i [steg 2: Konfigurera domän kontrol Lanterna](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) och tabellerna R, V, S, i och A i [steg 1: Konfigurera Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="62eb7-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="62eb7-147">När du har angett alla värden kör du det resulterande blocket vid kommando tolken i Azure PowerShell eller i PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="62eb7-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="62eb7-148">Eftersom de här virtuella datorerna är för ett intranät program är de inte tilldelad en offentlig IP-adress eller en DNS-domän namns etikett och är exponerad för Internet.</span><span class="sxs-lookup"><span data-stu-id="62eb7-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="62eb7-149">Det innebär att du inte kan ansluta till dem från Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="62eb7-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="62eb7-150">Alternativet **Anslut** är inte tillgängligt när du visar egenskaperna för den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="62eb7-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="62eb7-151">Använd anslutning till fjärr skrivbord eller ett annat fjärr skrivbord för att ansluta till den virtuella datorn via dess privata IP-adress eller intranät-DNS-namn och autentiseringsuppgifterna för det lokala administratörs kontot.</span><span class="sxs-lookup"><span data-stu-id="62eb7-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="62eb7-152">Här är konfigurationen som skapas när den här fasen har slutförts, med plats hållare för dator namn.</span><span class="sxs-lookup"><span data-stu-id="62eb7-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="62eb7-153">**Fas 4: Internet-belastningsutjämna och Webbprogramproxy för din höganvända federerad infrastruktur i Azure**</span><span class="sxs-lookup"><span data-stu-id="62eb7-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Fas 4 i den övergripande Microsoft 365-infrastrukturen för extern tillgänglighet i Azure med Webbprogramproxy-servrar](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="62eb7-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="62eb7-155">Next step</span></span>

<span data-ttu-id="62eb7-156">Använd [fas 5: Konfigurera federerad auktorisering för Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) för att fortsätta att konfigurera arbets belastningen.</span><span class="sxs-lookup"><span data-stu-id="62eb7-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62eb7-157">Se även</span><span class="sxs-lookup"><span data-stu-id="62eb7-157">See Also</span></span>

[<span data-ttu-id="62eb7-158">Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="62eb7-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="62eb7-159">Federerad identitet för din Microsoft 365-miljö</span><span class="sxs-lookup"><span data-stu-id="62eb7-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="62eb7-160">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="62eb7-160">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

