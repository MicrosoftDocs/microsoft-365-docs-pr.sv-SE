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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998734"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="74111-104">Hämta IP-statistik-API</span><span class="sxs-lookup"><span data-stu-id="74111-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74111-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74111-105">**Applies to:**</span></span>
- [<span data-ttu-id="74111-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74111-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74111-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74111-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74111-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="74111-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="74111-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="74111-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="74111-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="74111-110">API description</span></span>
<span data-ttu-id="74111-111">Hämtar statistik för den givna IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="74111-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="74111-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="74111-112">Limitations</span></span>
1. <span data-ttu-id="74111-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="74111-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="74111-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="74111-114">Permissions</span></span>
<span data-ttu-id="74111-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="74111-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="74111-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="74111-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="74111-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="74111-117">Permission type</span></span> |   <span data-ttu-id="74111-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="74111-118">Permission</span></span>  |   <span data-ttu-id="74111-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="74111-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="74111-120">Program</span><span class="sxs-lookup"><span data-stu-id="74111-120">Application</span></span> |   <span data-ttu-id="74111-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="74111-121">Ip.Read.All</span></span> |   <span data-ttu-id="74111-122">"Läs IP-adressprofiler"</span><span class="sxs-lookup"><span data-stu-id="74111-122">'Read IP address profiles'</span></span>
<span data-ttu-id="74111-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="74111-123">Delegated (work or school account)</span></span> | <span data-ttu-id="74111-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="74111-124">Ip.Read.All</span></span> |  <span data-ttu-id="74111-125">"Läs IP-adressprofiler"</span><span class="sxs-lookup"><span data-stu-id="74111-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="74111-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="74111-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="74111-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="74111-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="74111-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="74111-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="74111-129">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="74111-129">Request headers</span></span>

<span data-ttu-id="74111-130">Namn</span><span class="sxs-lookup"><span data-stu-id="74111-130">Name</span></span> | <span data-ttu-id="74111-131">Typ</span><span class="sxs-lookup"><span data-stu-id="74111-131">Type</span></span> | <span data-ttu-id="74111-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74111-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="74111-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="74111-133">Authorization</span></span> | <span data-ttu-id="74111-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="74111-134">String</span></span> | <span data-ttu-id="74111-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="74111-135">Bearer {token}.</span></span> <span data-ttu-id="74111-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="74111-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="74111-137">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="74111-137">Request URI parameters</span></span>

<span data-ttu-id="74111-138">Namn</span><span class="sxs-lookup"><span data-stu-id="74111-138">Name</span></span> | <span data-ttu-id="74111-139">Typ</span><span class="sxs-lookup"><span data-stu-id="74111-139">Type</span></span> | <span data-ttu-id="74111-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74111-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="74111-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="74111-141">lookBackHours</span></span> | <span data-ttu-id="74111-142">Int32</span><span class="sxs-lookup"><span data-stu-id="74111-142">Int32</span></span> | <span data-ttu-id="74111-143">Definierar hur många timmar vi söker tillbaka för att få fram statistiken.</span><span class="sxs-lookup"><span data-stu-id="74111-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="74111-144">Standard är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="74111-144">Defaults to 30 days.</span></span> <span data-ttu-id="74111-145">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="74111-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="74111-146">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="74111-146">Request body</span></span>
<span data-ttu-id="74111-147">Tom</span><span class="sxs-lookup"><span data-stu-id="74111-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="74111-148">Svar</span><span class="sxs-lookup"><span data-stu-id="74111-148">Response</span></span>
<span data-ttu-id="74111-149">Om det lyckas och ip finns - 200 OK med statistiska data i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="74111-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="74111-150">IP finns inte – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="74111-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="74111-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="74111-151">Example</span></span>

<span data-ttu-id="74111-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="74111-152">**Request**</span></span>

<span data-ttu-id="74111-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="74111-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="74111-154">**Svar**</span><span class="sxs-lookup"><span data-stu-id="74111-154">**Response**</span></span>

<span data-ttu-id="74111-155">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="74111-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="74111-156">Namn</span><span class="sxs-lookup"><span data-stu-id="74111-156">Name</span></span> | <span data-ttu-id="74111-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74111-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="74111-158">Organisationens organisationers</span><span class="sxs-lookup"><span data-stu-id="74111-158">Organization prevalence</span></span> | <span data-ttu-id="74111-159">det distinkta antalet enheter som öppnade nätverksanslutningen till denna IP.</span><span class="sxs-lookup"><span data-stu-id="74111-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="74111-160">Org visas först</span><span class="sxs-lookup"><span data-stu-id="74111-160">Org first seen</span></span> | <span data-ttu-id="74111-161">den första anslutningen för denna IP i organisationen.</span><span class="sxs-lookup"><span data-stu-id="74111-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="74111-162">Org senast sedd</span><span class="sxs-lookup"><span data-stu-id="74111-162">Org last seen</span></span>  | <span data-ttu-id="74111-163">den sista anslutningen för denna IP i organisationen.</span><span class="sxs-lookup"><span data-stu-id="74111-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="74111-164">Den här statistiken baseras på data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="74111-164">This statistic information is based on data from the past 30 days.</span></span> 
