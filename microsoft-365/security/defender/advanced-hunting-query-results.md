---
title: Arbeta med avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Få ut mesta resultatet av frågeresultatet som returneras av avancerad sökning i Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto, visualization, chart, filters, drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952602"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="06662-104">Arbeta med avancerade frågeresultat för sökning</span><span class="sxs-lookup"><span data-stu-id="06662-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="06662-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="06662-105">**Applies to:**</span></span>
- <span data-ttu-id="06662-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06662-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="06662-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="06662-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="06662-108">Du kan skapa avancerade [sökfrågor](advanced-hunting-overview.md) för att få exakt information, men du kan också arbeta med frågeresultatet för att få ytterligare insikter och undersöka specifika aktiviteter och indikatorer.</span><span class="sxs-lookup"><span data-stu-id="06662-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="06662-109">Du kan utföra följande åtgärder på dina frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="06662-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="06662-110">Visa resultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="06662-110">View results as a table or chart</span></span>
- <span data-ttu-id="06662-111">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="06662-111">Export tables and charts</span></span>
- <span data-ttu-id="06662-112">Granska nedåt till detaljerad entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="06662-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="06662-113">Justera frågorna direkt från resultatet eller använd filter</span><span class="sxs-lookup"><span data-stu-id="06662-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="06662-114">Visa frågeresultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="06662-114">View query results as a table or chart</span></span>
<span data-ttu-id="06662-115">Som standard visar avancerad sökning frågeresultat som tabelldata.</span><span class="sxs-lookup"><span data-stu-id="06662-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="06662-116">Du kan också visa samma data som ett diagram.</span><span class="sxs-lookup"><span data-stu-id="06662-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="06662-117">Avancerad sökning har stöd för följande vyer:</span><span class="sxs-lookup"><span data-stu-id="06662-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="06662-118">Vytyp</span><span class="sxs-lookup"><span data-stu-id="06662-118">View type</span></span> | <span data-ttu-id="06662-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="06662-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="06662-120">**Tabell**</span><span class="sxs-lookup"><span data-stu-id="06662-120">**Table**</span></span> | <span data-ttu-id="06662-121">Visar frågeresultatet i tabellformat</span><span class="sxs-lookup"><span data-stu-id="06662-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="06662-122">**Stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-122">**Column chart**</span></span> | <span data-ttu-id="06662-123">Återger en serie unika objekt på x-axeln som lodräta staplar vars höjd representerar numeriska värden från ett annat fält</span><span class="sxs-lookup"><span data-stu-id="06662-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="06662-124">**Staplat stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-124">**Stacked column chart**</span></span> | <span data-ttu-id="06662-125">Återger en serie unika objekt på x-axeln som staplade lodräta staplar vars höjd representerar numeriska värden från ett eller flera andra fält</span><span class="sxs-lookup"><span data-stu-id="06662-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="06662-126">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-126">**Pie chart**</span></span> | <span data-ttu-id="06662-127">Återger avsnittsdiagram som representerar unika element.</span><span class="sxs-lookup"><span data-stu-id="06662-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="06662-128">Storleken på varje cirkel representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="06662-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="06662-129">**Ringdiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-129">**Donut chart**</span></span> | <span data-ttu-id="06662-130">Återger avsnittsbåge som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="06662-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="06662-131">Längden på varje båge representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="06662-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="06662-132">**Linjediagram**</span><span class="sxs-lookup"><span data-stu-id="06662-132">**Line chart**</span></span> | <span data-ttu-id="06662-133">Ritar numeriska värden för en serie unika objekt och kopplar samman de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="06662-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="06662-134">**Punktdiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-134">**Scatter chart**</span></span> | <span data-ttu-id="06662-135">Ritar numeriska värden för en serie unika objekt</span><span class="sxs-lookup"><span data-stu-id="06662-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="06662-136">**Areadiagram**</span><span class="sxs-lookup"><span data-stu-id="06662-136">**Area chart**</span></span> | <span data-ttu-id="06662-137">Ritar numeriska värden för en serie unika objekt och fyller i avsnitten under de uppritade värdena</span><span class="sxs-lookup"><span data-stu-id="06662-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="06662-138">Skapa frågor för effektiva diagram</span><span class="sxs-lookup"><span data-stu-id="06662-138">Construct queries for effective charts</span></span>
<span data-ttu-id="06662-139">Vid rendering av diagram identifierar avancerad sökning automatiskt kolumner av intresse och de numeriska värdena som ska aggregeras.</span><span class="sxs-lookup"><span data-stu-id="06662-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="06662-140">Skapa meningsfulla diagram genom att skapa frågor för att returnera de specifika värden som du vill se visualiserade.</span><span class="sxs-lookup"><span data-stu-id="06662-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="06662-141">Här är några exempelfrågor och de resulterande diagrammen.</span><span class="sxs-lookup"><span data-stu-id="06662-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="06662-142">Aviseringar efter allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="06662-142">Alerts by severity</span></span>
<span data-ttu-id="06662-143">Använd `summarize` operatorn för att räkna antalet värden som ska visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="06662-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="06662-144">I frågan nedan används `summarize` operatorn för att få antalet varningar med allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="06662-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="06662-145">När resultatet återges visas varje allvarlighetsgrad i ett stapeldiagram som en separat kolumn:</span><span class="sxs-lookup"><span data-stu-id="06662-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="06662-146">![Bild av avancerade frågeresultat för sökning som visas som ett stapeldiagram ](../../media/advanced-hunting-column-chart.jpg)
 *Frågeresultat för aviseringar efter allvarlighetsgrad som visas som ett stapeldiagram*</span><span class="sxs-lookup"><span data-stu-id="06662-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="06662-147">Aviserings allvarlighetsgrad per operativsystem</span><span class="sxs-lookup"><span data-stu-id="06662-147">Alert severity by operating system</span></span>
