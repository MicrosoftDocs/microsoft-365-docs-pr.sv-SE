---
title: Microsoft 365 Nätverksinsikter
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
description: Microsoft 365 Nätverksinsikter
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470574"
---
# <a name="microsoft-365-network-insights"></a><span data-ttu-id="4b737-103">Microsoft 365 Nätverksinsikter</span><span class="sxs-lookup"><span data-stu-id="4b737-103">Microsoft 365 Network Insights</span></span>

<span data-ttu-id="4b737-104">**Nätverksinsikter** är prestandamätvärden som samlas in från Microsoft 365-klientorganisationen och är tillgängliga för visning endast av administrativa användare i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4b737-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="4b737-105">Insikter visas i administrationscentret Microsoft 365 i <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="4b737-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="4b737-106">Insikter är avsedda att bidra till att utforma nätverks perimeter för dina kontorsplatser.</span><span class="sxs-lookup"><span data-stu-id="4b737-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="4b737-107">Varje insikt ger detaljerad information om prestandaegenskaper för ett specifikt vanligt problem för varje geografisk plats där användarna har åtkomst till din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4b737-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="4b737-108">Det finns sex specifika nätverksinsikter som kan visas för varje kontorsplats:</span><span class="sxs-lookup"><span data-stu-id="4b737-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="4b737-109">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="4b737-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="4b737-110">Nätverkets mellanledde enhet</span><span class="sxs-lookup"><span data-stu-id="4b737-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="4b737-111">Bättre prestanda som upptäckts för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="4b737-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="4b737-112">Användning av en icke-optimal Exchange Online tjänst framifrån</span><span class="sxs-lookup"><span data-stu-id="4b737-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="4b737-113">Användning av en icke-optimal SharePoint för onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="4b737-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="4b737-114">Låg nedladdningshastighet SharePoint fronten</span><span class="sxs-lookup"><span data-stu-id="4b737-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="4b737-115">Optimal utgående nätverkstrafik för användare i Kina</span><span class="sxs-lookup"><span data-stu-id="4b737-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="4b737-116">Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4b737-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="4b737-117">De visas även på produktivitetsresultatsidorna:</span><span class="sxs-lookup"><span data-stu-id="4b737-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="4b737-118">Exchange exempel på anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="4b737-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="4b737-119">SharePoint exempel på anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="4b737-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="4b737-120">Nätverksinsikter, prestandarekommendationer och utvärderingar i administrationscentret för Microsoft 365 är för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-klienter som har registrerats i programmet för förhandsgranskning av funktioner.</span><span class="sxs-lookup"><span data-stu-id="4b737-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="4b737-121">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="4b737-121">Backhauled network egress</span></span>

<span data-ttu-id="4b737-122">Den här insikten visas om tjänsten nätverksinsikter upptäcker att avståndet från en viss användarplats till nätverkets utgående punkt är större än 800 kilometer, vilket indikerar att Microsoft 365-trafik backar till en gemensam Internet edge-enhet eller proxy.</span><span class="sxs-lookup"><span data-stu-id="4b737-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="4b737-123">Den här insikten är förkortad som "Egress" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="4b737-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b737-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="4b737-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-125">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-125">What does this mean?</span></span>

<span data-ttu-id="4b737-126">Detta identifierar att avståndet mellan kontorsplatsen och nätverkets utgående punkt är mer än 500 km (800 meter).</span><span class="sxs-lookup"><span data-stu-id="4b737-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="4b737-127">Kontorsplatsen identifieras med en obfuscerad klientdatorplats och nätverkets utgående plats identifieras med hjälp av omvänd IP-adress till platsdatabaser.</span><span class="sxs-lookup"><span data-stu-id="4b737-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="4b737-128">Platsen på kontoret kan vara felaktig om Windows platstjänster är inaktiverat på datorer.</span><span class="sxs-lookup"><span data-stu-id="4b737-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="4b737-129">Nätverkets utgående plats kan vara felaktig om informationen i den omvända IP-adressdatabasen är felaktig.</span><span class="sxs-lookup"><span data-stu-id="4b737-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="4b737-130">Information för den här insikten omfattar kontorsplats, uppskattad procentandel av den totala klientorganisationens användare på platsen, den aktuella utgående platsen för nätverket, relevansen för den utgående platsen, avståndet mellan platsen och den aktuella utgående punkten, datumet då villkoret först identifierades och det datum då villkoret löstes.</span><span class="sxs-lookup"><span data-stu-id="4b737-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-131">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-131">What should I do?</span></span>

