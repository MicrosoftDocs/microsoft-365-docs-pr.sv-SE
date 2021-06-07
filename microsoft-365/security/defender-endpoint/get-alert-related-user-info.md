---
title: Hämta varningsinformation om användare
description: Lär dig hur du använder API:t för att få aviseringsrelaterad användarinformation för att hämta användaren som är relaterad till en viss avisering i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, avisering, information, relaterad, användare
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
ms.openlocfilehash: e895885a638c60a845ed4857c682cd472e42615c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772323"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="2bd20-104">API:t för aviseringsrelaterad användarinformation</span><span class="sxs-lookup"><span data-stu-id="2bd20-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bd20-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2bd20-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bd20-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bd20-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bd20-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bd20-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2bd20-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2bd20-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2bd20-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2bd20-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2bd20-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bd20-110">API description</span></span>
<span data-ttu-id="2bd20-111">Hämtar användaren som är relaterad till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="2bd20-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="2bd20-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="2bd20-112">Limitations</span></span>
1. <span data-ttu-id="2bd20-113">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="2bd20-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2bd20-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="2bd20-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2bd20-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2bd20-115">Permissions</span></span>
<span data-ttu-id="2bd20-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="2bd20-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2bd20-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2bd20-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2bd20-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="2bd20-118">Permission type</span></span> |   <span data-ttu-id="2bd20-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="2bd20-119">Permission</span></span>  |   <span data-ttu-id="2bd20-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="2bd20-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2bd20-121">Program</span><span class="sxs-lookup"><span data-stu-id="2bd20-121">Application</span></span> |   <span data-ttu-id="2bd20-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bd20-122">User.Read.All</span></span> | <span data-ttu-id="2bd20-123">"Läsa användarprofiler"</span><span class="sxs-lookup"><span data-stu-id="2bd20-123">'Read user profiles'</span></span>
<span data-ttu-id="2bd20-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="2bd20-124">Delegated (work or school account)</span></span> | <span data-ttu-id="2bd20-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bd20-125">User.Read.All</span></span> | <span data-ttu-id="2bd20-126">"Läsa användarprofiler"</span><span class="sxs-lookup"><span data-stu-id="2bd20-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="2bd20-127">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="2bd20-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2bd20-128">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="2bd20-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2bd20-129">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="2bd20-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2bd20-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2bd20-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="2bd20-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2bd20-131">Request headers</span></span>

<span data-ttu-id="2bd20-132">Namn</span><span class="sxs-lookup"><span data-stu-id="2bd20-132">Name</span></span> | <span data-ttu-id="2bd20-133">Typ</span><span class="sxs-lookup"><span data-stu-id="2bd20-133">Type</span></span> | <span data-ttu-id="2bd20-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bd20-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="2bd20-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2bd20-135">Authorization</span></span> | <span data-ttu-id="2bd20-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="2bd20-136">String</span></span> | <span data-ttu-id="2bd20-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2bd20-137">Bearer {token}.</span></span> <span data-ttu-id="2bd20-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2bd20-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2bd20-139">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2bd20-139">Request body</span></span>
<span data-ttu-id="2bd20-140">Tom</span><span class="sxs-lookup"><span data-stu-id="2bd20-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2bd20-141">Svar</span><span class="sxs-lookup"><span data-stu-id="2bd20-141">Response</span></span>
<span data-ttu-id="2bd20-142">Om det lyckas och en avisering och en användare finns – 200 OK med användaren i meddelandetexten.</span><span class="sxs-lookup"><span data-stu-id="2bd20-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="2bd20-143">Om aviseringen eller användaren inte hittas – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="2bd20-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2bd20-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="2bd20-144">Example</span></span>

<span data-ttu-id="2bd20-145">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2bd20-145">**Request**</span></span>

<span data-ttu-id="2bd20-146">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2bd20-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="2bd20-147">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2bd20-147">**Response**</span></span>

<span data-ttu-id="2bd20-148">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2bd20-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
