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
ms.openlocfilehash: 02fd995b04c1644e88b38fd0feebc2c80a3681ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933631"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="53a7e-104">Information om Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="53a7e-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="53a7e-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="53a7e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="53a7e-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="53a7e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53a7e-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="53a7e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="53a7e-108">Följande information innehåller uppdateringar av Microsoft Defender för slutpunkts-API:er och datum då de gjordes.</span><span class="sxs-lookup"><span data-stu-id="53a7e-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="53a7e-109">RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:</span><span class="sxs-lookup"><span data-stu-id="53a7e-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="53a7e-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="53a7e-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="53a7e-111">Nytt API har lagts till: [Batchuppdateringsaviseringar](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="53a7e-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="53a7e-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="53a7e-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="53a7e-113">Uppdaterade räntebegränsningar [för Advanced Hunting API](run-advanced-query-api.md) från 15 till 45 förfrågningar per minut.</span><span class="sxs-lookup"><span data-stu-id="53a7e-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="53a7e-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="53a7e-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="53a7e-115">Nytt API har lagts till: [Hitta enheter efter tagg.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="53a7e-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="53a7e-116">Nytt API har lagts till: [Importindikatorer](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="53a7e-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="53a7e-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="53a7e-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="53a7e-118">Uppdaterade aviserings bevis: lade till ***detectionStatus** _, _*_parentProcessFilePath_*_ och _ *_parentProcessFileName_** egenskaper.</span><span class="sxs-lookup"><span data-stu-id="53a7e-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="53a7e-119">Uppdaterad [avisering entitet:](alerts.md)lade ***till egenskapen id-egenskap.***</span><span class="sxs-lookup"><span data-stu-id="53a7e-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="53a7e-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="53a7e-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="53a7e-121">Uppdaterad [](machine.md) enhetsentitet: ***IpInterfaces-lista*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="53a7e-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="53a7e-122">Se [Listenheter](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="53a7e-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="53a7e-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="53a7e-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="53a7e-124">Nytt API har lagts till: [Ange enhetsvärde](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="53a7e-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="53a7e-125">Uppdaterade [enhetsentitet:](machine.md) egenskapen ***deviceValue*** tillagd.</span><span class="sxs-lookup"><span data-stu-id="53a7e-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="53a7e-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="53a7e-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="53a7e-127">Lade till alternativ för att expandera aviseringsenheten med tillhörande bevis.</span><span class="sxs-lookup"><span data-stu-id="53a7e-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="53a7e-128">Visa [listaviseringar](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="53a7e-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>