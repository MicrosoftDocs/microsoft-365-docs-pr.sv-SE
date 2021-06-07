---
title: Få saknade KBs genom programvaru-ID
description: Hämtar säkerhetsuppdateringar som saknas med hjälp av programvaru-ID
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaru-ID, & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
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
ms.openlocfilehash: d9218ad447f926f0086801036277323e7c1efb4c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770568"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="c0e5e-104">Få saknade KBs genom programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="c0e5e-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0e5e-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c0e5e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c0e5e-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c0e5e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0e5e-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="c0e5e-108">Hämtar saknade KBs (säkerhetsuppdateringar) efter programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="c0e5e-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="c0e5e-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c0e5e-109">Permissions</span></span>

<span data-ttu-id="c0e5e-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c0e5e-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c0e5e-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="c0e5e-112">Permission type</span></span> |   <span data-ttu-id="c0e5e-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="c0e5e-113">Permission</span></span>   |   <span data-ttu-id="c0e5e-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="c0e5e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c0e5e-115">Program</span><span class="sxs-lookup"><span data-stu-id="c0e5e-115">Application</span></span> |<span data-ttu-id="c0e5e-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c0e5e-116">Software.Read.All</span></span> |   <span data-ttu-id="c0e5e-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="c0e5e-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c0e5e-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="c0e5e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c0e5e-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c0e5e-119">Software.Read</span></span> |   <span data-ttu-id="c0e5e-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="c0e5e-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c0e5e-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="c0e5e-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="c0e5e-122">Sidhuvud för begäran</span><span class="sxs-lookup"><span data-stu-id="c0e5e-122">Request header</span></span>

<span data-ttu-id="c0e5e-123">Namn</span><span class="sxs-lookup"><span data-stu-id="c0e5e-123">Name</span></span> | <span data-ttu-id="c0e5e-124">Typ</span><span class="sxs-lookup"><span data-stu-id="c0e5e-124">Type</span></span> | <span data-ttu-id="c0e5e-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c0e5e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0e5e-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="c0e5e-126">Authorization</span></span> | <span data-ttu-id="c0e5e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="c0e5e-127">String</span></span> | <span data-ttu-id="c0e5e-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-128">Bearer {token}.</span></span> <span data-ttu-id="c0e5e-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="c0e5e-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c0e5e-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="c0e5e-130">Request body</span></span>

<span data-ttu-id="c0e5e-131">Tom</span><span class="sxs-lookup"><span data-stu-id="c0e5e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c0e5e-132">Svar</span><span class="sxs-lookup"><span data-stu-id="c0e5e-132">Response</span></span>

<span data-ttu-id="c0e5e-133">Om det lyckas returnerar den här metoden 200 OK, när angiven programvara saknar KB-data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="c0e5e-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="c0e5e-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="c0e5e-135">Begäran</span><span class="sxs-lookup"><span data-stu-id="c0e5e-135">Request</span></span>

<span data-ttu-id="c0e5e-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="c0e5e-137">Svar</span><span class="sxs-lookup"><span data-stu-id="c0e5e-137">Response</span></span>

<span data-ttu-id="c0e5e-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="c0e5e-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="c0e5e-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c0e5e-139">Related topics</span></span>

- [<span data-ttu-id="c0e5e-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="c0e5e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c0e5e-141">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="c0e5e-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
