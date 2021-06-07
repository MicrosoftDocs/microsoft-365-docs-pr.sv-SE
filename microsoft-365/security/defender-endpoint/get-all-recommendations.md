---
title: Lista alla rekommendationer
description: Hämtar en lista över alla säkerhetsrekommendationer som påverkar organisationen.
keywords: apis, graph api, api som stöds, få, säkerhetsrekommendationer, Microsoft Defender för Endpoint tvm api, Hantering av hot och säkerhetsrisker, Hantering av hot och säkerhetsrisker api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768939"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="6b0d6-104">Lista alla rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b0d6-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b0d6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6b0d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b0d6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b0d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b0d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b0d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6b0d6-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6b0d6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b0d6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6b0d6-110">Hämtar en lista över alla säkerhetsrekommendationer som påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="6b0d6-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6b0d6-111">Permissions</span></span>
<span data-ttu-id="6b0d6-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6b0d6-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6b0d6-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="6b0d6-114">Permission type</span></span> |   <span data-ttu-id="6b0d6-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="6b0d6-115">Permission</span></span>  |   <span data-ttu-id="6b0d6-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="6b0d6-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6b0d6-117">Program</span><span class="sxs-lookup"><span data-stu-id="6b0d6-117">Application</span></span> |   <span data-ttu-id="6b0d6-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="6b0d6-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="6b0d6-119">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="6b0d6-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="6b0d6-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="6b0d6-120">Delegated (work or school account)</span></span> | <span data-ttu-id="6b0d6-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="6b0d6-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="6b0d6-122">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="6b0d6-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6b0d6-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="6b0d6-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="6b0d6-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="6b0d6-124">Request headers</span></span>

<span data-ttu-id="6b0d6-125">Namn</span><span class="sxs-lookup"><span data-stu-id="6b0d6-125">Name</span></span> | <span data-ttu-id="6b0d6-126">Typ</span><span class="sxs-lookup"><span data-stu-id="6b0d6-126">Type</span></span> | <span data-ttu-id="6b0d6-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6b0d6-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="6b0d6-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="6b0d6-128">Authorization</span></span> | <span data-ttu-id="6b0d6-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="6b0d6-129">String</span></span> | <span data-ttu-id="6b0d6-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-130">Bearer {token}.</span></span> <span data-ttu-id="6b0d6-131">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6b0d6-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6b0d6-132">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="6b0d6-132">Request body</span></span>
<span data-ttu-id="6b0d6-133">Tom</span><span class="sxs-lookup"><span data-stu-id="6b0d6-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6b0d6-134">Svar</span><span class="sxs-lookup"><span data-stu-id="6b0d6-134">Response</span></span>
<span data-ttu-id="6b0d6-135">Om det lyckas returnerar den här metoden 200 OK med listan med säkerhetsrekommendationer i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="6b0d6-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="6b0d6-136">Example</span></span>

<span data-ttu-id="6b0d6-137">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="6b0d6-137">**Request**</span></span>

<span data-ttu-id="6b0d6-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="6b0d6-139">**Svar**</span><span class="sxs-lookup"><span data-stu-id="6b0d6-139">**Response**</span></span>

<span data-ttu-id="6b0d6-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="6b0d6-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="6b0d6-141">Se även</span><span class="sxs-lookup"><span data-stu-id="6b0d6-141">See also</span></span>
- [<span data-ttu-id="6b0d6-142">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6b0d6-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6b0d6-143">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="6b0d6-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

