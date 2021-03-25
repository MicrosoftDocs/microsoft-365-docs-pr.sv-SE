---
title: Få aviseringsrelaterad maskininformation
description: Hämta alla enheter som är relaterade till en viss avisering med Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, få aviseringsinformation, aviseringsinformation, relaterad enhet
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
ms.technology: mde
ms.openlocfilehash: 70ce6adce3e14be7ee440b96587b8f9402c0b99f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166989"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="ee012-104">Få aviseringsrelaterat API för maskininformation</span><span class="sxs-lookup"><span data-stu-id="ee012-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ee012-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ee012-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee012-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee012-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee012-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee012-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ee012-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ee012-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ee012-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ee012-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ee012-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="ee012-110">API description</span></span>
<span data-ttu-id="ee012-111">Hämtar enheten [som](machine.md) är relaterad till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="ee012-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="ee012-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="ee012-112">Limitations</span></span>
1. <span data-ttu-id="ee012-113">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="ee012-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ee012-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="ee012-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ee012-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="ee012-115">Permissions</span></span>
<span data-ttu-id="ee012-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="ee012-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ee012-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ee012-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ee012-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="ee012-118">Permission type</span></span> |   <span data-ttu-id="ee012-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="ee012-119">Permission</span></span>  |   <span data-ttu-id="ee012-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="ee012-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ee012-121">Program</span><span class="sxs-lookup"><span data-stu-id="ee012-121">Application</span></span> |   <span data-ttu-id="ee012-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="ee012-122">Machine.Read.All</span></span> |  <span data-ttu-id="ee012-123">"Läs all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="ee012-123">'Read all machine information'</span></span>
<span data-ttu-id="ee012-124">Program</span><span class="sxs-lookup"><span data-stu-id="ee012-124">Application</span></span> |   <span data-ttu-id="ee012-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ee012-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="ee012-126">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="ee012-126">'Read and write all machine information'</span></span>
<span data-ttu-id="ee012-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="ee012-127">Delegated (work or school account)</span></span> | <span data-ttu-id="ee012-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="ee012-128">Machine.Read</span></span> | <span data-ttu-id="ee012-129">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="ee012-129">'Read machine information'</span></span>
<span data-ttu-id="ee012-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="ee012-130">Delegated (work or school account)</span></span> | <span data-ttu-id="ee012-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ee012-131">Machine.ReadWrite</span></span> | <span data-ttu-id="ee012-132">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="ee012-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="ee012-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="ee012-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ee012-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="ee012-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ee012-135">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ee012-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ee012-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="ee012-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="ee012-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="ee012-137">Request headers</span></span>

<span data-ttu-id="ee012-138">Namn</span><span class="sxs-lookup"><span data-stu-id="ee012-138">Name</span></span> | <span data-ttu-id="ee012-139">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="ee012-139">Type</span></span> | <span data-ttu-id="ee012-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ee012-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="ee012-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="ee012-141">Authorization</span></span> | <span data-ttu-id="ee012-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="ee012-142">String</span></span> | <span data-ttu-id="ee012-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ee012-143">Bearer {token}.</span></span> <span data-ttu-id="ee012-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="ee012-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ee012-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="ee012-145">Request body</span></span>
<span data-ttu-id="ee012-146">Tom</span><span class="sxs-lookup"><span data-stu-id="ee012-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ee012-147">Svar</span><span class="sxs-lookup"><span data-stu-id="ee012-147">Response</span></span>
<span data-ttu-id="ee012-148">Om det lyckas och avisering och enheten finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="ee012-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="ee012-149">Om aviseringen inte hittas eller om enheten inte hittas – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="ee012-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="ee012-150">Exempel</span><span class="sxs-lookup"><span data-stu-id="ee012-150">Example</span></span>

<span data-ttu-id="ee012-151">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="ee012-151">**Request**</span></span>

<span data-ttu-id="ee012-152">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="ee012-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="ee012-153">**Svar**</span><span class="sxs-lookup"><span data-stu-id="ee012-153">**Response**</span></span>

<span data-ttu-id="ee012-154">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="ee012-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
