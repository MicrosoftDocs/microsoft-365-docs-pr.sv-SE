---
title: Avancerade kvoter för sökning och användningsparametrar i Microsoft 365 Defender
description: Förstå olika kvoter och användningsparametrar (tjänstbegränsningar) som ser till att tjänsten för avancerad sökning är dynamisk
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 19606b06ff1a1369614bab533a949bc383c90ad3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072770"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="2b1e7-104">Avancerade kvoter för sökning och användningsparametrar</span><span class="sxs-lookup"><span data-stu-id="2b1e7-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2b1e7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2b1e7-105">**Applies to:**</span></span>
- <span data-ttu-id="2b1e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b1e7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2b1e7-107">För att hålla tjänstens prestanda och responsiva, anger avancerad sökning olika kvoter och användningsparametrar (kallas även "tjänstbegränsningar").</span><span class="sxs-lookup"><span data-stu-id="2b1e7-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="2b1e7-108">De här kvoter och parametrar som gäller för frågor körs manuellt och av [anpassade identifieringsregler.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="2b1e7-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="2b1e7-109">Kunder som kör flera frågor regelbundet bör spåra förbrukning och [använda optimeringstips för](advanced-hunting-best-practices.md) att minimera störningar.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="2b1e7-110">Se följande tabell för att förstå befintliga kvoter och användningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="2b1e7-111">Kvot eller parameter</span><span class="sxs-lookup"><span data-stu-id="2b1e7-111">Quota or parameter</span></span> | <span data-ttu-id="2b1e7-112">Storlek</span><span class="sxs-lookup"><span data-stu-id="2b1e7-112">Size</span></span> | <span data-ttu-id="2b1e7-113">Uppdatera cykler</span><span class="sxs-lookup"><span data-stu-id="2b1e7-113">Refresh cycle</span></span> | <span data-ttu-id="2b1e7-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2b1e7-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="2b1e7-115">Dataområde</span><span class="sxs-lookup"><span data-stu-id="2b1e7-115">Data range</span></span> | <span data-ttu-id="2b1e7-116">30 dagar</span><span class="sxs-lookup"><span data-stu-id="2b1e7-116">30 days</span></span> | <span data-ttu-id="2b1e7-117">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="2b1e7-117">Every query</span></span> | <span data-ttu-id="2b1e7-118">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="2b1e7-119">Resultatuppsättning</span><span class="sxs-lookup"><span data-stu-id="2b1e7-119">Result set</span></span> | <span data-ttu-id="2b1e7-120">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="2b1e7-120">10,000 rows</span></span> | <span data-ttu-id="2b1e7-121">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="2b1e7-121">Every query</span></span> | <span data-ttu-id="2b1e7-122">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="2b1e7-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="2b1e7-123">Timeout</span></span> | <span data-ttu-id="2b1e7-124">10 minuter</span><span class="sxs-lookup"><span data-stu-id="2b1e7-124">10 minutes</span></span> | <span data-ttu-id="2b1e7-125">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="2b1e7-125">Every query</span></span> | <span data-ttu-id="2b1e7-126">Varje fråga kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="2b1e7-127">Om det inte är klart inom 10 minuter visar tjänsten ett fel.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="2b1e7-128">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="2b1e7-128">CPU resources</span></span> | <span data-ttu-id="2b1e7-129">Baserat på klientorganisationens storlek</span><span class="sxs-lookup"><span data-stu-id="2b1e7-129">Based on tenant size</span></span> | <span data-ttu-id="2b1e7-130">- I timmen och sedan var 15:e minut</span><span class="sxs-lookup"><span data-stu-id="2b1e7-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="2b1e7-131">- Dagligen vid 12 midnatt</span><span class="sxs-lookup"><span data-stu-id="2b1e7-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="2b1e7-132">Tjänsten tillämpar den dagliga kvoten och 15-minuterskvoten separat.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="2b1e7-133">För varje kvot visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av de tilldelade resurserna.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="2b1e7-134">Frågor blockeras om klientorganisationen har nått 100 % till efter nästa dagliga eller 15-minuterscykel.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="2b1e7-135">En separat uppsättning kvoter och parametrar gäller för avancerade sökningsfrågor som utförs via API:t.</span><span class="sxs-lookup"><span data-stu-id="2b1e7-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="2b1e7-136">Läs mer om avancerade API:er för sökning</span><span class="sxs-lookup"><span data-stu-id="2b1e7-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="2b1e7-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2b1e7-137">Related topics</span></span>

- [<span data-ttu-id="2b1e7-138">Avancerade metodtips för sökning</span><span class="sxs-lookup"><span data-stu-id="2b1e7-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2b1e7-139">Hantera avancerade sökfel</span><span class="sxs-lookup"><span data-stu-id="2b1e7-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="2b1e7-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="2b1e7-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2b1e7-141">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="2b1e7-141">Custom detections overview</span></span>](custom-detections-overview.md)