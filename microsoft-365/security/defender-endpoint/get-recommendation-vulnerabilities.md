---
title: Lista svagheter efter rekommendation
description: Hämtar en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationerna.
keywords: apis, graph api, API som stöds, få, lista över säkerhetsproblem, säkerhetsrekommendationer, säkerhetsrekommendationer för säkerhetsproblem, hantering av hot och risker, API för hot och sårbarhetshantering
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198607"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="3e4f5-104">Lista svagheter efter rekommendation</span><span class="sxs-lookup"><span data-stu-id="3e4f5-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e4f5-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3e4f5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="3e4f5-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3e4f5-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3e4f5-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3e4f5-108">Hämtar en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="3e4f5-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3e4f5-109">Permissions</span></span>
<span data-ttu-id="3e4f5-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3e4f5-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="3e4f5-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3e4f5-112">Permission type</span></span> |   <span data-ttu-id="3e4f5-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3e4f5-113">Permission</span></span>  |   <span data-ttu-id="3e4f5-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3e4f5-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3e4f5-115">Program</span><span class="sxs-lookup"><span data-stu-id="3e4f5-115">Application</span></span> |   <span data-ttu-id="3e4f5-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="3e4f5-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="3e4f5-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="3e4f5-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="3e4f5-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3e4f5-118">Delegated (work or school account)</span></span> | <span data-ttu-id="3e4f5-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="3e4f5-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="3e4f5-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="3e4f5-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3e4f5-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3e4f5-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="3e4f5-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="3e4f5-122">Request headers</span></span>

<span data-ttu-id="3e4f5-123">Namn</span><span class="sxs-lookup"><span data-stu-id="3e4f5-123">Name</span></span> | <span data-ttu-id="3e4f5-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="3e4f5-124">Type</span></span> | <span data-ttu-id="3e4f5-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3e4f5-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="3e4f5-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3e4f5-126">Authorization</span></span> | <span data-ttu-id="3e4f5-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="3e4f5-127">String</span></span> | <span data-ttu-id="3e4f5-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-128">Bearer {token}.</span></span> <span data-ttu-id="3e4f5-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3e4f5-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3e4f5-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="3e4f5-130">Request body</span></span>
<span data-ttu-id="3e4f5-131">Tom</span><span class="sxs-lookup"><span data-stu-id="3e4f5-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3e4f5-132">Svar</span><span class="sxs-lookup"><span data-stu-id="3e4f5-132">Response</span></span>
<span data-ttu-id="3e4f5-133">Om den lyckas returnerar den här metoden 200 OK, med en lista över säkerhetsproblem som är kopplade till säkerhetsrekommendationern.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="3e4f5-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="3e4f5-134">Example</span></span>

<span data-ttu-id="3e4f5-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="3e4f5-135">**Request**</span></span>

<span data-ttu-id="3e4f5-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="3e4f5-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="3e4f5-137">**Response**</span></span>

<span data-ttu-id="3e4f5-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="3e4f5-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="3e4f5-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3e4f5-139">Related topics</span></span>
- [<span data-ttu-id="3e4f5-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="3e4f5-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3e4f5-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="3e4f5-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
