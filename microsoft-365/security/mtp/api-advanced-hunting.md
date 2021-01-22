---
title: API för avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du kör avancerade sökfrågor med hjälp av Microsoft 365 Defenders avancerade API för sökningar
keywords: Advanced Hunting, API:er, api, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932088"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="c829f-104">API för Microsoft 365 Defender Advanced-sökning</span><span class="sxs-lookup"><span data-stu-id="c829f-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c829f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c829f-105">**Applies to:**</span></span>

- <span data-ttu-id="c829f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c829f-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c829f-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="c829f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c829f-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="c829f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c829f-109">[Avancerad sökning](advanced-hunting-overview.md) är ett verktyg för hot efter hot som använder [särskilt](advanced-hunting-query-language.md) uppbyggda frågor för att undersöka händelsedata för de senaste 30 dagarna i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c829f-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="c829f-110">Du kan använda avancerade sökningsfrågor för att inspektera ovanlig aktivitet, identifiera möjliga hot och även svara på attacker.</span><span class="sxs-lookup"><span data-stu-id="c829f-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="c829f-111">Med API:t för avancerad sökning kan du programmässigt fråga händelsedata.</span><span class="sxs-lookup"><span data-stu-id="c829f-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="c829f-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="c829f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="c829f-113">Följande villkor gäller för alla frågor.</span><span class="sxs-lookup"><span data-stu-id="c829f-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="c829f-114">Frågor utforskar och returnerar data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c829f-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="c829f-115">Resultatet kan returnera upp till 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="c829f-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="c829f-116">Du kan ringa upp till 10 samtal per minut per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c829f-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="c829f-117">Du har 10 minuters körning per timme per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c829f-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="c829f-118">Du har totalt fyra timmar löpande dag per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c829f-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="c829f-119">Om en enskild begäran körs i mer än 10 minuter time out och returnerar ett fel.</span><span class="sxs-lookup"><span data-stu-id="c829f-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="c829f-120">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas eller `429` med tilldelad körningstid.</span><span class="sxs-lookup"><span data-stu-id="c829f-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="c829f-121">Svarstexten innehåller tiden tills kvoten du har nått återställs.</span><span class="sxs-lookup"><span data-stu-id="c829f-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="c829f-122">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c829f-122">Permissions</span></span>

<span data-ttu-id="c829f-123">En av följande behörigheter krävs för att anropa API för avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="c829f-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="c829f-124">Mer information, inklusive hur du väljer behörigheter, finns i Access API:er för [Microsoft 365 Defender Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c829f-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="c829f-125">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="c829f-125">Permission type</span></span> | <span data-ttu-id="c829f-126">Behörighet</span><span class="sxs-lookup"><span data-stu-id="c829f-126">Permission</span></span> | <span data-ttu-id="c829f-127">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="c829f-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="c829f-128">Program</span><span class="sxs-lookup"><span data-stu-id="c829f-128">Application</span></span> | <span data-ttu-id="c829f-129">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="c829f-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="c829f-130">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="c829f-130">Run advanced queries</span></span>
<span data-ttu-id="c829f-131">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="c829f-131">Delegated (work or school account)</span></span> | <span data-ttu-id="c829f-132">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="c829f-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="c829f-133">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="c829f-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="c829f-134">När du skaffar ett token med användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="c829f-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="c829f-135">Användaren måste ha AD-rollen Visa data</span><span class="sxs-lookup"><span data-stu-id="c829f-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="c829f-136">Användaren måste ha åtkomst till enheten, baserat på enhetsgruppsinställningar.</span><span class="sxs-lookup"><span data-stu-id="c829f-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c829f-137">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="c829f-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c829f-138">Begär sidhuvuden</span><span class="sxs-lookup"><span data-stu-id="c829f-138">Request headers</span></span>

<span data-ttu-id="c829f-139">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="c829f-139">Header</span></span> | <span data-ttu-id="c829f-140">Value</span><span class="sxs-lookup"><span data-stu-id="c829f-140">Value</span></span>
-|-
<span data-ttu-id="c829f-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="c829f-141">Authorization</span></span> | <span data-ttu-id="c829f-142">Bearer {token} **Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="c829f-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="c829f-143">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="c829f-143">Content-Type</span></span> | <span data-ttu-id="c829f-144">application/json</span><span class="sxs-lookup"><span data-stu-id="c829f-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c829f-145">Begärandetext</span><span class="sxs-lookup"><span data-stu-id="c829f-145">Request body</span></span>

<span data-ttu-id="c829f-146">Ange ett JSON-objekt med följande parametrar i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="c829f-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c829f-147">Parameter</span><span class="sxs-lookup"><span data-stu-id="c829f-147">Parameter</span></span> | <span data-ttu-id="c829f-148">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="c829f-148">Type</span></span> | <span data-ttu-id="c829f-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c829f-149">Description</span></span>
-|-|-
<span data-ttu-id="c829f-150">Fråga</span><span class="sxs-lookup"><span data-stu-id="c829f-150">Query</span></span> | <span data-ttu-id="c829f-151">Text</span><span class="sxs-lookup"><span data-stu-id="c829f-151">Text</span></span> | <span data-ttu-id="c829f-152">Frågan som ska köras.</span><span class="sxs-lookup"><span data-stu-id="c829f-152">The query to run.</span></span> <span data-ttu-id="c829f-153">**Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="c829f-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="c829f-154">Svar</span><span class="sxs-lookup"><span data-stu-id="c829f-154">Response</span></span>

<span data-ttu-id="c829f-155">Om det lyckas returneras den här `200 OK` metoden och _ett QueryResponse-objekt_ i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="c829f-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="c829f-156">Svarsobjektet innehåller tre egenskaper på översta nivån:</span><span class="sxs-lookup"><span data-stu-id="c829f-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="c829f-157">Statistik – en ordlista för frågeprestandastatistik.</span><span class="sxs-lookup"><span data-stu-id="c829f-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="c829f-158">Schema – Schemat för svaret, en lista Name-Type par för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="c829f-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="c829f-159">Resultat – En lista över avancerade sökningsevenemang.</span><span class="sxs-lookup"><span data-stu-id="c829f-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c829f-160">Exempel</span><span class="sxs-lookup"><span data-stu-id="c829f-160">Example</span></span>

<span data-ttu-id="c829f-161">I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsobjekt som `Stats` innehåller `Schema` , `Results` och.</span><span class="sxs-lookup"><span data-stu-id="c829f-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="c829f-162">Fråga</span><span class="sxs-lookup"><span data-stu-id="c829f-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="c829f-163">Response-objekt</span><span class="sxs-lookup"><span data-stu-id="c829f-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c829f-164">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="c829f-164">Related articles</span></span>

- [<span data-ttu-id="c829f-165">Få åtkomst till API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c829f-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c829f-166">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="c829f-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c829f-167">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="c829f-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c829f-168">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c829f-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
