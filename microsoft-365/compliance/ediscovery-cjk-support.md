---
title: Stöd för CJK/Double Byte för Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig Advanced eDiscovery tecken Microsoft 365 kinesiska, japanska och koreanska (CJK) som använder teckenuppsättning med dubbla byte.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162234"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="6725d-103">CJK-språkstöd för Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6725d-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="6725d-104">Advanced eDiscovery har stöd för språk med teckenuppsättning med dubbla byte (till exempel förenklad kinesiska, traditionell kinesiska, japanska och koreanska som gemensamt kallas *CJK-språk)* för följande avancerade scenarier i en granskningsuppsättning:</span><span class="sxs-lookup"><span data-stu-id="6725d-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="6725d-105">När du [ställer frågor mot data i en granskningsuppsättning](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="6725d-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="6725d-106">När du [taggar dokument i en granskningsuppsättning](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="6725d-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="6725d-107">När du [analyserar ärendedata i en granskningsuppsättning med](analyzing-data-in-review-set.md) nästan dubblettidentifiering, e-posttrådning och teman.</span><span class="sxs-lookup"><span data-stu-id="6725d-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6725d-108">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="6725d-108">Frequently asked questions</span></span>

<span data-ttu-id="6725d-109">**Hur skapar jag en sökning för att samla objekt som innehåller CJK-tecken?**</span><span class="sxs-lookup"><span data-stu-id="6725d-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="6725d-110">Du kan använda CJK-tecken [för](building-search-queries.md#keyword-searches) [nyckelordssökningar, nyckelordsfrågor](keyword-queries-and-search-conditions.md) och sökvillkor när du söker efter innehåll i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6725d-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="6725d-111">Det går även att söka efter CJK-tecken när du söker efter innehåll i Core eDiscovery och Content Search.</span><span class="sxs-lookup"><span data-stu-id="6725d-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="6725d-112">Vi har stöd för CJK [för](keyword-queries-and-search-conditions.md#search-operators) alla sökoperatorer och sökvillkor, [](keyword-queries-and-search-conditions.md#search-conditions)inklusive booleska operatorer **OCH,** **ELLER,** **NOT** och **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="6725d-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="6725d-113">Om du är säker på att innehållsplatser eller objekt innehåller CJK-tecken men sökningar inte returnerar några resultat klickar du på ikonen för frågans språk/land/region</span><span class="sxs-lookup"><span data-stu-id="6725d-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Ikonen för språk/region för fråga i innehållssökning](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="6725d-115">och välj motsvarande språk-land-kulturkodvärde för sökningen.</span><span class="sxs-lookup"><span data-stu-id="6725d-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="6725d-116">Standardalternativet för språk/region är neutralt.</span><span class="sxs-lookup"><span data-stu-id="6725d-116">The default language/region is neutral.</span></span>

<span data-ttu-id="6725d-117">**Kan jag söka efter flera språk samtidigt?**</span><span class="sxs-lookup"><span data-stu-id="6725d-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="6725d-118">Det beror på sökscenariot.</span><span class="sxs-lookup"><span data-stu-id="6725d-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="6725d-119">När du [avfrågar data i en granskningsuppsättning](review-set-search.md) Advanced eDiscovery kan du söka efter flera språk.</span><span class="sxs-lookup"><span data-stu-id="6725d-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="6725d-120">När du [skapar en sökning för att samla in data](create-search-to-collect-data.md)skapar du en separat sökning för varje språk du riktar.</span><span class="sxs-lookup"><span data-stu-id="6725d-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="6725d-121">Om du till exempel söker efter ett dokument som innehåller både kinesiska och koreanska väljer du Kinesiska för din första fråga och sedan Koreanska för din andra fråga.</span><span class="sxs-lookup"><span data-stu-id="6725d-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="6725d-122">**Jag ser inte ikonen för att välja språk/region för frågan för att välja ett språk för frågor i en granskningsuppsättning. Hur anger jag ett frågespråk i en granskningsuppsättningssökning?**</span><span class="sxs-lookup"><span data-stu-id="6725d-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="6725d-123">För frågor i en granskningsuppsättning behöver du inte ange ett dokumentspråk.</span><span class="sxs-lookup"><span data-stu-id="6725d-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="6725d-124">Advanced eDiscovery automatiskt identifierar dokumentspråk när du lägger till innehåll i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="6725d-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="6725d-125">Det hjälper dig att optimera frågeresultatet i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="6725d-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="6725d-126">**Kan jag se identifierade språk i [filmetadata?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="6725d-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="6725d-127">Nej, du kan inte se identifierade språk i filmetadata.</span><span class="sxs-lookup"><span data-stu-id="6725d-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="6725d-128">**Kan jag filtrera efter dokumentspråk i en granskningsuppsättning?**</span><span class="sxs-lookup"><span data-stu-id="6725d-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="6725d-129">Nej, du kan inte filtrera, sortera eller söka efter dokumentspråk i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="6725d-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="6725d-130">**Påverkar den här CJK-versionen för granskningsscenarier några av mina befintliga sökningar och granskningsuppsättningar?**</span><span class="sxs-lookup"><span data-stu-id="6725d-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="6725d-131">Nej, inga av dina befintliga sökningar eller granskningsuppsättningar kommer att ändras.</span><span class="sxs-lookup"><span data-stu-id="6725d-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="6725d-132">Du behöver inte indexera om befintliga data, och sökresultaten för text på engelska är desamma.</span><span class="sxs-lookup"><span data-stu-id="6725d-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="6725d-133">**Hur ändrar jag visningsspråket till kinesiska, japanska eller koreanska?**</span><span class="sxs-lookup"><span data-stu-id="6725d-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="6725d-134">Mer information om hur du ändrar visningsspråk och tidszon finns i Så här anger du språk- och [regionsinställningar för Office 365.](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="6725d-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="6725d-135">Kända problem</span><span class="sxs-lookup"><span data-stu-id="6725d-135">Known issues</span></span>

- <span data-ttu-id="6725d-136">OCR stöder inte CJK-tecken från bildfiler</span><span class="sxs-lookup"><span data-stu-id="6725d-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="6725d-137">E-postfiler (till exempel \*.eml och [](view-documents-in-review-set.md#annotate-view) \*.msg) i vyn Anteckningar stöds inte för CJK-språk.</span><span class="sxs-lookup"><span data-stu-id="6725d-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="6725d-138">Sökningsmarkering i [textvyn](view-documents-in-review-set.md#text-view) stöds inte för CJK-språk.</span><span class="sxs-lookup"><span data-stu-id="6725d-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="6725d-139">Den [relevansmodul](using-relevance.md) som används för att analysera data stöder inte CJK-språk.</span><span class="sxs-lookup"><span data-stu-id="6725d-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="6725d-140">[Frågebaserade spärrade](managing-holds.md#manage-non-custodial-holds) frågor stöds inte för CJK-språk.</span><span class="sxs-lookup"><span data-stu-id="6725d-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>