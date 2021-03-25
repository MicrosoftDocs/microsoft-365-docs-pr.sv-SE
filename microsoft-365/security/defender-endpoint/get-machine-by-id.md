---
title: Skaffa datorn via ID API
description: Lär dig hur du använder Hämta dator genom ID API för att hämta en dator med dess enhets-ID eller datornamn i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, enheter, entitet, id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200106"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="cc07e-104">Skaffa datorn via ID API</span><span class="sxs-lookup"><span data-stu-id="cc07e-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc07e-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cc07e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="cc07e-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cc07e-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc07e-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cc07e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cc07e-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="cc07e-108">API description</span></span>
<span data-ttu-id="cc07e-109">Hämtar specifik dator [med](machine.md) dess enhets-ID eller datornamn.</span><span class="sxs-lookup"><span data-stu-id="cc07e-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="cc07e-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="cc07e-110">Limitations</span></span>
1. <span data-ttu-id="cc07e-111">Du kan se till att enheter som visas senast enligt din konfigurerade bevarandeprincip.</span><span class="sxs-lookup"><span data-stu-id="cc07e-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="cc07e-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="cc07e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cc07e-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="cc07e-113">Permissions</span></span>
<span data-ttu-id="cc07e-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="cc07e-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cc07e-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cc07e-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cc07e-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="cc07e-116">Permission type</span></span> |   <span data-ttu-id="cc07e-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="cc07e-117">Permission</span></span>  |   <span data-ttu-id="cc07e-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="cc07e-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cc07e-119">Program</span><span class="sxs-lookup"><span data-stu-id="cc07e-119">Application</span></span> |   <span data-ttu-id="cc07e-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="cc07e-120">Machine.Read.All</span></span> |  <span data-ttu-id="cc07e-121">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="cc07e-121">'Read all machine profiles'</span></span>
<span data-ttu-id="cc07e-122">Program</span><span class="sxs-lookup"><span data-stu-id="cc07e-122">Application</span></span> |   <span data-ttu-id="cc07e-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cc07e-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="cc07e-124">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="cc07e-124">'Read and write all machine information'</span></span>
<span data-ttu-id="cc07e-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="cc07e-125">Delegated (work or school account)</span></span> | <span data-ttu-id="cc07e-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="cc07e-126">Machine.Read</span></span> | <span data-ttu-id="cc07e-127">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="cc07e-127">'Read machine information'</span></span>
<span data-ttu-id="cc07e-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="cc07e-128">Delegated (work or school account)</span></span> | <span data-ttu-id="cc07e-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cc07e-129">Machine.ReadWrite</span></span> | <span data-ttu-id="cc07e-130">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="cc07e-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="cc07e-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="cc07e-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cc07e-132">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="cc07e-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cc07e-133">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="cc07e-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="cc07e-134">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="cc07e-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cc07e-135">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="cc07e-135">Request headers</span></span>

<span data-ttu-id="cc07e-136">Namn</span><span class="sxs-lookup"><span data-stu-id="cc07e-136">Name</span></span> | <span data-ttu-id="cc07e-137">Skriv</span><span class="sxs-lookup"><span data-stu-id="cc07e-137">Type</span></span> | <span data-ttu-id="cc07e-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cc07e-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="cc07e-139">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="cc07e-139">Authorization</span></span> | <span data-ttu-id="cc07e-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="cc07e-140">String</span></span> | <span data-ttu-id="cc07e-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cc07e-141">Bearer {token}.</span></span> <span data-ttu-id="cc07e-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="cc07e-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cc07e-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="cc07e-143">Request body</span></span>
<span data-ttu-id="cc07e-144">Tom</span><span class="sxs-lookup"><span data-stu-id="cc07e-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cc07e-145">Svar</span><span class="sxs-lookup"><span data-stu-id="cc07e-145">Response</span></span>
<span data-ttu-id="cc07e-146">Om det fungerar och enheten finns - 200 OK med [datorenheten](machine.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="cc07e-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="cc07e-147">Om ingen dator med det angivna ID:t hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="cc07e-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="cc07e-148">Exempel</span><span class="sxs-lookup"><span data-stu-id="cc07e-148">Example</span></span>

<span data-ttu-id="cc07e-149">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="cc07e-149">**Request**</span></span>

<span data-ttu-id="cc07e-150">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="cc07e-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="cc07e-151">**Svar**</span><span class="sxs-lookup"><span data-stu-id="cc07e-151">**Response**</span></span>

<span data-ttu-id="cc07e-152">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="cc07e-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
