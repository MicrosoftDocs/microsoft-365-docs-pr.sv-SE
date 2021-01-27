---
title: Microsoft 365 Defender Advanced jakt-API
description: Lär dig hur du kör avancerade jakt frågor med Microsoft 365 Defender s Advanced jakt API
keywords: 'Avancerad jakt, API: er, MTP, M365 Defender, Microsoft 365 Defender'
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988122"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="8c4c9-104">Microsoft 365 Defender Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="8c4c9-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8c4c9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8c4c9-105">**Applies to:**</span></span>

- <span data-ttu-id="8c4c9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c4c9-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c4c9-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8c4c9-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8c4c9-109">[Avancerad jakt](advanced-hunting-overview.md) är ett hot-jakt-verktyg som använder [särskilt utformade frågor](advanced-hunting-query-language.md) för att undersöka de senaste 30 dagarna av händelse data i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="8c4c9-110">Du kan använda avancerade jakt frågor för att kontrol lera ovanlig aktivitet, upptäcka möjliga hot och till och med reagera på attacker.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="8c4c9-111">Med Advanced jakt API kan du programatically fråga efter händelse data.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="8c4c9-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="8c4c9-112">Quotas and resource allocation</span></span>

<span data-ttu-id="8c4c9-113">Följande villkor gäller för alla frågor.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="8c4c9-114">Frågor utforskar och returnerar data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="8c4c9-115">Resultaten kan returnera upp till 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="8c4c9-116">Du kan ringa upp till 15 samtal per minut per klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="8c4c9-117">Du har 10 minuters kör tid per timme per klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="8c4c9-118">Du har fyra totala timmar med kör tid per dag per klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="8c4c9-119">Om en enda begäran körs i mer än 10 minuter upphör den att fungera och ett fel meddelande returneras.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="8c4c9-120">En `429` http-svarskod visar att du har nått en kvot, antingen av antalet begär Anden som skickats eller via utsatt tid för drift.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="8c4c9-121">Läs svars texten för att förstå den gräns du har uppnått.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c4c9-122">Alla kvoter ovan (till exempel 15 samtal per minut) är per innehavare.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="8c4c9-123">De här kvoterna är minst.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="8c4c9-124">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="8c4c9-124">Permissions</span></span>

<span data-ttu-id="8c4c9-125">En av följande behörigheter krävs för att kunna ringa det avancerade jakt-API: t.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="8c4c9-126">Om du vill veta mer, inklusive hur du väljer behörigheter, läser du [gå till Microsoft 365 Defender-skydds-API: erna](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="8c4c9-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="8c4c9-127">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="8c4c9-127">Permission type</span></span> | <span data-ttu-id="8c4c9-128">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="8c4c9-128">Permission</span></span> | <span data-ttu-id="8c4c9-129">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="8c4c9-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="8c4c9-130">Program</span><span class="sxs-lookup"><span data-stu-id="8c4c9-130">Application</span></span> | <span data-ttu-id="8c4c9-131">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="8c4c9-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="8c4c9-132">Kör avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="8c4c9-132">Run advanced queries</span></span>
<span data-ttu-id="8c4c9-133">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="8c4c9-133">Delegated (work or school account)</span></span> | <span data-ttu-id="8c4c9-134">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="8c4c9-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="8c4c9-135">Kör avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="8c4c9-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="8c4c9-136">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="8c4c9-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="8c4c9-137">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="8c4c9-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="8c4c9-138">Användaren måste ha åtkomst till enheten baserat på Inställningar för enhets grupp.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="8c4c9-139">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8c4c9-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="8c4c9-140">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="8c4c9-140">Request headers</span></span>

<span data-ttu-id="8c4c9-141">Meddelande</span><span class="sxs-lookup"><span data-stu-id="8c4c9-141">Header</span></span> | <span data-ttu-id="8c4c9-142">Value</span><span class="sxs-lookup"><span data-stu-id="8c4c9-142">Value</span></span>
-|-
<span data-ttu-id="8c4c9-143">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="8c4c9-143">Authorization</span></span> | <span data-ttu-id="8c4c9-144">Bevarad {token} **Obs!**</span><span class="sxs-lookup"><span data-stu-id="8c4c9-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="8c4c9-145">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="8c4c9-145">Content-Type</span></span> | <span data-ttu-id="8c4c9-146">program/JSON</span><span class="sxs-lookup"><span data-stu-id="8c4c9-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="8c4c9-147">Brödtext</span><span class="sxs-lookup"><span data-stu-id="8c4c9-147">Request body</span></span>

<span data-ttu-id="8c4c9-148">Ange ett JSON-objekt med följande parametrar i den efterfrågade texten:</span><span class="sxs-lookup"><span data-stu-id="8c4c9-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8c4c9-149">Indataparametern</span><span class="sxs-lookup"><span data-stu-id="8c4c9-149">Parameter</span></span> | <span data-ttu-id="8c4c9-150">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="8c4c9-150">Type</span></span> | <span data-ttu-id="8c4c9-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c4c9-151">Description</span></span>
-|-|-
<span data-ttu-id="8c4c9-152">Frågeserver</span><span class="sxs-lookup"><span data-stu-id="8c4c9-152">Query</span></span> | <span data-ttu-id="8c4c9-153">Text</span><span class="sxs-lookup"><span data-stu-id="8c4c9-153">Text</span></span> | <span data-ttu-id="8c4c9-154">Frågan att köra.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-154">The query to run.</span></span> <span data-ttu-id="8c4c9-155">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="8c4c9-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="8c4c9-156">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="8c4c9-156">Response</span></span>

<span data-ttu-id="8c4c9-157">Om det lyckas returneras den här metoden `200 OK` och ett _QueryResponse_ -objekt i svars texten.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="8c4c9-158">Response-objektet innehåller tre högsta nivå egenskaper:</span><span class="sxs-lookup"><span data-stu-id="8c4c9-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="8c4c9-159">Statistik – en ord lista med prestanda statistik för frågor.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="8c4c9-160">Schema – schemat för svaret, en lista över Name-Type par för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="8c4c9-161">Resultat – en lista över avancerade jakt händelser.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="8c4c9-162">Exempel</span><span class="sxs-lookup"><span data-stu-id="8c4c9-162">Example</span></span>

<span data-ttu-id="8c4c9-163">I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsmeddelande som innehåller `Stats` , `Schema` , och `Results` .</span><span class="sxs-lookup"><span data-stu-id="8c4c9-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="8c4c9-164">Frågeserver</span><span class="sxs-lookup"><span data-stu-id="8c4c9-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="8c4c9-165">Response-objekt</span><span class="sxs-lookup"><span data-stu-id="8c4c9-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="8c4c9-166">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="8c4c9-166">Related articles</span></span>

- [<span data-ttu-id="8c4c9-167">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c4c9-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8c4c9-168">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="8c4c9-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="8c4c9-169">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="8c4c9-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="8c4c9-170">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8c4c9-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
