---
title: Lista över exponeringsresultat per enhetsgrupp
description: Hämtar en lista över exponeringsresultat per enhetsgrupp.
keywords: apis, graph api, api som stöds, skaffa, exponeringsresultat, enhetsgrupp, exponeringsresultat för enhetsgrupp
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fe4c2d4a4f18a1057472007f21936b4111673849
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166784"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="b503a-104">Lista över exponeringsresultat per enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b503a-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b503a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b503a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b503a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b503a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b503a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b503a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b503a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b503a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b503a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b503a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b503a-110">Hämtar en samling aviseringar som är relaterade till en viss domänadress.</span><span class="sxs-lookup"><span data-stu-id="b503a-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="b503a-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b503a-111">Permissions</span></span>

<span data-ttu-id="b503a-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b503a-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b503a-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b503a-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b503a-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b503a-114">Permission type</span></span> |   <span data-ttu-id="b503a-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b503a-115">Permission</span></span>  |   <span data-ttu-id="b503a-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b503a-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b503a-117">Program</span><span class="sxs-lookup"><span data-stu-id="b503a-117">Application</span></span> | <span data-ttu-id="b503a-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="b503a-118">Score.Read.All</span></span> | <span data-ttu-id="b503a-119">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="b503a-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="b503a-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b503a-120">Delegated (work or school account)</span></span> | <span data-ttu-id="b503a-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="b503a-121">Score.Read</span></span> | <span data-ttu-id="b503a-122">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="b503a-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="b503a-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b503a-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="b503a-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b503a-124">Request headers</span></span>

| <span data-ttu-id="b503a-125">Namn</span><span class="sxs-lookup"><span data-stu-id="b503a-125">Name</span></span>        | <span data-ttu-id="b503a-126">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="b503a-126">Type</span></span> | <span data-ttu-id="b503a-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b503a-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="b503a-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b503a-128">Authorization</span></span> | <span data-ttu-id="b503a-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="b503a-129">String</span></span> | <span data-ttu-id="b503a-130">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="b503a-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b503a-131">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b503a-131">Request body</span></span>

<span data-ttu-id="b503a-132">Tom</span><span class="sxs-lookup"><span data-stu-id="b503a-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b503a-133">Svar</span><span class="sxs-lookup"><span data-stu-id="b503a-133">Response</span></span>

<span data-ttu-id="b503a-134">Om det lyckas returnerar den här metoden 200 OK, med en lista över exponeringsresultat per enhetsgruppsdata i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="b503a-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="b503a-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="b503a-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="b503a-136">Begäran</span><span class="sxs-lookup"><span data-stu-id="b503a-136">Request</span></span>

<span data-ttu-id="b503a-137">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b503a-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="b503a-138">Svar</span><span class="sxs-lookup"><span data-stu-id="b503a-138">Response</span></span>

<span data-ttu-id="b503a-139">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="b503a-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b503a-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b503a-140">Related topics</span></span>

- [<span data-ttu-id="b503a-141">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="b503a-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b503a-142">Exponeringsresultat & för hot</span><span class="sxs-lookup"><span data-stu-id="b503a-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)