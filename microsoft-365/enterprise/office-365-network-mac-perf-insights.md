---
title: Microsoft 365 nätverks insikter (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 nätverks insikter (för hands version)
ms.openlocfilehash: e3730704b6672c931b7538659a38f218e769dd0a
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962377"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="eec68-103">Microsoft 365 nätverks insikter (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eec68-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="eec68-104">**Nätverks insikter** är prestanda värden som samlas från din Microsoft 365-klient organisation och kan bara visas av administrativa användare i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="eec68-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="eec68-105">Insikter visas i administrations centret för Microsoft 365 på <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="eec68-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="eec68-106">Insikter är avsedda att hjälpa dig att utforma nätverks gränser för dina Office-platser.</span><span class="sxs-lookup"><span data-stu-id="eec68-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="eec68-107">Varje Insight ger direkt information om prestanda egenskaper för ett specifikt gemensamt problem för varje geografisk plats där användare kan komma åt din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="eec68-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="eec68-108">Det finns sex specifika nätverks insikter som kan visas för varje Office-plats:</span><span class="sxs-lookup"><span data-stu-id="eec68-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="eec68-109">Utgående nätverks utgångar</span><span class="sxs-lookup"><span data-stu-id="eec68-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="eec68-110">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="eec68-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="eec68-111">Användning av en icke optimal Exchange Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="eec68-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="eec68-112">Användning av en icke-optimal SharePoint Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="eec68-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="eec68-113">Liten nedladdnings hastighet från SharePoint-startdörren</span><span class="sxs-lookup"><span data-stu-id="eec68-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="eec68-114">Kina-användarens optimala nätverks utgång</span><span class="sxs-lookup"><span data-stu-id="eec68-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="eec68-115">Det finns två nätverks insikter för klient organisations nivå som kan visas för klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="eec68-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="eec68-116">Dessa visas också på producvitivy resultat sidor:</span><span class="sxs-lookup"><span data-stu-id="eec68-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="eec68-117">Exchange-sampel som påverkas av anslutnings problem</span><span class="sxs-lookup"><span data-stu-id="eec68-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="eec68-118">SharePoint-sampel som påverkas av anslutnings problem</span><span class="sxs-lookup"><span data-stu-id="eec68-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="eec68-119">Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.</span><span class="sxs-lookup"><span data-stu-id="eec68-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="eec68-120">Utgående nätverks utgångar</span><span class="sxs-lookup"><span data-stu-id="eec68-120">Backhauled network egress</span></span>

<span data-ttu-id="eec68-121">Denna inblick visas om tjänsten nätverks insikter upptäcker att avståndet från en viss användares plats till nätverket utfaller över 500 mil (800 kilo meter), vilket betyder att Microsoft 365-trafik behålls till en gemensam Internet kant linje eller proxyserver.</span><span class="sxs-lookup"><span data-stu-id="eec68-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="eec68-122">Denna inblick är för kortas som "ut" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="eec68-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Utgående nätverks utgångar](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-124">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-124">What does this mean?</span></span>

<span data-ttu-id="eec68-125">Detta anger att avståndet mellan arbets platsen och nätverket tar mer än 500 miles (800 kilo meter).</span><span class="sxs-lookup"><span data-stu-id="eec68-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="eec68-126">Office-platsen identifieras av en Obfuscated och nätverks platsen identifieras med omvänd IP-adress till plats databaser.</span><span class="sxs-lookup"><span data-stu-id="eec68-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="eec68-127">Office-platsen kanske inte stämmer om Windows Location Services är inaktiverat på datorer.</span><span class="sxs-lookup"><span data-stu-id="eec68-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="eec68-128">Nätverks utgångs platsen kan vara felaktig om den återförda IP Address-databas informationen är felaktig.</span><span class="sxs-lookup"><span data-stu-id="eec68-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="eec68-129">Information om den här inblicken inkluderar arbets platsen, den uppskattade procent andelen av klient organisationen på platsen, den aktuella nätverks utgångs platsen, relevansen för den utgående platsen, avståndet mellan platsen och den aktuella avsluts punkten, det datum då villkoret först identifierades och det datum då villkoret löstes.</span><span class="sxs-lookup"><span data-stu-id="eec68-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-130">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-130">What should I do?</span></span>

<span data-ttu-id="eec68-131">För den här inblicken rekommenderar vi att nätverks utfallet närmar sig till Office-platsen så att anslutningen kan leda optimalt till Microsofts globala nätverk och till närmaste Microsoft 365-tjänst.</span><span class="sxs-lookup"><span data-stu-id="eec68-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="eec68-132">Om du har ett nära nätverks utleverans till användarnas Office-platser kan du också få bättre prestanda i framtiden allteftersom Microsoft expanderar både nätverks punkter och Microsoft 365-tjänstens front dörrar.</span><span class="sxs-lookup"><span data-stu-id="eec68-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="eec68-133">Mer information om hur du löser det här problemet finns i [utgående nätverks anslutningar lokalt](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="eec68-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="eec68-134">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="eec68-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="eec68-135">Denna inblick visas om tjänsten nätverks insikter upptäcker att ett stort antal kunder i din tunnelbane linje har bättre prestanda än användare i organisationen på den här platsen.</span><span class="sxs-lookup"><span data-stu-id="eec68-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="eec68-136">Denna inblick är uppkopplad som "peers" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="eec68-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relativ nätverks prestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-138">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-138">What does this mean?</span></span>

<span data-ttu-id="eec68-139">Den här inblicken undersöker den sammanlagda prestandan hos Microsoft 365-kunder i samma stad som den här kontoret.</span><span class="sxs-lookup"><span data-stu-id="eec68-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="eec68-140">Denna inblick visas om medelvärdet för användarna är 10% högre än genomsnittlig fördröjning för närliggande klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="eec68-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-141">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-141">What should I do?</span></span>

<span data-ttu-id="eec68-142">Det kan finnas många orsaker till det här problemet, inklusive svars tid i företagets nätverks-eller Internet leverantör, Flask halsar eller arkitektur design.</span><span class="sxs-lookup"><span data-stu-id="eec68-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="eec68-143">Undersök fördröjningen mellan varje hopp i vägen mellan ditt kontors nät verk och den aktuella Microsoft 365-dörren.</span><span class="sxs-lookup"><span data-stu-id="eec68-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="eec68-144">Mer information finns i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="eec68-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="eec68-145">Användning av en icke optimal Exchange Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="eec68-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="eec68-146">Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till en optimal Exchange Online-tjänst.</span><span class="sxs-lookup"><span data-stu-id="eec68-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="eec68-147">Denna inblick är för kortas som "routing" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="eec68-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Icke-optimal EXO främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-149">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-149">What does this mean?</span></span>

<span data-ttu-id="eec68-150">Vi visar Exchange Online Service front dörrar som är lämpliga för användning från Office-platsen med bra prestanda.</span><span class="sxs-lookup"><span data-stu-id="eec68-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="eec68-151">Om det aktuella testet visar användning av en Exchange Online-onlinetjänst som inte finns med i listan, ringer vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="eec68-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-152">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-152">What should I do?</span></span>

<span data-ttu-id="eec68-153">Användning av en icke optimal Exchange Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avsluts, vilket innebär att det lokala och dirigerade nätverks uttaget rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="eec68-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="eec68-154">Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="eec68-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="eec68-155">Användning av en icke-optimal SharePoint Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="eec68-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="eec68-156">Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till närmaste SharePoint Online-tjänst.</span><span class="sxs-lookup"><span data-stu-id="eec68-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="eec68-157">Denna inblick är för kortas med "AFD" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="eec68-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Icke-optimal SPO främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-159">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-159">What does this mean?</span></span>

<span data-ttu-id="eec68-160">Vi identifierar SharePoint Online-tjänsten som test klienten ansluter till.</span><span class="sxs-lookup"><span data-stu-id="eec68-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="eec68-161">För platsen för Office-plats jämför vi nu att du har den förväntade SharePoint Online-tjänstens främre dörr.</span><span class="sxs-lookup"><span data-stu-id="eec68-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="eec68-162">Om den inte matchar gör vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="eec68-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-163">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-163">What should I do?</span></span>

<span data-ttu-id="eec68-164">Användning av en icke-optimal SharePoint Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avslut ATS, vilket innebär att det lokala och direkta nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="eec68-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="eec68-165">Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="eec68-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="eec68-166">Liten nedladdnings hastighet från SharePoint-startdörren</span><span class="sxs-lookup"><span data-stu-id="eec68-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="eec68-167">Denna inblick visas om tjänsten nätverks insikter upptäcker att bandbredden mellan den specifika Office-platsen och SharePoint Online är mindre än 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="eec68-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="eec68-168">Denna inblick är för kortas som "genomflöde" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="eec68-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-169">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-169">What does this mean?</span></span>

<span data-ttu-id="eec68-170">Nedladdnings hastigheten som en användare kan få från SharePoint Online och tjänsten OneDrive för företag-tjänst mäts i megabyte per sekund (MBps).</span><span class="sxs-lookup"><span data-stu-id="eec68-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="eec68-171">Om det här värdet är mindre än 1 MBps ger vi denna insikt.</span><span class="sxs-lookup"><span data-stu-id="eec68-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-172">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-172">What should I do?</span></span>

<span data-ttu-id="eec68-173">För att förbättra nedladdnings hastigheten kan bandbredden behöva ökas.</span><span class="sxs-lookup"><span data-stu-id="eec68-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="eec68-174">Det kan också hända att nätverks belastningen är överbelastade på Office-platsen och front dörren för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="eec68-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="eec68-175">Det här kallas ibland för congestive förlust och begränsar nedladdnings hastigheten till användarna även om det finns tillräckligt med bandbredd.</span><span class="sxs-lookup"><span data-stu-id="eec68-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="eec68-176">Kina-användarens optimala nätverks utgång</span><span class="sxs-lookup"><span data-stu-id="eec68-176">China user optimal network egress</span></span>

<span data-ttu-id="eec68-177">Denna inblick visas om din organisation har användare i Kina som ansluter till din Microsoft 365-klient organisation på andra geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="eec68-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-178">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-178">What does this mean?</span></span>

<span data-ttu-id="eec68-179">Om din organisation har en privat WAN-anslutning rekommenderar vi att du konfigurerar nätverks WAN-kretsen från din Office-plats i Kina som har nätverks täckning på Internet på någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="eec68-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="eec68-180">Hongkong</span><span class="sxs-lookup"><span data-stu-id="eec68-180">Hong Kong</span></span>
- <span data-ttu-id="eec68-181">Japan </span><span class="sxs-lookup"><span data-stu-id="eec68-181">Japan</span></span>
- <span data-ttu-id="eec68-182">Taiwan</span><span class="sxs-lookup"><span data-stu-id="eec68-182">Taiwan</span></span>
- <span data-ttu-id="eec68-183">Sydkorea</span><span class="sxs-lookup"><span data-stu-id="eec68-183">South Korea</span></span>
- <span data-ttu-id="eec68-184">Singapore</span><span class="sxs-lookup"><span data-stu-id="eec68-184">Singapore</span></span>
- <span data-ttu-id="eec68-185">Malaysia</span><span class="sxs-lookup"><span data-stu-id="eec68-185">Malaysia</span></span>

<span data-ttu-id="eec68-186">Internet upphör längre bort från användare än de här platserna minskar prestanda och utgångs i Kina kan orsaka hög latens och anslutnings problem på grund av gränsöverskridande överbelastning.</span><span class="sxs-lookup"><span data-stu-id="eec68-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-187">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-187">What should I do?</span></span>

<span data-ttu-id="eec68-188">Mer information om hur du minskar prestanda problem som är relaterade till den här inblicken finns i [Office 365 global Performance Optimization för användare i Kina](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="eec68-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="eec68-189">Exchange-sampel som påverkas av anslutnings problem</span><span class="sxs-lookup"><span data-stu-id="eec68-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="eec68-190">Denna inblick visar när 50% eller fler av de uppkopplings bara förbindelserna påverkas.</span><span class="sxs-lookup"><span data-stu-id="eec68-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="eec68-191">Effekten definieras av Exchange utvärdering som unders tiger 60% för varje prov.</span><span class="sxs-lookup"><span data-stu-id="eec68-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-192">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-192">What does this mean?</span></span>

<span data-ttu-id="eec68-193">Det är en indikation på att de flesta av användarna troligt vis drabbas av problem med att Outlook ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eec68-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="eec68-194">Procent andelen av proverna representerar procent av användare som visar under 60 punkter.</span><span class="sxs-lookup"><span data-stu-id="eec68-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-195">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-195">What should I do?</span></span>

<span data-ttu-id="eec68-196">Aktivera synligheten för nätverks anslutningar för Office om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="eec68-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="eec68-197">Du vill identifiera vilka kontor som är impactred av dåligt ansluten till nätverket som påverkar Exchange och hitta olika sätt att förbättra nätverks behållning hos alla som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="eec68-197">You want to identify which offices are impactred by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="eec68-198">SharePoint-sampel som påverkas av anslutnings problem</span><span class="sxs-lookup"><span data-stu-id="eec68-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="eec68-199">Denna inblick visar när 50% eller fler av de uppkopplings bara förbindelserna påverkas.</span><span class="sxs-lookup"><span data-stu-id="eec68-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="eec68-200">Effekten definieras av SharePoint-utvärderingen under 40% för varje prov.</span><span class="sxs-lookup"><span data-stu-id="eec68-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="eec68-201">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="eec68-201">What does this mean?</span></span>

<span data-ttu-id="eec68-202">Det är en indikation på att de flesta av användarna sannolikt har problem med användar miljön med SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="eec68-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="eec68-203">Procent andelen av proverna representerar procent av användare som visar under 40 punkter.</span><span class="sxs-lookup"><span data-stu-id="eec68-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="eec68-204">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="eec68-204">What should I do?</span></span>

<span data-ttu-id="eec68-205">Aktivera synligheten för nätverks anslutningar för Office om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="eec68-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="eec68-206">Du vill identifiera vilka kontor som är impactred av dåligt nätverksanslutna anslutningar som påverkar SharePoint och hittar olika sätt att förbättra nätverks behållning hos alla som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="eec68-206">You want to identify which offices are impactred by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eec68-207">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="eec68-207">Related topics</span></span>

[<span data-ttu-id="eec68-208">Nätverks anslutning i Microsoft 365 Admin Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eec68-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="eec68-209">Microsoft 365 Network Assessment (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eec68-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="eec68-210">Microsoft 365 anslutnings test i M365 administrations Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eec68-210">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="eec68-211">Microsoft 365 nätverks anslutningar (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eec68-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
