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
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="90003-103">Fas 4 för hög tillgänglighet för federerad autentisering: Konfigurera proxyprogram för webbprogram</span><span class="sxs-lookup"><span data-stu-id="90003-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="90003-104">I den här fasen av distributionen av hög tillgänglighet för Microsoft 365-federerad autentisering i Azure-infrastrukturtjänster skapar du en intern belastningsutjämnare och två AD FS-servrar.</span><span class="sxs-lookup"><span data-stu-id="90003-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="90003-105">Du måste slutföra den här fasen innan du går vidare [till steg 5: Konfigurera federerad autentisering för Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)</span><span class="sxs-lookup"><span data-stu-id="90003-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="90003-106">Se [Distribuera hög tillgänglighet federerad autentisering för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="90003-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="90003-107">Skapa belastningsutjämaren mot Internet i Azure</span><span class="sxs-lookup"><span data-stu-id="90003-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="90003-108">Du måste skapa en belastningsutjämnare på Internet så att Azure distribuerar inkommande klientautentiseringstrafik från Internet jämnt mellan de två proxyservrarna för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="90003-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90003-109">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90003-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="90003-110">Se [Komma igång med Azure PowerShell.](/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="90003-110">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="90003-111">När du har angett värden för plats- och resursgrupper kör du det resulterande blocket i Azure PowerShell-kommandotolken eller i PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="90003-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="90003-112">Använd den här arbetsboken för Microsoft Excel-konfiguration om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på [dina egna inställningar.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="90003-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="90003-113">Om du vill visa den offentliga IP-adressen som är kopplad till din Internet-belastningsutjämnare kör du följande kommandon i Azure PowerShell-kommandotolken på den lokala datorn:</span><span class="sxs-lookup"><span data-stu-id="90003-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="90003-114">Bestäm FQDN för federationstjänsten och skapa DNS-poster</span><span class="sxs-lookup"><span data-stu-id="90003-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="90003-115">Du måste ta reda på DNS-namnet för att kunna identifiera federationstjänstens namn på Internet.</span><span class="sxs-lookup"><span data-stu-id="90003-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="90003-116">Azure AD Connect konfigurerar Microsoft 365 med det här namnet i fas 5, som blir en del av URL-adressen som Microsoft 365 skickar till anslutande klienter för att få en säkerhetstoken.</span><span class="sxs-lookup"><span data-stu-id="90003-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="90003-117">Ett exempel är fs.contoso.com (fs står för federationstjänst).</span><span class="sxs-lookup"><span data-stu-id="90003-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="90003-118">När du har federationstjänstens FDQN skapar du en offentlig DNS-domän En post för federationstjänstens FDQN som löser den offentliga IP-adressen för Azure Internet-belastningsutjämnaren.</span><span class="sxs-lookup"><span data-stu-id="90003-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="90003-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="90003-119">**Name**</span></span>|<span data-ttu-id="90003-120">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="90003-120">**Type**</span></span>|<span data-ttu-id="90003-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90003-121">**TTL**</span></span>|<span data-ttu-id="90003-122">**Värde**</span><span class="sxs-lookup"><span data-stu-id="90003-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90003-123">federationstjänst FDQN</span><span class="sxs-lookup"><span data-stu-id="90003-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="90003-124">A</span><span class="sxs-lookup"><span data-stu-id="90003-124">A</span></span>  <br/> |<span data-ttu-id="90003-125">3600</span><span class="sxs-lookup"><span data-stu-id="90003-125">3600</span></span>  <br/> |<span data-ttu-id="90003-126">offentlig IP-adress för Azure-belastningsutjämaren (visas av **kommandot Write-Host** i föregående avsnitt)</span><span class="sxs-lookup"><span data-stu-id="90003-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="90003-127">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="90003-127">Here is an example:</span></span>
  
|<span data-ttu-id="90003-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="90003-128">**Name**</span></span>|<span data-ttu-id="90003-129">**Type (typ)**</span><span class="sxs-lookup"><span data-stu-id="90003-129">**Type**</span></span>|<span data-ttu-id="90003-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90003-130">**TTL**</span></span>|<span data-ttu-id="90003-131">**Värde**</span><span class="sxs-lookup"><span data-stu-id="90003-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90003-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90003-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="90003-133">A</span><span class="sxs-lookup"><span data-stu-id="90003-133">A</span></span>  <br/> |<span data-ttu-id="90003-134">3600</span><span class="sxs-lookup"><span data-stu-id="90003-134">3600</span></span>  <br/> |<span data-ttu-id="90003-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="90003-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="90003-136">Lägg sedan till en DNS-adresspost i organisationens privata DNS-namnområde som löser federationstjänstens FQDN till den privata IP-adressen som tilldelats den interna belastningsutjämaren för AD FS-servrarna (tabell I, objekt 4, värdekolumnen).</span><span class="sxs-lookup"><span data-stu-id="90003-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="90003-137">Skapa webbprogramproxyserverns virtuella datorer i Azure</span><span class="sxs-lookup"><span data-stu-id="90003-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="90003-138">Använd följande block med Azure PowerShell-kommandon för att skapa virtuella datorer för de två proxyservrarna för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="90003-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="90003-139">Observera att följande Azure PowerShell-kommandouppsättningar använder värden från följande tabeller:</span><span class="sxs-lookup"><span data-stu-id="90003-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="90003-140">Tabell M, för virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="90003-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="90003-141">Tabell R, för resursgrupper</span><span class="sxs-lookup"><span data-stu-id="90003-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="90003-142">Tabell V, för dina virtuella nätverksinställningar</span><span class="sxs-lookup"><span data-stu-id="90003-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="90003-143">Tabell S, för dina undernät</span><span class="sxs-lookup"><span data-stu-id="90003-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="90003-144">Tabell I, för statiska IP-adresser</span><span class="sxs-lookup"><span data-stu-id="90003-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="90003-145">Tabell A, för dina tillgänglighetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="90003-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="90003-146">Kom ihåg att du definierade Tabell M i fas [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Konfigurera domänkontrollanter och tabell R, V, S, I och A i [fas 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="90003-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="90003-147">När du har angett alla värden kör du det resulterande blocket i Azure PowerShell-kommandotolken eller i PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="90003-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="90003-148">Eftersom dessa virtuella datorer är för ett intranätprogram, tilldelas de inte en offentlig IP-adress eller en DNS-domännamnsetikett och exponeras för Internet.</span><span class="sxs-lookup"><span data-stu-id="90003-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="90003-149">Det innebär dock också att du inte kan ansluta till dem från Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="90003-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="90003-150">Alternativet **Anslut** är inte tillgängligt när du visar egenskaperna för den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="90003-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="90003-151">Använd Fjärrskrivbordanslutningstillbehör eller ett annat Fjärrskrivbord-verktyg för att ansluta till den virtuella datorn med dess privata IP-adress eller DNS-namn på intranätet och det lokala administratörskontots autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="90003-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="90003-152">Här är konfigurationen som är ett resultat av att den här fasen slutförts, med platshållardatornamn.</span><span class="sxs-lookup"><span data-stu-id="90003-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="90003-153">**Fas 4: Proxyservrarna för internetbaserad belastningsutjämning och webbprogram för din hög tillgänglighetsinfrastruktur för federerad autentisering i Azure**</span><span class="sxs-lookup"><span data-stu-id="90003-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Fas 4 av Hög tillgänglighet : Microsoft 365-infrastruktur för federerad autentisering i Azure med proxyservrarna för webbprogram](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="90003-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="90003-155">Next step</span></span>

<span data-ttu-id="90003-156">Använd [fas 5: Konfigurera federerad autentisering för Microsoft 365 för att](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) fortsätta konfigurera arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="90003-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90003-157">Se även</span><span class="sxs-lookup"><span data-stu-id="90003-157">See Also</span></span>

[<span data-ttu-id="90003-158">Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="90003-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="90003-159">Federerad identitet för din Utvecklings-/testmiljö för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90003-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="90003-160">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="90003-160">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)