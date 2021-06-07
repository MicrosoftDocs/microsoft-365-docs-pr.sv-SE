---
title: Hämta IP-statistik-API
description: Få de senaste statistikerna för din IP med hjälp av Microsoft Defender för Endpoint.
keywords: apis, graph api, api som stöds, skaffa, ip, statistik, dokumentation
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
ms.openlocfilehash: 55bf10d01093c17ba2d186ce0a1d1313db2c3a75
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770091"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="d4363-104">Hämta IP-statistik-API</span><span class="sxs-lookup"><span data-stu-id="d4363-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d4363-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d4363-105">**Applies to:**</span></span>
- [<span data-ttu-id="d4363-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d4363-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d4363-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4363-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d4363-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d4363-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d4363-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d4363-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d4363-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4363-110">API description</span></span>
<span data-ttu-id="d4363-111">Hämtar statistik för den givna IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="d4363-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="d4363-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="d4363-112">Limitations</span></span>
1. <span data-ttu-id="d4363-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="d4363-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="d4363-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="d4363-114">Permissions</span></span>
<span data-ttu-id="d4363-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="d4363-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d4363-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d4363-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d4363-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="d4363-117">Permission type</span></span> |   <span data-ttu-id="d4363-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d4363-118">Permission</span></span>  |   <span data-ttu-id="d4363-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="d4363-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d4363-120">Program</span><span class="sxs-lookup"><span data-stu-id="d4363-120">Application</span></span> |   <span data-ttu-id="d4363-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="d4363-121">Ip.Read.All</span></span> |   <span data-ttu-id="d4363-122">"Läs IP-adressprofiler"</span><span class="sxs-lookup"><span data-stu-id="d4363-122">'Read IP address profiles'</span></span>
<span data-ttu-id="d4363-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="d4363-123">Delegated (work or school account)</span></span> | <span data-ttu-id="d4363-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="d4363-124">Ip.Read.All</span></span> |  <span data-ttu-id="d4363-125">"Läs IP-adressprofiler"</span><span class="sxs-lookup"><span data-stu-id="d4363-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="d4363-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="d4363-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d4363-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="d4363-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d4363-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="d4363-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="d4363-129">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="d4363-129">Request headers</span></span>

<span data-ttu-id="d4363-130">Namn</span><span class="sxs-lookup"><span data-stu-id="d4363-130">Name</span></span> | <span data-ttu-id="d4363-131">Typ</span><span class="sxs-lookup"><span data-stu-id="d4363-131">Type</span></span> | <span data-ttu-id="d4363-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4363-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="d4363-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="d4363-133">Authorization</span></span> | <span data-ttu-id="d4363-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="d4363-134">String</span></span> | <span data-ttu-id="d4363-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d4363-135">Bearer {token}.</span></span> <span data-ttu-id="d4363-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="d4363-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="d4363-137">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="d4363-137">Request URI parameters</span></span>

<span data-ttu-id="d4363-138">Namn</span><span class="sxs-lookup"><span data-stu-id="d4363-138">Name</span></span> | <span data-ttu-id="d4363-139">Typ</span><span class="sxs-lookup"><span data-stu-id="d4363-139">Type</span></span> | <span data-ttu-id="d4363-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4363-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="d4363-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="d4363-141">lookBackHours</span></span> | <span data-ttu-id="d4363-142">Int32</span><span class="sxs-lookup"><span data-stu-id="d4363-142">Int32</span></span> | <span data-ttu-id="d4363-143">Definierar hur många timmar vi söker tillbaka för att få fram statistiken.</span><span class="sxs-lookup"><span data-stu-id="d4363-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="d4363-144">Standard är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="d4363-144">Defaults to 30 days.</span></span> <span data-ttu-id="d4363-145">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="d4363-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d4363-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="d4363-146">Request body</span></span>
<span data-ttu-id="d4363-147">Tom</span><span class="sxs-lookup"><span data-stu-id="d4363-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d4363-148">Svar</span><span class="sxs-lookup"><span data-stu-id="d4363-148">Response</span></span>
<span data-ttu-id="d4363-149">Om det lyckas och ip finns - 200 OK med statistiska data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="d4363-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="d4363-150">IP finns inte – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="d4363-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d4363-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="d4363-151">Example</span></span>

<span data-ttu-id="d4363-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="d4363-152">**Request**</span></span>

<span data-ttu-id="d4363-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="d4363-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="d4363-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="d4363-154">**Response**</span></span>

<span data-ttu-id="d4363-155">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="d4363-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="d4363-156">Namn</span><span class="sxs-lookup"><span data-stu-id="d4363-156">Name</span></span> | <span data-ttu-id="d4363-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4363-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="d4363-158">Organisations hos en organisation</span><span class="sxs-lookup"><span data-stu-id="d4363-158">Org prevalence</span></span> | <span data-ttu-id="d4363-159">det distinkta antalet enheter som öppnade nätverksanslutningen till denna IP.</span><span class="sxs-lookup"><span data-stu-id="d4363-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="d4363-160">Org visas först</span><span class="sxs-lookup"><span data-stu-id="d4363-160">Org first seen</span></span> | <span data-ttu-id="d4363-161">den första anslutningen för denna IP i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d4363-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="d4363-162">Org senast sedd</span><span class="sxs-lookup"><span data-stu-id="d4363-162">Org last seen</span></span>  | <span data-ttu-id="d4363-163">den sista anslutningen för denna IP i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d4363-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="d4363-164">Den här statistiken baseras på data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="d4363-164">This statistic information is based on data from the past 30 days.</span></span> 
