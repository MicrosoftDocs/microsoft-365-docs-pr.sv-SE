---
title: Lär dig det avancerade jaktfrågespråket i Microsoft Threat Protection
description: Skapa din första hotjaktsfråga och lär dig mer om vanliga operatörer och andra aspekter av det avancerade jaktfrågespråket
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, språk, lär dig, första frågan, telemetri, händelser, telemetri, anpassade upptäckter, schema, kusto, operatörer, datatyper, powershell ladda ned, frågeexempel
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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929002"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="e9f39-104">Lär dig det avancerade jaktfrågespråket</span><span class="sxs-lookup"><span data-stu-id="e9f39-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="e9f39-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="e9f39-105">**Applies to:**</span></span>
- <span data-ttu-id="e9f39-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="e9f39-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e9f39-107">Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="e9f39-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="e9f39-108">Du kan använda Kusto-syntax och operatorer för att konstruera frågor som hittar information i [schemat](advanced-hunting-schema-tables.md) som är särskilt strukturerat för avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="e9f39-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="e9f39-109">Om du vill förstå dessa begrepp bättre kör du din första fråga.</span><span class="sxs-lookup"><span data-stu-id="e9f39-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="e9f39-110">Prova din första fråga</span><span class="sxs-lookup"><span data-stu-id="e9f39-110">Try your first query</span></span>

<span data-ttu-id="e9f39-111">I Microsoft 365 security center går du till **Jakt** för att köra din första fråga.</span><span class="sxs-lookup"><span data-stu-id="e9f39-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="e9f39-112">Använd följande exempel:</span><span class="sxs-lookup"><span data-stu-id="e9f39-112">Use the following example:</span></span>

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

<span data-ttu-id="e9f39-113">Så här kommer det att se ut i avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="e9f39-113">This is how it will look like in advanced hunting.</span></span>

