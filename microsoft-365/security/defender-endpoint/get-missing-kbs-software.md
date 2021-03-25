---
title: Få saknade KBs genom programvaru-ID
description: Hämtar säkerhetsuppdateringar som saknas med hjälp av programvaru-ID
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaru-ID, hot & sårbarhetshantering api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c90854b043674a61c4996456c9d718b3c25afd1c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197798"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="41de9-104">Få saknade KBs genom programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="41de9-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41de9-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="41de9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="41de9-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="41de9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41de9-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="41de9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="41de9-108">Hämtar saknade KBs (säkerhetsuppdateringar) efter programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="41de9-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="41de9-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="41de9-109">Permissions</span></span>

<span data-ttu-id="41de9-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="41de9-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41de9-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="41de9-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="41de9-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="41de9-112">Permission type</span></span> |   <span data-ttu-id="41de9-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="41de9-113">Permission</span></span>   |   <span data-ttu-id="41de9-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="41de9-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="41de9-115">Program</span><span class="sxs-lookup"><span data-stu-id="41de9-115">Application</span></span> |<span data-ttu-id="41de9-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="41de9-116">Software.Read.All</span></span> |   <span data-ttu-id="41de9-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="41de9-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="41de9-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="41de9-118">Delegated (work or school account)</span></span> | <span data-ttu-id="41de9-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="41de9-119">Software.Read</span></span> |   <span data-ttu-id="41de9-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="41de9-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="41de9-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="41de9-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="41de9-122">Sidhuvud för begäran</span><span class="sxs-lookup"><span data-stu-id="41de9-122">Request header</span></span>

<span data-ttu-id="41de9-123">Namn</span><span class="sxs-lookup"><span data-stu-id="41de9-123">Name</span></span> | <span data-ttu-id="41de9-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="41de9-124">Type</span></span> | <span data-ttu-id="41de9-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="41de9-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="41de9-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="41de9-126">Authorization</span></span> | <span data-ttu-id="41de9-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="41de9-127">String</span></span> | <span data-ttu-id="41de9-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="41de9-128">Bearer {token}.</span></span> <span data-ttu-id="41de9-129">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="41de9-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="41de9-130">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="41de9-130">Request body</span></span>

<span data-ttu-id="41de9-131">Tom</span><span class="sxs-lookup"><span data-stu-id="41de9-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="41de9-132">Svar</span><span class="sxs-lookup"><span data-stu-id="41de9-132">Response</span></span>

<span data-ttu-id="41de9-133">Om det lyckas returnerar den här metoden 200 OK, när angiven programvara saknar KB-data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="41de9-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="41de9-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="41de9-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="41de9-135">Begäran</span><span class="sxs-lookup"><span data-stu-id="41de9-135">Request</span></span>

<span data-ttu-id="41de9-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="41de9-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="41de9-137">Svar</span><span class="sxs-lookup"><span data-stu-id="41de9-137">Response</span></span>

<span data-ttu-id="41de9-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="41de9-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="41de9-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="41de9-139">Related topics</span></span>

- [<span data-ttu-id="41de9-140">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="41de9-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="41de9-141">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="41de9-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
