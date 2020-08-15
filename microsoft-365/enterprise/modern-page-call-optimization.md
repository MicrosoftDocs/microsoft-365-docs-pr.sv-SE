---
title: Optimera sid samtal i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du optimerar sidor för en modern och klassisk publicerings webbplats i SharePoint Online genom att begränsa antalet samtal till SharePoint Online-tjänstens slut punkter.
ms.openlocfilehash: b3c41dfe308f1546887f28cf0e8fbe9ab4dc2761
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694907"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="4c3e9-103">Optimera sid samtal i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser</span><span class="sxs-lookup"><span data-stu-id="4c3e9-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="4c3e9-104">Både moderna och klassiska SharePoint Online-webbplatser innehåller länkar som läser in data från (eller ringer till) SharePoint-funktioner och CDN.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="4c3e9-105">Det fler samtal som görs av en sida, desto längre tid tar det att läsa in sidan.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="4c3e9-106">Detta kallas **slutanvändarens uppskattade svars tid** eller **EUPL**.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="4c3e9-107">Den här artikeln hjälper dig att förstå hur du tar reda på hur många samtal som kommer till externa slut punkter från dina sidor för en modern och en klassisk publicerings webbplats och hur du kan begränsa deras effekt på slutanvändarens uppskattade svars tid.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="4c3e9-108">Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="4c3e9-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="4c3e9-109">Analysera samtal med Page Diagnostics för SharePoint</span><span class="sxs-lookup"><span data-stu-id="4c3e9-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="4c3e9-110">Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="4c3e9-111">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="4c3e9-112">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="4c3e9-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="4c3e9-113">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="4c3e9-114">När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du se information om externa samtal i resultatet **till SharePoint** i fönstret _diagnostiktest_ .</span><span class="sxs-lookup"><span data-stu-id="4c3e9-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="4c3e9-115">Raden kommer att synas i grönt om webbplats sidan innehåller färre än bas linjens antal samtal och rött om sidan överskrider original numret.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="4c3e9-116">Original Plans numret skiljer sig från de moderna och klassiska sidorna eftersom webb sidor använder HTTP 1.1 och moderna sidor använder HTTP 2.0:</span><span class="sxs-lookup"><span data-stu-id="4c3e9-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="4c3e9-117">Moderna webbplats sidor ska innehålla högst **25** samtal</span><span class="sxs-lookup"><span data-stu-id="4c3e9-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="4c3e9-118">Klassiska publicerings sidor ska innehålla högst **6** samtal</span><span class="sxs-lookup"><span data-stu-id="4c3e9-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="4c3e9-119">Möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="4c3e9-119">Possible results include:</span></span>

- <span data-ttu-id="4c3e9-120">**Åtgärd krävs** (röd): Sidan överskrider bas linjens antal samtal</span><span class="sxs-lookup"><span data-stu-id="4c3e9-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="4c3e9-121">**Ingen åtgärd krävs** (grön): Sidan innehåller färre än bas linje numret för samtal</span><span class="sxs-lookup"><span data-stu-id="4c3e9-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="4c3e9-122">Om **begäran till SharePoint** -resultatet visas i avsnittet **åtgärdat krävs** kan du klicka på resultatet för att få information, inklusive det totala antalet samtal på sidan och en lista med URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Förfrågningar till SharePoint-resultat](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="4c3e9-124">Åtgärda prestanda problem relaterade till för många samtal på en sida</span><span class="sxs-lookup"><span data-stu-id="4c3e9-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="4c3e9-125">Om en sida innehåller för många samtal kan du använda listan med URL-adresser i **förfrågningar till SharePoint** -resultat för att avgöra om det finns upprepade samtal, samtal som ska registreras eller samtal som returnerar data som ska cachelagras.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="4c3e9-126">Med **grupp rest-samtal** kan du minska prestanda.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="4c3e9-127">Mer information om hur du grupperar API-samtal finns i [göra batch-begäranden med resten av API: erna](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="4c3e9-127">For more information about API call batching, see [Make batch requests with the REST APIs](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="4c3e9-128">Om du **använder ett cacheminne** för att lagra resultaten av ett API-samtal kan du förbättra prestandan hos en varm förfrågan genom att låta klienten använda cachelagrade data i stället för att ringa ytterligare ett samtal för varje efterföljande sid laddning.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="4c3e9-129">Det finns flera sätt att närma den här lösningen beroende på affärs kraven.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="4c3e9-130">Vanligt vis om data kommer att vara desamma för alla användare, är det lämpligt att använda mellannivå caching-tjänsten, till exempel att [ _Azure Redis_ cache](https://azure.microsoft.com/services/cache/) är ett bra alternativ för att avsevärt minska API-trafik mot en webbplats, eftersom användarna kan begära data från cache-tjänsten i stället för direkt från SPO.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="4c3e9-131">De enda SPO-samtal som krävs är att uppdatera mellanskiktets cache.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="4c3e9-132">Om data kommer att ändras för enskilda användare kanske det är bäst att implementera ett klient-Side-cacheminne, till exempel LocalStorage eller till och med en cookie.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="4c3e9-133">Detta minskar antalet samtals volymer genom att eliminera efterföljande begär Anden som görs av samma användare under cachens varaktighet, men det är mindre effektivt än en särskild cache-tjänst.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="4c3e9-134">Med PnP kan du använda LocalStorage med lite extra utveckling som krävs.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="4c3e9-135">Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="4c3e9-136">Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="4c3e9-138">Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="4c3e9-139">Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.</span><span class="sxs-lookup"><span data-stu-id="4c3e9-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c3e9-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4c3e9-140">Related topics</span></span>

[<span data-ttu-id="4c3e9-141">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="4c3e9-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="4c3e9-142">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="4c3e9-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="4c3e9-143">Prestanda i den moderna SharePoint-upplevelsen</span><span class="sxs-lookup"><span data-stu-id="4c3e9-143">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="4c3e9-144">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="4c3e9-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="4c3e9-145">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4c3e9-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
