---
title: Få rekommendation från Id
description: Hämtar en säkerhetsrekommendationer genom dess ID.
keywords: apis, graph api, api som stöds, få, säkerhetsrekommendationer, säkerhetsrekommendationer genom ID, hantering av hot och sårbarhet, api för hot och sårbarhetshantering
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199519"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="24c7b-104">Få rekommendation via ID</span><span class="sxs-lookup"><span data-stu-id="24c7b-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24c7b-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="24c7b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="24c7b-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="24c7b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24c7b-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="24c7b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="24c7b-108">Hämtar en säkerhetsrekommendationer genom dess ID.</span><span class="sxs-lookup"><span data-stu-id="24c7b-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="24c7b-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="24c7b-109">Permissions</span></span>
<span data-ttu-id="24c7b-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="24c7b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="24c7b-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="24c7b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="24c7b-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="24c7b-112">Permission type</span></span> |   <span data-ttu-id="24c7b-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="24c7b-113">Permission</span></span>  |   <span data-ttu-id="24c7b-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="24c7b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="24c7b-115">Program</span><span class="sxs-lookup"><span data-stu-id="24c7b-115">Application</span></span> |   <span data-ttu-id="24c7b-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="24c7b-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="24c7b-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="24c7b-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="24c7b-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="24c7b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="24c7b-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="24c7b-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="24c7b-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="24c7b-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="24c7b-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="24c7b-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="24c7b-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="24c7b-122">Request headers</span></span>

<span data-ttu-id="24c7b-123">Namn</span><span class="sxs-lookup"><span data-stu-id="24c7b-123">Name</span></span> | <span data-ttu-id="24c7b-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="24c7b-124">Type</span></span> | <span data-ttu-id="24c7b-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24c7b-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="24c7b-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="24c7b-126">Authorization</span></span> | <span data-ttu-id="24c7b-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="24c7b-127">String</span></span> | <span data-ttu-id="24c7b-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="24c7b-128">Bearer {token}.</span></span> <span data-ttu-id="24c7b-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="24c7b-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="24c7b-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="24c7b-130">Request body</span></span>
<span data-ttu-id="24c7b-131">Tom</span><span class="sxs-lookup"><span data-stu-id="24c7b-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="24c7b-132">Svar</span><span class="sxs-lookup"><span data-stu-id="24c7b-132">Response</span></span>
<span data-ttu-id="24c7b-133">Om det lyckas returnerar den här metoden 200 OK med säkerhetsrekommendationerna i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="24c7b-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="24c7b-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="24c7b-134">Example</span></span>

<span data-ttu-id="24c7b-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="24c7b-135">**Request**</span></span>

<span data-ttu-id="24c7b-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="24c7b-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="24c7b-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="24c7b-137">**Response**</span></span>

<span data-ttu-id="24c7b-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="24c7b-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="24c7b-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="24c7b-139">Related topics</span></span>
- [<span data-ttu-id="24c7b-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="24c7b-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="24c7b-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="24c7b-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
