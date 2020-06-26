---
title: Arbeta med avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Få ut det mesta av frågeresultaten som returneras av avancerad jakt i Microsoft Threat Protection
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, drill-down
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
ms.openlocfilehash: 14afd3c098c99a6e1e6ccfc7e9f6accbf8bf0e7d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899092"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="db066-104">Arbeta med avancerade jaktfrågeresultat</span><span class="sxs-lookup"><span data-stu-id="db066-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="db066-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="db066-105">**Applies to:**</span></span>
- <span data-ttu-id="db066-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="db066-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="db066-107">Även om du kan konstruera dina [avancerade jaktfrågor](advanced-hunting-overview.md) för att returnera mycket exakt information, kan du också arbeta med frågeresultaten för att få ytterligare insikt och undersöka specifika aktiviteter och indikatorer.</span><span class="sxs-lookup"><span data-stu-id="db066-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="db066-108">Du kan vidta följande åtgärder för frågeresultaten:</span><span class="sxs-lookup"><span data-stu-id="db066-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="db066-109">Visa resultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="db066-109">View results as a table or chart</span></span>
- <span data-ttu-id="db066-110">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="db066-110">Export tables and charts</span></span>
- <span data-ttu-id="db066-111">Öka detaljnivån till detaljerad information om entitet</span><span class="sxs-lookup"><span data-stu-id="db066-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="db066-112">Justera dina frågor direkt från resultaten eller tillämpa filter</span><span class="sxs-lookup"><span data-stu-id="db066-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="db066-113">Visa frågeresultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="db066-113">View query results as a table or chart</span></span>
<span data-ttu-id="db066-114">Som standard visar avancerad jakt frågeresultat som tabelldata.</span><span class="sxs-lookup"><span data-stu-id="db066-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="db066-115">Du kan också visa samma data som ett diagram.</span><span class="sxs-lookup"><span data-stu-id="db066-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="db066-116">Avancerad jakt stöder följande vyer:</span><span class="sxs-lookup"><span data-stu-id="db066-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="db066-117">Visa typ</span><span class="sxs-lookup"><span data-stu-id="db066-117">View type</span></span> | <span data-ttu-id="db066-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="db066-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="db066-119">**Tabell**</span><span class="sxs-lookup"><span data-stu-id="db066-119">**Table**</span></span> | <span data-ttu-id="db066-120">Visar frågeresultatet i tabellformat</span><span class="sxs-lookup"><span data-stu-id="db066-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="db066-121">**Stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="db066-121">**Column chart**</span></span> | <span data-ttu-id="db066-122">Återger en serie unika objekt på x-axeln som lodräta staplar vars höjder representerar numeriska värden från ett annat fält</span><span class="sxs-lookup"><span data-stu-id="db066-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="db066-123">**Staplat stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="db066-123">**Stacked column chart**</span></span> | <span data-ttu-id="db066-124">Återger en serie unika objekt på x-axeln som staplade lodräta staplar vars höjder representerar numeriska värden från ett eller flera andra fält</span><span class="sxs-lookup"><span data-stu-id="db066-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="db066-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="db066-125">**Pie chart**</span></span> | <span data-ttu-id="db066-126">Återger avsnittspajer som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="db066-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="db066-127">Storleken på varje cirkel representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="db066-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="db066-128">**Donut diagram**</span><span class="sxs-lookup"><span data-stu-id="db066-128">**Donut chart**</span></span> | <span data-ttu-id="db066-129">Återger sektionsbågar som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="db066-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="db066-130">Längden på varje båge representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="db066-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="db066-131">**Linjediagram**</span><span class="sxs-lookup"><span data-stu-id="db066-131">**Line chart**</span></span> | <span data-ttu-id="db066-132">Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="db066-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="db066-133">**Punktdiagram**</span><span class="sxs-lookup"><span data-stu-id="db066-133">**Scatter chart**</span></span> | <span data-ttu-id="db066-134">Ritar numeriska värden för en serie unika objekt</span><span class="sxs-lookup"><span data-stu-id="db066-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="db066-135">**Områdesdiagram**</span><span class="sxs-lookup"><span data-stu-id="db066-135">**Area chart**</span></span> | <span data-ttu-id="db066-136">Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="db066-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="db066-137">Konstruera frågor för effektiva diagram</span><span class="sxs-lookup"><span data-stu-id="db066-137">Construct queries for effective charts</span></span>
<span data-ttu-id="db066-138">Vid rendering av diagram identifierar avancerad jakt automatiskt kolumner av intresse och de numeriska värdena som ska sammanställas.</span><span class="sxs-lookup"><span data-stu-id="db066-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="db066-139">Skapa dina frågor för att returnera de specifika värden som du vill se visualiseras för att få meningsfulla diagram.</span><span class="sxs-lookup"><span data-stu-id="db066-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="db066-140">Här är några exempelfrågor och de resulterande diagrammen.</span><span class="sxs-lookup"><span data-stu-id="db066-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="db066-141">Aviseringar efter allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="db066-141">Alerts by severity</span></span>
<span data-ttu-id="db066-142">Använd `summarize` operatorn för att få ett numeriskt antal av de värden som du vill kartlägga.</span><span class="sxs-lookup"><span data-stu-id="db066-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="db066-143">Frågan nedan använder `summarize` operatorn för att få antalet aviseringar efter allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="db066-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="db066-144">När resultaten återges visas varje allvarlighetsgrad i ett stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="db066-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="db066-145">![Bild av avancerade jaktfrågeresultat som visas som ett stapeldiagram ](../../media/advanced-hunting-column-chart.jpg)
 *Frågeresultat för aviseringar efter allvarlighetsgrad som visas som ett stapeldiagram*</span><span class="sxs-lookup"><span data-stu-id="db066-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="db066-146">Allvarlighetsgrad för aviseringar efter operativsystem</span><span class="sxs-lookup"><span data-stu-id="db066-146">Alert severity by operating system</span></span>
