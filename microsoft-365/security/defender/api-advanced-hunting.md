---
title: Microsoft 365 API för avancerad sökning för Defender
description: Lär dig hur du kör avancerade sökfrågor med Microsoft 365 Defenders avancerade API för sökning
keywords: Advanced Hunting, API:er, api, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769593"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="6ef1f-104">Microsoft 365 API för avancerad sökning för Defender</span><span class="sxs-lookup"><span data-stu-id="6ef1f-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6ef1f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6ef1f-105">**Applies to:**</span></span>

- <span data-ttu-id="6ef1f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ef1f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef1f-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6ef1f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6ef1f-109">[Avancerad sökning](advanced-hunting-overview.md) är ett verktyg för hot efter hot som använder specialkonstruktiona frågor för att undersöka de senaste 30 [dagarnas](advanced-hunting-query-language.md) händelsedata i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="6ef1f-110">Du kan använda avancerade sökfrågor för att inspektera ovanlig aktivitet, identifiera möjliga hot och även svara på attacker.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="6ef1f-111">Med API:t för avancerad sökning kan du programmässigt fråga händelsedata.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6ef1f-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="6ef1f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6ef1f-113">Följande villkor gäller för alla frågor.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="6ef1f-114">Frågor utforskar och returnerar data från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="6ef1f-115">Resultatet kan returnera upp till 100 000 rader.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="6ef1f-116">Du kan ringa upp till 15 samtal per minut per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="6ef1f-117">Frågor blockeras om klientorganisationen har nått 100 % till efter den kommande 15-minuterscykeln.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="6ef1f-118">Om en enskild begäran körs i mer än 10 minuter time out och returnerar ett fel.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="6ef1f-119">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6ef1f-120">Läs svarstexten för att förstå gränsen som du har nått.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="6ef1f-121">Alla kvoter som anges ovan (till exempel 15 samtal per min) är per klientorganisationsstorlek.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="6ef1f-122">Dessa kvoter är de lägsta.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="6ef1f-123">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6ef1f-123">Permissions</span></span>

<span data-ttu-id="6ef1f-124">En av följande behörigheter krävs för att anropa det avancerade API:t för sökning.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="6ef1f-125">Mer information, inklusive hur du väljer behörigheter, finns i [Komma åt MICROSOFT 365 Defender Protection-API:er](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6ef1f-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="6ef1f-126">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="6ef1f-126">Permission type</span></span> | <span data-ttu-id="6ef1f-127">Behörighet</span><span class="sxs-lookup"><span data-stu-id="6ef1f-127">Permission</span></span> | <span data-ttu-id="6ef1f-128">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="6ef1f-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="6ef1f-129">Program</span><span class="sxs-lookup"><span data-stu-id="6ef1f-129">Application</span></span> | <span data-ttu-id="6ef1f-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="6ef1f-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="6ef1f-131">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="6ef1f-131">Run advanced queries</span></span>
<span data-ttu-id="6ef1f-132">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="6ef1f-132">Delegated (work or school account)</span></span> | <span data-ttu-id="6ef1f-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="6ef1f-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="6ef1f-134">Köra avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="6ef1f-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="6ef1f-135">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="6ef1f-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="6ef1f-136">Användaren måste ha AD-rollen "Visa data"</span><span class="sxs-lookup"><span data-stu-id="6ef1f-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="6ef1f-137">Användaren måste ha åtkomst till enheten, baserat på enhetens gruppinställningar.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="6ef1f-138">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="6ef1f-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="6ef1f-139">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="6ef1f-139">Request headers</span></span>

<span data-ttu-id="6ef1f-140">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="6ef1f-140">Header</span></span> | <span data-ttu-id="6ef1f-141">Värde</span><span class="sxs-lookup"><span data-stu-id="6ef1f-141">Value</span></span>
-|-
<span data-ttu-id="6ef1f-142">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="6ef1f-142">Authorization</span></span> | <span data-ttu-id="6ef1f-143">Bearer {token} **Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="6ef1f-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="6ef1f-144">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="6ef1f-144">Content-Type</span></span> | <span data-ttu-id="6ef1f-145">application/json</span><span class="sxs-lookup"><span data-stu-id="6ef1f-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="6ef1f-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="6ef1f-146">Request body</span></span>

<span data-ttu-id="6ef1f-147">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="6ef1f-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6ef1f-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ef1f-148">Parameter</span></span> | <span data-ttu-id="6ef1f-149">Typ</span><span class="sxs-lookup"><span data-stu-id="6ef1f-149">Type</span></span> | <span data-ttu-id="6ef1f-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6ef1f-150">Description</span></span>
-|-|-
<span data-ttu-id="6ef1f-151">Fråga</span><span class="sxs-lookup"><span data-stu-id="6ef1f-151">Query</span></span> | <span data-ttu-id="6ef1f-152">Text</span><span class="sxs-lookup"><span data-stu-id="6ef1f-152">Text</span></span> | <span data-ttu-id="6ef1f-153">Frågan som ska köras.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-153">The query to run.</span></span> <span data-ttu-id="6ef1f-154">**Obs! obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="6ef1f-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="6ef1f-155">Svar</span><span class="sxs-lookup"><span data-stu-id="6ef1f-155">Response</span></span>

<span data-ttu-id="6ef1f-156">Om det lyckas returnerar den här `200 OK` metoden och _ett QueryResponse-objekt_ i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="6ef1f-157">Svarsobjektet innehåller tre egenskaper på översta nivån:</span><span class="sxs-lookup"><span data-stu-id="6ef1f-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="6ef1f-158">Statistik – en ordlista med frågeprestandastatistik.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="6ef1f-159">Schema – Schemat för svaret, en lista Name-Type par för varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="6ef1f-160">Resultat – En lista över avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="6ef1f-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="6ef1f-161">Exempel</span><span class="sxs-lookup"><span data-stu-id="6ef1f-161">Example</span></span>

<span data-ttu-id="6ef1f-162">I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsobjekt som `Stats` innehåller `Schema` , och `Results` .</span><span class="sxs-lookup"><span data-stu-id="6ef1f-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="6ef1f-163">Fråga</span><span class="sxs-lookup"><span data-stu-id="6ef1f-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="6ef1f-164">Response-objekt</span><span class="sxs-lookup"><span data-stu-id="6ef1f-164">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="6ef1f-165">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6ef1f-165">Related articles</span></span>

- [<span data-ttu-id="6ef1f-166">Komma åt Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="6ef1f-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6ef1f-167">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="6ef1f-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6ef1f-168">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="6ef1f-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6ef1f-169">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6ef1f-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
