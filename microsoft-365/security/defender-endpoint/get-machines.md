---
title: API för listdatorer
description: Lär dig hur du använder List machines API till att hämta en samling datorer som har kommunicerat med Microsoft Defender för Endpoint Cloud.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770757"
---
# <a name="list-machines-api"></a><span data-ttu-id="3da76-104">API för listdatorer</span><span class="sxs-lookup"><span data-stu-id="3da76-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3da76-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3da76-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3da76-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3da76-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3da76-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3da76-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3da76-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="3da76-108">API description</span></span>
<span data-ttu-id="3da76-109">Hämtar en samling datorer som [har](machine.md) kommunicerat med Microsoft Defender för Endpoint-molnet.</span><span class="sxs-lookup"><span data-stu-id="3da76-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="3da76-110">Stöder [OData V4-frågor.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="3da76-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="3da76-111">OData-frågan `$filter` stöds på: `computerDnsName` , `lastSeen` , , `healthStatus` och `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="3da76-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="3da76-112">Se exempel på [OData-frågor med Defender för Slutpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="3da76-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="3da76-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="3da76-113">Limitations</span></span>
1. <span data-ttu-id="3da76-114">Du kan se till att enheter visas senast enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="3da76-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="3da76-115">Maximal sidstorlek är 10 000.</span><span class="sxs-lookup"><span data-stu-id="3da76-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="3da76-116">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="3da76-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3da76-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3da76-117">Permissions</span></span>

<span data-ttu-id="3da76-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3da76-118">Permission type</span></span> |   <span data-ttu-id="3da76-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3da76-119">Permission</span></span>  |   <span data-ttu-id="3da76-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3da76-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3da76-121">Program</span><span class="sxs-lookup"><span data-stu-id="3da76-121">Application</span></span> |   <span data-ttu-id="3da76-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="3da76-122">Machine.Read.All</span></span> |  <span data-ttu-id="3da76-123">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="3da76-123">'Read all machine profiles'</span></span>
<span data-ttu-id="3da76-124">Program</span><span class="sxs-lookup"><span data-stu-id="3da76-124">Application</span></span> |   <span data-ttu-id="3da76-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3da76-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="3da76-126">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="3da76-126">'Read and write all machine information'</span></span>
<span data-ttu-id="3da76-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3da76-127">Delegated (work or school account)</span></span> | <span data-ttu-id="3da76-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="3da76-128">Machine.Read</span></span> | <span data-ttu-id="3da76-129">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="3da76-129">'Read machine information'</span></span>
<span data-ttu-id="3da76-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3da76-130">Delegated (work or school account)</span></span> | <span data-ttu-id="3da76-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3da76-131">Machine.ReadWrite</span></span> | <span data-ttu-id="3da76-132">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="3da76-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="3da76-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="3da76-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3da76-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="3da76-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3da76-135">Svaret omfattar endast enheter, som användaren har åtkomst till, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="3da76-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3da76-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3da76-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="3da76-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="3da76-137">Request headers</span></span>

<span data-ttu-id="3da76-138">Namn</span><span class="sxs-lookup"><span data-stu-id="3da76-138">Name</span></span> | <span data-ttu-id="3da76-139">Typ</span><span class="sxs-lookup"><span data-stu-id="3da76-139">Type</span></span> | <span data-ttu-id="3da76-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3da76-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="3da76-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3da76-141">Authorization</span></span> | <span data-ttu-id="3da76-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="3da76-142">String</span></span> | <span data-ttu-id="3da76-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3da76-143">Bearer {token}.</span></span> <span data-ttu-id="3da76-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3da76-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3da76-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="3da76-145">Request body</span></span>
<span data-ttu-id="3da76-146">Tom</span><span class="sxs-lookup"><span data-stu-id="3da76-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3da76-147">Svar</span><span class="sxs-lookup"><span data-stu-id="3da76-147">Response</span></span>
<span data-ttu-id="3da76-148">Om lyckat, och datorer finns - 200 OK med en lista [över maskinenheter](machine.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="3da76-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="3da76-149">Om det inte finns några senaste datorer - 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="3da76-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3da76-150">Exempel</span><span class="sxs-lookup"><span data-stu-id="3da76-150">Example</span></span>

<span data-ttu-id="3da76-151">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="3da76-151">**Request**</span></span>

<span data-ttu-id="3da76-152">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="3da76-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="3da76-153">**Svar**</span><span class="sxs-lookup"><span data-stu-id="3da76-153">**Response**</span></span>

<span data-ttu-id="3da76-154">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="3da76-154">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="3da76-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3da76-155">Related topics</span></span>
- [<span data-ttu-id="3da76-156">OData-frågor med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="3da76-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
