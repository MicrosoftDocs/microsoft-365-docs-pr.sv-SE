---
title: Hämta upptäckta sårbarheter
description: Hämtar en samling av identifierade svagheter i samband med ett visst enhets-ID.
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, upptäckta svagheter, & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ac7a9ef932f2640bbc5325f0154c0ceb48ae3018
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772299"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="2bc7c-104">Hämta upptäckta sårbarheter</span><span class="sxs-lookup"><span data-stu-id="2bc7c-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bc7c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2bc7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bc7c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bc7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bc7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bc7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2bc7c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2bc7c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2bc7c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2bc7c-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bc7c-110">API description</span></span>
<span data-ttu-id="2bc7c-111">Hämtar en samling av identifierade svagheter i samband med ett visst enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="2bc7c-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="2bc7c-112">Limitations</span></span>
1. <span data-ttu-id="2bc7c-113">Begränsningar i kursen för detta API är 50 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="2bc7c-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2bc7c-114">Permissions</span></span>

<span data-ttu-id="2bc7c-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2bc7c-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2bc7c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2bc7c-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="2bc7c-117">Permission type</span></span> | <span data-ttu-id="2bc7c-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="2bc7c-118">Permission</span></span> | <span data-ttu-id="2bc7c-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="2bc7c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2bc7c-120">Program</span><span class="sxs-lookup"><span data-stu-id="2bc7c-120">Application</span></span> |<span data-ttu-id="2bc7c-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bc7c-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="2bc7c-122">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="2bc7c-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="2bc7c-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="2bc7c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2bc7c-124">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="2bc7c-124">Vulnerability.Read</span></span> | <span data-ttu-id="2bc7c-125">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="2bc7c-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2bc7c-126">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2bc7c-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="2bc7c-127">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2bc7c-127">Request headers</span></span>

<span data-ttu-id="2bc7c-128">Namn</span><span class="sxs-lookup"><span data-stu-id="2bc7c-128">Name</span></span> | <span data-ttu-id="2bc7c-129">Typ</span><span class="sxs-lookup"><span data-stu-id="2bc7c-129">Type</span></span> | <span data-ttu-id="2bc7c-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bc7c-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="2bc7c-131">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2bc7c-131">Authorization</span></span> | <span data-ttu-id="2bc7c-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="2bc7c-132">String</span></span> | <span data-ttu-id="2bc7c-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-133">Bearer {token}.</span></span> <span data-ttu-id="2bc7c-134">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2bc7c-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2bc7c-135">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2bc7c-135">Request body</span></span>

<span data-ttu-id="2bc7c-136">Tom</span><span class="sxs-lookup"><span data-stu-id="2bc7c-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2bc7c-137">Svar</span><span class="sxs-lookup"><span data-stu-id="2bc7c-137">Response</span></span>

<span data-ttu-id="2bc7c-138">Om det lyckas returnerar den här metoden 200 OK med den identifierade sårbarhetsinformationen i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="2bc7c-139">Exempel</span><span class="sxs-lookup"><span data-stu-id="2bc7c-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="2bc7c-140">Begäran</span><span class="sxs-lookup"><span data-stu-id="2bc7c-140">Request</span></span>

<span data-ttu-id="2bc7c-141">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="2bc7c-142">Svar</span><span class="sxs-lookup"><span data-stu-id="2bc7c-142">Response</span></span>

<span data-ttu-id="2bc7c-143">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2bc7c-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="2bc7c-144">Se även</span><span class="sxs-lookup"><span data-stu-id="2bc7c-144">See also</span></span>

- [<span data-ttu-id="2bc7c-145">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="2bc7c-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2bc7c-146">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="2bc7c-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