<span data-ttu-id="4b737-132">För den här insikten rekommenderar vi att nätverkets utgående trafik ligger närmare kontorsplatsen så att anslutningen kan dirigeras optimalt till Microsofts globala nätverk och till närmaste Microsoft 365 tjänst front.</span><span class="sxs-lookup"><span data-stu-id="4b737-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="4b737-133">Att stänga nätverkets utgående trafik till användarnas kontorsplatser gör det också möjligt att förbättra prestanda i framtiden eftersom Microsoft utökar båda nätverkspunkterna av närvaro Microsoft 365 tjänst så att dörrar till fronten i framtiden utökas.</span><span class="sxs-lookup"><span data-stu-id="4b737-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="4b737-134">Mer information om hur du löser problemet finns i artikeln [Egress anslutningar lokalt](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) i Office 365 principer för [nätverksanslutning.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="4b737-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="4b737-135">Nätverkets mellanledde enhet</span><span class="sxs-lookup"><span data-stu-id="4b737-135">Network intermediary device</span></span>

<span data-ttu-id="4b737-136">Den här insikten visas om vi har upptäckt enheter mellan dina användare och Microsofts nätverk som kan påverka Office 365 upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="4b737-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="4b737-137">Vi rekommenderar att dessa kringgås för specifik Microsoft 365 nätverkstrafik som är avsedd för Microsofts datacenter.</span><span class="sxs-lookup"><span data-stu-id="4b737-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="4b737-138">Denna rekommendation beskrivs Microsoft 365 [principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="4b737-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="4b737-139">En information som visas för mellanled i nätverket är SSL-avbrott och kontroll när viktiga Office 365-nätverksslutpunkter för Exchange, SharePoint och Teams snappas upp och dekrypteras av nätverkets mellanled.</span><span class="sxs-lookup"><span data-stu-id="4b737-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-140">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-140">What does this mean?</span></span>

<span data-ttu-id="4b737-141">Nätverkledande enheter som proxyservrar, VPN och enheter för dataförlustskydd kan påverka prestanda och stabilitet Microsoft 365 klienter där trafiken är mellanliggande.</span><span class="sxs-lookup"><span data-stu-id="4b737-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-142">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-142">What should I do?</span></span>

<span data-ttu-id="4b737-143">Konfigurera nätverkets mellanledsenhet som har upptäckts att kringgå bearbetning för Microsoft 365 nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="4b737-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="4b737-144">Bättre prestanda som upptäckts för kunder nära dig</span><span class="sxs-lookup"><span data-stu-id="4b737-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="4b737-145">Den här insikten visas om tjänsten Network Insights upptäcker att ett stort antal kunder i din metroområde har bättre prestanda än användare i organisationen på den här kontorsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4b737-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="4b737-146">Den här insikten är förkortad som "Peers" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="4b737-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b737-147">![Relativ nätverksprestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="4b737-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-148">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-148">What does this mean?</span></span>

<span data-ttu-id="4b737-149">Den här insikten undersöker de aggregerade prestanda Microsoft 365 kunder i samma stad som den här kontorsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4b737-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="4b737-150">Den här insikten visas om den genomsnittliga svarstiden för dina användare är 10 % högre än den genomsnittliga svarstiden för intilliggande klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4b737-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-151">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-151">What should I do?</span></span>

<span data-ttu-id="4b737-152">Det kan finnas många orsaker till det här villkoret, till exempel svarstiden i företagsnätverket eller Internetleverantören, flaskhalsar och designproblem i arkitekturen.</span><span class="sxs-lookup"><span data-stu-id="4b737-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="4b737-153">Undersök svarstiden mellan varje hopp i vägen mellan ditt kontorsnätverk och den Microsoft 365 fronten.</span><span class="sxs-lookup"><span data-stu-id="4b737-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="4b737-154">Mer information finns i Microsoft 365 [principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="4b737-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="4b737-155">Användning av en icke-optimal Exchange Online tjänst framifrån</span><span class="sxs-lookup"><span data-stu-id="4b737-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="4b737-156">Den här insikten visas om tjänsten nätverksinsikter upptäcker att användare på en viss plats inte ansluter till en optimal Exchange Online tjänst hos alla.</span><span class="sxs-lookup"><span data-stu-id="4b737-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="4b737-157">Den här insikten är förkortad som "Dirigering" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="4b737-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b737-158">![Icke-optimal EXO-framport](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="4b737-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-159">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-159">What does this mean?</span></span>

<span data-ttu-id="4b737-160">Vi listar Exchange Online service så att dörrar fram som är lämpliga för användning från kontorsplatsens ort med bra prestanda.</span><span class="sxs-lookup"><span data-stu-id="4b737-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="4b737-161">Om det aktuella testet visar att en tjänst Exchange Online frontend inte finns med på den här listan kallar vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="4b737-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-162">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-162">What should I do?</span></span>

<span data-ttu-id="4b737-163">Användningen av en icke-optimal Exchange Online tjänst hos fronten kan orsakas av nätverkets backhaul innan företagsnätverkets utgående trafik. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="4b737-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="4b737-164">Det kan också orsakas av att en fjärr-DNS-rekursiv resolverserver används. I sådana fall rekommenderar vi att du justerar DNS-rekursiv resolverserver med nätverkets utgående linje.</span><span class="sxs-lookup"><span data-stu-id="4b737-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="4b737-165">Användning av en icke-optimal SharePoint för onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="4b737-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="4b737-166">Den här insikten visas om tjänsten nätverksinsikter upptäcker att användare på en viss plats inte ansluter till den SharePoint onlinetjänsten fronten.</span><span class="sxs-lookup"><span data-stu-id="4b737-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="4b737-167">Den här insikten är förkortad som "Afd" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="4b737-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b737-168">![Ej optimal SPO-framport](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="4b737-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-169">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-169">What does this mean?</span></span>

<span data-ttu-id="4b737-170">Vi identifierar SharePoint onlinetjänstens klient som testklienten ansluter till.</span><span class="sxs-lookup"><span data-stu-id="4b737-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="4b737-171">För kontorsplatsen jämförs det med den förväntade SharePoint för den staden.</span><span class="sxs-lookup"><span data-stu-id="4b737-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="4b737-172">Om den inte stämmer överens med den här rekommendationen gör vi den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="4b737-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-173">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-173">What should I do?</span></span>

<span data-ttu-id="4b737-174">Användningen av en icke-optimal SharePoint onlinetjänst front front skulle kunna orsakas av nätverkets backhaul innan företagsnätverkets utgående trafik. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="4b737-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="4b737-175">Det kan också orsakas av att en fjärr-DNS-rekursiv resolverserver används. I sådana fall rekommenderar vi att du justerar DNS-rekursiv resolverserver med nätverkets utgående linje.</span><span class="sxs-lookup"><span data-stu-id="4b737-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="4b737-176">Låg nedladdningshastighet SharePoint fronten</span><span class="sxs-lookup"><span data-stu-id="4b737-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="4b737-177">Den här insikten visas om tjänsten för nätverksinsikter upptäcker att bandbredden mellan den specifika kontorsplatsen och den SharePoint Online är mindre än 1 MBP.</span><span class="sxs-lookup"><span data-stu-id="4b737-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="4b737-178">Den här insikten är förkortad som "Dataflöde" i vissa sammanfattningsvyer.</span><span class="sxs-lookup"><span data-stu-id="4b737-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-179">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-179">What does this mean?</span></span>

<span data-ttu-id="4b737-180">Den nedladdningshastighet som en användare kan få från SharePoint Online och OneDrive för företag av dörrar till tjänstens framsida mäts i megabyte per sekund (MBps).</span><span class="sxs-lookup"><span data-stu-id="4b737-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="4b737-181">Om det här värdet är mindre än 1 MBP ger vi den här insikten.</span><span class="sxs-lookup"><span data-stu-id="4b737-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-182">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-182">What should I do?</span></span>

<span data-ttu-id="4b737-183">Bandbredden kan behöva ökas för att förbättra nedladdningshastigheten.</span><span class="sxs-lookup"><span data-stu-id="4b737-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="4b737-184">Alternativt kan nätverksstockningar vara överbelastade mellan användares datorer på kontoret och SharePoint Online-tjänstens dörr.</span><span class="sxs-lookup"><span data-stu-id="4b737-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="4b737-185">Det här kallas ibland för grattis till förlust och det begränsar nedladdningshastigheten som är tillgänglig för användarna även om det finns tillräcklig bandbredd.</span><span class="sxs-lookup"><span data-stu-id="4b737-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="4b737-186">Optimal utgående nätverkstrafik för användare i Kina</span><span class="sxs-lookup"><span data-stu-id="4b737-186">China user optimal network egress</span></span>

<span data-ttu-id="4b737-187">Den här insikten visas om din organisation har användare i Kina som ansluter till Microsoft 365-klientorganisation i andra geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="4b737-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-188">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-188">What does this mean?</span></span>

<span data-ttu-id="4b737-189">Om din organisation har privat WAN-anslutning rekommenderar vi att du konfigurerar en WAN-nätverkskrets från dina kontorsplatser i Kina som har utgående nätverk till Internet på någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="4b737-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="4b737-190">Hongkong</span><span class="sxs-lookup"><span data-stu-id="4b737-190">Hong Kong</span></span>
- <span data-ttu-id="4b737-191">Japan </span><span class="sxs-lookup"><span data-stu-id="4b737-191">Japan</span></span>
- <span data-ttu-id="4b737-192">Taiwan</span><span class="sxs-lookup"><span data-stu-id="4b737-192">Taiwan</span></span>
- <span data-ttu-id="4b737-193">Sydkorea</span><span class="sxs-lookup"><span data-stu-id="4b737-193">South Korea</span></span>
- <span data-ttu-id="4b737-194">Singapore</span><span class="sxs-lookup"><span data-stu-id="4b737-194">Singapore</span></span>
- <span data-ttu-id="4b737-195">Malaysia</span><span class="sxs-lookup"><span data-stu-id="4b737-195">Malaysia</span></span>

<span data-ttu-id="4b737-196">Internet som går längre bort från användarna än de här platserna kommer att minska prestandan, och utgående trafik i Kina kan orsaka problem med lång fördröjning och anslutning på grund av överbelastning i andra gränser.</span><span class="sxs-lookup"><span data-stu-id="4b737-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-197">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-197">What should I do?</span></span>

<span data-ttu-id="4b737-198">Mer information om hur du åtgärdar prestandaproblem relaterade till den här insikten finns i Microsoft 365 den globala [klientorganisationens prestandaoptimering för kinaanvändare.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="4b737-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="4b737-199">Exchange exempel på anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="4b737-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="4b737-200">Den här insikten visas när 50 % eller fler av de exempelkopplingar som används påverkas.</span><span class="sxs-lookup"><span data-stu-id="4b737-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="4b737-201">Effekterna definieras av den Exchange under 60 % för varje sampel.</span><span class="sxs-lookup"><span data-stu-id="4b737-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-202">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-202">What does this mean?</span></span>

<span data-ttu-id="4b737-203">Det är en indikation på att majoriteten av dina användare troligtvis har problem med att använda Outlook ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b737-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="4b737-204">Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 60 punkter.</span><span class="sxs-lookup"><span data-stu-id="4b737-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-205">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-205">What should I do?</span></span>

<span data-ttu-id="4b737-206">Aktivera nätverksanslutning för office-plats om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="4b737-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="4b737-207">Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar Exchange och hitta sätt att förbättra nätverks perimeter på varje som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="4b737-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="4b737-208">SharePoint exempel på anslutningar som påverkas av anslutningsproblem</span><span class="sxs-lookup"><span data-stu-id="4b737-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="4b737-209">Den här insikten visas när 50 % eller fler av de exempelkopplingar som används påverkas.</span><span class="sxs-lookup"><span data-stu-id="4b737-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="4b737-210">Effekterna definieras av den SharePoint under 40 % för varje sampel.</span><span class="sxs-lookup"><span data-stu-id="4b737-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="4b737-211">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="4b737-211">What does this mean?</span></span>

<span data-ttu-id="4b737-212">Det är en indikation på att majoriteten av dina användare sannolikt har problem med användarupplevelse med SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4b737-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="4b737-213">Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 40 punkter.</span><span class="sxs-lookup"><span data-stu-id="4b737-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="4b737-214">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="4b737-214">What should I do?</span></span>

<span data-ttu-id="4b737-215">Aktivera nätverksanslutning för office-plats om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="4b737-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="4b737-216">Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar SharePoint och hitta sätt att förbättra nätverks perimeter på varje som ansluter användarna till Microsofts nätverk.</span><span class="sxs-lookup"><span data-stu-id="4b737-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b737-217">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4b737-217">Related topics</span></span>

[<span data-ttu-id="4b737-218">Nätverksanslutningen i Microsoft 365 (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4b737-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="4b737-219">Microsoft 365 nätverksutvärdering (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4b737-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="4b737-220">Microsoft 365 testverktyget för nätverksanslutning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4b737-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="4b737-221">Microsoft 365 Nätverksplatstjänster (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4b737-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