<span data-ttu-id="06662-148">Du kan också använda `summarize` operatorn för att förbereda resultat för diagramvärden från flera fält.</span><span class="sxs-lookup"><span data-stu-id="06662-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="06662-149">Du kanske till exempel vill veta hur allvarlighetsgraderna för varningar fördelas mellan operativsystemen.</span><span class="sxs-lookup"><span data-stu-id="06662-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="06662-150">Frågan nedan använder en operator för att hämta OS-information från tabellen och använder sedan `join` för att räkna värden i både och `DeviceInfo` `summarize` `OSPlatform` `Severity` kolumner:</span><span class="sxs-lookup"><span data-stu-id="06662-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="06662-151">Dessa resultat visualiseras bäst med hjälp av ett staplat diagram:</span><span class="sxs-lookup"><span data-stu-id="06662-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="06662-152">![Bild av avancerade frågeresultat för sökning i ett staplat diagram Frågeresultat för varningar efter OS och allvarlighetsgrad ](../../media/advanced-hunting-stacked-chart.jpg)
 *som visas som ett staplat diagram*</span><span class="sxs-lookup"><span data-stu-id="06662-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="06662-153">Nätfiskemeddelanden i topp tio avsändardomäner</span><span class="sxs-lookup"><span data-stu-id="06662-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="06662-154">Om du hanterar en lista med värden som inte är ändliga kan du använda operatorn för att visa endast de värden som har `Top` flest förekomster.</span><span class="sxs-lookup"><span data-stu-id="06662-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="06662-155">Om du till exempel vill ha de tio vanligaste avsändardomänerna med flest nätfiskemeddelanden använder du frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="06662-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="06662-156">Använd vyn cirkeldiagram för att effektivt visa distribution över de övre domänerna:</span><span class="sxs-lookup"><span data-stu-id="06662-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="06662-157">![Bild av avancerade frågeresultat för sökning som visas som ett cirkeldiagram Cirkeldiagram som visar fördelningen av ](../../media/advanced-hunting-pie-chart.jpg)
 *nätfiskemeddelanden mellan de övre avsändardomänerna*</span><span class="sxs-lookup"><span data-stu-id="06662-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="06662-158">Filaktiviteter över tid</span><span class="sxs-lookup"><span data-stu-id="06662-158">File activities over time</span></span>
<span data-ttu-id="06662-159">Med hjälp `summarize` av operatorn `bin()` med funktionen kan du söka efter händelser som innefattar en viss indikator över tid.</span><span class="sxs-lookup"><span data-stu-id="06662-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="06662-160">I frågan nedan räknas händelser som innefattar filen med 30 minuters intervall `invoice.doc` för att visa insamlingar i aktivitet relaterad till den filen:</span><span class="sxs-lookup"><span data-stu-id="06662-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="06662-161">I linjediagrammet nedan markeras tidsperioder tydligt med mer aktivitet som `invoice.doc` innefattar:</span><span class="sxs-lookup"><span data-stu-id="06662-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="06662-162">![Bild av avancerade frågeresultat för sökning som visas som ett linjediagram ](../../media/advanced-hunting-line-chart.jpg)
 *som visar antalet händelser som innefattar en fil över tid*</span><span class="sxs-lookup"><span data-stu-id="06662-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="06662-163">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="06662-163">Export tables and charts</span></span>
