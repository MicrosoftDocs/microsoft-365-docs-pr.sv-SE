---
title: Microsoft 365 Network Insights (förhandsversion)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (förhandsversion)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055479"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="0dc3a-103">Microsoft 365 Network Insights (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="0dc3a-104">**Nätverksinsikter** är prestandamätvärden som samlas in från Microsoft 365-klienten och är tillgängliga för visning endast av administrativa användare i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="0dc3a-105">Insikter visas i administrationscentret för Microsoft 365 i <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="0dc3a-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="0dc3a-106">Insikter är avsedda att hjälpa dig att utforma nätverks perimeter för dina kontorsplatser.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="0dc3a-107">Varje insikt ger direktinformation om prestandaegenskaper för ett specifikt gemensamt problem för varje geografisk plats där användarna har åtkomst till din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="0dc3a-108">Det finns sex specifika nätverksinsikter som kan visas för varje kontorsplats:</span><span class="sxs-lookup"><span data-stu-id="0dc3a-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="0dc3a-109">Utgående nätverksback</span><span class="sxs-lookup"><span data-stu-id="0dc3a-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="0dc3a-110">Nätverkets mellanliggande enhet</span><span class="sxs-lookup"><span data-stu-id="0dc3a-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="0dc3a-111">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="0dc3a-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="0dc3a-112">Användning av en icke-optimal Exchange Online-tjänsts framsida</span><span class="sxs-lookup"><span data-stu-id="0dc3a-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="0dc3a-113">Användning av en icke-optimal SharePoint Online-tjänsts framsida</span><span class="sxs-lookup"><span data-stu-id="0dc3a-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="0dc3a-114">Låg nedladdningshastighet från SharePoints dörr</span><span class="sxs-lookup"><span data-stu-id="0dc3a-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="0dc3a-115">Optimal utgående nätverkstrafik för användare i Kina</span><span class="sxs-lookup"><span data-stu-id="0dc3a-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="0dc3a-116">Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="0dc3a-117">De visas även på resultatsidorna:</span><span class="sxs-lookup"><span data-stu-id="0dc3a-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="0dc3a-118">Exempel på Exchange-anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="0dc3a-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="0dc3a-119">SharePoint-exempelanslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="0dc3a-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="0dc3a-120">Nätverksinsikter, prestandarekommendationer och utvärderingar i Administrationscenter för Microsoft 365 är för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-innehavare som har registrerats i programmet för funktionsförhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="0dc3a-121">Utgående nätverksback</span><span class="sxs-lookup"><span data-stu-id="0dc3a-121">Backhauled network egress</span></span>

