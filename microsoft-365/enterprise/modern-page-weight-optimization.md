---
title: Optimera sid vikt i SharePoint moderna webbplatssidor online
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
description: Lär dig hur du använder verktyget Siddiagnostik för att optimera sidvikten på SharePoint sidor för moderna webbplatser online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907450"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="fcfa5-103">Optimera sid vikt i SharePoint moderna webbplatssidor online</span><span class="sxs-lookup"><span data-stu-id="fcfa5-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="fcfa5-104">SharePoint Moderna webbplatssidor online innehåller serialiserad kod som krävs för att återge sidans innehåll, inklusive bilder, text, objekt i innehållsområdet under navigerings-/kommandofält och annan HTML-kod som utgör sidans ramverk.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="fcfa5-105">Sidvikt är ett mått på den här HTML-koden och bör vara begränsat för optimala inläsningstider för sidor.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="fcfa5-106">Den här artikeln hjälper dig att förstå hur du minskar sidvikten på moderna webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="fcfa5-107">Mer information om prestanda i SharePoint moderna portaler finns i [Prestanda i det moderna SharePoint upplevelse.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="fcfa5-108">Använda siddiagnostik för det SharePoint verktyget för att analysera sidvikt</span><span class="sxs-lookup"><span data-stu-id="fcfa5-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="fcfa5-109">Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="fcfa5-110">Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="fcfa5-111">Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="fcfa5-112">Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="fcfa5-113">När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint visas information om sidan i **sidvikten under 500 kB** i fönstret _Diagnostiktest._</span><span class="sxs-lookup"><span data-stu-id="fcfa5-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="fcfa5-114">Resultatet visas i grönt om sidvikten är under baslinjevärdet och röd om sidvikten överskrider baslinjevärdet.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="fcfa5-115">Möjliga resultat är:</span><span class="sxs-lookup"><span data-stu-id="fcfa5-115">Possible results include:</span></span>

- <span data-ttu-id="fcfa5-116">**Obs!** Krävs (rött): Sid vikt överskrider 500 KB</span><span class="sxs-lookup"><span data-stu-id="fcfa5-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="fcfa5-117">**Ingen åtgärd krävs** (grön): Sidvikt är under 500 KB</span><span class="sxs-lookup"><span data-stu-id="fcfa5-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="fcfa5-118">Om **Sidvikt under 500 kB visas** i avsnittet Åtgärder **krävs** kan du klicka på resultatet för mer information.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Förfrågningar om SharePoint resultat](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="fcfa5-120">Åtgärda problem med sidvikt</span><span class="sxs-lookup"><span data-stu-id="fcfa5-120">Remediate page weight issues</span></span>

<span data-ttu-id="fcfa5-121">Om sidvikten överskrider 500 KB kan du förbättra inläsningstiden för den övergripande sidan genom att minska antalet webbdelar och begränsa sidinnehållet till lämplig grad.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="fcfa5-122">Allmän vägledning för att minska sidvikten omfattar:</span><span class="sxs-lookup"><span data-stu-id="fcfa5-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="fcfa5-123">Begränsa sidinnehållet till ett rimligt belopp och använd flera sidor för relaterat innehåll.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="fcfa5-124">Minimera användningen av webbdelar som har stora egenskapsskatter.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="fcfa5-125">Använd icke-interaktiva uppslagsvyer när det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="fcfa5-126">Optimera bildstorlekar genom att ändra storlek på bilderna på rätt sätt, med komprimerade bildformat och se till att de laddas ned från en CDN.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="fcfa5-127">Ytterligare anvisningar om hur du begränsar sidvikten finns i följande artikel:</span><span class="sxs-lookup"><span data-stu-id="fcfa5-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="fcfa5-128">Optimera sidprestanda i SharePoint</span><span class="sxs-lookup"><span data-stu-id="fcfa5-128">Optimize page performance in SharePoint</span></span>](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="fcfa5-129">Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="fcfa5-130">Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="fcfa5-132">Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="fcfa5-133">Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcfa5-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fcfa5-134">Related topics</span></span>

[<span data-ttu-id="fcfa5-135">Justera SharePoint onlineprestanda</span><span class="sxs-lookup"><span data-stu-id="fcfa5-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="fcfa5-136">Justera Office 365 prestanda</span><span class="sxs-lookup"><span data-stu-id="fcfa5-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="fcfa5-137">Prestanda i den moderna SharePoint upplevelsen</span><span class="sxs-lookup"><span data-stu-id="fcfa5-137">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="fcfa5-138">Nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="fcfa5-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="fcfa5-139">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fcfa5-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)