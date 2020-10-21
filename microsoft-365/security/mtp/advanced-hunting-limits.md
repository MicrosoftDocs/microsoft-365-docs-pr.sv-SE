---
title: Avancerade jakt kvoter och användnings parametrar i Microsoft Threat Protection
description: Förstå olika kvoter och användnings parametrar (tjänst begränsningar) som håller den avancerade jakt tjänsten tillgänglig
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, kusto, processor gräns, maxgräns, resurser, högsta resultat, kvot, parametrar, tilldelning
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636911"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="bf75a-104">Avancerade jakt kvoter och användnings parametrar</span><span class="sxs-lookup"><span data-stu-id="bf75a-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf75a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bf75a-105">**Applies to:**</span></span>
- <span data-ttu-id="bf75a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf75a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bf75a-107">För att hålla tjänsten igång och svarar kan de avancerade jaktarna ange olika kvoter och användnings parametrar (kallas även "tjänst gränser").</span><span class="sxs-lookup"><span data-stu-id="bf75a-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="bf75a-108">Dessa kvoter och parametrar gäller för frågor som körs manuellt och efter [anpassade identifierings regler](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="bf75a-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="bf75a-109">Kunder som ofta kör flera frågor bör spåra förbrukning och [tillämpa optimerings metod tips](advanced-hunting-best-practices.md) för att minimera störningar.</span><span class="sxs-lookup"><span data-stu-id="bf75a-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="bf75a-110">Se tabellen nedan för att förstå befintliga kvoter och användnings parametrar.</span><span class="sxs-lookup"><span data-stu-id="bf75a-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="bf75a-111">Kvot eller parameter</span><span class="sxs-lookup"><span data-stu-id="bf75a-111">Quota or parameter</span></span> | <span data-ttu-id="bf75a-112">Storlek</span><span class="sxs-lookup"><span data-stu-id="bf75a-112">Size</span></span> | <span data-ttu-id="bf75a-113">Uppdaterings cykel</span><span class="sxs-lookup"><span data-stu-id="bf75a-113">Refresh cycle</span></span> | <span data-ttu-id="bf75a-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bf75a-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="bf75a-115">Data område</span><span class="sxs-lookup"><span data-stu-id="bf75a-115">Data range</span></span> | <span data-ttu-id="bf75a-116">30 dagar</span><span class="sxs-lookup"><span data-stu-id="bf75a-116">30 days</span></span> | <span data-ttu-id="bf75a-117">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="bf75a-117">Every query</span></span> | <span data-ttu-id="bf75a-118">Varje fråga kan slå upp data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="bf75a-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="bf75a-119">Resultat uppsättning</span><span class="sxs-lookup"><span data-stu-id="bf75a-119">Result set</span></span> | <span data-ttu-id="bf75a-120">10 000 rader</span><span class="sxs-lookup"><span data-stu-id="bf75a-120">10,000 rows</span></span> | <span data-ttu-id="bf75a-121">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="bf75a-121">Every query</span></span> | <span data-ttu-id="bf75a-122">Varje fråga kan returnera upp till 10 000 poster.</span><span class="sxs-lookup"><span data-stu-id="bf75a-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="bf75a-123">Kort</span><span class="sxs-lookup"><span data-stu-id="bf75a-123">Timeout</span></span> | <span data-ttu-id="bf75a-124">10 minuter</span><span class="sxs-lookup"><span data-stu-id="bf75a-124">10 minutes</span></span> | <span data-ttu-id="bf75a-125">Alla frågor</span><span class="sxs-lookup"><span data-stu-id="bf75a-125">Every query</span></span> | <span data-ttu-id="bf75a-126">Alla frågor kan köras i upp till 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="bf75a-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="bf75a-127">Om den inte slutförs inom 10 minuter visas ett fel.</span><span class="sxs-lookup"><span data-stu-id="bf75a-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="bf75a-128">CPU-resurser</span><span class="sxs-lookup"><span data-stu-id="bf75a-128">CPU resources</span></span> | <span data-ttu-id="bf75a-129">Baserat på innehavarens storlek</span><span class="sxs-lookup"><span data-stu-id="bf75a-129">Based on tenant size</span></span> | <span data-ttu-id="bf75a-130">-På timme och sedan var 15: e minut</span><span class="sxs-lookup"><span data-stu-id="bf75a-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="bf75a-131">-Per dag 12 midnatt</span><span class="sxs-lookup"><span data-stu-id="bf75a-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="bf75a-132">Tjänsten tillämpar den dagliga och 15-minuters kvoten separat.</span><span class="sxs-lookup"><span data-stu-id="bf75a-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="bf75a-133">För varje kvot [visas ett fel](advanced-hunting-errors.md) när en fråga körs och innehavaren har konsumerat över 10% av tilldelade resurser.</span><span class="sxs-lookup"><span data-stu-id="bf75a-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="bf75a-134">Frågor blockeras om klient organisationen har nått 100% fram till efter nästa dagliga eller 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="bf75a-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="bf75a-135">En separat uppsättning kvoter och parametrar gäller för avancerade frågor som utförs via API.</span><span class="sxs-lookup"><span data-stu-id="bf75a-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="bf75a-136">Läsa om avancerade API: er för jakt</span><span class="sxs-lookup"><span data-stu-id="bf75a-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="bf75a-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bf75a-137">Related topics</span></span>

- [<span data-ttu-id="bf75a-138">Avancerade råd om att få råd</span><span class="sxs-lookup"><span data-stu-id="bf75a-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="bf75a-139">Hantera avancerade jakt fel</span><span class="sxs-lookup"><span data-stu-id="bf75a-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="bf75a-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="bf75a-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf75a-141">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="bf75a-141">Custom detections overview</span></span>](custom-detections-overview.md)