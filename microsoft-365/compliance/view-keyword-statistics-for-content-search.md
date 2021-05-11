---
title: Visa statistik för eDiscovery-sökresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Lär dig hur du använder funktionen sökstatistik för att visa statistik för innehållssökningar och sökningar som är kopplade till ett grundläggande eDiscovery-ärende i Microsoft 365 efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311154"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="d12e7-103">Visa statistik för eDiscovery-sökresultat</span><span class="sxs-lookup"><span data-stu-id="d12e7-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="d12e7-104">När du har skapat och kört en innehållssökning eller en sökning som är kopplad till ett basfall för e-dataidentifiering kan du visa statistik om de uppskattade sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="d12e7-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="d12e7-105">Den innehåller en sammanfattning av sökresultaten (ungefär som sammanfattningen av det uppskattade sökresultatet som visas på den utfällande sidan för sökning), frågestatistik som antalet innehållsplatser med objekt som matchar sökfrågan och identiteten på innehållsplatser som har de mest matchande objekten.</span><span class="sxs-lookup"><span data-stu-id="d12e7-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="d12e7-106">Dessutom kan du använda listan nyckelord för att konfigurera en sökning för att returnera statistik för varje nyckelord i en sökfråga.</span><span class="sxs-lookup"><span data-stu-id="d12e7-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="d12e7-107">På så sätt kan du jämföra antalet resultat som returneras av varje nyckelord i en fråga.</span><span class="sxs-lookup"><span data-stu-id="d12e7-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="d12e7-108">Du kan också ladda ned sökstatistik till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d12e7-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="d12e7-109">På så sätt kan du använda filtrerings- och sorteringsfunktionerna i Excel för att jämföra resultat och förbereda rapporter för sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="d12e7-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="d12e7-110">Hämta statistik för sökningar</span><span class="sxs-lookup"><span data-stu-id="d12e7-110">Get statistics for searches</span></span>

<span data-ttu-id="d12e7-111">Så här visar du statistik för en innehållssökning eller en sökning kopplad till ett Bas-eDiscovery-ärende.:</span><span class="sxs-lookup"><span data-stu-id="d12e7-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="d12e7-112">Klicka Microsoft 365 alla i **kompatibilitetscentret** och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="d12e7-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="d12e7-113">Klicka **på Innehållssökning** och välj sedan en sökning för att visa den utfällade sidan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="d12e7-114">ELLER</span><span class="sxs-lookup"><span data-stu-id="d12e7-114">OR</span></span>

   - <span data-ttu-id="d12e7-115">Klicka **på Bas för e-dataidentifiering,** markera ett ärende och välj sedan en sökning på fliken Sökningar för att visa den  >  utfällande sidan. </span><span class="sxs-lookup"><span data-stu-id="d12e7-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="d12e7-116">Klicka på fliken Sökstatistik på den utfällade sidan av **den markerade** sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Fliken Sökstatistik](../media/SearchStatistics1.png)

<span data-ttu-id="d12e7-118">Fliken **Sökstatistik** innehåller följande avsnitt som innehåller olika typer av statistik om sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="d12e7-119">Söka efter innehåll</span><span class="sxs-lookup"><span data-stu-id="d12e7-119">Search content</span></span>

<span data-ttu-id="d12e7-120">I det här avsnittet visas en grafisk sammanfattning av de uppskattade objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="d12e7-121">Här visas antalet objekt som matchar sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="d12e7-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="d12e7-122">Den här informationen ger dig en uppfattning om det uppskattade antalet objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Sökberäkningar för en sökning](../media/SearchContentReport.png)

- <span data-ttu-id="d12e7-124">**Uppskattade objekt efter platser:** Det totala antalet uppskattade objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="d12e7-125">Det specifika antalet objekt i postlådor och på webbplatser visas också.</span><span class="sxs-lookup"><span data-stu-id="d12e7-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="d12e7-126">**Uppskattade platser med träffar:** Det totala antalet innehållsplatser som innehåller objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="d12e7-127">Det specifika antalet postlådor och webbplatser visas också.</span><span class="sxs-lookup"><span data-stu-id="d12e7-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="d12e7-128">**Datavolym per plats (i MB)**: Total storlek för alla uppskattade objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="d12e7-129">Den specifika storleken på postlådeobjekt och webbplatsobjekt visas också.</span><span class="sxs-lookup"><span data-stu-id="d12e7-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="d12e7-130">Villkorsrapport</span><span class="sxs-lookup"><span data-stu-id="d12e7-130">Condition report</span></span>

