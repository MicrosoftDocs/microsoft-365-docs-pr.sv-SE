---
title: Mellanliggande federerad autentiseringsläge med hög tillgänglighet konfigurera Azure
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
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Sammanfattning: Konfigurera Microsoft Azure-infrastrukturen för att hantera federerad åtkomst med hög tillgänglighet för Microsoft 365.'
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332346"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="d0470-103">Mellanliggande federerad autentiseringsläge med hög tillgänglighet: Konfigurera Azure</span><span class="sxs-lookup"><span data-stu-id="d0470-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="d0470-104">I den här fasen skapar du resurs grupper, virtuella nätverk (VNet) och tillgänglighets uppsättningar i Azure som ska vara värd för de virtuella datorerna i steg 2, 3 och 4.</span><span class="sxs-lookup"><span data-stu-id="d0470-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="d0470-105">Du måste slutföra den här fasen innan du går vidare till [steg 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="d0470-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="d0470-106">Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="d0470-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="d0470-107">Azure måste tillhandahållas med dessa grundläggande komponenter:</span><span class="sxs-lookup"><span data-stu-id="d0470-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="d0470-108">Resurs grupper</span><span class="sxs-lookup"><span data-stu-id="d0470-108">Resource groups</span></span>
    
- <span data-ttu-id="d0470-109">Ett lokalt Azure-nätverk (VNet) med undernät för att vara värd för de virtuella Azure-datorerna</span><span class="sxs-lookup"><span data-stu-id="d0470-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="d0470-110">Nätverks säkerhets grupper för att utföra under näts isolering</span><span class="sxs-lookup"><span data-stu-id="d0470-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="d0470-111">Tillgänglighets uppsättningar</span><span class="sxs-lookup"><span data-stu-id="d0470-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="d0470-112">Konfigurera Azure-komponenter</span><span class="sxs-lookup"><span data-stu-id="d0470-112">Configure Azure components</span></span>

