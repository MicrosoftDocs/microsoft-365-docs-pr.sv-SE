---
title: Hämta API för användarinformation
description: Lär dig hur du använder API:t för att hämta användarinformation för att hämta en användarentitet efter nyckel eller användarnamn i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, hämta, användare, användarinformation
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198547"
---
# <a name="get-user-information-api"></a><span data-ttu-id="e6d83-104">Hämta API för användarinformation</span><span class="sxs-lookup"><span data-stu-id="e6d83-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6d83-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e6d83-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e6d83-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e6d83-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e6d83-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e6d83-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="e6d83-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e6d83-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e6d83-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e6d83-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="e6d83-110">Hämta en användarentitet efter nyckel (användarnamn).</span><span class="sxs-lookup"><span data-stu-id="e6d83-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="e6d83-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="e6d83-111">Permissions</span></span>
<span data-ttu-id="e6d83-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="e6d83-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e6d83-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e6d83-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e6d83-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="e6d83-114">Permission type</span></span> |   <span data-ttu-id="e6d83-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="e6d83-115">Permission</span></span>  |   <span data-ttu-id="e6d83-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="e6d83-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e6d83-117">Program</span><span class="sxs-lookup"><span data-stu-id="e6d83-117">Application</span></span> |   <span data-ttu-id="e6d83-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="e6d83-118">User.Read.All</span></span> | <span data-ttu-id="e6d83-119">"Läs alla användarprofiler"</span><span class="sxs-lookup"><span data-stu-id="e6d83-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="e6d83-120">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="e6d83-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="e6d83-121">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="e6d83-121">Request headers</span></span>

<span data-ttu-id="e6d83-122">Namn</span><span class="sxs-lookup"><span data-stu-id="e6d83-122">Name</span></span> | <span data-ttu-id="e6d83-123">Typ</span><span class="sxs-lookup"><span data-stu-id="e6d83-123">Type</span></span> | <span data-ttu-id="e6d83-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6d83-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="e6d83-125">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="e6d83-125">Authorization</span></span> | <span data-ttu-id="e6d83-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="e6d83-126">String</span></span> | <span data-ttu-id="e6d83-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e6d83-127">Bearer {token}.</span></span> <span data-ttu-id="e6d83-128">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="e6d83-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e6d83-129">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="e6d83-129">Request body</span></span>
<span data-ttu-id="e6d83-130">Tom</span><span class="sxs-lookup"><span data-stu-id="e6d83-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e6d83-131">Svar</span><span class="sxs-lookup"><span data-stu-id="e6d83-131">Response</span></span>
<span data-ttu-id="e6d83-132">Om det lyckas och användaren finns – 200 OK med [entitet](user.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="e6d83-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="e6d83-133">Om användaren inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="e6d83-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e6d83-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="e6d83-134">Example</span></span>

<span data-ttu-id="e6d83-135">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="e6d83-135">**Request**</span></span>

<span data-ttu-id="e6d83-136">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="e6d83-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="e6d83-137">**Svar**</span><span class="sxs-lookup"><span data-stu-id="e6d83-137">**Response**</span></span>

<span data-ttu-id="e6d83-138">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="e6d83-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
