---
title: Arbeta med avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Få ut mesta av sökresultaten som returneras av avancerad sökning i Microsoft 365 Defender
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3481190a615cfa8914b3623f09d4079468bd431f
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712120"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="07633-104">Arbeta med avancerade frågeresultat för sökning</span><span class="sxs-lookup"><span data-stu-id="07633-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07633-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07633-105">**Applies to:**</span></span>
- <span data-ttu-id="07633-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07633-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="07633-107">Du kan skapa [](advanced-hunting-overview.md) avancerade sökfrågor för att returnera mycket exakt information, men du kan också arbeta med frågeresultatet för att få ytterligare insikter och undersöka specifika aktiviteter och indikatorer.</span><span class="sxs-lookup"><span data-stu-id="07633-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="07633-108">Du kan utföra följande åtgärder på dina frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="07633-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="07633-109">Visa resultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="07633-109">View results as a table or chart</span></span>
- <span data-ttu-id="07633-110">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="07633-110">Export tables and charts</span></span>
- <span data-ttu-id="07633-111">Öka detaljgranskningen för detaljerad entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="07633-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="07633-112">Justera frågorna direkt från resultatet eller använd filter</span><span class="sxs-lookup"><span data-stu-id="07633-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="07633-113">Visa frågeresultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="07633-113">View query results as a table or chart</span></span>
<span data-ttu-id="07633-114">Som standard visar avancerad sökning frågeresultat som tabelldata.</span><span class="sxs-lookup"><span data-stu-id="07633-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="07633-115">Du kan också visa samma data som ett diagram.</span><span class="sxs-lookup"><span data-stu-id="07633-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="07633-116">Avancerad sökning har stöd för följande vyer:</span><span class="sxs-lookup"><span data-stu-id="07633-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="07633-117">Vytyp</span><span class="sxs-lookup"><span data-stu-id="07633-117">View type</span></span> | <span data-ttu-id="07633-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="07633-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="07633-119">**Tabell**</span><span class="sxs-lookup"><span data-stu-id="07633-119">**Table**</span></span> | <span data-ttu-id="07633-120">Visar frågeresultatet i tabellformat</span><span class="sxs-lookup"><span data-stu-id="07633-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="07633-121">**Stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-121">**Column chart**</span></span> | <span data-ttu-id="07633-122">Återger en serie unika objekt på x-axeln som lodräta staplar vars höjd representerar numeriska värden från ett annat fält</span><span class="sxs-lookup"><span data-stu-id="07633-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="07633-123">**Staplat stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-123">**Stacked column chart**</span></span> | <span data-ttu-id="07633-124">Återger en serie unika element på x-axeln som staplade lodräta staplar vars höjd representerar numeriska värden från ett eller flera andra fält</span><span class="sxs-lookup"><span data-stu-id="07633-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="07633-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-125">**Pie chart**</span></span> | <span data-ttu-id="07633-126">Återger avsnittsdiagram som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="07633-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="07633-127">Storleken på varje cirkel representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="07633-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="07633-128">**Ringdiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-128">**Donut chart**</span></span> | <span data-ttu-id="07633-129">Återger avsnittsbåge som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="07633-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="07633-130">Längden på varje båge representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="07633-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="07633-131">**Linjediagram**</span><span class="sxs-lookup"><span data-stu-id="07633-131">**Line chart**</span></span> | <span data-ttu-id="07633-132">Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="07633-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="07633-133">**Punktdiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-133">**Scatter chart**</span></span> | <span data-ttu-id="07633-134">Ritar numeriska värden för en serie unika objekt</span><span class="sxs-lookup"><span data-stu-id="07633-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="07633-135">**Områdesdiagram**</span><span class="sxs-lookup"><span data-stu-id="07633-135">**Area chart**</span></span> | <span data-ttu-id="07633-136">Ritar numeriska värden för en serie unika objekt och fyller avsnitten under de utritade värdena</span><span class="sxs-lookup"><span data-stu-id="07633-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="07633-137">Skapa frågor för effektiva diagram</span><span class="sxs-lookup"><span data-stu-id="07633-137">Construct queries for effective charts</span></span>
<span data-ttu-id="07633-138">Vid rendering av diagram identifierar avancerad sökning automatiskt kolumner av intresse och de numeriska värden som ska aggregeras.</span><span class="sxs-lookup"><span data-stu-id="07633-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="07633-139">För att få meningsfulla diagram skapar du frågorna för att returnera de specifika värden som du vill se visualiserade.</span><span class="sxs-lookup"><span data-stu-id="07633-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="07633-140">Här är några exempelfrågor och de resulterande diagrammen.</span><span class="sxs-lookup"><span data-stu-id="07633-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="07633-141">Varningar efter allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="07633-141">Alerts by severity</span></span>
<span data-ttu-id="07633-142">Använd `summarize` operatorn för att räkna antalet numeriska värden som du vill visa i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="07633-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="07633-143">I frågan nedan används `summarize` operatorn för att få antalet varningar med allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="07633-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="07633-144">När resultatet återges visas varje allvarlighetsgrad i ett stapeldiagram som en separat kolumn:</span><span class="sxs-lookup"><span data-stu-id="07633-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="07633-145">![Bild av avancerade frågeresultat för sökning som visas som ett stapeldiagram Med frågeresultat visas varningar efter ](../../media/advanced-hunting-column-chart.jpg)
 *allvarlighetsgrad som ett stapeldiagram*</span><span class="sxs-lookup"><span data-stu-id="07633-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="07633-146">Aviserings allvarlighetsgrad per operativsystem</span><span class="sxs-lookup"><span data-stu-id="07633-146">Alert severity by operating system</span></span>
