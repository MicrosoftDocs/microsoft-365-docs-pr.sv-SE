---
title: Få enhet säker poäng
description: Hämtar organisationens säkerhetsresultat.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166882"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="68f78-104">Få enhet säker poäng</span><span class="sxs-lookup"><span data-stu-id="68f78-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68f78-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="68f78-105">**Applies to:**</span></span>
- [<span data-ttu-id="68f78-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="68f78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68f78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68f78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="68f78-108">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="68f78-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="68f78-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="68f78-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68f78-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="68f78-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="68f78-111">Hämtar Microsoft [Secure Score för enheter.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="68f78-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="68f78-112">Ett högre Microsoft Secure Score för enheter innebär att dina slutpunkter är mer flexibel mot attacker mot hot om cyberhot.</span><span class="sxs-lookup"><span data-stu-id="68f78-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="68f78-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="68f78-113">Permissions</span></span>

<span data-ttu-id="68f78-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="68f78-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="68f78-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="68f78-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="68f78-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="68f78-116">Permission type</span></span> |   <span data-ttu-id="68f78-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="68f78-117">Permission</span></span>  |   <span data-ttu-id="68f78-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="68f78-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="68f78-119">Program</span><span class="sxs-lookup"><span data-stu-id="68f78-119">Application</span></span> |   <span data-ttu-id="68f78-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="68f78-120">Score.Read.Alll</span></span> |   <span data-ttu-id="68f78-121">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="68f78-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="68f78-122">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="68f78-122">Delegated (work or school account)</span></span> | <span data-ttu-id="68f78-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="68f78-123">Score.Read</span></span> | <span data-ttu-id="68f78-124">"Read Threat and Vulnerability Management Score"</span><span class="sxs-lookup"><span data-stu-id="68f78-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="68f78-125">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="68f78-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="68f78-126">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="68f78-126">Request headers</span></span>

<span data-ttu-id="68f78-127">Namn</span><span class="sxs-lookup"><span data-stu-id="68f78-127">Name</span></span> | <span data-ttu-id="68f78-128">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="68f78-128">Type</span></span> | <span data-ttu-id="68f78-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="68f78-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="68f78-130">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="68f78-130">Authorization</span></span> | <span data-ttu-id="68f78-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="68f78-131">String</span></span> | <span data-ttu-id="68f78-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="68f78-132">Bearer {token}.</span></span> <span data-ttu-id="68f78-133">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="68f78-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="68f78-134">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="68f78-134">Request body</span></span>

<span data-ttu-id="68f78-135">Tom</span><span class="sxs-lookup"><span data-stu-id="68f78-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="68f78-136">Svar</span><span class="sxs-lookup"><span data-stu-id="68f78-136">Response</span></span>

<span data-ttu-id="68f78-137">Om det lyckas returnerar den här metoden 200 OK, med enhetens säkra poängdata i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="68f78-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="68f78-138">Exempel</span><span class="sxs-lookup"><span data-stu-id="68f78-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="68f78-139">Begäran</span><span class="sxs-lookup"><span data-stu-id="68f78-139">Request</span></span>

<span data-ttu-id="68f78-140">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="68f78-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="68f78-141">Svar</span><span class="sxs-lookup"><span data-stu-id="68f78-141">Response</span></span>

<span data-ttu-id="68f78-142">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="68f78-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="68f78-143">Svarslistan som visas här kan trunkeras för att vara kort.</span><span class="sxs-lookup"><span data-stu-id="68f78-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="68f78-144">Se även</span><span class="sxs-lookup"><span data-stu-id="68f78-144">See also</span></span>

- [<span data-ttu-id="68f78-145">OData-frågor med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="68f78-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
