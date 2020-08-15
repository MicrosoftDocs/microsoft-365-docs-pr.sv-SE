---
title: Optimera sid tjock leken i sidor i SharePoint Online
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du kan använda verktyget för att optimera sid tjock leken i sidor med moderna webbplatser i SharePoint Online.
ms.openlocfilehash: 64fb3c90db78a23c7f1c3fcfe604c8ef58703be0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694369"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="68eb5-103">Optimera sid tjock leken i sidor i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68eb5-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="68eb5-104">Moderna webbplats sidor för SharePoint Online innehåller serialiserad kod som krävs för att återge sidans innehåll, inklusive bilder, text, objekt i innehålls området under navigering/kommando fält och annan HTML-kod som utgör ramverket för sidan.</span><span class="sxs-lookup"><span data-stu-id="68eb5-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="68eb5-105">Sid tjock leken är en mätning av den här HTML-koden och bör begränsas för att säkerställa optimal sid inläsnings tid.</span><span class="sxs-lookup"><span data-stu-id="68eb5-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="68eb5-106">Den här artikeln hjälper dig att förstå hur du kan minska sid tjock leken på dina sidor.</span><span class="sxs-lookup"><span data-stu-id="68eb5-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="68eb5-107">Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="68eb5-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="68eb5-108">Använd verktyget för nätverksdiagnostik för SharePoint för att analysera sid tjock leken</span><span class="sxs-lookup"><span data-stu-id="68eb5-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="68eb5-109">Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="68eb5-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="68eb5-110">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="68eb5-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="68eb5-111">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="68eb5-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="68eb5-112">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="68eb5-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="68eb5-113">När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om sidan i **sid vikten under 500KB** resultat. _Diagnostic tests_</span><span class="sxs-lookup"><span data-stu-id="68eb5-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="68eb5-114">Resultatet visas i grönt om sid tjock leken är under bas linjens värde och sedan rött om sid bredden överskrider bas linjens värde.</span><span class="sxs-lookup"><span data-stu-id="68eb5-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="68eb5-115">Möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="68eb5-115">Possible results include:</span></span>

- <span data-ttu-id="68eb5-116">**Åtgärd krävs** (röd): sid bredden överskrider 500KB</span><span class="sxs-lookup"><span data-stu-id="68eb5-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="68eb5-117">**Ingen åtgärd krävs** (grön): sid tjock leken är under 500KB</span><span class="sxs-lookup"><span data-stu-id="68eb5-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="68eb5-118">Om **sid tjock leken under 500KB** resultat visas i avsnittet **åtgärdat måste** du klicka på resultatet för mer information.</span><span class="sxs-lookup"><span data-stu-id="68eb5-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Förfrågningar till SharePoint-resultat](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="68eb5-120">Åtgärda problem med sidans vikt</span><span class="sxs-lookup"><span data-stu-id="68eb5-120">Remediate page weight issues</span></span>

<span data-ttu-id="68eb5-121">Om sid tjock leken överskrider 500KB kan du förbättra den allmänna sid inläsnings tiden genom att minska antalet webb delar och begränsa sid innehållet till en lämplig grad.</span><span class="sxs-lookup"><span data-stu-id="68eb5-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="68eb5-122">Allmänna rikt linjer för att minska sid vikten inkluderar:</span><span class="sxs-lookup"><span data-stu-id="68eb5-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="68eb5-123">Begränsa sid innehållet till ett rimligt belopp och Använd flera sidor för relaterat innehåll.</span><span class="sxs-lookup"><span data-stu-id="68eb5-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="68eb5-124">Minimera användningen av webb delar som har stora egenskaps uppsättningar.</span><span class="sxs-lookup"><span data-stu-id="68eb5-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="68eb5-125">Använd icke-interaktiva upplyft vy när så är möjligt.</span><span class="sxs-lookup"><span data-stu-id="68eb5-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="68eb5-126">Optimera bild storlekarna genom att använda komprimerade bild format och se till att de hämtas från ett CDN.</span><span class="sxs-lookup"><span data-stu-id="68eb5-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="68eb5-127">Du hittar ytterligare vägledning om hur du begränsar sid tjock leken i följande artikel:</span><span class="sxs-lookup"><span data-stu-id="68eb5-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="68eb5-128">Optimera sid prestanda i SharePoint</span><span class="sxs-lookup"><span data-stu-id="68eb5-128">Optimize page performance in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="68eb5-129">Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten.</span><span class="sxs-lookup"><span data-stu-id="68eb5-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="68eb5-130">Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.</span><span class="sxs-lookup"><span data-stu-id="68eb5-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="68eb5-132">Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden.</span><span class="sxs-lookup"><span data-stu-id="68eb5-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="68eb5-133">Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.</span><span class="sxs-lookup"><span data-stu-id="68eb5-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68eb5-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="68eb5-134">Related topics</span></span>

[<span data-ttu-id="68eb5-135">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="68eb5-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="68eb5-136">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="68eb5-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="68eb5-137">Prestanda i den moderna SharePoint-upplevelsen</span><span class="sxs-lookup"><span data-stu-id="68eb5-137">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="68eb5-138">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="68eb5-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="68eb5-139">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68eb5-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
