---
title: Optimera bilder i SharePoint Online-sidor med moderna webbplatser
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
description: Lär dig hur du använder verktygen i SharePoint Online för att optimera bilder i SharePoint Online-moderna webbplats sidor.
ms.openlocfilehash: 09122dfd0bc832cf9a09cfb05bf0540e323797d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694810"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="f88be-103">Optimera bilder i SharePoint Online-sidor med moderna webbplatser</span><span class="sxs-lookup"><span data-stu-id="f88be-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="f88be-104">Den här artikeln hjälper dig att förstå hur du optimerar bilder i SharePoint Online-moderna webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="f88be-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="f88be-105">Information om hur du optimerar bilder i klassiska publicerings webbplatser finns i [bild optimering för SharePoint Online](image-optimization-for-sharepoint-online.md)..</span><span class="sxs-lookup"><span data-stu-id="f88be-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="f88be-106">Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="f88be-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="f88be-107">Använd verktyget för nätverksdiagnostik för SharePoint för att analysera bild optimering</span><span class="sxs-lookup"><span data-stu-id="f88be-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="f88be-108">Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="f88be-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="f88be-109">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="f88be-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="f88be-110">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="f88be-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="f88be-111">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="f88be-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="f88be-112">När du analyserar en modern SharePoint-webbplats med verktyget för SharePoint-diagnostik kan du se information om stora bilder i fönstret _diagnos test_ .</span><span class="sxs-lookup"><span data-stu-id="f88be-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="f88be-113">Möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="f88be-113">Possible results include:</span></span>

- <span data-ttu-id="f88be-114">**Åtgärd krävs** (röd): Sidan innehåller **en eller flera** bilder över 300KB storlek</span><span class="sxs-lookup"><span data-stu-id="f88be-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="f88be-115">**Ingen åtgärd krävs** (grön): Sidan innehåller inga bilder över 300KB storlek</span><span class="sxs-lookup"><span data-stu-id="f88be-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="f88be-116">Om resultatet som **identifieras** visas i det **underskrivna underavsnittet** i resultatet kan du klicka på resultatet för att visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="f88be-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Resultat för verktyget Nätverksdiagnostik](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="f88be-118">Åtgärda stora problem med bilden</span><span class="sxs-lookup"><span data-stu-id="f88be-118">Remediate large image issues</span></span>

<span data-ttu-id="f88be-119">Om en sida innehåller bilder över 300KB väljer du de **stora bilderna som identifieras** och visar vilka bilder som är för stora.</span><span class="sxs-lookup"><span data-stu-id="f88be-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="f88be-120">På moderna SharePoint Online-sidor visas åter givningar av bilder automatiskt och storlek beroende på webbläsarens fönster och upplösningen för klient övervakaren.</span><span class="sxs-lookup"><span data-stu-id="f88be-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="f88be-121">Du bör alltid optimera bilder för webb användning innan du laddar upp till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f88be-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="f88be-122">Mycket stora bilder kommer automatiskt att minskas till storlek och upplösning, vilket kan leda till oväntade åter givnings egenskaper.</span><span class="sxs-lookup"><span data-stu-id="f88be-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="f88be-123">Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten.</span><span class="sxs-lookup"><span data-stu-id="f88be-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="f88be-124">Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.</span><span class="sxs-lookup"><span data-stu-id="f88be-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="f88be-126">Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden.</span><span class="sxs-lookup"><span data-stu-id="f88be-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="f88be-127">Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.</span><span class="sxs-lookup"><span data-stu-id="f88be-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f88be-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f88be-128">Related topics</span></span>

[<span data-ttu-id="f88be-129">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="f88be-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="f88be-130">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="f88be-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="f88be-131">Prestanda i den moderna SharePoint-upplevelsen</span><span class="sxs-lookup"><span data-stu-id="f88be-131">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="f88be-132">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="f88be-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="f88be-133">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f88be-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