<span data-ttu-id="d12e7-131">I det här avsnittet visas statistik om sökfrågan och antalet uppskattade objekt som matchade olika delar av sökfrågan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="d12e7-132">Du kan använda statistiken för att analysera antalet objekt som matchar varje komponent i sökfrågan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="d12e7-133">Det kan hjälpa dig att förfina sökvillkoren och vid behov begränsa omfattningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="d12e7-134">Du kan också ladda ned en kopia av rapporten i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="d12e7-134">You can also download a copy of this report in CSV format.</span></span>

![Villkorsrapport](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="d12e7-136">**Platstyp:** Den typ av innehållsplats som frågestatistiken gäller för.</span><span class="sxs-lookup"><span data-stu-id="d12e7-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="d12e7-137">Värdet för en **Exchange** anger en postlådas plats. Värdet för en **SharePoint** anger en webbplatsplats.</span><span class="sxs-lookup"><span data-stu-id="d12e7-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="d12e7-138">**Del**: Den del av sökfrågan som statistiken gäller för.</span><span class="sxs-lookup"><span data-stu-id="d12e7-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="d12e7-139">**Primär** anger hela sökfrågan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="d12e7-140">**Nyckelord** anger att statistiken på raden är för ett visst nyckelord.</span><span class="sxs-lookup"><span data-stu-id="d12e7-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="d12e7-141">Om du använder en nyckelordslista för sökfråga inkluderas statistik för varje komponent i frågan i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="d12e7-142">Mer information finns i Hämta [nyckelordsstatistik för sökningar](#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="d12e7-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="d12e7-143">**Villkor:** Den faktiska komponenten (nyckelord eller villkor) i sökfrågan som returnerar den statistik som visas på motsvarande rad.</span><span class="sxs-lookup"><span data-stu-id="d12e7-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="d12e7-144">**Platser med träffar:** Antalet innehållsplatser (anges av  kolumnen Platstyp) som innehåller objekt som matchar den primära frågan eller nyckelordsfrågan som visas i **kolumnen** Villkor.</span><span class="sxs-lookup"><span data-stu-id="d12e7-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="d12e7-145">**Objekt:** Det antal objekt (från den angivna innehållsplatsen) som matchar frågan som visas i **kolumnen** Villkor.</span><span class="sxs-lookup"><span data-stu-id="d12e7-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="d12e7-146">Som tidigare förklarats räknas ett objekt bara en gång i den här kolumnen om det innehåller flera förekomster av ett nyckelord som söks igenom.</span><span class="sxs-lookup"><span data-stu-id="d12e7-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="d12e7-147">**Storlek (MB)**: Den totala storleken på alla objekt som hittades (på den angivna innehållsplatsen) som matchar sökfrågan i **kolumnen** Villkor.</span><span class="sxs-lookup"><span data-stu-id="d12e7-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="d12e7-148">Mest populära platserna</span><span class="sxs-lookup"><span data-stu-id="d12e7-148">Top locations</span></span>

<span data-ttu-id="d12e7-149">I det här avsnittet visas statistik för specifika innehållsplatser med de flesta objekt som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="d12e7-150">De 1 000 översta platserna visas.</span><span class="sxs-lookup"><span data-stu-id="d12e7-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="d12e7-151">Du kan också ladda ned en kopia av rapporten i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="d12e7-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="d12e7-152">Namnet på platsnamnet (postlådors e-postadress och webbplatsadressen).</span><span class="sxs-lookup"><span data-stu-id="d12e7-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="d12e7-153">Platstyp (en postlåda eller webbplats).</span><span class="sxs-lookup"><span data-stu-id="d12e7-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="d12e7-154">Beräknat antal objekt på innehållsplatsen som returneras av sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="d12e7-155">Den totala storleken på uppskattade objekt på varje innehållsplats.</span><span class="sxs-lookup"><span data-stu-id="d12e7-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="d12e7-156">Hämta nyckelordsstatistik för sökningar</span><span class="sxs-lookup"><span data-stu-id="d12e7-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="d12e7-157">Som tidigare förklarats **visar villkorsrapporten** sökfrågan och antalet (och storleken) objekt som matchar frågan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="d12e7-158">Om du använder en nyckelordslista när du skapar eller redigerar en sökfråga kan du få utökad statistik som visar hur många objekt som matchar varje nyckelord eller nyckelordsfras.</span><span class="sxs-lookup"><span data-stu-id="d12e7-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="d12e7-159">Det kan hjälpa dig att snabbt identifiera vilka delar av frågan som är mest (och minst) effektiva.</span><span class="sxs-lookup"><span data-stu-id="d12e7-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="d12e7-160">Om ett nyckelord till exempel returnerar ett stort antal objekt kan du välja att förfina nyckelordsfrågan för att begränsa sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="d12e7-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="d12e7-161">Så här skapar du en nyckelordslista och visar nyckelordsstatistik för en sökning:</span><span class="sxs-lookup"><span data-stu-id="d12e7-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="d12e7-162">Skapa en Microsoft 365 innehållssökning eller en sökning kopplad till ett Core eDiscovery-ärende i säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="d12e7-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="d12e7-163">På **sidan** Villkor i sökguiden.</span><span class="sxs-lookup"><span data-stu-id="d12e7-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="d12e7-164">markera **kryssrutan Visa** nyckelordslista.</span><span class="sxs-lookup"><span data-stu-id="d12e7-164">select the **Show keyword list** checkbox.</span></span>

   ![Kryssrutan Visa lista över nyckelord](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="d12e7-166">Skriv ett nyckelord eller en nyckelordsfas på en rad i tabellen nyckelord.</span><span class="sxs-lookup"><span data-stu-id="d12e7-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="d12e7-167">Skriv till exempel **budget på** den  första raden, ange säkerhet på den andra raden och **skriv RÅ2021** på den tredje raden.</span><span class="sxs-lookup"><span data-stu-id="d12e7-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Skriv upp till 20 nyckelord eller nyckelordsfraser i listan](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="d12e7-169">För att minska problemen som orsakas av stora nyckelordslistor är du begränsad till högst 20 rader i nyckelordslistan för en sökfråga.</span><span class="sxs-lookup"><span data-stu-id="d12e7-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="d12e7-170">Kör sökningen när du har lagt till nyckelorden i listan som du vill söka efter och hämta statistik för.</span><span class="sxs-lookup"><span data-stu-id="d12e7-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="d12e7-171">När sökningen är klar väljer du den för att visa den utfällklara sidan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="d12e7-172">Klicka på **villkorsrapporten** på fliken **Sökstatistik om** du vill visa nyckelordsstatistik för sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![Statistiken för varje nyckelord visas](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="d12e7-174">Som du ser i föregående skärmbild visas statistiken för varje nyckelord. detta omfattar:</span><span class="sxs-lookup"><span data-stu-id="d12e7-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="d12e7-175">Nyckelordsstatistik för varje typ av innehållsplats som ingår i sökningen.</span><span class="sxs-lookup"><span data-stu-id="d12e7-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="d12e7-176">Antalet icke indexerade postlådeobjekt.</span><span class="sxs-lookup"><span data-stu-id="d12e7-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="d12e7-177">Den faktiska sökfrågan och resultaten för varje  nyckelord (identifieras som **Nyckelord** i kolumnen Del), som innehåller eventuella villkor från sökfrågan.</span><span class="sxs-lookup"><span data-stu-id="d12e7-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="d12e7-178">Den fullständiga sökfrågan (identifieras **som primär** i **kolumnen** Del) och statistik för hela frågan för varje platstyp.</span><span class="sxs-lookup"><span data-stu-id="d12e7-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="d12e7-179">Observera att detta är samma statistik som visas på **fliken** Sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="d12e7-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
