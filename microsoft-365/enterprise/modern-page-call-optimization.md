---
title: Optimera sidsamtal i SharePoint moderna och klassiska publiceringswebbplatssidor
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
description: Lär dig hur du optimerar moderna och klassiska publiceringswebbplatssidor i SharePoint Online genom att begränsa antalet samtal SharePoint slutpunkter för onlinetjänsten.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921624"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="04b45-103">Optimera sidsamtal i SharePoint moderna och klassiska publiceringswebbplatssidor</span><span class="sxs-lookup"><span data-stu-id="04b45-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="04b45-104">Både SharePoint moderna och klassiska publiceringswebbplatser innehåller länkar som läser in data från (eller ringer till) SharePoint och CDN.</span><span class="sxs-lookup"><span data-stu-id="04b45-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="04b45-105">Ju fler samtal en sida ringer, desto längre tid tar det att läsa in sidan.</span><span class="sxs-lookup"><span data-stu-id="04b45-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="04b45-106">Detta kallas för att **slutanvändaren uppfattas som fördröjning** eller **EUPL.**</span><span class="sxs-lookup"><span data-stu-id="04b45-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="04b45-107">Den här artikeln hjälper dig att förstå hur du fastställer antal och påverkan på samtal till externa slutpunkter från dina moderna och klassiska publiceringswebbplatssidor och hur du kan begränsa effekten på slutanvändarens uppfattas svarstid.</span><span class="sxs-lookup"><span data-stu-id="04b45-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="04b45-108">Mer information om prestanda i SharePoint moderna portaler finns i [Prestanda i det moderna SharePoint upplevelse.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="04b45-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="04b45-109">Använda siddiagnostik för SharePoint för att analysera sidsamtal</span><span class="sxs-lookup"><span data-stu-id="04b45-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="04b45-110">Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="04b45-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="04b45-111">Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor.</span><span class="sxs-lookup"><span data-stu-id="04b45-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="04b45-112">Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="04b45-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="04b45-113">Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.</span><span class="sxs-lookup"><span data-stu-id="04b45-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="04b45-114">När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint kan du se information om externa samtal i resultatet för Förfrågningar om **SharePoint** i fönstret _Diagnostiktest._</span><span class="sxs-lookup"><span data-stu-id="04b45-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="04b45-115">Linjen visas i grönt om webbplatssidan innehåller färre än baslinjenumret och röd om sidan överskrider baslinjenumret.</span><span class="sxs-lookup"><span data-stu-id="04b45-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="04b45-116">Baslinjenumret skiljer sig för moderna och klassiska sidor eftersom klassiska webbplatssidor använder HTTP1.1 och moderna sidor använder HTTP2.0:</span><span class="sxs-lookup"><span data-stu-id="04b45-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="04b45-117">Moderna webbplatssidor får inte innehålla fler än **25** samtal</span><span class="sxs-lookup"><span data-stu-id="04b45-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="04b45-118">Klassiska publiceringssidor får innehålla högst **6** samtal</span><span class="sxs-lookup"><span data-stu-id="04b45-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="04b45-119">Möjliga resultat är:</span><span class="sxs-lookup"><span data-stu-id="04b45-119">Possible results include:</span></span>

- <span data-ttu-id="04b45-120">**Obs!** Obligatoriskt (rött): Sidan överskrider baslinjenumret för samtal</span><span class="sxs-lookup"><span data-stu-id="04b45-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="04b45-121">**Ingen åtgärd krävs** (grön): Sidan innehåller färre än originalantalet samtal</span><span class="sxs-lookup"><span data-stu-id="04b45-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="04b45-122">Om resultatet **Requests to SharePoint** visas i avsnittet Attention **required** (åtgärder krävs) kan du klicka på resultatet för mer information, inklusive det totala antalet samtal på sidan och en lista över URL:er.</span><span class="sxs-lookup"><span data-stu-id="04b45-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Förfrågningar om SharePoint resultat](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="04b45-124">Åtgärda prestandaproblem som är relaterade till för många samtal på en sida</span><span class="sxs-lookup"><span data-stu-id="04b45-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="04b45-125">Om en sida innehåller för många samtal kan du använda listan med URL-adresser i Begäran om **SharePoint-resultat** för att avgöra om det finns några upprepade samtal, samtal som ska batchas eller samtal som returnerar data som ska cachelagras.</span><span class="sxs-lookup"><span data-stu-id="04b45-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="04b45-126">**Att batcha REST-samtal** kan minska prestandan.</span><span class="sxs-lookup"><span data-stu-id="04b45-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="04b45-127">Mer information om API-anropsbatchning finns [i Göra batchbegäranden med REST-API:er.](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)</span><span class="sxs-lookup"><span data-stu-id="04b45-127">For more information about API call batching, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="04b45-128">**Om du** använder en cache för att lagra resultaten av ett API-anrop kan du förbättra prestandan för en uppvärmningsbegäran genom att låta klienten använda cachelagrade data i stället för att ringa ytterligare ett samtal för varje efterföljande sidinläsning.</span><span class="sxs-lookup"><span data-stu-id="04b45-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="04b45-129">Det finns flera sätt att hantera den här lösningen beroende på affärsbehovet.</span><span class="sxs-lookup"><span data-stu-id="04b45-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="04b45-130">Vanligtvis om data är samma för alla användare är en cachelagringstjänst på mellannivå som [ _Azure Redis-cache_](https://azure.microsoft.com/services/cache/) ett bra alternativ för att avsevärt minska API-trafiken mot en webbplats eftersom användarna skulle begära data från cachelagringstjänsten i stället för direkt från SPO.</span><span class="sxs-lookup"><span data-stu-id="04b45-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="04b45-131">De enda SPO-anrop som behövs är att uppdatera cachen på mittnivån.</span><span class="sxs-lookup"><span data-stu-id="04b45-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="04b45-132">Om data fluktuerar för enskilda användare kan det vara bäst att implementera en klientbaserad cache, som LocalStorage eller till och med en cookie.</span><span class="sxs-lookup"><span data-stu-id="04b45-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="04b45-133">Det här kommer fortfarande att minska samtalsvolymerna genom att du eliminerar efterföljande förfrågningar som görs av samma användare under cachelängden, men kommer att vara mindre effektivt än en dedikerad cachelagringstjänst.</span><span class="sxs-lookup"><span data-stu-id="04b45-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="04b45-134">Med PnP kan du använda LocalStorage med lite ytterligare utveckling som krävs.</span><span class="sxs-lookup"><span data-stu-id="04b45-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="04b45-135">Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet.</span><span class="sxs-lookup"><span data-stu-id="04b45-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="04b45-136">Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.</span><span class="sxs-lookup"><span data-stu-id="04b45-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="04b45-138">Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor.</span><span class="sxs-lookup"><span data-stu-id="04b45-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="04b45-139">Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.</span><span class="sxs-lookup"><span data-stu-id="04b45-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="04b45-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="04b45-140">Related topics</span></span>

[<span data-ttu-id="04b45-141">Justera SharePoint onlineprestanda</span><span class="sxs-lookup"><span data-stu-id="04b45-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="04b45-142">Justera Office 365 prestanda</span><span class="sxs-lookup"><span data-stu-id="04b45-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="04b45-143">Prestanda i den moderna SharePoint upplevelsen</span><span class="sxs-lookup"><span data-stu-id="04b45-143">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="04b45-144">Nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="04b45-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="04b45-145">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="04b45-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)