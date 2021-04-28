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
ms.openlocfilehash: 7bae413028a0add7e5288e52bc3184e30f319c46
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073845"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="98a00-104">Information om Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="98a00-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="98a00-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="98a00-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="98a00-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="98a00-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="98a00-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="98a00-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="98a00-108">Följande information innehåller uppdateringar av Microsoft Defender för slutpunkts-API:er och datum då de gjordes.</span><span class="sxs-lookup"><span data-stu-id="98a00-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="98a00-109">RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:</span><span class="sxs-lookup"><span data-stu-id="98a00-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="98a00-110">Versionsanteckningar – nyaste till äldsta</span><span class="sxs-lookup"><span data-stu-id="98a00-110">Release notes - newest to oldest</span></span>

### <a name="10022021"></a><span data-ttu-id="98a00-111">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="98a00-111">10.02.2021</span></span>

- <span data-ttu-id="98a00-112">Nytt API har lagts till: [Batchuppdateringsaviseringar](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="98a00-112">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="98a00-113">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="98a00-113">25.01.2021</span></span>

- <span data-ttu-id="98a00-114">Uppdaterade räntebegränsningar [för Advanced Hunting API](run-advanced-query-api.md) från 15 till 45 förfrågningar per minut.</span><span class="sxs-lookup"><span data-stu-id="98a00-114">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="98a00-115">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="98a00-115">21.01.2021</span></span>

- <span data-ttu-id="98a00-116">Nytt API har lagts till: [Hitta enheter efter tagg.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="98a00-116">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="98a00-117">Nytt API har lagts till: [Importindikatorer](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="98a00-117">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="98a00-118">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="98a00-118">03.01.2021</span></span>

- <span data-ttu-id="98a00-119">Uppdaterade aviserings bevis: lade till ***detectionStatus** _, _*_parentProcessFilePath_*_ och _ *_parentProcessFileName_** egenskaper.</span><span class="sxs-lookup"><span data-stu-id="98a00-119">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="98a00-120">Uppdaterad [avisering entitet:](alerts.md)lade ***till egenskapen id-egenskap.***</span><span class="sxs-lookup"><span data-stu-id="98a00-120">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="98a00-121">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="98a00-121">15.12.2020</span></span>

- <span data-ttu-id="98a00-122">Uppdaterad [](machine.md) enhetsentitet: ***IpInterfaces-lista*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="98a00-122">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="98a00-123">Se [Listenheter](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="98a00-123">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="98a00-124">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="98a00-124">04.11.2020</span></span>

- <span data-ttu-id="98a00-125">Nytt API har lagts till: [Ange enhetsvärde](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="98a00-125">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="98a00-126">Uppdaterade [enhetsentitet:](machine.md) egenskapen ***deviceValue*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="98a00-126">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="98a00-127">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="98a00-127">01.09.2020</span></span>

- <span data-ttu-id="98a00-128">Lade till alternativ för att expandera aviseringsenheten med tillhörande bevis.</span><span class="sxs-lookup"><span data-stu-id="98a00-128">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="98a00-129">Visa [listaviseringar](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="98a00-129">See [List Alerts](get-alerts.md).</span></span>
