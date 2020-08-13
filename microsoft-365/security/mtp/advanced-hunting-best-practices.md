---
title: Avancerad jakt metod tips för Microsoft Threat Protection
description: Lär dig hur du skapar snabba, effektiva och problem med hotfrågor när du använder avancerad jakt
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, undvika tids gräns, kommando rader, process-ID
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
ms.openlocfilehash: f66b17fbdaaa58cf12bd0373d0fece59349c3a48
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649505"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="afe11-104">Metod tips för avancerad jakt frågor</span><span class="sxs-lookup"><span data-stu-id="afe11-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="afe11-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="afe11-105">**Applies to:**</span></span>
- <span data-ttu-id="afe11-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="afe11-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="afe11-107">Optimera frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="afe11-107">Optimize query performance</span></span>
<span data-ttu-id="afe11-108">Använd dessa rekommendationer för att få snabbare resultat och undvika tids gränser när du kör komplexa frågor:</span><span class="sxs-lookup"><span data-stu-id="afe11-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="afe11-109">När du försöker med nya frågor bör `limit` du alltid använda för att undvika extremt stora resultat mängder.</span><span class="sxs-lookup"><span data-stu-id="afe11-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="afe11-110">Du kan också börja med att bedöma storleken på resultatet som används `count` .</span><span class="sxs-lookup"><span data-stu-id="afe11-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="afe11-111">Använd tids filter först.</span><span class="sxs-lookup"><span data-stu-id="afe11-111">Use time filters first.</span></span> <span data-ttu-id="afe11-112">Det bästa är att begränsa dina frågor till ännu dagar.</span><span class="sxs-lookup"><span data-stu-id="afe11-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="afe11-113">Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tids filtret.</span><span class="sxs-lookup"><span data-stu-id="afe11-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="afe11-114">Använd `has` operatorn `contains` när du letar efter fullständiga token.</span><span class="sxs-lookup"><span data-stu-id="afe11-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="afe11-115">Leta i en viss kolumn i stället för att köra fullständig text ökning i alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="afe11-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="afe11-116">När du kopplar tabeller ska du ange tabellen med färre rader först.</span><span class="sxs-lookup"><span data-stu-id="afe11-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="afe11-117">`project`endast kolumner från tabeller som du har anslutit till.</span><span class="sxs-lookup"><span data-stu-id="afe11-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="afe11-118">För mer information om hur du förbättrar frågeresultatet kan du läsa [Kusto metod tips](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="afe11-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="afe11-119">Tips för frågor och fall GRO par</span><span class="sxs-lookup"><span data-stu-id="afe11-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="afe11-120">Frågor med process-ID: n</span><span class="sxs-lookup"><span data-stu-id="afe11-120">Queries with process IDs</span></span>
<span data-ttu-id="afe11-121">Process-ID: n återvinns i Windows och återanvänds för nya processer.</span><span class="sxs-lookup"><span data-stu-id="afe11-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="afe11-122">De kan inte fungera som unika identifierare för specifika processer.</span><span class="sxs-lookup"><span data-stu-id="afe11-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="afe11-123">Om du vill ha en unik identifierare för en process på en specifik dator använder du process-ID: t tillsammans med processen för skapande av process.</span><span class="sxs-lookup"><span data-stu-id="afe11-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="afe11-124">När du ansluter till eller sammanfattar data i processer inkluderar du kolumner för datorns ID (antingen `DeviceId` eller `DeviceName` ), process-ID ( `ProcessId` eller `InitiatingProcessId` ) och processens skapelse tid ( `ProcessCreationTime` eller `InitiatingProcessCreationTime` )</span><span class="sxs-lookup"><span data-stu-id="afe11-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="afe11-125">I följande exempel fråga hittas processer med åtkomst till fler än 10 IP-adresser över Port 445 (SMB), eventuellt genomsökning efter fil resurser.</span><span class="sxs-lookup"><span data-stu-id="afe11-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="afe11-126">Exempel fråga:</span><span class="sxs-lookup"><span data-stu-id="afe11-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="afe11-127">Frågan sammanfattar både efter båda `InitiatingProcessId` och `InitiatingProcessCreationTime` så att den ser ut på en enstaka gång, utan att flera processer med samma process-ID kan blandas.</span><span class="sxs-lookup"><span data-stu-id="afe11-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="afe11-128">Frågor med kommando rader</span><span class="sxs-lookup"><span data-stu-id="afe11-128">Queries with command lines</span></span>

<span data-ttu-id="afe11-129">Kommando rader kan variera.</span><span class="sxs-lookup"><span data-stu-id="afe11-129">Command lines can vary.</span></span> <span data-ttu-id="afe11-130">I tillämpliga fall filtrerar du efter fil namn och utför fuzzy-matchning.</span><span class="sxs-lookup"><span data-stu-id="afe11-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="afe11-131">Det finns många olika sätt att skapa en kommando rad för att utföra en uppgift.</span><span class="sxs-lookup"><span data-stu-id="afe11-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="afe11-132">En angripare kan till exempel referera till en bildfil med eller utan en sökväg, utan fil namns tillägg, med hjälp av miljövariabler eller med citat tecken.</span><span class="sxs-lookup"><span data-stu-id="afe11-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="afe11-133">Dessutom kan angriparen också ändra ordningen på parametrar eller lägga till flera citat tecken och blank steg.</span><span class="sxs-lookup"><span data-stu-id="afe11-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="afe11-134">Gör så här om du vill skapa fler beständiga frågor med kommando rader:</span><span class="sxs-lookup"><span data-stu-id="afe11-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="afe11-135">Identifiera kända processer (till exempel *net.exe* eller *psexec.exe*) genom att matcha fil namns fälten i stället för filtrering i kommando rads fältet.</span><span class="sxs-lookup"><span data-stu-id="afe11-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="afe11-136">Leta inte efter en exakt matchning på flera icke relaterade argument i en viss ordning när du frågar efter kommando rads argument.</span><span class="sxs-lookup"><span data-stu-id="afe11-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="afe11-137">Använd i stället vanliga uttryck eller Använd flera separata innehåller operatorer.</span><span class="sxs-lookup"><span data-stu-id="afe11-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="afe11-138">Använd Skift läges okänsliga träffar.</span><span class="sxs-lookup"><span data-stu-id="afe11-138">Use case insensitive matches.</span></span> <span data-ttu-id="afe11-139">Till exempel använda `=~` , `in~` och `contains` i stället för `==` , `in` och`contains_cs`</span><span class="sxs-lookup"><span data-stu-id="afe11-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="afe11-140">Om du vill minska DOS-obfuscation metoder kan du ta bort citat tecken, ersätta kommatecken med blank steg och ersätta flera sammanhängande blank steg med ett enda blank steg.</span><span class="sxs-lookup"><span data-stu-id="afe11-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="afe11-141">Observera att det finns mer komplexa DOS obfuscation-tekniker som kräver andra metoder, men dessa kan hjälpa till med att adressera de vanligaste.</span><span class="sxs-lookup"><span data-stu-id="afe11-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="afe11-142">Följande exempel visar olika sätt att skapa en fråga som söker efter filen *net.exe* att stoppa Windows Defender Firewall-tjänsten:</span><span class="sxs-lookup"><span data-stu-id="afe11-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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
## <a name="related-topics"></a><span data-ttu-id="afe11-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="afe11-143">Related topics</span></span>
- [<span data-ttu-id="afe11-144">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="afe11-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="afe11-145">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="afe11-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="afe11-146">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="afe11-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="afe11-147">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="afe11-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="afe11-148">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="afe11-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="afe11-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="afe11-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
