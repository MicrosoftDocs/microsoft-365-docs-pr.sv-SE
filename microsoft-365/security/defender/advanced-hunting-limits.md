---
title: Avancerade kvoter för sökning och användningsparametrar i Microsoft 365 Defender
description: Förstå olika kvoter och användningsparametrar (tjänstbegränsningar) som ser till att tjänsten för avancerad sökning är dynamisk
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: c9526363b0430514455db1fbdf12cfb7a18229f1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932995"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="6432b-104">Avancerade kvoter för sökning och användningsparametrar</span><span class="sxs-lookup"><span data-stu-id="6432b-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6432b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6432b-105">**Applies to:**</span></span>
- <span data-ttu-id="6432b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6432b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6432b-107">För att hålla tjänstens prestanda och responsiva, anger avancerad sökning olika kvoter och användningsparametrar (kallas även "tjänstbegränsningar").</span><span class="sxs-lookup"><span data-stu-id="6432b-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="6432b-108">De här kvoter och parametrar som gäller för frågor körs manuellt och av [anpassade identifieringsregler.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6432b-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="6432b-109">Kunder som kör flera frågor regelbundet bör spåra förbrukning och [använda optimeringstips för](advanced-hunting-best-practices.md) att minimera störningar.</span><span class="sxs-lookup"><span data-stu-id="6432b-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="6432b-110">Se följande tabell för att förstå befintliga kvoter och användningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="6432b-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="6432b-111">Kvot eller parameter</span><span class="sxs-lookup"><span data-stu-id="6432b-111">Quota or parameter</span></span> | <span data-ttu-id="6432b-112">Storlek</span><span class="sxs-lookup"><span data-stu-id="6432b-112">Size</span></span> | <span data-ttu-id="6432b-113">Uppdatera cykler</span><span class="sxs-lookup"><span data-stu-id="6432b-113">Refresh cycle</span></span> | <span data-ttu-id="6432b-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6432b-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="6432b-115">Dataområde</span><span class="sxs-lookup"><span data-stu-id="6432b-115">Data range</span></span> | <span data-ttu-id="6432b-116">30 dagar</span><span class="sxs-lookup"><span data-stu-id="6432b-116">30 days</span></span> | <span data-ttu-id="6432b-117">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="6432b-117">Every query</span></span> | <span data-ttu-id="6432b-118">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="6432b-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="6432b-119">Resultatuppsättning</span><span class="sxs-lookup"><span data-stu-id="6432b-119">Result set</span></span> | <span data-ttu-id="6432b-120">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="6432b-120">10,000 rows</span></span> | <span data-ttu-id="6432b-121">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="6432b-121">Every query</span></span> | <span data-ttu-id="6432b-122">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="6432b-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="6432b-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="6432b-123">Timeout</span></span> | <span data-ttu-id="6432b-124">10 minuter</span><span class="sxs-lookup"><span data-stu-id="6432b-124">10 minutes</span></span> | <span data-ttu-id="6432b-125">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="6432b-125">Every query</span></span> | <span data-ttu-id="6432b-126">Varje fråga kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="6432b-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="6432b-127">Om det inte är klart inom 10 minuter visar tjänsten ett fel.</span><span class="sxs-lookup"><span data-stu-id="6432b-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="6432b-128">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="6432b-128">CPU resources</span></span> | <span data-ttu-id="6432b-129">Baserat på klientorganisationens storlek</span><span class="sxs-lookup"><span data-stu-id="6432b-129">Based on tenant size</span></span> | <span data-ttu-id="6432b-130">- I timmen och sedan var 15:e minut</span><span class="sxs-lookup"><span data-stu-id="6432b-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="6432b-131">- Dagligen vid 12 midnatt</span><span class="sxs-lookup"><span data-stu-id="6432b-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="6432b-132">Tjänsten tillämpar den dagliga kvoten och 15-minuterskvoten separat.</span><span class="sxs-lookup"><span data-stu-id="6432b-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="6432b-133">För varje kvot visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av de tilldelade resurserna.</span><span class="sxs-lookup"><span data-stu-id="6432b-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="6432b-134">Frågor blockeras om klientorganisationen har nått 100 % till efter nästa dagliga eller 15-minuterscykel.</span><span class="sxs-lookup"><span data-stu-id="6432b-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="6432b-135">En separat uppsättning kvoter och parametrar gäller för avancerade sökningsfrågor som utförs via API:t.</span><span class="sxs-lookup"><span data-stu-id="6432b-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="6432b-136">Läs mer om avancerade API:er för sökning</span><span class="sxs-lookup"><span data-stu-id="6432b-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="6432b-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6432b-137">Related topics</span></span>

- [<span data-ttu-id="6432b-138">Avancerade metodtips för sökning</span><span class="sxs-lookup"><span data-stu-id="6432b-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6432b-139">Hantera avancerade sökfel</span><span class="sxs-lookup"><span data-stu-id="6432b-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="6432b-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6432b-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6432b-141">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="6432b-141">Custom detections overview</span></span>](custom-detections-overview.md)