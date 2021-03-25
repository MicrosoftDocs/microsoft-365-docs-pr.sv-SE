---
title: Hämta programvara genom Id
description: Hämtar en lista över exponeringsresultat per enhetsgrupp.
keywords: apis, graph api, api som stöds, skaffa, programvara, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198595"
---
# <a name="get-software-by-id"></a><span data-ttu-id="c8962-104">Hämta programvara genom Id</span><span class="sxs-lookup"><span data-stu-id="c8962-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8962-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c8962-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c8962-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c8962-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8962-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c8962-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c8962-108">Hämtar programvaruinformation efter ID.</span><span class="sxs-lookup"><span data-stu-id="c8962-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="c8962-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c8962-109">Permissions</span></span>
<span data-ttu-id="c8962-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="c8962-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c8962-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="c8962-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c8962-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="c8962-112">Permission type</span></span> |   <span data-ttu-id="c8962-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="c8962-113">Permission</span></span>  |   <span data-ttu-id="c8962-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="c8962-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c8962-115">Program</span><span class="sxs-lookup"><span data-stu-id="c8962-115">Application</span></span> | <span data-ttu-id="c8962-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c8962-116">Software.Read.All</span></span> | <span data-ttu-id="c8962-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="c8962-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c8962-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="c8962-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c8962-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c8962-119">Software.Read</span></span> | <span data-ttu-id="c8962-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="c8962-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c8962-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="c8962-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="c8962-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="c8962-122">Request headers</span></span>

| <span data-ttu-id="c8962-123">Namn</span><span class="sxs-lookup"><span data-stu-id="c8962-123">Name</span></span>        | <span data-ttu-id="c8962-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="c8962-124">Type</span></span> | <span data-ttu-id="c8962-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8962-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="c8962-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="c8962-126">Authorization</span></span> | <span data-ttu-id="c8962-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8962-127">String</span></span> | <span data-ttu-id="c8962-128">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="c8962-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c8962-129">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="c8962-129">Request body</span></span>
<span data-ttu-id="c8962-130">Tom</span><span class="sxs-lookup"><span data-stu-id="c8962-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c8962-131">Svar</span><span class="sxs-lookup"><span data-stu-id="c8962-131">Response</span></span>
<span data-ttu-id="c8962-132">Om det lyckas returnerar den här metoden 200 OK med angivna programvarudata i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="c8962-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="c8962-133">Exempel</span><span class="sxs-lookup"><span data-stu-id="c8962-133">Example</span></span>

<span data-ttu-id="c8962-134">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="c8962-134">**Request**</span></span>

<span data-ttu-id="c8962-135">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="c8962-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="c8962-136">**Svar**</span><span class="sxs-lookup"><span data-stu-id="c8962-136">**Response**</span></span>

<span data-ttu-id="c8962-137">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="c8962-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="c8962-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c8962-138">Related topics</span></span>
- [<span data-ttu-id="c8962-139">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="c8962-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c8962-140">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="c8962-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)