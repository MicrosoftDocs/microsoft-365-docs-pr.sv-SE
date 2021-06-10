---
title: Hämta varningsinformation om relaterade domäner
description: Hämta alla domäner som är relaterade till en viss avisering med Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, få aviseringsinformation, aviseringsinformation, relaterad domän
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
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771267"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="b90a5-104">Få aviseringsrelaterat API för domäninformation</span><span class="sxs-lookup"><span data-stu-id="b90a5-104">Get alert related domain information API</span></span>

<span data-ttu-id="b90a5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b90a5-105">**Applies to:**</span></span> 
- [<span data-ttu-id="b90a5-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b90a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="b90a5-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b90a5-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b90a5-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b90a5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b90a5-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="b90a5-109">API description</span></span>
<span data-ttu-id="b90a5-110">Hämtar alla domäner som är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="b90a5-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="b90a5-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="b90a5-111">Limitations</span></span>
1. <span data-ttu-id="b90a5-112">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="b90a5-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="b90a5-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="b90a5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b90a5-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b90a5-114">Permissions</span></span>
<span data-ttu-id="b90a5-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b90a5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b90a5-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b90a5-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b90a5-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b90a5-117">Permission type</span></span> | <span data-ttu-id="b90a5-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b90a5-118">Permission</span></span> | <span data-ttu-id="b90a5-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b90a5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b90a5-120">Program</span><span class="sxs-lookup"><span data-stu-id="b90a5-120">Application</span></span> | <span data-ttu-id="b90a5-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="b90a5-121">URL.Read.All</span></span> | <span data-ttu-id="b90a5-122">"Läs URL:er"</span><span class="sxs-lookup"><span data-stu-id="b90a5-122">'Read URLs'</span></span>
<span data-ttu-id="b90a5-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b90a5-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b90a5-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="b90a5-124">URL.Read.All</span></span> | <span data-ttu-id="b90a5-125">"Läs URL:er"</span><span class="sxs-lookup"><span data-stu-id="b90a5-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="b90a5-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="b90a5-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b90a5-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="b90a5-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b90a5-128">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b90a5-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b90a5-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b90a5-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="b90a5-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b90a5-130">Request headers</span></span>

<span data-ttu-id="b90a5-131">Namn</span><span class="sxs-lookup"><span data-stu-id="b90a5-131">Name</span></span> | <span data-ttu-id="b90a5-132">Typ</span><span class="sxs-lookup"><span data-stu-id="b90a5-132">Type</span></span> | <span data-ttu-id="b90a5-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b90a5-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="b90a5-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b90a5-134">Authorization</span></span> | <span data-ttu-id="b90a5-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="b90a5-135">String</span></span> | <span data-ttu-id="b90a5-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b90a5-136">Bearer {token}.</span></span> <span data-ttu-id="b90a5-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="b90a5-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b90a5-138">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b90a5-138">Request body</span></span>
<span data-ttu-id="b90a5-139">Tom</span><span class="sxs-lookup"><span data-stu-id="b90a5-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b90a5-140">Svar</span><span class="sxs-lookup"><span data-stu-id="b90a5-140">Response</span></span>
<span data-ttu-id="b90a5-141">Om det lyckas och avisering och domän finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="b90a5-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="b90a5-142">Om aviseringen inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="b90a5-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b90a5-143">Exempel</span><span class="sxs-lookup"><span data-stu-id="b90a5-143">Example</span></span>

<span data-ttu-id="b90a5-144">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b90a5-144">**Request**</span></span>

<span data-ttu-id="b90a5-145">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b90a5-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="b90a5-146">**Svar**</span><span class="sxs-lookup"><span data-stu-id="b90a5-146">**Response**</span></span>

<span data-ttu-id="b90a5-147">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="b90a5-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