<span data-ttu-id="06662-164">När du har kört en fråga väljer **du Exportera** för att spara resultaten i en lokal fil.</span><span class="sxs-lookup"><span data-stu-id="06662-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="06662-165">Den valda vyn avgör hur resultatet exporteras:</span><span class="sxs-lookup"><span data-stu-id="06662-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="06662-166">**Tabellvy** – frågeresultatet exporteras i tabellform som en Microsoft Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="06662-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="06662-167">**Alla diagram** – frågeresultatet exporteras som en JPEG-bild av det återgivna diagrammet</span><span class="sxs-lookup"><span data-stu-id="06662-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="06662-168">Öka detalj detalj detalj för frågeresultat</span><span class="sxs-lookup"><span data-stu-id="06662-168">Drill down from query results</span></span>
<span data-ttu-id="06662-169">Om du snabbt vill granska en post i dina frågeresultat markerar du motsvarande rad för att öppna **panelen Kontrollera** post.</span><span class="sxs-lookup"><span data-stu-id="06662-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="06662-170">Panelen innehåller följande information baserad på den valda posten:</span><span class="sxs-lookup"><span data-stu-id="06662-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="06662-171">**Tillgångar** – sammanfattad vy över huvudtillgångarna (postlådor, enheter och användare) som finns i posten, allt bättre med tillgänglig information, t.ex. risk- och exponeringsnivåer</span><span class="sxs-lookup"><span data-stu-id="06662-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="06662-172">**Processträd** – genererat för poster med processinformation och som är bättre genom att använda tillgänglig kontextinformation. I allmänhet kan frågor som returnerar fler kolumner leda till rikare processträd.</span><span class="sxs-lookup"><span data-stu-id="06662-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="06662-173">**All information** – alla värden från kolumnerna i posten</span><span class="sxs-lookup"><span data-stu-id="06662-173">**All details** — all the values from the columns in the record</span></span>  

![Bild av markerad post med panel för att kontrollera posten](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="06662-175">Om du vill visa mer information om en specifik entitet i frågeresultatet, till exempel en dator, fil, användare, IP-adress eller URL väljer du entitetsidentifieraren för att öppna en detaljerad profilsida för enheten.</span><span class="sxs-lookup"><span data-stu-id="06662-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="06662-176">Justera frågorna från resultatet</span><span class="sxs-lookup"><span data-stu-id="06662-176">Tweak your queries from the results</span></span>
<span data-ttu-id="06662-177">Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan.</span><span class="sxs-lookup"><span data-stu-id="06662-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="06662-178">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="06662-178">You can use the options to:</span></span>

- <span data-ttu-id="06662-179">Leta explicit efter det markerade värdet ( `==` )</span><span class="sxs-lookup"><span data-stu-id="06662-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="06662-180">Utesluta det valda värdet från frågan ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="06662-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="06662-181">Få mer avancerade operatorer för att lägga till värdet i din fråga, till exempel `contains` `starts with` , och `ends with`</span><span class="sxs-lookup"><span data-stu-id="06662-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild på avancerad uppsättning med resultat för sökning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="06662-183">Filtrera frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="06662-183">Filter the query results</span></span>
<span data-ttu-id="06662-184">Filtren som visas till höger ger en sammanfattning av resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="06662-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="06662-185">Varje kolumn har ett eget avsnitt med distinkta värden för kolumnen och antalet förekomster.</span><span class="sxs-lookup"><span data-stu-id="06662-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="06662-186">Förfina frågan genom att välja eller knapparna på de värden som du `+` vill inkludera eller exkludera och sedan välja Kör `-` **fråga.**</span><span class="sxs-lookup"><span data-stu-id="06662-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild på avancerat sökfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="06662-188">När du använder filtret för att ändra frågan och sedan kör frågan uppdateras resultatet.</span><span class="sxs-lookup"><span data-stu-id="06662-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="06662-189">Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="06662-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="06662-190">[Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor.</span><span class="sxs-lookup"><span data-stu-id="06662-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="06662-191">Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="06662-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="06662-192">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="06662-192">Related topics</span></span>
- [<span data-ttu-id="06662-193">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="06662-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06662-194">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="06662-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06662-195">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="06662-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06662-196">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="06662-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06662-197">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="06662-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06662-198">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="06662-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="06662-199">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="06662-199">Custom detections overview</span></span>](custom-detections-overview.md)
