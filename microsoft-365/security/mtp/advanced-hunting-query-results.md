---
title: Arbeta med avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Få ut det mesta av frågeresultaten som returneras genom avancerad jakt i Microsoft Threat Protection
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, detaljgranskning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929248"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="c5b9a-104">Arbeta med avancerade jaktfrågeresultat</span><span class="sxs-lookup"><span data-stu-id="c5b9a-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="c5b9a-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-105">**Applies to:**</span></span>
- <span data-ttu-id="c5b9a-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="c5b9a-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c5b9a-107">Även om du kan konstruera dina [avancerade jaktfrågor](advanced-hunting-overview.md) för att returnera mycket exakt information, kan du också arbeta med frågeresultaten för att få ytterligare insikt och undersöka specifika aktiviteter och indikatorer.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="c5b9a-108">Du kan vidta följande åtgärder för frågeresultaten:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="c5b9a-109">Visa resultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="c5b9a-109">View results as a table or chart</span></span>
- <span data-ttu-id="c5b9a-110">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="c5b9a-110">Export tables and charts</span></span>
- <span data-ttu-id="c5b9a-111">Öka detaljnivån till detaljerad information om entitet</span><span class="sxs-lookup"><span data-stu-id="c5b9a-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="c5b9a-112">Justera dina frågor direkt från resultaten eller tillämpa filter</span><span class="sxs-lookup"><span data-stu-id="c5b9a-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="c5b9a-113">Visa frågeresultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="c5b9a-113">View query results as a table or chart</span></span>
<span data-ttu-id="c5b9a-114">Som standard visar avancerad jakt frågeresultat som tabelldata.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="c5b9a-115">Du kan också visa samma data som ett diagram.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="c5b9a-116">Avancerad jakt stöder följande vyer:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="c5b9a-117">Visa typ</span><span class="sxs-lookup"><span data-stu-id="c5b9a-117">View type</span></span> | <span data-ttu-id="c5b9a-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c5b9a-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="c5b9a-119">**Tabell**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-119">**Table**</span></span> | <span data-ttu-id="c5b9a-120">Visar frågeresultatet i tabellformat</span><span class="sxs-lookup"><span data-stu-id="c5b9a-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="c5b9a-121">**Stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-121">**Column chart**</span></span> | <span data-ttu-id="c5b9a-122">Återger en serie unika objekt på x-axeln som lodräta staplar vars höjder representerar numeriska värden från ett annat fält</span><span class="sxs-lookup"><span data-stu-id="c5b9a-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="c5b9a-123">**Staplat stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-123">**Stacked column chart**</span></span> | <span data-ttu-id="c5b9a-124">Återger en serie unika objekt på x-axeln som staplade lodräta staplar vars höjder representerar numeriska värden från ett eller flera andra fält</span><span class="sxs-lookup"><span data-stu-id="c5b9a-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="c5b9a-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-125">**Pie chart**</span></span> | <span data-ttu-id="c5b9a-126">Återger avsnittspäror som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="c5b9a-127">Storleken på varje cirkel representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="c5b9a-128">**Donut diagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-128">**Donut chart**</span></span> | <span data-ttu-id="c5b9a-129">Återger avsnittsbågar som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="c5b9a-130">Längden på varje båge representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="c5b9a-131">**Linjediagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-131">**Line chart**</span></span> | <span data-ttu-id="c5b9a-132">Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="c5b9a-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="c5b9a-133">**Punktdiagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-133">**Scatter chart**</span></span> | <span data-ttu-id="c5b9a-134">Ritar numeriska värden för en serie unika objekt</span><span class="sxs-lookup"><span data-stu-id="c5b9a-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="c5b9a-135">**Områdesdiagram**</span><span class="sxs-lookup"><span data-stu-id="c5b9a-135">**Area chart**</span></span> | <span data-ttu-id="c5b9a-136">Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="c5b9a-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="c5b9a-137">Konstruera frågor för effektiva diagram</span><span class="sxs-lookup"><span data-stu-id="c5b9a-137">Construct queries for effective charts</span></span>
<span data-ttu-id="c5b9a-138">Vid rendering av diagram identifierar avancerad jakt automatiskt kolumner av intresse och de numeriska värdena som ska aggregeras.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="c5b9a-139">Skapa dina frågor för att returnera de specifika värden som du vill se visualiseras för att få meningsfulla diagram.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="c5b9a-140">Här är några exempelfrågor och de resulterande diagrammen.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="c5b9a-141">Varningar efter allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="c5b9a-141">Alerts by severity</span></span>
<span data-ttu-id="c5b9a-142">Använd `summarize` operatorn för att få ett numeriskt antal av de värden som du vill kartlägga.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="c5b9a-143">Frågan nedan använder `summarize` operatorn för att få antalet aviseringar efter allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="c5b9a-144">När resultaten återges visas varje allvarlighetsgrad i ett stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="c5b9a-145">![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-column-chart.jpg)
som visas som ett stapeldiagram*Frågeresultat för aviseringar efter allvarlighetsgrad som visas som ett stapeldiagram*</span><span class="sxs-lookup"><span data-stu-id="c5b9a-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="c5b9a-146">Allvarlighetsgrad för aviseringar efter operativsystem</span><span class="sxs-lookup"><span data-stu-id="c5b9a-146">Alert severity by operating system</span></span>
<span data-ttu-id="c5b9a-147">Du kan också `summarize` använda operatorn för att förbereda resultat för att kartlägga värden från flera fält.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="c5b9a-148">Du kanske till exempel vill förstå hur allvarlighetsgrader för aviseringar fördelas över operativsystem (OS).</span><span class="sxs-lookup"><span data-stu-id="c5b9a-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="c5b9a-149">Frågan nedan använder `join` en operator för att `DeviceInfo` hämta OS-information från tabellen och sedan används `summarize` för att räkna värden i både kolumnerna `OSPlatform` och `Severity` kolumnerna:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="c5b9a-150">Dessa resultat visualiseras bäst med hjälp av ett staplat stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="c5b9a-151">![Bild av avancerade jaktfrågeresultat som](../../media/advanced-hunting-stacked-chart.jpg)
visas som ett staplat diagram*Frågeresultat för aviseringar efter operativsystem och allvarlighetsgrad som visas som ett staplat diagram*</span><span class="sxs-lookup"><span data-stu-id="c5b9a-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="c5b9a-152">Nätfiskemeddelanden på de tio bästa avsändarna</span><span class="sxs-lookup"><span data-stu-id="c5b9a-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="c5b9a-153">Om du har att göra med en lista med värden som `Top` inte är begränsad kan du använda operatorn för att bara kartlägga de värden som har flest instanser.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="c5b9a-154">Om du till exempel vill hämta de tio bästa avsändarna med de mest nätfiskemeddelanden använder du frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="c5b9a-155">Använd cirkeldiagramvyn för att effektivt visa distributionen mellan de populäraste domänerna:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="c5b9a-156">![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-pie-chart.jpg)
som visas som ett*cirkeldiagram Cirkeldiagram som visar distribution av nätfiskemeddelanden över de vanligaste avsändande domänerna*</span><span class="sxs-lookup"><span data-stu-id="c5b9a-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="c5b9a-157">Filaktiviteter över tid</span><span class="sxs-lookup"><span data-stu-id="c5b9a-157">File activities over time</span></span>
<span data-ttu-id="c5b9a-158">Med `summarize` hjälp av `bin()` operatören med funktionen kan du söka efter händelser som involverar en viss indikator över tid.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="c5b9a-159">Frågan nedan räknar händelser `invoice.doc` som involverar filen med 30 minuters intervall för att visa toppar i aktivitet som är relaterade till filen:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="c5b9a-160">Linjediagrammet nedan belyser tydligt `invoice.doc`tidsperioder med mer aktivitet som omfattar:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="c5b9a-161">![Bild av avancerade jaktfrågeresultat](../../media/advanced-hunting-line-chart.jpg)
som visas som ett linjediagram*Linjediagram som visar antalet händelser som involverar en fil över tid*</span><span class="sxs-lookup"><span data-stu-id="c5b9a-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="c5b9a-162">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="c5b9a-162">Export tables and charts</span></span>
<span data-ttu-id="c5b9a-163">När du har kört en fråga väljer du **Exportera** för att spara resultaten i den lokala filen.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="c5b9a-164">Den valda vyn avgör hur resultaten exporteras:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="c5b9a-165">**Tabellvy** – frågeresultaten exporteras i tabellform som en Microsoft Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="c5b9a-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="c5b9a-166">**Alla diagram** – frågeresultaten exporteras som en JPEG-bild av det renderade diagrammet</span><span class="sxs-lookup"><span data-stu-id="c5b9a-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="c5b9a-167">Öka detaljnivån från frågeresultat</span><span class="sxs-lookup"><span data-stu-id="c5b9a-167">Drill down from query results</span></span>
<span data-ttu-id="c5b9a-168">Om du vill visa mer information om entiteter, till exempel datorer, filer, användare, IP-adresser och webbadresser, klickar du bara på entitetsidentifieraren i frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="c5b9a-169">Då öppnas en detaljerad profilsida för den valda entiteten i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="c5b9a-170">Justera dina frågor från resultaten</span><span class="sxs-lookup"><span data-stu-id="c5b9a-170">Tweak your queries from the results</span></span>
<span data-ttu-id="c5b9a-171">Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="c5b9a-172">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="c5b9a-172">You can use the options to:</span></span>

