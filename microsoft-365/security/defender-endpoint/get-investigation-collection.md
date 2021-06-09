---
title: API för listundersökningar
description: Använd detta API för att skapa samtal relaterade till samlingen Undersökningar
keywords: apis, graph api, api som stöds, samlingar för undersökningar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770151"
---
# <a name="list-investigations-api"></a><span data-ttu-id="222f7-104">API för listundersökningar</span><span class="sxs-lookup"><span data-stu-id="222f7-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="222f7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="222f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="222f7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="222f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="222f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="222f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="222f7-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="222f7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="222f7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="222f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="222f7-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="222f7-110">API description</span></span>
<span data-ttu-id="222f7-111">Hämtar en samling av [undersökningar](investigation.md).</span><span class="sxs-lookup"><span data-stu-id="222f7-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="222f7-112">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="222f7-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="222f7-113">OData-frågan ```$filter``` stöds för: ```startTime``` ```state``` , ```machineId``` och ```triggeringAlertId``` egenskaper.</span><span class="sxs-lookup"><span data-stu-id="222f7-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="222f7-114">Se exempel på [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="222f7-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="222f7-115">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="222f7-115">Limitations</span></span>
1. <span data-ttu-id="222f7-116">Maximal sidstorlek är 10 000.</span><span class="sxs-lookup"><span data-stu-id="222f7-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="222f7-117">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="222f7-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="222f7-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="222f7-118">Permissions</span></span>
<span data-ttu-id="222f7-119">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="222f7-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="222f7-120">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="222f7-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="222f7-121">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="222f7-121">Permission type</span></span> |   <span data-ttu-id="222f7-122">Behörighet</span><span class="sxs-lookup"><span data-stu-id="222f7-122">Permission</span></span>  |   <span data-ttu-id="222f7-123">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="222f7-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="222f7-124">Program</span><span class="sxs-lookup"><span data-stu-id="222f7-124">Application</span></span> |   <span data-ttu-id="222f7-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="222f7-125">Alert.Read.All</span></span> |    <span data-ttu-id="222f7-126">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="222f7-126">'Read all alerts'</span></span>
<span data-ttu-id="222f7-127">Program</span><span class="sxs-lookup"><span data-stu-id="222f7-127">Application</span></span> |   <span data-ttu-id="222f7-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="222f7-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="222f7-129">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="222f7-129">'Read and write all alerts'</span></span>
<span data-ttu-id="222f7-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="222f7-130">Delegated (work or school account)</span></span> | <span data-ttu-id="222f7-131">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="222f7-131">Alert.Read</span></span> | <span data-ttu-id="222f7-132">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="222f7-132">'Read alerts'</span></span>
<span data-ttu-id="222f7-133">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="222f7-133">Delegated (work or school account)</span></span> | <span data-ttu-id="222f7-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="222f7-134">Alert.ReadWrite</span></span> | <span data-ttu-id="222f7-135">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="222f7-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="222f7-136">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="222f7-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="222f7-137">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="222f7-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="222f7-138">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="222f7-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="222f7-139">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="222f7-139">Request headers</span></span>

<span data-ttu-id="222f7-140">Namn</span><span class="sxs-lookup"><span data-stu-id="222f7-140">Name</span></span> | <span data-ttu-id="222f7-141">Typ</span><span class="sxs-lookup"><span data-stu-id="222f7-141">Type</span></span> | <span data-ttu-id="222f7-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="222f7-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="222f7-143">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="222f7-143">Authorization</span></span> | <span data-ttu-id="222f7-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="222f7-144">String</span></span> | <span data-ttu-id="222f7-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="222f7-145">Bearer {token}.</span></span> <span data-ttu-id="222f7-146">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="222f7-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="222f7-147">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="222f7-147">Request body</span></span>
<span data-ttu-id="222f7-148">Tom</span><span class="sxs-lookup"><span data-stu-id="222f7-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="222f7-149">Svar</span><span class="sxs-lookup"><span data-stu-id="222f7-149">Response</span></span>
<span data-ttu-id="222f7-150">Om det lyckas returnerar den här metoden 200, Ok-svarskod med en samling enheter [för undersökningar.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="222f7-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="222f7-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="222f7-151">Example</span></span>

<span data-ttu-id="222f7-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="222f7-152">**Request**</span></span>

<span data-ttu-id="222f7-153">Här är ett exempel på en begäran om att få alla undersökningar:</span><span class="sxs-lookup"><span data-stu-id="222f7-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="222f7-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="222f7-154">**Response**</span></span>

<span data-ttu-id="222f7-155">Här är ett exempel på svaret:</span><span class="sxs-lookup"><span data-stu-id="222f7-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
