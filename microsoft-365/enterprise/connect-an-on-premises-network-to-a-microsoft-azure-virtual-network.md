---
title: Ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk
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
description: 'Sammanfattning: Lär dig hur du konfigurerar ett lokalt Azure-virtuellt nätverk för Office Server-arbetsbelastningar med en VPN-anslutning för webbplatser.'
ms.openlocfilehash: cddb9cfcff02f91ef76f989b87e9dda049cc1b08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696674"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="caea5-103">Ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk</span><span class="sxs-lookup"><span data-stu-id="caea5-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="caea5-104">Ett lokalt Azure-nätverk ansluts till ditt lokala nätverk, så att nätverket utökas för att omfatta delnät och virtuella datorer i Azure Infrastructure Services.</span><span class="sxs-lookup"><span data-stu-id="caea5-104">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services.</span></span> <span data-ttu-id="caea5-105">Med den här anslutningen kan datorer i ditt lokala nätverk direkt komma åt virtuella datorer i Azure och vice versa.</span><span class="sxs-lookup"><span data-stu-id="caea5-105">This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="caea5-106">En programkatalogpartition som körs på en virtuell Azure-dator måste till exempel söka efter ändringar i de lokala domän kontrol Lanterna och synkronisera ändringarna med ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="caea5-106">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription.</span></span> <span data-ttu-id="caea5-107">I den här artikeln beskrivs hur du konfigurerar ett lokalt Azure-nätverk med en VPN-anslutning som är redo att vara värd för virtuella Azure-datorer.</span><span class="sxs-lookup"><span data-stu-id="caea5-107">This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="caea5-108">Konfigurera ett lokalt Azure-virtuellt nätverk</span><span class="sxs-lookup"><span data-stu-id="caea5-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="caea5-109">De virtuella datorerna i Azure behöver inte isoleras från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="caea5-109">Your virtual machines in Azure don't have to be isolated from your on-premises environment.</span></span> <span data-ttu-id="caea5-110">För att ansluta virtuella Azure-datorer till lokala nätverks resurser måste du konfigurera ett lokalt Azure-virtuellt nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-110">To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network.</span></span> <span data-ttu-id="caea5-111">I följande diagram visas de komponenter som krävs för att distribuera ett interlokalt Azure-virtuellt nätverk med en virtuell dator i Azure.</span><span class="sxs-lookup"><span data-stu-id="caea5-111">The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![Lokalt nätverk anslutna till Microsoft Azure via en VPN-anslutning för webbplats-till-plats](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="caea5-113">I diagrammet finns det två nätverk anslutna med en VPN-anslutning för plats-till-plats: det lokala nätverket och det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-113">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="caea5-114">VPN-anslutningen för webbplats-till-plats är:</span><span class="sxs-lookup"><span data-stu-id="caea5-114">The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="caea5-115">Mellan två slut punkter som är adresser bara och finns på det offentliga Internet.</span><span class="sxs-lookup"><span data-stu-id="caea5-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="caea5-116">Avbröts av en VPN-enhet i det lokala nätverket och en Azure VPN gateway i det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="caea5-117">Virtuella datorer för Azure virtuella nätverk värdar.</span><span class="sxs-lookup"><span data-stu-id="caea5-117">The Azure virtual network hosts virtual machines.</span></span> <span data-ttu-id="caea5-118">Nätverks trafik från virtuella datorer i det virtuella Azure-nätverket vidarebefordras till VPN-gatewayen, som sedan vidarebefordrar trafiken via plats-till-plats-anslutningen till VPN-enheten i det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-118">Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network.</span></span> <span data-ttu-id="caea5-119">Infrastrukturen för routning i det lokala nätverket vidarebefordrar sedan trafiken till dess mål.</span><span class="sxs-lookup"><span data-stu-id="caea5-119">The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="caea5-120">Du kan också använda [ExpressRoute](https://azure.microsoft.com/services/expressroute/), som är en direkt förbindelse mellan din organisation och Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-120">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network.</span></span> <span data-ttu-id="caea5-121">Trafik över ExpressRoute reser inte över det offentliga Internet.</span><span class="sxs-lookup"><span data-stu-id="caea5-121">Traffic over ExpressRoute does not travel over the public Internet.</span></span> <span data-ttu-id="caea5-122">I den här artikeln beskrivs inte hur ExpressRoute används.</span><span class="sxs-lookup"><span data-stu-id="caea5-122">This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="caea5-123">Följ de här stegen om du vill konfigurera VPN-anslutningen mellan Azure Virtual Network och det lokala nätverket:</span><span class="sxs-lookup"><span data-stu-id="caea5-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="caea5-124">**Lokalt:** Definiera och skapa en lokal nätverks väg för adress utrymmet för det virtuella Azure-nätverket som pekar på din lokala VPN-enhet.</span><span class="sxs-lookup"><span data-stu-id="caea5-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="caea5-125">**Microsoft Azure:** Skapa ett Azure Virtual Network med en VPN-anslutning för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="caea5-126">**Lokalt:** Konfigurera den lokala maskinvaru-eller program varu-VPN-enheten för att avsluta VPN-anslutningen, som använder IP-säkerhet (IPsec).</span><span class="sxs-lookup"><span data-stu-id="caea5-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="caea5-127">När du har upprättat VPN-anslutningen för plats-till-plats lägger du till virtuella Azure-datorer i under näten för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="caea5-128">Planera det virtuella Azure-nätverket</span><span class="sxs-lookup"><span data-stu-id="caea5-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="caea5-129">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="caea5-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="caea5-130">En Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="caea5-130">An Azure subscription.</span></span> <span data-ttu-id="caea5-131">Om du vill ha mer information om Azure-prenumerationer går du till [sidan om att köpa Azure](https://azure.microsoft.com/pricing/purchase-options/).</span><span class="sxs-lookup"><span data-stu-id="caea5-131">For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="caea5-132">Ett tillgängligt privat IPv4-adress utrymme som kan kopplas till det virtuella nätverket och dess undernät, med tillräckligt utrymme för tillväxt för att rymma det antal virtuella datorer som behövs nu och i framtiden.</span><span class="sxs-lookup"><span data-stu-id="caea5-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="caea5-133">En tillgänglig VPN-enhet i det lokala nätverket för att avsluta VPN-anslutningen för webbplats-till-plats som stöder kraven för IPsec.</span><span class="sxs-lookup"><span data-stu-id="caea5-133">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec.</span></span> <span data-ttu-id="caea5-134">Mer information finns i [om VPN-enheter för virtuella nätverks anslutningar mellan](https://go.microsoft.com/fwlink/p/?LinkId=393093)webbplatser.</span><span class="sxs-lookup"><span data-stu-id="caea5-134">For more information, see [About VPN devices for site-to-site virtual network connections](https://go.microsoft.com/fwlink/p/?LinkId=393093).</span></span>
    
- <span data-ttu-id="caea5-135">Ändringar i infrastrukturen för routning så att trafiken dirigeras till den VPN-enhet som är värd för VPN-anslutningen för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="caea5-136">En webbproxy som ger datorer som är anslutna till det lokala nätverket och det virtuella Azure-nätverket till gång till Internet.</span><span class="sxs-lookup"><span data-stu-id="caea5-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="caea5-137">Utvecklings antagande för lösnings arkitektur</span><span class="sxs-lookup"><span data-stu-id="caea5-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="caea5-138">Följande lista visar de design alternativ som har gjorts för den här lösnings arkitekturen.</span><span class="sxs-lookup"><span data-stu-id="caea5-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="caea5-139">Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-139">This solution uses a single Azure virtual network with a site-to-site VPN connection.</span></span> <span data-ttu-id="caea5-140">Det virtuella Azure-nätverket har ett enda undernät som kan innehålla flera virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="caea5-140">The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="caea5-141">Du kan använda tjänsten Routning och fjärråtkomst (RRAS) i Windows Server 2016 eller Windows Server 2012 för att upprätta en IPsec-plats-till-plats-VPN-anslutning mellan det lokala nätverket och det virtuella Azure-nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-141">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="caea5-142">Du kan också använda andra alternativ, till exempel Cisco-eller Juniper-nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-142">You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="caea5-143">Det lokala nätverket kan fortfarande ha nätverks tjänster, till exempel AD DS (Active Directory Domain Services), DNS (Domain Name System) och proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="caea5-143">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers.</span></span> <span data-ttu-id="caea5-144">Beroende på dina behov kan det vara bra att placera vissa av de här nätverks resurserna i Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="caea5-144">Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="caea5-145">För ett befintligt Azure Virtual Network med ett eller flera undernät kan du ta reda på om det finns återstående adress utrymme för ytterligare undernät som är värdar för dina nödvändiga virtuella datorer, baserat på dina behov.</span><span class="sxs-lookup"><span data-stu-id="caea5-145">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements.</span></span> <span data-ttu-id="caea5-146">Om du inte har kvar adress utrymmet för ytterligare ett undernät kan du skapa ett ytterligare virtuellt nätverk som har sin egen VPN-anslutning för plats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-146">If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="caea5-147">Planera ändringar i infrastrukturs infrastrukturen för Azure Virtual Network</span><span class="sxs-lookup"><span data-stu-id="caea5-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="caea5-148">Du måste konfigurera den lokala infrastruktur infrastrukturen för att vidarekoppla trafik till den lokala VPN-enhet som är värd för det virtuella Azure-nätverkets adress utrymme.</span><span class="sxs-lookup"><span data-stu-id="caea5-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="caea5-149">Exakt hur du uppdaterar infrastrukturen för routning beror på hur du hanterar routningsinformation, som kan vara:</span><span class="sxs-lookup"><span data-stu-id="caea5-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="caea5-150">Uppdateringar för routningstabell baserat på manuell konfiguration.</span><span class="sxs-lookup"><span data-stu-id="caea5-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="caea5-151">Uppdateringar för routningstabell baserat på routningsprotokoll, till exempel RIP (Routing Information Protocol) eller Open Shortest Path First (OSPF).</span><span class="sxs-lookup"><span data-stu-id="caea5-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="caea5-152">Råd fråga din routningsgrupp för att se till att trafiken till den lokala VPN-enheten vidarebefordras till den.</span><span class="sxs-lookup"><span data-stu-id="caea5-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="caea5-153">Planera för brand Väggs regler för trafik till och från den lokala VPN-enheten</span><span class="sxs-lookup"><span data-stu-id="caea5-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="caea5-154">Om din VPN-enhet finns i ett perimeternätverk med en brand vägg mellan perimeternätverket och Internet kan du behöva konfigurera brand väggen för följande regler för att tillåta VPN-anslutningen för webbplats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="caea5-155">Trafik till VPN-enheten (inkommande från Internet):</span><span class="sxs-lookup"><span data-stu-id="caea5-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="caea5-156">Mål-IP-adress för VPN-enhet och IP-protokoll 50</span><span class="sxs-lookup"><span data-stu-id="caea5-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="caea5-157">Mål-IP-adress för VPN-enhet och UDP-målport 500</span><span class="sxs-lookup"><span data-stu-id="caea5-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="caea5-158">Mål-IP-adress för VPN-enhet och UDP-målport 4500</span><span class="sxs-lookup"><span data-stu-id="caea5-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="caea5-159">Trafik från VPN-enheten (utgående till Internet):</span><span class="sxs-lookup"><span data-stu-id="caea5-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="caea5-160">Käll-IP-adress för VPN-enhet och IP-protokoll 50</span><span class="sxs-lookup"><span data-stu-id="caea5-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="caea5-161">Käll-IP-adress för VPN-enhet och UDP-källport 500</span><span class="sxs-lookup"><span data-stu-id="caea5-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="caea5-162">Käll-IP-adress för VPN-enhet och UDP-källport 4500</span><span class="sxs-lookup"><span data-stu-id="caea5-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="caea5-163">Planera för det privata IP-adressutrymmet för Azure Virtual Network</span><span class="sxs-lookup"><span data-stu-id="caea5-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="caea5-164">Det privata IP-adressutrymmet för Azure Virtual Network måste kunna hantera adresser som används av Azure för att hantera det virtuella nätverket och med minst ett undernät som har tillräckligt med adresser för dina virtuella Azure-datorer.</span><span class="sxs-lookup"><span data-stu-id="caea5-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="caea5-165">Om du vill ta reda på antalet adresser som behövs för under nätet kan du räkna antalet virtuella datorer du behöver nu, uppskatta för framtida tillväxt och sedan använda tabellen nedan för att bestämma storleken på under nätet.</span><span class="sxs-lookup"><span data-stu-id="caea5-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="caea5-166">**Antal virtuella datorer som behövs**</span><span class="sxs-lookup"><span data-stu-id="caea5-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="caea5-167">**Antal värd bitar som behövs**</span><span class="sxs-lookup"><span data-stu-id="caea5-167">**Number of host bits needed**</span></span>|<span data-ttu-id="caea5-168">**Storlek på under nätet**</span><span class="sxs-lookup"><span data-stu-id="caea5-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="caea5-169">1-3</span><span class="sxs-lookup"><span data-stu-id="caea5-169">1-3</span></span>  <br/> |<span data-ttu-id="caea5-170">amp;3D</span><span class="sxs-lookup"><span data-stu-id="caea5-170">3</span></span>  <br/> |<span data-ttu-id="caea5-171">/29</span><span class="sxs-lookup"><span data-stu-id="caea5-171">/29</span></span>  <br/> |
|<span data-ttu-id="caea5-172">4-11</span><span class="sxs-lookup"><span data-stu-id="caea5-172">4-11</span></span>  <br/> |<span data-ttu-id="caea5-173">9.4</span><span class="sxs-lookup"><span data-stu-id="caea5-173">4</span></span>  <br/> |<span data-ttu-id="caea5-174">/28</span><span class="sxs-lookup"><span data-stu-id="caea5-174">/28</span></span>  <br/> |
|<span data-ttu-id="caea5-175">12-27</span><span class="sxs-lookup"><span data-stu-id="caea5-175">12-27</span></span>  <br/> |<span data-ttu-id="caea5-176">T5</span><span class="sxs-lookup"><span data-stu-id="caea5-176">5</span></span>  <br/> |<span data-ttu-id="caea5-177">/27</span><span class="sxs-lookup"><span data-stu-id="caea5-177">/27</span></span>  <br/> |
|<span data-ttu-id="caea5-178">28-59</span><span class="sxs-lookup"><span data-stu-id="caea5-178">28-59</span></span>  <br/> |<span data-ttu-id="caea5-179">18.6</span><span class="sxs-lookup"><span data-stu-id="caea5-179">6</span></span>  <br/> |<span data-ttu-id="caea5-180">/26</span><span class="sxs-lookup"><span data-stu-id="caea5-180">/26</span></span>  <br/> |
|<span data-ttu-id="caea5-181">60-123</span><span class="sxs-lookup"><span data-stu-id="caea5-181">60-123</span></span>  <br/> |<span data-ttu-id="caea5-182">borttagning</span><span class="sxs-lookup"><span data-stu-id="caea5-182">7</span></span>  <br/> |<span data-ttu-id="caea5-183">/25</span><span class="sxs-lookup"><span data-stu-id="caea5-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="caea5-184">Planera kalkyl blad för att konfigurera ditt Azure Virtual Network</span><span class="sxs-lookup"><span data-stu-id="caea5-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="caea5-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="caea5-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="caea5-186">Innan du skapar ett virtuellt Azure-nätverk för att vara värd för virtuella datorer måste du bestämma vilka inställningar som behövs i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="caea5-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="caea5-187">Fyll i tabell V för att få inställningar för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="caea5-188">**Tabell V: konfiguration för lokalt nätverk**</span><span class="sxs-lookup"><span data-stu-id="caea5-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="caea5-189">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="caea5-189">**Item**</span></span>|<span data-ttu-id="caea5-190">**Konfigurations element**</span><span class="sxs-lookup"><span data-stu-id="caea5-190">**Configuration element**</span></span>|<span data-ttu-id="caea5-191">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="caea5-191">**Description**</span></span>|<span data-ttu-id="caea5-192">**Värde**</span><span class="sxs-lookup"><span data-stu-id="caea5-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="caea5-193">1.</span><span class="sxs-lookup"><span data-stu-id="caea5-193">1.</span></span>  <br/> |<span data-ttu-id="caea5-194">Virtuellt nätverks namn</span><span class="sxs-lookup"><span data-stu-id="caea5-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="caea5-195">Ett namn som ska tilldelas Azure Virtual Network (exempel DirSyncNet).</span><span class="sxs-lookup"><span data-stu-id="caea5-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="caea5-197">2.</span><span class="sxs-lookup"><span data-stu-id="caea5-197">2.</span></span>  <br/> |<span data-ttu-id="caea5-198">Virtuell nätverks plats</span><span class="sxs-lookup"><span data-stu-id="caea5-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="caea5-199">Azure-datacentret som kommer att innehålla det virtuella nätverket (till exempel västra USA).</span><span class="sxs-lookup"><span data-stu-id="caea5-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="caea5-201">3.</span><span class="sxs-lookup"><span data-stu-id="caea5-201">3.</span></span>  <br/> |<span data-ttu-id="caea5-202">IP-adress för VPN-enhet</span><span class="sxs-lookup"><span data-stu-id="caea5-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="caea5-203">Offentlig IPv4-adress för din VPN-enhets gränssnitt på Internet.</span><span class="sxs-lookup"><span data-stu-id="caea5-203">The public IPv4 address of your VPN device's interface on the Internet.</span></span> <span data-ttu-id="caea5-204">Arbeta med IT-avdelningen för att bestämma den här adressen.</span><span class="sxs-lookup"><span data-stu-id="caea5-204">Work with your IT department to determine this address.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="caea5-206">4.</span><span class="sxs-lookup"><span data-stu-id="caea5-206">4.</span></span>  <br/> |<span data-ttu-id="caea5-207">Adress utrymme för virtuellt nätverk</span><span class="sxs-lookup"><span data-stu-id="caea5-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="caea5-208">Adress utrymmet (definierat i ett prefix för enskilda privata adresser) för det virtuella nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-208">The address space (defined in a single private address prefix) for the virtual network.</span></span> <span data-ttu-id="caea5-209">Arbeta med IT-avdelningen för att ta reda på det här adress utrymmet.</span><span class="sxs-lookup"><span data-stu-id="caea5-209">Work with your IT department to determine this address space.</span></span> <span data-ttu-id="caea5-210">Adress utrymmet bör vara i CIDR-format (Classless Interdomain Routing), som även kallas för nätverksprefix.</span><span class="sxs-lookup"><span data-stu-id="caea5-210">The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="caea5-211">Ett exempel är 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="caea5-211">An example is 10.24.64.0/20.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="caea5-213">5.</span><span class="sxs-lookup"><span data-stu-id="caea5-213">5.</span></span>  <br/> |<span data-ttu-id="caea5-214">Delad IPsec-nycklar</span><span class="sxs-lookup"><span data-stu-id="caea5-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="caea5-215">En 32-tecken slumpmässig, alfanumerisk sträng som används för att autentisera båda sidor av VPN-anslutningen för webbplats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-215">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="caea5-216">Arbeta med din IT-eller säkerhets avdelning för att fastställa det här nyckelvärdet och spara det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-216">Work with your IT or security department to determine this key value and then store it in a secure location.</span></span> <span data-ttu-id="caea5-217">Du kan också läsa [skapa en slumpmässig sträng för en förutdelad IPsec-produktnyckel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span><span class="sxs-lookup"><span data-stu-id="caea5-217">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="caea5-219">Fyll i tabell S för under nätet i den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="caea5-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="caea5-220">För det första under nätet bestämmer du ett 28-bitars adress utrymme (med en/28 prefixlängd) för Azure Gateway-undernätet.</span><span class="sxs-lookup"><span data-stu-id="caea5-220">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet.</span></span> <span data-ttu-id="caea5-221">Se [Beräkna adress utrymmet för gateway-adressundernät för virtuella Azure-nätverk](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/) för information om hur du tar reda på det här adress utrymmet.</span><span class="sxs-lookup"><span data-stu-id="caea5-221">See [Calculating the gateway subnet address space for Azure virtual networks](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="caea5-222">För det andra under nätet anger du ett eget namn, ett enskilt IP-adressutrymmet baserat på adress utrymmet för det virtuella nätverket och ett beskrivande syfte.</span><span class="sxs-lookup"><span data-stu-id="caea5-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="caea5-223">Arbeta med IT-avdelningen för att fastställa dessa adress utrymmen från det virtuella nätverkets adress utrymme.</span><span class="sxs-lookup"><span data-stu-id="caea5-223">Work with your IT department to determine these address spaces from the virtual network address space.</span></span> <span data-ttu-id="caea5-224">Båda adress utrymmen bör vara i CIDR-format.</span><span class="sxs-lookup"><span data-stu-id="caea5-224">Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="caea5-225">**Tabell S: undernät i det virtuella nätverket**</span><span class="sxs-lookup"><span data-stu-id="caea5-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="caea5-226">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="caea5-226">**Item**</span></span>|<span data-ttu-id="caea5-227">**Namn på undernät**</span><span class="sxs-lookup"><span data-stu-id="caea5-227">**Subnet name**</span></span>|<span data-ttu-id="caea5-228">**Adress utrymme för undernät**</span><span class="sxs-lookup"><span data-stu-id="caea5-228">**Subnet address space**</span></span>|<span data-ttu-id="caea5-229">**Ändamål**</span><span class="sxs-lookup"><span data-stu-id="caea5-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="caea5-230">1.</span><span class="sxs-lookup"><span data-stu-id="caea5-230">1.</span></span>  <br/> |<span data-ttu-id="caea5-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="caea5-231">GatewaySubnet</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="caea5-233">Under nätet som används av Azure Gateway.</span><span class="sxs-lookup"><span data-stu-id="caea5-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="caea5-234">2.</span><span class="sxs-lookup"><span data-stu-id="caea5-234">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="caea5-238">Fyll i tabell D för de lokala DNS-servrar som du vill att de virtuella datorerna i det virtuella nätverket ska använda. ge varje DNS-Server ett eget namn och en enda IP-adress.</span><span class="sxs-lookup"><span data-stu-id="caea5-238">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address.</span></span> <span data-ttu-id="caea5-239">Det eget namnet behöver inte matcha värd namnet eller dator namnet för DNS-servern.</span><span class="sxs-lookup"><span data-stu-id="caea5-239">This friendly name does not need to match the host name or computer name of the DNS server.</span></span> <span data-ttu-id="caea5-240">Observera att två tomma poster visas, men du kan lägga till fler.</span><span class="sxs-lookup"><span data-stu-id="caea5-240">Note that two blank entries are listed, but you can add more.</span></span> <span data-ttu-id="caea5-241">Arbeta med IT-avdelningen för att fastställa den här listan.</span><span class="sxs-lookup"><span data-stu-id="caea5-241">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="caea5-242">**Tabell D: lokala DNS-servrar**</span><span class="sxs-lookup"><span data-stu-id="caea5-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="caea5-243">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="caea5-243">**Item**</span></span>|<span data-ttu-id="caea5-244">**Eget namn på DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="caea5-244">**DNS server friendly name**</span></span>|<span data-ttu-id="caea5-245">**IP-adress för DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="caea5-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="caea5-246">1.</span><span class="sxs-lookup"><span data-stu-id="caea5-246">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="caea5-249">2.</span><span class="sxs-lookup"><span data-stu-id="caea5-249">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="caea5-252">Om du vill dirigera paket från det virtuella Azure-nätverket till organisationens nätverk via VPN-anslutningen för webbplats-till-plats måste du konfigurera det virtuella nätverket med ett lokalt nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-252">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network.</span></span> <span data-ttu-id="caea5-253">Det här lokala nätverket har en lista med adress utrymmen (i CIDR-format) för alla platser i organisationens lokala nätverk som de virtuella datorerna måste nå.</span><span class="sxs-lookup"><span data-stu-id="caea5-253">This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach.</span></span> <span data-ttu-id="caea5-254">Detta kan vara alla platser i det lokala nätverket eller en del uppsättning.</span><span class="sxs-lookup"><span data-stu-id="caea5-254">This can be all of the locations on the on-premises network or a subset.</span></span> <span data-ttu-id="caea5-255">Listan med adress utrymmen som definierar ditt lokala nätverk måste vara unikt och får inte överlappa adresserna som används för det här virtuella nätverket eller andra lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-255">The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="caea5-256">För uppsättningen med lokala nätverks adress utrymmen fyller du i tabell L. Lägg märke till att tre tomma poster visas, men att du oftast behöver mer.</span><span class="sxs-lookup"><span data-stu-id="caea5-256">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="caea5-257">Arbeta med IT-avdelningen för att fastställa den här listan.</span><span class="sxs-lookup"><span data-stu-id="caea5-257">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="caea5-258">**Tabell L: adressprefix för det lokala nätverket**</span><span class="sxs-lookup"><span data-stu-id="caea5-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="caea5-259">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="caea5-259">**Item**</span></span>|<span data-ttu-id="caea5-260">**Lokala nätverks adress utrymmet**</span><span class="sxs-lookup"><span data-stu-id="caea5-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="caea5-261">1.</span><span class="sxs-lookup"><span data-stu-id="caea5-261">1.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="caea5-263">2.</span><span class="sxs-lookup"><span data-stu-id="caea5-263">2.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="caea5-265">3.</span><span class="sxs-lookup"><span data-stu-id="caea5-265">3.</span></span>  <br/> |![linjetyp](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="caea5-267">Distributions översikt</span><span class="sxs-lookup"><span data-stu-id="caea5-267">Deployment roadmap</span></span>
<span data-ttu-id="caea5-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="caea5-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="caea5-269">Att skapa det lokala virtuella nätverket och lägga till virtuella datorer i Azure består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="caea5-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="caea5-270">Fas 1: förbereda det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="caea5-271">Fas 2: skapa det lokala virtuella nätverket i Azure.</span><span class="sxs-lookup"><span data-stu-id="caea5-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="caea5-272">Phase 3 (valfritt): lägga till virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="caea5-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="caea5-273">Fas 1: förbereda ditt lokala nätverk</span><span class="sxs-lookup"><span data-stu-id="caea5-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="caea5-274">Du måste konfigurera det lokala nätverket med en väg som pekar på och slutligen levererar trafik till det virtuella nätverkets adress utrymme till routern på kanten av det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-274">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network.</span></span> <span data-ttu-id="caea5-275">Kontakta nätverks administratören för att få reda på hur du lägger till vägen i infrastrukturen för det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="caea5-275">Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="caea5-276">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="caea5-276">Here is your resulting configuration.</span></span>
  
![Det lokala nätverket måste ha en väg för det virtuella nätverkets adress utrymme som pekar mot VPN-enheten.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="caea5-278">Fas 2: skapa det lokala virtuella nätverket i Azure</span><span class="sxs-lookup"><span data-stu-id="caea5-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="caea5-279">Öppna först en Azure PowerShell-kommandotolk.</span><span class="sxs-lookup"><span data-stu-id="caea5-279">First, open an Azure PowerShell prompt.</span></span> <span data-ttu-id="caea5-280">Om du inte har installerat Azure PowerShell läser du [komma igång med Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="caea5-280">If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="caea5-281">Logga sedan in på ditt Azure-konto med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="caea5-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="caea5-282">Hämta ditt prenumerationsnamn med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="caea5-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="caea5-283">Ställ in ditt Azure-abonnemang med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="caea5-283">Set your Azure subscription with these commands.</span></span> <span data-ttu-id="caea5-284">Ersätt allt inom citat tecken, inklusive < och > tecken, med rätt prenumerations namn.</span><span class="sxs-lookup"><span data-stu-id="caea5-284">Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="caea5-285">Skapa sedan en ny resurs grupp för ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-285">Next, create a new resource group for your virtual network.</span></span> <span data-ttu-id="caea5-286">Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.</span><span class="sxs-lookup"><span data-stu-id="caea5-286">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="caea5-287">Skapa den nya resursgruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="caea5-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="caea5-288">Sedan skapar du Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="caea5-288">Next, you create the Azure virtual network.</span></span>
  
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

<span data-ttu-id="caea5-289">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="caea5-289">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket är ännu inte anslutet till det lokala nätverket.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="caea5-291">Använd sedan dessa kommandon för att skapa gatewayen för VPN-anslutningen för webbplats-till-plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
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

<span data-ttu-id="caea5-292">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="caea5-292">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket har nu en gateway.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="caea5-294">Konfigurera sedan din lokala VPN-enhet för att ansluta till Azure VPN gateway.</span><span class="sxs-lookup"><span data-stu-id="caea5-294">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="caea5-295">Mer information finns i [om VPN-enheter för virtuella Azure-anslutningar mellan](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)webbplatser.</span><span class="sxs-lookup"><span data-stu-id="caea5-295">For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="caea5-296">För att konfigurera din VPN-enhet behöver du följande:</span><span class="sxs-lookup"><span data-stu-id="caea5-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="caea5-297">Den offentliga IPv4-adressen för Azure VPN gateway för ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="caea5-298">Använd kommandot **Get-AzPublicIpAddress-Name $vnetGatewayIpConfigName-ResourceGroupName $rgName** för att visa denna adress.</span><span class="sxs-lookup"><span data-stu-id="caea5-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="caea5-299">Den fördelade IPsec-länken för VPN för webbplats-till-plats (tabell V-post 5-värde-kolumnen).</span><span class="sxs-lookup"><span data-stu-id="caea5-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="caea5-300">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="caea5-300">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket är nu anslutet till det lokala nätverket.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="caea5-302">Phase 3 (valfritt): lägga till virtuella datorer</span><span class="sxs-lookup"><span data-stu-id="caea5-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="caea5-303">Skapa de virtuella datorerna du behöver i Azure.</span><span class="sxs-lookup"><span data-stu-id="caea5-303">Create the virtual machines you need in Azure.</span></span> <span data-ttu-id="caea5-304">Mer information finns i [skapa en virtuell Windows-dator med Azure-portalen](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span><span class="sxs-lookup"><span data-stu-id="caea5-304">For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="caea5-305">Använd följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="caea5-305">Use the following settings:</span></span>
  
- <span data-ttu-id="caea5-306">På fliken **grundläggande** väljer du samma prenumeration och resurs grupp som ditt virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="caea5-306">On the **Basics** tab, select the same subscription and resource group as your virtual network.</span></span> <span data-ttu-id="caea5-307">Du behöver dessa senare för att logga in på den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="caea5-307">You will need these later to sign in to the virtual machine.</span></span> <span data-ttu-id="caea5-308">I avsnittet **instans information** väljer du en lämplig virtuell dator storlek.</span><span class="sxs-lookup"><span data-stu-id="caea5-308">In the **Instance details** section, choose the appropriate virtual machine size.</span></span> <span data-ttu-id="caea5-309">Spela in användar namnet och lösen ordet för administratörs kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="caea5-309">Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="caea5-310">På fliken **nätverk** väljer du namnet på ditt virtuella nätverk och under nätet för att vara värd för virtuella datorer (inte GatewaySubnet).</span><span class="sxs-lookup"><span data-stu-id="caea5-310">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet).</span></span> <span data-ttu-id="caea5-311">Lämna övriga inställningar till standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="caea5-311">Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="caea5-312">Kontrol lera att din virtuella dator använder DNS på rätt sätt genom att kontrol lera den interna DNS-servern för att se till att adress posterna (A) har lagts till för en ny virtuell dator.</span><span class="sxs-lookup"><span data-stu-id="caea5-312">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine.</span></span> <span data-ttu-id="caea5-313">För att få åtkomst till Internet måste dina virtuella Azure-datorer vara konfigurerade för att använda det lokala nätverkets proxyserver.</span><span class="sxs-lookup"><span data-stu-id="caea5-313">To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server.</span></span> <span data-ttu-id="caea5-314">Kontakta nätverks administratören för ytterligare konfigurations steg för servern.</span><span class="sxs-lookup"><span data-stu-id="caea5-314">Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="caea5-315">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="caea5-315">Here is your resulting configuration.</span></span>
  
![Det virtuella nätverket hanterar nu virtuella datorer som är tillgängliga från det lokala nätverket.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="caea5-317">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="caea5-317">Next step</span></span>
  
[<span data-ttu-id="caea5-318">Distribuera Microsoft 365-profilsynkronisering i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="caea5-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)
