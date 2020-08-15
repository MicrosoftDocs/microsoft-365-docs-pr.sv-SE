---
title: Introduktion till prestanda justering för SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: I den här artikeln förklaras vilka specifika aspekter du bör tänka på när du utformar sidor för bästa prestanda i SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694819"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="b5887-103">Introduktion till prestanda justering för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="b5887-104">I den här artikeln förklaras vilka specifika aspekter du bör tänka på när du utformar sidor för bästa prestanda i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b5887-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="b5887-105">SharePoint Online-statistik</span><span class="sxs-lookup"><span data-stu-id="b5887-105">SharePoint Online metrics</span></span>

<span data-ttu-id="b5887-106">Följande breda mått för SharePoint Online ger Real data om prestanda:</span><span class="sxs-lookup"><span data-stu-id="b5887-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="b5887-107">Hur fasta sidor läses in</span><span class="sxs-lookup"><span data-stu-id="b5887-107">How fast pages load</span></span>
    
- <span data-ttu-id="b5887-108">Hur många rund resor som krävs per sida</span><span class="sxs-lookup"><span data-stu-id="b5887-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="b5887-109">Problem med tjänsten</span><span class="sxs-lookup"><span data-stu-id="b5887-109">Issues with the service</span></span>
    
- <span data-ttu-id="b5887-110">Andra saker som orsakar prestanda försämring</span><span class="sxs-lookup"><span data-stu-id="b5887-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="b5887-111">Slut satser som har nåtts på grund av data</span><span class="sxs-lookup"><span data-stu-id="b5887-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="b5887-112">Informationen säger att:</span><span class="sxs-lookup"><span data-stu-id="b5887-112">The data tells us:</span></span>
  
- <span data-ttu-id="b5887-113">De flesta sidorna fungerar bra på SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b5887-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="b5887-114">Icke anpassade sidor laddas snabbt.</span><span class="sxs-lookup"><span data-stu-id="b5887-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="b5887-115">OneDrive för företag, grupp webbplatser och system sidor, till exempel _layouts etc., är snabbt att läsa in.</span><span class="sxs-lookup"><span data-stu-id="b5887-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="b5887-116">De långsammast 1% av SharePoint Online-sidorna tar mer än 5 000 millisekunder att läsa in.</span><span class="sxs-lookup"><span data-stu-id="b5887-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="b5887-117">Ett enkelt benchmark-test du kan använda är att mäta prestanda genom att jämföra inläsnings tiden för din egen portal mot inläsnings tiden för OneDrive för företag – start sidan, eftersom det innehåller få anpassade funktioner.</span><span class="sxs-lookup"><span data-stu-id="b5887-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="b5887-118">Det här är ofta det första steg supporten ber dig genomföra när du felsöker problem med nätverks prestanda.</span><span class="sxs-lookup"><span data-stu-id="b5887-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="b5887-119">Använda ett vanligt användar konto när du kontrollerar prestanda</span><span class="sxs-lookup"><span data-stu-id="b5887-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="b5887-120">En administratör för en webbplats samling, webbplats ägare, redigerare eller deltagare tillhör ytterligare säkerhets grupper, har ytterligare behörigheter och kan därför innehålla ytterligare element som SharePoint läser in på en sida.</span><span class="sxs-lookup"><span data-stu-id="b5887-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="b5887-121">Det här gäller för SharePoint lokalt och SharePoint Online, men i ett lokalt scenario är skillnaderna inte lika lätt att notera som i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b5887-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="b5887-122">För att du ska kunna utvärdera hur en sida fungerar för användarna bör du använda ett vanligt användar konto för att undvika att läsa in redigerings kontroller och ytterligare trafik relaterade till säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="b5887-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="b5887-123">Anslutnings kategorier för prestanda justering</span><span class="sxs-lookup"><span data-stu-id="b5887-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="b5887-124">Du kan kategorisera anslutningar mellan servern och användaren i tre huvud komponenter.</span><span class="sxs-lookup"><span data-stu-id="b5887-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="b5887-125">Tänk på följande när du utformar SharePoint Online-sidor för inläsning av laddnings tider.</span><span class="sxs-lookup"><span data-stu-id="b5887-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="b5887-126">**Server** Servrar som Microsoft-värdar i Data Center.</span><span class="sxs-lookup"><span data-stu-id="b5887-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="b5887-127">**Nätverk** Microsoft-nätverket, Internet och det lokala nätverket mellan data centret och dina användare.</span><span class="sxs-lookup"><span data-stu-id="b5887-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="b5887-128">**Webbläsare** Där sidan laddas.</span><span class="sxs-lookup"><span data-stu-id="b5887-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="b5887-129">Inom dessa tre anslutningar är det vanligt vis fem skäl att orsaka 95% av långsamma sidor.</span><span class="sxs-lookup"><span data-stu-id="b5887-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="b5887-130">Var och en av följande anledningar finns i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="b5887-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="b5887-131">Navigerings problem</span><span class="sxs-lookup"><span data-stu-id="b5887-131">Navigation issues</span></span>
    
