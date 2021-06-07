---
title: Lista sårbarheter efter rekommendation
description: Hämtar en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationerna.
keywords: apis, graph api, api som stöds, få, lista över säkerhetsproblem, säkerhetsrekommendationer, säkerhetsrekommendationer för säkerhetsproblem, Hantering av hot och säkerhetsrisker, Hantering av hot och säkerhetsrisker api
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
ms.openlocfilehash: 8fc9bb53fd2cfe768710129704c13ee751a695a2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770451"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="f02f8-104">Lista sårbarheter efter rekommendation</span><span class="sxs-lookup"><span data-stu-id="f02f8-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f02f8-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f02f8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f02f8-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f02f8-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f02f8-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f02f8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f02f8-108">Hämtar en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="f02f8-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="f02f8-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="f02f8-109">Permissions</span></span>
<span data-ttu-id="f02f8-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="f02f8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f02f8-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="f02f8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f02f8-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="f02f8-112">Permission type</span></span> |   <span data-ttu-id="f02f8-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="f02f8-113">Permission</span></span>  |   <span data-ttu-id="f02f8-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="f02f8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f02f8-115">Program</span><span class="sxs-lookup"><span data-stu-id="f02f8-115">Application</span></span> |   <span data-ttu-id="f02f8-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="f02f8-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="f02f8-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="f02f8-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="f02f8-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="f02f8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="f02f8-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="f02f8-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="f02f8-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="f02f8-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f02f8-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="f02f8-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f02f8-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="f02f8-122">Request headers</span></span>

<span data-ttu-id="f02f8-123">Namn</span><span class="sxs-lookup"><span data-stu-id="f02f8-123">Name</span></span> | <span data-ttu-id="f02f8-124">Typ</span><span class="sxs-lookup"><span data-stu-id="f02f8-124">Type</span></span> | <span data-ttu-id="f02f8-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f02f8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="f02f8-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="f02f8-126">Authorization</span></span> | <span data-ttu-id="f02f8-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="f02f8-127">String</span></span> | <span data-ttu-id="f02f8-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f02f8-128">Bearer {token}.</span></span> <span data-ttu-id="f02f8-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="f02f8-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f02f8-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="f02f8-130">Request body</span></span>
<span data-ttu-id="f02f8-131">Tom</span><span class="sxs-lookup"><span data-stu-id="f02f8-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f02f8-132">Svar</span><span class="sxs-lookup"><span data-stu-id="f02f8-132">Response</span></span>
<span data-ttu-id="f02f8-133">Om den lyckas returnerar den här metoden 200 OK, med en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationern.</span><span class="sxs-lookup"><span data-stu-id="f02f8-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="f02f8-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="f02f8-134">Example</span></span>

<span data-ttu-id="f02f8-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="f02f8-135">**Request**</span></span>

<span data-ttu-id="f02f8-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="f02f8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="f02f8-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="f02f8-137">**Response**</span></span>

<span data-ttu-id="f02f8-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="f02f8-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="f02f8-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f02f8-139">Related topics</span></span>
- [<span data-ttu-id="f02f8-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="f02f8-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f02f8-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="f02f8-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