<span data-ttu-id="d0470-113">Innan du börjar konfigurera Azure-komponenter fyller du i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="d0470-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="d0470-114">För att hjälpa dig att konfigurera Azure kan du skriva ut det här avsnittet och skriva ner informationen eller kopiera det här avsnittet till ett dokument och fylla i det.</span><span class="sxs-lookup"><span data-stu-id="d0470-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="d0470-115">För inställningar för VNet fyller du i tabell V.</span><span class="sxs-lookup"><span data-stu-id="d0470-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="d0470-116">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-116">**Item**</span></span>|<span data-ttu-id="d0470-117">**Konfigurations inställning**</span><span class="sxs-lookup"><span data-stu-id="d0470-117">**Configuration setting**</span></span>|<span data-ttu-id="d0470-118">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d0470-118">**Description**</span></span>|<span data-ttu-id="d0470-119">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d0470-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0470-120">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-120">1.</span></span>  <br/> |<span data-ttu-id="d0470-121">VNet-namn</span><span class="sxs-lookup"><span data-stu-id="d0470-121">VNet name</span></span>  <br/> |<span data-ttu-id="d0470-122">Ett namn som ska kopplas till VNet (exempel FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="d0470-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-124">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-124">2.</span></span>  <br/> |<span data-ttu-id="d0470-125">VNet-plats</span><span class="sxs-lookup"><span data-stu-id="d0470-125">VNet location</span></span>  <br/> |<span data-ttu-id="d0470-126">Det regionala Azure-datacentret som kommer att innehålla det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="d0470-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-128">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-128">3.</span></span>  <br/> |<span data-ttu-id="d0470-129">IP-adress för VPN-enhet</span><span class="sxs-lookup"><span data-stu-id="d0470-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="d0470-130">Offentlig IPv4-adress för din VPN-enhets gränssnitt på Internet.</span><span class="sxs-lookup"><span data-stu-id="d0470-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-132">4.</span><span class="sxs-lookup"><span data-stu-id="d0470-132">4.</span></span>  <br/> |<span data-ttu-id="d0470-133">Virtuellt nätverk-adress utrymme</span><span class="sxs-lookup"><span data-stu-id="d0470-133">VNet address space</span></span>  <br/> |<span data-ttu-id="d0470-134">Adress utrymmet för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="d0470-134">The address space for the virtual network.</span></span> <span data-ttu-id="d0470-135">Arbeta med IT-avdelningen för att ta reda på det här adress utrymmet.</span><span class="sxs-lookup"><span data-stu-id="d0470-135">Work with your IT department to determine this address space.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-137">5.</span><span class="sxs-lookup"><span data-stu-id="d0470-137">5.</span></span>  <br/> |<span data-ttu-id="d0470-138">Delad IPsec-nycklar</span><span class="sxs-lookup"><span data-stu-id="d0470-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="d0470-139">En 32-tecken slumpmässig, alfanumerisk sträng som används för att autentisera båda sidor av VPN-anslutningen för webbplats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="d0470-139">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="d0470-140">Arbeta med din IT-eller säkerhets avdelning för att fastställa det här nyckelvärdet.</span><span class="sxs-lookup"><span data-stu-id="d0470-140">Work with your IT or security department to determine this key value.</span></span> <span data-ttu-id="d0470-141">Du kan också läsa [skapa en slumpmässig sträng för en förutdelad IPsec-produktnyckel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="d0470-141">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="d0470-143">**Tabell V: konfiguration för lokalt nätverk**</span><span class="sxs-lookup"><span data-stu-id="d0470-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="d0470-144">Fyll i tabell S efter under nätet för den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="d0470-144">Next, fill in Table S for the subnets of this solution.</span></span> <span data-ttu-id="d0470-145">Alla adress utrymmen bör vara i CIDR-format (Classless Interdomain Routing), som även kallas för nätverksprefix.</span><span class="sxs-lookup"><span data-stu-id="d0470-145">All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="d0470-146">Ett exempel är 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="d0470-146">An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="d0470-147">För de tre första under näten anger du ett namn och ett enskilt IP-adressutrymmet baserat på det virtuella nätverkets adress utrymme.</span><span class="sxs-lookup"><span data-stu-id="d0470-147">For the first three subnets, specify a name and a single IP address space based on the virtual network address space.</span></span> <span data-ttu-id="d0470-148">För gateway-undernätet bestämmer du det 27-bitars adress utrymmet (med en/27 prefixlängd) för Azure Gateway-under nätet med följande:</span><span class="sxs-lookup"><span data-stu-id="d0470-148">For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="d0470-149">Ställ in de variabla bitarna i det mellanliggande nätverkets adress utrymme till 1, upp till de bitar som används av Gateway-undernätet och ange sedan de återstående bitarna till 0.</span><span class="sxs-lookup"><span data-stu-id="d0470-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="d0470-150">Konvertera de resulterande bitarna till decimal och uttrycka det som ett adress utrymme med prefixlängden angiven till gateway-undernätets längd.</span><span class="sxs-lookup"><span data-stu-id="d0470-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="d0470-151">Se [adress utrymmes Kalkylatorn för Azure Gateway-undernät](address-space-calculator-for-azure-gateway-subnets.md) för ett PowerShell Command block-och C#-eller python-konsol program som utför den här beräkningen åt dig.</span><span class="sxs-lookup"><span data-stu-id="d0470-151">See [Address space calculator for Azure gateway subnets](address-space-calculator-for-azure-gateway-subnets.md) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="d0470-152">Arbeta med IT-avdelningen för att fastställa dessa adress utrymmen från det virtuella nätverkets adress utrymme.</span><span class="sxs-lookup"><span data-stu-id="d0470-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="d0470-153">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-153">**Item**</span></span>|<span data-ttu-id="d0470-154">**Namn på undernät**</span><span class="sxs-lookup"><span data-stu-id="d0470-154">**Subnet name**</span></span>|<span data-ttu-id="d0470-155">**Adress utrymme för undernät**</span><span class="sxs-lookup"><span data-stu-id="d0470-155">**Subnet address space**</span></span>|<span data-ttu-id="d0470-156">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="d0470-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0470-157">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-157">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-160">Det undernät som används av AD DS-domänkontrollanten (Active Directory Domain Services) och virtuella datorer för katalogpartition för katalog.</span><span class="sxs-lookup"><span data-stu-id="d0470-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="d0470-161">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-161">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-164">Under nätet som används av AD FS VM.</span><span class="sxs-lookup"><span data-stu-id="d0470-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="d0470-165">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-165">3.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-168">Under nätet som används av Webbprogramproxy för webb programmet.</span><span class="sxs-lookup"><span data-stu-id="d0470-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="d0470-169">4.</span><span class="sxs-lookup"><span data-stu-id="d0470-169">4.</span></span>  <br/> |<span data-ttu-id="d0470-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="d0470-170">GatewaySubnet</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-172">Under nätet som används av Azure Gateway VMs.</span><span class="sxs-lookup"><span data-stu-id="d0470-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="d0470-173">**Tabell S: undernät i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="d0470-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="d0470-174">Fyll i tabell I för de statiska IP-adresser som är tilldelade till virtuella datorer och belastnings Utjämnings instanser.</span><span class="sxs-lookup"><span data-stu-id="d0470-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="d0470-175">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-175">**Item**</span></span>|<span data-ttu-id="d0470-176">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="d0470-176">**Purpose**</span></span>|<span data-ttu-id="d0470-177">**IP-adress på under nätet**</span><span class="sxs-lookup"><span data-stu-id="d0470-177">**IP address on the subnet**</span></span>|<span data-ttu-id="d0470-178">**Värde**</span><span class="sxs-lookup"><span data-stu-id="d0470-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0470-179">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-179">1.</span></span>  <br/> |<span data-ttu-id="d0470-180">Statisk IP-adress för den första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="d0470-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="d0470-181">Den fjärde möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 1 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-183">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-183">2.</span></span>  <br/> |<span data-ttu-id="d0470-184">Den andra domänkontrollantens statiska IP-adress</span><span class="sxs-lookup"><span data-stu-id="d0470-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="d0470-185">Den femte möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 1 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-187">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-187">3.</span></span>  <br/> |<span data-ttu-id="d0470-188">Statisk IP-adress för katalogpartitionen</span><span class="sxs-lookup"><span data-stu-id="d0470-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="d0470-189">Den sjätte möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 1 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-191">4.</span><span class="sxs-lookup"><span data-stu-id="d0470-191">4.</span></span>  <br/> |<span data-ttu-id="d0470-192">Statisk IP-adress för intern belastningsutjämnaren för AD FS-servrarna</span><span class="sxs-lookup"><span data-stu-id="d0470-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="d0470-193">Den fjärde möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 2 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-195">5.</span><span class="sxs-lookup"><span data-stu-id="d0470-195">5.</span></span>  <br/> |<span data-ttu-id="d0470-196">Statisk IP-adress för den första AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="d0470-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="d0470-197">Den femte möjliga IP-adressen för det under nätets adress utrymme som definieras i punkt 2 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-199">18.6.</span><span class="sxs-lookup"><span data-stu-id="d0470-199">6.</span></span>  <br/> |<span data-ttu-id="d0470-200">Statisk IP-adress för den andra AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="d0470-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="d0470-201">Den sjätte möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 2 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-203">borttagning.</span><span class="sxs-lookup"><span data-stu-id="d0470-203">7.</span></span>  <br/> |<span data-ttu-id="d0470-204">Statisk IP-adress för den första Web Application-proxyservern</span><span class="sxs-lookup"><span data-stu-id="d0470-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="d0470-205">Den fjärde möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 3 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-207">8.2.</span><span class="sxs-lookup"><span data-stu-id="d0470-207">8.</span></span>  <br/> |<span data-ttu-id="d0470-208">Statisk IP-adress för den andra Web Application Proxy-servern</span><span class="sxs-lookup"><span data-stu-id="d0470-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="d0470-209">Den femte möjliga IP-adressen för adress utrymmet för under nätet som definieras i punkt 3 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="d0470-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="d0470-211">**Tabell I: statiska IP-adresser i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="d0470-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="d0470-212">För två DNS-servrar (Domain Name System) i det lokala nätverk som du vill använda när du först konfigurerar domän kontrol Lanterna i det virtuella nätverket fyller du i tabell D. arbeta med IT-avdelningen för att fastställa den här listan.</span><span class="sxs-lookup"><span data-stu-id="d0470-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="d0470-213">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-213">**Item**</span></span>|<span data-ttu-id="d0470-214">**Eget namn på DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="d0470-214">**DNS server friendly name**</span></span>|<span data-ttu-id="d0470-215">**IP-adress för DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="d0470-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0470-216">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-216">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-219">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-219">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="d0470-222">**Tabell D: lokala DNS-servrar**</span><span class="sxs-lookup"><span data-stu-id="d0470-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="d0470-223">Om du vill dirigera paket från det lokala nätverket till organisationens nätverk via VPN-anslutningen för webbplats-till-plats måste du konfigurera det virtuella nätverket med ett lokalt nätverk som har en lista med adress utrymmen (i CIDR-notation) för alla tillgängliga platser i organisationens lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="d0470-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="d0470-224">Listan med adress utrymmen som definierar ditt lokala nätverk måste vara unikt och får inte överlappa det adress utrymme som används för andra virtuella nätverk eller andra lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="d0470-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="d0470-225">För uppsättningen med lokala nätverks adress utrymmen fyller du i tabell L. Lägg märke till att tre tomma poster visas, men att du oftast behöver mer.</span><span class="sxs-lookup"><span data-stu-id="d0470-225">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="d0470-226">Arbeta med IT-avdelningen för att fastställa den här listan med adress utrymmen.</span><span class="sxs-lookup"><span data-stu-id="d0470-226">Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="d0470-227">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-227">**Item**</span></span>|<span data-ttu-id="d0470-228">**Lokala nätverks adress utrymmet**</span><span class="sxs-lookup"><span data-stu-id="d0470-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d0470-229">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-229">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-231">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-231">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-233">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-233">3.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="d0470-235">**Tabell L: adressprefix för det lokala nätverket**</span><span class="sxs-lookup"><span data-stu-id="d0470-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="d0470-236">Nu kan du börja bygga Azure-infrastrukturen för att hantera din federerad lösenordsautentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0470-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0470-237">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0470-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="d0470-238">Se [komma igång med Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="d0470-238">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="d0470-239">Starta först en Azure PowerShell-kommandotolk och logga in på ditt konto.</span><span class="sxs-lookup"><span data-stu-id="d0470-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="d0470-240">Använd den här [arbets boken för Microsoft Excel-konfiguration](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)om du vill skapa PowerShell-Kommandotolken som är klara att köra.</span><span class="sxs-lookup"><span data-stu-id="d0470-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="d0470-241">Hämta ditt prenumerationsnamn med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="d0470-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="d0470-242">Använd det här kommandot i stället för äldre versioner av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0470-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="d0470-243">Ange din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d0470-243">Set your Azure subscription.</span></span> <span data-ttu-id="d0470-244">Ersätt allt inom citattecknen, inklusive \< and >-tecknen med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="d0470-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="d0470-245">Skapa sedan de nya resurs grupperna.</span><span class="sxs-lookup"><span data-stu-id="d0470-245">Next, create the new resource groups.</span></span> <span data-ttu-id="d0470-246">Använd det här kommandot för att ange en lista över befintliga resurs grupper.</span><span class="sxs-lookup"><span data-stu-id="d0470-246">To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="d0470-247">Fyll i följande tabell efter uppsättningen med unika resurs grupps namn.</span><span class="sxs-lookup"><span data-stu-id="d0470-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="d0470-248">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-248">**Item**</span></span>|<span data-ttu-id="d0470-249">**Resurs grupps namn**</span><span class="sxs-lookup"><span data-stu-id="d0470-249">**Resource group name**</span></span>|<span data-ttu-id="d0470-250">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="d0470-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0470-251">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-251">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-253">Domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="d0470-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="d0470-254">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-254">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-256">AD FS-servrar</span><span class="sxs-lookup"><span data-stu-id="d0470-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="d0470-257">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-257">3.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-259">Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="d0470-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="d0470-260">4.</span><span class="sxs-lookup"><span data-stu-id="d0470-260">4.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="d0470-262">Infrastruktur element</span><span class="sxs-lookup"><span data-stu-id="d0470-262">Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id="d0470-263">**Tabell R: resurs grupper**</span><span class="sxs-lookup"><span data-stu-id="d0470-263">**Table R: Resource groups**</span></span>
  
<span data-ttu-id="d0470-264">Skapa dina nya resurs grupper med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="d0470-264">Create your new resource groups with these commands.</span></span>
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="d0470-265">Sedan skapar du ett Azure Virtual Network och dess undernät.</span><span class="sxs-lookup"><span data-stu-id="d0470-265">Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="d0470-266">Sedan skapar du nätverks säkerhets grupper för varje undernät som har virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="d0470-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="d0470-267">Om du vill utföra under näts isolering kan du lägga till regler för de specifika trafik typer som tillåts eller nekas till nätverks säkerhets gruppen för ett undernät.</span><span class="sxs-lookup"><span data-stu-id="d0470-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="d0470-268">Använd sedan dessa kommandon för att skapa gatewayen för VPN-anslutningen för webbplats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="d0470-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="d0470-269">Federerad inloggningsautentisering för enskilda användare förlitar sig inte på lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="d0470-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="d0470-270">Men om den här VPN-anslutningen för webbplats-till-plats blir otillgänglig kommer domän kontrol Lanterna i VNet inte att få uppdateringar för användar konton och grupper som görs i lokala Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="d0470-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="d0470-271">För att säkerställa att detta inte sker kan du konfigurera hög tillgänglighet för din VPN-anslutning för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="d0470-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="d0470-272">Mer information finns i [lättillgängliga kors lokala och VNET-till-VNet-anslutningar](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="d0470-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="d0470-273">Ange sedan den offentliga IPv4-adressen för Azure VPN gateway för ditt virtuella nätverk från visningen av det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d0470-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="d0470-274">Konfigurera sedan din lokala VPN-enhet för att ansluta till Azure VPN gateway.</span><span class="sxs-lookup"><span data-stu-id="d0470-274">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="d0470-275">Mer information finns i [Konfigurera din VPN-enhet](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="d0470-275">For more information, see [Configure your VPN device](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="d0470-276">För att konfigurera den lokala VPN-enheten behöver du följande:</span><span class="sxs-lookup"><span data-stu-id="d0470-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="d0470-277">Offentlig IPv4-adress för Azure VPN gateway.</span><span class="sxs-lookup"><span data-stu-id="d0470-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="d0470-278">Den fördelade IPsec-länken för VPN för webbplats-till-plats (tabell V-post 5-värde-kolumnen).</span><span class="sxs-lookup"><span data-stu-id="d0470-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="d0470-279">Kontrol lera sedan att adress utrymmet för det virtuella nätverket kan nås från det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="d0470-279">Next, ensure that the address space of the virtual network is reachable from your on-premises network.</span></span> <span data-ttu-id="d0470-280">Detta görs vanligt vis genom att lägga till en väg som motsvarar det virtuella nätverks adress utrymmet till din VPN-enhet och sedan annonseras till resten av infrastrukturen för routning i organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="d0470-280">This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network.</span></span> <span data-ttu-id="d0470-281">Arbeta med IT-avdelningen för att ta reda på hur det går till.</span><span class="sxs-lookup"><span data-stu-id="d0470-281">Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="d0470-282">Definiera sedan namnen på tre tillgänglighets uppsättningar.</span><span class="sxs-lookup"><span data-stu-id="d0470-282">Next, define the names of three availability sets.</span></span> <span data-ttu-id="d0470-283">Fyll i tabell A.</span><span class="sxs-lookup"><span data-stu-id="d0470-283">Fill out Table A.</span></span> 
  
|<span data-ttu-id="d0470-284">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="d0470-284">**Item**</span></span>|<span data-ttu-id="d0470-285">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="d0470-285">**Purpose**</span></span>|<span data-ttu-id="d0470-286">**Namn på tillgänglighets uppsättning**</span><span class="sxs-lookup"><span data-stu-id="d0470-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0470-287">1.</span><span class="sxs-lookup"><span data-stu-id="d0470-287">1.</span></span>  <br/> |<span data-ttu-id="d0470-288">Domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="d0470-288">Domain controllers</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-290">2.</span><span class="sxs-lookup"><span data-stu-id="d0470-290">2.</span></span>  <br/> |<span data-ttu-id="d0470-291">AD FS-servrar</span><span class="sxs-lookup"><span data-stu-id="d0470-291">AD FS servers</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="d0470-293">3.</span><span class="sxs-lookup"><span data-stu-id="d0470-293">3.</span></span>  <br/> |<span data-ttu-id="d0470-294">Webbprogramproxy</span><span class="sxs-lookup"><span data-stu-id="d0470-294">Web application proxy servers</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="d0470-296">**Tabell A: tillgänglighets uppsättningar**</span><span class="sxs-lookup"><span data-stu-id="d0470-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="d0470-297">Du behöver dessa namn när du skapar de virtuella datorerna i steg 2, 3 och 4.</span><span class="sxs-lookup"><span data-stu-id="d0470-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="d0470-298">Skapa nya tillgänglighets uppsättningar med de här Azure PowerShell-kommandona.</span><span class="sxs-lookup"><span data-stu-id="d0470-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="d0470-299">Det här är konfigurationen som skapas när den här fasen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d0470-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="d0470-300">**Fas 1: Azure-infrastrukturen för extern tillgänglighets-federerad inloggningsautentisering för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="d0470-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fas 1 av Microsoft 365-federerad verifierad hög tillgänglighet i Azure med Azure Infrastructure](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="d0470-302">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d0470-302">Next step</span></span>

<span data-ttu-id="d0470-303">Använda [fas 2: Konfigurera domän kontrol Lanterna](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) för att fortsätta med konfigurationen av denna arbets belastning.</span><span class="sxs-lookup"><span data-stu-id="d0470-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0470-304">Se även</span><span class="sxs-lookup"><span data-stu-id="d0470-304">See Also</span></span>

[<span data-ttu-id="d0470-305">Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="d0470-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="d0470-306">Federerad identitet för din Microsoft 365-miljö</span><span class="sxs-lookup"><span data-stu-id="d0470-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="d0470-307">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="d0470-307">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="d0470-308">Förstå Microsoft 365-identitet och Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0470-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)


