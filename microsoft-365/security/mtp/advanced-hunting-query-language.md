---
title: Lär dig mer om det avancerade frågespråket för jakt i Microsoft Threat Protection
description: Skapa din första hot-fråga och lär dig mer om vanliga operatörer och andra aspekter av det avancerade frågespråket
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, språk, lära sig, första frågan, telemetri, händelser, telemetri, anpassade identifieringar, schema, kusto, operatorer, data typer, PowerShell-nedladdning, exempel på frågor
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
ms.openlocfilehash: 64f0b19cfd9588e975b06cb43ca73270b00c5e26
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649397"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="28109-104">Lär dig mer om det avancerade frågespråket</span><span class="sxs-lookup"><span data-stu-id="28109-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="28109-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="28109-105">**Applies to:**</span></span>
- <span data-ttu-id="28109-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="28109-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="28109-107">Avancerad jakt är baserat på [Kusto frågespråk](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="28109-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="28109-108">Du kan använda Kusto syntax och operatorer för att skapa frågor som visar information i det [schema](advanced-hunting-schema-tables.md) som är specifikt strukturerade för avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="28109-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="28109-109">Kör den första frågan för att förstå de här begreppen bättre.</span><span class="sxs-lookup"><span data-stu-id="28109-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="28109-110">Prova den första frågan</span><span class="sxs-lookup"><span data-stu-id="28109-110">Try your first query</span></span>

<span data-ttu-id="28109-111">I Microsoft 365 säkerhets Center går du till **jakt** för att köra den första frågan.</span><span class="sxs-lookup"><span data-stu-id="28109-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="28109-112">Använd följande exempel:</span><span class="sxs-lookup"><span data-stu-id="28109-112">Use the following example:</span></span>

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

<span data-ttu-id="28109-113">Så här kommer det att se ut i avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="28109-113">This is how it will look like in advanced hunting.</span></span>

![Bild av en avancerad jakt fråga i Microsoft Threat Protection](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="28109-115">Beskriv frågan och ange vilka tabeller som ska sökas igenom</span><span class="sxs-lookup"><span data-stu-id="28109-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="28109-116">En kort kommentar har lagts till i början av frågan för att beskriva vad den är för.</span><span class="sxs-lookup"><span data-stu-id="28109-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="28109-117">Det här hjälper om du senare bestämmer dig för att spara frågan och dela den med andra i din organisation.</span><span class="sxs-lookup"><span data-stu-id="28109-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="28109-118">Frågan börjar normalt med ett tabell namn följt av en serie element som startas av ett vertikalstreck ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="28109-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="28109-119">I det här exemplet börjar vi med att skapa en union av två tabeller `DeviceProcessEvents` och `DeviceNetworkEvents` lägga till piped-element efter behov.</span><span class="sxs-lookup"><span data-stu-id="28109-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="28109-120">Ange tidsintervall</span><span class="sxs-lookup"><span data-stu-id="28109-120">Set the time range</span></span>
<span data-ttu-id="28109-121">Det första piped-elementet är ett tids filter som är begränsat till de föregående sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="28109-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="28109-122">Om du vill att tids området ska vara så smalt som möjligt ser du till att frågor fungerar bra, returnerar hanterbara resultat och inte tids gräns.</span><span class="sxs-lookup"><span data-stu-id="28109-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="28109-123">Kontrol lera specifika processer</span><span class="sxs-lookup"><span data-stu-id="28109-123">Check specific processes</span></span>
<span data-ttu-id="28109-124">Tidsintervallet följs omedelbart av en sökning efter process fil namn som representerar PowerShell-programmet.</span><span class="sxs-lookup"><span data-stu-id="28109-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="28109-125">Sök efter specifika kommando strängar</span><span class="sxs-lookup"><span data-stu-id="28109-125">Search for specific command strings</span></span>
<span data-ttu-id="28109-126">Därefter söker frågan efter strängar i kommando rader som vanligt vis används för att ladda ned filer med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28109-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="28109-127">Anpassa resultat kolumner och längd</span><span class="sxs-lookup"><span data-stu-id="28109-127">Customize result columns and length</span></span> 
<span data-ttu-id="28109-128">Nu när frågan tydligt identifierar de data som du vill hitta kan du lägga till element som definierar hur resultatet ser ut.</span><span class="sxs-lookup"><span data-stu-id="28109-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="28109-129">`project`Returnerar specifika kolumner och `top` begränsar antalet resultat.</span><span class="sxs-lookup"><span data-stu-id="28109-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="28109-130">Dessa operatörer ser till att resultaten är välformaterade och rimligt stora och lätta att bearbeta.</span><span class="sxs-lookup"><span data-stu-id="28109-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="28109-131">Klicka på **Kör fråga** för att visa resultatet.</span><span class="sxs-lookup"><span data-stu-id="28109-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="28109-132">Välj ikonen Expandera längst upp till höger i Frågeredigeraren för att fokusera på frågan och resultaten.</span><span class="sxs-lookup"><span data-stu-id="28109-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Bild av kontrollen Expand i den avancerade Frågeredigeraren](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="28109-134">Du kan visa frågeresultat som diagram och snabbt justera filter.</span><span class="sxs-lookup"><span data-stu-id="28109-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="28109-135">[Läs mer om hur du arbetar med frågeresultat](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="28109-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="28109-136">Lär dig mer om vanliga fråge operatörer för avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="28109-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="28109-137">Nu när du har kört den första frågan och har en allmän uppfattning om dess komponenter är det dags att gå tillbaka lite bit och lära dig grunderna.</span><span class="sxs-lookup"><span data-stu-id="28109-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="28109-138">Kusto Query-språk som används i Advanced jakt har stöd för en rad operatörer, bland annat följande.</span><span class="sxs-lookup"><span data-stu-id="28109-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="28109-139">Ansvaret</span><span class="sxs-lookup"><span data-stu-id="28109-139">Operator</span></span> | <span data-ttu-id="28109-140">Beskrivning och användning</span><span class="sxs-lookup"><span data-stu-id="28109-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="28109-141">Filtrera en tabell till den del av rader som uppfyller ett predikat.</span><span class="sxs-lookup"><span data-stu-id="28109-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="28109-142">Skapa en tabell som aggregerar innehållet i inmatnings tabellen.</span><span class="sxs-lookup"><span data-stu-id="28109-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="28109-143">Sammanfoga raderna i två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från respektive tabell.</span><span class="sxs-lookup"><span data-stu-id="28109-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="28109-144">Returnera antalet poster i Indataposten.</span><span class="sxs-lookup"><span data-stu-id="28109-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="28109-145">Returnera de första N posterna sorterade efter de angivna kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="28109-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="28109-146">Gå tillbaka till angivet antal rader.</span><span class="sxs-lookup"><span data-stu-id="28109-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="28109-147">Markera kolumnerna som du vill ta med, byta namn på eller ta bort och infoga nya beräknade kolumner.</span><span class="sxs-lookup"><span data-stu-id="28109-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="28109-148">Skapa beräknade kolumner och Lägg till dem i resultatet.</span><span class="sxs-lookup"><span data-stu-id="28109-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="28109-149">Returnera en dynamisk (JSON) matris av uppsättningen med distinkta värden som uttryck används i gruppen.</span><span class="sxs-lookup"><span data-stu-id="28109-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="28109-150">Hitta rader som matchar ett predikat i en uppsättning tabeller.</span><span class="sxs-lookup"><span data-stu-id="28109-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="28109-151">Om du vill se ett exempel på dessa operatörer kan du köra det från avsnittet **komma igång** i avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="28109-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="28109-152">Förstå data typer och deras frågeresultat</span><span class="sxs-lookup"><span data-stu-id="28109-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="28109-153">Data i de avancerade jakt tabellerna klassificeras normalt i följande data typer.</span><span class="sxs-lookup"><span data-stu-id="28109-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="28109-154">Datatyp</span><span class="sxs-lookup"><span data-stu-id="28109-154">Data type</span></span> | <span data-ttu-id="28109-155">Beskrivningar och frågor</span><span class="sxs-lookup"><span data-stu-id="28109-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="28109-156">Data-och tidsinformation som vanligt vis representerar tids stämplingar</span><span class="sxs-lookup"><span data-stu-id="28109-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="28109-157">Tecken sträng</span><span class="sxs-lookup"><span data-stu-id="28109-157">Character string</span></span> |
| `bool` | <span data-ttu-id="28109-158">Sant eller falskt</span><span class="sxs-lookup"><span data-stu-id="28109-158">True or false</span></span> |
| `int` | <span data-ttu-id="28109-159">32-bitars numeriskt värde</span><span class="sxs-lookup"><span data-stu-id="28109-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="28109-160">64-bitars numeriskt värde</span><span class="sxs-lookup"><span data-stu-id="28109-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="28109-161">Få hjälp medan du skriver frågor</span><span class="sxs-lookup"><span data-stu-id="28109-161">Get help as you write queries</span></span>
<span data-ttu-id="28109-162">Dra nytta av följande funktioner när du vill skriva frågor snabbare:</span><span class="sxs-lookup"><span data-stu-id="28109-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="28109-163">**Autoföreslå** – när du skriver frågor kan du med hjälp av en avancerad jakt förslag från IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="28109-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="28109-164">**Schema träd** – en schema representation som innehåller listan med tabeller och deras kolumner visas bredvid arbets ytan.</span><span class="sxs-lookup"><span data-stu-id="28109-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="28109-165">För mer information, Hovra över ett objekt.</span><span class="sxs-lookup"><span data-stu-id="28109-165">For more information, hover over an item.</span></span> <span data-ttu-id="28109-166">Dubbelklicka på ett objekt om du vill infoga det i Frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="28109-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="28109-167">**[Schema referens](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – i-Portal referens med tabell-och kolumn beskrivningar samt de händelse typer som stöds `ActionType` och urvals frågor</span><span class="sxs-lookup"><span data-stu-id="28109-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="28109-168">Arbeta med flera frågor i redigeraren</span><span class="sxs-lookup"><span data-stu-id="28109-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="28109-169">Frågeredigeraren kan fungera som en borttagningsgest för att experimentera med flera frågor.</span><span class="sxs-lookup"><span data-stu-id="28109-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="28109-170">Så här använder du flera frågor:</span><span class="sxs-lookup"><span data-stu-id="28109-170">To use multiple queries:</span></span>

- <span data-ttu-id="28109-171">Avgränsa varje fråga med en tom rad.</span><span class="sxs-lookup"><span data-stu-id="28109-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="28109-172">Placera markören på en del av en fråga för att välja frågan innan den körs.</span><span class="sxs-lookup"><span data-stu-id="28109-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="28109-173">Detta kommer bara att köra den valda frågan.</span><span class="sxs-lookup"><span data-stu-id="28109-173">This will run only the selected query.</span></span> <span data-ttu-id="28109-174">Om du vill köra en ny fråga flyttar du markören i enlighet med den och väljer **Kör fråga**.</span><span class="sxs-lookup"><span data-stu-id="28109-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Bild av Frågeredigeraren med flera frågor](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="28109-176">Använda exempel frågor</span><span class="sxs-lookup"><span data-stu-id="28109-176">Use sample queries</span></span>

<span data-ttu-id="28109-177">Avsnittet **komma igång** innehåller några enkla frågor med vanliga operatorer.</span><span class="sxs-lookup"><span data-stu-id="28109-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="28109-178">Prova att köra de här frågorna och gör små ändringar i dem.</span><span class="sxs-lookup"><span data-stu-id="28109-178">Try running these queries and making small modifications to them.</span></span>

![Bild av fönstret för avancerad jakt](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="28109-180">Förutom de grundläggande fråge exemplen kan du även komma åt [delade frågor](advanced-hunting-shared-queries.md) för speciella scenarier med hot.</span><span class="sxs-lookup"><span data-stu-id="28109-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="28109-181">Utforska de delade frågorna på vänster sida av sidan eller i GitHub.</span><span class="sxs-lookup"><span data-stu-id="28109-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="28109-182">Dokumentation för Access-frågespråk</span><span class="sxs-lookup"><span data-stu-id="28109-182">Access query language documentation</span></span>

<span data-ttu-id="28109-183">Mer information om Kusto-frågespråk och operatorer som stöds finns i [dokumentationen om Kusto-språk](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="28109-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="28109-184">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="28109-184">Related topics</span></span>
- [<span data-ttu-id="28109-185">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="28109-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="28109-186">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="28109-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="28109-187">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="28109-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="28109-188">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="28109-188">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="28109-189">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="28109-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="28109-190">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="28109-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
