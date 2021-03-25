---
title: API för avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du kör avancerade sökfrågor med hjälp av Microsoft 365 Defenders avancerade API för sökning
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074801"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="b7057-104">API för avancerad sökning för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7057-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b7057-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b7057-105">**Applies to:**</span></span>

- <span data-ttu-id="b7057-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b7057-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7057-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="b7057-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b7057-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="b7057-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b7057-109">[Avancerad sökning](advanced-hunting-overview.md) är ett verktyg för hot efter hot som använder särskilt uppbyggda frågor för att undersöka de senaste 30 [dagarnas](advanced-hunting-query-language.md) händelsedata i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b7057-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="b7057-110">Du kan använda avancerade sökfrågor för att inspektera ovanlig aktivitet, identifiera möjliga hot och även svara på attacker.</span><span class="sxs-lookup"><span data-stu-id="b7057-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="b7057-111">Med API:t för avancerad sökning kan du programmässigt fråga händelsedata.</span><span class="sxs-lookup"><span data-stu-id="b7057-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="b7057-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="b7057-112">Quotas and resource allocation</span></span>

<span data-ttu-id="b7057-113">Följande villkor gäller för alla frågor.</span><span class="sxs-lookup"><span data-stu-id="b7057-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="b7057-114">Frågor utforskar och returnerar data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="b7057-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="b7057-115">Resultatet kan returnera upp till 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="b7057-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="b7057-116">Du kan ringa upp till 15 samtal per minut per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b7057-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="b7057-117">Du har 10 minuters körning per timme per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b7057-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="b7057-118">Du har fyra timmar körtid per dag per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b7057-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="b7057-119">Om en enskild begäran körs i mer än 10 minuter time out och returnerar ett fel.</span><span class="sxs-lookup"><span data-stu-id="b7057-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="b7057-120">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid.</span><span class="sxs-lookup"><span data-stu-id="b7057-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="b7057-121">Läs svarstexten för att förstå gränsen som du har nått.</span><span class="sxs-lookup"><span data-stu-id="b7057-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7057-122">Alla kvoter som anges ovan (till exempel 15 samtal per min) är per klientorganisationsstorlek.</span><span class="sxs-lookup"><span data-stu-id="b7057-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="b7057-123">Dessa kvoter är de lägsta.</span><span class="sxs-lookup"><span data-stu-id="b7057-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="b7057-124">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b7057-124">Permissions</span></span>

<span data-ttu-id="b7057-125">En av följande behörigheter krävs för att anropa det avancerade API:t för sökning.</span><span class="sxs-lookup"><span data-stu-id="b7057-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="b7057-126">Mer information, inklusive hur du väljer behörigheter, finns i Åtkomst till [API:er för Microsoft 365 Defender Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b7057-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="b7057-127">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b7057-127">Permission type</span></span> | <span data-ttu-id="b7057-128">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b7057-128">Permission</span></span> | <span data-ttu-id="b7057-129">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b7057-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="b7057-130">Program</span><span class="sxs-lookup"><span data-stu-id="b7057-130">Application</span></span> | <span data-ttu-id="b7057-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="b7057-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="b7057-132">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="b7057-132">Run advanced queries</span></span>
<span data-ttu-id="b7057-133">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b7057-133">Delegated (work or school account)</span></span> | <span data-ttu-id="b7057-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="b7057-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="b7057-135">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="b7057-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="b7057-136">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="b7057-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="b7057-137">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="b7057-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="b7057-138">Användaren måste ha åtkomst till enheten, baserat på enhetens gruppinställningar.</span><span class="sxs-lookup"><span data-stu-id="b7057-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="b7057-139">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b7057-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="b7057-140">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b7057-140">Request headers</span></span>

<span data-ttu-id="b7057-141">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="b7057-141">Header</span></span> | <span data-ttu-id="b7057-142">Value</span><span class="sxs-lookup"><span data-stu-id="b7057-142">Value</span></span>
-|-
<span data-ttu-id="b7057-143">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b7057-143">Authorization</span></span> | <span data-ttu-id="b7057-144">Bearer {token} **Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="b7057-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="b7057-145">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="b7057-145">Content-Type</span></span> | <span data-ttu-id="b7057-146">application/json</span><span class="sxs-lookup"><span data-stu-id="b7057-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="b7057-147">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b7057-147">Request body</span></span>

<span data-ttu-id="b7057-148">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="b7057-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b7057-149">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7057-149">Parameter</span></span> | <span data-ttu-id="b7057-150">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="b7057-150">Type</span></span> | <span data-ttu-id="b7057-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b7057-151">Description</span></span>
-|-|-
<span data-ttu-id="b7057-152">Fråga</span><span class="sxs-lookup"><span data-stu-id="b7057-152">Query</span></span> | <span data-ttu-id="b7057-153">Text</span><span class="sxs-lookup"><span data-stu-id="b7057-153">Text</span></span> | <span data-ttu-id="b7057-154">Frågan som ska köras.</span><span class="sxs-lookup"><span data-stu-id="b7057-154">The query to run.</span></span> <span data-ttu-id="b7057-155">**Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="b7057-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="b7057-156">Svar</span><span class="sxs-lookup"><span data-stu-id="b7057-156">Response</span></span>

<span data-ttu-id="b7057-157">Om det lyckas returnerar den här `200 OK` metoden och _ett QueryResponse-objekt_ i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="b7057-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="b7057-158">Svarsobjektet innehåller tre egenskaper på översta nivån:</span><span class="sxs-lookup"><span data-stu-id="b7057-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="b7057-159">Statistik – en ordlista med frågeprestandastatistik.</span><span class="sxs-lookup"><span data-stu-id="b7057-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="b7057-160">Schema – Schemat för svaret, en lista Name-Type par för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="b7057-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="b7057-161">Resultat – En lista över avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="b7057-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="b7057-162">Exempel</span><span class="sxs-lookup"><span data-stu-id="b7057-162">Example</span></span>

<span data-ttu-id="b7057-163">I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsobjekt som `Stats` innehåller `Schema` , och `Results` .</span><span class="sxs-lookup"><span data-stu-id="b7057-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="b7057-164">Fråga</span><span class="sxs-lookup"><span data-stu-id="b7057-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="b7057-165">Response-objekt</span><span class="sxs-lookup"><span data-stu-id="b7057-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="b7057-166">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="b7057-166">Related articles</span></span>

- [<span data-ttu-id="b7057-167">Åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="b7057-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b7057-168">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="b7057-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b7057-169">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="b7057-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b7057-170">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b7057-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
