---
title: Få alla säkerhetsproblem av maskin- och programvara
description: Hämtar en lista över alla säkerhetsproblem som påverkar organisationen av maskin- och programvaran
keywords: apis, graph api, API som stöds, hämta, sårbarhetsinformation, Microsoft Defender för Endpoint tvm api
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
ms.openlocfilehash: 01e14be20cee2b8644ebe5d1d1212f921a2fb9b5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841528"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="08910-104">Lista sårbarheter efter maskin och programvara</span><span class="sxs-lookup"><span data-stu-id="08910-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08910-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="08910-105">**Applies to:**</span></span>
- [<span data-ttu-id="08910-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="08910-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08910-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08910-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="08910-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="08910-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08910-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="08910-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="08910-110">Hämtar en lista över alla säkerhetsproblem som påverkar organisationen per [maskin-](machine.md) och [programvara.](software.md)</span><span class="sxs-lookup"><span data-stu-id="08910-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="08910-111">Om problemet har åtgärdats, visas det i svaret.</span><span class="sxs-lookup"><span data-stu-id="08910-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="08910-112">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="08910-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="08910-113">OData ```$filter``` stöds för alla egenskaper.</span><span class="sxs-lookup"><span data-stu-id="08910-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="08910-114">Det här är bra API för [Power BI integration.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="08910-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="08910-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="08910-115">Permissions</span></span>
<span data-ttu-id="08910-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="08910-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="08910-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="08910-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="08910-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="08910-118">Permission type</span></span> |   <span data-ttu-id="08910-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="08910-119">Permission</span></span>  |   <span data-ttu-id="08910-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="08910-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="08910-121">Program</span><span class="sxs-lookup"><span data-stu-id="08910-121">Application</span></span> |   <span data-ttu-id="08910-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="08910-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="08910-123">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="08910-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="08910-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="08910-124">Delegated (work or school account)</span></span> | <span data-ttu-id="08910-125">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="08910-125">Vulnerability.Read</span></span> |   <span data-ttu-id="08910-126">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="08910-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="08910-127">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="08910-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="08910-128">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="08910-128">Request headers</span></span>

<span data-ttu-id="08910-129">Namn</span><span class="sxs-lookup"><span data-stu-id="08910-129">Name</span></span> | <span data-ttu-id="08910-130">Typ</span><span class="sxs-lookup"><span data-stu-id="08910-130">Type</span></span> | <span data-ttu-id="08910-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="08910-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="08910-132">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="08910-132">Authorization</span></span> | <span data-ttu-id="08910-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="08910-133">String</span></span> | <span data-ttu-id="08910-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="08910-134">Bearer {token}.</span></span> <span data-ttu-id="08910-135">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="08910-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="08910-136">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="08910-136">Request body</span></span>
<span data-ttu-id="08910-137">Tom</span><span class="sxs-lookup"><span data-stu-id="08910-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="08910-138">Svar</span><span class="sxs-lookup"><span data-stu-id="08910-138">Response</span></span>
<span data-ttu-id="08910-139">Om det lyckas returnerar den här metoden 200 OK med en lista över säkerhetsproblem i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="08910-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="08910-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="08910-140">Example</span></span>

<span data-ttu-id="08910-141">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="08910-141">**Request**</span></span>

<span data-ttu-id="08910-142">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="08910-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="08910-143">**Svar**</span><span class="sxs-lookup"><span data-stu-id="08910-143">**Response**</span></span>

<span data-ttu-id="08910-144">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="08910-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="08910-145">Se även</span><span class="sxs-lookup"><span data-stu-id="08910-145">See also</span></span>

- [<span data-ttu-id="08910-146">Riskbaserade Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="08910-146">Risk-based threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="08910-147">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="08910-147">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
