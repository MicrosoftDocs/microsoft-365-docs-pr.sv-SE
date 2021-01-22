---
title: API för uppdatering av incidenter
description: Lär dig hur du uppdaterar incidenter med Microsoft 365 Defender API
keywords: uppdatering, api, incident
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
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929076"
---
# <a name="update-incidents-api"></a><span data-ttu-id="94c7a-104">API för uppdatering av incidenter</span><span class="sxs-lookup"><span data-stu-id="94c7a-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="94c7a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="94c7a-105">**Applies to:**</span></span>

- <span data-ttu-id="94c7a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94c7a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94c7a-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="94c7a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="94c7a-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="94c7a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="94c7a-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="94c7a-109">API description</span></span>

<span data-ttu-id="94c7a-110">Uppdateringsegenskaper för befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="94c7a-110">Updates properties of existing incident.</span></span> <span data-ttu-id="94c7a-111">Egenskaper som kan uppdateras är: ```status``` , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="94c7a-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="94c7a-112">Kvoter, resurstilldelning och andra villkor</span><span class="sxs-lookup"><span data-stu-id="94c7a-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="94c7a-113">Du kan ringa upp till 50 samtal per minut eller 1 500 samtal per timme innan du kommer upp till tröskelvärdet för begränsning.</span><span class="sxs-lookup"><span data-stu-id="94c7a-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="94c7a-114">Du kan bara ange `determination` egenskapen om den är inställd på `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="94c7a-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="94c7a-115">Om din begäran begränsas returneras en `429` svarskod.</span><span class="sxs-lookup"><span data-stu-id="94c7a-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="94c7a-116">Svarstexten anger när du kan börja ringa nya samtal.</span><span class="sxs-lookup"><span data-stu-id="94c7a-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="94c7a-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="94c7a-117">Permissions</span></span>

