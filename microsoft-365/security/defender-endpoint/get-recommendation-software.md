---
title: Få rekommendation från programvara
description: Hämtar en säkerhetsrekommendationer för en viss programvara.
keywords: apis, graph api, API som stöds, få, säkerhetsrekommendationer, säkerhetsrekommendationer för programvara, hot och sårbarhetshantering, API för hot och sårbarhetshantering
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199507"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="d9010-104">Få rekommendation från programvara</span><span class="sxs-lookup"><span data-stu-id="d9010-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d9010-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d9010-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="d9010-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d9010-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9010-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d9010-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d9010-108">Hämtar en säkerhetsrekommendationer för en viss programvara.</span><span class="sxs-lookup"><span data-stu-id="d9010-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="d9010-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="d9010-109">Permissions</span></span>
<span data-ttu-id="d9010-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="d9010-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d9010-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="d9010-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="d9010-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="d9010-112">Permission type</span></span> |   <span data-ttu-id="d9010-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d9010-113">Permission</span></span>  |   <span data-ttu-id="d9010-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="d9010-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d9010-115">Program</span><span class="sxs-lookup"><span data-stu-id="d9010-115">Application</span></span> |   <span data-ttu-id="d9010-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="d9010-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="d9010-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="d9010-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="d9010-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="d9010-118">Delegated (work or school account)</span></span> | <span data-ttu-id="d9010-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="d9010-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="d9010-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="d9010-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="d9010-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="d9010-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="d9010-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="d9010-122">Request headers</span></span>

<span data-ttu-id="d9010-123">Namn</span><span class="sxs-lookup"><span data-stu-id="d9010-123">Name</span></span> | <span data-ttu-id="d9010-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="d9010-124">Type</span></span> | <span data-ttu-id="d9010-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d9010-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9010-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="d9010-126">Authorization</span></span> | <span data-ttu-id="d9010-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="d9010-127">String</span></span> | <span data-ttu-id="d9010-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d9010-128">Bearer {token}.</span></span> <span data-ttu-id="d9010-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="d9010-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d9010-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="d9010-130">Request body</span></span>
<span data-ttu-id="d9010-131">Tom</span><span class="sxs-lookup"><span data-stu-id="d9010-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d9010-132">Svar</span><span class="sxs-lookup"><span data-stu-id="d9010-132">Response</span></span>
<span data-ttu-id="d9010-133">Om det lyckas returnerar den här metoden 200 OK med programvaran som är kopplad till säkerhetsrekommendationerna i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="d9010-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="d9010-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="d9010-134">Example</span></span>

<span data-ttu-id="d9010-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="d9010-135">**Request**</span></span>

<span data-ttu-id="d9010-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="d9010-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="d9010-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="d9010-137">**Response**</span></span>

<span data-ttu-id="d9010-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="d9010-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="d9010-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d9010-139">Related topics</span></span>
- [<span data-ttu-id="d9010-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="d9010-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="d9010-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="d9010-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