- <span data-ttu-id="b5887-132">Innehåll som lyfts upp</span><span class="sxs-lookup"><span data-stu-id="b5887-132">Content roll up</span></span>
    
- <span data-ttu-id="b5887-133">Stora filer</span><span class="sxs-lookup"><span data-stu-id="b5887-133">Large files</span></span>
    
- <span data-ttu-id="b5887-134">Många förfrågningar till servern</span><span class="sxs-lookup"><span data-stu-id="b5887-134">Many requests to the server</span></span>
    
- <span data-ttu-id="b5887-135">Bearbetning av webb delar</span><span class="sxs-lookup"><span data-stu-id="b5887-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="b5887-136">Server anslutning</span><span class="sxs-lookup"><span data-stu-id="b5887-136">Server connection</span></span>

<span data-ttu-id="b5887-137">Många av de problem som påverkar prestanda med SharePoint lokalt gäller även för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b5887-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="b5887-138">Som du skulle förvänta dig har du mycket mer kontroll över hur servrar fungerar med lokala SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b5887-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="b5887-139">Med SharePoint Online-saker är något annat.</span><span class="sxs-lookup"><span data-stu-id="b5887-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="b5887-140">Det mer du gör med en server är det längre att ta en sida.</span><span class="sxs-lookup"><span data-stu-id="b5887-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="b5887-141">Med SharePoint är det största culprit i detta hänseende komplexa sidor med flera webb delar.</span><span class="sxs-lookup"><span data-stu-id="b5887-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="b5887-142">SharePoint Server lokalt</span><span class="sxs-lookup"><span data-stu-id="b5887-142">SharePoint Server on-premises</span></span>
  
