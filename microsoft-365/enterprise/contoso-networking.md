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
description: Förstå nätverks infrastrukturen contoso och hur företaget använder sin SD-WAN-teknik för optimal nätverks prestanda till Microsoft 365 för företags moln tjänster.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754020"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="c438f-103">Nätverk för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="c438f-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="c438f-104">För att kunna använda molnbaserade infrastrukturer har Contoso en grundläggande skift på hur nätverks trafik till moln tjänster flyttas.</span><span class="sxs-lookup"><span data-stu-id="c438f-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="c438f-105">I stället för en intern modell för nav-och-eker som fokuserar på nätverks anslutning och trafik för nästa nivå i Office-hierarkin, mappas användarna till lokala Internet-avslut-och lokala anslutningar till den närmaste Microsoft 365-nätverks platsen på Internet.</span><span class="sxs-lookup"><span data-stu-id="c438f-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="c438f-106">Nätverks infrastruktur</span><span class="sxs-lookup"><span data-stu-id="c438f-106">Networking infrastructure</span></span>

<span data-ttu-id="c438f-107">Det här är nätverks element som länkar contoso-kontor över hela världen:</span><span class="sxs-lookup"><span data-stu-id="c438f-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="c438f-108">MPLS-WAN-nätverk</span><span class="sxs-lookup"><span data-stu-id="c438f-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="c438f-109">Ett MPLS WAN-nätverk ansluter Paris till lokala kontor och lokala kontor till satellit kontor i en konfiguration med ekrar och nav.</span><span class="sxs-lookup"><span data-stu-id="c438f-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="c438f-110">Nätverket gör att användare kan komma åt lokala servrar som bildar branschspecifika tillämpningar i Paris-kontoret.</span><span class="sxs-lookup"><span data-stu-id="c438f-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="c438f-111">Den dirigerar också all allmän Internet trafik till Paris kontoret, där nätverks säkerhetsenheterna sveper på begäran.</span><span class="sxs-lookup"><span data-stu-id="c438f-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="c438f-112">Inom varje kontor levererar routrar trafik till trådanslutna och trådlösa åtkomstpunkter i undernät, som använder det privata IP-adressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="c438f-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="c438f-113">Lokal direkt Internet åtkomst för Microsoft 365-trafik</span><span class="sxs-lookup"><span data-stu-id="c438f-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="c438f-114">Varje Office har en programdefinierad WAN-enhet (SD-WAN) med en eller flera lokala Internet-nätkretsar med sin egen Internet anslutning via en proxyserver.</span><span class="sxs-lookup"><span data-stu-id="c438f-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="c438f-115">Lösningen implementeras vanligtvis som en WAN-länk till en lokal Internetleverantör, som även tillhandahåller offentliga IP-adresser och en lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="c438f-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="c438f-116">Internet-närvaro</span><span class="sxs-lookup"><span data-stu-id="c438f-116">Internet presence</span></span>

  <span data-ttu-id="c438f-117">Contoso äger det contoso \. com offentlige-domännamnet.</span><span class="sxs-lookup"><span data-stu-id="c438f-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="c438f-118">Den offentliga contoso-webbplatsen för att beställa produkter är en uppsättning servrar i ett Internet-anslutet Data Center i Paris campus.</span><span class="sxs-lookup"><span data-stu-id="c438f-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="c438f-119">Contoso använder ett/24 offentliga IP-adressintervall på Internet.</span><span class="sxs-lookup"><span data-stu-id="c438f-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="c438f-120">Bild 1 visar nätverks infrastrukturen contoso och dess anslutningar till Internet.</span><span class="sxs-lookup"><span data-stu-id="c438f-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso-nätverket](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="c438f-122">**Bild 1: Contoso-nätverket**</span><span class="sxs-lookup"><span data-stu-id="c438f-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="c438f-123">Användning av SD-WAN för optimal nätverksanslutning till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c438f-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="c438f-124">Contoso följde [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) för att:</span><span class="sxs-lookup"><span data-stu-id="c438f-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="c438f-125">Identifiera och särskilja Microsoft 365-nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="c438f-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="c438f-126">Utgående nätverksanslutningar lokalt</span><span class="sxs-lookup"><span data-stu-id="c438f-126">Egress network connections locally</span></span>
- <span data-ttu-id="c438f-127">Undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="c438f-127">Avoid network hairpins</span></span>
- <span data-ttu-id="c438f-128">Kringgå dubblerade enheter för nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="c438f-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="c438f-129">Det finns tre kategorier av nätverks trafik för Microsoft 365: *optimera*, *tillåta*och *standard*.</span><span class="sxs-lookup"><span data-stu-id="c438f-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="c438f-130">Optimera och tillåta trafik är betrodd nätverks trafik som krypteras och skyddas på slut punkterna och är avsedd för Microsoft 365-nätverket.</span><span class="sxs-lookup"><span data-stu-id="c438f-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="c438f-131">Contoso fattade beslutet att:</span><span class="sxs-lookup"><span data-stu-id="c438f-131">Contoso decided to:</span></span>

- <span data-ttu-id="c438f-132">Använd direkt Internet avslut för att optimera och tillåta kategori trafik och vidarebefordra all standard kategori trafik till den Paris centrala Internet anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c438f-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="c438f-133">Distribuera SD-WAN-enheter på varje kontor för att enkelt kunna följa dessa principer och uppnå optimal nätverks prestanda för Microsoft 365-molnbaserade tjänster.</span><span class="sxs-lookup"><span data-stu-id="c438f-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="c438f-134">SD-WAN-enheterna har en LAN-port för det lokala kontorsnätverket och flera WAN-portar.</span><span class="sxs-lookup"><span data-stu-id="c438f-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="c438f-135">En WAN-port ansluter till deras MPLS-nätverk.</span><span class="sxs-lookup"><span data-stu-id="c438f-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="c438f-136">En annan ansluter till en lokal Internet-leverantör.</span><span class="sxs-lookup"><span data-stu-id="c438f-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="c438f-137">SD-WAN-enheten dirigerar nätverkstrafik i kategorierna Optimera och Tillåt via Internetleverantörslänken.</span><span class="sxs-lookup"><span data-stu-id="c438f-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="c438f-138">Program infrastrukturen contoso line of Business</span><span class="sxs-lookup"><span data-stu-id="c438f-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="c438f-139">Contoso har utformat sin infrastruktur för program och Server intranät för följande:</span><span class="sxs-lookup"><span data-stu-id="c438f-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="c438f-140">Satellitkontor använder lokala cache-servrar för att lagra dokument som används ofta och interna webbplatser.</span><span class="sxs-lookup"><span data-stu-id="c438f-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="c438f-141">Regionala nav använder regionala programservrar för region- och satellitkontor.</span><span class="sxs-lookup"><span data-stu-id="c438f-141">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="c438f-142">Servrarna synkroniseras med servrar på huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="c438f-142">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="c438f-143">Paris Campus-datacentren innehåller centraliserade program servrar som tjänar hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="c438f-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="c438f-144">Bild 2 visar hur stor andel av nätverks trafiken som används vid åtkomst till servrar i Contoso-intranätet.</span><span class="sxs-lookup"><span data-stu-id="c438f-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Contoso-infrastrukturen för interna program](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="c438f-146">**Bild 2: contoso-infrastrukturen för interna program**</span><span class="sxs-lookup"><span data-stu-id="c438f-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="c438f-147">För satellit-eller regionala Hubbs kontoret kan 60 procent av de resurser som behövs av de anställda betjänas via satellit-och regionala hubb kontor.</span><span class="sxs-lookup"><span data-stu-id="c438f-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="c438f-148">Ytterligare 40 procent av resurs begär Anden måste gå via WAN-länken till Paris campus.</span><span class="sxs-lookup"><span data-stu-id="c438f-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="c438f-149">Nätverks analys och förberedelse för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c438f-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="c438f-150">Om du har godkänt Microsoft 365 för företags tjänster av Skype-användare beror det på hög tillgänglighet och anslutning till Internet eller direkt till Microsofts moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="c438f-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="c438f-151">Contoso vidtog de här stegen för att planera och implementera optimerad anslutning till Microsoft 365 för företags moln tjänster:</span><span class="sxs-lookup"><span data-stu-id="c438f-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="c438f-152">Skapa ett nätverks diagram för företagets WAN till stöd för planering</span><span class="sxs-lookup"><span data-stu-id="c438f-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="c438f-153">För att kunna starta sin nätverks planering skapar Contoso ett diagram som visar deras Office-platser, befintliga nätverks anslutningar, befintliga nätverks gränser och tjänste klasser som hanteras i nätverket.</span><span class="sxs-lookup"><span data-stu-id="c438f-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="c438f-154">De använde diagrammet för varje efterföljande steg under planering och implementering av nätverksanslutningen.</span><span class="sxs-lookup"><span data-stu-id="c438f-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="c438f-155">Skapa ett abonnemang för Microsoft 365 för företags nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="c438f-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="c438f-156">Contoso använde [principer för nätverks anslutningen för microsoft 365](microsoft-365-network-connectivity-principles.md) och exempel referens nätverks arkitektur för att identifiera SD-WAN som sin bästa topologi för Microsoft 365-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="c438f-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="c438f-157">Analysera Internet-anslutnings användning och MPLS – WAN-bandbredd för varje kontor och öka bandbredden efter behov</span><span class="sxs-lookup"><span data-stu-id="c438f-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="c438f-158">Varje Office-nuvarande användning analyserades och kretsarna har ökats så att den förutsedda Microsoft 365-molnbaserade trafiken skulle fungera med en genomsnittlig oanvänd kapacitet på 20 procent.</span><span class="sxs-lookup"><span data-stu-id="c438f-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="c438f-159">Optimera prestandan till Microsofts nätverks tjänster</span><span class="sxs-lookup"><span data-stu-id="c438f-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="c438f-160">Contoso har fastställt uppsättningen av Office 365-, Intune-och Azure-slutpunkter samt konfigurerade brand väggar, säkerhetsenheter och andra system i Internet-sökvägen för optimal prestanda.</span><span class="sxs-lookup"><span data-stu-id="c438f-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="c438f-161">Slut punkter för Office 365 optimera och Tillåt att kategori trafik konfigurerades till SD-WAN-enheter för routning via Internet-kretsen.</span><span class="sxs-lookup"><span data-stu-id="c438f-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="c438f-162">Konfigurera intern DNS</span><span class="sxs-lookup"><span data-stu-id="c438f-162">Configure internal DNS</span></span>

   <span data-ttu-id="c438f-163">DNS måste fungera och letas upp lokalt för Microsoft 365-trafik.</span><span class="sxs-lookup"><span data-stu-id="c438f-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="c438f-164">Verifiera nätverks slut punkten och port anslutningar</span><span class="sxs-lookup"><span data-stu-id="c438f-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="c438f-165">Contoso körde test verktyg för Microsoft Network connectivity för att verifiera anslutningen för Microsoft 365 för företags moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="c438f-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="c438f-166">Optimera datorns datorer för nätverks anslutningar</span><span class="sxs-lookup"><span data-stu-id="c438f-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="c438f-167">Enskilda datorer markerades för att se till att de senaste operativ system uppdateringarna installerades och att övervakning av slut punkts säkerhet var aktivt för alla klienter.</span><span class="sxs-lookup"><span data-stu-id="c438f-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="c438f-168">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c438f-168">Next step</span></span>

<span data-ttu-id="c438f-169">Lär dig hur Contoso använder [sin lokala Active Directory Domain Services i molnet](contoso-identity.md) för anställda och federering för kunder och affärs partners.</span><span class="sxs-lookup"><span data-stu-id="c438f-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="c438f-170">Se även</span><span class="sxs-lookup"><span data-stu-id="c438f-170">See also</span></span>

[<span data-ttu-id="c438f-171">Nätverks översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c438f-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="c438f-172">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c438f-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c438f-173">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="c438f-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
