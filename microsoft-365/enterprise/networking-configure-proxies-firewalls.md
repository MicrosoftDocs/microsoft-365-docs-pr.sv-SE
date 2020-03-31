---
title: 'Steg 4: Konfigurera förbikoppling av trafik'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera webbläsare och gränsenheter för förbikoppling av trafik till betrodda Office 365-platser.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812223"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="47a24-103">Steg 4: Konfigurera förbikoppling av trafik</span><span class="sxs-lookup"><span data-stu-id="47a24-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="47a24-104">*Det här steget är valfritt och gäller både E3-versionen och E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="47a24-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="47a24-106">Eftersom allmän Internettrafik kan utgöra en risk använder företagsnätverk vanligtvis gränsenheter som proxyservrar, SSL-inspektion, paketinspektionsenheter och system för skydd mot dataförlust.</span><span class="sxs-lookup"><span data-stu-id="47a24-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="47a24-107">Läs om några av problemen med nätverksavlyssningsenheter i [Använda nätverksenheter eller lösningar från tredje part för Office 365-trafik](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="47a24-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="47a24-108">De DNS-domännamn och IP-adresser som används av de molnbaserade tjänsterna i Microsoft 365 är välkända.</span><span class="sxs-lookup"><span data-stu-id="47a24-108">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known.</span></span> <span data-ttu-id="47a24-109">Dessutom skyddas själva trafiken och tjänsterna med många säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="47a24-109">Additionally, the traffic and services themselves are protected with many security features.</span></span> <span data-ttu-id="47a24-110">Eftersom det redan finns skydd på plats behöver dina gränsenheter inte duplicera det.</span><span class="sxs-lookup"><span data-stu-id="47a24-110">Because this security and protection is already in place, your edge devices don’t need to duplicate it.</span></span> <span data-ttu-id="47a24-111">Mellanliggande destinationer och duplicerad säkerhetsbearbetning för Microsoft 365-trafik kan ge dramatiskt försämrade prestanda.</span><span class="sxs-lookup"><span data-stu-id="47a24-111">Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="47a24-112">Det första steget för att undvika mellanliggande destinationer och duplicerad säkerhetsbearbetning är att identifiera Microsoft 365-trafik.</span><span class="sxs-lookup"><span data-stu-id="47a24-112">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic.</span></span> <span data-ttu-id="47a24-113">Microsoft har definierat följande typer av DNS-domännamn och IP-adressintervall, så kallade slutpunkter:</span><span class="sxs-lookup"><span data-stu-id="47a24-113">Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="47a24-114">**Optimera** – Krävs för anslutning till varje Office 365-tjänst och representerar över 75 procent av bandbredden, anslutningarna och datavolymen för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47a24-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="47a24-115">Dessa slutpunkter representerar Microsoft 365-scenarier som är mest känsliga när det gäller nätverksprestanda, svarstid och tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="47a24-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="47a24-116">**Tillåt** – Krävs för anslutning till vissa tjänster och funktioner i Microsoft 365, men dessa slutpunkter är inte lika känsliga för nätverksprestanda och svarstider som slutpunkterna i kategorin Optimera.</span><span class="sxs-lookup"><span data-stu-id="47a24-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="47a24-117">**Standard** – Representerar tjänster och beroenden för Microsoft 365 som inte kräver någon optimering.</span><span class="sxs-lookup"><span data-stu-id="47a24-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="47a24-118">Du kan hantera slutpunkterna i kategorin Standard som vanlig Internettrafik.</span><span class="sxs-lookup"><span data-stu-id="47a24-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="47a24-119">DNS-domännamnen och IP-adressintervallen hittar du på [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="47a24-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="47a24-120">Microsoft rekommenderar att du:</span><span class="sxs-lookup"><span data-stu-id="47a24-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="47a24-121">Använder PAC-skript i webbläsare på lokala datorer för att kringgå dina proxyservrar för DNS-domännamnen för molnbaserade Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="47a24-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="47a24-122">Mer information om det senaste PAC-skriptet för Microsoft 365 finns i [PowerShell-skriptet Get-Pacfile](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="47a24-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="47a24-123">Analyserar dina gränsenheter för att ta reda på om det förekommer duplicerad bearbetning och konfigurerar gränsenheterna till att vidarebefordra trafik för att optimera och tillåta slutpunkter utan bearbetning.</span><span class="sxs-lookup"><span data-stu-id="47a24-123">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing.</span></span> <span data-ttu-id="47a24-124">Detta kallas förbikoppling av trafik.</span><span class="sxs-lookup"><span data-stu-id="47a24-124">This is known as traffic bypass.</span></span> 

<span data-ttu-id="47a24-125">Här följer rekommendationer för din nätverksinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="47a24-125">Here are these recommendations in your network infrastructure.</span></span>

![Rekommendationer för optimering av lokal trafik](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="47a24-127">Gränsenheterna inkluderar brandväggar, SSL-inspektion, paketinspektionsenheter och skydd mot dataförlust.</span><span class="sxs-lookup"><span data-stu-id="47a24-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="47a24-128">Om du vill konfigurera och uppdatera konfigurationerna för gränsenheter kan du använda ett skript eller ett REST-anrop för att hämta en strukturerad lista med slutpunkter från webbtjänsten för Office 365-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="47a24-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="47a24-129">Mer information finns i [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service) (IP-adresser och URL:er för Office 365-webbtjänst).</span><span class="sxs-lookup"><span data-stu-id="47a24-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="47a24-130">Observera att du bara kringgår normal proxy och nätverkssäkerhetsbearbetning för trafik till slutpunkterna i kategorin Optimera och Tillåt för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47a24-130">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints.</span></span> <span data-ttu-id="47a24-131">All annan allmän Internettrafik går via proxy och omfattas av din befintliga nätverkssäkerhetsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="47a24-131">All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="47a24-132">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step4) för det här steget.</span><span class="sxs-lookup"><span data-stu-id="47a24-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="47a24-133">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="47a24-133">Next step</span></span>

|||
|:-------|:-----|
|![Steg 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="47a24-135">Optimera prestanda för klienten och Office 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="47a24-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



