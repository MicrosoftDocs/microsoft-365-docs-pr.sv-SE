---
title: Översikt över avancerad jakt i Microsoft Threat Protection
description: Lär dig mer om avancerade jaktfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806063"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="32cb6-104">Proaktivt jaga hot med avancerad jakt i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="32cb6-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="32cb6-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="32cb6-105">**Applies to:**</span></span>
- <span data-ttu-id="32cb6-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="32cb6-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="32cb6-107">Avancerad jakt är ett frågebaserat hotjaktsverktyg som låter dig utforska upp till 30 dagars rådata.</span><span class="sxs-lookup"><span data-stu-id="32cb6-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="32cb6-108">Du kan proaktivt granska händelser i nätverket för att hitta intressanta indikatorer och entiteter.</span><span class="sxs-lookup"><span data-stu-id="32cb6-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="32cb6-109">Den flexibla tillgången till data underlättar obegränsad jakt efter både kända och potentiella hot.</span><span class="sxs-lookup"><span data-stu-id="32cb6-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="32cb6-110">I Microsoft 365 security center stöder avancerad jakt frågor som undersöker data från både Microsoft Defender ATP, som täcker data från inbyggda enheter och Office 365 ATP, som tillhandahåller data från e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="32cb6-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="32cb6-111">Om du vill använda avancerad jakt [aktiverar du Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="32cb6-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="32cb6-112">Kom igång med avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="32cb6-112">Get started with advanced hunting</span></span>

<span data-ttu-id="32cb6-113">Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="32cb6-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="32cb6-114">Lärande mål</span><span class="sxs-lookup"><span data-stu-id="32cb6-114">Learning goal</span></span> | <span data-ttu-id="32cb6-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="32cb6-115">Description</span></span> | <span data-ttu-id="32cb6-116">Resurs</span><span class="sxs-lookup"><span data-stu-id="32cb6-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="32cb6-117">**Få en känsla för språket**</span><span class="sxs-lookup"><span data-stu-id="32cb6-117">**Get a feel for the language**</span></span> | <span data-ttu-id="32cb6-118">Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/), som stöder samma syntax och operatorer.</span><span class="sxs-lookup"><span data-stu-id="32cb6-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="32cb6-119">Börja lära dig frågespråket genom att köra den första frågan.</span><span class="sxs-lookup"><span data-stu-id="32cb6-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="32cb6-120">Översikt över frågespråk</span><span class="sxs-lookup"><span data-stu-id="32cb6-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="32cb6-121">**Förstå schemat**</span><span class="sxs-lookup"><span data-stu-id="32cb6-121">**Understand the schema**</span></span> | <span data-ttu-id="32cb6-122">Få en bra förståelse på hög nivå av tabellerna i schemat och deras kolumner.</span><span class="sxs-lookup"><span data-stu-id="32cb6-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="32cb6-123">Detta hjälper dig att avgöra var du ska leta efter data och hur du konstruerar dina frågor.</span><span class="sxs-lookup"><span data-stu-id="32cb6-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="32cb6-124">Schemareferens</span><span class="sxs-lookup"><span data-stu-id="32cb6-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="32cb6-125">**Använda fördefinierade frågor**</span><span class="sxs-lookup"><span data-stu-id="32cb6-125">**Use predefined queries**</span></span> | <span data-ttu-id="32cb6-126">Utforska samlingar av fördefinierade frågor som täcker olika hotjaktsscenarier.</span><span class="sxs-lookup"><span data-stu-id="32cb6-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="32cb6-127">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="32cb6-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="32cb6-128">**Optimera frågor**</span><span class="sxs-lookup"><span data-stu-id="32cb6-128">**Optimize queries**</span></span> | <span data-ttu-id="32cb6-129">Förstå hur du skapar effektiva frågor och frågor som kombinerar data från e-postmeddelanden och enheter.</span><span class="sxs-lookup"><span data-stu-id="32cb6-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="32cb6-130">[Fråga metodtips](advanced-hunting-shared-queries.md), [Jaga över enheter och e-postmeddelanden](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="32cb6-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="32cb6-131">Få hjälp när du skriver frågor</span><span class="sxs-lookup"><span data-stu-id="32cb6-131">Get help as you write queries</span></span>
<span data-ttu-id="32cb6-132">Dra nytta av följande funktioner för att skriva frågor snabbare:</span><span class="sxs-lookup"><span data-stu-id="32cb6-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="32cb6-133">**Autosuggest** - när du skriver frågor, avancerad jakt ger förslag.</span><span class="sxs-lookup"><span data-stu-id="32cb6-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="32cb6-134">**Schemareferens** – en schemareferens som innehåller listan med tabeller och deras kolumner anges bredvid arbetsområdet.</span><span class="sxs-lookup"><span data-stu-id="32cb6-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="32cb6-135">Om du vill ha mer information håller du muspekaren över ett objekt.</span><span class="sxs-lookup"><span data-stu-id="32cb6-135">For more information, hover over an item.</span></span> <span data-ttu-id="32cb6-136">Dubbelklicka på ett objekt för att infoga det i frågeredigeraren.</span><span class="sxs-lookup"><span data-stu-id="32cb6-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="32cb6-137">Detaljerad granskning från frågeresultat</span><span class="sxs-lookup"><span data-stu-id="32cb6-137">Drilldown from query results</span></span>
<span data-ttu-id="32cb6-138">Om du vill visa mer information om entiteter, till exempel datorer, filer, användare, IP-adresser och webbadresser, klickar du bara på entitetsidentifieraren i frågeresultaten.</span><span class="sxs-lookup"><span data-stu-id="32cb6-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="32cb6-139">Då öppnas en detaljerad profilsida för den valda entiteten i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="32cb6-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="32cb6-140">Justera dina frågor från resultaten</span><span class="sxs-lookup"><span data-stu-id="32cb6-140">Tweak your queries from the results</span></span>
<span data-ttu-id="32cb6-141">Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan.</span><span class="sxs-lookup"><span data-stu-id="32cb6-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="32cb6-142">Du kan använda alternativen för att:</span><span class="sxs-lookup"><span data-stu-id="32cb6-142">You can use the options to:</span></span>

- <span data-ttu-id="32cb6-143">Leta uttryckligen efter det`==`valda värdet ( )</span><span class="sxs-lookup"><span data-stu-id="32cb6-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="32cb6-144">Exkludera det markerade`!=`värdet från frågan ( )</span><span class="sxs-lookup"><span data-stu-id="32cb6-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="32cb6-145">Få fler avancerade operatorer för att lägga `contains`till `starts with` värdet i frågan, till exempel, och`ends with`</span><span class="sxs-lookup"><span data-stu-id="32cb6-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild på Microsoft Defender ATP avancerade jaktresultat set](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="32cb6-147">Filtrera frågeresultaten</span><span class="sxs-lookup"><span data-stu-id="32cb6-147">Filter the query results</span></span>
<span data-ttu-id="32cb6-148">Filtren som visas till höger ger en sammanfattning av resultatuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="32cb6-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="32cb6-149">Varje kolumn har ett eget avsnitt som visar de distinkta värden som finns för den kolumnen och antalet instanser.</span><span class="sxs-lookup"><span data-stu-id="32cb6-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="32cb6-150">Förfina frågan genom att välja knapparna "+" eller "-" på de värden som du vill inkludera eller utesluta och sedan välja **Kör fråga**.</span><span class="sxs-lookup"><span data-stu-id="32cb6-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Bild av avancerat jaktfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="32cb6-152">När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="32cb6-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32cb6-153">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="32cb6-153">Related topics</span></span>
- [<span data-ttu-id="32cb6-154">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="32cb6-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="32cb6-155">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="32cb6-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="32cb6-156">Jaga hot mellan enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="32cb6-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="32cb6-157">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="32cb6-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="32cb6-158">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="32cb6-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
