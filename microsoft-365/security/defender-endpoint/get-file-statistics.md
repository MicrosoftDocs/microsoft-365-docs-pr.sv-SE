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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770211"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="aaecc-104">Hämta API för filstatistik</span><span class="sxs-lookup"><span data-stu-id="aaecc-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aaecc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="aaecc-105">**Applies to:**</span></span>
- [<span data-ttu-id="aaecc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="aaecc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aaecc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aaecc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aaecc-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="aaecc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aaecc-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="aaecc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="aaecc-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="aaecc-110">API description</span></span>
<span data-ttu-id="aaecc-111">Hämtar statistik för den angivna filen.</span><span class="sxs-lookup"><span data-stu-id="aaecc-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="aaecc-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="aaecc-112">Limitations</span></span>
1. <span data-ttu-id="aaecc-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="aaecc-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="aaecc-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="aaecc-114">Permissions</span></span>
<span data-ttu-id="aaecc-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="aaecc-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aaecc-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aaecc-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="aaecc-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="aaecc-117">Permission type</span></span> |   <span data-ttu-id="aaecc-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="aaecc-118">Permission</span></span>  |   <span data-ttu-id="aaecc-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="aaecc-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aaecc-120">Program</span><span class="sxs-lookup"><span data-stu-id="aaecc-120">Application</span></span> |   <span data-ttu-id="aaecc-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="aaecc-121">File.Read.All</span></span> | <span data-ttu-id="aaecc-122">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="aaecc-122">'Read file profiles'</span></span>
<span data-ttu-id="aaecc-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="aaecc-123">Delegated (work or school account)</span></span> | <span data-ttu-id="aaecc-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="aaecc-124">File.Read.All</span></span> | <span data-ttu-id="aaecc-125">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="aaecc-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="aaecc-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="aaecc-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="aaecc-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="aaecc-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="aaecc-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="aaecc-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="aaecc-129">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="aaecc-129">Request headers</span></span>

<span data-ttu-id="aaecc-130">Namn</span><span class="sxs-lookup"><span data-stu-id="aaecc-130">Name</span></span> | <span data-ttu-id="aaecc-131">Typ</span><span class="sxs-lookup"><span data-stu-id="aaecc-131">Type</span></span> | <span data-ttu-id="aaecc-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aaecc-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="aaecc-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="aaecc-133">Authorization</span></span> | <span data-ttu-id="aaecc-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="aaecc-134">String</span></span> | <span data-ttu-id="aaecc-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aaecc-135">Bearer {token}.</span></span> <span data-ttu-id="aaecc-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="aaecc-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="aaecc-137">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="aaecc-137">Request URI parameters</span></span>

<span data-ttu-id="aaecc-138">Namn</span><span class="sxs-lookup"><span data-stu-id="aaecc-138">Name</span></span> | <span data-ttu-id="aaecc-139">Typ</span><span class="sxs-lookup"><span data-stu-id="aaecc-139">Type</span></span> | <span data-ttu-id="aaecc-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aaecc-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="aaecc-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="aaecc-141">lookBackHours</span></span> | <span data-ttu-id="aaecc-142">Int32</span><span class="sxs-lookup"><span data-stu-id="aaecc-142">Int32</span></span> | <span data-ttu-id="aaecc-143">Definierar hur många timmar vi söker tillbaka för att få fram statistiken.</span><span class="sxs-lookup"><span data-stu-id="aaecc-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="aaecc-144">Standard är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="aaecc-144">Defaults to 30 days.</span></span> <span data-ttu-id="aaecc-145">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="aaecc-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="aaecc-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="aaecc-146">Request body</span></span>
<span data-ttu-id="aaecc-147">Tom</span><span class="sxs-lookup"><span data-stu-id="aaecc-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aaecc-148">Svar</span><span class="sxs-lookup"><span data-stu-id="aaecc-148">Response</span></span>
<span data-ttu-id="aaecc-149">Om det lyckas och det finns en fil – 200 OK med statistiska data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="aaecc-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="aaecc-150">Om filen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="aaecc-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="aaecc-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="aaecc-151">Example</span></span>

<span data-ttu-id="aaecc-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="aaecc-152">**Request**</span></span>

<span data-ttu-id="aaecc-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="aaecc-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="aaecc-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="aaecc-154">**Response**</span></span>

<span data-ttu-id="aaecc-155">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="aaecc-155">Here is an example of the response.</span></span>


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
