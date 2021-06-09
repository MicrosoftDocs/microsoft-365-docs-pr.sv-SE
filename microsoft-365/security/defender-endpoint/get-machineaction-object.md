---
title: Get MachineAction object API
description: Lär dig hur du använder Get MachineAction API för att hämta en specifik maskinåtgärd med dess ID i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, machineaction-objekt
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
ms.openlocfilehash: dcb00d0d2afc7f873ea9c4afa3174ac46babf879
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770787"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="5f427-104">Skaffa machineAction API</span><span class="sxs-lookup"><span data-stu-id="5f427-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f427-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5f427-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5f427-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5f427-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f427-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5f427-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5f427-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="5f427-108">API description</span></span>
<span data-ttu-id="5f427-109">Hämtar specifik [maskinåtgärd genom](machineaction.md) dess ID.</span><span class="sxs-lookup"><span data-stu-id="5f427-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="5f427-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="5f427-110">Limitations</span></span>
1. <span data-ttu-id="5f427-111">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="5f427-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5f427-112">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5f427-112">Permissions</span></span>
<span data-ttu-id="5f427-113">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="5f427-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5f427-114">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5f427-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5f427-115">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="5f427-115">Permission type</span></span> |   <span data-ttu-id="5f427-116">Behörighet</span><span class="sxs-lookup"><span data-stu-id="5f427-116">Permission</span></span>  |   <span data-ttu-id="5f427-117">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="5f427-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5f427-118">Program</span><span class="sxs-lookup"><span data-stu-id="5f427-118">Application</span></span> |   <span data-ttu-id="5f427-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5f427-119">Machine.Read.All</span></span> |  <span data-ttu-id="5f427-120">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="5f427-120">'Read all machine profiles'</span></span>
<span data-ttu-id="5f427-121">Program</span><span class="sxs-lookup"><span data-stu-id="5f427-121">Application</span></span> |   <span data-ttu-id="5f427-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5f427-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5f427-123">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="5f427-123">'Read and write all machine information'</span></span>
<span data-ttu-id="5f427-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5f427-124">Delegated (work or school account)</span></span> | <span data-ttu-id="5f427-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5f427-125">Machine.Read</span></span> | <span data-ttu-id="5f427-126">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="5f427-126">'Read machine information'</span></span>
<span data-ttu-id="5f427-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5f427-127">Delegated (work or school account)</span></span> | <span data-ttu-id="5f427-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5f427-128">Machine.ReadWrite</span></span> | <span data-ttu-id="5f427-129">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="5f427-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5f427-130">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="5f427-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5f427-131">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="5f427-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5f427-132">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5f427-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5f427-133">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="5f427-133">Request headers</span></span>

<span data-ttu-id="5f427-134">Namn</span><span class="sxs-lookup"><span data-stu-id="5f427-134">Name</span></span> | <span data-ttu-id="5f427-135">Typ</span><span class="sxs-lookup"><span data-stu-id="5f427-135">Type</span></span> | <span data-ttu-id="5f427-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5f427-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="5f427-137">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5f427-137">Authorization</span></span> | <span data-ttu-id="5f427-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="5f427-138">String</span></span> | <span data-ttu-id="5f427-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5f427-139">Bearer {token}.</span></span> <span data-ttu-id="5f427-140">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5f427-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5f427-141">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="5f427-141">Request body</span></span>
<span data-ttu-id="5f427-142">Tom</span><span class="sxs-lookup"><span data-stu-id="5f427-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5f427-143">Svar</span><span class="sxs-lookup"><span data-stu-id="5f427-143">Response</span></span>
<span data-ttu-id="5f427-144">Om det lyckas returnerar den här metoden 200, OK-svarskod med en [datoråtgärdsentitet.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="5f427-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="5f427-145">Om maskinåtgärdsentitet med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="5f427-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="5f427-146">Exempel</span><span class="sxs-lookup"><span data-stu-id="5f427-146">Example</span></span>

<span data-ttu-id="5f427-147">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="5f427-147">**Request**</span></span>

<span data-ttu-id="5f427-148">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="5f427-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="5f427-149">**Svar**</span><span class="sxs-lookup"><span data-stu-id="5f427-149">**Response**</span></span>

<span data-ttu-id="5f427-150">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="5f427-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
