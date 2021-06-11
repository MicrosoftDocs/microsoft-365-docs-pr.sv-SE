---
title: Lista distribution av programvaruversion
description: Hämtar en lista över organisationens programvaruversionsdistribution
keywords: apis, graph api, API som stöds, skaffa, distribution av programvaruversion, Microsoft Defender för Endpoint tvm api
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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845036"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="e9104-104">Lista distribution av programvaruversion</span><span class="sxs-lookup"><span data-stu-id="e9104-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9104-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e9104-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e9104-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e9104-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9104-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e9104-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e9104-108">Hämtar en lista över organisationens distribution av programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="e9104-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="e9104-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="e9104-109">Permissions</span></span>
<span data-ttu-id="e9104-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="e9104-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e9104-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="e9104-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="e9104-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="e9104-112">Permission type</span></span> |   <span data-ttu-id="e9104-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="e9104-113">Permission</span></span>  |   <span data-ttu-id="e9104-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="e9104-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e9104-115">Program</span><span class="sxs-lookup"><span data-stu-id="e9104-115">Application</span></span> | <span data-ttu-id="e9104-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="e9104-116">Software.Read.All</span></span> | <span data-ttu-id="e9104-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="e9104-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="e9104-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="e9104-118">Delegated (work or school account)</span></span> | <span data-ttu-id="e9104-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="e9104-119">Software.Read</span></span> | <span data-ttu-id="e9104-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="e9104-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e9104-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="e9104-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="e9104-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="e9104-122">Request headers</span></span>

| <span data-ttu-id="e9104-123">Namn</span><span class="sxs-lookup"><span data-stu-id="e9104-123">Name</span></span>        | <span data-ttu-id="e9104-124">Typ</span><span class="sxs-lookup"><span data-stu-id="e9104-124">Type</span></span> | <span data-ttu-id="e9104-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e9104-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="e9104-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="e9104-126">Authorization</span></span> | <span data-ttu-id="e9104-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9104-127">String</span></span> | <span data-ttu-id="e9104-128">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="e9104-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e9104-129">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="e9104-129">Request body</span></span>
<span data-ttu-id="e9104-130">Tom</span><span class="sxs-lookup"><span data-stu-id="e9104-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e9104-131">Svar</span><span class="sxs-lookup"><span data-stu-id="e9104-131">Response</span></span>
<span data-ttu-id="e9104-132">Om den lyckas returnerar den här metoden 200 OK med en lista över distributionsdata för programvara i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="e9104-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="e9104-133">Exempel</span><span class="sxs-lookup"><span data-stu-id="e9104-133">Example</span></span>

<span data-ttu-id="e9104-134">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="e9104-134">**Request**</span></span>

<span data-ttu-id="e9104-135">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="e9104-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="e9104-136">**Svar**</span><span class="sxs-lookup"><span data-stu-id="e9104-136">**Response**</span></span>

<span data-ttu-id="e9104-137">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="e9104-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="e9104-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e9104-138">Related topics</span></span>
- [<span data-ttu-id="e9104-139">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="e9104-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e9104-140">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="e9104-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
