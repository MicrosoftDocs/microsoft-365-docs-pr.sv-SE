---
title: Introduktion till prestandajustering för SharePoint Online
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
description: I den här artikeln förklaras vilka specifika aspekter du måste tänka på när du skapar sidor för bästa möjliga prestanda i SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909744"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="95c2d-103">Introduktion till prestandajustering för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="95c2d-104">I den här artikeln förklaras vilka specifika aspekter du måste tänka på när du skapar sidor för bästa möjliga prestanda i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="95c2d-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="95c2d-105">Mått i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-105">SharePoint Online metrics</span></span>

<span data-ttu-id="95c2d-106">Följande breda mått för SharePoint Online ger verkliga data om prestanda:</span><span class="sxs-lookup"><span data-stu-id="95c2d-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="95c2d-107">Hur snabbt sidor läses in</span><span class="sxs-lookup"><span data-stu-id="95c2d-107">How fast pages load</span></span>
    
- <span data-ttu-id="95c2d-108">Hur många tur och returresor som krävs per sida</span><span class="sxs-lookup"><span data-stu-id="95c2d-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="95c2d-109">Problem med tjänsten</span><span class="sxs-lookup"><span data-stu-id="95c2d-109">Issues with the service</span></span>
    
- <span data-ttu-id="95c2d-110">Andra saker som kan medföra försämrad prestanda</span><span class="sxs-lookup"><span data-stu-id="95c2d-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="95c2d-111">Beslut som har uppnåtts på grund av data</span><span class="sxs-lookup"><span data-stu-id="95c2d-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="95c2d-112">Data talar om för oss:</span><span class="sxs-lookup"><span data-stu-id="95c2d-112">The data tells us:</span></span>
  
- <span data-ttu-id="95c2d-113">De flesta sidor fungerar bra i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="95c2d-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="95c2d-114">Det går mycket snabbt att läsa in sidor som inte är anpassade.</span><span class="sxs-lookup"><span data-stu-id="95c2d-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="95c2d-115">OneDrive för företag, gruppwebbplatser och systemsidor, till exempel _layouts och så vidare, är snabba att läsa in.</span><span class="sxs-lookup"><span data-stu-id="95c2d-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="95c2d-116">Den långsammaste procenten SharePoint Online-sidor tar mer än 5 000 millisekunder att läsa in.</span><span class="sxs-lookup"><span data-stu-id="95c2d-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="95c2d-117">Ett enkelt prestandatest du kan använda är att mäta prestandan genom att jämföra inläsningstiden för din egen portal med inläsningstiden för startsidan för OneDrive för företag, eftersom den inte har så många anpassade funktioner.</span><span class="sxs-lookup"><span data-stu-id="95c2d-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="95c2d-118">Supporten ber dig gärna att göra det första steget när du felsöker prestandaproblem i nätverket.</span><span class="sxs-lookup"><span data-stu-id="95c2d-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="95c2d-119">Använda ett vanligt användarkonto när du kontrollerar prestanda</span><span class="sxs-lookup"><span data-stu-id="95c2d-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="95c2d-120">En administratör för webbplatssamlingen, webbplatsägare, redaktör eller deltagare tillhör ytterligare säkerhetsgrupper, har ytterligare behörigheter och har därför ytterligare element som läses in på en sida av SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c2d-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="95c2d-121">Det här gäller för lokal SharePoint och SharePoint Online, men i ett lokalt scenario kommer skillnaderna inte att vara lika lätta att se som i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="95c2d-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="95c2d-122">Om du vill utvärdera hur en sida kommer att se ut för användare bör du använda ett standardanvändarkonto för att undvika inläsning av redigeringskontroller och extra trafik relaterad till säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="95c2d-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="95c2d-123">Anslutningskategorier för prestandajustering</span><span class="sxs-lookup"><span data-stu-id="95c2d-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="95c2d-124">Du kan kategorisera anslutningarna mellan servern och användaren i tre huvudkomponenter.</span><span class="sxs-lookup"><span data-stu-id="95c2d-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="95c2d-125">Tänk på de här när du skapar SharePoint Online-sidor och vill ha insyn i inläsningstider.</span><span class="sxs-lookup"><span data-stu-id="95c2d-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="95c2d-126">**Server** Servrarna som Microsoft är värd för i datacenter.</span><span class="sxs-lookup"><span data-stu-id="95c2d-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="95c2d-127">**Nätverk** Microsofts nätverk, Internet och ditt lokala nätverk mellan datacentret och dina användare.</span><span class="sxs-lookup"><span data-stu-id="95c2d-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="95c2d-128">**Webbläsare** Här läses sidan in.</span><span class="sxs-lookup"><span data-stu-id="95c2d-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="95c2d-129">I de här tre anslutningarna finns vanligtvis fem orsaker till 95 % av alla långsamma sidor.</span><span class="sxs-lookup"><span data-stu-id="95c2d-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="95c2d-130">Var och en av de här orsakerna tas upp i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="95c2d-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="95c2d-131">Navigeringsproblem</span><span class="sxs-lookup"><span data-stu-id="95c2d-131">Navigation issues</span></span>
    
