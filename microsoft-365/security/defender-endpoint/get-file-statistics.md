---
title: Hämta API för filstatistik
description: Lär dig hur du använder API:t för filstatistik för att hämta statistik för den givna filen i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, hämta, fil, statistik
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
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167122"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="2d34a-104">Hämta API för filstatistik</span><span class="sxs-lookup"><span data-stu-id="2d34a-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d34a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2d34a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d34a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d34a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2d34a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d34a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2d34a-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2d34a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d34a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2d34a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2d34a-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="2d34a-110">API description</span></span>
<span data-ttu-id="2d34a-111">Hämtar statistik för den angivna filen.</span><span class="sxs-lookup"><span data-stu-id="2d34a-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="2d34a-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="2d34a-112">Limitations</span></span>
1. <span data-ttu-id="2d34a-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="2d34a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2d34a-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2d34a-114">Permissions</span></span>
<span data-ttu-id="2d34a-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="2d34a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d34a-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2d34a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2d34a-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="2d34a-117">Permission type</span></span> |   <span data-ttu-id="2d34a-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="2d34a-118">Permission</span></span>  |   <span data-ttu-id="2d34a-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="2d34a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d34a-120">Program</span><span class="sxs-lookup"><span data-stu-id="2d34a-120">Application</span></span> |   <span data-ttu-id="2d34a-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="2d34a-121">File.Read.All</span></span> | <span data-ttu-id="2d34a-122">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="2d34a-122">'Read file profiles'</span></span>
<span data-ttu-id="2d34a-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="2d34a-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2d34a-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="2d34a-124">File.Read.All</span></span> | <span data-ttu-id="2d34a-125">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="2d34a-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="2d34a-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="2d34a-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2d34a-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="2d34a-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2d34a-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2d34a-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="2d34a-129">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2d34a-129">Request headers</span></span>

<span data-ttu-id="2d34a-130">Namn</span><span class="sxs-lookup"><span data-stu-id="2d34a-130">Name</span></span> | <span data-ttu-id="2d34a-131">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="2d34a-131">Type</span></span> | <span data-ttu-id="2d34a-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2d34a-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d34a-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2d34a-133">Authorization</span></span> | <span data-ttu-id="2d34a-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="2d34a-134">String</span></span> | <span data-ttu-id="2d34a-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2d34a-135">Bearer {token}.</span></span> <span data-ttu-id="2d34a-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2d34a-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="2d34a-137">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="2d34a-137">Request URI parameters</span></span>

<span data-ttu-id="2d34a-138">Namn</span><span class="sxs-lookup"><span data-stu-id="2d34a-138">Name</span></span> | <span data-ttu-id="2d34a-139">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="2d34a-139">Type</span></span> | <span data-ttu-id="2d34a-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2d34a-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d34a-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="2d34a-141">lookBackHours</span></span> | <span data-ttu-id="2d34a-142">Int32</span><span class="sxs-lookup"><span data-stu-id="2d34a-142">Int32</span></span> | <span data-ttu-id="2d34a-143">Definierar hur många timmar vi söker tillbaka för att få fram statistiken.</span><span class="sxs-lookup"><span data-stu-id="2d34a-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="2d34a-144">Standard är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2d34a-144">Defaults to 30 days.</span></span> <span data-ttu-id="2d34a-145">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="2d34a-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2d34a-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2d34a-146">Request body</span></span>
<span data-ttu-id="2d34a-147">Tom</span><span class="sxs-lookup"><span data-stu-id="2d34a-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2d34a-148">Svar</span><span class="sxs-lookup"><span data-stu-id="2d34a-148">Response</span></span>
<span data-ttu-id="2d34a-149">Om det lyckas och det finns en fil – 200 OK med statistiska data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="2d34a-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="2d34a-150">Om filen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="2d34a-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2d34a-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="2d34a-151">Example</span></span>

<span data-ttu-id="2d34a-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2d34a-152">**Request**</span></span>

<span data-ttu-id="2d34a-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2d34a-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="2d34a-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2d34a-154">**Response**</span></span>

<span data-ttu-id="2d34a-155">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2d34a-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
