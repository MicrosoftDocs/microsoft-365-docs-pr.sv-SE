---
title: Avancerade begränsningar för sökning i Microsoft Defender ATP
description: Förstå olika tjänstbegränsningar som ser till att din avancerade service för sökning är dynamisk
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499531"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="00876-104">Avancerade servicebegränsningar för söktjänster</span><span class="sxs-lookup"><span data-stu-id="00876-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00876-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="00876-105">**Applies to:**</span></span>
- [<span data-ttu-id="00876-106">Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="00876-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="00876-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="00876-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="00876-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="00876-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="00876-109">För att tjänsten ska kunna köras snabbt och snabbt, anger avancerad sökning olika begränsningar för frågor som körs manuellt och enligt [anpassade identifieringsregler.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="00876-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="00876-110">Se följande tabell för att förstå de här begränsningarna.</span><span class="sxs-lookup"><span data-stu-id="00876-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="00876-111">Gräns</span><span class="sxs-lookup"><span data-stu-id="00876-111">Limit</span></span> | <span data-ttu-id="00876-112">Storlek</span><span class="sxs-lookup"><span data-stu-id="00876-112">Size</span></span> | <span data-ttu-id="00876-113">Uppdatera cykler</span><span class="sxs-lookup"><span data-stu-id="00876-113">Refresh cycle</span></span> | <span data-ttu-id="00876-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="00876-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="00876-115">Dataområde</span><span class="sxs-lookup"><span data-stu-id="00876-115">Data range</span></span> | <span data-ttu-id="00876-116">30 dagar</span><span class="sxs-lookup"><span data-stu-id="00876-116">30 days</span></span> | <span data-ttu-id="00876-117">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="00876-117">Every query</span></span> | <span data-ttu-id="00876-118">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="00876-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="00876-119">Resultatuppsättning</span><span class="sxs-lookup"><span data-stu-id="00876-119">Result set</span></span> | <span data-ttu-id="00876-120">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="00876-120">10,000 rows</span></span> | <span data-ttu-id="00876-121">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="00876-121">Every query</span></span> | <span data-ttu-id="00876-122">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="00876-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="00876-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="00876-123">Timeout</span></span> | <span data-ttu-id="00876-124">10 minuter</span><span class="sxs-lookup"><span data-stu-id="00876-124">10 minutes</span></span> | <span data-ttu-id="00876-125">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="00876-125">Every query</span></span> | <span data-ttu-id="00876-126">Varje fråga kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="00876-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="00876-127">Om det inte är klart inom 10 minuter visar tjänsten ett fel.</span><span class="sxs-lookup"><span data-stu-id="00876-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="00876-128">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="00876-128">CPU resources</span></span> | <span data-ttu-id="00876-129">Baserat på klientorganisationens storlek</span><span class="sxs-lookup"><span data-stu-id="00876-129">Based on tenant size</span></span> | <span data-ttu-id="00876-130">- I timmen och sedan var 15:e minut</span><span class="sxs-lookup"><span data-stu-id="00876-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="00876-131">- Dagligen vid 12 midnatt</span><span class="sxs-lookup"><span data-stu-id="00876-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="00876-132">Tjänsten tillämpar den dagliga och 15-minutersgränsen separat.</span><span class="sxs-lookup"><span data-stu-id="00876-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="00876-133">För varje gräns visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av de tilldelade resurserna.</span><span class="sxs-lookup"><span data-stu-id="00876-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="00876-134">Frågor blockeras om klientorganisationen har nått 100 % till efter nästa dagliga eller 15-minuterscykel.</span><span class="sxs-lookup"><span data-stu-id="00876-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="00876-135">En separat uppsättning begränsningar gäller för avancerade sökningsfrågor som utförs via API:t.</span><span class="sxs-lookup"><span data-stu-id="00876-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="00876-136">Läs mer om avancerade API:er för sökning</span><span class="sxs-lookup"><span data-stu-id="00876-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="00876-137">Kunder som kör flera frågor regelbundet [](advanced-hunting-best-practices.md) bör spåra förbrukning och använda optimeringstips för att minimera avbrottet, till följd av att de överskrider dessa gränser.</span><span class="sxs-lookup"><span data-stu-id="00876-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00876-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="00876-138">Related topics</span></span>

- [<span data-ttu-id="00876-139">Avancerade metodtips för sökning</span><span class="sxs-lookup"><span data-stu-id="00876-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="00876-140">Hantera avancerade sökfel</span><span class="sxs-lookup"><span data-stu-id="00876-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="00876-141">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="00876-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00876-142">Anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="00876-142">Custom detections rules</span></span>](custom-detection-rules.md)
