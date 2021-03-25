---
title: Få exponeringsresultat
description: Hämtar exponeringsresultatet för organisationen.
keywords: apis, graph api, api som stöds, skaffa, exponeringsresultat, exponeringsresultat för organisationen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166858"
---
# <a name="get-exposure-score"></a><span data-ttu-id="72cf3-104">Få exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="72cf3-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72cf3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="72cf3-105">**Applies to:**</span></span>
- [<span data-ttu-id="72cf3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="72cf3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72cf3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72cf3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="72cf3-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="72cf3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72cf3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="72cf3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="72cf3-110">Hämtar exponeringsresultatet för organisationen.</span><span class="sxs-lookup"><span data-stu-id="72cf3-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="72cf3-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="72cf3-111">Permissions</span></span>

<span data-ttu-id="72cf3-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="72cf3-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72cf3-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72cf3-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="72cf3-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="72cf3-114">Permission type</span></span> | <span data-ttu-id="72cf3-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="72cf3-115">Permission</span></span> | <span data-ttu-id="72cf3-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="72cf3-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="72cf3-117">Program</span><span class="sxs-lookup"><span data-stu-id="72cf3-117">Application</span></span> | <span data-ttu-id="72cf3-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="72cf3-118">Score.Read.All</span></span> | <span data-ttu-id="72cf3-119">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="72cf3-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="72cf3-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="72cf3-120">Delegated (work or school account)</span></span> | <span data-ttu-id="72cf3-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="72cf3-121">Score.Read</span></span> | <span data-ttu-id="72cf3-122">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="72cf3-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="72cf3-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="72cf3-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="72cf3-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="72cf3-124">Request headers</span></span>

<span data-ttu-id="72cf3-125">Namn</span><span class="sxs-lookup"><span data-stu-id="72cf3-125">Name</span></span> | <span data-ttu-id="72cf3-126">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="72cf3-126">Type</span></span> | <span data-ttu-id="72cf3-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="72cf3-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="72cf3-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="72cf3-128">Authorization</span></span> | <span data-ttu-id="72cf3-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="72cf3-129">String</span></span> | <span data-ttu-id="72cf3-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="72cf3-130">Bearer {token}.</span></span> <span data-ttu-id="72cf3-131">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="72cf3-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="72cf3-132">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="72cf3-132">Request body</span></span>

<span data-ttu-id="72cf3-133">Tom</span><span class="sxs-lookup"><span data-stu-id="72cf3-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="72cf3-134">Svar</span><span class="sxs-lookup"><span data-stu-id="72cf3-134">Response</span></span>

<span data-ttu-id="72cf3-135">Om det lyckas returnerar den här metoden 200 OK, med exponeringsdata i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="72cf3-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="72cf3-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="72cf3-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="72cf3-137">Begäran</span><span class="sxs-lookup"><span data-stu-id="72cf3-137">Request</span></span>

<span data-ttu-id="72cf3-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="72cf3-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="72cf3-139">Svar</span><span class="sxs-lookup"><span data-stu-id="72cf3-139">Response</span></span>

<span data-ttu-id="72cf3-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="72cf3-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="72cf3-141">Svarslistan som visas här kan trunkeras för att vara kort.</span><span class="sxs-lookup"><span data-stu-id="72cf3-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="72cf3-142">Se även</span><span class="sxs-lookup"><span data-stu-id="72cf3-142">See also</span></span>

- [<span data-ttu-id="72cf3-143">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="72cf3-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="72cf3-144">Exponeringsresultat & för hot</span><span class="sxs-lookup"><span data-stu-id="72cf3-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)