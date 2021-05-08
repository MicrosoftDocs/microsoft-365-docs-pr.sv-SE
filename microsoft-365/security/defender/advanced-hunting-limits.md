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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245606"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="af915-104">Avancerade kvoter för sökning och användningsparametrar</span><span class="sxs-lookup"><span data-stu-id="af915-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af915-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af915-105">**Applies to:**</span></span>
- <span data-ttu-id="af915-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af915-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="af915-107">För att hålla tjänstens prestanda och responsiva, anger avancerad sökning olika kvoter och användningsparametrar (kallas även "tjänstbegränsningar").</span><span class="sxs-lookup"><span data-stu-id="af915-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="af915-108">Dessa kvoter och parametrar gäller separat för frågor som körs manuellt och för frågor som körs med anpassade [identifieringsregler.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="af915-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="af915-109">Kunder som kör flera frågor regelbundet bör tänka på de här begränsningarna och [tillämpa optimeringstips för](advanced-hunting-best-practices.md) att minimera störningar.</span><span class="sxs-lookup"><span data-stu-id="af915-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="af915-110">Se följande tabell för att förstå befintliga kvoter och användningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="af915-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="af915-111">Kvot eller parameter</span><span class="sxs-lookup"><span data-stu-id="af915-111">Quota or parameter</span></span> | <span data-ttu-id="af915-112">Storlek</span><span class="sxs-lookup"><span data-stu-id="af915-112">Size</span></span> | <span data-ttu-id="af915-113">Uppdatera cykler</span><span class="sxs-lookup"><span data-stu-id="af915-113">Refresh cycle</span></span> | <span data-ttu-id="af915-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="af915-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="af915-115">Dataområde</span><span class="sxs-lookup"><span data-stu-id="af915-115">Data range</span></span> | <span data-ttu-id="af915-116">30 dagar</span><span class="sxs-lookup"><span data-stu-id="af915-116">30 days</span></span> | <span data-ttu-id="af915-117">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="af915-117">Every query</span></span> | <span data-ttu-id="af915-118">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="af915-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="af915-119">Resultatuppsättning</span><span class="sxs-lookup"><span data-stu-id="af915-119">Result set</span></span> | <span data-ttu-id="af915-120">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="af915-120">10,000 rows</span></span> | <span data-ttu-id="af915-121">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="af915-121">Every query</span></span> | <span data-ttu-id="af915-122">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="af915-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="af915-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="af915-123">Timeout</span></span> | <span data-ttu-id="af915-124">10 minuter</span><span class="sxs-lookup"><span data-stu-id="af915-124">10 minutes</span></span> | <span data-ttu-id="af915-125">Varje fråga</span><span class="sxs-lookup"><span data-stu-id="af915-125">Every query</span></span> | <span data-ttu-id="af915-126">Varje fråga kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="af915-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="af915-127">Om det inte är klart inom 10 minuter visar tjänsten ett fel.</span><span class="sxs-lookup"><span data-stu-id="af915-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="af915-128">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="af915-128">CPU resources</span></span> | <span data-ttu-id="af915-129">Baserat på klientorganisationens storlek</span><span class="sxs-lookup"><span data-stu-id="af915-129">Based on tenant size</span></span> | <span data-ttu-id="af915-130">Var 15:e minut</span><span class="sxs-lookup"><span data-stu-id="af915-130">Every 15 minutes</span></span> | <span data-ttu-id="af915-131">Portalen [visar ett fel när](advanced-hunting-errors.md) en fråga körs och klientorganisationen har förbrukat över 10 % av de allokerade resurserna.</span><span class="sxs-lookup"><span data-stu-id="af915-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="af915-132">Frågor blockeras om klientorganisationen har nått 100 % till efter den kommande 15-minuterscykeln.</span><span class="sxs-lookup"><span data-stu-id="af915-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="af915-133">En separat uppsättning kvoter och parametrar gäller för avancerade sökningsfrågor som utförs via API:t.</span><span class="sxs-lookup"><span data-stu-id="af915-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="af915-134">Läs mer om avancerade API:er för sökning</span><span class="sxs-lookup"><span data-stu-id="af915-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="af915-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="af915-135">Related topics</span></span>

- [<span data-ttu-id="af915-136">Avancerade metodtips för sökning</span><span class="sxs-lookup"><span data-stu-id="af915-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="af915-137">Hantera avancerade sökfel</span><span class="sxs-lookup"><span data-stu-id="af915-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="af915-138">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="af915-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af915-139">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="af915-139">Custom detections overview</span></span>](custom-detections-overview.md)