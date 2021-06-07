---
title: List machineActions API
description: Lär dig hur du använder API:t List MachineActions för att hämta en samling av maskinåtgärder i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, machineaction-samling
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
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771123"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="8cb45-104">List MachineActions API</span><span class="sxs-lookup"><span data-stu-id="8cb45-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8cb45-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8cb45-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8cb45-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8cb45-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8cb45-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8cb45-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8cb45-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="8cb45-108">API description</span></span>
<span data-ttu-id="8cb45-109">Hämtar en samling [datoråtgärder.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="8cb45-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="8cb45-110">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="8cb45-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="8cb45-111">OData-frågan ```$filter``` stöds för: ```status``` , ```machineId``` ```type``` , ```requestor``` och ```creationDateTimeUtc``` egenskaper.</span><span class="sxs-lookup"><span data-stu-id="8cb45-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="8cb45-112">Se exempel på [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="8cb45-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="8cb45-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="8cb45-113">Limitations</span></span>
1. <span data-ttu-id="8cb45-114">Maximal sidstorlek är 10 000.</span><span class="sxs-lookup"><span data-stu-id="8cb45-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="8cb45-115">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="8cb45-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="8cb45-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="8cb45-116">Permissions</span></span>
<span data-ttu-id="8cb45-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="8cb45-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8cb45-118">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8cb45-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8cb45-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="8cb45-119">Permission type</span></span> |   <span data-ttu-id="8cb45-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="8cb45-120">Permission</span></span>  |   <span data-ttu-id="8cb45-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="8cb45-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8cb45-122">Program</span><span class="sxs-lookup"><span data-stu-id="8cb45-122">Application</span></span> |   <span data-ttu-id="8cb45-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="8cb45-123">Machine.Read.All</span></span> |  <span data-ttu-id="8cb45-124">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="8cb45-124">'Read all machine profiles'</span></span>
<span data-ttu-id="8cb45-125">Program</span><span class="sxs-lookup"><span data-stu-id="8cb45-125">Application</span></span> |   <span data-ttu-id="8cb45-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8cb45-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8cb45-127">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="8cb45-127">'Read and write all machine information'</span></span>
<span data-ttu-id="8cb45-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="8cb45-128">Delegated (work or school account)</span></span> | <span data-ttu-id="8cb45-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="8cb45-129">Machine.Read</span></span> | <span data-ttu-id="8cb45-130">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="8cb45-130">'Read machine information'</span></span>
<span data-ttu-id="8cb45-131">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="8cb45-131">Delegated (work or school account)</span></span> | <span data-ttu-id="8cb45-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8cb45-132">Machine.ReadWrite</span></span> | <span data-ttu-id="8cb45-133">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="8cb45-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8cb45-134">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="8cb45-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8cb45-135">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="8cb45-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8cb45-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8cb45-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="8cb45-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="8cb45-137">Request headers</span></span>

<span data-ttu-id="8cb45-138">Namn</span><span class="sxs-lookup"><span data-stu-id="8cb45-138">Name</span></span> | <span data-ttu-id="8cb45-139">Typ</span><span class="sxs-lookup"><span data-stu-id="8cb45-139">Type</span></span> | <span data-ttu-id="8cb45-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8cb45-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8cb45-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="8cb45-141">Authorization</span></span> | <span data-ttu-id="8cb45-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="8cb45-142">String</span></span> | <span data-ttu-id="8cb45-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8cb45-143">Bearer {token}.</span></span> <span data-ttu-id="8cb45-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="8cb45-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8cb45-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="8cb45-145">Request body</span></span>
<span data-ttu-id="8cb45-146">Tom</span><span class="sxs-lookup"><span data-stu-id="8cb45-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8cb45-147">Svar</span><span class="sxs-lookup"><span data-stu-id="8cb45-147">Response</span></span>
<span data-ttu-id="8cb45-148">Om det lyckas returnerar den här metoden 200, OK-svarskod med en samling [machineAction-enheter.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="8cb45-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="8cb45-149">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="8cb45-149">Example 1</span></span>

<span data-ttu-id="8cb45-150">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="8cb45-150">**Request**</span></span>

<span data-ttu-id="8cb45-151">Här är ett exempel på begäran för en organisation som har tre maskinåtgärder.</span><span class="sxs-lookup"><span data-stu-id="8cb45-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="8cb45-152">**Svar**</span><span class="sxs-lookup"><span data-stu-id="8cb45-152">**Response**</span></span>

<span data-ttu-id="8cb45-153">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="8cb45-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="8cb45-154">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="8cb45-154">Example 2</span></span>

<span data-ttu-id="8cb45-155">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="8cb45-155">**Request**</span></span>

<span data-ttu-id="8cb45-156">Här är ett exempel på en begäran som filtrerar MachineActions efter maskin-ID och visar de senaste två MachineActions.</span><span class="sxs-lookup"><span data-stu-id="8cb45-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="8cb45-157">**Svar**</span><span class="sxs-lookup"><span data-stu-id="8cb45-157">**Response**</span></span>

<span data-ttu-id="8cb45-158">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="8cb45-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="8cb45-159">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8cb45-159">Related topics</span></span>
- [<span data-ttu-id="8cb45-160">OData-frågor med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="8cb45-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
