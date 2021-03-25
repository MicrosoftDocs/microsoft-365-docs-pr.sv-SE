---
title: API för listdatorer
description: Lär dig hur du använder List machines API för att hämta en samling datorer som har kommunicerat med Microsoft Defender ATP cloud.
keywords: apis, graph api, API som stöds, skaffa, enheter
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200383"
---
# <a name="list-machines-api"></a><span data-ttu-id="78c25-104">API för listdatorer</span><span class="sxs-lookup"><span data-stu-id="78c25-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="78c25-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="78c25-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="78c25-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="78c25-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="78c25-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="78c25-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="78c25-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="78c25-108">API description</span></span>
<span data-ttu-id="78c25-109">Hämtar en samling datorer som [har](machine.md) kommunicerat med Microsoft Defender för Endpoint-molnet.</span><span class="sxs-lookup"><span data-stu-id="78c25-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="78c25-110">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="78c25-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="78c25-111">OData-frågan `$filter` stöds på: `computerDnsName` , `lastSeen` , , `healthStatus` och `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="78c25-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="78c25-112">Se exempel på [OData-frågor med Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="78c25-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="78c25-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="78c25-113">Limitations</span></span>
1. <span data-ttu-id="78c25-114">Du kan se till att enheter visas senast enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="78c25-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="78c25-115">Maximal sidstorlek är 10 000.</span><span class="sxs-lookup"><span data-stu-id="78c25-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="78c25-116">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="78c25-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="78c25-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="78c25-117">Permissions</span></span>

<span data-ttu-id="78c25-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="78c25-118">Permission type</span></span> |   <span data-ttu-id="78c25-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="78c25-119">Permission</span></span>  |   <span data-ttu-id="78c25-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="78c25-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="78c25-121">Program</span><span class="sxs-lookup"><span data-stu-id="78c25-121">Application</span></span> |   <span data-ttu-id="78c25-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="78c25-122">Machine.Read.All</span></span> |  <span data-ttu-id="78c25-123">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="78c25-123">'Read all machine profiles'</span></span>
<span data-ttu-id="78c25-124">Program</span><span class="sxs-lookup"><span data-stu-id="78c25-124">Application</span></span> |   <span data-ttu-id="78c25-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="78c25-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="78c25-126">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="78c25-126">'Read and write all machine information'</span></span>
<span data-ttu-id="78c25-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="78c25-127">Delegated (work or school account)</span></span> | <span data-ttu-id="78c25-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="78c25-128">Machine.Read</span></span> | <span data-ttu-id="78c25-129">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="78c25-129">'Read machine information'</span></span>
<span data-ttu-id="78c25-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="78c25-130">Delegated (work or school account)</span></span> | <span data-ttu-id="78c25-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="78c25-131">Machine.ReadWrite</span></span> | <span data-ttu-id="78c25-132">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="78c25-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="78c25-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="78c25-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="78c25-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="78c25-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="78c25-135">Svaret omfattar endast enheter, som användaren har åtkomst till, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="78c25-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="78c25-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="78c25-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="78c25-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="78c25-137">Request headers</span></span>

<span data-ttu-id="78c25-138">Namn</span><span class="sxs-lookup"><span data-stu-id="78c25-138">Name</span></span> | <span data-ttu-id="78c25-139">Skriv</span><span class="sxs-lookup"><span data-stu-id="78c25-139">Type</span></span> | <span data-ttu-id="78c25-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="78c25-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="78c25-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="78c25-141">Authorization</span></span> | <span data-ttu-id="78c25-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="78c25-142">String</span></span> | <span data-ttu-id="78c25-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="78c25-143">Bearer {token}.</span></span> <span data-ttu-id="78c25-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="78c25-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="78c25-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="78c25-145">Request body</span></span>
<span data-ttu-id="78c25-146">Tom</span><span class="sxs-lookup"><span data-stu-id="78c25-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="78c25-147">Svar</span><span class="sxs-lookup"><span data-stu-id="78c25-147">Response</span></span>
<span data-ttu-id="78c25-148">Om lyckat, och datorer finns - 200 OK med en lista [över maskinenheter](machine.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="78c25-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="78c25-149">Om det inte finns några senaste datorer - 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="78c25-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="78c25-150">Exempel</span><span class="sxs-lookup"><span data-stu-id="78c25-150">Example</span></span>

<span data-ttu-id="78c25-151">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="78c25-151">**Request**</span></span>

<span data-ttu-id="78c25-152">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="78c25-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="78c25-153">**Svar**</span><span class="sxs-lookup"><span data-stu-id="78c25-153">**Response**</span></span>

<span data-ttu-id="78c25-154">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="78c25-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="78c25-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="78c25-155">Related topics</span></span>
- [<span data-ttu-id="78c25-156">OData-frågor med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="78c25-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
