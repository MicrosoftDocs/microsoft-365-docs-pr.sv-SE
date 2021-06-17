---
title: Hämta API för domänstatistik
description: Lär dig hur du använder API:t för att hämta domänstatistik för att hämta statistik för den givna domänen i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, domän, domänrelaterade enheter
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998782"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="3bf88-104">Hämta API för domänstatistik</span><span class="sxs-lookup"><span data-stu-id="3bf88-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3bf88-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3bf88-105">**Applies to:**</span></span>
- [<span data-ttu-id="3bf88-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3bf88-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3bf88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bf88-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3bf88-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3bf88-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3bf88-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3bf88-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3bf88-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="3bf88-110">API description</span></span>
<span data-ttu-id="3bf88-111">Hämtar statistiken för den givna domänen.</span><span class="sxs-lookup"><span data-stu-id="3bf88-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="3bf88-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="3bf88-112">Limitations</span></span>
1. <span data-ttu-id="3bf88-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="3bf88-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3bf88-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3bf88-114">Permissions</span></span>
<span data-ttu-id="3bf88-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="3bf88-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3bf88-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3bf88-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3bf88-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3bf88-117">Permission type</span></span> |   <span data-ttu-id="3bf88-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3bf88-118">Permission</span></span>  |   <span data-ttu-id="3bf88-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3bf88-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3bf88-120">Program</span><span class="sxs-lookup"><span data-stu-id="3bf88-120">Application</span></span> |   <span data-ttu-id="3bf88-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="3bf88-121">URL.Read.All</span></span> |  <span data-ttu-id="3bf88-122">"Läs URL:er"</span><span class="sxs-lookup"><span data-stu-id="3bf88-122">'Read URLs'</span></span>
<span data-ttu-id="3bf88-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3bf88-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3bf88-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="3bf88-124">URL.Read.All</span></span> | <span data-ttu-id="3bf88-125">"Läs URL:er"</span><span class="sxs-lookup"><span data-stu-id="3bf88-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="3bf88-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="3bf88-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3bf88-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="3bf88-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3bf88-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3bf88-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="3bf88-129">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="3bf88-129">Request headers</span></span>

<span data-ttu-id="3bf88-130">Rubrik</span><span class="sxs-lookup"><span data-stu-id="3bf88-130">Header</span></span> | <span data-ttu-id="3bf88-131">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf88-131">Value</span></span> 
:---|:---
<span data-ttu-id="3bf88-132">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3bf88-132">Authorization</span></span> | <span data-ttu-id="3bf88-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3bf88-133">Bearer {token}.</span></span> <span data-ttu-id="3bf88-134">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3bf88-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="3bf88-135">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="3bf88-135">Request URI parameters</span></span>

<span data-ttu-id="3bf88-136">Namn</span><span class="sxs-lookup"><span data-stu-id="3bf88-136">Name</span></span> | <span data-ttu-id="3bf88-137">Typ</span><span class="sxs-lookup"><span data-stu-id="3bf88-137">Type</span></span> | <span data-ttu-id="3bf88-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3bf88-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="3bf88-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="3bf88-139">lookBackHours</span></span> | <span data-ttu-id="3bf88-140">Int32</span><span class="sxs-lookup"><span data-stu-id="3bf88-140">Int32</span></span> | <span data-ttu-id="3bf88-141">Definierar hur många timmar vi söker tillbaka för att få fram statistiken.</span><span class="sxs-lookup"><span data-stu-id="3bf88-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="3bf88-142">Standard är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="3bf88-142">Defaults to 30 days.</span></span> <span data-ttu-id="3bf88-143">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="3bf88-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3bf88-144">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="3bf88-144">Request body</span></span>
<span data-ttu-id="3bf88-145">Tom</span><span class="sxs-lookup"><span data-stu-id="3bf88-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3bf88-146">Svar</span><span class="sxs-lookup"><span data-stu-id="3bf88-146">Response</span></span>
<span data-ttu-id="3bf88-147">Om det lyckas och domän finns - 200 OK, med statistikobjekt i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="3bf88-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="3bf88-148">Om domänen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="3bf88-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3bf88-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="3bf88-149">Example</span></span>

<span data-ttu-id="3bf88-150">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="3bf88-150">**Request**</span></span>

<span data-ttu-id="3bf88-151">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="3bf88-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="3bf88-152">**Svar**</span><span class="sxs-lookup"><span data-stu-id="3bf88-152">**Response**</span></span>

<span data-ttu-id="3bf88-153">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="3bf88-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
