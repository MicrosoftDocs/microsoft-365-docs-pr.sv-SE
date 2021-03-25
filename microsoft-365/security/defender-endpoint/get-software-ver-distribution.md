---
title: Lista över distribution av programvaruversion
description: Hämtar en lista över organisationens programvaruversionsdistribution
keywords: apis, graph api, API som stöds, get, software version distribution, mdatp tvm api
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
ms.openlocfilehash: 88f446ddd87768817099c1a206bab17aa8be5b7b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198583"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="2a9f9-104">Lista över distribution av programvaruversion</span><span class="sxs-lookup"><span data-stu-id="2a9f9-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a9f9-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2a9f9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2a9f9-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2a9f9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a9f9-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2a9f9-108">Hämtar en lista över organisationens distribution av programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="2a9f9-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2a9f9-109">Permissions</span></span>
<span data-ttu-id="2a9f9-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2a9f9-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2a9f9-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="2a9f9-112">Permission type</span></span> |   <span data-ttu-id="2a9f9-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="2a9f9-113">Permission</span></span>  |   <span data-ttu-id="2a9f9-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="2a9f9-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2a9f9-115">Program</span><span class="sxs-lookup"><span data-stu-id="2a9f9-115">Application</span></span> | <span data-ttu-id="2a9f9-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2a9f9-116">Software.Read.All</span></span> | <span data-ttu-id="2a9f9-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="2a9f9-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2a9f9-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="2a9f9-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2a9f9-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2a9f9-119">Software.Read</span></span> | <span data-ttu-id="2a9f9-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="2a9f9-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2a9f9-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2a9f9-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="2a9f9-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2a9f9-122">Request headers</span></span>

| <span data-ttu-id="2a9f9-123">Namn</span><span class="sxs-lookup"><span data-stu-id="2a9f9-123">Name</span></span>        | <span data-ttu-id="2a9f9-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="2a9f9-124">Type</span></span> | <span data-ttu-id="2a9f9-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2a9f9-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="2a9f9-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2a9f9-126">Authorization</span></span> | <span data-ttu-id="2a9f9-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="2a9f9-127">String</span></span> | <span data-ttu-id="2a9f9-128">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2a9f9-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2a9f9-129">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2a9f9-129">Request body</span></span>
<span data-ttu-id="2a9f9-130">Tom</span><span class="sxs-lookup"><span data-stu-id="2a9f9-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2a9f9-131">Svar</span><span class="sxs-lookup"><span data-stu-id="2a9f9-131">Response</span></span>
<span data-ttu-id="2a9f9-132">Om den lyckas returnerar den här metoden 200 OK med en lista över distributionsdata för programvara i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="2a9f9-133">Exempel</span><span class="sxs-lookup"><span data-stu-id="2a9f9-133">Example</span></span>

<span data-ttu-id="2a9f9-134">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2a9f9-134">**Request**</span></span>

<span data-ttu-id="2a9f9-135">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="2a9f9-136">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2a9f9-136">**Response**</span></span>

<span data-ttu-id="2a9f9-137">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2a9f9-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2a9f9-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2a9f9-138">Related topics</span></span>
- [<span data-ttu-id="2a9f9-139">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="2a9f9-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2a9f9-140">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="2a9f9-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
