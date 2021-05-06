---
title: Sökstatistik i Advance eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Validera dina sökresultat genom att visa den statistik som skapas efter att du har kört en sökning i en Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161712"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="a56f7-103">Sökstatistik i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a56f7-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="a56f7-104">Ett sätt att verifiera sökresultaten är att titta på statistiken runt resultaten och se till att de stämmer överens med dina förväntningar.</span><span class="sxs-lookup"><span data-stu-id="a56f7-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="a56f7-105">När sökningen är klar visas statistik på hög nivå på den utfällbaserade sökinformationen:</span><span class="sxs-lookup"><span data-stu-id="a56f7-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="a56f7-106">Antal objekt och antal objekt som hämtats i sökningen</span><span class="sxs-lookup"><span data-stu-id="a56f7-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="a56f7-107">Antal och volym för delvis indexerade eller icke indexerade objekt som hittades på sökplatserna</span><span class="sxs-lookup"><span data-stu-id="a56f7-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="a56f7-108">Antalet postlådor och platser som sökts.</span><span class="sxs-lookup"><span data-stu-id="a56f7-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="a56f7-109">Om du vill se mer detaljerad statistik klickar du på "Statistik" i den utfällade menyn med sökdetaljer.</span><span class="sxs-lookup"><span data-stu-id="a56f7-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="a56f7-110">Sammanfattningsvy</span><span class="sxs-lookup"><span data-stu-id="a56f7-110">Summary view</span></span>

<span data-ttu-id="a56f7-111">I sammanfattningsvyn kan du se sökresultaten uppdelade efter platstyp (t.ex. Exchange).</span><span class="sxs-lookup"><span data-stu-id="a56f7-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="a56f7-112">För varje platstyp visas:</span><span class="sxs-lookup"><span data-stu-id="a56f7-112">For each location type, you can see:</span></span>

- <span data-ttu-id="a56f7-113">Antal platser som hade objekt som matchade sökvillkoren</span><span class="sxs-lookup"><span data-stu-id="a56f7-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="a56f7-114">Antal objekt från dessa platser som matchade sökvillkoren</span><span class="sxs-lookup"><span data-stu-id="a56f7-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="a56f7-115">Den totala mängden objekt som matchade sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="a56f7-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="a56f7-116">Vyn Populära platser</span><span class="sxs-lookup"><span data-stu-id="a56f7-116">Top locations view</span></span>

<span data-ttu-id="a56f7-117">I vyn Toppplatser ser du de enskilda platser som överensstämmer mest.</span><span class="sxs-lookup"><span data-stu-id="a56f7-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="a56f7-118">För varje plats visas:</span><span class="sxs-lookup"><span data-stu-id="a56f7-118">For each location, you will see:</span></span>

- <span data-ttu-id="a56f7-119">Platsnamn (t.ex. SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="a56f7-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="a56f7-120">Platstyp</span><span class="sxs-lookup"><span data-stu-id="a56f7-120">Location type</span></span>

- <span data-ttu-id="a56f7-121">Antal objekt som matchade sökvillkoren</span><span class="sxs-lookup"><span data-stu-id="a56f7-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="a56f7-122">Den totala mängden objekt som matchade sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="a56f7-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="a56f7-123">Frågevyn</span><span class="sxs-lookup"><span data-stu-id="a56f7-123">Queries view</span></span>

<span data-ttu-id="a56f7-124">Om du har använt (c:s) nyckelord eller nyckelordsrader i frågan kan du se detaljerad information om frågan i vyn Frågor per platstyp.</span><span class="sxs-lookup"><span data-stu-id="a56f7-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="a56f7-125">För varje platstyp visas:</span><span class="sxs-lookup"><span data-stu-id="a56f7-125">For each location type, you will see:</span></span>

- <span data-ttu-id="a56f7-126">Del: Den här kolumnen innehåller antingen ordet "Primär" eller "Nyckelord".</span><span class="sxs-lookup"><span data-stu-id="a56f7-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="a56f7-127">"Primär" innebär att raden presenterar statistik för hela frågan, medan "Nyckelord" betyder en av frågekomponenterna.</span><span class="sxs-lookup"><span data-stu-id="a56f7-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="a56f7-128">Fråga: den faktiska frågekomponenten raden refererar till.</span><span class="sxs-lookup"><span data-stu-id="a56f7-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="a56f7-129">Om del är "Primär" kommer detta att vara hela frågan. Om delen var "Nyckelord" visas en av frågekomponenterna här.</span><span class="sxs-lookup"><span data-stu-id="a56f7-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="a56f7-130">När du söker i allt innehåll i postlådor (genom att inte ange några nyckelord) är den faktiska frågan (storlek >= 0) så att alla objekt returneras</span><span class="sxs-lookup"><span data-stu-id="a56f7-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="a56f7-131">När du söker SharePoint Online OneDrive för företag webbplatser läggs de två följande komponenterna till:</span><span class="sxs-lookup"><span data-stu-id="a56f7-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="a56f7-132">NOT IsExternalContent:1 – undantar allt innehåll från en lokal SharePoint organisation</span><span class="sxs-lookup"><span data-stu-id="a56f7-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="a56f7-133">NOT isOneNotePage: 1 - undantar alla OneNote filer eftersom det skulle vara dubbletter av alla dokument som matchar sökfrågan.</span><span class="sxs-lookup"><span data-stu-id="a56f7-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="a56f7-134">Antal platser som hade objekt som matchade sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="a56f7-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="a56f7-135">Antalet objekt från dessa platser som matchade sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="a56f7-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="a56f7-136">Den totala mängden objekt som matchade sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="a56f7-136">Total volume of items that matched the search conditions.</span></span>