<span data-ttu-id="db066-147">Du kan också använda `summarize` operatorn för att förbereda resultat för att kartlägga värden från flera fält.</span><span class="sxs-lookup"><span data-stu-id="db066-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="db066-148">Du kanske till exempel vill förstå hur allvarlighetsgrader för aviseringar fördelas över operativsystem (OS).</span><span class="sxs-lookup"><span data-stu-id="db066-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="db066-149">Frågan nedan använder en `join` operator för att hämta OS-information från tabellen och sedan används för att räkna värden i både `DeviceInfo` `summarize` `OSPlatform` kolumnerna och `Severity` kolumnerna:</span><span class="sxs-lookup"><span data-stu-id="db066-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="db066-150">Dessa resultat visualiseras bäst med hjälp av ett staplat stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="db066-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="db066-151">![Bild av avancerade jaktfrågeresultat som visas som ett staplat diagram ](../../media/advanced-hunting-stacked-chart.jpg)
 *Frågeresultat för aviseringar efter operativsystem och allvarlighetsgrad som visas som ett staplat diagram*</span><span class="sxs-lookup"><span data-stu-id="db066-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="db066-152">Nätfiskemeddelanden på de tio bästa avsändarna</span><span class="sxs-lookup"><span data-stu-id="db066-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="db066-153">Om du har att göra med en lista med värden som inte är begränsad kan du använda `Top` operatorn för att bara kartlägga de värden som har flest instanser.</span><span class="sxs-lookup"><span data-stu-id="db066-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="db066-154">Om du till exempel vill få de tio bästa avsändarna med de mest nätfiskemeddelanden använder du frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="db066-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="db066-155">Använd cirkeldiagramvyn för att effektivt visa distributionen mellan de populäraste domänerna:</span><span class="sxs-lookup"><span data-stu-id="db066-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="db066-156">![Bild av avancerade jaktfrågeresultat som visas som ett cirkeldiagram ](../../media/advanced-hunting-pie-chart.jpg)
 *Cirkeldiagram som visar distribution av nätfiskemeddelanden mellan de vanligaste avsändande domänerna*</span><span class="sxs-lookup"><span data-stu-id="db066-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="db066-157">Filaktiviteter över tid</span><span class="sxs-lookup"><span data-stu-id="db066-157">File activities over time</span></span>
<span data-ttu-id="db066-158">Med hjälp av `summarize` operatören med funktionen kan du söka efter händelser som `bin()` involverar en viss indikator över tid.</span><span class="sxs-lookup"><span data-stu-id="db066-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="db066-159">Frågan nedan räknar händelser som involverar filen `invoice.doc` med 30 minuters intervall för att visa toppar i aktivitet som är relaterade till filen:</span><span class="sxs-lookup"><span data-stu-id="db066-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="db066-160">Linjediagrammet nedan belyser tydligt tidsperioder med mer aktivitet som `invoice.doc` omfattar:</span><span class="sxs-lookup"><span data-stu-id="db066-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="db066-161">![Bild av avancerade jaktfrågeresultat som visas som ett linjediagram ](../../media/advanced-hunting-line-chart.jpg)
 *Linjediagram som visar antalet händelser som involverar en fil över tid*</span><span class="sxs-lookup"><span data-stu-id="db066-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="db066-162">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="db066-162">Export tables and charts</span></span>
