---
title: Avancerad jaktpraxis i Microsofts hotskydd
description: Lär dig hur du konstruerar snabba, effektiva och felfria hotjaktsfrågor när du använder avancerad jakt
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, undvika timeout, kommandorader, process-ID
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
ms.openlocfilehash: 9d7f6ee67e231ce7aa9bce1decc4de2f2d5a6d41
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929510"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="58461-104">Metodtips för avancerad jaktfråga</span><span class="sxs-lookup"><span data-stu-id="58461-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="58461-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="58461-105">**Applies to:**</span></span>
- <span data-ttu-id="58461-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="58461-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="58461-107">Optimera frågeprestanda</span><span class="sxs-lookup"><span data-stu-id="58461-107">Optimize query performance</span></span>
<span data-ttu-id="58461-108">Använd dessa rekommendationer för att få resultat snabbare och undvika timeout när du kör komplexa frågor:</span><span class="sxs-lookup"><span data-stu-id="58461-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="58461-109">När du provar nya `limit` frågor, använd alltid för att undvika extremt stora resultatuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="58461-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="58461-110">Du kan också först bedöma storleken på `count`resultatuppsättningen med .</span><span class="sxs-lookup"><span data-stu-id="58461-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="58461-111">Använd tidsfilter först.</span><span class="sxs-lookup"><span data-stu-id="58461-111">Use time filters first.</span></span> <span data-ttu-id="58461-112">Begränsa dina frågor till jämna dagar.</span><span class="sxs-lookup"><span data-stu-id="58461-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="58461-113">Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tidsfiltret.</span><span class="sxs-lookup"><span data-stu-id="58461-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="58461-114">Använd `has` operatorn `contains` över när du letar efter fullständiga tokens.</span><span class="sxs-lookup"><span data-stu-id="58461-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="58461-115">Titta i en viss kolumn i stället för att köra fulltextsökningar i alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="58461-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="58461-116">När du sammanfogar tabeller anger du tabellen med färre rader först.</span><span class="sxs-lookup"><span data-stu-id="58461-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="58461-117">`project`bara nödvändiga kolumner från tabeller som du har gått med i.</span><span class="sxs-lookup"><span data-stu-id="58461-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="58461-118">Mer information om hur du förbättrar frågeprestanda finns i [bästa praxis för Kusto-frågor](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="58461-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="58461-119">Frågetips och fallgropar</span><span class="sxs-lookup"><span data-stu-id="58461-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="58461-120">Frågor med process-ID</span><span class="sxs-lookup"><span data-stu-id="58461-120">Queries with process IDs</span></span>
<span data-ttu-id="58461-121">Process-ID (PID) återvinns i Windows och återanvänds för nya processer.</span><span class="sxs-lookup"><span data-stu-id="58461-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="58461-122">På egen hand kan de inte fungera som unika identifierare för specifika processer.</span><span class="sxs-lookup"><span data-stu-id="58461-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="58461-123">Om du vill få en unik identifierare för en process på en viss dator använder du process-ID:t tillsammans med processens skapandetid.</span><span class="sxs-lookup"><span data-stu-id="58461-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="58461-124">När du sammanfogar eller summerar data runt processer, `DeviceId` `DeviceName`inkludera kolumner för`ProcessId` maskinidentifieraren (antingen eller ), process-ID (eller `InitiatingProcessId`), och processens skapandetid (`ProcessCreationTime` eller `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="58461-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="58461-125">Följande exempelfråga hittar processer som kommer åt mer än 10 IP-adresser över port 445 (SMB), eventuellt genomsökning efter filresurser.</span><span class="sxs-lookup"><span data-stu-id="58461-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="58461-126">Exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="58461-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="58461-127">Frågan sammanfattas med `InitiatingProcessId` `InitiatingProcessCreationTime` båda och så att den tittar på en enda process, utan att blanda flera processer med samma process-ID.</span><span class="sxs-lookup"><span data-stu-id="58461-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="58461-128">Frågor med kommandorader</span><span class="sxs-lookup"><span data-stu-id="58461-128">Queries with command lines</span></span>

<span data-ttu-id="58461-129">Kommandorader kan variera.</span><span class="sxs-lookup"><span data-stu-id="58461-129">Command lines can vary.</span></span> <span data-ttu-id="58461-130">I förekommande fall filtrera på filnamn och gör suddig matchning.</span><span class="sxs-lookup"><span data-stu-id="58461-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="58461-131">Det finns många sätt att skapa en kommandorad för att utföra en uppgift.</span><span class="sxs-lookup"><span data-stu-id="58461-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="58461-132">En angripare kan till exempel referera till en bildfil med eller utan sökväg, utan filtillägg, använda miljövariabler eller med citattecken.</span><span class="sxs-lookup"><span data-stu-id="58461-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="58461-133">Dessutom kan angriparen också ändra ordningen på parametrar eller lägga till flera citattecken och blanksteg.</span><span class="sxs-lookup"><span data-stu-id="58461-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="58461-134">Om du vill skapa mer varaktiga frågor med kommandorader använder du följande metoder:</span><span class="sxs-lookup"><span data-stu-id="58461-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="58461-135">Identifiera kända processer (till exempel *net.exe* eller *psexec.exe)* genom att matcha i filnamnsfälten i stället för att filtrera i kommandoradsfältet.</span><span class="sxs-lookup"><span data-stu-id="58461-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="58461-136">När du frågar efter kommandoradsargument ska du inte leta efter en exakt matchning på flera orelaterade argument i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="58461-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="58461-137">Använd i stället reguljära uttryck eller använd flera separata operatorer.</span><span class="sxs-lookup"><span data-stu-id="58461-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="58461-138">Använd skiftläge okänsliga matchningar.</span><span class="sxs-lookup"><span data-stu-id="58461-138">Use case insensitive matches.</span></span> <span data-ttu-id="58461-139">Använd till `=~`exempel `in~`, `contains` och `==` `in`i stället för , och`contains_cs`</span><span class="sxs-lookup"><span data-stu-id="58461-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="58461-140">Om du vill minska DOS-kommandoradsfördunklingstekniker bör du överväga att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera på varandra följande blanksteg med ett enda blanksteg.</span><span class="sxs-lookup"><span data-stu-id="58461-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="58461-141">Observera att det finns mer komplexa DOS-fördunklingstekniker som kräver andra metoder, men dessa kan hjälpa till att ta itu med de vanligaste.</span><span class="sxs-lookup"><span data-stu-id="58461-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="58461-142">I följande exempel visas olika sätt att skapa en fråga som söker efter filen *net.exe* för att stoppa windows defender-brandväggen:</span><span class="sxs-lookup"><span data-stu-id="58461-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="58461-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="58461-143">Related topics</span></span>
- [<span data-ttu-id="58461-144">Avancerad jaktöversikt</span><span class="sxs-lookup"><span data-stu-id="58461-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58461-145">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="58461-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="58461-146">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="58461-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="58461-147">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="58461-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="58461-148">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="58461-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="58461-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="58461-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
