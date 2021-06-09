---
title: Nätverk för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå Contoso-nätverksinfrastrukturen och hur företaget använder sin SD-WAN-teknik för optimala nätverksprestanda för att Microsoft 365 företagmolntjänster.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754020"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="9b626-103">Nätverk för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="9b626-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="9b626-104">För att införa en molnomfattande infrastruktur har Contoso utformat ett grundläggande skift för hur nätverkstrafik till molntjänster färdas.</span><span class="sxs-lookup"><span data-stu-id="9b626-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="9b626-105">I stället för en intern modell med hub-and-ekrar som fokuserar nätverksanslutning och trafik för nästa nivå av Office-hierarkin mappade de användarplatser till lokal internetpunkt och lokala anslutningar till närmaste Microsoft 365-nätverksplats på internet.</span><span class="sxs-lookup"><span data-stu-id="9b626-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="9b626-106">Nätverksinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="9b626-106">Networking infrastructure</span></span>

<span data-ttu-id="9b626-107">Det här är de nätverkselement som kopplar samman Contosos kontor över hela världen:</span><span class="sxs-lookup"><span data-stu-id="9b626-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="9b626-108">MPLS-WAN-nätverk</span><span class="sxs-lookup"><span data-stu-id="9b626-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="9b626-109">Ett MPLS WAN-nätverk ansluter Paris huvudkontor till regionala kontor och regionala kontor till satellitkontor i en ek-och-hubb-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b626-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="9b626-110">Nätverket gör det möjligt för användare att få åtkomst till lokala servrar som består av affärsprogram i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="9b626-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="9b626-111">Den dirigerar även all allmän internettrafik till Paris kontor, där nätverkssäkerhetsenheter skrubbar förfrågningarna.</span><span class="sxs-lookup"><span data-stu-id="9b626-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="9b626-112">Inom varje kontor levererar routrar trafik till trådanslutna och trådlösa åtkomstpunkter i undernät, som använder det privata IP-adressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="9b626-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="9b626-113">Lokal direkt internetanslutning för Microsoft 365 trafik</span><span class="sxs-lookup"><span data-stu-id="9b626-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="9b626-114">Varje kontor har en programvarudefinierad WAN-enhet (WAN) som har en eller flera lokala internetnätverkskretsar via Internet via en proxyserver.</span><span class="sxs-lookup"><span data-stu-id="9b626-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="9b626-115">Lösningen implementeras vanligtvis som en WAN-länk till en lokal Internetleverantör, som även tillhandahåller offentliga IP-adresser och en lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="9b626-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="9b626-116">Internet-närvaro</span><span class="sxs-lookup"><span data-stu-id="9b626-116">Internet presence</span></span>

  <span data-ttu-id="9b626-117">Contoso äger det offentliga domännamnet contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="9b626-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="9b626-118">Den offentliga Contoso-webbplatsen för produktorder är en uppsättning servrar i ett internetanslutet datacenter i Paris campus.</span><span class="sxs-lookup"><span data-stu-id="9b626-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="9b626-119">Contoso använder ett /24 offentligt IP-adressintervall på Internet.</span><span class="sxs-lookup"><span data-stu-id="9b626-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="9b626-120">Bild 1 visar Contosos nätverksinfrastruktur och dess anslutningar till Internet.</span><span class="sxs-lookup"><span data-stu-id="9b626-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso-nätverket](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="9b626-122">**Bild 1: Contoso-nätverket**</span><span class="sxs-lookup"><span data-stu-id="9b626-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="9b626-123">Användning av SD-WAN för optimal nätverksanslutning till Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b626-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="9b626-124">Contoso följde [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) för att:</span><span class="sxs-lookup"><span data-stu-id="9b626-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="9b626-125">Identifiera och särskilja Microsoft 365-nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="9b626-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="9b626-126">Utgående nätverksanslutningar lokalt</span><span class="sxs-lookup"><span data-stu-id="9b626-126">Egress network connections locally</span></span>
- <span data-ttu-id="9b626-127">Undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="9b626-127">Avoid network hairpins</span></span>
- <span data-ttu-id="9b626-128">Kringgå dubblerade enheter för nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="9b626-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="9b626-129">Det finns tre kategorier av nätverkstrafik för Microsoft 365: *Optimera,* *Tillåt* och *Standard.*</span><span class="sxs-lookup"><span data-stu-id="9b626-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="9b626-130">Optimera och tillåt trafik är betrodd nätverkstrafik som är krypterad och säker på slutpunkterna och är avsedd för det Microsoft 365 nätverket.</span><span class="sxs-lookup"><span data-stu-id="9b626-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="9b626-131">Contoso fattade beslutet att:</span><span class="sxs-lookup"><span data-stu-id="9b626-131">Contoso decided to:</span></span>

- <span data-ttu-id="9b626-132">Använd direkt utgående Internet för optimera och tillåt kategoritrafik och för att vidarebefordra all standardkategoritrafik till den parisbaserade centrala Internetanslutningen.</span><span class="sxs-lookup"><span data-stu-id="9b626-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="9b626-133">Distribuera SD-WAN-enheter på varje kontor som ett enkelt sätt att följa de här principerna och få optimala nätverksprestanda för Microsoft 365 molnbaserade tjänster.</span><span class="sxs-lookup"><span data-stu-id="9b626-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="9b626-134">SD-WAN-enheterna har en LAN-port för det lokala kontorsnätverket och flera WAN-portar.</span><span class="sxs-lookup"><span data-stu-id="9b626-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="9b626-135">En WAN-port ansluter till sitt MPLS-nätverk.</span><span class="sxs-lookup"><span data-stu-id="9b626-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="9b626-136">En annan ansluter till en lokal ISP-krets.</span><span class="sxs-lookup"><span data-stu-id="9b626-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="9b626-137">SD-WAN-enheten dirigerar nätverkstrafik i kategorierna Optimera och Tillåt via Internetleverantörslänken.</span><span class="sxs-lookup"><span data-stu-id="9b626-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="9b626-138">Infrastrukturen för appen Contoso-affärsprogrammet</span><span class="sxs-lookup"><span data-stu-id="9b626-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="9b626-139">Contoso har byggt sin infrastruktur för branschprogram och server intranät för följande:</span><span class="sxs-lookup"><span data-stu-id="9b626-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="9b626-140">Satellitkontor använder lokala cache-servrar för att lagra dokument som används ofta och interna webbplatser.</span><span class="sxs-lookup"><span data-stu-id="9b626-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="9b626-141">Regionala nav använder regionala programservrar för region- och satellitkontor.</span><span class="sxs-lookup"><span data-stu-id="9b626-141">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="9b626-142">Servrarna synkroniseras med servrar på huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="9b626-142">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="9b626-143">Datacenter i Paris campus innehåller centraliserade programservrar som används av hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="9b626-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="9b626-144">I bild 2 visas den procentandel av nätverkskapaciteten som används vid åtkomst av servrar i Contoso-intranätet.</span><span class="sxs-lookup"><span data-stu-id="9b626-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Contoso-infrastrukturen för interna program](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="9b626-146">**Bild 2: Contoso-infrastrukturen för interna program**</span><span class="sxs-lookup"><span data-stu-id="9b626-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="9b626-147">För satellit- eller regionala navkontor kan 60 procent av de anställdas resurser användas av satellit- och regionala navkontorsservrar.</span><span class="sxs-lookup"><span data-stu-id="9b626-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="9b626-148">Ytterligare 40 procent av resursförfrågningarna måste gå över WAN-länken till Paris campus.</span><span class="sxs-lookup"><span data-stu-id="9b626-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="9b626-149">Nätverksanalys och förberedelse inför Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="9b626-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="9b626-150">Ett lyckat införande Microsoft 365 företagstjänster av Contoso-användare är beroende av att Contoso-användarna är tillgängliga och är uppkopplade direkt till Internet eller direkt till Microsofts molntjänster.</span><span class="sxs-lookup"><span data-stu-id="9b626-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="9b626-151">Contoso har gjort följande för att planera och implementera optimerad anslutning för Microsoft 365 för molntjänster för företag:</span><span class="sxs-lookup"><span data-stu-id="9b626-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="9b626-152">Skapa ett företags WAN-nätverksdiagram för planering</span><span class="sxs-lookup"><span data-stu-id="9b626-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="9b626-153">Contoso började sin nätverksplanering genom att skapa ett diagram som visar deras kontorsplatser, befintliga nätverksanslutningar, befintliga perimeterenheter för nätverket och klasser för tjänster som hanteras i nätverket.</span><span class="sxs-lookup"><span data-stu-id="9b626-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="9b626-154">De använde diagrammet för varje efterföljande steg under planering och implementering av nätverksanslutningen.</span><span class="sxs-lookup"><span data-stu-id="9b626-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="9b626-155">Skapa en plan för Microsoft 365 för företagsnätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="9b626-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="9b626-156">Contoso använde [Microsoft 365](microsoft-365-network-connectivity-principles.md) principer för nätverksanslutning och nätverksarkitekturer för exempelreferenser för att identifiera SD-WAN som primär topologi för Microsoft 365 anslutning.</span><span class="sxs-lookup"><span data-stu-id="9b626-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="9b626-157">Analysera användningen av Internetanslutning och MPLS-WAN-bandbredd på varje kontor, och öka bandbredden vid behov</span><span class="sxs-lookup"><span data-stu-id="9b626-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="9b626-158">Varje kontors aktuella användning analyserades och kretsarna utökades så att förutsägelsen Microsoft 365 molnbaserad trafik skulle fungera med i genomsnitt 20 procents oanvänd kapacitet.</span><span class="sxs-lookup"><span data-stu-id="9b626-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="9b626-159">Optimera prestanda för Microsofts nätverkstjänster</span><span class="sxs-lookup"><span data-stu-id="9b626-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="9b626-160">Contoso bestämde uppsättningen Office 365, Intune och Azure-slutpunkter och konfigurerade brandväggar, säkerhetsenheter och andra system i Internetsökvägen för optimala prestanda.</span><span class="sxs-lookup"><span data-stu-id="9b626-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="9b626-161">Slutpunkter för Office 365 optimera och tillåt kategoritrafik konfigurerades i SD-WAN-enheter för dirigering över ISP-kretsen.</span><span class="sxs-lookup"><span data-stu-id="9b626-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="9b626-162">Konfigurera intern DNS</span><span class="sxs-lookup"><span data-stu-id="9b626-162">Configure internal DNS</span></span>

   <span data-ttu-id="9b626-163">DNS måste fungera och letas upp lokalt för Microsoft 365-trafik.</span><span class="sxs-lookup"><span data-stu-id="9b626-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="9b626-164">Validera nätverksslutpunkt och portanslutning</span><span class="sxs-lookup"><span data-stu-id="9b626-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="9b626-165">Contoso körde testverktygen för Microsoft-nätverksanslutning för att validera Microsoft 365 för företagmolntjänster.</span><span class="sxs-lookup"><span data-stu-id="9b626-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="9b626-166">Optimera nätverksanslutningar för anställdas datorer</span><span class="sxs-lookup"><span data-stu-id="9b626-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="9b626-167">Enskilda datorer har kontrollerats för att säkerställa att de senaste uppdateringarna av operativsystemet installerades och att säkerhetsövervakning av slutpunkten var aktiv på alla klienter.</span><span class="sxs-lookup"><span data-stu-id="9b626-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="9b626-168">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9b626-168">Next step</span></span>

<span data-ttu-id="9b626-169">Lär dig hur Contoso utnyttjar sina lokala [Active Directory Domain Services](contoso-identity.md) i molnet för anställda och federera autentisering för kunder och affärspartner.</span><span class="sxs-lookup"><span data-stu-id="9b626-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b626-170">Se även</span><span class="sxs-lookup"><span data-stu-id="9b626-170">See also</span></span>

[<span data-ttu-id="9b626-171">Nätverksöversikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b626-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="9b626-172">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="9b626-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9b626-173">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="9b626-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
