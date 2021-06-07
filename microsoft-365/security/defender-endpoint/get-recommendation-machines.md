---
title: Lista enheter enligt rekommendation
description: Hämtar en lista över enheter som är kopplade till säkerhetsrekommendationerna.
keywords: apis, graph api, api som stöds, få, säkerhetsrekommendationer för sårbara enheter, Hantering av hot och säkerhetsrisker, Hantering av hot och säkerhetsrisker api
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
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771819"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="6e9a8-104">Lista enheter enligt rekommendation</span><span class="sxs-lookup"><span data-stu-id="6e9a8-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e9a8-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6e9a8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="6e9a8-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6e9a8-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6e9a8-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6e9a8-108">Hämtar en lista över enheter som är kopplade till säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="6e9a8-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6e9a8-109">Permissions</span></span>
<span data-ttu-id="6e9a8-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6e9a8-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6e9a8-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="6e9a8-112">Permission type</span></span> |   <span data-ttu-id="6e9a8-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="6e9a8-113">Permission</span></span>  |   <span data-ttu-id="6e9a8-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="6e9a8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6e9a8-115">Program</span><span class="sxs-lookup"><span data-stu-id="6e9a8-115">Application</span></span> |   <span data-ttu-id="6e9a8-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e9a8-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="6e9a8-117">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="6e9a8-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="6e9a8-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="6e9a8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="6e9a8-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="6e9a8-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="6e9a8-120">"Läs rekommendationer om hot och sårbarhetshantering säkerhet"</span><span class="sxs-lookup"><span data-stu-id="6e9a8-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6e9a8-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="6e9a8-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="6e9a8-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="6e9a8-122">Request headers</span></span>

<span data-ttu-id="6e9a8-123">Namn</span><span class="sxs-lookup"><span data-stu-id="6e9a8-123">Name</span></span> | <span data-ttu-id="6e9a8-124">Typ</span><span class="sxs-lookup"><span data-stu-id="6e9a8-124">Type</span></span> | <span data-ttu-id="6e9a8-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6e9a8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="6e9a8-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="6e9a8-126">Authorization</span></span> | <span data-ttu-id="6e9a8-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="6e9a8-127">String</span></span> | <span data-ttu-id="6e9a8-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-128">Bearer {token}.</span></span> <span data-ttu-id="6e9a8-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6e9a8-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6e9a8-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="6e9a8-130">Request body</span></span>
<span data-ttu-id="6e9a8-131">Tom</span><span class="sxs-lookup"><span data-stu-id="6e9a8-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6e9a8-132">Svar</span><span class="sxs-lookup"><span data-stu-id="6e9a8-132">Response</span></span>
<span data-ttu-id="6e9a8-133">Om det lyckas returnerar den här metoden 200 OK med listan över enheter som är kopplade till säkerhetsrekommendationern.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="6e9a8-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="6e9a8-134">Example</span></span>

<span data-ttu-id="6e9a8-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="6e9a8-135">**Request**</span></span>

<span data-ttu-id="6e9a8-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="6e9a8-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="6e9a8-137">**Response**</span></span>

<span data-ttu-id="6e9a8-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="6e9a8-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6e9a8-139">Related topics</span></span>
- [<span data-ttu-id="6e9a8-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6e9a8-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6e9a8-141">Rekommendation & säkerhetsrisk för hot</span><span class="sxs-lookup"><span data-stu-id="6e9a8-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
