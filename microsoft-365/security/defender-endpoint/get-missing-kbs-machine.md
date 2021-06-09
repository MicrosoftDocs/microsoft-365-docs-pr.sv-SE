---
title: Få saknade KBs efter enhets-ID
description: Hämtar säkerhetsuppdateringar efter enhets-ID
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, enhets-ID, & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845240"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="907e2-104">Få saknade KBs efter enhets-ID</span><span class="sxs-lookup"><span data-stu-id="907e2-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="907e2-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="907e2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="907e2-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="907e2-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="907e2-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="907e2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="907e2-108">Hämtar saknade KBs (säkerhetsuppdateringar) efter enhets-ID</span><span class="sxs-lookup"><span data-stu-id="907e2-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="907e2-109">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="907e2-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="907e2-110">Sidhuvud för begäran</span><span class="sxs-lookup"><span data-stu-id="907e2-110">Request header</span></span>

<span data-ttu-id="907e2-111">Namn</span><span class="sxs-lookup"><span data-stu-id="907e2-111">Name</span></span> | <span data-ttu-id="907e2-112">Typ</span><span class="sxs-lookup"><span data-stu-id="907e2-112">Type</span></span> | <span data-ttu-id="907e2-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="907e2-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="907e2-114">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="907e2-114">Authorization</span></span> | <span data-ttu-id="907e2-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="907e2-115">String</span></span> | <span data-ttu-id="907e2-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="907e2-116">Bearer {token}.</span></span> <span data-ttu-id="907e2-117">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="907e2-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="907e2-118">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="907e2-118">Request body</span></span>

<span data-ttu-id="907e2-119">Tom</span><span class="sxs-lookup"><span data-stu-id="907e2-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="907e2-120">Svar</span><span class="sxs-lookup"><span data-stu-id="907e2-120">Response</span></span>

<span data-ttu-id="907e2-121">Om den lyckas returnerar den här metoden 200 OK, när den angivna enheten saknar KB-data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="907e2-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="907e2-122">Exempel</span><span class="sxs-lookup"><span data-stu-id="907e2-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="907e2-123">Begäran</span><span class="sxs-lookup"><span data-stu-id="907e2-123">Request</span></span>

<span data-ttu-id="907e2-124">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="907e2-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="907e2-125">Svar</span><span class="sxs-lookup"><span data-stu-id="907e2-125">Response</span></span>

<span data-ttu-id="907e2-126">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="907e2-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="907e2-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="907e2-127">Related topics</span></span>

- [<span data-ttu-id="907e2-128">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="907e2-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="907e2-129">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="907e2-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
