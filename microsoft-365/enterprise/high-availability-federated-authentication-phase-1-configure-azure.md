---
title: Hög tillgänglighet federerad autentisering Fas 1 Konfigurera Azure
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
description: 'Sammanfattning: Konfigurera Microsoft Azure-infrastrukturen för federerad autentisering med hög tillgänglighet för Microsoft 365.'
ms.openlocfilehash: 7f9a935648fedd2c6235c443f7398f97c0a06e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929114"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="58d94-103">Fas 1 med hög tillgänglighet för federerad autentisering: Konfigurera Azure</span><span class="sxs-lookup"><span data-stu-id="58d94-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="58d94-104">I den här fasen skapar du resursgrupper, virtuellt nätverk (VNet) och tillgänglighetsuppsättningar i Azure som ska vara värd för virtuella datorer i fas 2, 3 och 4.</span><span class="sxs-lookup"><span data-stu-id="58d94-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="58d94-105">Du måste slutföra den här fasen innan du går vidare [till fas 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="58d94-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="58d94-106">Se [Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="58d94-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="58d94-107">Azure måste tillhandahållas med följande grundläggande komponenter:</span><span class="sxs-lookup"><span data-stu-id="58d94-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="58d94-108">Resursgrupper</span><span class="sxs-lookup"><span data-stu-id="58d94-108">Resource groups</span></span>
    
- <span data-ttu-id="58d94-109">Ett virtuellt Azure-nätverk (VNet) på plats med undernät som värd för virtuella Azure-datorer</span><span class="sxs-lookup"><span data-stu-id="58d94-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="58d94-110">Nätverkssäkerhetsgrupper för att utföra undernätsisolering</span><span class="sxs-lookup"><span data-stu-id="58d94-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="58d94-111">Tillgänglighetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="58d94-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="58d94-112">Konfigurera Azure-komponenter</span><span class="sxs-lookup"><span data-stu-id="58d94-112">Configure Azure components</span></span>

<span data-ttu-id="58d94-113">Innan du börjar konfigurera Azure-komponenter fyller du i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="58d94-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="58d94-114">Skriv ut det här avsnittet och skriv ned den information som behövs eller kopiera avsnittet till ett dokument och fyll i det som behövs för att hjälpa dig med procedurerna för konfiguration av Azure.</span><span class="sxs-lookup"><span data-stu-id="58d94-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="58d94-115">För inställningarna för VNet fyller du i Tabell V.</span><span class="sxs-lookup"><span data-stu-id="58d94-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="58d94-116">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-116">**Item**</span></span>|<span data-ttu-id="58d94-117">**Konfigurationsinställning**</span><span class="sxs-lookup"><span data-stu-id="58d94-117">**Configuration setting**</span></span>|<span data-ttu-id="58d94-118">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="58d94-118">**Description**</span></span>|<span data-ttu-id="58d94-119">**Värde**</span><span class="sxs-lookup"><span data-stu-id="58d94-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58d94-120">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-120">1.</span></span>  <br/> |<span data-ttu-id="58d94-121">VNet-namn</span><span class="sxs-lookup"><span data-stu-id="58d94-121">VNet name</span></span>  <br/> |<span data-ttu-id="58d94-122">Ett namn att tilldela till VNet (exempel FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="58d94-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-124">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-124">2.</span></span>  <br/> |<span data-ttu-id="58d94-125">VNet-plats</span><span class="sxs-lookup"><span data-stu-id="58d94-125">VNet location</span></span>  <br/> |<span data-ttu-id="58d94-126">Det regionala Azure-datacenter som kommer att innehålla det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="58d94-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-128">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-128">3.</span></span>  <br/> |<span data-ttu-id="58d94-129">IP-adress för VPN-enhet</span><span class="sxs-lookup"><span data-stu-id="58d94-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="58d94-130">Den offentliga IPv4-adressen till VPN-enhetens gränssnitt på Internet.</span><span class="sxs-lookup"><span data-stu-id="58d94-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-132">4.</span><span class="sxs-lookup"><span data-stu-id="58d94-132">4.</span></span>  <br/> |<span data-ttu-id="58d94-133">VNet-adressutrymme</span><span class="sxs-lookup"><span data-stu-id="58d94-133">VNet address space</span></span>  <br/> |<span data-ttu-id="58d94-134">Adressutrymmet för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="58d94-134">The address space for the virtual network.</span></span> <span data-ttu-id="58d94-135">Ta reda på det här adressutrymmet tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-135">Work with your IT department to determine this address space.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-137">5.</span><span class="sxs-lookup"><span data-stu-id="58d94-137">5.</span></span>  <br/> |<span data-ttu-id="58d94-138">Delad IPsec-nyckel</span><span class="sxs-lookup"><span data-stu-id="58d94-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="58d94-139">En slumpmässig alfanumerisk sträng med 32 tecken som används för att autentisera båda sidorna av VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="58d94-139">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="58d94-140">Arbeta med IT- eller säkerhetsavdelningen för att fastställa det här nyckelvärdet.</span><span class="sxs-lookup"><span data-stu-id="58d94-140">Work with your IT or security department to determine this key value.</span></span> <span data-ttu-id="58d94-141">Alternativt kan du gå till [Skapa en slumpmässig sträng för en IPsec-fördelsnyckel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="58d94-141">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="58d94-143">**Tabell V: Konfiguration av virtuellt nätverk på flera platser**</span><span class="sxs-lookup"><span data-stu-id="58d94-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="58d94-144">Fyll sedan i Tabell S för undernäten för den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-144">Next, fill in Table S for the subnets of this solution.</span></span> <span data-ttu-id="58d94-145">Alla adress blanksteg ska vara i CIDR-format (Classless Interdomain Routing), även kallat nätverksprefixformat.</span><span class="sxs-lookup"><span data-stu-id="58d94-145">All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="58d94-146">Ett exempel är 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="58d94-146">An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="58d94-147">För de första tre undernäten anger du ett namn och ett enda IP-adressutrymme baserat på det virtuella nätverksadressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="58d94-147">For the first three subnets, specify a name and a single IP address space based on the virtual network address space.</span></span> <span data-ttu-id="58d94-148">För gatewayundernätet bestämmer du 27-bitarsadressutrymmet (med prefixlängden /27) för Azure Gateway-undernätet med följande:</span><span class="sxs-lookup"><span data-stu-id="58d94-148">For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="58d94-149">Ange de variabla bitarna i adressutrymmet för VNet till 1, upp till de bitar som används av gatewayundernätet, och ange sedan 0 för återstående bitar.</span><span class="sxs-lookup"><span data-stu-id="58d94-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="58d94-150">Konvertera de resulterande bitarna till decimalt och uttryck det som ett adressutrymme med prefixlängden inställd på storleken på gatewayundernätet.</span><span class="sxs-lookup"><span data-stu-id="58d94-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="58d94-151">Se [Adressutrymmeskalkylatorn för Azure Gateway-undernät](address-space-calculator-for-azure-gateway-subnets.md) för ett PowerShell-kommandoblock och C# eller Python-konsolprogram som utför den här beräkningen åt dig.</span><span class="sxs-lookup"><span data-stu-id="58d94-151">See [Address space calculator for Azure gateway subnets](address-space-calculator-for-azure-gateway-subnets.md) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="58d94-152">Arbeta med IT-avdelningen för att fastställa dessa adressutrymmen från det virtuella nätverksadressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="58d94-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="58d94-153">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-153">**Item**</span></span>|<span data-ttu-id="58d94-154">**Undernätsnamn**</span><span class="sxs-lookup"><span data-stu-id="58d94-154">**Subnet name**</span></span>|<span data-ttu-id="58d94-155">**Adressutrymme för undernät**</span><span class="sxs-lookup"><span data-stu-id="58d94-155">**Subnet address space**</span></span>|<span data-ttu-id="58d94-156">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="58d94-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58d94-157">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-157">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-160">Undernätet som används av AD DS-domänkontrollanten (Active Directory Domain Services) och katalogsynkroniseringsserverns virtuella maskiner (VMs).</span><span class="sxs-lookup"><span data-stu-id="58d94-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="58d94-161">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-161">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-164">Undernätet som används av AD FS VMs.</span><span class="sxs-lookup"><span data-stu-id="58d94-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="58d94-165">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-165">3.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-168">Undernätet som används av virtuella proxyservrar för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="58d94-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="58d94-169">4.</span><span class="sxs-lookup"><span data-stu-id="58d94-169">4.</span></span>  <br/> |<span data-ttu-id="58d94-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="58d94-170">GatewaySubnet</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-172">Undernätet som används av virtuella maskiner för Azure Gateway.</span><span class="sxs-lookup"><span data-stu-id="58d94-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="58d94-173">**Tabell S: Undernät i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="58d94-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="58d94-174">Fyll sedan i tabell I för de statiska IP-adresserna som tilldelats virtuella maskiner och belastningsutjämningsinstanser.</span><span class="sxs-lookup"><span data-stu-id="58d94-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="58d94-175">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-175">**Item**</span></span>|<span data-ttu-id="58d94-176">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="58d94-176">**Purpose**</span></span>|<span data-ttu-id="58d94-177">**IP-adress i undernätet**</span><span class="sxs-lookup"><span data-stu-id="58d94-177">**IP address on the subnet**</span></span>|<span data-ttu-id="58d94-178">**Värde**</span><span class="sxs-lookup"><span data-stu-id="58d94-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58d94-179">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-179">1.</span></span>  <br/> |<span data-ttu-id="58d94-180">Statisk IP-adress för den första domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="58d94-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="58d94-181">Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 1 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-183">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-183">2.</span></span>  <br/> |<span data-ttu-id="58d94-184">Statisk IP-adress för den andra domänkontrollanten</span><span class="sxs-lookup"><span data-stu-id="58d94-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="58d94-185">Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 1 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-187">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-187">3.</span></span>  <br/> |<span data-ttu-id="58d94-188">Statisk IP-adress för katalogsynkroniseringsservern</span><span class="sxs-lookup"><span data-stu-id="58d94-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="58d94-189">Den sjätte möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 1 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-191">4.</span><span class="sxs-lookup"><span data-stu-id="58d94-191">4.</span></span>  <br/> |<span data-ttu-id="58d94-192">Statisk IP-adress för den interna belastningsutjämaren för AD FS-servrarna</span><span class="sxs-lookup"><span data-stu-id="58d94-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="58d94-193">Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 2 i tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-195">5.</span><span class="sxs-lookup"><span data-stu-id="58d94-195">5.</span></span>  <br/> |<span data-ttu-id="58d94-196">Statisk IP-adress för den första AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="58d94-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="58d94-197">Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 2 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-199">6.</span><span class="sxs-lookup"><span data-stu-id="58d94-199">6.</span></span>  <br/> |<span data-ttu-id="58d94-200">Statisk IP-adress för den andra AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="58d94-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="58d94-201">Den sjätte möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 2 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-203">7.</span><span class="sxs-lookup"><span data-stu-id="58d94-203">7.</span></span>  <br/> |<span data-ttu-id="58d94-204">Statisk IP-adress för den första proxyservern för webbprogrammet</span><span class="sxs-lookup"><span data-stu-id="58d94-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="58d94-205">Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 3 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-207">8.</span><span class="sxs-lookup"><span data-stu-id="58d94-207">8.</span></span>  <br/> |<span data-ttu-id="58d94-208">Statisk IP-adress för den andra webbprogramproxyservern</span><span class="sxs-lookup"><span data-stu-id="58d94-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="58d94-209">Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 3 i Tabell S.</span><span class="sxs-lookup"><span data-stu-id="58d94-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="58d94-211">**Tabell I: Statiska IP-adresser i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="58d94-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="58d94-212">För två DNS-servrar (Domain Name System) i det lokala nätverket som du vill använda när du först bestäm om domänkontrollanterna i det virtuella nätverket fyller du i Tabell D. Ta reda på listan tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="58d94-213">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-213">**Item**</span></span>|<span data-ttu-id="58d94-214">**Eget namn för DNS-server**</span><span class="sxs-lookup"><span data-stu-id="58d94-214">**DNS server friendly name**</span></span>|<span data-ttu-id="58d94-215">**IP-adress för DNS-server**</span><span class="sxs-lookup"><span data-stu-id="58d94-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58d94-216">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-216">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-219">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-219">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="58d94-222">**Tabell D: Lokala DNS-servrar**</span><span class="sxs-lookup"><span data-stu-id="58d94-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="58d94-223">Om du vill dirigera paket från det lokala nätverket till organisationens nätverk via VPN-anslutningen mellan webbplatser måste du konfigurera det virtuella nätverket med ett lokalt nätverk som har en lista över adressplatserna (i CIDR-notation) för alla platser som kan nås i organisationens lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="58d94-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="58d94-224">Listan med adressutrymmen som definierar ditt lokala nätverk måste vara unik och får inte överlappa det adressutrymme som används för andra virtuella nätverk eller andra lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="58d94-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="58d94-225">För de lokala nätverksadressutrymmena fyller du i Tabell L. Observera att tre tomma poster visas, men du behöver vanligtvis mer.</span><span class="sxs-lookup"><span data-stu-id="58d94-225">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="58d94-226">Ta reda på listan med adressutrymmen tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-226">Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="58d94-227">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-227">**Item**</span></span>|<span data-ttu-id="58d94-228">**Lokalt nätverksadressutrymme**</span><span class="sxs-lookup"><span data-stu-id="58d94-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58d94-229">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-229">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-231">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-231">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-233">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-233">3.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="58d94-235">**Tabell L: Adressprefix för det lokala nätverket**</span><span class="sxs-lookup"><span data-stu-id="58d94-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="58d94-236">Nu börjar vi bygga Azure-infrastrukturen för din externa autentisering för att Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58d94-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58d94-237">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58d94-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="58d94-238">Se [Komma igång med Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="58d94-238">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="58d94-239">Börja med att Azure PowerShell och logga in på ditt konto.</span><span class="sxs-lookup"><span data-stu-id="58d94-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="58d94-240">Om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på dina anpassade inställningar använder du den [här Microsoft Excel konfigurationsarbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="58d94-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="58d94-241">Hämta ditt prenumerationsnamn med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="58d94-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="58d94-242">För äldre versioner av Azure PowerShell ska du använda det här kommandot i stället.</span><span class="sxs-lookup"><span data-stu-id="58d94-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="58d94-243">Ange din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="58d94-243">Set your Azure subscription.</span></span> <span data-ttu-id="58d94-244">Ersätt allt inom citattecknen, inklusive \< and >-tecknen med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="58d94-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="58d94-245">Skapa sedan de nya resursgrupperna.</span><span class="sxs-lookup"><span data-stu-id="58d94-245">Next, create the new resource groups.</span></span> <span data-ttu-id="58d94-246">Om du vill ta reda på en unik uppsättning namn på resursgrupper använder du det här kommandot för att lista de befintliga resursgrupperna.</span><span class="sxs-lookup"><span data-stu-id="58d94-246">To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="58d94-247">Fyll i följande tabell för uppsättningen unika resursgruppnamn.</span><span class="sxs-lookup"><span data-stu-id="58d94-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="58d94-248">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-248">**Item**</span></span>|<span data-ttu-id="58d94-249">**Resursgruppnamn**</span><span class="sxs-lookup"><span data-stu-id="58d94-249">**Resource group name**</span></span>|<span data-ttu-id="58d94-250">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="58d94-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58d94-251">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-251">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-253">Domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="58d94-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="58d94-254">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-254">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-256">AD FS-servrar</span><span class="sxs-lookup"><span data-stu-id="58d94-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="58d94-257">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-257">3.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-259">Proxyservrar för webbprogram</span><span class="sxs-lookup"><span data-stu-id="58d94-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="58d94-260">4.</span><span class="sxs-lookup"><span data-stu-id="58d94-260">4.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="58d94-262&quot;>Infrastrukturelement</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;58d94-262&quot;>Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id=&quot;58d94-263&quot;>**Tabell R: Resursgrupper**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;58d94-263&quot;>**Table R: Resource groups**</span></span>
  
<span data-ttu-id=&quot;58d94-264&quot;>Skapa de nya resursgrupperna med dessa kommandon.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;58d94-264&quot;>Create your new resource groups with these commands.</span></span>
  
```powershell
$locName=&quot;<an Azure location, such as West US>&quot;
$rgName=&quot;<Table R - Item 1 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 2 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 3 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 4 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id=&quot;58d94-265&quot;>Därefter skapar du det virtuella Azure-nätverket och dess undernät.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;58d94-265&quot;>Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName=&quot;<Table R - Item 4 - Resource group name column>&quot;
$locName=&quot;<your Azure location>&quot;
$vnetName=&quot;<Table V - Item 1 - Value column>&quot;
$vnetAddrPrefix=&quot;<Table V - Item 4 - Value column>&quot;
$dnsServers=@( &quot;<Table D - Item 1 - DNS server IP address column>&quot;, &quot;<Table D - Item 2 - DNS server IP address column>" )
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

<span data-ttu-id="58d94-266">Därefter skapar du nätverkssäkerhetsgrupper för varje undernät som har virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="58d94-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="58d94-267">Om du vill isolera undernät kan du lägga till regler för specifika typer av trafik som tillåts eller nekas till nätverkssäkerhetsgruppen för ett undernät.</span><span class="sxs-lookup"><span data-stu-id="58d94-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
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

<span data-ttu-id="58d94-268">Använd sedan dessa kommandon för att skapa gateways för VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="58d94-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
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
> <span data-ttu-id="58d94-269">Federerad autentisering av enskilda användare är inte beroende av några lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="58d94-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="58d94-270">Men om den här VPN-anslutningen mellan webbplatser blir otillgänglig kommer domänkontrollanterna på VNet inte att få uppdateringar för användarkonton och grupper som gjorts i den lokala Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="58d94-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="58d94-271">Du kan säkerställa att det inte sker genom att konfigurera hög tillgänglighet för VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="58d94-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="58d94-272">Mer information finns i [Mycket tillgänglig, tvärlokal anslutning och VNet-till-VNet-anslutning](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="58d94-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="58d94-273">Spela sedan in den offentliga IPv4-adressen för Azure VPN-gatewayen för ditt virtuella nätverk från visningen av det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="58d94-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="58d94-274">Konfigurera sedan din lokala VPN-enhet för att ansluta till Azure VPN-gatewayen.</span><span class="sxs-lookup"><span data-stu-id="58d94-274">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="58d94-275">Mer information finns i [Konfigurera din VPN-enhet.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)</span><span class="sxs-lookup"><span data-stu-id="58d94-275">For more information, see [Configure your VPN device](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="58d94-276">För att konfigurera din lokala VPN-enhet behöver du följande:</span><span class="sxs-lookup"><span data-stu-id="58d94-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="58d94-277">Den offentliga IPv4-adressen för Azure VPN-gatewayen.</span><span class="sxs-lookup"><span data-stu-id="58d94-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="58d94-278">IPsec-fördelade nyckeln för VPN-anslutningen mellan webbplatser (Tabell V - Objekt 5 - Värdekolumnen).</span><span class="sxs-lookup"><span data-stu-id="58d94-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="58d94-279">Se sedan till att adressutrymmet i det virtuella nätverket kan nås från ditt lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="58d94-279">Next, ensure that the address space of the virtual network is reachable from your on-premises network.</span></span> <span data-ttu-id="58d94-280">Det görs vanligtvis genom att lägga till en route som motsvarar det virtuella nätverksadressutrymmet på din VPN-enhet och sedan annonsera den till resten av routningsinfrastrukturen i ditt organisations nätverk.</span><span class="sxs-lookup"><span data-stu-id="58d94-280">This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network.</span></span> <span data-ttu-id="58d94-281">Ta reda på hur du ska göra det med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-281">Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="58d94-282">Definiera sedan namnen på tre tillgänglighetsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="58d94-282">Next, define the names of three availability sets.</span></span> <span data-ttu-id="58d94-283">Fyll i Tabell A.</span><span class="sxs-lookup"><span data-stu-id="58d94-283">Fill out Table A.</span></span> 
  
|<span data-ttu-id="58d94-284">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="58d94-284">**Item**</span></span>|<span data-ttu-id="58d94-285">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="58d94-285">**Purpose**</span></span>|<span data-ttu-id="58d94-286">**Namn på tillgänglighetsuppsättning**</span><span class="sxs-lookup"><span data-stu-id="58d94-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58d94-287">1.</span><span class="sxs-lookup"><span data-stu-id="58d94-287">1.</span></span>  <br/> |<span data-ttu-id="58d94-288">Domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="58d94-288">Domain controllers</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-290">2.</span><span class="sxs-lookup"><span data-stu-id="58d94-290">2.</span></span>  <br/> |<span data-ttu-id="58d94-291">AD FS-servrar</span><span class="sxs-lookup"><span data-stu-id="58d94-291">AD FS servers</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="58d94-293">3.</span><span class="sxs-lookup"><span data-stu-id="58d94-293">3.</span></span>  <br/> |<span data-ttu-id="58d94-294">Proxyservrar för webbprogram</span><span class="sxs-lookup"><span data-stu-id="58d94-294">Web application proxy servers</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="58d94-296">**Tabell A: Tillgänglighetsuppsättningar**</span><span class="sxs-lookup"><span data-stu-id="58d94-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="58d94-297">Du behöver dessa namn när du skapar de virtuella maskinerna i faserna 2, 3 och 4.</span><span class="sxs-lookup"><span data-stu-id="58d94-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="58d94-298">Skapa de nya tillgänglighetsuppsättningarna med dessa Azure PowerShell kommandon.</span><span class="sxs-lookup"><span data-stu-id="58d94-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
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

<span data-ttu-id="58d94-299">Det här är konfigurationen som är ett resultat av att den här fasen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="58d94-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="58d94-300">**Fas 1: Azure-infrastrukturen för federerad autentisering med hög tillgänglighet för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="58d94-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fas 1 av hög tillgänglighet Microsoft 365 federerad autentisering i Azure med Azure-infrastrukturen](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="58d94-302">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="58d94-302">Next step</span></span>

<span data-ttu-id="58d94-303">Använd [fas 2: Konfigurera domänkontrollanter så](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) att de kan fortsätta konfigurera den här arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="58d94-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58d94-304">Se även</span><span class="sxs-lookup"><span data-stu-id="58d94-304">See Also</span></span>

[<span data-ttu-id="58d94-305">Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="58d94-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="58d94-306">Federerad identitet för din Microsoft 365 utvecklings-/testmiljö</span><span class="sxs-lookup"><span data-stu-id="58d94-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="58d94-307">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="58d94-307">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="58d94-308">Förstå Microsoft 365 identitet och Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="58d94-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)