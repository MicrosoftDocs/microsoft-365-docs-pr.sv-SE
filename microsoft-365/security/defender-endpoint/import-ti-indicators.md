---
title: API för import av indikatorer
description: Lär dig hur du använder importbatchen av indikator-API i Microsoft Defender för Slutpunkt.
keywords: apis, apis som stöds, skicka, ti, indikator, uppdatera
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198251"
---
# <a name="import-indicators-api"></a><span data-ttu-id="743d8-104">API för import av indikatorer</span><span class="sxs-lookup"><span data-stu-id="743d8-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="743d8-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="743d8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="743d8-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="743d8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="743d8-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="743d8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="743d8-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="743d8-108">API description</span></span>
<span data-ttu-id="743d8-109">Batchen Skicka eller Uppdateringar med [indikatorenheter.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="743d8-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="743d8-110">CIDR-notation för IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="743d8-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="743d8-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="743d8-111">Limitations</span></span>
1. <span data-ttu-id="743d8-112">Prisbegränsningar för detta API är 30 samtal per minut.</span><span class="sxs-lookup"><span data-stu-id="743d8-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="743d8-113">Det finns en gräns på 15 000 aktiva [indikatorer](ti-indicator.md) per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="743d8-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="743d8-114">Den maximala batchstorleken för ett API-anrop är 500.</span><span class="sxs-lookup"><span data-stu-id="743d8-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="743d8-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="743d8-115">Permissions</span></span>
<span data-ttu-id="743d8-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="743d8-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="743d8-117">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="743d8-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="743d8-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="743d8-118">Permission type</span></span> |   <span data-ttu-id="743d8-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="743d8-119">Permission</span></span>  |   <span data-ttu-id="743d8-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="743d8-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="743d8-121">Program</span><span class="sxs-lookup"><span data-stu-id="743d8-121">Application</span></span> |   <span data-ttu-id="743d8-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="743d8-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="743d8-123">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="743d8-123">'Read and write Indicators'</span></span>
<span data-ttu-id="743d8-124">Program</span><span class="sxs-lookup"><span data-stu-id="743d8-124">Application</span></span> |   <span data-ttu-id="743d8-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="743d8-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="743d8-126">"Läsa och skriva alla indikatorer"</span><span class="sxs-lookup"><span data-stu-id="743d8-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="743d8-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="743d8-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="743d8-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="743d8-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="743d8-129">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="743d8-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="743d8-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="743d8-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="743d8-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="743d8-131">Request headers</span></span>

<span data-ttu-id="743d8-132">Namn</span><span class="sxs-lookup"><span data-stu-id="743d8-132">Name</span></span> | <span data-ttu-id="743d8-133">Typ</span><span class="sxs-lookup"><span data-stu-id="743d8-133">Type</span></span> | <span data-ttu-id="743d8-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="743d8-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="743d8-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="743d8-135">Authorization</span></span> | <span data-ttu-id="743d8-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="743d8-136">String</span></span> | <span data-ttu-id="743d8-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="743d8-137">Bearer {token}.</span></span> <span data-ttu-id="743d8-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="743d8-138">**Required**.</span></span>
<span data-ttu-id="743d8-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="743d8-139">Content-Type</span></span> | <span data-ttu-id="743d8-140">sträng</span><span class="sxs-lookup"><span data-stu-id="743d8-140">string</span></span> | <span data-ttu-id="743d8-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="743d8-141">application/json.</span></span> <span data-ttu-id="743d8-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="743d8-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="743d8-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="743d8-143">Request body</span></span>
<span data-ttu-id="743d8-144">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="743d8-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="743d8-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="743d8-145">Parameter</span></span> | <span data-ttu-id="743d8-146">Typ</span><span class="sxs-lookup"><span data-stu-id="743d8-146">Type</span></span>    | <span data-ttu-id="743d8-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="743d8-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="743d8-148">Indikatorer</span><span class="sxs-lookup"><span data-stu-id="743d8-148">Indicators</span></span> | <span data-ttu-id="743d8-149">Indikator<[lista](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="743d8-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="743d8-150">Lista över [indikatorer](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="743d8-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="743d8-151">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="743d8-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="743d8-152">Svar</span><span class="sxs-lookup"><span data-stu-id="743d8-152">Response</span></span>
- <span data-ttu-id="743d8-153">Om det lyckas returnerar den här metoden 200 – OK-svarskod med en lista med importresultat per indikator, se exemplet nedan.</span><span class="sxs-lookup"><span data-stu-id="743d8-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="743d8-154">Om det inte lyckas: den här metoden returnerar 400 – Bad Request.</span><span class="sxs-lookup"><span data-stu-id="743d8-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="743d8-155">Felaktig begäran anger vanligtvis felaktigt brödtext.</span><span class="sxs-lookup"><span data-stu-id="743d8-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="743d8-156">Exempel</span><span class="sxs-lookup"><span data-stu-id="743d8-156">Example</span></span>

<span data-ttu-id="743d8-157">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="743d8-157">**Request**</span></span>

<span data-ttu-id="743d8-158">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="743d8-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="743d8-159">**Svar**</span><span class="sxs-lookup"><span data-stu-id="743d8-159">**Response**</span></span>

<span data-ttu-id="743d8-160">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="743d8-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="743d8-161">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="743d8-161">Related topic</span></span>
- [<span data-ttu-id="743d8-162">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="743d8-162">Manage indicators</span></span>](manage-indicators.md)