<span data-ttu-id="07633-147">Du kan också använda `summarize` operatorn för att förbereda resultat för diagramvärden från flera fält.</span><span class="sxs-lookup"><span data-stu-id="07633-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="07633-148">Du kanske till exempel vill förstå hur allvarlighetsgraderna för varningar är fördelade mellan operativsystem (OS).</span><span class="sxs-lookup"><span data-stu-id="07633-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="07633-149">Frågan nedan använder en operator för att hämta OS-information från tabellen och använder `join` sedan för att räkna värden i både kolumner och `DeviceInfo` `summarize` `OSPlatform` `Severity` kolumner:</span><span class="sxs-lookup"><span data-stu-id="07633-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="07633-150">De här resultaten visualiseras bäst med hjälp av ett staplat diagram:</span><span class="sxs-lookup"><span data-stu-id="07633-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="07633-151">![Bild av avancerade frågeresultat för sökning visade som ett staplat diagram, frågeresultat för varningar efter ](../../media/advanced-hunting-stacked-chart.jpg)
 *OS och allvarlighetsgrad visad som ett staplat diagram*</span><span class="sxs-lookup"><span data-stu-id="07633-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="07633-152">Nätfiskemeddelanden i de tio översta avsändardomänerna</span><span class="sxs-lookup"><span data-stu-id="07633-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="07633-153">Om du hanterar en lista med värden som inte är ändliga kan du använda operatorn för att visa endast de värden som innehåller `Top` de flesta förekomster.</span><span class="sxs-lookup"><span data-stu-id="07633-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="07633-154">Om du till exempel vill ha de tio vanligaste avsändardomänerna med flest nätfiskemeddelanden använder du frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="07633-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="07633-155">Använd cirkeldiagramvyn för att effektivt visa fördelningen över de översta domänerna:</span><span class="sxs-lookup"><span data-stu-id="07633-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="07633-156">![Bild av avancerade frågeresultat för sökning som visas som ett cirkeldiagram som visar ](../../media/advanced-hunting-pie-chart.jpg)
 *fördelningen av nätfiskemeddelanden över de översta avsändardomänerna*</span><span class="sxs-lookup"><span data-stu-id="07633-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="07633-157">Filaktiviteter över tid</span><span class="sxs-lookup"><span data-stu-id="07633-157">File activities over time</span></span>
<span data-ttu-id="07633-158">Med hjälp `summarize` av operatorn `bin()` med funktionen kan du söka efter händelser som innefattar en viss indikator över tid.</span><span class="sxs-lookup"><span data-stu-id="07633-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="07633-159">Frågan nedan räknar händelser som innefattar filen med 30 minuters intervall `invoice.doc` för att visa insamlingar i aktiviteter relaterade till den filen:</span><span class="sxs-lookup"><span data-stu-id="07633-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="07633-160">I linjediagrammet nedan markeras tidsperioder tydligt med mer aktivitet som `invoice.doc` innefattar:</span><span class="sxs-lookup"><span data-stu-id="07633-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="07633-161">![Bild av avancerade sökresultat för sökfrågor som visas som ett linjediagram som visar antalet ](../../media/advanced-hunting-line-chart.jpg)
 *händelser som innefattar en fil över tid*</span><span class="sxs-lookup"><span data-stu-id="07633-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="07633-162">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="07633-162">Export tables and charts</span></span>
