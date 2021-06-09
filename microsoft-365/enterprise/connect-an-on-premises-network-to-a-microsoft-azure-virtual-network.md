---
title: Anslut ett lokalt nätverk till ett virtuellt Microsoft Azure nätverk
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 'Sammanfattning: Lär dig hur du konfigurerar ett virtuellt Azure-Office för serverarbetsbelastning med en VPN-anslutning mellan webbplatser.'
ms.openlocfilehash: 00fd1c2246e9e9ac3eb55ca5ece9d84ecf49a1d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907714"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="f4149-103">Anslut ett lokalt nätverk till ett virtuellt Microsoft Azure nätverk</span><span class="sxs-lookup"><span data-stu-id="f4149-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="f4149-104">Ett virtuellt Azure-nätverk är anslutet till ditt lokala nätverk och utökar ditt nätverk så att undernät och virtuella datorer som finns i Azures infrastrukturtjänster inkluderas.</span><span class="sxs-lookup"><span data-stu-id="f4149-104">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services.</span></span> <span data-ttu-id="f4149-105">Med den här anslutningen kan datorer i det lokala nätverket få direkt åtkomst till virtuella datorer i Azure och vice versa.</span><span class="sxs-lookup"><span data-stu-id="f4149-105">This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="f4149-106">Till exempel måste en katalogsynkroniseringsserver som körs på en virtuell Azure-dator fråga dina lokala domänkontrollanter om kontoändringar och synkronisera dessa ändringar med din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="f4149-106">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription.</span></span> <span data-ttu-id="f4149-107">I den här artikeln finns information om hur du kryssar upp ett virtuellt Azure-nätverk på en plats till en webbplats med en anslutning för virtuellt privat nätverk (VPN) som är redo att vara värd för virtuella Azure-datorer.</span><span class="sxs-lookup"><span data-stu-id="f4149-107">This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="f4149-108">Konfigurera ett virtuellt Azure-nätverk på plats</span><span class="sxs-lookup"><span data-stu-id="f4149-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="f4149-109">Dina virtuella datorer i Azure behöver inte isoleras från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="f4149-109">Your virtual machines in Azure don't have to be isolated from your on-premises environment.</span></span> <span data-ttu-id="f4149-110">Om du vill ansluta virtuella Azure-datorer till dina lokala nätverksresurser måste du konfigurera ett virtuellt Azure-nätverk på plats.</span><span class="sxs-lookup"><span data-stu-id="f4149-110">To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network.</span></span> <span data-ttu-id="f4149-111">Följande diagram visar de komponenter som krävs för att distribuera ett virtuellt Azure-nätverk med en virtuell dator i Azure.</span><span class="sxs-lookup"><span data-stu-id="f4149-111">The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![Lokalt nätverk som är anslutet Microsoft Azure via en VPN-anslutning mellan webbplatser](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="f4149-113">I diagrammet finns det två nätverk som är anslutna med en VPN-anslutning mellan webbplatser: det lokala nätverket och det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-113">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="f4149-114">VPN-anslutningen mellan webbplatser är:</span><span class="sxs-lookup"><span data-stu-id="f4149-114">The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="f4149-115">Mellan två slutpunkter som är adresserbara och placerade på det offentliga Internet.</span><span class="sxs-lookup"><span data-stu-id="f4149-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="f4149-116">Avslutas av en VPN-enhet i det lokala nätverket och en Azure VPN-gateway i det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="f4149-117">Det virtuella Azure-nätverket är värd för virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="f4149-117">The Azure virtual network hosts virtual machines.</span></span> <span data-ttu-id="f4149-118">Nätverkstrafik som kommer från virtuella datorer i det virtuella Azure-nätverket vidarebefordras till VPN-gatewayen, som sedan vidarebefordrar trafiken via VPN-anslutningen mellan kontor till VPN-enheten i det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-118">Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network.</span></span> <span data-ttu-id="f4149-119">Routningsinfrastrukturen i det lokala nätverket vidarebefordrar sedan trafiken till destinationen.</span><span class="sxs-lookup"><span data-stu-id="f4149-119">The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="f4149-120">Du kan också använda [ExpressRoute](https://azure.microsoft.com/services/expressroute/), som är en direkt anslutning mellan din organisation och Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-120">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network.</span></span> <span data-ttu-id="f4149-121">Trafik genom ExpressRoute färdas inte via det offentliga Internet.</span><span class="sxs-lookup"><span data-stu-id="f4149-121">Traffic over ExpressRoute does not travel over the public Internet.</span></span> <span data-ttu-id="f4149-122">I den här artikeln beskrivs inte hur ExpressRoute används.</span><span class="sxs-lookup"><span data-stu-id="f4149-122">This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="f4149-123">Om du vill konfigurera VPN-anslutningen mellan ditt virtuella Azure-nätverk och ditt lokala nätverk gör du så här:</span><span class="sxs-lookup"><span data-stu-id="f4149-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="f4149-124">**Lokalt:** Definiera och skapa en lokal nätverksrutt för adressutrymmet i det virtuella Azure-nätverket som pekar på din lokala VPN-enhet.</span><span class="sxs-lookup"><span data-stu-id="f4149-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="f4149-125">**Microsoft Azure:** Skapa ett virtuellt Azure-nätverk med en VPN-anslutning mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="f4149-126">**Lokalt:** Konfigurera din lokala maskinvara eller programvara VPN-enhet för att avsluta VPN-anslutningen som använder IPsec (Internet Protocol security).</span><span class="sxs-lookup"><span data-stu-id="f4149-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="f4149-127">När du har upprättat VPN-anslutningen mellan webbplatser lägger du till Virtuella Azure-datorer till undernäten för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="f4149-128">Planera ditt virtuella Azure-nätverk</span><span class="sxs-lookup"><span data-stu-id="f4149-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="f4149-129">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f4149-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="f4149-130">En Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="f4149-130">An Azure subscription.</span></span> <span data-ttu-id="f4149-131">Mer information om Azure-prenumerationer finns på [sidan Så här köper du Azure.](https://azure.microsoft.com/pricing/purchase-options/)</span><span class="sxs-lookup"><span data-stu-id="f4149-131">For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="f4149-132">Ett tillgängligt privat IPv4-adressutrymme för tilldelning till det virtuella nätverket och dess undernät, med tillräckligt med utrymme för tillväxt för att hantera antalet virtuella maskiner som behövs både nu och i framtiden.</span><span class="sxs-lookup"><span data-stu-id="f4149-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="f4149-133">En tillgänglig VPN-enhet i ditt lokala nätverk för att avsluta VPN-anslutningen mellan webbplatser som stöder kraven för IPsec.</span><span class="sxs-lookup"><span data-stu-id="f4149-133">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec.</span></span> <span data-ttu-id="f4149-134">Mer information finns i [Om VPN-enheter för virtuella nätverksanslutningar](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)till webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-134">For more information, see [About VPN devices for site-to-site virtual network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
    
- <span data-ttu-id="f4149-135">Ändringar av din routningsinfrastruktur så att trafik som dirigeras till adressutrymmet i det virtuella Azure-nätverket vidarebefordras till VPN-enheten som är värd för VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="f4149-136">En webbproxy som ger datorer som är anslutna till det lokala nätverket och Azure-virtuella nätverket åtkomst till Internet.</span><span class="sxs-lookup"><span data-stu-id="f4149-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="f4149-137">Antaganden om design av lösningsarkitektur</span><span class="sxs-lookup"><span data-stu-id="f4149-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="f4149-138">I följande lista visas de designval som har gjorts för den här lösningsarkitekturen.</span><span class="sxs-lookup"><span data-stu-id="f4149-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="f4149-139">Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-139">This solution uses a single Azure virtual network with a site-to-site VPN connection.</span></span> <span data-ttu-id="f4149-140">Det virtuella Azure-nätverket är värd för ett enda undernät som kan innehålla flera virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="f4149-140">The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="f4149-141">Du kan använda RRAS (Routing and Remote Access Service) i Windows Server 2016 eller Windows Server 2012 för att upprätta en VPN-anslutning mellan det lokala nätverket och det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-141">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="f4149-142">Du kan också använda andra alternativ, till exempel Cisco eller Juniper Networks VPN-enheter.</span><span class="sxs-lookup"><span data-stu-id="f4149-142">You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="f4149-143">Det lokala nätverket kan fortfarande ha nätverkstjänster som AD DS (Active Directory Domain Services), DNS (Domain Name System) och proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="f4149-143">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers.</span></span> <span data-ttu-id="f4149-144">Beroende på dina behov kan det vara bra att placera några av dessa nätverksresurser i det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-144">Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="f4149-145">För ett befintligt virtuellt Azure-nätverk med ett eller flera undernät ska du avgöra om det finns återstående adressutrymme för ett extra undernät som värd för dina virtuella maskiner, baserat på dina behov.</span><span class="sxs-lookup"><span data-stu-id="f4149-145">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements.</span></span> <span data-ttu-id="f4149-146">Om du inte har kvar adressutrymmet för ytterligare ett undernät skapar du ett ytterligare virtuellt nätverk som har en egen VPN-anslutning mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-146">If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="f4149-147">Planera ändringar i routningsinfrastrukturen för det virtuella Azure-nätverket</span><span class="sxs-lookup"><span data-stu-id="f4149-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="f4149-148">Du måste konfigurera den lokala routningsinfrastrukturen för att vidarebefordra trafik till adressutrymmet i det virtuella Azure-nätverket till den lokala VPN-enhet som är värd för VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="f4149-149">Den exakta metoden för att uppdatera routningsinfrastrukturen beror på hur du hanterar routningsinformationen, vilket kan vara:</span><span class="sxs-lookup"><span data-stu-id="f4149-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="f4149-150">Uppdateringar av routningstabeller baserat på manuell konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f4149-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="f4149-151">Uppdateringar av routningstabeller baserade på routningsprotokoll, t.ex. ROUTING Information Protocol (USA) eller Open Shortest Path First (OSPF).</span><span class="sxs-lookup"><span data-stu-id="f4149-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="f4149-152">Kontakta din routingspecialist för att se till att trafik med destinationen till det virtuella Azure-nätverket vidarebefordras till den lokala VPN-enheten.</span><span class="sxs-lookup"><span data-stu-id="f4149-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="f4149-153">Planera för brandväggsregler för trafik till och från den lokala VPN-enheten</span><span class="sxs-lookup"><span data-stu-id="f4149-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="f4149-154">Om din VPN-enhet finns i ett perimeternätverk som har en brandvägg mellan perimeternätverket och Internet kan du behöva konfigurera brandväggen för följande regler för att tillåta VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="f4149-155">Trafik till VPN-enheten (inkommande från Internet):</span><span class="sxs-lookup"><span data-stu-id="f4149-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="f4149-156">Mål-IP-adress för VPN-enheten och IP-protokollet 50</span><span class="sxs-lookup"><span data-stu-id="f4149-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="f4149-157">Mål-IP-adressen för VPN-enheten och UDP-målport 500</span><span class="sxs-lookup"><span data-stu-id="f4149-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="f4149-158">Mål-IP-adressen för VPN-enheten och UDP-målport 4500</span><span class="sxs-lookup"><span data-stu-id="f4149-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="f4149-159">Trafik från VPN-enheten (utgående till Internet):</span><span class="sxs-lookup"><span data-stu-id="f4149-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="f4149-160">Käll-IP-adressen för VPN-enheten och IP-protokollet 50</span><span class="sxs-lookup"><span data-stu-id="f4149-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="f4149-161">Käll-IP-adressen för VPN-enheten och UDP-källport 500</span><span class="sxs-lookup"><span data-stu-id="f4149-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="f4149-162">Käll-IP-adressen för VPN-enheten och UDP-källport 4500</span><span class="sxs-lookup"><span data-stu-id="f4149-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="f4149-163">Planera för det privata IP-adressutrymmet i det virtuella Azure-nätverket</span><span class="sxs-lookup"><span data-stu-id="f4149-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="f4149-164">Det privata IP-adressutrymmet i det virtuella Azure-nätverket måste kunna hantera adresser som används av Azure som värd för det virtuella nätverket och med minst ett undernät som har tillräckligt med adresser för dina virtuella Azure-datorer.</span><span class="sxs-lookup"><span data-stu-id="f4149-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="f4149-165">Beräkna antalet adresser som behövs för undernätet genom att räkna antalet virtuella maskiner som du behöver nu, uppskatta framtida tillväxt och använd sedan följande tabell för att fastställa storleken på undernätet.</span><span class="sxs-lookup"><span data-stu-id="f4149-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="f4149-166">**Antal virtuella maskiner som behövs**</span><span class="sxs-lookup"><span data-stu-id="f4149-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="f4149-167">**Antal värd bitar som behövs**</span><span class="sxs-lookup"><span data-stu-id="f4149-167">**Number of host bits needed**</span></span>|<span data-ttu-id="f4149-168">**Storlek på undernätet**</span><span class="sxs-lookup"><span data-stu-id="f4149-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4149-169">1-3</span><span class="sxs-lookup"><span data-stu-id="f4149-169">1-3</span></span>  <br/> |<span data-ttu-id="f4149-170">3</span><span class="sxs-lookup"><span data-stu-id="f4149-170">3</span></span>  <br/> |<span data-ttu-id="f4149-171">/29</span><span class="sxs-lookup"><span data-stu-id="f4149-171">/29</span></span>  <br/> |
|<span data-ttu-id="f4149-172">4-11</span><span class="sxs-lookup"><span data-stu-id="f4149-172">4-11</span></span>  <br/> |<span data-ttu-id="f4149-173">4</span><span class="sxs-lookup"><span data-stu-id="f4149-173">4</span></span>  <br/> |<span data-ttu-id="f4149-174">/28</span><span class="sxs-lookup"><span data-stu-id="f4149-174">/28</span></span>  <br/> |
|<span data-ttu-id="f4149-175">12-27</span><span class="sxs-lookup"><span data-stu-id="f4149-175">12-27</span></span>  <br/> |<span data-ttu-id="f4149-176">5</span><span class="sxs-lookup"><span data-stu-id="f4149-176">5</span></span>  <br/> |<span data-ttu-id="f4149-177">/27</span><span class="sxs-lookup"><span data-stu-id="f4149-177">/27</span></span>  <br/> |
|<span data-ttu-id="f4149-178">28-59</span><span class="sxs-lookup"><span data-stu-id="f4149-178">28-59</span></span>  <br/> |<span data-ttu-id="f4149-179">6</span><span class="sxs-lookup"><span data-stu-id="f4149-179">6</span></span>  <br/> |<span data-ttu-id="f4149-180">/26</span><span class="sxs-lookup"><span data-stu-id="f4149-180">/26</span></span>  <br/> |
|<span data-ttu-id="f4149-181">60-123</span><span class="sxs-lookup"><span data-stu-id="f4149-181">60-123</span></span>  <br/> |<span data-ttu-id="f4149-182">7</span><span class="sxs-lookup"><span data-stu-id="f4149-182">7</span></span>  <br/> |<span data-ttu-id="f4149-183">/25</span><span class="sxs-lookup"><span data-stu-id="f4149-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="f4149-184">Planeringskalkylblad för konfiguration av ditt virtuella Azure-nätverk</span><span class="sxs-lookup"><span data-stu-id="f4149-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="f4149-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="f4149-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="f4149-186">Innan du skapar ett virtuellt Azure-nätverk som värd för virtuella maskiner måste du fastställa de inställningar som krävs i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="f4149-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="f4149-187">Fyll i Tabell V för inställningarna för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="f4149-188">**Tabell V: Konfiguration av virtuellt nätverk på flera platser**</span><span class="sxs-lookup"><span data-stu-id="f4149-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="f4149-189">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="f4149-189">**Item**</span></span>|<span data-ttu-id="f4149-190">**Konfigurationselement**</span><span class="sxs-lookup"><span data-stu-id="f4149-190">**Configuration element**</span></span>|<span data-ttu-id="f4149-191">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="f4149-191">**Description**</span></span>|<span data-ttu-id="f4149-192">**Värde**</span><span class="sxs-lookup"><span data-stu-id="f4149-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4149-193">1.</span><span class="sxs-lookup"><span data-stu-id="f4149-193">1.</span></span>  <br/> |<span data-ttu-id="f4149-194">Namn på virtuellt nätverk</span><span class="sxs-lookup"><span data-stu-id="f4149-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="f4149-195">Ett namn att tilldela till det virtuella Azure-nätverket (exempel DirSyncNet).</span><span class="sxs-lookup"><span data-stu-id="f4149-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="f4149-197">2.</span><span class="sxs-lookup"><span data-stu-id="f4149-197">2.</span></span>  <br/> |<span data-ttu-id="f4149-198">Virtuell nätverksplats</span><span class="sxs-lookup"><span data-stu-id="f4149-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="f4149-199">Azure-datacentret som kommer att innehålla det virtuella nätverket (t.ex. Väst USA).</span><span class="sxs-lookup"><span data-stu-id="f4149-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="f4149-201">3.</span><span class="sxs-lookup"><span data-stu-id="f4149-201">3.</span></span>  <br/> |<span data-ttu-id="f4149-202">IP-adress för VPN-enhet</span><span class="sxs-lookup"><span data-stu-id="f4149-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="f4149-203">Den offentliga IPv4-adressen till VPN-enhetens gränssnitt på Internet.</span><span class="sxs-lookup"><span data-stu-id="f4149-203">The public IPv4 address of your VPN device's interface on the Internet.</span></span> <span data-ttu-id="f4149-204">Ta reda på adressen tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="f4149-204">Work with your IT department to determine this address.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="f4149-206">4.</span><span class="sxs-lookup"><span data-stu-id="f4149-206">4.</span></span>  <br/> |<span data-ttu-id="f4149-207">Virtuellt nätverksadressutrymme</span><span class="sxs-lookup"><span data-stu-id="f4149-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="f4149-208">Adressutrymmet (som definierats i ett enda privat adressprefix) för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-208">The address space (defined in a single private address prefix) for the virtual network.</span></span> <span data-ttu-id="f4149-209">Ta reda på det här adressutrymmet tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="f4149-209">Work with your IT department to determine this address space.</span></span> <span data-ttu-id="f4149-210">Adressutrymmet ska vara i CIDR-format (Classless Interdomain Routing), även kallat nätverksprefixformat.</span><span class="sxs-lookup"><span data-stu-id="f4149-210">The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="f4149-211">Ett exempel är 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="f4149-211">An example is 10.24.64.0/20.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="f4149-213">5.</span><span class="sxs-lookup"><span data-stu-id="f4149-213">5.</span></span>  <br/> |<span data-ttu-id="f4149-214">Delad IPsec-nyckel</span><span class="sxs-lookup"><span data-stu-id="f4149-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="f4149-215">En slumpmässig alfanumerisk sträng med 32 tecken som används för att autentisera båda sidorna av VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-215">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="f4149-216">Arbeta med IT- eller säkerhetsavdelningen för att fastställa det här nyckelvärdet och lagra det sedan på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="f4149-216">Work with your IT or security department to determine this key value and then store it in a secure location.</span></span> <span data-ttu-id="f4149-217">Alternativt kan du gå till [Skapa en slumpmässig sträng för en IPsec-fördelsnyckel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="f4149-217">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="f4149-219">Fyll i Tabell S för undernäten för den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="f4149-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="f4149-220">För det första undernätet bestämmer du ett 28-bitars adressutrymme (med prefixlängden /28) för Azure Gateway-undernätet.</span><span class="sxs-lookup"><span data-stu-id="f4149-220">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet.</span></span> <span data-ttu-id="f4149-221">Mer [information om hur du fastställer det här adressutrymmet finns i](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) Beräkna gatewayundernätets adressutrymme för virtuella Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-221">See [Calculating the gateway subnet address space for Azure virtual networks](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="f4149-222">För det andra undernätet anger du ett eget namn, ett enda IP-adressutrymme baserat på det virtuella nätverksadressutrymmet och ett beskrivande syfte.</span><span class="sxs-lookup"><span data-stu-id="f4149-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="f4149-223">Arbeta med IT-avdelningen för att fastställa dessa adressutrymmen från det virtuella nätverksadressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="f4149-223">Work with your IT department to determine these address spaces from the virtual network address space.</span></span> <span data-ttu-id="f4149-224">Båda adress blankstegen ska vara i CIDR-format.</span><span class="sxs-lookup"><span data-stu-id="f4149-224">Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="f4149-225">**Tabell S: Undernät i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="f4149-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="f4149-226">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="f4149-226">**Item**</span></span>|<span data-ttu-id="f4149-227">**Undernätsnamn**</span><span class="sxs-lookup"><span data-stu-id="f4149-227">**Subnet name**</span></span>|<span data-ttu-id="f4149-228">**Adressutrymme för undernät**</span><span class="sxs-lookup"><span data-stu-id="f4149-228">**Subnet address space**</span></span>|<span data-ttu-id="f4149-229">**Syfte**</span><span class="sxs-lookup"><span data-stu-id="f4149-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4149-230">1.</span><span class="sxs-lookup"><span data-stu-id="f4149-230">1.</span></span>  <br/> |<span data-ttu-id="f4149-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="f4149-231">GatewaySubnet</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="f4149-233">Det undernät som används av Azure Gateway.</span><span class="sxs-lookup"><span data-stu-id="f4149-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="f4149-234">2.</span><span class="sxs-lookup"><span data-stu-id="f4149-234">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="f4149-238">Fyll i Tabell D för de lokala DNS-servrar som du vill att de virtuella maskinerna i det virtuella nätverket ska använda. Ge varje DNS-server ett eget namn och en enda IP-adress.</span><span class="sxs-lookup"><span data-stu-id="f4149-238">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address.</span></span> <span data-ttu-id="f4149-239">Det här användarvänliga namnet behöver inte matcha DNS-serverns värdnamn eller datornamn.</span><span class="sxs-lookup"><span data-stu-id="f4149-239">This friendly name does not need to match the host name or computer name of the DNS server.</span></span> <span data-ttu-id="f4149-240">Observera att två tomma poster visas, men du kan lägga till fler.</span><span class="sxs-lookup"><span data-stu-id="f4149-240">Note that two blank entries are listed, but you can add more.</span></span> <span data-ttu-id="f4149-241">Ta reda på listan tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="f4149-241">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="f4149-242">**Tabell D: Lokala DNS-servrar**</span><span class="sxs-lookup"><span data-stu-id="f4149-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="f4149-243">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="f4149-243">**Item**</span></span>|<span data-ttu-id="f4149-244">**Eget namn för DNS-server**</span><span class="sxs-lookup"><span data-stu-id="f4149-244">**DNS server friendly name**</span></span>|<span data-ttu-id="f4149-245">**IP-adress för DNS-server**</span><span class="sxs-lookup"><span data-stu-id="f4149-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4149-246">1.</span><span class="sxs-lookup"><span data-stu-id="f4149-246">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="f4149-249">2.</span><span class="sxs-lookup"><span data-stu-id="f4149-249">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="f4149-252">Om du vill dirigera paket från det virtuella Azure-nätverket till organisationens nätverk via VPN-anslutningen mellan webbplatser måste du konfigurera det virtuella nätverket med ett lokalt nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-252">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network.</span></span> <span data-ttu-id="f4149-253">Det här lokala nätverket har en lista med adressutrymmen (i CIDR-format) för alla platser i organisationens lokala nätverk som virtuella maskiner i det virtuella nätverket måste nå.</span><span class="sxs-lookup"><span data-stu-id="f4149-253">This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach.</span></span> <span data-ttu-id="f4149-254">Det kan vara alla platser i det lokala nätverket eller en delmängd.</span><span class="sxs-lookup"><span data-stu-id="f4149-254">This can be all of the locations on the on-premises network or a subset.</span></span> <span data-ttu-id="f4149-255">Listan med adressutrymmen som definierar ditt lokala nätverk måste vara unik och får inte överlappa med de adressutrymmen som används för det här virtuella nätverket eller andra virtuella korslokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-255">The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="f4149-256">För de lokala nätverksadressutrymmena fyller du i Tabell L. Observera att tre tomma poster visas, men du behöver vanligtvis mer.</span><span class="sxs-lookup"><span data-stu-id="f4149-256">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="f4149-257">Ta reda på listan tillsammans med IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="f4149-257">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="f4149-258">**Tabell L: Adressprefix för det lokala nätverket**</span><span class="sxs-lookup"><span data-stu-id="f4149-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="f4149-259">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="f4149-259">**Item**</span></span>|<span data-ttu-id="f4149-260">**Lokalt nätverksadressutrymme**</span><span class="sxs-lookup"><span data-stu-id="f4149-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4149-261">1.</span><span class="sxs-lookup"><span data-stu-id="f4149-261">1.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="f4149-263">2.</span><span class="sxs-lookup"><span data-stu-id="f4149-263">2.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="f4149-265">3.</span><span class="sxs-lookup"><span data-stu-id="f4149-265">3.</span></span>  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="f4149-267">Distributionsöversikt</span><span class="sxs-lookup"><span data-stu-id="f4149-267">Deployment roadmap</span></span>
<span data-ttu-id="f4149-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="f4149-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="f4149-269">Att skapa det virtuella nätverket på plats och lägga till virtuella maskiner i Azure består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="f4149-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="f4149-270">Fas 1: Förbereda det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="f4149-271">Fas 2: Skapa det virtuella korslokala nätverket i Azure.</span><span class="sxs-lookup"><span data-stu-id="f4149-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="f4149-272">Fas 3 (valfritt): Lägg till virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="f4149-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="f4149-273">Fas 1: Förbereda det lokala nätverket</span><span class="sxs-lookup"><span data-stu-id="f4149-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="f4149-274">Du måste konfigurera det lokala nätverket med en route som pekar på och i slutänden levererar trafik till det virtuella nätverkets adressutrymme till routern vid kanten av det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-274">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network.</span></span> <span data-ttu-id="f4149-275">Fråga nätverksadministratören hur du lägger till routningen i det lokala nätverkets routningsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="f4149-275">Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="f4149-276">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="f4149-276">Here is your resulting configuration.</span></span>
  
![Det lokala nätverket måste ha en route för det virtuella nätverkets adressutrymme som pekar mot VPN-enheten.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="f4149-278">Fas 2: Skapa det virtuella korslokala nätverket i Azure</span><span class="sxs-lookup"><span data-stu-id="f4149-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="f4149-279">Öppna först ett meddelande Azure PowerShell meddelande.</span><span class="sxs-lookup"><span data-stu-id="f4149-279">First, open an Azure PowerShell prompt.</span></span> <span data-ttu-id="f4149-280">Om du inte har installerat Azure PowerShell kan du [gå till Komma igång Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="f4149-280">If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="f4149-281">Sedan loggar du in på ditt Azure-konto med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="f4149-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="f4149-282">Hämta ditt prenumerationsnamn med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="f4149-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="f4149-283">Ställ in din Azure-prenumeration med de här kommandona.</span><span class="sxs-lookup"><span data-stu-id="f4149-283">Set your Azure subscription with these commands.</span></span> <span data-ttu-id="f4149-284">Ersätt allt inom citattförfrågningarna, inklusive < och > tecken, med rätt prenumerationsnamn.</span><span class="sxs-lookup"><span data-stu-id="f4149-284">Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="f4149-285">Skapa sedan en ny resursgrupp för ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-285">Next, create a new resource group for your virtual network.</span></span> <span data-ttu-id="f4149-286">Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.</span><span class="sxs-lookup"><span data-stu-id="f4149-286">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="f4149-287">Skapa den nya resursgruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="f4149-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="f4149-288">Därefter skapar du det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-288">Next, you create the Azure virtual network.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="f4149-289">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="f4149-289">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket är ännu inte anslutet till det lokala nätverket.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="f4149-291">Använd sedan dessa kommandon för att skapa gateways för VPN-anslutningen mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

<span data-ttu-id="f4149-292">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="f4149-292">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket har nu en gateway.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="f4149-294">Konfigurera sedan din lokala VPN-enhet för att ansluta till Azure VPN-gatewayen.</span><span class="sxs-lookup"><span data-stu-id="f4149-294">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="f4149-295">Mer information finns i [Om VPN-enheter för Azure Virtual Network-anslutningar](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)mellan webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f4149-295">For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="f4149-296">För att konfigurera VPN-enheten behöver du följande:</span><span class="sxs-lookup"><span data-stu-id="f4149-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="f4149-297">Den offentliga IPv4-adressen för Azure VPN-gatewayen för ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="f4149-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="f4149-298">Använd kommandot **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** för att visa den här adressen.</span><span class="sxs-lookup"><span data-stu-id="f4149-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="f4149-299">IPsec-fördelade nyckeln för VPN-anslutningen mellan webbplatser (Tabell V- Objekt 5 – Värdekolumn).</span><span class="sxs-lookup"><span data-stu-id="f4149-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="f4149-300">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="f4149-300">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket är nu anslutet till det lokala nätverket.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="f4149-302">Fas 3 (valfritt): Lägg till virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="f4149-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="f4149-303">Skapa de virtuella datorer du behöver i Azure.</span><span class="sxs-lookup"><span data-stu-id="f4149-303">Create the virtual machines you need in Azure.</span></span> <span data-ttu-id="f4149-304">Mer information finns i [Skapa en Windows virtuell dator med Azure-portalen](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="f4149-304">For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="f4149-305">Använd följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f4149-305">Use the following settings:</span></span>
  
- <span data-ttu-id="f4149-306">På fliken **Grunder väljer** du samma prenumerations- och resursgrupp som det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="f4149-306">On the **Basics** tab, select the same subscription and resource group as your virtual network.</span></span> <span data-ttu-id="f4149-307">Du behöver dem senare för att logga in på den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="f4149-307">You will need these later to sign in to the virtual machine.</span></span> <span data-ttu-id="f4149-308">I avsnittet **Instansinformation** väljer du rätt storlek på den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="f4149-308">In the **Instance details** section, choose the appropriate virtual machine size.</span></span> <span data-ttu-id="f4149-309">Registrera användarnamnet och lösenordet för administratörskontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="f4149-309">Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="f4149-310">På fliken **Nätverk** väljer du namnet på ditt virtuella nätverk och undernätet för värd för virtuella maskiner (inte GatewaySubnet).</span><span class="sxs-lookup"><span data-stu-id="f4149-310">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet).</span></span> <span data-ttu-id="f4149-311">Lämna alla andra inställningar för standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="f4149-311">Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="f4149-312">Kontrollera att den virtuella datorn använder DNS korrekt genom att kontrollera din interna DNS så att adressposterna (A) har lagts till åt den nya virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="f4149-312">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine.</span></span> <span data-ttu-id="f4149-313">För att du ska kunna komma åt Internet måste dina virtuella Azure-datorer vara konfigurerade för att använda ditt lokala nätverks proxyserver.</span><span class="sxs-lookup"><span data-stu-id="f4149-313">To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server.</span></span> <span data-ttu-id="f4149-314">Kontakta nätverksadministratören för att få ytterligare konfigurationssteg att utföra på servern.</span><span class="sxs-lookup"><span data-stu-id="f4149-314">Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="f4149-315">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="f4149-315">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket är nu värd för virtuella maskiner som är tillgängliga från det lokala nätverket.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="f4149-317">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f4149-317">Next step</span></span>
  
[<span data-ttu-id="f4149-318">Distribuera Microsoft 365 katalogsynkronisering i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f4149-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)