<span data-ttu-id="94c7a-118">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="94c7a-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94c7a-119">Mer information, inklusive hur du väljer behörigheter, finns i Access API:er för [Microsoft 365 Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="94c7a-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="94c7a-120">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="94c7a-120">Permission type</span></span> | <span data-ttu-id="94c7a-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="94c7a-121">Permission</span></span> | <span data-ttu-id="94c7a-122">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="94c7a-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="94c7a-123">Program</span><span class="sxs-lookup"><span data-stu-id="94c7a-123">Application</span></span> | <span data-ttu-id="94c7a-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="94c7a-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="94c7a-125">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="94c7a-125">Read and write all incidents</span></span>
<span data-ttu-id="94c7a-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="94c7a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="94c7a-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="94c7a-127">Incident.ReadWrite</span></span> | <span data-ttu-id="94c7a-128">Läs- och skrivincidenter</span><span class="sxs-lookup"><span data-stu-id="94c7a-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="94c7a-129">När du skaffar en token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera incidenten i portalen.</span><span class="sxs-lookup"><span data-stu-id="94c7a-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="94c7a-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="94c7a-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="94c7a-131">Begär sidhuvuden</span><span class="sxs-lookup"><span data-stu-id="94c7a-131">Request headers</span></span>

<span data-ttu-id="94c7a-132">Namn</span><span class="sxs-lookup"><span data-stu-id="94c7a-132">Name</span></span> | <span data-ttu-id="94c7a-133">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="94c7a-133">Type</span></span> | <span data-ttu-id="94c7a-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="94c7a-134">Description</span></span>
-|-|-
<span data-ttu-id="94c7a-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="94c7a-135">Authorization</span></span> | <span data-ttu-id="94c7a-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="94c7a-136">String</span></span> | <span data-ttu-id="94c7a-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="94c7a-137">Bearer {token}.</span></span> <span data-ttu-id="94c7a-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="94c7a-138">**Required**.</span></span>
<span data-ttu-id="94c7a-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="94c7a-139">Content-Type</span></span> | <span data-ttu-id="94c7a-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="94c7a-140">String</span></span> | <span data-ttu-id="94c7a-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="94c7a-141">application/json.</span></span> <span data-ttu-id="94c7a-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="94c7a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="94c7a-143">Begärandetext</span><span class="sxs-lookup"><span data-stu-id="94c7a-143">Request body</span></span>

<span data-ttu-id="94c7a-144">Ange värden för fälten som ska uppdateras i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="94c7a-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="94c7a-145">Befintliga egenskaper som inte ingår i begärans brödtext behåller sina värden, såvida de inte behöver beräknas om på grund av ändringar av relaterade värden.</span><span class="sxs-lookup"><span data-stu-id="94c7a-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="94c7a-146">För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="94c7a-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="94c7a-147">Egenskap</span><span class="sxs-lookup"><span data-stu-id="94c7a-147">Property</span></span> | <span data-ttu-id="94c7a-148">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="94c7a-148">Type</span></span> | <span data-ttu-id="94c7a-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="94c7a-149">Description</span></span>
-|-|-
<span data-ttu-id="94c7a-150">status</span><span class="sxs-lookup"><span data-stu-id="94c7a-150">status</span></span> | <span data-ttu-id="94c7a-151">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="94c7a-151">Enum</span></span> | <span data-ttu-id="94c7a-152">Anger aktuell status för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="94c7a-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="94c7a-153">Möjliga värden är: ```Active``` ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="94c7a-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="94c7a-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="94c7a-154">assignedTo</span></span> | <span data-ttu-id="94c7a-155">sträng</span><span class="sxs-lookup"><span data-stu-id="94c7a-155">string</span></span> | <span data-ttu-id="94c7a-156">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="94c7a-156">Owner of the incident.</span></span>
<span data-ttu-id="94c7a-157">klassificering</span><span class="sxs-lookup"><span data-stu-id="94c7a-157">classification</span></span> | <span data-ttu-id="94c7a-158">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="94c7a-158">Enum</span></span> | <span data-ttu-id="94c7a-159">Specifikation för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="94c7a-159">Specification of the alert.</span></span> <span data-ttu-id="94c7a-160">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="94c7a-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="94c7a-161">determination</span><span class="sxs-lookup"><span data-stu-id="94c7a-161">determination</span></span> | <span data-ttu-id="94c7a-162">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="94c7a-162">Enum</span></span> | <span data-ttu-id="94c7a-163">Anger aviseringens avgörande.</span><span class="sxs-lookup"><span data-stu-id="94c7a-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="94c7a-164">Möjliga värden är: ```NotAvailable``` , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="94c7a-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="94c7a-165">taggar</span><span class="sxs-lookup"><span data-stu-id="94c7a-165">tags</span></span> | <span data-ttu-id="94c7a-166">stränglista</span><span class="sxs-lookup"><span data-stu-id="94c7a-166">string List</span></span> | <span data-ttu-id="94c7a-167">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="94c7a-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="94c7a-168">Svar</span><span class="sxs-lookup"><span data-stu-id="94c7a-168">Response</span></span>

<span data-ttu-id="94c7a-169">Om det lyckas returnerar den här `200 OK` metoden.</span><span class="sxs-lookup"><span data-stu-id="94c7a-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="94c7a-170">Svarstexten innehåller incidententitet med uppdaterade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="94c7a-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="94c7a-171">Om en incident med det angivna ID:t inte hittas returneras `404 Not Found` metoden.</span><span class="sxs-lookup"><span data-stu-id="94c7a-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="94c7a-172">Exempel</span><span class="sxs-lookup"><span data-stu-id="94c7a-172">Example</span></span>

<span data-ttu-id="94c7a-173">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="94c7a-173">**Request**</span></span>

<span data-ttu-id="94c7a-174">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="94c7a-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="94c7a-175">**Svar**</span><span class="sxs-lookup"><span data-stu-id="94c7a-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="94c7a-176">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="94c7a-176">Related articles</span></span>

- [<span data-ttu-id="94c7a-177">Få åtkomst till API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94c7a-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="94c7a-178">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="94c7a-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="94c7a-179">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="94c7a-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="94c7a-180">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="94c7a-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="94c7a-181">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="94c7a-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="94c7a-182">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="94c7a-182">Incidents overview</span></span>](incidents-overview.md)
