---
title: API för listindikatorer
description: Lär dig hur du använder API:t för listindikatorer för att hämta en samling av alla aktiva indikatorer i Microsoft Defender för slutpunkt.
keywords: apis, public api, apis som stöds, indikatorsamling
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770434"
---
# <a name="list-indicators-api"></a><span data-ttu-id="d475f-104">API för listindikatorer</span><span class="sxs-lookup"><span data-stu-id="d475f-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d475f-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d475f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d475f-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d475f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d475f-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d475f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d475f-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="d475f-108">API description</span></span>
<span data-ttu-id="d475f-109">Hämtar en samling av alla aktiva [indikatorer](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="d475f-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="d475f-110">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="d475f-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="d475f-111">OData-frågan ```$filter``` stöds för: ```indicatorValue``` , ```indicatorType``` , , ```creationTimeDateTimeUtc``` och ```createdBy``` ```action``` ```severity``` egenskaper.</span><span class="sxs-lookup"><span data-stu-id="d475f-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="d475f-112">Se exempel på [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d475f-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="d475f-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="d475f-113">Limitations</span></span>
1. <span data-ttu-id="d475f-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="d475f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="d475f-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="d475f-115">Permissions</span></span>
<span data-ttu-id="d475f-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="d475f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d475f-117">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d475f-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="d475f-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="d475f-118">Permission type</span></span> |   <span data-ttu-id="d475f-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d475f-119">Permission</span></span>  |   <span data-ttu-id="d475f-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="d475f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d475f-121">Program</span><span class="sxs-lookup"><span data-stu-id="d475f-121">Application</span></span> |   <span data-ttu-id="d475f-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d475f-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="d475f-123">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="d475f-123">'Read and write Indicators'</span></span>
<span data-ttu-id="d475f-124">Program</span><span class="sxs-lookup"><span data-stu-id="d475f-124">Application</span></span> |   <span data-ttu-id="d475f-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d475f-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="d475f-126">"Läsa och skriva alla indikatorer"</span><span class="sxs-lookup"><span data-stu-id="d475f-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="d475f-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="d475f-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="d475f-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d475f-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="d475f-129">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="d475f-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="d475f-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="d475f-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="d475f-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="d475f-131">Request headers</span></span>

<span data-ttu-id="d475f-132">Namn</span><span class="sxs-lookup"><span data-stu-id="d475f-132">Name</span></span> | <span data-ttu-id="d475f-133">Typ</span><span class="sxs-lookup"><span data-stu-id="d475f-133">Type</span></span> | <span data-ttu-id="d475f-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d475f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d475f-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="d475f-135">Authorization</span></span> | <span data-ttu-id="d475f-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="d475f-136">String</span></span> | <span data-ttu-id="d475f-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d475f-137">Bearer {token}.</span></span> <span data-ttu-id="d475f-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="d475f-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d475f-139">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="d475f-139">Request body</span></span>
<span data-ttu-id="d475f-140">Tom</span><span class="sxs-lookup"><span data-stu-id="d475f-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d475f-141">Svar</span><span class="sxs-lookup"><span data-stu-id="d475f-141">Response</span></span>
<span data-ttu-id="d475f-142">Om det lyckas returnerar den här metoden 200, Ok-svarskod med en samling [indikatorenheter.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d475f-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="d475f-143">Om programmet har behörigheten Ti.ReadWrite.All visas den för alla indikatorer.</span><span class="sxs-lookup"><span data-stu-id="d475f-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="d475f-144">I annat fall kommer den bara att visas för de indikatorer som skapas.</span><span class="sxs-lookup"><span data-stu-id="d475f-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="d475f-145">Exempel 1: </span><span class="sxs-lookup"><span data-stu-id="d475f-145">Example 1:</span></span>

<span data-ttu-id="d475f-146">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="d475f-146">**Request**</span></span>

<span data-ttu-id="d475f-147">Här är ett exempel på en begäran som hämtar alla indikatorer</span><span class="sxs-lookup"><span data-stu-id="d475f-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="d475f-148">**Svar**</span><span class="sxs-lookup"><span data-stu-id="d475f-148">**Response**</span></span>

<span data-ttu-id="d475f-149">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="d475f-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="d475f-150">Exempe 2l: </span><span class="sxs-lookup"><span data-stu-id="d475f-150">Example 2:</span></span>

<span data-ttu-id="d475f-151">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="d475f-151">**Request**</span></span>

<span data-ttu-id="d475f-152">Här är ett exempel på en begäran som hämtar alla indikatorer med åtgärden AviseringOchBlock</span><span class="sxs-lookup"><span data-stu-id="d475f-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="d475f-153">**Svar**</span><span class="sxs-lookup"><span data-stu-id="d475f-153">**Response**</span></span>

<span data-ttu-id="d475f-154">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="d475f-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