<span data-ttu-id="db066-163">När du har kört en fråga väljer du **Exportera** för att spara resultaten i den lokala filen.</span><span class="sxs-lookup"><span data-stu-id="db066-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="db066-164">Den valda vyn avgör hur resultaten exporteras:</span><span class="sxs-lookup"><span data-stu-id="db066-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="db066-165">**Tabellvy** – frågeresultaten exporteras i tabellform som en Microsoft Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="db066-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="db066-166">**Alla diagram** – frågeresultaten exporteras som en JPEG-bild av det renderade diagrammet</span><span class="sxs-lookup"><span data-stu-id="db066-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="db066-167">Öka detaljnivån från frågeresultat</span><span class="sxs-lookup"><span data-stu-id="db066-167">Drill down from query results</span></span>
<span data-ttu-id="db066-168">Om du snabbt vill granska en post i frågeresultatet markerar du motsvarande rad för att öppna **inspelningspanelen Inspektera.**</span><span class="sxs-lookup"><span data-stu-id="db066-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="db066-169">Panelen innehåller följande information baserat på den valda posten:</span><span class="sxs-lookup"><span data-stu-id="db066-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="db066-170">**Tillgångar** – sammanfattad vy över de viktigaste tillgångarna (postlådor, enheter och användare) som finns i posten, berikade med tillgänglig information, till exempel risk- och exponeringsnivåer</span><span class="sxs-lookup"><span data-stu-id="db066-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="db066-171">**Processträd** – som genereras för poster med processinformation och berikas med hjälp av tillgänglig kontextuell information. I allmänhet kan frågor som returnerar fler kolumner resultera i rikare processträd.</span><span class="sxs-lookup"><span data-stu-id="db066-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="db066-172">**Alla detaljer** – alla värden från kolumnerna i posten</span><span class="sxs-lookup"><span data-stu-id="db066-172">**All details** — all the values from the columns in the record</span></span>  

![Bild på vald post med panel för att kontrollera posten](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="db066-174">Om du vill visa mer information om en viss entitet i frågeresultaten, till exempel en dator, fil, användare, IP-adress eller URL, väljer du entitetsidentifieraren för att öppna en detaljerad profilsida för den entiteten.</span><span class="sxs-lookup"><span data-stu-id="db066-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="db066-175">Justera dina frågor från resultaten</span><span class="sxs-lookup"><span data-stu-id="db066-175">Tweak your queries from the results</span></span>
<span data-ttu-id="db066-176">Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan.</span><span class="sxs-lookup"><span data-stu-id="db066-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="db066-177">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="db066-177">You can use the options to:</span></span>

- <span data-ttu-id="db066-178">Leta uttryckligen efter det valda värdet ( `==` )</span><span class="sxs-lookup"><span data-stu-id="db066-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="db066-179">Uteslut det markerade värdet från frågan ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="db066-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="db066-180">Få mer avancerade operatorer för att lägga till värdet i frågan, till exempel `contains` `starts with``ends with`</span><span class="sxs-lookup"><span data-stu-id="db066-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild på avancerad jaktresultatuppsättning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="db066-182">Filtrera frågeresultaten</span><span class="sxs-lookup"><span data-stu-id="db066-182">Filter the query results</span></span>
<span data-ttu-id="db066-183">Filtren som visas till höger ger en sammanfattning av resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="db066-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="db066-184">Varje kolumn har ett eget avsnitt med de distinkta värden som hittats för den kolumnen och antalet instanser.</span><span class="sxs-lookup"><span data-stu-id="db066-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="db066-185">Förfina frågan genom att markera `+` knapparna eller `-` på de värden som du vill inkludera eller utesluta och sedan välja Kör **fråga**.</span><span class="sxs-lookup"><span data-stu-id="db066-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild på avancerat jaktfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="db066-187">När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="db066-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db066-188">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="db066-188">Related topics</span></span>
- [<span data-ttu-id="db066-189">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="db066-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="db066-190">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="db066-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="db066-191">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="db066-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="db066-192">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="db066-192">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="db066-193">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="db066-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="db066-194">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="db066-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="db066-195">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="db066-195">Custom detections overview</span></span>](custom-detections-overview.md)
