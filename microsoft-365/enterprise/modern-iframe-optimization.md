---
title: Optimera iFrames i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser
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
description: Lär dig hur du optimerar prestanda i iFrames i SharePoint Online-sidor för moderna och klassisk publicerings webbplatser.
ms.openlocfilehash: 8985eb1038bbdfc53dc3c6a8ea9350fa6df33556
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694927"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="97d02-103">Optimera iFrames i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser</span><span class="sxs-lookup"><span data-stu-id="97d02-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="97d02-104">iFrames kan vara användbara när du vill förhandsgranska innehåll som videoklipp eller andra medier.</span><span class="sxs-lookup"><span data-stu-id="97d02-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="97d02-105">Men eftersom iFrames läser in en separat sida på sidan på SharePoint-webbplatsen kan innehåll som öppnas i iFrame innehålla stora bilder, videor eller andra element som kan bidra till att alla sid inläsnings tider och att du inte kan styra på sidan.</span><span class="sxs-lookup"><span data-stu-id="97d02-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="97d02-106">Den här artikeln hjälper dig att förstå hur iFrames på dina sidor påverkar uppskattad svars tid och hur du åtgärdar vanliga problem.</span><span class="sxs-lookup"><span data-stu-id="97d02-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="97d02-107">Mer information om prestanda i moderna SharePoint Online-webbplatser finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="97d02-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="97d02-108">Använda verktyget för nätverksdiagnostik för SharePoint för att analysera webb delar med hjälp av iFrames</span><span class="sxs-lookup"><span data-stu-id="97d02-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="97d02-109">Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="97d02-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="97d02-110">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="97d02-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="97d02-111">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="97d02-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="97d02-112">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="97d02-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="97d02-113">När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om webb delar som innehåller iFrames i fönstret _diagnostiktest_ .</span><span class="sxs-lookup"><span data-stu-id="97d02-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="97d02-114">Bas linjens mått är detsamma för moderna och klassiska sidor.</span><span class="sxs-lookup"><span data-stu-id="97d02-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="97d02-115">Möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="97d02-115">Possible results include:</span></span>

- <span data-ttu-id="97d02-116">**Åtgärd krävs** (röd): Sidan innehåller **tre eller fler** webb delar med iframes</span><span class="sxs-lookup"><span data-stu-id="97d02-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="97d02-117">**Förbättrings möjligheter** (gula): Sidan innehåller **en eller två** webb delar med iframes</span><span class="sxs-lookup"><span data-stu-id="97d02-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="97d02-118">**Ingen åtgärd krävs** (grön): Sidan innehåller inga webb delar med hjälp av iframes</span><span class="sxs-lookup"><span data-stu-id="97d02-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="97d02-119">Om **webb delarna med iframes identifierat** resultat visas i avsnittet **förbättring av affärs möjligheter** eller **åtgärd krävs)** kan du klicka på resultatet för att visa de webb delar som innehåller iframes.</span><span class="sxs-lookup"><span data-stu-id="97d02-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Resultat för verktyget Nätverksdiagnostik](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="97d02-121">Åtgärda problem med iFrame-prestanda</span><span class="sxs-lookup"><span data-stu-id="97d02-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="97d02-122">Använda **webb delarna med hjälp av iframes identifierade** resultatet i verktyget diskdiagnostik för att avgöra vilka webb delar som innehåller iframes och kan komma att bidra till långsamma sid laddnings tider.</span><span class="sxs-lookup"><span data-stu-id="97d02-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="97d02-123">iFrames är mycket långsamma eftersom de laddar en separat extern sida inklusive allt associerat innehåll, till exempel Java Script-, CSS-och Ramverks element, och kan öka platsens overhead med en faktor på två eller fler.</span><span class="sxs-lookup"><span data-stu-id="97d02-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="97d02-124">Följ anvisningarna nedan för att säkerställa optimal användning av iFrames.</span><span class="sxs-lookup"><span data-stu-id="97d02-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="97d02-125">När det är möjligt kan du använda bilder i stället för iFrames om förhands granskningen är liten för att börja med eller icke-interaktiv.</span><span class="sxs-lookup"><span data-stu-id="97d02-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="97d02-126">Om du måste använda iFrames kan du minimera numret och/eller flytta ut dem från visnings området.</span><span class="sxs-lookup"><span data-stu-id="97d02-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="97d02-127">Inbäddade Office-filer som Word, Excel och PowerPoint är interaktiva, men är långsamma att läsa in.</span><span class="sxs-lookup"><span data-stu-id="97d02-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="97d02-128">Miniatyrer med en länk till det fullständiga dokumentet är ofta bättre.</span><span class="sxs-lookup"><span data-stu-id="97d02-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="97d02-129">Inbäddade YouTube-videor och Twitter-feeds tenderar att utföra bättre i iFrames, men använder de här typerna av judiciously.</span><span class="sxs-lookup"><span data-stu-id="97d02-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="97d02-130">Isolerade webb delar är ett rimligt undantag men minimerar deras nummer och placering i visnings området.</span><span class="sxs-lookup"><span data-stu-id="97d02-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="97d02-131">Om det finns en iFrame utanför visnings området bör du överväga att använda en _IntersectionObserver_ för att försena renderingen av iframe tills den visas.</span><span class="sxs-lookup"><span data-stu-id="97d02-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="97d02-132">Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten.</span><span class="sxs-lookup"><span data-stu-id="97d02-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="97d02-133">Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.</span><span class="sxs-lookup"><span data-stu-id="97d02-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="97d02-135">Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden.</span><span class="sxs-lookup"><span data-stu-id="97d02-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="97d02-136">Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.</span><span class="sxs-lookup"><span data-stu-id="97d02-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="97d02-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="97d02-137">Related topics</span></span>

[<span data-ttu-id="97d02-138">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="97d02-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="97d02-139">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="97d02-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="97d02-140">Prestanda i den moderna SharePoint-upplevelsen</span><span class="sxs-lookup"><span data-stu-id="97d02-140">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)
