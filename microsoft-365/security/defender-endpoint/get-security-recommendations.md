---
title: Få säkerhetsrekommendationer
description: Hämtar en samling säkerhetsrekommendationer relaterade till ett visst enhets-ID.
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, säkerhetsrekommendationer per enhet, hot & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 6c65926985c7c8a194ab87c44c3fc269488c463c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199778"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="1b2a4-104">Få säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="1b2a4-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b2a4-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1b2a4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1b2a4-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1b2a4-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1b2a4-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1b2a4-108">Hämtar en samling säkerhetsrekommendationer relaterade till ett visst enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="1b2a4-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1b2a4-109">Permissions</span></span>
<span data-ttu-id="1b2a4-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1b2a4-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1b2a4-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1b2a4-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="1b2a4-112">Permission type</span></span> |   <span data-ttu-id="1b2a4-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="1b2a4-113">Permission</span></span>  |   <span data-ttu-id="1b2a4-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="1b2a4-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1b2a4-115">Program</span><span class="sxs-lookup"><span data-stu-id="1b2a4-115">Application</span></span> | <span data-ttu-id="1b2a4-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="1b2a4-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="1b2a4-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="1b2a4-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1b2a4-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1b2a4-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1b2a4-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="1b2a4-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1b2a4-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="1b2a4-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1b2a4-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="1b2a4-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="1b2a4-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="1b2a4-122">Request headers</span></span>

<span data-ttu-id="1b2a4-123">Namn</span><span class="sxs-lookup"><span data-stu-id="1b2a4-123">Name</span></span> | <span data-ttu-id="1b2a4-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="1b2a4-124">Type</span></span> | <span data-ttu-id="1b2a4-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b2a4-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1b2a4-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="1b2a4-126">Authorization</span></span> | <span data-ttu-id="1b2a4-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="1b2a4-127">String</span></span> | <span data-ttu-id="1b2a4-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-128">Bearer {token}.</span></span> <span data-ttu-id="1b2a4-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="1b2a4-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1b2a4-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="1b2a4-130">Request body</span></span>
<span data-ttu-id="1b2a4-131">Tom</span><span class="sxs-lookup"><span data-stu-id="1b2a4-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1b2a4-132">Svar</span><span class="sxs-lookup"><span data-stu-id="1b2a4-132">Response</span></span>
<span data-ttu-id="1b2a4-133">Om det lyckas returnerar den här metoden 200 OK med säkerhetsrekommendationerna i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1b2a4-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="1b2a4-134">Example</span></span>

<span data-ttu-id="1b2a4-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="1b2a4-135">**Request**</span></span>

<span data-ttu-id="1b2a4-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="1b2a4-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="1b2a4-137">**Response**</span></span>

<span data-ttu-id="1b2a4-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="1b2a4-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="1b2a4-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1b2a4-139">Related topics</span></span>
- [<span data-ttu-id="1b2a4-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="1b2a4-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1b2a4-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="1b2a4-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