<span data-ttu-id="07633-163">När du har kört en fråga **väljer du Exportera** för att spara resultaten i en lokal fil.</span><span class="sxs-lookup"><span data-stu-id="07633-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="07633-164">Den valda vyn avgör hur resultatet exporteras:</span><span class="sxs-lookup"><span data-stu-id="07633-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="07633-165">**Tabellvy** – frågeresultatet exporteras i tabellform som en Microsoft Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="07633-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="07633-166">**Alla diagram** – frågeresultatet exporteras som en JPEG-bild av det renderade diagrammet</span><span class="sxs-lookup"><span data-stu-id="07633-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="07633-167">Granska nedåt från frågeresultat</span><span class="sxs-lookup"><span data-stu-id="07633-167">Drill down from query results</span></span>
<span data-ttu-id="07633-168">Om du snabbt vill granska en post i frågeresultatet markerar du motsvarande rad för att öppna **panelen Kontrollera** post.</span><span class="sxs-lookup"><span data-stu-id="07633-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="07633-169">Panelen innehåller följande information baserat på den valda posten:</span><span class="sxs-lookup"><span data-stu-id="07633-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="07633-170">**Tillgångar** – sammanfattad vy över huvudtillgångarna (postlådor, enheter och användare) som finns i posten, som är bättre beskad med tillgänglig information, t.ex. risk- och exponeringsnivåer</span><span class="sxs-lookup"><span data-stu-id="07633-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="07633-171">**Processträd** – som genereras för arkivhandlingar med processinformation och som är bättre genom att använda tillgänglig kontextinformation. I allmänhet kan frågor som returnerar fler kolumner resultera i rikare processträd.</span><span class="sxs-lookup"><span data-stu-id="07633-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="07633-172">**All information** – alla värden från kolumnerna i posten</span><span class="sxs-lookup"><span data-stu-id="07633-172">**All details** — all the values from the columns in the record</span></span>  

![Bild på markerad post med panel för att kontrollera posten](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="07633-174">Om du vill visa mer information om en viss enhet i frågeresultatet, till exempel en dator, fil, användare, IP-adress eller URL, väljer du entitetsidentifieraren för att öppna en detaljerad profilsida för enheten.</span><span class="sxs-lookup"><span data-stu-id="07633-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="07633-175">Justera frågorna från resultatet</span><span class="sxs-lookup"><span data-stu-id="07633-175">Tweak your queries from the results</span></span>
<span data-ttu-id="07633-176">Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan.</span><span class="sxs-lookup"><span data-stu-id="07633-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="07633-177">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="07633-177">You can use the options to:</span></span>

- <span data-ttu-id="07633-178">Leta explicit efter det valda värdet `==` ()</span><span class="sxs-lookup"><span data-stu-id="07633-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="07633-179">Exkludera det valda värdet från frågan ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="07633-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="07633-180">Få mer avancerade operatorer för att lägga till värdet i frågan, till exempel `contains` `starts with` och `ends with`</span><span class="sxs-lookup"><span data-stu-id="07633-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild på avancerad uppsättning med sökresultat](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="07633-182">Filtrera frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="07633-182">Filter the query results</span></span>
<span data-ttu-id="07633-183">Filtren som visas till höger ger en sammanfattning av resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="07633-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="07633-184">Varje kolumn har ett eget avsnitt med distinkta värden för kolumnen och antalet förekomster.</span><span class="sxs-lookup"><span data-stu-id="07633-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="07633-185">Förfina frågan genom att välja eller knapparna för de värden som du `+` vill inkludera eller exkludera och sedan välja Kör `-` **fråga.**</span><span class="sxs-lookup"><span data-stu-id="07633-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild av avancerat sökfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="07633-187">När du använder filtret för att ändra frågan och sedan kör frågan uppdateras resultaten i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="07633-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07633-188">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="07633-188">Related topics</span></span>
- [<span data-ttu-id="07633-189">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="07633-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07633-190">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="07633-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07633-191">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="07633-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="07633-192">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="07633-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="07633-193">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="07633-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="07633-194">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="07633-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="07633-195">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="07633-195">Custom detections overview</span></span>](custom-detections-overview.md)
