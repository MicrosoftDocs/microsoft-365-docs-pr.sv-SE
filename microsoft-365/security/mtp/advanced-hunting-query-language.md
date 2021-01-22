---
title: Lär dig det avancerade sökfrågespråket i Microsoft 365 Defender
description: Skapa din första fråga för hot och lär dig mer om vanliga operatorer och andra aspekter av det avancerade sökfrågans språk
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, språk, lär dig, första frågan, telemetri, händelser, telemetri, anpassade identifieringar, schema, kusto, operatörer, datatyper, powershell-nedladdning, frågeexempel
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
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929808"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="099f7-104">Lär dig det avancerade språket för sökfrågor</span><span class="sxs-lookup"><span data-stu-id="099f7-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="099f7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="099f7-105">**Applies to:**</span></span>
- <span data-ttu-id="099f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="099f7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="099f7-107">Avancerad sökning är baserad på [kustofrågans språk.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="099f7-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="099f7-108">Du kan använda kustooperatorer och -uttryck för att skapa frågor som letar upp information i ett särskilt [schema.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="099f7-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="099f7-109">Kör den första frågan för att bättre förstå de här begreppen.</span><span class="sxs-lookup"><span data-stu-id="099f7-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="099f7-110">Prova din första fråga</span><span class="sxs-lookup"><span data-stu-id="099f7-110">Try your first query</span></span>

<span data-ttu-id="099f7-111">Gå till Sök i Microsoft 365 säkerhetscenter **för** att köra din första fråga.</span><span class="sxs-lookup"><span data-stu-id="099f7-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="099f7-112">Använd följande exempel:</span><span class="sxs-lookup"><span data-stu-id="099f7-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="099f7-113">**[Kör den här frågan på avancerad sökning](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="099f7-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="099f7-114">Beskriv frågan och ange vilka tabeller som ska sökas</span><span class="sxs-lookup"><span data-stu-id="099f7-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="099f7-115">En kort kommentar har lagts till i början av frågan för att beskriva vad den används till.</span><span class="sxs-lookup"><span data-stu-id="099f7-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="099f7-116">Den här kommentaren hjälper dig om du senare bestämmer dig för att spara frågan och dela den med andra i organisationen.</span><span class="sxs-lookup"><span data-stu-id="099f7-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="099f7-117">Själva frågan börjar vanligtvis med ett tabellnamn följt av flera element som börjar med en pipe ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="099f7-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="099f7-118">I det här exemplet börjar vi med att skapa en union med två tabeller och lägger  `DeviceProcessEvents` `DeviceNetworkEvents` till rörelement efter behov.</span><span class="sxs-lookup"><span data-stu-id="099f7-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="099f7-119">Ange ett tidsintervall</span><span class="sxs-lookup"><span data-stu-id="099f7-119">Set the time range</span></span>
<span data-ttu-id="099f7-120">Det första rörelementet är ett tidsfilter som är inderat i de föregående sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="099f7-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="099f7-121">Genom att begränsa tidsperioden ser du till att frågorna presterar bra, returnerar hanterbara resultat och inte time out.</span><span class="sxs-lookup"><span data-stu-id="099f7-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="099f7-122">Kontrollera specifika processer</span><span class="sxs-lookup"><span data-stu-id="099f7-122">Check specific processes</span></span>
<span data-ttu-id="099f7-123">Tidsperioden följs omedelbart av en sökning efter processfilnamn som representerar PowerShell-programmet.</span><span class="sxs-lookup"><span data-stu-id="099f7-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="099f7-124">Söka efter specifika kommandosträngar</span><span class="sxs-lookup"><span data-stu-id="099f7-124">Search for specific command strings</span></span>
<span data-ttu-id="099f7-125">Därefter letar frågan efter strängar på kommandorader som vanligtvis används för att ladda ned filer med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="099f7-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="099f7-126">Anpassa resultatkolumner och längd</span><span class="sxs-lookup"><span data-stu-id="099f7-126">Customize result columns and length</span></span> 
<span data-ttu-id="099f7-127">Nu när frågan tydligt identifierar de data du vill hitta kan du definiera hur resultatet ska se ut.</span><span class="sxs-lookup"><span data-stu-id="099f7-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="099f7-128">`project` returnerar specifika kolumner `top` och begränsar antalet resultat.</span><span class="sxs-lookup"><span data-stu-id="099f7-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="099f7-129">De här operatorerna säkerställer att resultaten är väl formaterade och ganska stora och enkla att bearbeta.</span><span class="sxs-lookup"><span data-stu-id="099f7-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="099f7-130">Välj **Kör fråga** för att se resultatet.</span><span class="sxs-lookup"><span data-stu-id="099f7-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="099f7-131">Använd expanderikonen längst upp till höger i frågeredigeraren för att fokusera på din sökfråga och resultaten.</span><span class="sxs-lookup"><span data-stu-id="099f7-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Bild av kontrollen Utöka i den avancerade frågeredigeraren för sökfrågor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="099f7-133">Du kan visa frågeresultat som diagram och snabbt justera filter.</span><span class="sxs-lookup"><span data-stu-id="099f7-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="099f7-134">Mer information finns [i om hur du arbetar med frågeresultat](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="099f7-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="099f7-135">Lär dig vanliga frågeoperatorer</span><span class="sxs-lookup"><span data-stu-id="099f7-135">Learn common query operators</span></span>

<span data-ttu-id="099f7-136">Du har just kört den första frågan och har en övergripande uppfattning om dess komponenter.</span><span class="sxs-lookup"><span data-stu-id="099f7-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="099f7-137">Det är dags att gå tillbaka lite och lära dig grunderna.</span><span class="sxs-lookup"><span data-stu-id="099f7-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="099f7-138">Det språk för kustofrågor som används av avancerad sökning har stöd för ett antal operatorer, bland annat följande vanliga.</span><span class="sxs-lookup"><span data-stu-id="099f7-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="099f7-139">Operator</span><span class="sxs-lookup"><span data-stu-id="099f7-139">Operator</span></span> | <span data-ttu-id="099f7-140">Beskrivning och användning</span><span class="sxs-lookup"><span data-stu-id="099f7-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="099f7-141">Filtrera en tabell till den delmängd rader som uppfyller ett predikat.</span><span class="sxs-lookup"><span data-stu-id="099f7-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="099f7-142">Skapa en tabell som aggregerar innehållet i indatatabellen.</span><span class="sxs-lookup"><span data-stu-id="099f7-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="099f7-143">Slå samman raderna i två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från varje tabell.</span><span class="sxs-lookup"><span data-stu-id="099f7-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="099f7-144">Returnera antalet poster i inmatningspostuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="099f7-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="099f7-145">Returnera de första N-posterna sorterade efter de angivna kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="099f7-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="099f7-146">Returnerar upp till det angivna antalet rader.</span><span class="sxs-lookup"><span data-stu-id="099f7-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="099f7-147">Markera de kolumner som du vill ta med, byta namn på eller släppa och infoga nya beräknade kolumner.</span><span class="sxs-lookup"><span data-stu-id="099f7-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="099f7-148">Skapa beräknade kolumner och lägg till dem i resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="099f7-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="099f7-149">Returnera en dynamisk (JSON) matris med uppsättningen distinkta värden som Uttr tar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="099f7-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="099f7-150">Hitta rader som matchar ett predikat i en uppsättning tabeller.</span><span class="sxs-lookup"><span data-stu-id="099f7-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="099f7-151">Om du vill se ett live-exempel på sådana operatorer kan du köra dem från **avsnittet Komma** igång på avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="099f7-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="099f7-152">Förstå datatyper</span><span class="sxs-lookup"><span data-stu-id="099f7-152">Understand data types</span></span>

<span data-ttu-id="099f7-153">Avancerad sökning stöder Kusto-datatyper, bland annat följande vanliga typer:</span><span class="sxs-lookup"><span data-stu-id="099f7-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="099f7-154">Datatyp</span><span class="sxs-lookup"><span data-stu-id="099f7-154">Data type</span></span> | <span data-ttu-id="099f7-155">Beskrivning och frågekonsekvenser</span><span class="sxs-lookup"><span data-stu-id="099f7-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="099f7-156">Data och tidsinformation som normalt representerar tidsstämplar för händelser.</span><span class="sxs-lookup"><span data-stu-id="099f7-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="099f7-157">Visa datumtidsformat som stöds</span><span class="sxs-lookup"><span data-stu-id="099f7-157">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="099f7-158">Teckensträng i UTF-8 inom enkla citattecken ( `'` ) eller dubbla citattecken ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="099f7-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="099f7-159">Läs mer om strängar</span><span class="sxs-lookup"><span data-stu-id="099f7-159">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="099f7-160">Den här datatypen stöder `true` eller `false` anger tillstånd.</span><span class="sxs-lookup"><span data-stu-id="099f7-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="099f7-161">Visa literaler och operatorer som stöds</span><span class="sxs-lookup"><span data-stu-id="099f7-161">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="099f7-162">32-bitars heltal</span><span class="sxs-lookup"><span data-stu-id="099f7-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="099f7-163">64-bitars heltal</span><span class="sxs-lookup"><span data-stu-id="099f7-163">64-bit integer</span></span> |

<span data-ttu-id="099f7-164">Mer information om dessa datatyper finns [i Kusto-skalära datatyper.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="099f7-164">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="099f7-165">Få hjälp medan du skriver frågor</span><span class="sxs-lookup"><span data-stu-id="099f7-165">Get help as you write queries</span></span>
<span data-ttu-id="099f7-166">Dra nytta av följande funktioner för att skriva frågor snabbare:</span><span class="sxs-lookup"><span data-stu-id="099f7-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="099f7-167">**Automatiska förslag – medan** du skriver frågor ger avancerad sökning förslag från IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="099f7-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="099f7-168">**Schematräd**– en schemarepresentation som innehåller listan med tabeller och deras kolumner visas bredvid ditt arbetsområde.</span><span class="sxs-lookup"><span data-stu-id="099f7-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="099f7-169">Hovra över ett objekt om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="099f7-169">For more information, hover over an item.</span></span> <span data-ttu-id="099f7-170">Dubbelklicka på ett objekt för att infoga det i frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="099f7-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="099f7-171">**[Schemareferens](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**– referens i portal med tabell- och kolumnbeskrivningar samt händelsetyper (värden) och `ActionType` exempelfrågor som stöds</span><span class="sxs-lookup"><span data-stu-id="099f7-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="099f7-172">Arbeta med flera frågor i redigeraren</span><span class="sxs-lookup"><span data-stu-id="099f7-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="099f7-173">Du kan använda frågeredigeraren och experimentera med flera frågor.</span><span class="sxs-lookup"><span data-stu-id="099f7-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="099f7-174">Så här använder du flera frågor:</span><span class="sxs-lookup"><span data-stu-id="099f7-174">To use multiple queries:</span></span>

- <span data-ttu-id="099f7-175">Avgränsa varje fråga med en tom rad.</span><span class="sxs-lookup"><span data-stu-id="099f7-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="099f7-176">Placera markören på någon del av en fråga för att välja den frågan innan du kör den.</span><span class="sxs-lookup"><span data-stu-id="099f7-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="099f7-177">Då körs endast den markerade frågan.</span><span class="sxs-lookup"><span data-stu-id="099f7-177">This will run only the selected query.</span></span> <span data-ttu-id="099f7-178">Om du vill köra en annan fråga flyttar du markören och väljer **Kör fråga.**</span><span class="sxs-lookup"><span data-stu-id="099f7-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Bild av frågeredigeraren med flera frågor](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="099f7-180">Använda exempelfrågor</span><span class="sxs-lookup"><span data-stu-id="099f7-180">Use sample queries</span></span>

<span data-ttu-id="099f7-181">I **avsnittet Komma** igång finns några enkla frågor med vanliga operatorer.</span><span class="sxs-lookup"><span data-stu-id="099f7-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="099f7-182">Prova att köra dessa frågor och göra små ändringar i dem.</span><span class="sxs-lookup"><span data-stu-id="099f7-182">Try running these queries and making small modifications to them.</span></span>

![Bild på en avancerad sökning](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="099f7-184">Förutom de grundläggande frågeexempelen kan du även komma åt delade frågor [för](advanced-hunting-shared-queries.md) specifika fall med hot på vis.</span><span class="sxs-lookup"><span data-stu-id="099f7-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="099f7-185">Utforska de delade frågorna till vänster på sidan eller lagringsplatsen för [GitHub-frågan.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="099f7-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="099f7-186">Dokumentation om frågespråk i Access</span><span class="sxs-lookup"><span data-stu-id="099f7-186">Access query language documentation</span></span>

<span data-ttu-id="099f7-187">Mer information om Kusto-frågespråk och operatorer som stöds finns i [dokumentationen för kustofrågans språk.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="099f7-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="099f7-188">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="099f7-188">Related topics</span></span>
- [<span data-ttu-id="099f7-189">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="099f7-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="099f7-190">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="099f7-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="099f7-191">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="099f7-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="099f7-192">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="099f7-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="099f7-193">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="099f7-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="099f7-194">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="099f7-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