- <span data-ttu-id="95c2d-132">Innehåll som återställs</span><span class="sxs-lookup"><span data-stu-id="95c2d-132">Content roll up</span></span>
    
- <span data-ttu-id="95c2d-133">Stora filer</span><span class="sxs-lookup"><span data-stu-id="95c2d-133">Large files</span></span>
    
- <span data-ttu-id="95c2d-134">Många förfrågningar till servern</span><span class="sxs-lookup"><span data-stu-id="95c2d-134">Many requests to the server</span></span>
    
- <span data-ttu-id="95c2d-135">Bearbetning av webbdel</span><span class="sxs-lookup"><span data-stu-id="95c2d-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="95c2d-136">Serveranslutning</span><span class="sxs-lookup"><span data-stu-id="95c2d-136">Server connection</span></span>

<span data-ttu-id="95c2d-137">Många av de problem som påverkar prestandan för SharePoint lokalt gäller även för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="95c2d-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="95c2d-138">Som förväntat har du mycket större kontroll över hur servrar fungerar lokalt med SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c2d-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="95c2d-139">Med SharePoint Online är saker lite annorlunda.</span><span class="sxs-lookup"><span data-stu-id="95c2d-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="95c2d-140">Ju mer arbete du får en server att göra, desto längre tid tar det att återge en sida.</span><span class="sxs-lookup"><span data-stu-id="95c2d-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="95c2d-141">Med SharePoint är den största boven i det här avseendet komplexa sidor med flera webbdelar.</span><span class="sxs-lookup"><span data-stu-id="95c2d-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="95c2d-142">SharePoint Server lokalt</span><span class="sxs-lookup"><span data-stu-id="95c2d-142">SharePoint Server on-premises</span></span>
  
