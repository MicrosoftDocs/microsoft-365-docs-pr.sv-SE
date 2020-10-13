---
title: Arbeta med frågor för avancerad jakt i Microsoft Threat Protection
description: Få ut mesta möjliga av frågeresultaten som har returnerats av Advanced jakt mot Microsoft Threat Protection
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, Microsoft 365, Microsoft Threat Protection, visualisering, diagram, filter, detalj granskning
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e19859189b57bbc9a6a4bbfb87fb224b2735331b
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431081"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="26855-104">Arbeta med resultat från avancerad jakt fråga</span><span class="sxs-lookup"><span data-stu-id="26855-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="26855-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="26855-105">**Applies to:**</span></span>
- <span data-ttu-id="26855-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="26855-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="26855-107">Du kan också använda frågeresultatet för att få mer detaljerad information och undersöka specifika aktiviteter och indikatorer, samtidigt som du skapar frågor för de [avancerade jakt](advanced-hunting-overview.md) frågorna.</span><span class="sxs-lookup"><span data-stu-id="26855-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="26855-108">Du kan utföra följande åtgärder i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="26855-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="26855-109">Visa resultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="26855-109">View results as a table or chart</span></span>
- <span data-ttu-id="26855-110">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="26855-110">Export tables and charts</span></span>
- <span data-ttu-id="26855-111">Öka detalj nivån till detaljerad entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="26855-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="26855-112">Justera dina frågor direkt från resultaten eller använda filter</span><span class="sxs-lookup"><span data-stu-id="26855-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="26855-113">Visa frågeresultat som en tabell eller ett diagram</span><span class="sxs-lookup"><span data-stu-id="26855-113">View query results as a table or chart</span></span>
<span data-ttu-id="26855-114">Som standard visar Advanced jakt frågeresultat som tabell data.</span><span class="sxs-lookup"><span data-stu-id="26855-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="26855-115">Du kan också visa samma data som ett diagram.</span><span class="sxs-lookup"><span data-stu-id="26855-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="26855-116">Avancerad jakt stöder följande vyer:</span><span class="sxs-lookup"><span data-stu-id="26855-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="26855-117">Vytyp</span><span class="sxs-lookup"><span data-stu-id="26855-117">View type</span></span> | <span data-ttu-id="26855-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="26855-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="26855-119">**Tabell**</span><span class="sxs-lookup"><span data-stu-id="26855-119">**Table**</span></span> | <span data-ttu-id="26855-120">Visar frågeresultaten i tabell format</span><span class="sxs-lookup"><span data-stu-id="26855-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="26855-121">**Stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="26855-121">**Column chart**</span></span> | <span data-ttu-id="26855-122">Återger en serie unika element på x-axeln som lodräta staplar vars höjder representerar numeriska värden från ett annat fält</span><span class="sxs-lookup"><span data-stu-id="26855-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="26855-123">**Staplat stapeldiagram**</span><span class="sxs-lookup"><span data-stu-id="26855-123">**Stacked column chart**</span></span> | <span data-ttu-id="26855-124">Återger en serie unika element på x-axeln som staplade lodräta staplar vars höjder representerar numeriska värden från ett eller flera andra fält</span><span class="sxs-lookup"><span data-stu-id="26855-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="26855-125">**Cirkel diagram**</span><span class="sxs-lookup"><span data-stu-id="26855-125">**Pie chart**</span></span> | <span data-ttu-id="26855-126">Återger avsnitts pajer som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="26855-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="26855-127">Storleken på varje cirkel representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="26855-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="26855-128">**Ring diagram**</span><span class="sxs-lookup"><span data-stu-id="26855-128">**Donut chart**</span></span> | <span data-ttu-id="26855-129">Återger avsnitts bågar som representerar unika objekt.</span><span class="sxs-lookup"><span data-stu-id="26855-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="26855-130">Längden på varje båge representerar numeriska värden från ett annat fält.</span><span class="sxs-lookup"><span data-stu-id="26855-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="26855-131">**Linje diagram**</span><span class="sxs-lookup"><span data-stu-id="26855-131">**Line chart**</span></span> | <span data-ttu-id="26855-132">Ritar numeriska värden för en serie unika objekt och kopplar de ritade värdena</span><span class="sxs-lookup"><span data-stu-id="26855-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="26855-133">**Punkt diagram**</span><span class="sxs-lookup"><span data-stu-id="26855-133">**Scatter chart**</span></span> | <span data-ttu-id="26855-134">Ritar numeriska värden för en serie unika objekt</span><span class="sxs-lookup"><span data-stu-id="26855-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="26855-135">**Ytdiagram**</span><span class="sxs-lookup"><span data-stu-id="26855-135">**Area chart**</span></span> | <span data-ttu-id="26855-136">Ritar numeriska värden för en serie unika element och fyller avsnitten nedanför de uppritade värdena</span><span class="sxs-lookup"><span data-stu-id="26855-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="26855-137">Skapa frågor för effektiva diagram</span><span class="sxs-lookup"><span data-stu-id="26855-137">Construct queries for effective charts</span></span>
<span data-ttu-id="26855-138">Vid åter givning av diagram identifieras kolumner av intresse automatiskt och de numeriska värdena till aggregation.</span><span class="sxs-lookup"><span data-stu-id="26855-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="26855-139">För att få meningsfulla diagram skapar du dina frågor för att returnera de specifika värden som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="26855-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="26855-140">Här är några exempel frågor och resulterande diagram.</span><span class="sxs-lookup"><span data-stu-id="26855-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="26855-141">Aviseringar efter allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="26855-141">Alerts by severity</span></span>
<span data-ttu-id="26855-142">Använd `summarize` operatorn för att få ett numeriskt antal värden som du vill visa i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="26855-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="26855-143">I frågan nedan används `summarize` operatorn för att få antalet aviseringar efter allvarlighets grad.</span><span class="sxs-lookup"><span data-stu-id="26855-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="26855-144">När du återger resultaten visas varje allvarlighets värde som en separat kolumn i ett stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="26855-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="26855-145">![En bild av de avancerade frågeresultaten visas som ett kolumn diagram ](../../media/advanced-hunting-column-chart.jpg)
 *Frågeresultat för aviseringar efter allvarlighets grad visas som ett stapeldiagram*</span><span class="sxs-lookup"><span data-stu-id="26855-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="26855-146">Aviserings allvarlighets grad per operativ system</span><span class="sxs-lookup"><span data-stu-id="26855-146">Alert severity by operating system</span></span>