<span data-ttu-id="0dc3a-122">Den här insikten visas om tjänsten nätverksinsikter identifierar att avståndet från en viss användarplats till nätverkets utgång är större än 800 km (800 km), vilket anger att Microsoft 365-trafik backar till en vanlig Internet-edge-enhet eller -proxy.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="0dc3a-123">Den här insikten är förkortad som "Egress" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Utgående nätverksback](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-125">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-125">What does this mean?</span></span>

<span data-ttu-id="0dc3a-126">Detta identifierar att avståndet mellan kontorsplatsen och nätverkets utgående punkt är mer än 500 miles (800 miles).</span><span class="sxs-lookup"><span data-stu-id="0dc3a-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="0dc3a-127">Kontorsplatsen identifieras av en obfyllande klientdatorplats och den utgående platsen för nätverket identifieras genom att använda omvänd IP-adress till platsdatabaser.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="0dc3a-128">Platsen på kontoret kan vara felaktig om Windows Platstjänster är inaktiverat på datorer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="0dc3a-129">Nätverkets utgående plats kan vara felaktig om den omvända IP-adressdatabasinformationen är felaktig.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="0dc3a-130">Information för den här insikten omfattar kontorsplatsen, uppskattad procentandel av den totala användaren för klientorganisationen på platsen, den aktuella utgående platsen för nätverket, relevans för den utgående platsen, avståndet mellan platsen och den aktuella utgående punkten, datumet då villkoret först identifierades och det datum då villkoret löstes.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-131">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-131">What should I do?</span></span>

<span data-ttu-id="0dc3a-132">För den här insikten rekommenderar vi att nätverket går närmare kontorsplatsen så att anslutningen kan dirigeras optimalt till Microsofts globala nätverk och till närmaste Microsoft 365-tjänstport.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="0dc3a-133">Att stänga nätverkets utgång till användarnas kontorsplatser gör det också möjligt att förbättra prestanda i framtiden eftersom Microsoft utökar båda nätverkspunkternas närvaro och Microsoft 365-tjänstens fram dörrar i framtiden.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="0dc3a-134">Mer information om hur du löser problemet finns i utgående [nätverksanslutningar lokalt i](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) principer för [Office 365-nätverksanslutning.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="0dc3a-135">Nätverkets mellanliggande enhet</span><span class="sxs-lookup"><span data-stu-id="0dc3a-135">Network intermediary device</span></span>

<span data-ttu-id="0dc3a-136">Den här insikten visas om vi har upptäckt enheter mellan dina användare och Microsofts nätverk som kan påverka användarupplevelsen för Office 365.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="0dc3a-137">Vi rekommenderar att dessa kringgås för specifik Microsoft 365-nätverkstrafik som är avsedd för Microsoft-datacenter.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="0dc3a-138">Den här rekommendationen beskrivs dessutom i [Microsoft 365-principer för nätverksanslutning](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-139">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-139">What does this mean?</span></span>

<span data-ttu-id="0dc3a-140">Nätverkets mellanledande enheter som proxyservrar, VPN och enheter för dataförlustskydd kan påverka prestanda och stabilitet för Microsoft 365-klienter där trafiken mellanliggandes.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-141">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-141">What should I do?</span></span>

<span data-ttu-id="0dc3a-142">Konfigurera den nätverksledande enhet som upptäckts att kringgå bearbetning för Microsoft 365-nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="0dc3a-143">Bättre prestanda upptäckt för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="0dc3a-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="0dc3a-144">Den här insikten visas om tjänsten Network Insights identifierar att ett stort antal kunder i metroområdet har bättre prestanda än användare i organisationen på den här kontorsplatsen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="0dc3a-145">Den här insikten är förkortad som "Peers" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relativ nätverksprestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-147">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-147">What does this mean?</span></span>

<span data-ttu-id="0dc3a-148">Den här insikten undersöker de aggregerade prestandan för Microsoft 365-kunder i samma stad som den här kontorsplatsen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="0dc3a-149">Den här insikten visas om den genomsnittliga svarstiden för dina användare är 10 % större än den genomsnittliga svarstiden för intilliggande klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-150">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-150">What should I do?</span></span>

<span data-ttu-id="0dc3a-151">Det kan finnas många orsaker till det här villkoret, till exempel svarstiden i företagsnätverket eller Internetleverantör, problem med flaskhalsar eller arkitekturdesign.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="0dc3a-152">Undersök svarstiden mellan varje hopp i vägen mellan ditt office-nätverk och den aktuella Front Door i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="0dc3a-153">Mer information finns i [Microsoft 365-principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="0dc3a-154">Användning av en icke-optimal Exchange Online-tjänsts framsida</span><span class="sxs-lookup"><span data-stu-id="0dc3a-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="0dc3a-155">Den här insikten visas om tjänsten nätverksinsikter identifierar att användare på en viss plats inte ansluter till en optimal Exchange Online-tjänst så att säga.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="0dc3a-156">Den här insikten är förkortad som "Routing" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Ej optimal EXO-dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-158">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-158">What does this mean?</span></span>

<span data-ttu-id="0dc3a-159">Vi listar Exchange Online-tjänstens fram dörrar som är lämpliga för användning från kontorsplatsens ort med bra prestanda.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="0dc3a-160">Om det i det aktuella testet visas att en Exchange Online-tjänst används utanför den här listan rekommenderar vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-161">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-161">What should I do?</span></span>

<span data-ttu-id="0dc3a-162">Användningen av en icke-optimal Exchange Online-tjänsts framsida kan orsakas av nätverkets backhaul innan företagsnätverket går ut. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="0dc3a-163">Det kan också bero på att en DNS-rekursiv rekursiv resolverserver används, och då rekommenderar vi att du justerar DNS Rekursiv resolver-servern med nätverkets utgående post.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="0dc3a-164">Användning av en icke-optimal SharePoint Online-tjänsts framsida</span><span class="sxs-lookup"><span data-stu-id="0dc3a-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="0dc3a-165">Den här insikten visas om tjänsten nätverksinsikter identifierar att användare på en viss plats inte ansluter till den närmaste SharePoint Online-tjänstens yttersida.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="0dc3a-166">Den här insikten är förkortad som "Afd" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Ej optimal SPO-dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-168">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-168">What does this mean?</span></span>

<span data-ttu-id="0dc3a-169">Vi identifierar SharePoint Online-tjänstens yttersida som testklienten ansluter till.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="0dc3a-170">För kontorsplatsen jämför vi den med den förväntade SharePoint Online-tjänstens framsida för den staden.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="0dc3a-171">Om den inte stämmer överens med den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-172">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-172">What should I do?</span></span>

<span data-ttu-id="0dc3a-173">Användningen av en icke-optimal SharePoint Online-tjänsts framsida skulle kunna orsakas av ett nätverksnätverk före företagsnätverkets utgång. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="0dc3a-174">Det kan också bero på att en DNS-rekursiv rekursiv resolverserver används, och då rekommenderar vi att du justerar DNS Rekursiv resolver-servern med nätverkets utgående post.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="0dc3a-175">Låg nedladdningshastighet från SharePoints dörr</span><span class="sxs-lookup"><span data-stu-id="0dc3a-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="0dc3a-176">Den här insikten visas om tjänsten nätverksinsikter identifierar den bandbredden mellan den specifika kontorsplatsen och SharePoint Online är mindre än 1 MBp.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="0dc3a-177">Den här insikten är förkortad som "Dataflöde" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-178">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-178">What does this mean?</span></span>

<span data-ttu-id="0dc3a-179">Den nedladdningshastighet som en användare kan få från SharePoint Online och OneDrive för företag-tjänstens dörrar fram mäts i megabyte per sekund (MBps).</span><span class="sxs-lookup"><span data-stu-id="0dc3a-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="0dc3a-180">Om det här värdet är mindre än 1 MBp ger vi den här insikten.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-181">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-181">What should I do?</span></span>

<span data-ttu-id="0dc3a-182">För att förbättra nedladdningshastigheter kan bandbredden behöva ökas.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="0dc3a-183">Alternativt kan nätverksstockningar vara överbelastade mellan användares datorer på kontoret och SharePoint Online-tjänstens framsida.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="0dc3a-184">Det här kallas ibland för en överbelastande förlust och det begränsar nedladdningshastigheten som är tillgänglig för användarna även om tillräcklig bandbredd finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="0dc3a-185">Optimal utgående nätverkstrafik för användare i Kina</span><span class="sxs-lookup"><span data-stu-id="0dc3a-185">China user optimal network egress</span></span>

<span data-ttu-id="0dc3a-186">Den här insikten visas om din organisation har användare i Kina som ansluter till din Microsoft 365-klientorganisation på andra geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-187">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-187">What does this mean?</span></span>

<span data-ttu-id="0dc3a-188">Om din organisation har privat WAN-anslutning rekommenderar vi att du konfigurerar en WAN-krets för nätverket från dina kontorsplatser i Kina som har utgående nätverk till Internet på någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="0dc3a-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="0dc3a-189">Hongkong</span><span class="sxs-lookup"><span data-stu-id="0dc3a-189">Hong Kong</span></span>
- <span data-ttu-id="0dc3a-190">Japan </span><span class="sxs-lookup"><span data-stu-id="0dc3a-190">Japan</span></span>
- <span data-ttu-id="0dc3a-191">Taiwan</span><span class="sxs-lookup"><span data-stu-id="0dc3a-191">Taiwan</span></span>
- <span data-ttu-id="0dc3a-192">Sydkorea</span><span class="sxs-lookup"><span data-stu-id="0dc3a-192">South Korea</span></span>
- <span data-ttu-id="0dc3a-193">Singapore</span><span class="sxs-lookup"><span data-stu-id="0dc3a-193">Singapore</span></span>
- <span data-ttu-id="0dc3a-194">Malaysia</span><span class="sxs-lookup"><span data-stu-id="0dc3a-194">Malaysia</span></span>

<span data-ttu-id="0dc3a-195">Internet som går ut längre bort från användarna än dessa platser kommer att minska prestandan, och utgående trafik i Kina kan orsaka problem med lång fördröjning och anslutning på grund av överbelastning över gränsen.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-196">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-196">What should I do?</span></span>

<span data-ttu-id="0dc3a-197">Mer information om hur du åtgärdar prestandaproblem relaterade till den här insikten finns i den globala klientorganisationens prestandaoptimering [för Microsoft 365 för kinaanvändare.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="0dc3a-198">Exempel på Exchange-anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="0dc3a-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="0dc3a-199">Den här insikten visas när 50 % eller fler av de exempelade anslutningarna påverkas.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="0dc3a-200">Effekterna definieras av Exchange-utvärderingen som understiger 60 % för varje stickprov.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-201">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-201">What does this mean?</span></span>

<span data-ttu-id="0dc3a-202">Det är en indikation på att majoriteten av användarna troligtvis har problem med användarupplevelse med Outlook som ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="0dc3a-203">Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 60 punkter.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-204">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-204">What should I do?</span></span>

<span data-ttu-id="0dc3a-205">Aktivera synligheten för nätverksanslutningen för kontorsplatser om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="0dc3a-206">Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar Exchange och hitta sätt att förbättra nätverks perimeter vid varje kontor som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="0dc3a-207">SharePoint-exempelanslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="0dc3a-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="0dc3a-208">Den här insikten visas när 50 % eller fler av de exempelade anslutningarna påverkas.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="0dc3a-209">Effekterna definieras av SharePoint-utvärderingen som understiger 40 % för varje stickprov.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="0dc3a-210">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-210">What does this mean?</span></span>

<span data-ttu-id="0dc3a-211">Det är en indikation på att majoriteten av användarna troligtvis har problem med användarupplevelse med SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="0dc3a-212">Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 40 punkter.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="0dc3a-213">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="0dc3a-213">What should I do?</span></span>

<span data-ttu-id="0dc3a-214">Aktivera synligheten för nätverksanslutningen för kontorsplatser om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="0dc3a-215">Du vill identifiera vilka kontor som påverkas av dåliga nätverksanslutningar som påverkar SharePoint och hitta sätt att förbättra nätverks perimeter vid varje kontor som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="0dc3a-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0dc3a-216">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0dc3a-216">Related topics</span></span>

[<span data-ttu-id="0dc3a-217">Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="0dc3a-218">Microsoft 365-nätverksutvärdering (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="0dc3a-219">Testverktyg för Microsoft 365-nätverksanslutning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="0dc3a-220">Microsoft 365 Network Connectivity Location Services (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="0dc3a-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