![Skärmbild av lokal server](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="95c2d-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-144">SharePoint Online</span></span>
  
![Skärmbild av server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="95c2d-146">Med SharePoint Online kan vissa förfrågningar faktiskt anropa flera servrar.</span><span class="sxs-lookup"><span data-stu-id="95c2d-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="95c2d-147">Du kan få en matris med förfrågningar mellan servrar för en enskild begäran.</span><span class="sxs-lookup"><span data-stu-id="95c2d-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="95c2d-148">Dessa interaktioner kostar mycket ur ett inläsningsperspektiv och gör att sidor läses in långsamt.</span><span class="sxs-lookup"><span data-stu-id="95c2d-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="95c2d-149">Här är några exempel på sådana interaktioner mellan servrar:</span><span class="sxs-lookup"><span data-stu-id="95c2d-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="95c2d-150">Webb till SQL-servrar</span><span class="sxs-lookup"><span data-stu-id="95c2d-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="95c2d-151">Webb till programservrar</span><span class="sxs-lookup"><span data-stu-id="95c2d-151">Web to application servers</span></span>
    
<span data-ttu-id="95c2d-152">En annan sak som kan göra att serverinteraktioner tar lång tid är cachemissar.</span><span class="sxs-lookup"><span data-stu-id="95c2d-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="95c2d-153">Till skillnad från ett lokalt SharePoint finns det en liten möjlighet att du träffar samma server för en sida du besökt tidigare. Det här gör cachelagringen av objekt inaktuell.</span><span class="sxs-lookup"><span data-stu-id="95c2d-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="95c2d-154">Nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="95c2d-154">Network connection</span></span>

<span data-ttu-id="95c2d-155">Med ett lokalt SharePoint som inte använder ett WAN kan du använda en snabb anslutning mellan datacentret och slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="95c2d-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="95c2d-156">I allmänhet är det enkelt att hantera saker ur ett nätverksperspektiv.</span><span class="sxs-lookup"><span data-stu-id="95c2d-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="95c2d-157">Med SharePoint Online finns det några fler faktorer att tänka på: till exempel:</span><span class="sxs-lookup"><span data-stu-id="95c2d-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="95c2d-158">Microsoft-nätverket</span><span class="sxs-lookup"><span data-stu-id="95c2d-158">The Microsoft network</span></span>
    
- <span data-ttu-id="95c2d-159">The Internet</span><span class="sxs-lookup"><span data-stu-id="95c2d-159">The Internet</span></span>
    
- <span data-ttu-id="95c2d-160">Internetleverantören</span><span class="sxs-lookup"><span data-stu-id="95c2d-160">The ISP</span></span>
    
<span data-ttu-id="95c2d-161">Oavsett vilken version av SharePoint (och vilket nätverk) du använder kan följande göra att nätverket är upptaget:</span><span class="sxs-lookup"><span data-stu-id="95c2d-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="95c2d-162">Stora nyttolaster</span><span class="sxs-lookup"><span data-stu-id="95c2d-162">Large payload</span></span>
    
- <span data-ttu-id="95c2d-163">Många filer</span><span class="sxs-lookup"><span data-stu-id="95c2d-163">Many files</span></span>
    
- <span data-ttu-id="95c2d-164">Stora fysiska avstånd till servern</span><span class="sxs-lookup"><span data-stu-id="95c2d-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="95c2d-165">En funktion som du kan dra nytta av i SharePoint Online är Microsoft CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="95c2d-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="95c2d-166">Ett CDN är i princip en samling servrar som distribuerats över flera datacenter.</span><span class="sxs-lookup"><span data-stu-id="95c2d-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="95c2d-167">Med ett CDN kan innehåll på sidor lagras på en server nära klienten även om klienten är långt från den ursprungliga SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="95c2d-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="95c2d-168">Microsoft kommer att använda detta mer i framtiden till att lagra lokala instanser av sidor som inte kan anpassas, till exempel startsidan för SharePoint Online-administratörer.</span><span class="sxs-lookup"><span data-stu-id="95c2d-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="95c2d-169">Mer information om CDN finns i [Nätverk för innehållsleverans.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="95c2d-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="95c2d-170">En sak som du måste vara medveten om men kanske inte kan göra så mycket åt är Internetleverantörens anslutningshastighet.</span><span class="sxs-lookup"><span data-stu-id="95c2d-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="95c2d-171">Ett enkelt testverktyg för hastighet kan ge information om anslutningshastigheten.</span><span class="sxs-lookup"><span data-stu-id="95c2d-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="95c2d-172">Webbläsaranslutning</span><span class="sxs-lookup"><span data-stu-id="95c2d-172">Browser connection</span></span>

<span data-ttu-id="95c2d-173">Det finns några faktorer att tänka på när det gäller webbläsare ur ett prestandaperspektiv.</span><span class="sxs-lookup"><span data-stu-id="95c2d-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="95c2d-174">Att besöka komplexa sidor kommer att påverka prestandan.</span><span class="sxs-lookup"><span data-stu-id="95c2d-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="95c2d-175">De flesta webbläsare bara har en liten cache (cirka 90 MB), medan en genomsnittlig webbsida normalt är cirka 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="95c2d-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="95c2d-176">Det tar inte lång tid att använda upp den.</span><span class="sxs-lookup"><span data-stu-id="95c2d-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="95c2d-177">Bandbredd kan också vara ett problem.</span><span class="sxs-lookup"><span data-stu-id="95c2d-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="95c2d-178">Om en användare till exempel visar videoklipp i en annan session kommer detta att påverka prestandan för SharePoint-sidan.</span><span class="sxs-lookup"><span data-stu-id="95c2d-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="95c2d-179">Du kan inte hindra användare från att direktuppspela media, men du kan styra hur en sida läses in för användarna.</span><span class="sxs-lookup"><span data-stu-id="95c2d-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="95c2d-180">Läs följande artiklar för olika anpassningstekniker för SharePoint Online-sidor och andra metodtips för att uppnå optimala prestanda.</span><span class="sxs-lookup"><span data-stu-id="95c2d-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="95c2d-181">Navigeringsalternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-182">Använda verktyget Siddiagnostik för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="95c2d-183">Bildoptimering för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-184">Fördröja inläsning av bilder och JavaScript i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-185">Förgrening och sammanslagning i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-186">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="95c2d-187">Använda webbdel för innehållssökning i stället för webbdel för innehållsfråga för att förbättra prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="95c2d-188">Kapacitetsplanering och belastningstestning av SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-189">Diagnostisering av prestandaproblem i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-190">Använda objektcachen med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="95c2d-191">Så här gör du för att: Undvika begränsningar och blockeringar i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95c2d-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
