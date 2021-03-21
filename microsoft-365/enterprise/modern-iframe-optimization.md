---
title: Optimera iFrames i SharePoint Online för moderna och klassiska publiceringswebbplatssidor
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
description: Lär dig hur du optimerar prestanda för iFrames på moderna och klassiska publiceringswebbplatssidor i SharePoint Online.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923070"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="b911f-103">Optimera iFrames i SharePoint Online för moderna och klassiska publiceringswebbplatssidor</span><span class="sxs-lookup"><span data-stu-id="b911f-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="b911f-104">iFrames kan vara användbart för att förhandsgranska innehållsrika innehåll som videor eller andra media.</span><span class="sxs-lookup"><span data-stu-id="b911f-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="b911f-105">Men eftersom iFrames läser in en separat sida i SharePoint-webbplatssidan kan innehåll som läses in i iFrame innehålla stora bilder, videor eller andra element som kan bidra till inläsningstider för sidan och som du inte kan styra över på sidan.</span><span class="sxs-lookup"><span data-stu-id="b911f-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="b911f-106">Den här artikeln hjälper dig att förstå hur iFrames på sidorna påverkar användarens uppfattas fördröjning och hur du åtgärdar vanliga problem.</span><span class="sxs-lookup"><span data-stu-id="b911f-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="b911f-107">Mer information om prestanda i moderna SharePoint Online-webbplatser finns i [Prestanda i det moderna SharePoint-programmet.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="b911f-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="b911f-108">Använda siddiagnostik för SharePoint-verktyget för att analysera webbdelar med iFrames</span><span class="sxs-lookup"><span data-stu-id="b911f-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="b911f-109">Verktyget Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna portaler för SharePoint Online och https://www.microsoft.com/edge) klassiska publiceringswebbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="b911f-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="b911f-110">Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor.</span><span class="sxs-lookup"><span data-stu-id="b911f-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="b911f-111">Om du vill installera och lära dig mer om verktyget Siddiagnostik för SharePoint går du [till Använda verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="b911f-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="b911f-112">Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.</span><span class="sxs-lookup"><span data-stu-id="b911f-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="b911f-113">När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint kan du se information om webbdelar som innehåller iFrames i _fönstret Diagnostiktest._</span><span class="sxs-lookup"><span data-stu-id="b911f-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="b911f-114">Baslinjemåttet är detsamma för moderna och klassiska sidor.</span><span class="sxs-lookup"><span data-stu-id="b911f-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="b911f-115">Möjliga resultat är:</span><span class="sxs-lookup"><span data-stu-id="b911f-115">Possible results include:</span></span>

- <span data-ttu-id="b911f-116">**Obs!** (röd): Sidan innehåller tre **eller fler webbdelar** med iFrames</span><span class="sxs-lookup"><span data-stu-id="b911f-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="b911f-117">**Förbättringsmöjligheter** (gul): Sidan innehåller **en eller två webbdelar** med iFrames</span><span class="sxs-lookup"><span data-stu-id="b911f-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="b911f-118">**Ingen åtgärd krävs** (grön): Sidan innehåller inga webbdelar med iFrames</span><span class="sxs-lookup"><span data-stu-id="b911f-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="b911f-119">Om de webbdelar som använder **iFrames**  upptäckta resultat visas i antingen resultatavsnittet Förbättringsmöjligheter eller Åtgärder **krävs)** kan du klicka på resultatet för att se de webbdelar som innehåller iFrames.</span><span class="sxs-lookup"><span data-stu-id="b911f-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Resultat av verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="b911f-121">Åtgärda prestandaproblem i iFrame</span><span class="sxs-lookup"><span data-stu-id="b911f-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="b911f-122">Använda **webbdelarna med iFrames** upptäckt resultat i verktyget Siddiagnostik för att avgöra vilka webbdelar som innehåller iFrames och kan bidra till långsam sidinläsning.</span><span class="sxs-lookup"><span data-stu-id="b911f-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="b911f-123">iFrames är mycket långsamt eftersom de läser in en separat extern sida med allt associerat innehåll, till exempel javascript, CSS och framework-element, som potentiellt ökar kostnaderna för webbplatsens sida av en faktor för två eller fler.</span><span class="sxs-lookup"><span data-stu-id="b911f-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="b911f-124">Följ vägledning nedan för optimal användning av iFrames.</span><span class="sxs-lookup"><span data-stu-id="b911f-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="b911f-125">Använd bilder i stället för iFrames om förhandsgranskningen är liten att börja med eller icke-interaktiva.</span><span class="sxs-lookup"><span data-stu-id="b911f-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="b911f-126">Om iFrames måste användas minimerar du numret och/eller flyttar dem från visningsområdet.</span><span class="sxs-lookup"><span data-stu-id="b911f-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="b911f-127">Inbäddade Office-filer som Word, Excel och PowerPoint är interaktiva, men tar lång tid att läsa in.</span><span class="sxs-lookup"><span data-stu-id="b911f-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="b911f-128">Miniatyrbilder med en länk till det fullständiga dokumentet fungerar ofta bättre.</span><span class="sxs-lookup"><span data-stu-id="b911f-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="b911f-129">Inbäddade YouTube-videor och Twitter-feeds presterar ofta bättre i iFrames, men använder dessa typer av inbäddningar på ett bra sätt.</span><span class="sxs-lookup"><span data-stu-id="b911f-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="b911f-130">Isolerade webbdelar är ett rimligt undantag, men minimera deras nummer och placering i visningsområdet.</span><span class="sxs-lookup"><span data-stu-id="b911f-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="b911f-131">Om en iFrame är placerad utanför visningsområdet kan du använda en _IntersectionObserver_ för att fördröja rendering av iFrame tills den visas.</span><span class="sxs-lookup"><span data-stu-id="b911f-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="b911f-132">Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet.</span><span class="sxs-lookup"><span data-stu-id="b911f-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="b911f-133">Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.</span><span class="sxs-lookup"><span data-stu-id="b911f-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="b911f-135">Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor.</span><span class="sxs-lookup"><span data-stu-id="b911f-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="b911f-136">Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.</span><span class="sxs-lookup"><span data-stu-id="b911f-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b911f-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b911f-137">Related topics</span></span>

[<span data-ttu-id="b911f-138">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="b911f-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="b911f-139">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="b911f-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="b911f-140">Prestanda i det moderna SharePoint-programmet</span><span class="sxs-lookup"><span data-stu-id="b911f-140">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)