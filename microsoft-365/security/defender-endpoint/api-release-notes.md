---
title: Information om Microsoft Defender för Endpoint API
description: Information om uppdateringar av Microsoft Defender för slutpunktsuppsättningen API:er.
keywords: Information om Microsoft Defender för endpoint API– utgivningsanteckningar, mde- och API:er, Microsoft Defender för slutpunkts-API, uppdateringar, anteckningar, utgivning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5093bf64614f30c7daa145484453d7c9000ef2c7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060891"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="11911-104">Information om Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="11911-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="11911-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="11911-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="11911-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="11911-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="11911-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="11911-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="11911-108">Följande information innehåller uppdateringar av Microsoft Defender för slutpunkts-API:er och datum då de gjordes.</span><span class="sxs-lookup"><span data-stu-id="11911-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="11911-109">RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:</span><span class="sxs-lookup"><span data-stu-id="11911-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```


## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="11911-110">Versionsanteckningar – nyaste till äldsta</span><span class="sxs-lookup"><span data-stu-id="11911-110">Release notes - newest to oldest</span></span>

### <a name="23042021"></a><span data-ttu-id="11911-111">23.04.2021</span><span class="sxs-lookup"><span data-stu-id="11911-111">23.04.2021</span></span>

- <span data-ttu-id="11911-112">Nytt API har lagts till: [Metoder och egenskaper för åtgärdsaktivitet.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="11911-112">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="11911-113">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="11911-113">10.02.2021</span></span>

- <span data-ttu-id="11911-114">Nytt API har lagts till: [Batchuppdateringsaviseringar](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="11911-114">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="11911-115">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="11911-115">25.01.2021</span></span>

- <span data-ttu-id="11911-116">Uppdaterade räntebegränsningar [för Advanced Hunting API](run-advanced-query-api.md) från 15 till 45 förfrågningar per minut.</span><span class="sxs-lookup"><span data-stu-id="11911-116">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="11911-117">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="11911-117">21.01.2021</span></span>

- <span data-ttu-id="11911-118">Nytt API har lagts till: [Hitta enheter efter tagg.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="11911-118">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="11911-119">Nytt API har lagts till: [Importindikatorer](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="11911-119">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="11911-120">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="11911-120">03.01.2021</span></span>

- <span data-ttu-id="11911-121">Uppdaterade aviserings bevis: lade till ***detectionStatus** _, _*_parentProcessFilePath_*_ och _ *_parentProcessFileName_** egenskaper.</span><span class="sxs-lookup"><span data-stu-id="11911-121">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="11911-122">Uppdaterad [avisering entitet:](alerts.md)lade ***till egenskapen id-egenskap.***</span><span class="sxs-lookup"><span data-stu-id="11911-122">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="11911-123">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="11911-123">15.12.2020</span></span>

- <span data-ttu-id="11911-124">Uppdaterad [](machine.md) enhetsentitet: ***IpInterfaces-lista*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="11911-124">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="11911-125">Se [Listenheter](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="11911-125">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="11911-126">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="11911-126">04.11.2020</span></span>

- <span data-ttu-id="11911-127">Nytt API har lagts till: [Ange enhetsvärde](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="11911-127">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="11911-128">Uppdaterade [enhetsentitet:](machine.md) egenskapen ***deviceValue*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="11911-128">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="11911-129">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="11911-129">01.09.2020</span></span>

- <span data-ttu-id="11911-130">Lade till alternativ för att expandera aviseringsenheten med tillhörande bevis.</span><span class="sxs-lookup"><span data-stu-id="11911-130">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="11911-131">Visa [listaviseringar](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="11911-131">See [List Alerts](get-alerts.md).</span></span>
