---
title: API för att hämta maskininloggningsanvändare
description: Lär dig hur du använder API:t Hämta datorinloggningsanvändare för att hämta en samling inloggade användare på en enhet i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, enhet, logga in, användare
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
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229029"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="a7def-104">API för att hämta maskininloggningsanvändare</span><span class="sxs-lookup"><span data-stu-id="a7def-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a7def-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a7def-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a7def-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a7def-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7def-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a7def-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a7def-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="a7def-108">API description</span></span>
<span data-ttu-id="a7def-109">Hämtar en samling inloggade användare på en viss enhet.</span><span class="sxs-lookup"><span data-stu-id="a7def-109">Retrieves a collection of logged on users on a specific device.</span></span>

## <a name="limitations"></a><span data-ttu-id="a7def-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="a7def-110">Limitations</span></span>
1. <span data-ttu-id="a7def-111">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="a7def-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="a7def-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="a7def-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="a7def-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a7def-113">Permissions</span></span>
<span data-ttu-id="a7def-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="a7def-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7def-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a7def-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a7def-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="a7def-116">Permission type</span></span> |<span data-ttu-id="a7def-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a7def-117">Permission</span></span>|<span data-ttu-id="a7def-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="a7def-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a7def-119">Program</span><span class="sxs-lookup"><span data-stu-id="a7def-119">Application</span></span> |<span data-ttu-id="a7def-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="a7def-120">User.Read.All</span></span> |<span data-ttu-id="a7def-121">"Läsa användarprofiler"</span><span class="sxs-lookup"><span data-stu-id="a7def-121">'Read user profiles'</span></span>
<span data-ttu-id="a7def-122">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a7def-122">Delegated (work or school account)</span></span> | <span data-ttu-id="a7def-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="a7def-123">User.Read.All</span></span> | <span data-ttu-id="a7def-124">"Läsa användarprofiler"</span><span class="sxs-lookup"><span data-stu-id="a7def-124">'Read user profiles'</span></span>

> [!NOTE]
> <span data-ttu-id="a7def-125">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="a7def-125">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="a7def-126">Användaren måste ha minst följande rollbehörighet: "Visa data".</span><span class="sxs-lookup"><span data-stu-id="a7def-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="a7def-127">Mer information finns i Skapa [och hantera roller](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a7def-127">For more information, see [Create and manage roles](user-roles.md)).</span></span>
> - <span data-ttu-id="a7def-128">Svaret inkluderar endast användare om enheten är synlig för användaren, baserat på enhetens gruppinställningar.</span><span class="sxs-lookup"><span data-stu-id="a7def-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="a7def-129">Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a7def-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="a7def-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="a7def-130">HTTP request</span></span>

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="a7def-131">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="a7def-131">Request headers</span></span>

<span data-ttu-id="a7def-132">Namn</span><span class="sxs-lookup"><span data-stu-id="a7def-132">Name</span></span> | <span data-ttu-id="a7def-133">Typ</span><span class="sxs-lookup"><span data-stu-id="a7def-133">Type</span></span> | <span data-ttu-id="a7def-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a7def-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7def-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="a7def-135">Authorization</span></span> | <span data-ttu-id="a7def-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="a7def-136">String</span></span> | <span data-ttu-id="a7def-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a7def-137">Bearer {token}.</span></span> <span data-ttu-id="a7def-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a7def-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a7def-139">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="a7def-139">Request body</span></span>

<span data-ttu-id="a7def-140">Tom</span><span class="sxs-lookup"><span data-stu-id="a7def-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a7def-141">Svar</span><span class="sxs-lookup"><span data-stu-id="a7def-141">Response</span></span>

<span data-ttu-id="a7def-142">Om det fungerar och det finns en enhet – 200 OK med en lista [över användarenheter](user.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="a7def-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="a7def-143">Om enheten inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="a7def-143">If device was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="a7def-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="a7def-144">Example</span></span>

### <a name="request"></a><span data-ttu-id="a7def-145">Begäran</span><span class="sxs-lookup"><span data-stu-id="a7def-145">Request</span></span>

<span data-ttu-id="a7def-146">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="a7def-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a><span data-ttu-id="a7def-147">Svar</span><span class="sxs-lookup"><span data-stu-id="a7def-147">Response</span></span>

<span data-ttu-id="a7def-148">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="a7def-148">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
