---
title: Advanced jakt-API
ms.reviewer: ''
description: Lär dig att använda API:t för avancerad sökning till att köra avancerade frågor på Microsoft Defender för Slutpunkt. Läs mer om begränsningar och se ett exempel.
keywords: apis, apis som stöds, avancerad sökning, fråga
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
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200203"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="f33f2-105">Api för avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="f33f2-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f33f2-106">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f33f2-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f33f2-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f33f2-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f33f2-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f33f2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="f33f2-109">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="f33f2-109">Limitations</span></span>
1. <span data-ttu-id="f33f2-110">Du kan endast köra en fråga på data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f33f2-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="f33f2-111">Resultatet kommer att innehålla högst 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="f33f2-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="f33f2-112">Antalet körningar är begränsat per klientorganisation:</span><span class="sxs-lookup"><span data-stu-id="f33f2-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="f33f2-113">API-anrop: Upp till 45 samtal per minut.</span><span class="sxs-lookup"><span data-stu-id="f33f2-113">API calls: Up to 45 calls per minute.</span></span>
   - <span data-ttu-id="f33f2-114">Körningstid: 10 minuters körningstid varje timme och 3 timmars körningstid per dag.</span><span class="sxs-lookup"><span data-stu-id="f33f2-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>
4. <span data-ttu-id="f33f2-115">Den maximala körningstiden för en enskild begäran är 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="f33f2-115">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="f33f2-116">429-svar motsvarar att nå en kvotgräns, antingen genom antal begäranden eller av cpu:n.</span><span class="sxs-lookup"><span data-stu-id="f33f2-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="f33f2-117">Läs svarstext för att förstå vilken gräns som har nåtts.</span><span class="sxs-lookup"><span data-stu-id="f33f2-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="f33f2-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="f33f2-118">Permissions</span></span>
<span data-ttu-id="f33f2-119">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="f33f2-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f33f2-120">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f33f2-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f33f2-121">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="f33f2-121">Permission type</span></span> |   <span data-ttu-id="f33f2-122">Behörighet</span><span class="sxs-lookup"><span data-stu-id="f33f2-122">Permission</span></span>  |   <span data-ttu-id="f33f2-123">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="f33f2-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f33f2-124">Program</span><span class="sxs-lookup"><span data-stu-id="f33f2-124">Application</span></span> |   <span data-ttu-id="f33f2-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="f33f2-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="f33f2-126">Kör avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="f33f2-126">'Run advanced queries'</span></span>
<span data-ttu-id="f33f2-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="f33f2-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f33f2-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="f33f2-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="f33f2-129">Kör avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="f33f2-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="f33f2-130">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="f33f2-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f33f2-131">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="f33f2-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="f33f2-132">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="f33f2-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f33f2-133">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="f33f2-133">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="f33f2-134">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="f33f2-134">Request headers</span></span>

<span data-ttu-id="f33f2-135">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="f33f2-135">Header</span></span> | <span data-ttu-id="f33f2-136">Värde</span><span class="sxs-lookup"><span data-stu-id="f33f2-136">Value</span></span> 
:---|:---
<span data-ttu-id="f33f2-137">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="f33f2-137">Authorization</span></span> | <span data-ttu-id="f33f2-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f33f2-138">Bearer {token}.</span></span> <span data-ttu-id="f33f2-139">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="f33f2-139">**Required**.</span></span>
<span data-ttu-id="f33f2-140">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="f33f2-140">Content-Type</span></span>    | <span data-ttu-id="f33f2-141">application/json</span><span class="sxs-lookup"><span data-stu-id="f33f2-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="f33f2-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="f33f2-142">Request body</span></span>
<span data-ttu-id="f33f2-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="f33f2-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f33f2-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="f33f2-144">Parameter</span></span> | <span data-ttu-id="f33f2-145">Skriv</span><span class="sxs-lookup"><span data-stu-id="f33f2-145">Type</span></span>    | <span data-ttu-id="f33f2-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f33f2-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="f33f2-147">Fråga</span><span class="sxs-lookup"><span data-stu-id="f33f2-147">Query</span></span> | <span data-ttu-id="f33f2-148">Text</span><span class="sxs-lookup"><span data-stu-id="f33f2-148">Text</span></span> |  <span data-ttu-id="f33f2-149">Frågan som ska köras.</span><span class="sxs-lookup"><span data-stu-id="f33f2-149">The query to run.</span></span> <span data-ttu-id="f33f2-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="f33f2-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="f33f2-151">Svar</span><span class="sxs-lookup"><span data-stu-id="f33f2-151">Response</span></span>
<span data-ttu-id="f33f2-152">Om det lyckas returnerar den här metoden 200 OK och _objektet QueryResponse_ i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="f33f2-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f33f2-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="f33f2-153">Example</span></span>

<span data-ttu-id="f33f2-154">Begäran</span><span class="sxs-lookup"><span data-stu-id="f33f2-154">Request</span></span>

<span data-ttu-id="f33f2-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="f33f2-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

<span data-ttu-id="f33f2-156">Svar</span><span class="sxs-lookup"><span data-stu-id="f33f2-156">Response</span></span>

<span data-ttu-id="f33f2-157">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="f33f2-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="f33f2-158">Det svarsobjekt som visas här kan trunkeras för korthet.</span><span class="sxs-lookup"><span data-stu-id="f33f2-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="f33f2-159">Alla egenskaper returneras från ett faktiskt samtal.</span><span class="sxs-lookup"><span data-stu-id="f33f2-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="f33f2-160">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="f33f2-160">Related topic</span></span>
- [<span data-ttu-id="f33f2-161">Introduktion till MICROSOFT Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="f33f2-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="f33f2-162">Avancerad sökning från portalen</span><span class="sxs-lookup"><span data-stu-id="f33f2-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f33f2-163">Advanced Hunting med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f33f2-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)