---
title: Microsoft 365 nätverks insikter (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694603"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="e84a1-103">Microsoft 365 nätverks insikter (för hands version)</span><span class="sxs-lookup"><span data-stu-id="e84a1-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="e84a1-104">**Nätverks insikter** är real tids värden som samlas från din Microsoft 365-klient organisation och kan bara visas av administrativa användare i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="e84a1-104">**Network insights** are live performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="e84a1-105">Insikter visas i administrations centret för Microsoft 365 på <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="e84a1-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="e84a1-106">Insikter är avsedda att hjälpa dig att utforma nätverks gränser för dina Office-platser.</span><span class="sxs-lookup"><span data-stu-id="e84a1-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="e84a1-107">Varje Insight ger direkt information om prestanda egenskaper för ett specifikt gemensamt problem för varje geografisk plats där användare kan komma åt din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="e84a1-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="e84a1-108">Det finns fem specifika nätverks insikter som kan visas för varje Office-plats:</span><span class="sxs-lookup"><span data-stu-id="e84a1-108">There are five specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="e84a1-109">Utgående nätverks utgångar</span><span class="sxs-lookup"><span data-stu-id="e84a1-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="e84a1-110">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="e84a1-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="e84a1-111">Användning av en icke optimal Exchange Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="e84a1-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="e84a1-112">Användning av en icke-optimal SharePoint Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="e84a1-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="e84a1-113">Liten nedladdnings hastighet från SharePoint-startdörren</span><span class="sxs-lookup"><span data-stu-id="e84a1-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
><span data-ttu-id="e84a1-114">Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.</span><span class="sxs-lookup"><span data-stu-id="e84a1-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="e84a1-115">Utgående nätverks utgångar</span><span class="sxs-lookup"><span data-stu-id="e84a1-115">Backhauled network egress</span></span>

<span data-ttu-id="e84a1-116">Denna inblick visas om tjänsten nätverks insikter upptäcker att avståndet från en viss användares plats till nätverket utfaller över 500 mil (800 kilo meter), vilket betyder att Microsoft 365-trafik behålls till en gemensam Internet kant linje eller proxyserver.</span><span class="sxs-lookup"><span data-stu-id="e84a1-116">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="e84a1-117">Denna inblick är för kortas som "ut" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="e84a1-117">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Utgående nätverks utgångar](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-119">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-119">What does this mean?</span></span>

<span data-ttu-id="e84a1-120">Detta anger att avståndet mellan arbets platsen och nätverket tar mer än 500 miles (800 kilo meter).</span><span class="sxs-lookup"><span data-stu-id="e84a1-120">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="e84a1-121">Office-platsen identifieras av en Obfuscated och nätverks platsen identifieras med omvänd IP-adress till plats databaser.</span><span class="sxs-lookup"><span data-stu-id="e84a1-121">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="e84a1-122">Office-platsen kanske inte stämmer om Windows Location Services är inaktiverat på datorer.</span><span class="sxs-lookup"><span data-stu-id="e84a1-122">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="e84a1-123">Nätverks utgångs platsen kan vara felaktig om den återförda IP Address-databas informationen är felaktig.</span><span class="sxs-lookup"><span data-stu-id="e84a1-123">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="e84a1-124">Information om den här inblicken inkluderar arbets platsen, den uppskattade procent andelen av klient organisationen på platsen, den aktuella nätverks utgångs platsen, relevansen för den utgående platsen, avståndet mellan platsen och den aktuella avsluts punkten, det datum då villkoret först identifierades och det datum då villkoret löstes.</span><span class="sxs-lookup"><span data-stu-id="e84a1-124">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-125">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-125">What should I do?</span></span>

<span data-ttu-id="e84a1-126">För den här inblicken rekommenderar vi att nätverks utfallet närmar sig till Office-platsen så att anslutningen kan leda optimalt till Microsofts globala nätverk och till närmaste Microsoft 365-tjänst.</span><span class="sxs-lookup"><span data-stu-id="e84a1-126">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="e84a1-127">Om du har ett nära nätverks utleverans till användarnas Office-platser kan du också få bättre prestanda i framtiden allteftersom Microsoft expanderar både nätverks punkter och Microsoft 365-tjänstens front dörrar.</span><span class="sxs-lookup"><span data-stu-id="e84a1-127">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="e84a1-128">Mer information om hur du löser det här problemet finns i [utgående nätverks anslutningar lokalt](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-128">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="e84a1-129">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="e84a1-129">Better performance detected for customers near you</span></span>

<span data-ttu-id="e84a1-130">Denna inblick visas om tjänsten nätverks insikter upptäcker att ett stort antal kunder i din tunnelbane linje har bättre prestanda än användare i organisationen på den här platsen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-130">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="e84a1-131">Denna inblick är uppkopplad som "peers" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="e84a1-131">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relativ nätverks prestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-133">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-133">What does this mean?</span></span>

<span data-ttu-id="e84a1-134">Den här inblicken undersöker den sammanlagda prestandan hos Microsoft 365-kunder i samma stad som den här kontoret.</span><span class="sxs-lookup"><span data-stu-id="e84a1-134">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="e84a1-135">Denna inblick visas om medelvärdet för användarna är 10% högre än genomsnittlig fördröjning för närliggande klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="e84a1-135">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-136">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-136">What should I do?</span></span>

<span data-ttu-id="e84a1-137">Det kan finnas många orsaker till det här problemet, inklusive svars tid i företagets nätverks-eller Internet leverantör, Flask halsar eller arkitektur design.</span><span class="sxs-lookup"><span data-stu-id="e84a1-137">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="e84a1-138">Undersök fördröjningen mellan varje hopp i vägen mellan ditt kontors nät verk och den aktuella Microsoft 365-dörren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-138">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="e84a1-139">Mer information finns i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-139">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="e84a1-140">Användning av en icke optimal Exchange Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="e84a1-140">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="e84a1-141">Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till en optimal Exchange Online-tjänst.</span><span class="sxs-lookup"><span data-stu-id="e84a1-141">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="e84a1-142">Denna inblick är för kortas som "routing" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="e84a1-142">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Icke optimal främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-144">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-144">What does this mean?</span></span>

<span data-ttu-id="e84a1-145">Vi visar Exchange Online Service front dörrar som är lämpliga för användning från Office-platsen med bra prestanda.</span><span class="sxs-lookup"><span data-stu-id="e84a1-145">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="e84a1-146">Om det aktuella testet visar användning av en Exchange Online-onlinetjänst som inte finns med i listan, ringer vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-146">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-147">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-147">What should I do?</span></span>

<span data-ttu-id="e84a1-148">Användning av en icke optimal Exchange Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avsluts, vilket innebär att det lokala och dirigerade nätverks uttaget rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="e84a1-148">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="e84a1-149">Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="e84a1-149">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="e84a1-150">Användning av en icke-optimal SharePoint Online-onlinetjänst</span><span class="sxs-lookup"><span data-stu-id="e84a1-150">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="e84a1-151">Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till närmaste SharePoint Online-tjänst.</span><span class="sxs-lookup"><span data-stu-id="e84a1-151">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="e84a1-152">Denna inblick är för kortas med "AFD" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="e84a1-152">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Icke optimal främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-154">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-154">What does this mean?</span></span>

<span data-ttu-id="e84a1-155">Vi identifierar SharePoint Online-tjänsten som test klienten ansluter till.</span><span class="sxs-lookup"><span data-stu-id="e84a1-155">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="e84a1-156">För platsen för Office-plats jämför vi nu att du har den förväntade SharePoint Online-tjänstens främre dörr.</span><span class="sxs-lookup"><span data-stu-id="e84a1-156">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="e84a1-157">Om den inte matchar gör vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-157">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-158">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-158">What should I do?</span></span>

<span data-ttu-id="e84a1-159">Användning av en icke-optimal SharePoint Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avslut ATS, vilket innebär att det lokala och direkta nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="e84a1-159">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="e84a1-160">Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.</span><span class="sxs-lookup"><span data-stu-id="e84a1-160">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="e84a1-161">Liten nedladdnings hastighet från SharePoint-startdörren</span><span class="sxs-lookup"><span data-stu-id="e84a1-161">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="e84a1-162">Denna inblick visas om tjänsten nätverks insikter upptäcker att bandbredden mellan den specifika Office-platsen och SharePoint Online är mindre än 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="e84a1-162">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="e84a1-163">Denna inblick är för kortas som "genomflöde" i vissa sammanfattningsvyn.</span><span class="sxs-lookup"><span data-stu-id="e84a1-163">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-164">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-164">What does this mean?</span></span>

<span data-ttu-id="e84a1-165">Nedladdnings hastigheten som en användare kan få från SharePoint Online och tjänsten OneDrive för företag-tjänst mäts i megabyte per sekund (MBps).</span><span class="sxs-lookup"><span data-stu-id="e84a1-165">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="e84a1-166">Om det här värdet är mindre än 1 MBps ger vi denna insikt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-166">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-167">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-167">What should I do?</span></span>

<span data-ttu-id="e84a1-168">För att förbättra nedladdnings hastigheten kan bandbredden behöva ökas.</span><span class="sxs-lookup"><span data-stu-id="e84a1-168">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="e84a1-169">Det kan också hända att nätverks belastningen är överbelastade på Office-platsen och front dörren för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e84a1-169">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="e84a1-170">Det här kallas ibland för congestive förlust och begränsar nedladdnings hastigheten till användarna även om det finns tillräckligt med bandbredd.</span><span class="sxs-lookup"><span data-stu-id="e84a1-170">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="e84a1-171">Kina-användarens optimala nätverks utgång</span><span class="sxs-lookup"><span data-stu-id="e84a1-171">China user optimal network egress</span></span>

<span data-ttu-id="e84a1-172">Denna inblick visas om din organisation har användare i Kina som ansluter till din Microsoft 365-klient organisation på andra geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="e84a1-172">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="e84a1-173">Vad innebär detta?</span><span class="sxs-lookup"><span data-stu-id="e84a1-173">What does this mean?</span></span>

<span data-ttu-id="e84a1-174">Om din organisation har en privat WAN-anslutning rekommenderar vi att du konfigurerar nätverks WAN-kretsen från din Office-plats i Kina som har nätverks täckning på Internet på någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="e84a1-174">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="e84a1-175">Hongkong</span><span class="sxs-lookup"><span data-stu-id="e84a1-175">Hong Kong</span></span>
- <span data-ttu-id="e84a1-176">Japan</span><span class="sxs-lookup"><span data-stu-id="e84a1-176">Japan</span></span>
- <span data-ttu-id="e84a1-177">Taiwan</span><span class="sxs-lookup"><span data-stu-id="e84a1-177">Taiwan</span></span>
- <span data-ttu-id="e84a1-178">Sydkorea</span><span class="sxs-lookup"><span data-stu-id="e84a1-178">South Korea</span></span>
- <span data-ttu-id="e84a1-179">Singapore</span><span class="sxs-lookup"><span data-stu-id="e84a1-179">Singapore</span></span>
- <span data-ttu-id="e84a1-180">Malaysia</span><span class="sxs-lookup"><span data-stu-id="e84a1-180">Malaysia</span></span>

<span data-ttu-id="e84a1-181">Internet upphör längre bort från användare än de här platserna minskar prestanda och utgångs i Kina kan orsaka hög latens och anslutnings problem på grund av gränsöverskridande överbelastning.</span><span class="sxs-lookup"><span data-stu-id="e84a1-181">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e84a1-182">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="e84a1-182">What should I do?</span></span>

<span data-ttu-id="e84a1-183">Mer information om hur du minskar prestanda problem som är relaterade till den här inblicken finns i [Office 365 global Performance Optimization för användare i Kina](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-183">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e84a1-184">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e84a1-184">Related topics</span></span>

[<span data-ttu-id="e84a1-185">Rekommendationer för nätverks prestanda i Microsoft 365 Admin Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="e84a1-185">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="e84a1-186">Microsoft 365 Network Assessment (för hands version)</span><span class="sxs-lookup"><span data-stu-id="e84a1-186">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="e84a1-187">Microsoft 365 anslutnings test i M365 administrations Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="e84a1-187">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="e84a1-188">Microsoft 365 nätverks anslutningar (för hands version)</span><span class="sxs-lookup"><span data-stu-id="e84a1-188">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
