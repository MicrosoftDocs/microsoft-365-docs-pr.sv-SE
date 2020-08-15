---
title: Nätverk för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå nätverks infrastrukturen contoso och hur den använder sin SD-WAN-teknik för optimal nätverks prestanda för Microsoft 365 för företags moln tjänster.
ms.openlocfilehash: bc2ae68917258b94ed46ef0c1257f56e0736105c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685824"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="5de1d-103">Nätverk för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="5de1d-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="5de1d-104">För att kunna använda en molnbaserad infrastruktur genomförde Contosos nätverkstekniker den övergripande övergången på samma sätt som nätverkstrafik till molntjänster sker.</span><span class="sxs-lookup"><span data-stu-id="5de1d-104">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels.</span></span> <span data-ttu-id="5de1d-105">I stället för en intern nav- och ekermodell som fokuserar på nätverksanslutning och trafik för nästa nivå i Contosos kontorshierarki, eftersträvade de att mappa användarplatser mot lokal, utgående Internettrafik och lokala anslutningar till närmaste Microsoft 365-nätverksplats på Internet.</span><span class="sxs-lookup"><span data-stu-id="5de1d-105">Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="5de1d-106">Contosos nätverksinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="5de1d-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="5de1d-107">Följande delar i Contosos nätverk länkar sina kontor över hela världen:</span><span class="sxs-lookup"><span data-stu-id="5de1d-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="5de1d-108">MPLS-WAN-nätverk</span><span class="sxs-lookup"><span data-stu-id="5de1d-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="5de1d-109">Ett MPLS WAN-nätverk kopplar samman huvudkontoret i Paris med lokala kontor, och regionala kontor med satellitkontor i en nav- och ekerkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="5de1d-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration.</span></span> <span data-ttu-id="5de1d-110">Avsikten är att användarna ska få åtkomst till de lokala servrar som används för branschtillämpningar på Paris-kontoret.</span><span class="sxs-lookup"><span data-stu-id="5de1d-110">This is for users to access on-premises servers that make up line of business applications in the Paris office.</span></span> <span data-ttu-id="5de1d-111">Den dirigerar även all allmän Internettrafik till Paris-kontoret där enheter för nätverkssäkerhet rensar förfrågningarna.</span><span class="sxs-lookup"><span data-stu-id="5de1d-111">It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests.</span></span> <span data-ttu-id="5de1d-112">Inom varje kontor levererar routrar trafik till trådanslutna och trådlösa åtkomstpunkter i undernät, som använder det privata IP-adressutrymmet.</span><span class="sxs-lookup"><span data-stu-id="5de1d-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="5de1d-113">Lokal, direkt Internet-åtkomst för Microsoft 365-trafik</span><span class="sxs-lookup"><span data-stu-id="5de1d-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="5de1d-114">Varje kontor har en SD WAN-enhet med en eller flera lokala Internetleverantörers nätverkskretsar och en egen Internetanslutning via en proxyserver.</span><span class="sxs-lookup"><span data-stu-id="5de1d-114">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server.</span></span> <span data-ttu-id="5de1d-115">Lösningen implementeras vanligtvis som en WAN-länk till en lokal Internetleverantör, som även tillhandahåller offentliga IP-adresser och en lokal DNS-server.</span><span class="sxs-lookup"><span data-stu-id="5de1d-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="5de1d-116">Internet-närvaro</span><span class="sxs-lookup"><span data-stu-id="5de1d-116">Internet presence</span></span>

  <span data-ttu-id="5de1d-117">Contoso äger det offentliga domännamnet contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5de1d-117">Contoso owns the contoso.com public domain name.</span></span> <span data-ttu-id="5de1d-118">Contosos offentliga webbplats för beställning av produkter är en uppsättning servrar på ett Internetanslutet datacenter på anläggningen i Paris.</span><span class="sxs-lookup"><span data-stu-id="5de1d-118">The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="5de1d-119">Contoso använder ett offentligt /24 IP-adressintervall på Internet.</span><span class="sxs-lookup"><span data-stu-id="5de1d-119">Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="5de1d-120">Bild 1 visar organisationens nätverksinfrastruktur och anslutningar till Internet.</span><span class="sxs-lookup"><span data-stu-id="5de1d-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Contosos nätverk](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="5de1d-122">**Bild 1: Contosos nätverk**</span><span class="sxs-lookup"><span data-stu-id="5de1d-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="5de1d-123">Användning av SD-WAN för optimal nätverksanslutning till Microsoft</span><span class="sxs-lookup"><span data-stu-id="5de1d-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="5de1d-124">Contoso följde [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) för att:</span><span class="sxs-lookup"><span data-stu-id="5de1d-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

1. <span data-ttu-id="5de1d-125">Identifiera och särskilja Microsoft 365-nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="5de1d-125">Identify and differentiate Microsoft 365 network traffic</span></span>
2. <span data-ttu-id="5de1d-126">Utgående nätverksanslutningar lokalt</span><span class="sxs-lookup"><span data-stu-id="5de1d-126">Egress network connections locally</span></span>
3. <span data-ttu-id="5de1d-127">Undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="5de1d-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="5de1d-128">Kringgå dubblerade enheter för nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="5de1d-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="5de1d-129">Det finns tre olika kategorier av nätverkstrafik för Microsoft 365: Optimera, Tillåt och Standard.</span><span class="sxs-lookup"><span data-stu-id="5de1d-129">There are three categories of network traffic for Microsoft 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="5de1d-130">Trafik av typerna Optimera och Tillåt är betrodd nätverkstrafik som krypteras och skyddas vid slutpunkterna och som är avsedd för Microsoft 365-nätverket.</span><span class="sxs-lookup"><span data-stu-id="5de1d-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="5de1d-131">Contoso fattade beslutet att:</span><span class="sxs-lookup"><span data-stu-id="5de1d-131">Contoso decided to:</span></span>

- <span data-ttu-id="5de1d-132">Använda Internetegress för trafik i kategorierna Optimera och Tillåt och vidarebefordra all trafik i kategorin Standard till den Paris-baserade, centrala Internet-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="5de1d-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="5de1d-133">Distribuera SD-WAN-enheter på varje arbetsplats som ett enkelt sätt att följa dessa principer och uppnå optimala nätverksprestanda för molnbaserade Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="5de1d-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="5de1d-134">SD-WAN-enheterna har en LAN-port för det lokala kontorsnätverket och flera WAN-portar.</span><span class="sxs-lookup"><span data-stu-id="5de1d-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="5de1d-135">En WAN-port ansluter till MPLS-nätverket och en annan WAN-port ansluter till en lokal Internetleverantörskrets.</span><span class="sxs-lookup"><span data-stu-id="5de1d-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="5de1d-136">SD-WAN-enheten dirigerar nätverkstrafik i kategorierna Optimera och Tillåt via Internetleverantörslänken.</span><span class="sxs-lookup"><span data-stu-id="5de1d-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="5de1d-137">Contosos infrastruktur för branschtillämpningar</span><span class="sxs-lookup"><span data-stu-id="5de1d-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="5de1d-138">Contoso har utformat sin infrastruktur för branschtillämpningar och serverintranät för följande:</span><span class="sxs-lookup"><span data-stu-id="5de1d-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="5de1d-139">Satellitkontor använder lokala cache-servrar för att lagra dokument som används ofta och interna webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5de1d-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="5de1d-140">Regionala nav använder regionala programservrar för region- och satellitkontor.</span><span class="sxs-lookup"><span data-stu-id="5de1d-140">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="5de1d-141">Servrarna synkroniseras med servrar på huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="5de1d-141">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="5de1d-142">På campus i Paris finns de datacenter som innehåller de centraliserade programservrar som används av hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="5de1d-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="5de1d-143">I bild 2 visas procentandelen nätverkstrafik vid anslutning till servrar på olika platser i Contosos intranät.</span><span class="sxs-lookup"><span data-stu-id="5de1d-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Contosos infrastruktur för interna program](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="5de1d-145">**Bild 2: Contosos infrastruktur för interna program**</span><span class="sxs-lookup"><span data-stu-id="5de1d-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="5de1d-146">För användare på satellitkontor eller regionkontor kan 60 % av de resurser som medarbetarna behöver tillhandahållas av servrar på satellitkontor och regionkontor.</span><span class="sxs-lookup"><span data-stu-id="5de1d-146">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="5de1d-147">Ytterligare 40 % av alla resursbegäranden måste gå via WAN-länken till företagets campus i Paris.</span><span class="sxs-lookup"><span data-stu-id="5de1d-147">The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-for-enterprise"></a><span data-ttu-id="5de1d-148">Organisationens nätverks analys och förberedelse av sitt nätverk för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5de1d-148">Contoso's network analysis and preparation of their network for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="5de1d-149">Om du har godkänt Microsoft 365 för företags tjänster av Skype-användare beror det på hög tillgänglighet och anslutning till Internet, eller direkt till Microsofts moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="5de1d-149">Successful adoption of Microsoft 365 for enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services.</span></span> <span data-ttu-id="5de1d-150">Contoso utförde de här stegen för att planera för och implementera optimerad anslutning till Microsoft 365 för företags moln tjänster:</span><span class="sxs-lookup"><span data-stu-id="5de1d-150">Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="5de1d-151">Skapade ett diagram över företagets WAN-nätverk för att underlätta planeringen</span><span class="sxs-lookup"><span data-stu-id="5de1d-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="5de1d-152">Contoso inledde sin nätverksplanering med att skapa ett diagram som visade deras arbetsplatser, befintliga nätverksanslutningar, enheter inom befintlig nätverksgräns och tjänstklasser som hanteras i nätverket.</span><span class="sxs-lookup"><span data-stu-id="5de1d-152">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network.</span></span> <span data-ttu-id="5de1d-153">De använde diagrammet för varje efterföljande steg under planering och implementering av nätverksanslutningen.</span><span class="sxs-lookup"><span data-stu-id="5de1d-153">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="5de1d-154">Skapat en plan för Microsoft 365 för företags nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="5de1d-154">Created a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="5de1d-155">Contoso använde sig av [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) och tillhandahöll referensnätverksarkitekturer för att utse SD-WAN som föredragen topologi för Microsoft 365-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="5de1d-155">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and provided reference network architectures to determine SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="5de1d-156">Analyserade användningen av Internet-anslutning och MPLS WAN-bandbredd för varje kontor och ökade bandbredd vid behov</span><span class="sxs-lookup"><span data-stu-id="5de1d-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="5de1d-157">Den aktuella användningen analyserades på varje kontor och kretsarna utökades så att den förutsedda, molnbaserade Microsoft 365-trafiken skulle fungera med en genomsnittlig outnyttjad kapacitet på 20 %.</span><span class="sxs-lookup"><span data-stu-id="5de1d-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="5de1d-158">Optimerade prestanda för Microsofts nätverkstjänster</span><span class="sxs-lookup"><span data-stu-id="5de1d-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="5de1d-159">Contoso identifierade sin uppsättning med Office 365-, Intune- och Azure-slutpunkter och konfigurerade brandväggar, säkerhetsenheter och andra system på Internetrutten för optimala prestanda.</span><span class="sxs-lookup"><span data-stu-id="5de1d-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="5de1d-160">Slutpunkter för Office 365-trafik i kategorierna Optimera och Tillåt konfigurerades i SD-WAN-enheter för routning över ISP-kretsen.</span><span class="sxs-lookup"><span data-stu-id="5de1d-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="5de1d-161">Konfigurerade intern DNS</span><span class="sxs-lookup"><span data-stu-id="5de1d-161">Configured internal DNS</span></span>

   <span data-ttu-id="5de1d-162">DNS måste fungera och letas upp lokalt för Microsoft 365-trafik.</span><span class="sxs-lookup"><span data-stu-id="5de1d-162">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="5de1d-163">Verifierade nätverksslutpunkter och portanslutningar</span><span class="sxs-lookup"><span data-stu-id="5de1d-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="5de1d-164">Contoso körde nätverks anslutningar som tillhandahålls av Microsoft för att verifiera anslutningen för Microsoft 365 för företags moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="5de1d-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="5de1d-165">Optimerade medarbetarnas datorer för nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="5de1d-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="5de1d-166">Enskilda datorer kontrollerades för att säkerställa att de senaste uppdateringarna av operativsystemet hade installerats och att övervakning av slutpunktssäkerhet var aktivt på alla klienter.</span><span class="sxs-lookup"><span data-stu-id="5de1d-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="5de1d-167">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5de1d-167">Next step</span></span>

<span data-ttu-id="5de1d-168">[Läs om](contoso-identity.md) hur Contoso drar nytta av sina lokala Active Directory-domäntjänster i molnet för sina medarbetare och federerar autentisering för kunder och affärspartner.</span><span class="sxs-lookup"><span data-stu-id="5de1d-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="5de1d-169">Se även</span><span class="sxs-lookup"><span data-stu-id="5de1d-169">See also</span></span>

[<span data-ttu-id="5de1d-170">Nätverks översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5de1d-170">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="5de1d-171">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5de1d-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5de1d-172">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="5de1d-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
