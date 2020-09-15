---
title: 'Avancerade jakt-API: er'
description: Lär dig hur du kör avancerade frågor med hjälp av Microsoft Threat Protection API
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650594"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="d4979-104">Avancerade jakt-API: er</span><span class="sxs-lookup"><span data-stu-id="d4979-104">Advanced hunting APIs</span></span>

<span data-ttu-id="d4979-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d4979-105">**Applies to:**</span></span>
- <span data-ttu-id="d4979-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d4979-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="d4979-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="d4979-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d4979-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="d4979-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="d4979-109">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="d4979-109">Limitations</span></span>
1. <span data-ttu-id="d4979-110">Du kan bara köra en fråga på data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="d4979-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="d4979-111">Resultaten inkluderar högst 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="d4979-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="d4979-112">Antalet körningar är begränsat per klient organisation: upp till 15 samtal per minut, 15 minuters kör tid varje timme och 4 timmar efter en dag.</span><span class="sxs-lookup"><span data-stu-id="d4979-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="d4979-113">Maximal körnings tid för en enda begäran är 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="d4979-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="d4979-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="d4979-114">Permissions</span></span>
<span data-ttu-id="d4979-115">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="d4979-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d4979-116">Om du vill veta mer, inklusive hur du väljer behörigheter, se [använda API: er för skydd mot Microsoft Threat Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="d4979-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="d4979-117">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="d4979-117">Permission type</span></span> |   <span data-ttu-id="d4979-118">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="d4979-118">Permission</span></span>  |   <span data-ttu-id="d4979-119">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="d4979-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d4979-120">Program</span><span class="sxs-lookup"><span data-stu-id="d4979-120">Application</span></span> |   <span data-ttu-id="d4979-121">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="d4979-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="d4979-122">"Kör avancerade frågor"</span><span class="sxs-lookup"><span data-stu-id="d4979-122">'Run advanced queries'</span></span>
<span data-ttu-id="d4979-123">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="d4979-123">Delegated (work or school account)</span></span> | <span data-ttu-id="d4979-124">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="d4979-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="d4979-125">"Kör avancerade frågor"</span><span class="sxs-lookup"><span data-stu-id="d4979-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="d4979-126">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="d4979-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d4979-127">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="d4979-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="d4979-128">Användaren måste ha åtkomst till enheten baserat på Inställningar för enhets grupp.</span><span class="sxs-lookup"><span data-stu-id="d4979-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="d4979-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="d4979-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="d4979-130">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="d4979-130">Request headers</span></span>

<span data-ttu-id="d4979-131">Meddelande</span><span class="sxs-lookup"><span data-stu-id="d4979-131">Header</span></span> | <span data-ttu-id="d4979-132">Value</span><span class="sxs-lookup"><span data-stu-id="d4979-132">Value</span></span> 
:---|:---
<span data-ttu-id="d4979-133">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="d4979-133">Authorization</span></span> | <span data-ttu-id="d4979-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d4979-134">Bearer {token}.</span></span> <span data-ttu-id="d4979-135">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="d4979-135">**Required**.</span></span>
<span data-ttu-id="d4979-136">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="d4979-136">Content-Type</span></span>    | <span data-ttu-id="d4979-137">program/JSON</span><span class="sxs-lookup"><span data-stu-id="d4979-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="d4979-138">Brödtext</span><span class="sxs-lookup"><span data-stu-id="d4979-138">Request body</span></span>
<span data-ttu-id="d4979-139">Ange ett JSON-objekt med följande parametrar i den efterfrågade texten:</span><span class="sxs-lookup"><span data-stu-id="d4979-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d4979-140">Indataparametern</span><span class="sxs-lookup"><span data-stu-id="d4979-140">Parameter</span></span> | <span data-ttu-id="d4979-141">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="d4979-141">Type</span></span>    | <span data-ttu-id="d4979-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4979-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="d4979-143">Frågeserver</span><span class="sxs-lookup"><span data-stu-id="d4979-143">Query</span></span> | <span data-ttu-id="d4979-144">Text</span><span class="sxs-lookup"><span data-stu-id="d4979-144">Text</span></span> |  <span data-ttu-id="d4979-145">Frågan att köra.</span><span class="sxs-lookup"><span data-stu-id="d4979-145">The query to run.</span></span> <span data-ttu-id="d4979-146">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="d4979-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="d4979-147">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="d4979-147">Response</span></span>
<span data-ttu-id="d4979-148">Om det lyckas returnerar den här metoden 200 OK och _QueryResponse_ -objekt i svars texten.</span><span class="sxs-lookup"><span data-stu-id="d4979-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="d4979-149">Response-objektet är uppdelat till 3 delar (egenskaper):</span><span class="sxs-lookup"><span data-stu-id="d4979-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="d4979-150">```Stats``` -Fråga prestanda statistik.</span><span class="sxs-lookup"><span data-stu-id="d4979-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="d4979-151">```Schema``` -Schemat för svaret, en lista med namn-textpar för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="d4979-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="d4979-152">```Results``` – En lista över avancerade jakt händelser.</span><span class="sxs-lookup"><span data-stu-id="d4979-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="d4979-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="d4979-153">Example</span></span>

<span data-ttu-id="d4979-154">Ställning</span><span class="sxs-lookup"><span data-stu-id="d4979-154">Request</span></span>

<span data-ttu-id="d4979-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="d4979-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="d4979-156">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="d4979-156">Response</span></span>

<span data-ttu-id="d4979-157">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="d4979-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="d4979-158">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="d4979-158">Related topic</span></span>
- [<span data-ttu-id="d4979-159">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="d4979-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