- <span data-ttu-id="c5b9a-173">Leta uttryckligen efter det`==`valda värdet ( )</span><span class="sxs-lookup"><span data-stu-id="c5b9a-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="c5b9a-174">Uteslut det valda värdet`!=`från frågan ( )</span><span class="sxs-lookup"><span data-stu-id="c5b9a-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="c5b9a-175">Få mer avancerade operatorer för att lägga `contains`till `starts with` värdet i frågan, till exempel`ends with`</span><span class="sxs-lookup"><span data-stu-id="c5b9a-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild på avancerad jaktresultatuppsättning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="c5b9a-177">Filtrera frågeresultaten</span><span class="sxs-lookup"><span data-stu-id="c5b9a-177">Filter the query results</span></span>
<span data-ttu-id="c5b9a-178">Filtren som visas till höger ger en sammanfattning av resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="c5b9a-179">Varje kolumn har ett eget avsnitt som visar de distinkta värden som hittats för den kolumnen och antalet instanser.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="c5b9a-180">Förfina frågan genom att `+` `-` markera knapparna eller på de värden som du vill inkludera eller utesluta och sedan välja **Kör fråga**.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild på avancerat jaktfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="c5b9a-182">När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="c5b9a-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5b9a-183">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c5b9a-183">Related topics</span></span>
- [<span data-ttu-id="c5b9a-184">Avancerad jaktöversikt</span><span class="sxs-lookup"><span data-stu-id="c5b9a-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5b9a-185">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c5b9a-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5b9a-186">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="c5b9a-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5b9a-187">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c5b9a-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c5b9a-188">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c5b9a-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5b9a-189">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c5b9a-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c5b9a-190">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="c5b9a-190">Custom detections overview</span></span>](custom-detections-overview.md)
