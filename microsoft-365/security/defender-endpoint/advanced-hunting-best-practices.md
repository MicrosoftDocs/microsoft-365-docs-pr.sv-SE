---
title: Metodtips för frågor för avancerad sökning
description: Lär dig att konstruera snabba, effektiva och felfria sökning efter hot när du använder avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499262"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="90cb8-104">Avancerade metodtips för sökningsfrågor</span><span class="sxs-lookup"><span data-stu-id="90cb8-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="90cb8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="90cb8-105">**Applies to:**</span></span>
- [<span data-ttu-id="90cb8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="90cb8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="90cb8-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="90cb8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="90cb8-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="90cb8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="90cb8-109">Optimera frågeprestanda</span><span class="sxs-lookup"><span data-stu-id="90cb8-109">Optimize query performance</span></span>

<span data-ttu-id="90cb8-110">Använd de här rekommendationerna för att få resultat snabbare och undvika tidsgränser när du kör komplexa frågor.</span><span class="sxs-lookup"><span data-stu-id="90cb8-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="90cb8-111">Undvik alltid extremt stora resultatuppsättningar när du `limit` försöker skapa nya frågor.</span><span class="sxs-lookup"><span data-stu-id="90cb8-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="90cb8-112">Du kan också börja med att bedöma storleken på resultatuppsättningen med hjälp av `count` .</span><span class="sxs-lookup"><span data-stu-id="90cb8-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="90cb8-113">Använd tidsfilter först.</span><span class="sxs-lookup"><span data-stu-id="90cb8-113">Use time filters first.</span></span> <span data-ttu-id="90cb8-114">Under idealiska tider bör du begränsa dina frågor till sju dagar.</span><span class="sxs-lookup"><span data-stu-id="90cb8-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="90cb8-115">Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tidsfiltret.</span><span class="sxs-lookup"><span data-stu-id="90cb8-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="90cb8-116">Använd `has` operatorn över `contains` när du letar efter fullständiga token.</span><span class="sxs-lookup"><span data-stu-id="90cb8-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="90cb8-117">Titta i en specifik kolumn i stället för att köra fullständiga textsökningar i alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="90cb8-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="90cb8-118">När du sammanfogar tabeller anger du först tabellen med färre rader.</span><span class="sxs-lookup"><span data-stu-id="90cb8-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="90cb8-119">`project` Endast kolumner från tabeller som du har anslutit till är nödvändiga.</span><span class="sxs-lookup"><span data-stu-id="90cb8-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="90cb8-120">Mer vägledning om hur du förbättrar frågeprestanda finns [i Metodtips för Kusto-frågor.](https://docs.microsoft.com/azure/kusto/query/best-practices)</span><span class="sxs-lookup"><span data-stu-id="90cb8-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="90cb8-121">Frågetips och fallgropar</span><span class="sxs-lookup"><span data-stu-id="90cb8-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="90cb8-122">Frågor med process-IDs</span><span class="sxs-lookup"><span data-stu-id="90cb8-122">Queries with process IDs</span></span>

<span data-ttu-id="90cb8-123">Process-ID:n (PID) återanvänds i Windows och återanvänds för nya processer.</span><span class="sxs-lookup"><span data-stu-id="90cb8-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="90cb8-124">De kan på egen hand inte fungera som unika identifierare för specifika processer.</span><span class="sxs-lookup"><span data-stu-id="90cb8-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="90cb8-125">Om du vill få en unik identifierare för en process på en viss enhet kan du använda process-ID:t tillsammans med den tid då processen skapades.</span><span class="sxs-lookup"><span data-stu-id="90cb8-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="90cb8-126">När du sammanfogar eller sammanfattar data runt processer tar du med kolumner för enhetsidentifieraren (antingen eller `DeviceId` `DeviceName` ), process-ID ( eller ) och tiden då processen skapades `ProcessId` ( eller `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="90cb8-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="90cb8-127">Följande exempelfråga hittar processer som har åtkomst till fler än 10 IP-adresser via port 445 (SMB), eventuellt genomsökning efter filresurser.</span><span class="sxs-lookup"><span data-stu-id="90cb8-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="90cb8-128">Frågan sammanfattas av båda och så att den tittar på en enda `InitiatingProcessId` `InitiatingProcessCreationTime` process, utan att blanda flera processer med samma process-ID.</span><span class="sxs-lookup"><span data-stu-id="90cb8-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="90cb8-129">Frågor med kommandorader</span><span class="sxs-lookup"><span data-stu-id="90cb8-129">Queries with command lines</span></span>

<span data-ttu-id="90cb8-130">Kommandorader kan variera.</span><span class="sxs-lookup"><span data-stu-id="90cb8-130">Command lines can vary.</span></span> <span data-ttu-id="90cb8-131">I förekommande fall kan du filtrera fram filnamnen och göra fuzzy-matchningen.</span><span class="sxs-lookup"><span data-stu-id="90cb8-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="90cb8-132">Det finns flera sätt att skapa en kommandorad för att utföra en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="90cb8-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="90cb8-133">En attackerare kan till exempel referera till en bildfil med eller utan en sökväg, utan filnamnstillägg, med hjälp av miljövariabler eller med citattecken.</span><span class="sxs-lookup"><span data-stu-id="90cb8-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="90cb8-134">Dessutom kan attackerarna ändra ordning på parametrarna eller lägga till flera citattecken och blanksteg.</span><span class="sxs-lookup"><span data-stu-id="90cb8-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="90cb8-135">Så här skapar du mer beständiga frågor med hjälp av kommandorader:</span><span class="sxs-lookup"><span data-stu-id="90cb8-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="90cb8-136">Identifiera de kända processerna (till *exempelnet.exe* eller *psexec.exe)* genom att matcha i filnamnsfälten, i stället för att filtrera på kommandoradsfältet.</span><span class="sxs-lookup"><span data-stu-id="90cb8-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="90cb8-137">Vid sökning efter kommandoradsargument bör du inte söka efter en exakt matchning för flera orelaterade argument i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="90cb8-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="90cb8-138">I stället kan du använda reguljära uttryck eller använda flera separata operatorer.</span><span class="sxs-lookup"><span data-stu-id="90cb8-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="90cb8-139">Använd fallkänsliga matchningar.</span><span class="sxs-lookup"><span data-stu-id="90cb8-139">Use case insensitive matches.</span></span> <span data-ttu-id="90cb8-140">Använd till exempel `=~` , och i stället för `in~` `contains` `==` `in` och `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="90cb8-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="90cb8-141">Överväg att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera efterföljande blanksteg med ett enda blanksteg för att minimera DOS-teknikerna för att begränsa doS-obfuseringsteknik.</span><span class="sxs-lookup"><span data-stu-id="90cb8-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="90cb8-142">Observera att det finns mer komplexa DOS-metoder som kräver andra metoder, men dessa kan hjälpa dig att lösa de vanligaste.</span><span class="sxs-lookup"><span data-stu-id="90cb8-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="90cb8-143">Följande exempel visar olika sätt att skapa en fråga som söker efter filen eller *net.exe* för att stoppa Windows Defender-brandväggstjänsten:</span><span class="sxs-lookup"><span data-stu-id="90cb8-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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

> <span data-ttu-id="90cb8-144">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="90cb8-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="90cb8-145">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="90cb8-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="90cb8-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="90cb8-146">Related topics</span></span>

- [<span data-ttu-id="90cb8-147">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="90cb8-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="90cb8-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="90cb8-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="90cb8-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="90cb8-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="90cb8-150">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="90cb8-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="90cb8-151">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="90cb8-151">Custom detections overview</span></span>](overview-custom-detections.md)
