---
title: Avancerade metodtips för sökning i Microsoft 365 Defender
description: Lär dig hur du skapar snabba, effektiva och felfria hotförfrågningar med avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process-id, optimize, best practice, parse, join, summarize
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
ms.openlocfilehash: ae2e7fb960dd8ce2a42ce62fe0b8da7675e00ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228381"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="e5f2f-104">Avancerade metodtips för sökningsfrågor</span><span class="sxs-lookup"><span data-stu-id="e5f2f-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e5f2f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e5f2f-105">**Applies to:**</span></span>
- <span data-ttu-id="e5f2f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5f2f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e5f2f-107">Använd de här rekommendationerna för att få resultat snabbare och undvika tidsgränser när du kör komplexa frågor.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="e5f2f-108">Mer vägledning om hur du förbättrar frågeprestanda finns [i Metodtips för Kusto-frågor.](/azure/kusto/query/best-practices)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="e5f2f-109">Förstå kvoter för CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="e5f2f-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="e5f2f-110">Beroende på klientorganisationens storlek har varje klientorganisation tillgång till en viss mängd CPU-resurser som tilldelats för avancerade sökfrågor.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="e5f2f-111">Detaljerad information om olika tjänstbegränsningar finns [i mer information om avancerade kvoter för sökning och användningsparametrar.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="e5f2f-112">Kunder som kör flera frågor regelbundet bör spåra förbrukning och använda optimeringsvägledningen i den här artikeln för att minimera avbrottet som ett resultat av att kvoter eller användningsparametrar överskrids.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="e5f2f-113">Allmänna optimeringstips</span><span class="sxs-lookup"><span data-stu-id="e5f2f-113">General optimization tips</span></span>