![Bild av avancerad jaktfråga för Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="e9f39-115">En kort kommentar har lagts till i början av frågan för att beskriva vad den är till för.</span><span class="sxs-lookup"><span data-stu-id="e9f39-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="e9f39-116">Detta hjälper om du senare bestämmer dig för att spara frågan och dela den med andra i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="e9f39-117">Själva frågan börjar vanligtvis med ett tabellnamn följt av en`|`serie element som startats av en pipe ( ).</span><span class="sxs-lookup"><span data-stu-id="e9f39-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="e9f39-118">I det här exemplet börjar vi med `DeviceProcessEvents` att `DeviceNetworkEvents`skapa en union med två tabeller och lägga till rörelement efter behov.</span><span class="sxs-lookup"><span data-stu-id="e9f39-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="e9f39-119">Det första rörelementet är ett tidsfilter som har scopets till de föregående sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="e9f39-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="e9f39-120">Om du håller tidsintervallet så smalt som möjligt säkerställer du att frågor presterar bra, returnerar hanterbara resultat och inte time out.</span><span class="sxs-lookup"><span data-stu-id="e9f39-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="e9f39-121">Tidsintervallet följs omedelbart av en sökning efter processfilnamn som representerar PowerShell-programmet.</span><span class="sxs-lookup"><span data-stu-id="e9f39-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="e9f39-122">Därefter söker frågan efter strängar på kommandorader som vanligtvis används för att hämta filer med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9f39-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="e9f39-123">Nu när frågan tydligt identifierar de data du vill hitta kan du lägga till element som definierar hur resultaten ser ut.</span><span class="sxs-lookup"><span data-stu-id="e9f39-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="e9f39-124">`project`returnerar specifika `top` kolumner och begränsar antalet resultat, vilket säkerställer att resultaten är välformaterade och någorlunda stora och lätta att bearbeta.</span><span class="sxs-lookup"><span data-stu-id="e9f39-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="e9f39-125">Klicka på **Kör fråga** om du vill se resultatet.</span><span class="sxs-lookup"><span data-stu-id="e9f39-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="e9f39-126">Välj ikonen expandera längst upp till höger i frågeredigeraren för att fokusera på jaktfrågan och resultaten.</span><span class="sxs-lookup"><span data-stu-id="e9f39-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Bild av utöka kontrollen i den avancerade jaktfråge redigeraren](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="e9f39-128">Lär dig vanliga frågeoperatorer för avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e9f39-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="e9f39-129">Nu när du har kört din första fråga och har en allmän uppfattning om dess komponenter, är det dags att backa lite och lära sig grunderna.</span><span class="sxs-lookup"><span data-stu-id="e9f39-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="e9f39-130">Kusto-frågespråket som används av avancerad jakt stöder en rad operatörer, inklusive följande vanliga.</span><span class="sxs-lookup"><span data-stu-id="e9f39-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="e9f39-131">Operatör</span><span class="sxs-lookup"><span data-stu-id="e9f39-131">Operator</span></span> | <span data-ttu-id="e9f39-132">Beskrivning och användning</span><span class="sxs-lookup"><span data-stu-id="e9f39-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="e9f39-133">Filtrera en tabell till den delmängd av rader som uppfyller ett predikat.</span><span class="sxs-lookup"><span data-stu-id="e9f39-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="e9f39-134">Skapa en tabell som sammanställer innehållet i indatatabellen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="e9f39-135">Sammanfoga raderna med två tabeller för att skapa en ny tabell genom att matcha värden för de angivna kolumnerna från varje tabell.</span><span class="sxs-lookup"><span data-stu-id="e9f39-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="e9f39-136">Returnera antalet poster i indatapostuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="e9f39-137">Returnera de första N-posterna sorterade efter de angivna kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="e9f39-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="e9f39-138">Returnera upp till angivet antal rader.</span><span class="sxs-lookup"><span data-stu-id="e9f39-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="e9f39-139">Markera de kolumner som ska inkluderas, byta namn på eller släppa och infoga nya beräknade kolumner.</span><span class="sxs-lookup"><span data-stu-id="e9f39-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="e9f39-140">Skapa beräknade kolumner och lägg till dem i resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="e9f39-141">Returnera en dynamisk (JSON) matris för uppsättningen distinkta värden som Uttr tar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="e9f39-142">Hitta rader som matchar ett predikat över en uppsättning tabeller.</span><span class="sxs-lookup"><span data-stu-id="e9f39-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="e9f39-143">Om du vill se ett levande exempel på dessa operatörer kör du dem från avsnittet **Kom igång** i avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="e9f39-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="e9f39-144">Förstå datatyper och deras frågesyntax implicationer</span><span class="sxs-lookup"><span data-stu-id="e9f39-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="e9f39-145">Uppgifter i avancerade jakttabeller är i allmänhet indelade i följande datatyper.</span><span class="sxs-lookup"><span data-stu-id="e9f39-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="e9f39-146">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e9f39-146">Data type</span></span> | <span data-ttu-id="e9f39-147">Beskrivnings- och frågekonsekvenser</span><span class="sxs-lookup"><span data-stu-id="e9f39-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="e9f39-148">Data- och tidsinformation som vanligtvis representerar händelsetidsstämplar</span><span class="sxs-lookup"><span data-stu-id="e9f39-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="e9f39-149">Teckensträng</span><span class="sxs-lookup"><span data-stu-id="e9f39-149">Character string</span></span> |
| `bool` | <span data-ttu-id="e9f39-150">Sant eller falskt</span><span class="sxs-lookup"><span data-stu-id="e9f39-150">True or false</span></span> |
| `int` | <span data-ttu-id="e9f39-151">32-bitars numeriskt värde</span><span class="sxs-lookup"><span data-stu-id="e9f39-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="e9f39-152">64-bitars numeriskt värde</span><span class="sxs-lookup"><span data-stu-id="e9f39-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="e9f39-153">Använda exempelfrågor</span><span class="sxs-lookup"><span data-stu-id="e9f39-153">Use sample queries</span></span>

<span data-ttu-id="e9f39-154">Avsnittet **Kom igång** innehåller några enkla frågor med vanliga operatorer.</span><span class="sxs-lookup"><span data-stu-id="e9f39-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="e9f39-155">Prova att köra dessa frågor och göra små ändringar i dem.</span><span class="sxs-lookup"><span data-stu-id="e9f39-155">Try running these queries and making small modifications to them.</span></span>

![Bild på avancerat jaktfönster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="e9f39-157">Förutom de grundläggande frågeexemplen kan du också komma åt delade frågor för specifika [hotjaktsscenarier.](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="e9f39-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="e9f39-158">Utforska de delade frågorna till vänster på sidan eller GitHub-frågedatabasen.</span><span class="sxs-lookup"><span data-stu-id="e9f39-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="e9f39-159">Dokumentation för åtkomst till frågespråk</span><span class="sxs-lookup"><span data-stu-id="e9f39-159">Access query language documentation</span></span>

<span data-ttu-id="e9f39-160">Mer information om Kusto-frågespråk och operatörer som stöds finns i [Kusto-frågespråkdokumentation](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="e9f39-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9f39-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e9f39-161">Related topics</span></span>
- [<span data-ttu-id="e9f39-162">Avancerad jaktöversikt</span><span class="sxs-lookup"><span data-stu-id="e9f39-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9f39-163">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="e9f39-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e9f39-164">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="e9f39-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e9f39-165">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="e9f39-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e9f39-166">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="e9f39-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e9f39-167">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="e9f39-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
