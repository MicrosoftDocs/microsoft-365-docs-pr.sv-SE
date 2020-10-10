---
title: Avancerade jakt begränsningar i Microsoft Threat Protection
description: Förstå olika tjänst begränsningar som håller den avancerade jakt tjänsten tillgänglig
keywords: Avancerad jakt, Hot jakt, cyberterrorism Threat stöldskydd, Microsoft Threat Protection, Microsoft 365, MTP, m365, Sök, fråga, telemetri, schema, kusto, processor gräns, sessionsgräns, resurser, högsta resultat
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ad21b4241d7cbbcc85639a0a10b47971e5fcebcb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412700"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="979e6-104">Begränsningar för avancerad jakt tjänst</span><span class="sxs-lookup"><span data-stu-id="979e6-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="979e6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="979e6-105">**Applies to:**</span></span>
- <span data-ttu-id="979e6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="979e6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="979e6-107">För att hålla tjänsten igång och svarar kan avancerade jakt uppsättningar olika gränser för frågor som körs manuellt och enligt [anpassade identifierings regler](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="979e6-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="979e6-108">Se tabellen nedan för att förstå dessa gränser.</span><span class="sxs-lookup"><span data-stu-id="979e6-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="979e6-109">Sten</span><span class="sxs-lookup"><span data-stu-id="979e6-109">Limit</span></span> | <span data-ttu-id="979e6-110">Storlek</span><span class="sxs-lookup"><span data-stu-id="979e6-110">Size</span></span> | <span data-ttu-id="979e6-111">Uppdaterings cykel</span><span class="sxs-lookup"><span data-stu-id="979e6-111">Refresh cycle</span></span> | <span data-ttu-id="979e6-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="979e6-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="979e6-113">Data område</span><span class="sxs-lookup"><span data-stu-id="979e6-113">Data range</span></span> | <span data-ttu-id="979e6-114">30 dagar</span><span class="sxs-lookup"><span data-stu-id="979e6-114">30 days</span></span> | <span data-ttu-id="979e6-115">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="979e6-115">Every query</span></span> | <span data-ttu-id="979e6-116">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="979e6-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="979e6-117">Resultat uppsättning</span><span class="sxs-lookup"><span data-stu-id="979e6-117">Result set</span></span> | <span data-ttu-id="979e6-118">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="979e6-118">10,000 rows</span></span> | <span data-ttu-id="979e6-119">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="979e6-119">Every query</span></span> | <span data-ttu-id="979e6-120">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="979e6-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="979e6-121">Kort</span><span class="sxs-lookup"><span data-stu-id="979e6-121">Timeout</span></span> | <span data-ttu-id="979e6-122">10 minuter</span><span class="sxs-lookup"><span data-stu-id="979e6-122">10 minutes</span></span> | <span data-ttu-id="979e6-123">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="979e6-123">Every query</span></span> | <span data-ttu-id="979e6-124">Alla frågor kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="979e6-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="979e6-125">Om den inte slutförs inom 10 minuter visas ett fel.</span><span class="sxs-lookup"><span data-stu-id="979e6-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="979e6-126">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="979e6-126">CPU resources</span></span> | <span data-ttu-id="979e6-127">Baserat på innehavarens storlek</span><span class="sxs-lookup"><span data-stu-id="979e6-127">Based on tenant size</span></span> | <span data-ttu-id="979e6-128">-På timme och sedan var 15: e minut</span><span class="sxs-lookup"><span data-stu-id="979e6-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="979e6-129">-Per dag 12 midnatt</span><span class="sxs-lookup"><span data-stu-id="979e6-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="979e6-130">Tjänsten tillämpar varje dag och 15-minuters gräns separat.</span><span class="sxs-lookup"><span data-stu-id="979e6-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="979e6-131">För varje gräns [visas ett fel](advanced-hunting-errors.md) när en fråga körs och innehavaren har konsumerat över 10% av tilldelade resurser.</span><span class="sxs-lookup"><span data-stu-id="979e6-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="979e6-132">Frågor blockeras om klient organisationen har nått 100% fram till efter nästa dagliga eller 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="979e6-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="979e6-133">En separat uppsättning begränsningar gäller för avancerade frågor som genomförs via API.</span><span class="sxs-lookup"><span data-stu-id="979e6-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="979e6-134">Läsa om avancerade API: er för jakt</span><span class="sxs-lookup"><span data-stu-id="979e6-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="979e6-135">Kunder som ofta kör flera frågor bör spåra förbrukningen och [tillämpa optimerings metod tips](advanced-hunting-best-practices.md) för att minimera störningar som orsakas av de här gränserna.</span><span class="sxs-lookup"><span data-stu-id="979e6-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="979e6-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="979e6-136">Related topics</span></span>

- [<span data-ttu-id="979e6-137">Avancerade råd om att få råd</span><span class="sxs-lookup"><span data-stu-id="979e6-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="979e6-138">Hantera avancerade jakt fel</span><span class="sxs-lookup"><span data-stu-id="979e6-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="979e6-139">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="979e6-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="979e6-140">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="979e6-140">Custom detections overview</span></span>](custom-detections-overview.md)