- <span data-ttu-id="e5f2f-114">**Storlek på nya frågor –** Om du misstänker att en fråga kommer att returnera en stor resultatuppsättning bör du utvärdera den först med hjälp av [antal-operatorn](/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="e5f2f-115">Använd [begränsningen](/azure/data-explorer/kusto/query/limitoperator) eller dess synonym `take` för att undvika stora resultatuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="e5f2f-116">**Använda filter** tidigt – Använd tidsfilter och andra filter för att minska datauppsättningen, särskilt innan du använder omvandlings- och parsningsfunktioner, t.ex. [understräng()](/azure/data-explorer/kusto/query/substringfunction), [ersätt()](/azure/data-explorer/kusto/query/replacefunction), [rensa()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction) [eller parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="e5f2f-117">I exemplet nedan används tolkningsfunktionen [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) när filtreringsoperatorer har minskat antalet poster.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="e5f2f-118">**Har beats innehåller .** Du kan undvika att söka efter understrängar i ord i onödan genom att använda `has` operatorn i stället för `contains` .</span><span class="sxs-lookup"><span data-stu-id="e5f2f-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="e5f2f-119">Lär dig mer om strängoperatorer</span><span class="sxs-lookup"><span data-stu-id="e5f2f-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="e5f2f-120">**Titta i specifika kolumner –** Leta i en specifik kolumn i stället för att köra en fullständig textsökning i alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="e5f2f-121">Använd inte för `*` att kontrollera alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="e5f2f-122">**Case-sensitive for speed**– Case-sensitive searches are more specific and generally more performant.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="e5f2f-123">Namnen på de [case-känsliga strängoperatorer](/azure/data-explorer/kusto/query/datatypes-string-operators)som exempelvis `has_cs` och , vanligtvis slutar med `contains_cs` `_cs` .</span><span class="sxs-lookup"><span data-stu-id="e5f2f-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="e5f2f-124">Du kan också använda operatorn case-sensitive equals `==` i stället för `=~` .</span><span class="sxs-lookup"><span data-stu-id="e5f2f-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="e5f2f-125">**Tolka, extrahera inte**– När det är möjligt använder du [parsoperatorn](/azure/data-explorer/kusto/query/parseoperator) eller en tolkningsfunktion som [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="e5f2f-126">Undvik `matches regex` strängoperatorn eller [extrahera()-funktionen,](/azure/data-explorer/kusto/query/extractfunction)som båda använder reguljära uttryck.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="e5f2f-127">Reservera användningen av reguljära uttryck för mer komplexa scenarier.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="e5f2f-128">Läs mer om tolkningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e5f2f-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="e5f2f-129">**Filtrera tabeller och inte** uttryck – Filtrera inte efter en beräknad kolumn om du kan filtrera på en tabellkolumn.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="e5f2f-130">**Inga termer med tre tecken**– Undvik att jämföra eller filtrera med hjälp av termer med tre tecken eller färre.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="e5f2f-131">Termerna indexeras inte och för att de ska matchas krävs fler resurser.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="e5f2f-132">**Project selektivt**– Gör resultatet enklare att förstå genom att projicera endast de kolumner du behöver.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="e5f2f-133">Att projicera specifika kolumner innan [du kör koppling](/azure/data-explorer/kusto/query/joinoperator) eller liknande åtgärder ger också bättre prestanda.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="e5f2f-134">Optimera `join` operatorn</span><span class="sxs-lookup"><span data-stu-id="e5f2f-134">Optimize the `join` operator</span></span>
<span data-ttu-id="e5f2f-135">[Kopplingsoperatorn](/azure/data-explorer/kusto/query/joinoperator) slår samman rader från två tabeller genom att matcha värden i angivna kolumner.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="e5f2f-136">Använd de här tipsen om du vill optimera frågor som använder den här operatorn.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="e5f2f-137">**Mindre tabell till vänster –** Operatorn matchar poster i tabellen på vänster sida av kopplingssatsen till poster till `join` höger.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="e5f2f-138">Genom att ha den mindre tabellen till vänster behöver färre poster matchas, vilket gör frågan snabbare.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span>

    <span data-ttu-id="e5f2f-139">I tabellen nedan ser vi till att den vänstra tabellen endast omfattar tre specifika enheter innan du ansluter `DeviceLogonEvents` till den med via `IdentityLogonEvents` konto-SID.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>

    ```kusto
    DeviceLogonEvents
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="e5f2f-140">**Använd den inre join-smak**– Standard för join-smak eller [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicerar rader i den vänstra tabellen med kopplingstangenten innan du returnerar en rad för varje matchning till höger tabell. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="e5f2f-141">Om den vänstra tabellen har flera rader med samma värde för nyckeln de här raderna dedupliceras till att lämna en enda `join` slumpmässig rad för varje unikt värde.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="e5f2f-142">Den här standardbeteendet kan lämna viktig information från den vänstra tabellen som kan ge användbar insyn.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="e5f2f-143">Frågan nedan visar till exempel bara ett e-postmeddelande som innehåller en viss bifogad fil, även om samma bifogade fil skickades med flera e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    <span data-ttu-id="e5f2f-144">För att åtgärda den här begränsningen tillämpar vi [den inre join-smak](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) genom att ange att alla rader i den vänstra tabellen ska visas `kind=inner` med matchande värden till höger:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- <span data-ttu-id="e5f2f-145">**Koppla poster från ett tidsfönster**– När analytiker undersöker säkerhetshändelser letar analytiker efter relaterade händelser som inträffar under samma tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="e5f2f-146">Tillämpa samma metod när du också `join` använder fördelar prestanda genom att minska antalet poster att kontrollera.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>

    <span data-ttu-id="e5f2f-147">Med frågan nedan söker du efter inloggningshändelser inom 30 minuter efter att en skadlig fil mottagits:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="e5f2f-148">**Använda tidsfilter på** båda sidor – Även om du inte undersöker ett visst tidsfönster kan du minska antalet poster för att kontrollera och förbättra prestanda genom att använda tidsfilter på både den vänstra och den högra `join` tabellen.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="e5f2f-149">Frågan nedan gäller för `Timestamp > ago(1h)` båda tabellerna så att den bara sammanför poster från den senaste timmen:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- <span data-ttu-id="e5f2f-150">**Använd tips för prestanda –** Använd tips med operatorn för att instruera backend att fördela belastningen när du kör `join` resursintensiva åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="e5f2f-151">Läs mer om kopplingstips</span><span class="sxs-lookup"><span data-stu-id="e5f2f-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="e5f2f-152">Med slumpningen **[](/azure/data-explorer/kusto/query/shufflequery)** kan du till exempel förbättra frågeprestandan när du sammanfogar tabeller med en tangent med hög kardinalitet – en nyckel med många unika värden – som i `AccountObjectId` frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    <span data-ttu-id="e5f2f-153">**[Sändningstipset](/azure/data-explorer/kusto/query/broadcastjoin)** hjälper när den vänstra tabellen är liten (upp till 100 000 poster) och den högra tabellen är extremt stor.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="e5f2f-154">Frågan nedan försöker till exempel ansluta till några e-postmeddelanden som har specifika ämnen med _alla_ meddelanden som innehåller länkar i `EmailUrlInfo` tabellen:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="e5f2f-155">Optimera `summarize` operatorn</span><span class="sxs-lookup"><span data-stu-id="e5f2f-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="e5f2f-156">[Summeringsoperatorn](/azure/data-explorer/kusto/query/summarizeoperator) aggregerar innehållet i en tabell.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="e5f2f-157">Använd de här tipsen om du vill optimera frågor som använder den här operatorn.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="e5f2f-158">**Hitta distinkta värden**– Använd i allmänhet för `summarize` att hitta distinkta värden som kan upprepas.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="e5f2f-159">Det kan vara onödigt att använda den för att sammanställa kolumner som inte har repetitiva värden.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="e5f2f-160">Även om ett enskilt e-postmeddelande kan vara  en del av flera händelser är exemplet nedan inte effektivt, eftersom ett nätverksmeddelande-ID för ett enskilt e-postmeddelande alltid levereras med en `summarize` unik avsändaradress.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="e5f2f-161">Operatorn `summarize` kan enkelt ersättas med , vilket `project` eventuellt ger samma resultat samtidigt som färre resurser används:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="e5f2f-162">Följande exempel är ett mer effektivt sätt att använda eftersom det kan finnas flera distinkta instanser av en avsändaradress som skickar `summarize` e-post till samma mottagaradress.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="e5f2f-163">Sådana kombinationer är mindre distinkta och kan ha dubbletter.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- <span data-ttu-id="e5f2f-164">**Blanda frågan –** Även om den bäst används i kolumner med repetitiva värden, kan samma kolumner också ha hög `summarize` _kardinalitet_ eller ett stort antal unika värden.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="e5f2f-165">Precis som operatorn kan du även använda slumpa aningen med för att fördela belastningen och potentiellt förbättra prestandan när du `join` arbetar med kolumner med hög [](/azure/data-explorer/kusto/query/shufflequery) `summarize` kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="e5f2f-166">Frågan nedan använder för `summarize` att räkna distinkta mottagares e-postadress, som kan köras i hundratals tusentals i stora organisationer.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="e5f2f-167">För att förbättra prestanda omfattar `hint.shufflekey` det:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="e5f2f-168">Frågescenarier</span><span class="sxs-lookup"><span data-stu-id="e5f2f-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="e5f2f-169">Identifiera unika processer med process-ID</span><span class="sxs-lookup"><span data-stu-id="e5f2f-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="e5f2f-170">Process-ID:n (PID) återanvänds i Windows återanvänds för nya processer.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="e5f2f-171">De kan på egen hand inte fungera som unika identifierare för specifika processer.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="e5f2f-172">Om du vill få en unik identifierare för en process på en viss dator kan du använda process-ID:t tillsammans med den tid då processen skapades.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="e5f2f-173">När du sammanfogar eller sammanfattar data runt processer tar du med kolumner för maskinidentifieraren (antingen eller `DeviceId` `DeviceName` ), process-ID ( eller ) och tiden då processen skapades `ProcessId` ( eller `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` )</span><span class="sxs-lookup"><span data-stu-id="e5f2f-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="e5f2f-174">Följande exempelfråga hittar processer som har åtkomst till fler än 10 IP-adresser via port 445 (SMB), eventuellt genomsökning efter filresurser.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="e5f2f-175">Exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="e5f2f-176">Frågan sammanfattas av båda och så att den tittar på en enda `InitiatingProcessId` `InitiatingProcessCreationTime` process, utan att blanda flera processer med samma process-ID.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="e5f2f-177">Frågekommandon</span><span class="sxs-lookup"><span data-stu-id="e5f2f-177">Query command lines</span></span>
<span data-ttu-id="e5f2f-178">Det finns flera sätt att skapa en kommandorad för att utföra en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="e5f2f-179">En attackerare kan till exempel referera till en bildfil utan en sökväg, utan filnamnstillägg, med hjälp av miljövariabler eller med citattecken.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="e5f2f-180">Attacken kan också ändra ordningen på parametrar eller lägga till flera citattecken och blanksteg.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="e5f2f-181">Använd följande metoder för att skapa mer beständiga frågor runt kommandorader:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="e5f2f-182">Identifiera de kända processerna (till *exempelnet.exe* eller *psexec.exe*) genom att matcha på filnamnsfälten, i stället för att filtrera på själva kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="e5f2f-183">Tolka kommandoradsavsnitt med funktionen [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span>
- <span data-ttu-id="e5f2f-184">Vid sökning efter kommandoradsargument bör du inte söka efter en exakt matchning för flera orelaterade argument i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="e5f2f-185">I stället kan du använda reguljära uttryck eller använda flera separata operatorer.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="e5f2f-186">Använd fallkänsliga matchningar.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-186">Use case insensitive matches.</span></span> <span data-ttu-id="e5f2f-187">Använd till exempel `=~` , och i stället för , och `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="e5f2f-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="e5f2f-188">Överväg att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera efterföljande blanksteg med ett enda blanksteg för att minimera teknik för att begränsa anropsteknik för kommandorader.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="e5f2f-189">Det finns mer komplexa lösningar på problem som kräver andra metoder, men de här justeringarna kan vara till stor hjälp för vanliga.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="e5f2f-190">Följande exempel visar olika sätt att skapa en  fråga som söker efter filennet.exestoppa brandväggstjänsten "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="e5f2f-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc"

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc"
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="e5f2f-191">Mata in data från externa källor</span><span class="sxs-lookup"><span data-stu-id="e5f2f-191">Ingest data from external sources</span></span>
<span data-ttu-id="e5f2f-192">Om du vill infoga långa listor eller stora tabeller i frågan använder du [operatorn externaldata för](/azure/data-explorer/kusto/query/externaldata-operator) att mata in data från en viss URI.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="e5f2f-193">Du kan hämta data från filer i TXT, CSV, JSON eller [andra format.](/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="e5f2f-194">Exemplet nedan visar hur du kan använda den omfattande listan med SHA-256-hashprogram för skadlig programvara som tillhandahålls av MalwareBazaar (abuse.ch) för att kontrollera bifogade filer i e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="e5f2f-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo
| where Timestamp > ago(1d)
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a><span data-ttu-id="e5f2f-195">Tolka strängar</span><span class="sxs-lookup"><span data-stu-id="e5f2f-195">Parse strings</span></span>
<span data-ttu-id="e5f2f-196">Det finns olika funktioner som du kan använda för att effektivt hantera strängar som behöver parsning eller konvertering.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span>

| <span data-ttu-id="e5f2f-197">Sträng</span><span class="sxs-lookup"><span data-stu-id="e5f2f-197">String</span></span> | <span data-ttu-id="e5f2f-198">Funktion</span><span class="sxs-lookup"><span data-stu-id="e5f2f-198">Function</span></span> | <span data-ttu-id="e5f2f-199">Användningsexempel</span><span class="sxs-lookup"><span data-stu-id="e5f2f-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="e5f2f-200">Kommandorader</span><span class="sxs-lookup"><span data-stu-id="e5f2f-200">Command-lines</span></span> | [<span data-ttu-id="e5f2f-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="e5f2f-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="e5f2f-202">Extrahera kommandot och alla argument.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-202">Extract the command and all arguments.</span></span> |
| <span data-ttu-id="e5f2f-203">Sökvägar</span><span class="sxs-lookup"><span data-stu-id="e5f2f-203">Paths</span></span> | [<span data-ttu-id="e5f2f-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="e5f2f-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="e5f2f-205">Extrahera avsnitten i en fil- eller mappsökväg.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="e5f2f-206">Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="e5f2f-206">Version numbers</span></span> | [<span data-ttu-id="e5f2f-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="e5f2f-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="e5f2f-208">Avmarkera ett versionsnummer med upp till fyra avsnitt och upp till åtta tecken per avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="e5f2f-209">Använd tolkade data för att jämföra versions ålder.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="e5f2f-210">IPv4-adresser</span><span class="sxs-lookup"><span data-stu-id="e5f2f-210">IPv4 addresses</span></span> | [<span data-ttu-id="e5f2f-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="e5f2f-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="e5f2f-212">Konvertera en IPv4-adress till ett långt heltal.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="e5f2f-213">Om du vill jämföra IPv4-adresser utan att konvertera dem använder [du ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="e5f2f-214">IPv6-adresser</span><span class="sxs-lookup"><span data-stu-id="e5f2f-214">IPv6 addresses</span></span> | [<span data-ttu-id="e5f2f-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="e5f2f-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="e5f2f-216">Konvertera en IPv4- eller IPv6-adress till den kanoniska IPv6-notationen.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="e5f2f-217">Jämför IPv6-adresser med hjälp [av ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="e5f2f-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="e5f2f-218">Mer information om alla parsingsfunktioner som stöds finns [i Kusto-strängfunktioner.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span>

>[!NOTE]
><span data-ttu-id="e5f2f-219">Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-219">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e5f2f-220">[Aktivera Microsoft 365 Defender](m365d-enable.md) för att leta efter hot med hjälp av fler datakällor.</span><span class="sxs-lookup"><span data-stu-id="e5f2f-220">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="e5f2f-221">Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="e5f2f-221">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5f2f-222">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e5f2f-222">Related topics</span></span>
- [<span data-ttu-id="e5f2f-223">Språkdokumentation för kustofrågor</span><span class="sxs-lookup"><span data-stu-id="e5f2f-223">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="e5f2f-224">Kvoter och användningsparametrar</span><span class="sxs-lookup"><span data-stu-id="e5f2f-224">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="e5f2f-225">Hantera avancerade sökfel</span><span class="sxs-lookup"><span data-stu-id="e5f2f-225">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="e5f2f-226">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e5f2f-226">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e5f2f-227">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="e5f2f-227">Learn the query language</span></span>](advanced-hunting-query-language.md)