![Skärm bild av lokal server](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="b5887-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-144">SharePoint Online</span></span>
  
![Skärm bild av server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="b5887-146">Med SharePoint Online kan vissa sid förfrågningar faktiskt avsluta samtalen med flera servrar.</span><span class="sxs-lookup"><span data-stu-id="b5887-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="b5887-147">Du kan få en matris med förfrågningar mellan servrar för en enskild begäran.</span><span class="sxs-lookup"><span data-stu-id="b5887-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="b5887-148">Dessa interaktioner är dyra från ett sid inläsnings perspektiv och gör dem långsamt.</span><span class="sxs-lookup"><span data-stu-id="b5887-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="b5887-149">Här är några exempel på Server interaktion:</span><span class="sxs-lookup"><span data-stu-id="b5887-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="b5887-150">Webben till SQL Servers</span><span class="sxs-lookup"><span data-stu-id="b5887-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="b5887-151">Webb till program servrar</span><span class="sxs-lookup"><span data-stu-id="b5887-151">Web to application servers</span></span>
    
<span data-ttu-id="b5887-152">Det andra som kan sakta ner kommunikationen mellan servrar är cache-missar.</span><span class="sxs-lookup"><span data-stu-id="b5887-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="b5887-153">Till skillnad från lokala SharePoint-servrar är det en väldigt tunn chans att du kommer att trycka på samma server för en sida som du har besökt tidigare; då görs föråldrad objektcache.</span><span class="sxs-lookup"><span data-stu-id="b5887-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="b5887-154">Nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="b5887-154">Network connection</span></span>

<span data-ttu-id="b5887-155">Med lokal SharePoint som inte utnyttjar ett WAN kan du använda en snabb anslutning mellan data Center och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="b5887-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="b5887-156">Vanligt vis är det lätt att hantera saker från ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="b5887-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="b5887-157">Med SharePoint Online är det några fler faktorer att överväga, till exempel:</span><span class="sxs-lookup"><span data-stu-id="b5887-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="b5887-158">Microsoft-nätverket</span><span class="sxs-lookup"><span data-stu-id="b5887-158">The Microsoft network</span></span>
    
- <span data-ttu-id="b5887-159">Internet</span><span class="sxs-lookup"><span data-stu-id="b5887-159">The Internet</span></span>
    
- <span data-ttu-id="b5887-160">Internet leverantören</span><span class="sxs-lookup"><span data-stu-id="b5887-160">The ISP</span></span>
    
<span data-ttu-id="b5887-161">Oavsett vilken version av SharePoint (och vilket nätverk) du använder är det vanligt vis möjligt att nätverket är upptaget genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="b5887-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="b5887-162">Stor nytto Last</span><span class="sxs-lookup"><span data-stu-id="b5887-162">Large payload</span></span>
    
- <span data-ttu-id="b5887-163">Många filer</span><span class="sxs-lookup"><span data-stu-id="b5887-163">Many files</span></span>
    
- <span data-ttu-id="b5887-164">Stort fysiskt avstånd på servern</span><span class="sxs-lookup"><span data-stu-id="b5887-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="b5887-165">En funktion som du kan använda i SharePoint Online är Microsoft CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="b5887-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="b5887-166">Ett CDN är i stort sett en distribuerad samling servrar som distribueras i flera data Center.</span><span class="sxs-lookup"><span data-stu-id="b5887-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="b5887-167">Med en CDN kan innehållet på sidor finnas på en server som är nära klienten även om klienten är långt borta från den ursprungliga SharePoint-servern.</span><span class="sxs-lookup"><span data-stu-id="b5887-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="b5887-168">Microsoft kommer att använda mer i framtiden för att lagra lokala instanser av sidor som inte kan anpassas, till exempel start sidan för SharePoint Online-administratören.</span><span class="sxs-lookup"><span data-stu-id="b5887-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="b5887-169">Mer information om CDN finns i avsnittet [innehålls leverans nätverk](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="b5887-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="b5887-170">Något som du måste känna till men kanske inte kan göra mycket om det är Internet leverantörens anslutnings hastighet.</span><span class="sxs-lookup"><span data-stu-id="b5887-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="b5887-171">Ett enkelt Speed-testverktyg ger dig anslutnings hastigheten.</span><span class="sxs-lookup"><span data-stu-id="b5887-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="b5887-172">Webb läsar anslutning</span><span class="sxs-lookup"><span data-stu-id="b5887-172">Browser connection</span></span>

<span data-ttu-id="b5887-173">Det finns några saker du bör tänka på när det gäller webbläsare från ett prestanda perspektiv.</span><span class="sxs-lookup"><span data-stu-id="b5887-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="b5887-174">Att besöka komplexa sidor påverkar prestanda.</span><span class="sxs-lookup"><span data-stu-id="b5887-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="b5887-175">De flesta webbläsare har bara ett litet cacheminne (runt 90MB), medan den genomsnittliga webb sidan normalt är cirka 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="b5887-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="b5887-176">Det tar inte lång tid att komma igång.</span><span class="sxs-lookup"><span data-stu-id="b5887-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="b5887-177">Bandbredd kan också vara ett problem.</span><span class="sxs-lookup"><span data-stu-id="b5887-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="b5887-178">Om en användare till exempel tittar på videoklipp i en annan session påverkar detta SharePoint-sidans prestanda.</span><span class="sxs-lookup"><span data-stu-id="b5887-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="b5887-179">Även om du inte kan hindra användare från att strömma media kan du kontrol lera hur en sida laddas för användarna.</span><span class="sxs-lookup"><span data-stu-id="b5887-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="b5887-180">Läs följande artiklar för olika anpassnings tekniker för SharePoint Online och andra tips för att få optimal prestanda.</span><span class="sxs-lookup"><span data-stu-id="b5887-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="b5887-181">Navigerings alternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-182">Använda verktyget för nätverksdiagnostik för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="b5887-183">Bild optimering för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-184">Fördröj inläsning av bilder och Java Script i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-185">För minskning och buntar i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-186">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="b5887-187">Använda webb delen för innehålls sökning i stället för webb delen innehålls fråga för att förbättra prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="b5887-188">Kapacitetsplanering och belastningstestning av SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-189">Diagnosticera prestanda problem med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-190">Använda objektcachen med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="b5887-191">Så här gör du för att undvika begränsning eller blockering i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b5887-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

