---
title: Få rekommendation från Id
description: Hämtar en säkerhetsrekommendationer genom dess ID.
keywords: apis, graph api, api som stöds, få, säkerhetsrekommendationer, säkerhetsrekommendationer genom ID, Hantering av hot och säkerhetsrisker, Hantering av hot och säkerhetsrisker api
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
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771807"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="46fa6-104">Hämta rekommendation efter ID</span><span class="sxs-lookup"><span data-stu-id="46fa6-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="46fa6-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="46fa6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="46fa6-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="46fa6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="46fa6-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="46fa6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="46fa6-108">Hämtar en säkerhetsrekommendationer genom dess ID.</span><span class="sxs-lookup"><span data-stu-id="46fa6-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="46fa6-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="46fa6-109">Permissions</span></span>
<span data-ttu-id="46fa6-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="46fa6-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="46fa6-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="46fa6-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="46fa6-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="46fa6-112">Permission type</span></span> |   <span data-ttu-id="46fa6-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="46fa6-113">Permission</span></span>  |   <span data-ttu-id="46fa6-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="46fa6-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="46fa6-115">Program</span><span class="sxs-lookup"><span data-stu-id="46fa6-115">Application</span></span> |   <span data-ttu-id="46fa6-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="46fa6-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="46fa6-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="46fa6-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="46fa6-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="46fa6-118">Delegated (work or school account)</span></span> | <span data-ttu-id="46fa6-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="46fa6-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="46fa6-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="46fa6-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="46fa6-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="46fa6-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="46fa6-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="46fa6-122">Request headers</span></span>

<span data-ttu-id="46fa6-123">Namn</span><span class="sxs-lookup"><span data-stu-id="46fa6-123">Name</span></span> | <span data-ttu-id="46fa6-124">Typ</span><span class="sxs-lookup"><span data-stu-id="46fa6-124">Type</span></span> | <span data-ttu-id="46fa6-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="46fa6-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="46fa6-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="46fa6-126">Authorization</span></span> | <span data-ttu-id="46fa6-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="46fa6-127">String</span></span> | <span data-ttu-id="46fa6-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="46fa6-128">Bearer {token}.</span></span> <span data-ttu-id="46fa6-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="46fa6-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="46fa6-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="46fa6-130">Request body</span></span>
<span data-ttu-id="46fa6-131">Tom</span><span class="sxs-lookup"><span data-stu-id="46fa6-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="46fa6-132">Svar</span><span class="sxs-lookup"><span data-stu-id="46fa6-132">Response</span></span>
<span data-ttu-id="46fa6-133">Om det lyckas returnerar den här metoden 200 OK med säkerhetsrekommendationerna i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="46fa6-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="46fa6-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="46fa6-134">Example</span></span>

<span data-ttu-id="46fa6-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="46fa6-135">**Request**</span></span>

<span data-ttu-id="46fa6-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="46fa6-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="46fa6-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="46fa6-137">**Response**</span></span>

<span data-ttu-id="46fa6-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="46fa6-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="46fa6-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="46fa6-139">Related topics</span></span>
- [<span data-ttu-id="46fa6-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="46fa6-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="46fa6-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="46fa6-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