<span data-ttu-id="26855-147">Du kan också använda `summarize` operatorn för att förbereda resultat för diagram värden från flera fält.</span><span class="sxs-lookup"><span data-stu-id="26855-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="26855-148">Du kanske till exempel vill förstå hur varnings allvarlighets grader distribueras för olika operativ system (OS).</span><span class="sxs-lookup"><span data-stu-id="26855-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="26855-149">Frågan nedan använder en `join` operator för att hämta OS-information från `DeviceInfo` tabellen och använder sedan `summarize` för att räkna värden i både `OSPlatform` `Severity` kolumnerna och.</span><span class="sxs-lookup"><span data-stu-id="26855-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="26855-150">De här resultaten är bäst visualiserade med ett staplat stapeldiagram:</span><span class="sxs-lookup"><span data-stu-id="26855-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="26855-151">![En bild av de avancerade frågeresultaten visas som ett staplat diagram ](../../media/advanced-hunting-stacked-chart.jpg)
 *Frågeresultat för aviseringar via OS och allvarlighets grad som visas som ett staplat diagram*</span><span class="sxs-lookup"><span data-stu-id="26855-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="26855-152">Nät fiske meddelanden via de tio främsta avsändarenas domäner</span><span class="sxs-lookup"><span data-stu-id="26855-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="26855-153">Om du arbetar med en lista med värden som inte är begränsade kan du använda `Top` operatorn för att endast visa de värden som har flest förekomster.</span><span class="sxs-lookup"><span data-stu-id="26855-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="26855-154">Om du till exempel vill få de tio främsta avsändare-domänerna med flest nätfiske-meddelanden använder du frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="26855-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="26855-155">Använd vyn cirkel diagram för att Visa fördelningen effektivt i de översta domänerna:</span><span class="sxs-lookup"><span data-stu-id="26855-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="26855-156">![En bild av de avancerade frågeresultaten visas som ett cirkel diagram i cirkel diagrammet som ](../../media/advanced-hunting-pie-chart.jpg)
 *visar fördelningen av nät fiske meddelanden via överdelen översändare*</span><span class="sxs-lookup"><span data-stu-id="26855-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="26855-157">Fil aktiviteter över tid</span><span class="sxs-lookup"><span data-stu-id="26855-157">File activities over time</span></span>
<span data-ttu-id="26855-158">Med `summarize` operatorn med `bin()` funktionen kan du söka efter händelser med en viss indikator över tiden.</span><span class="sxs-lookup"><span data-stu-id="26855-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="26855-159">Frågan nedan räknar händelser som berör filen `invoice.doc` med 30 minuters mellanrum för att Visa mellanvara i en aktivitet som är relaterad till filen:</span><span class="sxs-lookup"><span data-stu-id="26855-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="26855-160">Linje diagrammet nedan tydligt markerar tids perioder med mer aktivitet som berör `invoice.doc` :</span><span class="sxs-lookup"><span data-stu-id="26855-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="26855-161">![En bild av de avancerade frågeresultaten visas som ett linje ](../../media/advanced-hunting-line-chart.jpg)
 *diagram med linjer som visar antalet händelser som rör en fil över tid*</span><span class="sxs-lookup"><span data-stu-id="26855-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="26855-162">Exportera tabeller och diagram</span><span class="sxs-lookup"><span data-stu-id="26855-162">Export tables and charts</span></span>
