---
title: Optimera bilder i SharePoint sidor för moderna webbplatser online
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
description: Lär dig hur du använder verktygen i SharePoint Online för att optimera bilder på SharePoint moderna webbsidor online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923022"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="5bce1-103">Optimera bilder i SharePoint sidor för moderna webbplatser online</span><span class="sxs-lookup"><span data-stu-id="5bce1-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="5bce1-104">Den här artikeln hjälper dig att förstå hur du optimerar bilder i SharePoint sidor med modern webbplats online.</span><span class="sxs-lookup"><span data-stu-id="5bce1-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="5bce1-105">Information om hur du optimerar bilder i klassiska publiceringswebbplatser finns [i SharePoint Online.](image-optimization-for-sharepoint-online.md)</span><span class="sxs-lookup"><span data-stu-id="5bce1-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="5bce1-106">Mer information om prestanda i SharePoint moderna portaler finns i [Prestanda i det moderna SharePoint upplevelse.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="5bce1-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="5bce1-107">Använda siddiagnostik för det SharePoint verktyget för att analysera bildoptimering</span><span class="sxs-lookup"><span data-stu-id="5bce1-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="5bce1-108">Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="5bce1-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="5bce1-109">Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor.</span><span class="sxs-lookup"><span data-stu-id="5bce1-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="5bce1-110">Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="5bce1-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="5bce1-111">Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.</span><span class="sxs-lookup"><span data-stu-id="5bce1-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="5bce1-112">När du analyserar SharePoint webbplats med siddiagnostik för SharePoint kan du se information om stora bilder i _fönstret Diagnostiktest._</span><span class="sxs-lookup"><span data-stu-id="5bce1-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="5bce1-113">Möjliga resultat är:</span><span class="sxs-lookup"><span data-stu-id="5bce1-113">Possible results include:</span></span>

- <span data-ttu-id="5bce1-114">**Obs!** Obligatoriskt (rött): Sidan **innehåller en eller flera** bilder som är större än 300 KB</span><span class="sxs-lookup"><span data-stu-id="5bce1-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="5bce1-115">**Ingen åtgärd krävs** (grön): Sidan innehåller inga bilder större än 300 KB</span><span class="sxs-lookup"><span data-stu-id="5bce1-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="5bce1-116">Om det **upptäckta resultatet för stora** bilder visas **i** avsnittet Kräver uppmärksamhet i resultatet kan du klicka på resultatet för att visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="5bce1-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Resultat av verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="5bce1-118">Åtgärda stora bildproblem</span><span class="sxs-lookup"><span data-stu-id="5bce1-118">Remediate large image issues</span></span>

<span data-ttu-id="5bce1-119">Om en sida innehåller bilder större än 300 kB väljer du resultatet För stora bilder som upptäckts kan du se vilka bilder som är för stora. </span><span class="sxs-lookup"><span data-stu-id="5bce1-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="5bce1-120">På moderna SharePoint onlinesidor tillhandahålls återgivningar av bilder automatiskt och deras storlek beroende på storleken på webbläsarfönstret och klientskärmens upplösning.</span><span class="sxs-lookup"><span data-stu-id="5bce1-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="5bce1-121">Du bör alltid optimera bilder för webbanvändning innan du laddar upp till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5bce1-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="5bce1-122">Mycket stora bilder minskar automatiskt i storlek och upplösning, vilket kan resultera i oväntade renderingsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="5bce1-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="5bce1-123">Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet.</span><span class="sxs-lookup"><span data-stu-id="5bce1-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="5bce1-124">Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.</span><span class="sxs-lookup"><span data-stu-id="5bce1-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="5bce1-126">Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor.</span><span class="sxs-lookup"><span data-stu-id="5bce1-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="5bce1-127">Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.</span><span class="sxs-lookup"><span data-stu-id="5bce1-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5bce1-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5bce1-128">Related topics</span></span>

[<span data-ttu-id="5bce1-129">Justera SharePoint onlineprestanda</span><span class="sxs-lookup"><span data-stu-id="5bce1-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="5bce1-130">Justera Office 365 prestanda</span><span class="sxs-lookup"><span data-stu-id="5bce1-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="5bce1-131">Prestanda i den moderna SharePoint upplevelsen</span><span class="sxs-lookup"><span data-stu-id="5bce1-131">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="5bce1-132">Nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="5bce1-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="5bce1-133">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5bce1-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)