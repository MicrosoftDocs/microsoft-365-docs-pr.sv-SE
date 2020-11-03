---
title: 'Avancerade jakt-API: er'
description: Lär dig hur du kör avancerade frågor med hjälp av Microsoft 365 Defender API
keywords: 'Avancerad jakt, API: er, MTP'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844038"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="c7a8f-104">Avancerade jakt-API: er</span><span class="sxs-lookup"><span data-stu-id="c7a8f-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c7a8f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c7a8f-105">**Applies to:**</span></span>
- <span data-ttu-id="c7a8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7a8f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c7a8f-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c7a8f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="c7a8f-109">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="c7a8f-109">Limitations</span></span>
1. <span data-ttu-id="c7a8f-110">Du kan bara köra en fråga på data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="c7a8f-111">Resultaten inkluderar högst 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="c7a8f-112">Antalet körningar är begränsat per klient organisation: upp till 10 samtal per minut, 10 minuters kör tid varje timme och 4 timmar efter en dag.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="c7a8f-113">Maximal körnings tid för en enda begäran är 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="c7a8f-114">429-svaret kommer att representera en kvot gräns antingen per antal begär Anden eller per CPU.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="c7a8f-115">Svars texten för 429 anger också tiden tills kvoten förnyas.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="c7a8f-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c7a8f-116">Permissions</span></span>
<span data-ttu-id="c7a8f-117">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c7a8f-118">Om du vill veta mer, inklusive hur du väljer behörigheter, se [Microsoft 365 Defender API: er](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c7a8f-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="c7a8f-119">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="c7a8f-119">Permission type</span></span> |   <span data-ttu-id="c7a8f-120">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="c7a8f-120">Permission</span></span>  |   <span data-ttu-id="c7a8f-121">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="c7a8f-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c7a8f-122">Program</span><span class="sxs-lookup"><span data-stu-id="c7a8f-122">Application</span></span> |   <span data-ttu-id="c7a8f-123">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="c7a8f-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="c7a8f-124">"Kör avancerade frågor"</span><span class="sxs-lookup"><span data-stu-id="c7a8f-124">'Run advanced queries'</span></span>
<span data-ttu-id="c7a8f-125">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="c7a8f-125">Delegated (work or school account)</span></span> | <span data-ttu-id="c7a8f-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="c7a8f-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="c7a8f-127">"Kör avancerade frågor"</span><span class="sxs-lookup"><span data-stu-id="c7a8f-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="c7a8f-128">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="c7a8f-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c7a8f-129">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="c7a8f-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="c7a8f-130">Användaren måste ha åtkomst till enheten baserat på Inställningar för enhets grupp.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c7a8f-131">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="c7a8f-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c7a8f-132">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="c7a8f-132">Request headers</span></span>

<span data-ttu-id="c7a8f-133">Meddelande</span><span class="sxs-lookup"><span data-stu-id="c7a8f-133">Header</span></span> | <span data-ttu-id="c7a8f-134">Värde</span><span class="sxs-lookup"><span data-stu-id="c7a8f-134">Value</span></span> 
:---|:---
<span data-ttu-id="c7a8f-135">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="c7a8f-135">Authorization</span></span> | <span data-ttu-id="c7a8f-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-136">Bearer {token}.</span></span> <span data-ttu-id="c7a8f-137">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-137">**Required**.</span></span>
<span data-ttu-id="c7a8f-138">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="c7a8f-138">Content-Type</span></span>    | <span data-ttu-id="c7a8f-139">program/JSON</span><span class="sxs-lookup"><span data-stu-id="c7a8f-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c7a8f-140">Brödtext</span><span class="sxs-lookup"><span data-stu-id="c7a8f-140">Request body</span></span>
<span data-ttu-id="c7a8f-141">Ange ett JSON-objekt med följande parametrar i den efterfrågade texten:</span><span class="sxs-lookup"><span data-stu-id="c7a8f-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c7a8f-142">Indataparametern</span><span class="sxs-lookup"><span data-stu-id="c7a8f-142">Parameter</span></span> | <span data-ttu-id="c7a8f-143">Skriv</span><span class="sxs-lookup"><span data-stu-id="c7a8f-143">Type</span></span>    | <span data-ttu-id="c7a8f-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c7a8f-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="c7a8f-145">Frågeserver</span><span class="sxs-lookup"><span data-stu-id="c7a8f-145">Query</span></span> | <span data-ttu-id="c7a8f-146">Text</span><span class="sxs-lookup"><span data-stu-id="c7a8f-146">Text</span></span> |  <span data-ttu-id="c7a8f-147">Frågan att köra.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-147">The query to run.</span></span> <span data-ttu-id="c7a8f-148">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c7a8f-149">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="c7a8f-149">Response</span></span>
<span data-ttu-id="c7a8f-150">Om det lyckas returnerar den här metoden 200 OK och _QueryResponse_ -objekt i svars texten.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="c7a8f-151">Response-objektet är uppdelat till 3 delar (egenskaper):</span><span class="sxs-lookup"><span data-stu-id="c7a8f-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="c7a8f-152">```Stats``` -Fråga prestanda statistik.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="c7a8f-153">```Schema``` -Schemat för svaret, en lista över Name-Type par för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="c7a8f-154">```Results``` – En lista över avancerade jakt händelser.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c7a8f-155">Exempel</span><span class="sxs-lookup"><span data-stu-id="c7a8f-155">Example</span></span>

<span data-ttu-id="c7a8f-156">Ställning</span><span class="sxs-lookup"><span data-stu-id="c7a8f-156">Request</span></span>

<span data-ttu-id="c7a8f-157">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="c7a8f-158">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="c7a8f-158">Response</span></span>

<span data-ttu-id="c7a8f-159">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="c7a8f-159">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="c7a8f-160">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="c7a8f-160">Related topic</span></span>
- [<span data-ttu-id="c7a8f-161">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7a8f-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
