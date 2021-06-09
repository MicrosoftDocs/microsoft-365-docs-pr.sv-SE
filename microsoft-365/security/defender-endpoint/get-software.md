---
title: Lista programvara
description: Hämtar en lista över programvaruinventering
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaruinventering, & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844280"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="b1528-104">Lista API för programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="b1528-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1528-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b1528-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b1528-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b1528-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1528-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b1528-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b1528-108">Hämtar organisationens programvaruinventering.</span><span class="sxs-lookup"><span data-stu-id="b1528-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="b1528-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b1528-109">Permissions</span></span>
<span data-ttu-id="b1528-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b1528-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b1528-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="b1528-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b1528-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b1528-112">Permission type</span></span> |   <span data-ttu-id="b1528-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b1528-113">Permission</span></span>  |   <span data-ttu-id="b1528-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b1528-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b1528-115">Program</span><span class="sxs-lookup"><span data-stu-id="b1528-115">Application</span></span> |<span data-ttu-id="b1528-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b1528-116">Software.Read.All</span></span> |    <span data-ttu-id="b1528-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="b1528-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b1528-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b1528-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b1528-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b1528-119">Software.Read</span></span> |    <span data-ttu-id="b1528-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="b1528-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b1528-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b1528-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="b1528-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b1528-122">Request headers</span></span>

<span data-ttu-id="b1528-123">Namn</span><span class="sxs-lookup"><span data-stu-id="b1528-123">Name</span></span> | <span data-ttu-id="b1528-124">Typ</span><span class="sxs-lookup"><span data-stu-id="b1528-124">Type</span></span> | <span data-ttu-id="b1528-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b1528-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b1528-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b1528-126">Authorization</span></span> | <span data-ttu-id="b1528-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="b1528-127">String</span></span> | <span data-ttu-id="b1528-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b1528-128">Bearer {token}.</span></span> <span data-ttu-id="b1528-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="b1528-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b1528-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b1528-130">Request body</span></span>
<span data-ttu-id="b1528-131">Tom</span><span class="sxs-lookup"><span data-stu-id="b1528-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b1528-132">Svar</span><span class="sxs-lookup"><span data-stu-id="b1528-132">Response</span></span>
<span data-ttu-id="b1528-133">Om det lyckas returnerar den här metoden 200 OK med programvaruinventeringen i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="b1528-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b1528-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="b1528-134">Example</span></span>

<span data-ttu-id="b1528-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b1528-135">**Request**</span></span>

<span data-ttu-id="b1528-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b1528-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="b1528-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="b1528-137">**Response**</span></span>

<span data-ttu-id="b1528-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="b1528-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b1528-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b1528-139">Related topics</span></span>
- [<span data-ttu-id="b1528-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="b1528-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b1528-141">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="b1528-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