<span data-ttu-id="26855-163">När du har kört en fråga väljer du **Exportera** för att spara resultatet i en lokal fil.</span><span class="sxs-lookup"><span data-stu-id="26855-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="26855-164">Den valda vyn bestämmer hur resultatet ska exporteras:</span><span class="sxs-lookup"><span data-stu-id="26855-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="26855-165">**Tabellvy** – frågeresultaten exporteras i tabell form som en Microsoft Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="26855-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="26855-166">**Ett diagram** – frågeresultaten exporteras som en JPEG-bild av det återgivna diagrammet</span><span class="sxs-lookup"><span data-stu-id="26855-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="26855-167">Öka detalj nivån från frågeresultat</span><span class="sxs-lookup"><span data-stu-id="26855-167">Drill down from query results</span></span>
<span data-ttu-id="26855-168">Om du snabbt vill inspektera en post i frågeresultatet markerar du motsvarande rad för att öppna panelen **Granska post** .</span><span class="sxs-lookup"><span data-stu-id="26855-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="26855-169">Panelen innehåller följande information baserad på den valda posten:</span><span class="sxs-lookup"><span data-stu-id="26855-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="26855-170">**Till gångar** – sammanfattad vy över huvud till gångar (post lådor, enheter och användare) som finns i posten, förföljda uppgifter, till exempel risk-och exponerings nivåer</span><span class="sxs-lookup"><span data-stu-id="26855-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="26855-171">**Process träd** – genererat för poster med process information och som berikas med tillgängliga kontext uppgifter; i allmänhet kan frågor som returnerar fler kolumner leda till bättre process träd.</span><span class="sxs-lookup"><span data-stu-id="26855-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="26855-172">**All information** – alla värden från kolumnerna i posten</span><span class="sxs-lookup"><span data-stu-id="26855-172">**All details** — all the values from the columns in the record</span></span>  

![Bild av den valda posten med panelen för kontroll av posten](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="26855-174">Om du vill visa mer information om en viss enhet i frågeresultatet, till exempel en dator, en fil, en användare, en IP-adress eller en URL, väljer du enhetens ID för att öppna en detaljerad profil sida för den enheten.</span><span class="sxs-lookup"><span data-stu-id="26855-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="26855-175">Justera dina frågor från resultaten</span><span class="sxs-lookup"><span data-stu-id="26855-175">Tweak your queries from the results</span></span>
<span data-ttu-id="26855-176">Högerklicka på ett värde i resultatet för att snabbt förbättra din fråga.</span><span class="sxs-lookup"><span data-stu-id="26855-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="26855-177">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="26855-177">You can use the options to:</span></span>

- <span data-ttu-id="26855-178">Leta tydligt efter det markerade värdet ( `==` )</span><span class="sxs-lookup"><span data-stu-id="26855-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="26855-179">Exkludera det markerade värdet från frågan ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="26855-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="26855-180">Få mer avancerade operatorer för att lägga till värdet i frågan, till `contains` exempel `starts with` och `ends with`</span><span class="sxs-lookup"><span data-stu-id="26855-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild av avancerad jakt resultat uppsättning](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="26855-182">Filtrera frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="26855-182">Filter the query results</span></span>
<span data-ttu-id="26855-183">De filter som visas till höger ger en sammanfattning av resultatet.</span><span class="sxs-lookup"><span data-stu-id="26855-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="26855-184">Varje kolumn har ett eget avsnitt med en lista med de DISTINCT-värden som hittas för den kolumnen och antalet förekomster.</span><span class="sxs-lookup"><span data-stu-id="26855-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="26855-185">Förfina frågan genom att välja `+` knapparna eller `-` på de värden som du vill inkludera eller exkludera och sedan välja **Kör fråga**.</span><span class="sxs-lookup"><span data-stu-id="26855-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild av filtret Avancerat jakt](../../media/advanced-hunting-filter.png)

<span data-ttu-id="26855-187">När du har tillämpat filtret för att ändra frågan och sedan kör frågan uppdateras resultaten.</span><span class="sxs-lookup"><span data-stu-id="26855-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26855-188">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="26855-188">Related topics</span></span>
- [<span data-ttu-id="26855-189">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="26855-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26855-190">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="26855-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="26855-191">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="26855-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="26855-192">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="26855-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="26855-193">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="26855-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="26855-194">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="26855-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="26855-195">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="26855-195">Custom detections overview</span></span>](custom-detections-overview.md)
