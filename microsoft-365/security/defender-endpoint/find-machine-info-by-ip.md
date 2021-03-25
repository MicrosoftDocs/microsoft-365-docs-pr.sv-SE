---
title: Hitta enhetsinformation genom internt IP API
description: Använd detta API för att skapa samtal som relaterar till att hitta en enhetspost runt en viss tidsstämpel efter intern IP.
keywords: ip, apis, graph api, API som stöds, hitta enhet, enhetsinformation
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167145"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="af61a-104">Hitta enhetsinformation genom internt IP API</span><span class="sxs-lookup"><span data-stu-id="af61a-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="af61a-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="af61a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="af61a-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="af61a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af61a-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="af61a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="af61a-108">Hitta en enhet genom intern IP.</span><span class="sxs-lookup"><span data-stu-id="af61a-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="af61a-109">Tidsstämpeln måste vara inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="af61a-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="af61a-110">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="af61a-110">Permissions</span></span>
<span data-ttu-id="af61a-111">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="af61a-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="af61a-112">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="af61a-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="af61a-113">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="af61a-113">Permission type</span></span> | <span data-ttu-id="af61a-114">Behörighet</span><span class="sxs-lookup"><span data-stu-id="af61a-114">Permission</span></span> | <span data-ttu-id="af61a-115">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="af61a-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="af61a-116">Program</span><span class="sxs-lookup"><span data-stu-id="af61a-116">Application</span></span> | <span data-ttu-id="af61a-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="af61a-117">Machine.Read.All</span></span> | <span data-ttu-id="af61a-118">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="af61a-118">'Read all machine profiles'</span></span>
<span data-ttu-id="af61a-119">Program</span><span class="sxs-lookup"><span data-stu-id="af61a-119">Application</span></span> | <span data-ttu-id="af61a-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="af61a-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="af61a-121">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="af61a-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="af61a-122">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="af61a-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="af61a-123">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="af61a-123">Request headers</span></span>

<span data-ttu-id="af61a-124">Namn</span><span class="sxs-lookup"><span data-stu-id="af61a-124">Name</span></span> | <span data-ttu-id="af61a-125">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="af61a-125">Type</span></span> | <span data-ttu-id="af61a-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="af61a-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="af61a-127">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="af61a-127">Authorization</span></span> | <span data-ttu-id="af61a-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="af61a-128">String</span></span> | <span data-ttu-id="af61a-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="af61a-129">Bearer {token}.</span></span> <span data-ttu-id="af61a-130">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="af61a-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="af61a-131">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="af61a-131">Request body</span></span>
<span data-ttu-id="af61a-132">Tom</span><span class="sxs-lookup"><span data-stu-id="af61a-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="af61a-133">Svar</span><span class="sxs-lookup"><span data-stu-id="af61a-133">Response</span></span>
<span data-ttu-id="af61a-134">Om det lyckas och datorn finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="af61a-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="af61a-135">Om ingen dator hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="af61a-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="af61a-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="af61a-136">Example</span></span>

<span data-ttu-id="af61a-137">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="af61a-137">**Request**</span></span>

<span data-ttu-id="af61a-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="af61a-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="af61a-139">**Svar**</span><span class="sxs-lookup"><span data-stu-id="af61a-139">**Response**</span></span>

<span data-ttu-id="af61a-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="af61a-140">Here is an example of the response.</span></span>

<span data-ttu-id="af61a-141">Svaret returnerar en lista över alla enheter som rapporterade den här IP-adressen inom 16 minuter före och efter tidsstämpeln.</span><span class="sxs-lookup"><span data-stu-id="af61a-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
