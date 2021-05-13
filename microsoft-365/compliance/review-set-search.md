---
title: Fråga data i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur du skapar och kör en fråga i en granskningsuppsättning för att ordna data för en effektivare granskning i Advanced eDiscovery ärende.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345806"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="f9d49-103">Fråga data i en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="f9d49-103">Query the data in a review set</span></span>

<span data-ttu-id="f9d49-104">I de flesta fall är det bra att kunna fördjupa sig i data i en granskningsuppsättning och ordna dessa data för att underlätta en effektivare granskning.</span><span class="sxs-lookup"><span data-stu-id="f9d49-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="f9d49-105">Med hjälp av Frågor i en granskningsuppsättning kan du fokusera på en delmängd dokument som uppfyller villkoren för din granskning.</span><span class="sxs-lookup"><span data-stu-id="f9d49-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="f9d49-106">Skapa och köra en fråga i en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="f9d49-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="f9d49-107">Om du vill skapa och köra en fråga på dokument i en granskningsuppsättning **väljer du Ny fråga** i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f9d49-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="f9d49-108">När du har namn upp frågan och definierat villkoren väljer **du Spara** för att spara och köra frågan.</span><span class="sxs-lookup"><span data-stu-id="f9d49-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="f9d49-109">Om du vill köra en fråga som har sparats tidigare väljer du en sparad fråga.</span><span class="sxs-lookup"><span data-stu-id="f9d49-109">To run a query that has been previously saved, select a saved query.</span></span>

![Granska uppsättningsfrågor](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="f9d49-111">Skapa en granskningsuppsättningsfråga</span><span class="sxs-lookup"><span data-stu-id="f9d49-111">Building a review set query</span></span>

<span data-ttu-id="f9d49-112">Du kan skapa en fråga genom att använda en kombination av nyckelord, egenskaper och villkor i villkoret Nyckelord.</span><span class="sxs-lookup"><span data-stu-id="f9d49-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="f9d49-113">Du kan också gruppera villkor som ett block (kallas *villkorsgrupp)* för att skapa en mer komplex fråga.</span><span class="sxs-lookup"><span data-stu-id="f9d49-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="f9d49-114">En lista och en beskrivning av metadataegenskaper som du kan söka i finns i [Dokumentmetadatafält i Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="f9d49-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="f9d49-115">Villkor</span><span class="sxs-lookup"><span data-stu-id="f9d49-115">Conditions</span></span>

<span data-ttu-id="f9d49-116">Alla sökbara fält i en granskningsuppsättning har motsvarande villkor som du kan använda för att skapa frågan.</span><span class="sxs-lookup"><span data-stu-id="f9d49-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="f9d49-117">Det finns flera typer av villkor:</span><span class="sxs-lookup"><span data-stu-id="f9d49-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="f9d49-118">Fritext: Ett fritextvillkor används för textfält som exempelvis ämne.</span><span class="sxs-lookup"><span data-stu-id="f9d49-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="f9d49-119">Du kan lista flera sökord genom att avgränsa dem med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="f9d49-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="f9d49-120">Datum: Ett datumvillkor används för datumfält som senast ändrad.</span><span class="sxs-lookup"><span data-stu-id="f9d49-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="f9d49-121">Sökalternativ: Ett sökalternativvillkor tillhandahåller en lista med möjliga värden för det specifika fältet i din granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="f9d49-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="f9d49-122">Det här används för fält, till exempel avsändare, där det finns ett ändlig antal möjliga värden i din granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="f9d49-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="f9d49-123">Nyckelord: Ett nyckelordsvillkor är en specifik instans av fritextvillkor som du kan använda för att söka efter termer, eller använda KQL-liknande frågespråk.</span><span class="sxs-lookup"><span data-stu-id="f9d49-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="f9d49-124">Se nedan för mer information.</span><span class="sxs-lookup"><span data-stu-id="f9d49-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="f9d49-125">Frågespråk</span><span class="sxs-lookup"><span data-stu-id="f9d49-125">Query language</span></span>

<span data-ttu-id="f9d49-126">Utöver villkor kan du använda ett KQL-liknande frågespråk i villkoret Nyckelord för att skapa frågan.</span><span class="sxs-lookup"><span data-stu-id="f9d49-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="f9d49-127">Frågespråket för granskningsuppsättningsfrågor har stöd för booleska standardoperatorer som **AND,** **OR,** **NOT** och **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="f9d49-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="f9d49-128">Det har också stöd för ett jokertecken (?) och ett jokertecken (\*).</span><span class="sxs-lookup"><span data-stu-id="f9d49-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="f9d49-129">Filter</span><span class="sxs-lookup"><span data-stu-id="f9d49-129">Filters</span></span>

<span data-ttu-id="f9d49-130">Förutom frågor som du kan spara kan du använda granskningsuppsättningsfilter för att snabbt tillämpa ytterligare villkor på en frågeuppsättning.</span><span class="sxs-lookup"><span data-stu-id="f9d49-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="f9d49-131">Med hjälp av filter kan du förfina resultatet som visas i en granskningsuppsättningsfråga.</span><span class="sxs-lookup"><span data-stu-id="f9d49-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Filter för granskningsuppsättning](../media/AeDReviewSetFilters.png)

<span data-ttu-id="f9d49-133">Filter skiljer sig från frågor på två väsentliga sätt:</span><span class="sxs-lookup"><span data-stu-id="f9d49-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="f9d49-134">Filter är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="f9d49-134">Filters are transient.</span></span> <span data-ttu-id="f9d49-135">De finns inte kvar efter den befintliga sessionen.</span><span class="sxs-lookup"><span data-stu-id="f9d49-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="f9d49-136">Med andra ord kan du inte spara ett filter.</span><span class="sxs-lookup"><span data-stu-id="f9d49-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="f9d49-137">Frågor sparas i granskningsuppsättningen och du kommer åt dem när du öppnar granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f9d49-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="f9d49-138">Filter är alltid additiva.</span><span class="sxs-lookup"><span data-stu-id="f9d49-138">Filters are always additive.</span></span> <span data-ttu-id="f9d49-139">Filter används utöver den aktuella granskningsuppsättningsfrågan.</span><span class="sxs-lookup"><span data-stu-id="f9d49-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="f9d49-140">Om du tillämpar en annan fråga ersätts resultatet som returneras av den aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="f9d49-140">Applying a different query will replace the results returned by the current query.</span></span>
