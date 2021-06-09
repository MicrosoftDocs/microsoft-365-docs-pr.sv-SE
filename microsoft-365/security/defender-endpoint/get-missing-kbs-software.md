---
title: Få saknade KBs genom programvaru-ID
description: Hämtar säkerhetsuppdateringar som saknas med hjälp av programvaru-ID
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaru-ID, & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bbb3e5dfe94d5efb026e21a4cbd94fac45f36594
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845228"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="12d42-104">Få saknade KBs genom programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="12d42-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12d42-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="12d42-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="12d42-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="12d42-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12d42-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="12d42-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="12d42-108">Hämtar saknade KBs (säkerhetsuppdateringar) efter programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="12d42-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="12d42-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="12d42-109">Permissions</span></span>

<span data-ttu-id="12d42-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="12d42-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="12d42-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="12d42-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="12d42-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="12d42-112">Permission type</span></span> |   <span data-ttu-id="12d42-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="12d42-113">Permission</span></span>   |   <span data-ttu-id="12d42-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="12d42-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="12d42-115">Program</span><span class="sxs-lookup"><span data-stu-id="12d42-115">Application</span></span> |<span data-ttu-id="12d42-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="12d42-116">Software.Read.All</span></span> |   <span data-ttu-id="12d42-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="12d42-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="12d42-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="12d42-118">Delegated (work or school account)</span></span> | <span data-ttu-id="12d42-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="12d42-119">Software.Read</span></span> |   <span data-ttu-id="12d42-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="12d42-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="12d42-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="12d42-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="12d42-122">Sidhuvud för begäran</span><span class="sxs-lookup"><span data-stu-id="12d42-122">Request header</span></span>

<span data-ttu-id="12d42-123">Namn</span><span class="sxs-lookup"><span data-stu-id="12d42-123">Name</span></span> | <span data-ttu-id="12d42-124">Typ</span><span class="sxs-lookup"><span data-stu-id="12d42-124">Type</span></span> | <span data-ttu-id="12d42-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="12d42-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="12d42-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="12d42-126">Authorization</span></span> | <span data-ttu-id="12d42-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="12d42-127">String</span></span> | <span data-ttu-id="12d42-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="12d42-128">Bearer {token}.</span></span> <span data-ttu-id="12d42-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="12d42-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="12d42-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="12d42-130">Request body</span></span>

<span data-ttu-id="12d42-131">Tom</span><span class="sxs-lookup"><span data-stu-id="12d42-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="12d42-132">Svar</span><span class="sxs-lookup"><span data-stu-id="12d42-132">Response</span></span>

<span data-ttu-id="12d42-133">Om det lyckas returnerar den här metoden 200 OK, när angiven programvara saknar KB-data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="12d42-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="12d42-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="12d42-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="12d42-135">Begäran</span><span class="sxs-lookup"><span data-stu-id="12d42-135">Request</span></span>

<span data-ttu-id="12d42-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="12d42-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="12d42-137">Svar</span><span class="sxs-lookup"><span data-stu-id="12d42-137">Response</span></span>

<span data-ttu-id="12d42-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="12d42-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="12d42-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="12d42-139">Related topics</span></span>

- [<span data-ttu-id="12d42-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="12d42-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="12d42-141">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="12d42-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
