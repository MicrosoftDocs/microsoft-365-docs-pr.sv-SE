---
title: Metod tips för avancerade frågor
description: Lär dig hur du skapar snabba, effektiva och problem fria hotfrågor med avancerad jakt
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, kusto, förhindra tids gräns, kommando rader, process-ID, optimera, metod tips, tolka, gå med och summera
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
ms.openlocfilehash: 3ca475ef6dbdbd66af47216c4130d748788730c2
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419138"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="42947-104">Metod tips för avancerad jakt frågor</span><span class="sxs-lookup"><span data-stu-id="42947-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="42947-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="42947-105">**Applies to:**</span></span>
- <span data-ttu-id="42947-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="42947-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="42947-107">Använd dessa rekommendationer för att få snabbare resultat och undvika tids gränser när komplexa frågor körs.</span><span class="sxs-lookup"><span data-stu-id="42947-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="42947-108">För mer information om hur du förbättrar frågeresultatet kan du läsa [Kusto metod tips](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="42947-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="general-guidance"></a><span data-ttu-id="42947-109">Allmän vägledning</span><span class="sxs-lookup"><span data-stu-id="42947-109">General guidance</span></span>

- <span data-ttu-id="42947-110">**Ändra storlek på nya frågor**– om du misstänker att en fråga returnerar en stor resultat mängd ska du först bedöma den med hjälp av [operatorn Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="42947-110">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="42947-111">Använd [gräns](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) eller synonym `take` för att undvika stora resultat mängder.</span><span class="sxs-lookup"><span data-stu-id="42947-111">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="42947-112">**Använd filter tidigt**– Använd tids filter och andra filter för att minska data uppsättningen, särskilt innan du använder omvandlings-och analys funktioner, till exempel [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Ersätt ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Rensa ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)eller [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="42947-112">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="42947-113">I exemplet nedan används parsnings funktionen [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) efter att filtrerings operatorerna har minskat antalet poster.</span><span class="sxs-lookup"><span data-stu-id="42947-113">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="42947-114">**Har taktslag innehåller**– för att undvika att under strängar under vissa ord visas kan du använda `has` operatorn i stället för `contains` .</span><span class="sxs-lookup"><span data-stu-id="42947-114">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="42947-115">Läs mer om sträng operatorer</span><span class="sxs-lookup"><span data-stu-id="42947-115">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="42947-116">**Leta i specifika kolumner**– titta i en viss kolumn i stället för att köra fullständig text ökning i alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="42947-116">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="42947-117">Använd inte `*` för att markera alla kolumner.</span><span class="sxs-lookup"><span data-stu-id="42947-117">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="42947-118">**SKIFT läges känslig för snabb**sökningar är mer specifika och generellt sett mer.</span><span class="sxs-lookup"><span data-stu-id="42947-118">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="42947-119">Namn på SKIFT läges känsliga [sträng operatorer](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), till exempel `has_cs` och `contains_cs` , vanligt vis slutar med `_cs` .</span><span class="sxs-lookup"><span data-stu-id="42947-119">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="42947-120">Du kan också använda en Skift läges känslig operator `==` i stället för `~=` .</span><span class="sxs-lookup"><span data-stu-id="42947-120">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="42947-121">**Tolka, extrahera inte**– när det är möjligt kan du använda [operatorn parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) eller en analys funktion som [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="42947-121">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="42947-122">Undvik `matches regex` operatorn sträng eller [extrahera ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), som båda använder reguljära uttryck.</span><span class="sxs-lookup"><span data-stu-id="42947-122">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="42947-123">Reservera användning av reguljära uttryck för mer komplexa scenarier.</span><span class="sxs-lookup"><span data-stu-id="42947-123">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="42947-124">Läs mer om att analysera funktioner</span><span class="sxs-lookup"><span data-stu-id="42947-124">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="42947-125">**Filtrera tabeller som inte är uttryck**– filtrera inte efter beräknade kolumner om du kan filtrera efter en tabell kolumn.</span><span class="sxs-lookup"><span data-stu-id="42947-125">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="42947-126">**Inga termer med tre tecken**– Undvik jämförelse eller filtrering med hjälp av termer med tre tecken eller färre.</span><span class="sxs-lookup"><span data-stu-id="42947-126">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="42947-127">Dessa villkor är inte indexerade och matchar dem kräver fler resurser.</span><span class="sxs-lookup"><span data-stu-id="42947-127">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="42947-128">**Project selektiv**– gör dina resultat lättare att förstå genom att bara projicera de kolumner du behöver.</span><span class="sxs-lookup"><span data-stu-id="42947-128">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="42947-129">Om du projicerar specifika kolumner innan du kör [Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) eller liknande operationer förbättras prestanda.</span><span class="sxs-lookup"><span data-stu-id="42947-129">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="42947-130">Optimera `join` operatorn</span><span class="sxs-lookup"><span data-stu-id="42947-130">Optimize the `join` operator</span></span>
<span data-ttu-id="42947-131">Med [operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) sammanfoga kopplas rader från två tabeller med matchande värden i angivna kolumner.</span><span class="sxs-lookup"><span data-stu-id="42947-131">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="42947-132">Använd de här tipsen för att optimera frågor som använder den här operatorn.</span><span class="sxs-lookup"><span data-stu-id="42947-132">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="42947-133">**Mindre tabell till vänster**– `join` operatorn matchar poster i tabellen till vänster om ditt JOIN-uttryck på poster till höger.</span><span class="sxs-lookup"><span data-stu-id="42947-133">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="42947-134">Genom att ha den mindre tabellen till vänster måste färre poster matchas, och därför blir frågan snabbare.</span><span class="sxs-lookup"><span data-stu-id="42947-134">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="42947-135">I tabellen nedan minskar vi den vänstra tabellen `DeviceLogonEvents` så att den bara täcker tre specifika enheter innan du ansluter den `IdentityLogonEvents` via konto-sid.</span><span class="sxs-lookup"><span data-stu-id="42947-135">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="42947-136">**Använd den inre kopplings funktionen**– standard alternativet för att [förena](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) eller [innerunique-koppla](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) ihop rader i den vänstra tabellen med hjälp av kopplings tangenten innan du returnerar en rad för varje träff till den högra tabellen.</span><span class="sxs-lookup"><span data-stu-id="42947-136">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="42947-137">Om den vänstra tabellen innehåller flera rader med samma värde för `join` tangenten dubbleras dessa rader så att de lämnar en slumpmässig rad för varje unikt värde.</span><span class="sxs-lookup"><span data-stu-id="42947-137">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="42947-138">Detta standard beteende kan leda till viktig information från den vänstra tabellen som kan ge användbar insyn.</span><span class="sxs-lookup"><span data-stu-id="42947-138">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="42947-139">Frågan nedan visar till exempel endast ett e-postmeddelande med en viss bifogad fil, även om den bifogade filen skickades med flera e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="42947-139">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="42947-140">För att adressera den här begränsningen använder vi den [inre kopplingen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) genom `kind=inner` att ange att visa alla rader i den vänstra tabellen med matchande värden till höger:</span><span class="sxs-lookup"><span data-stu-id="42947-140">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="42947-141">**Ansluta till poster från ett tidsfönster**– när du undersöker säkerhets händelser letar analytiker efter relaterade händelser som inträffar inom samma tids period.</span><span class="sxs-lookup"><span data-stu-id="42947-141">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="42947-142">Använd samma tillvägagångs sätt när du använder olika `join` prestanda genom att minska antalet poster att kontrol lera.</span><span class="sxs-lookup"><span data-stu-id="42947-142">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="42947-143">Frågan nedan söker efter inloggnings händelser inom 30 minuter efter att du har tagit emot en skadlig fil:</span><span class="sxs-lookup"><span data-stu-id="42947-143">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="42947-144">**Tillämpa tids filter på båda sidor**– även om du inte undersöker ett specifikt tidsfönster kan du använda tids filter för både vänster och höger tabell för att minska antalet poster för att kontrol lera och förbättra `join` prestanda.</span><span class="sxs-lookup"><span data-stu-id="42947-144">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="42947-145">Frågan nedan gäller `Timestamp > ago(1h)` båda tabellerna så att den bara ansluter till poster från den senaste timmen:</span><span class="sxs-lookup"><span data-stu-id="42947-145">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="42947-146">**Använda tips för prestanda**– Använd tips med `join` operatorn för att instruera Server delen att distribuera belastningen när resurser körs.</span><span class="sxs-lookup"><span data-stu-id="42947-146">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="42947-147">Lär dig mer om att delta i tips</span><span class="sxs-lookup"><span data-stu-id="42947-147">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="42947-148">Med **[blanda tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** kan du till exempel förbättra frågans prestanda när du ansluter tabeller med hjälp av en transparens med hög kardinalitet – en transparens med många unika värden – till exempel `AccountObjectId` i frågan nedan:</span><span class="sxs-lookup"><span data-stu-id="42947-148">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="42947-149">Med **[sändnings tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** ser du när den vänstra tabellen är liten (upp till 100 000 poster) och den högra tabellen är oerhört stor.</span><span class="sxs-lookup"><span data-stu-id="42947-149">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="42947-150">Frågan nedan försöker till exempel ansluta till några e-postmeddelanden med specifika ämnen med _alla_ meddelanden som innehåller länkar i `EmailUrlInfo` tabellen:</span><span class="sxs-lookup"><span data-stu-id="42947-150">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="42947-151">Optimera `summarize` operatorn</span><span class="sxs-lookup"><span data-stu-id="42947-151">Optimize the `summarize` operator</span></span>
<span data-ttu-id="42947-152">Den [summerade operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregerar innehållet i en tabell.</span><span class="sxs-lookup"><span data-stu-id="42947-152">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="42947-153">Använd de här tipsen för att optimera frågor som använder den här operatorn.</span><span class="sxs-lookup"><span data-stu-id="42947-153">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="42947-154">**Sök efter distinkta värden**— i allmänhet `summarize` för att hitta distinkta värden som kan upprepas.</span><span class="sxs-lookup"><span data-stu-id="42947-154">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="42947-155">Det kan vara onödigt att använda det för att aggregera kolumner som inte innehåller upprepade värden.</span><span class="sxs-lookup"><span data-stu-id="42947-155">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="42947-156">Även om ett enskilt e-postmeddelande kan ingå i flera händelser används _inte_ exemplet nedan för `summarize` att ett nätverks meddelande-ID för ett enskilt e-postmeddelande alltid innehåller en unik avsändar adress.</span><span class="sxs-lookup"><span data-stu-id="42947-156">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="42947-157">Det `summarize` går lätt att byta ut operatorn `project` , vilket ger eventuellt samma resultat när du förbrukar färre resurser:</span><span class="sxs-lookup"><span data-stu-id="42947-157">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="42947-158">Följande exempel är en mer effektiv användning av `summarize` eftersom det kan finnas flera olika instanser av en avsändar adress som skickar e-post till samma mottagares adress.</span><span class="sxs-lookup"><span data-stu-id="42947-158">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="42947-159">Sådana kombinationer är mindre distinkta och har troligen dubbletter.</span><span class="sxs-lookup"><span data-stu-id="42947-159">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="42947-160">Om **du blandar frågan**– medan `summarize` är bäst i kolumner med repetitiva värden kan samma kolumner också ha en _hög kardinalitet_ eller ett stort antal unika värden.</span><span class="sxs-lookup"><span data-stu-id="42947-160">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="42947-161">Precis som med `join` operatorn kan du även använda [blanda-tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) med `summarize` för att distribuera bearbetnings belastning och kan förbättra prestandan när du arbetar med kolumner med stor kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="42947-161">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="42947-162">Frågan nedan används `summarize` för att räkna distinkt mottagares e-postadress, som kan köras i hundratals tusen i stora organisationer.</span><span class="sxs-lookup"><span data-stu-id="42947-162">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="42947-163">För att förbättra prestandan inkluderar den `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="42947-163">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="42947-164">Fråge scenarier</span><span class="sxs-lookup"><span data-stu-id="42947-164">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="42947-165">Identifiera unika processer med process-ID</span><span class="sxs-lookup"><span data-stu-id="42947-165">Identify unique processes with process IDs</span></span>
<span data-ttu-id="42947-166">Process-ID: n återvinns i Windows och återanvänds för nya processer.</span><span class="sxs-lookup"><span data-stu-id="42947-166">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="42947-167">De kan inte fungera som unika identifierare för specifika processer.</span><span class="sxs-lookup"><span data-stu-id="42947-167">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="42947-168">Om du vill ha en unik identifierare för en process på en specifik dator använder du process-ID: t tillsammans med processen för skapande av process.</span><span class="sxs-lookup"><span data-stu-id="42947-168">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="42947-169">När du ansluter till eller sammanfattar data i processer inkluderar du kolumner för datorns ID (antingen `DeviceId` eller `DeviceName` ), process-ID ( `ProcessId` eller `InitiatingProcessId` ) och processens skapelse tid ( `ProcessCreationTime` eller `InitiatingProcessCreationTime` )</span><span class="sxs-lookup"><span data-stu-id="42947-169">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="42947-170">I följande exempel fråga hittas processer med åtkomst till fler än 10 IP-adresser över Port 445 (SMB), eventuellt genomsökning efter fil resurser.</span><span class="sxs-lookup"><span data-stu-id="42947-170">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="42947-171">Exempel fråga:</span><span class="sxs-lookup"><span data-stu-id="42947-171">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="42947-172">Frågan sammanfattar både efter båda `InitiatingProcessId` och `InitiatingProcessCreationTime` så att den ser ut på en enstaka gång, utan att flera processer med samma process-ID kan blandas.</span><span class="sxs-lookup"><span data-stu-id="42947-172">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="42947-173">Kommando rader för fråga</span><span class="sxs-lookup"><span data-stu-id="42947-173">Query command lines</span></span>
<span data-ttu-id="42947-174">Det finns många olika sätt att skapa en kommando rad för att utföra en uppgift.</span><span class="sxs-lookup"><span data-stu-id="42947-174">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="42947-175">En angripare kan till exempel referera till en bildfil utan sökväg, utan fil namns tillägg, med hjälp av miljövariabler eller med citat tecken.</span><span class="sxs-lookup"><span data-stu-id="42947-175">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="42947-176">Angriparen kan också ändra ordningen på parametrar eller lägga till flera citat tecken och blank steg.</span><span class="sxs-lookup"><span data-stu-id="42947-176">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="42947-177">Gör så här om du vill skapa fler fasta frågor kring kommando rader:</span><span class="sxs-lookup"><span data-stu-id="42947-177">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="42947-178">Identifiera kända processer (till exempel *net.exe* eller *psexec.exe*) genom att matcha i fil namns fälten i stället för att filtrera på själva kommando raden.</span><span class="sxs-lookup"><span data-stu-id="42947-178">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="42947-179">Kommando rads avsnitt för parsning med [funktionen parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="42947-179">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="42947-180">Leta inte efter en exakt matchning på flera icke relaterade argument i en viss ordning när du frågar efter kommando rads argument.</span><span class="sxs-lookup"><span data-stu-id="42947-180">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="42947-181">Använd i stället vanliga uttryck eller Använd flera separata innehåller operatorer.</span><span class="sxs-lookup"><span data-stu-id="42947-181">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="42947-182">Använd Skift läges okänsliga träffar.</span><span class="sxs-lookup"><span data-stu-id="42947-182">Use case insensitive matches.</span></span> <span data-ttu-id="42947-183">Du kan till exempel använda `=~` , `in~` och `contains` i stället för `==` , `in` och `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="42947-183">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="42947-184">För att minska kommando rads obfuscation metoder bör du överväga att ta bort citat tecken, ersätta kommatecken med blank steg och ersätta flera sammanhängande blank steg med ett enda blank steg.</span><span class="sxs-lookup"><span data-stu-id="42947-184">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="42947-185">Det finns mer komplexa obfuscation-tekniker som kräver andra metoder, men dessa kan hjälpa dig att åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="42947-185">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="42947-186">Följande exempel visar olika sätt att skapa en fråga som söker efter filen *net.exe* att stoppa brand Väggs tjänsten "Mpssvc":</span><span class="sxs-lookup"><span data-stu-id="42947-186">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="42947-187">Intag från externa källor</span><span class="sxs-lookup"><span data-stu-id="42947-187">Ingest data from external sources</span></span>
<span data-ttu-id="42947-188">Om du vill införliva långa listor eller stora tabeller i din fråga kan du använda [externaldata-operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) för att förtära data från en angiven URI.</span><span class="sxs-lookup"><span data-stu-id="42947-188">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="42947-189">Du kan hämta data från filer i TXT, CSV, JSON eller [andra format](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="42947-189">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="42947-190">I exemplet nedan visas hur du kan använda den omfattande listan med SHA-256-hashar från MalwareBazaar (abuse.ch) för att kontrol lera bifogade filer i e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="42947-190">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="42947-191">Tolka strängar</span><span class="sxs-lookup"><span data-stu-id="42947-191">Parse strings</span></span>
<span data-ttu-id="42947-192">Det finns olika funktioner som du kan använda för att effektivt hantera strängar som behöver parsas eller konverteras.</span><span class="sxs-lookup"><span data-stu-id="42947-192">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="42947-193">Sträng</span><span class="sxs-lookup"><span data-stu-id="42947-193">String</span></span> | <span data-ttu-id="42947-194">&</span><span class="sxs-lookup"><span data-stu-id="42947-194">Function</span></span> | <span data-ttu-id="42947-195">Exempel på användning</span><span class="sxs-lookup"><span data-stu-id="42947-195">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="42947-196">Kommando rader</span><span class="sxs-lookup"><span data-stu-id="42947-196">Command-lines</span></span> | [<span data-ttu-id="42947-197">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="42947-197">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="42947-198">Extrahera kommandot och alla argument.</span><span class="sxs-lookup"><span data-stu-id="42947-198">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="42947-199">Banan</span><span class="sxs-lookup"><span data-stu-id="42947-199">Paths</span></span> | [<span data-ttu-id="42947-200">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="42947-200">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="42947-201">Extrahera avsnitt i en fil-eller mappsökväg.</span><span class="sxs-lookup"><span data-stu-id="42947-201">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="42947-202">Versions nummer</span><span class="sxs-lookup"><span data-stu-id="42947-202">Version numbers</span></span> | [<span data-ttu-id="42947-203">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="42947-203">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="42947-204">Avkonstruerar ett versions nummer med upp till fyra avsnitt och upp till åtta tecken per avsnitt.</span><span class="sxs-lookup"><span data-stu-id="42947-204">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="42947-205">Jämför versions åldern med analyserade data.</span><span class="sxs-lookup"><span data-stu-id="42947-205">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="42947-206">IPv4-adresser</span><span class="sxs-lookup"><span data-stu-id="42947-206">IPv4 addresses</span></span> | [<span data-ttu-id="42947-207">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="42947-207">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="42947-208">Konvertera en IPv4-adress till ett långt heltal.</span><span class="sxs-lookup"><span data-stu-id="42947-208">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="42947-209">Använd [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)om du vill jämföra IPv4-adresser utan att konvertera dem.</span><span class="sxs-lookup"><span data-stu-id="42947-209">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="42947-210">IPv6-adresser</span><span class="sxs-lookup"><span data-stu-id="42947-210">IPv6 addresses</span></span> | [<span data-ttu-id="42947-211">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="42947-211">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="42947-212">Konvertera en IPv4-eller IPv6-adress till det kanoniska IPv6-formatet.</span><span class="sxs-lookup"><span data-stu-id="42947-212">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="42947-213">Använd [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)om du vill jämföra IPv6-adresser.</span><span class="sxs-lookup"><span data-stu-id="42947-213">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="42947-214">Om du vill veta mer om alla analys funktioner som stöds [läser du Kusto sträng funktioner](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="42947-214">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="42947-215">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="42947-215">Related topics</span></span>
- [<span data-ttu-id="42947-216">Dokumentation för Kusto</span><span class="sxs-lookup"><span data-stu-id="42947-216">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="42947-217">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="42947-217">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42947-218">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="42947-218">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="42947-219">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="42947-219">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="42947-220">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="42947-220">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="42947-221">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="42947-221">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="42947-222">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="42947-222">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
