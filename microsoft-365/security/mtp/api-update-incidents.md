---
title: Uppdatera incident API
description: Lär dig hur du uppdaterar incidenter med hjälp av Microsoft 365 Defender API
keywords: uppdatering, API, incident
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719410"
---
# <a name="update-incidents-api"></a><span data-ttu-id="84253-104">Uppdatera incident API</span><span class="sxs-lookup"><span data-stu-id="84253-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="84253-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="84253-105">**Applies to:**</span></span>

- <span data-ttu-id="84253-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84253-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84253-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="84253-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="84253-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="84253-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="84253-109">API-Beskrivning</span><span class="sxs-lookup"><span data-stu-id="84253-109">API description</span></span>

<span data-ttu-id="84253-110">Uppdaterar egenskaper för befintlig incident.</span><span class="sxs-lookup"><span data-stu-id="84253-110">Updates properties of existing incident.</span></span> <span data-ttu-id="84253-111">Uppdaterings bara egenskaper är: ```status``` , ```determination``` ,, ```classification``` ```assignedTo``` och ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="84253-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="84253-112">Kvoter, resursallokering och andra villkor</span><span class="sxs-lookup"><span data-stu-id="84253-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="84253-113">Du kan ringa upp till 50 samtal per minut eller 1500 samtal per timme innan du klickar på tröskelvärdet för begränsning av bandbredd.</span><span class="sxs-lookup"><span data-stu-id="84253-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="84253-114">Du kan endast ställa in `determination` egenskapen om `classification` är inställd på TruePositive.</span><span class="sxs-lookup"><span data-stu-id="84253-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="84253-115">Om din begäran är begränsad returneras en `429` svarskod.</span><span class="sxs-lookup"><span data-stu-id="84253-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="84253-116">I svars texten visas tiden då du kan börja ringa nya samtal.</span><span class="sxs-lookup"><span data-stu-id="84253-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="84253-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="84253-117">Permissions</span></span>

<span data-ttu-id="84253-118">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="84253-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="84253-119">Mer information om hur du väljer behörigheter finns i avsnittet [om Microsoft 365 Defender API: er](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="84253-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="84253-120">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="84253-120">Permission type</span></span> | <span data-ttu-id="84253-121">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="84253-121">Permission</span></span> | <span data-ttu-id="84253-122">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="84253-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="84253-123">Program</span><span class="sxs-lookup"><span data-stu-id="84253-123">Application</span></span> | <span data-ttu-id="84253-124">Incident. ReadWrite. alla</span><span class="sxs-lookup"><span data-stu-id="84253-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="84253-125">Läsa och skriva alla händelser</span><span class="sxs-lookup"><span data-stu-id="84253-125">Read and write all incidents</span></span>
<span data-ttu-id="84253-126">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="84253-126">Delegated (work or school account)</span></span> | <span data-ttu-id="84253-127">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="84253-127">Incident.ReadWrite</span></span> | <span data-ttu-id="84253-128">Läs-och skriv händelser</span><span class="sxs-lookup"><span data-stu-id="84253-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="84253-129">När du erhåller ett token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera händelsen i portalen.</span><span class="sxs-lookup"><span data-stu-id="84253-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="84253-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="84253-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="84253-131">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="84253-131">Request headers</span></span>

<span data-ttu-id="84253-132">Namn</span><span class="sxs-lookup"><span data-stu-id="84253-132">Name</span></span> | <span data-ttu-id="84253-133">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="84253-133">Type</span></span> | <span data-ttu-id="84253-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="84253-134">Description</span></span>
-|-|-
<span data-ttu-id="84253-135">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="84253-135">Authorization</span></span> | <span data-ttu-id="84253-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="84253-136">String</span></span> | <span data-ttu-id="84253-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="84253-137">Bearer {token}.</span></span> <span data-ttu-id="84253-138">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="84253-138">**Required**.</span></span>
<span data-ttu-id="84253-139">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="84253-139">Content-Type</span></span> | <span data-ttu-id="84253-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="84253-140">String</span></span> | <span data-ttu-id="84253-141">Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="84253-141">application/json.</span></span> <span data-ttu-id="84253-142">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="84253-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="84253-143">Brödtext</span><span class="sxs-lookup"><span data-stu-id="84253-143">Request body</span></span>

<span data-ttu-id="84253-144">I begärans brödtext anger du värden för de fält som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="84253-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="84253-145">Befintliga egenskaper som inte är inkluderade i kravet på brödtext bibehåller sina värden, såvida de inte måste beräknas på nytt på grund av ändringar i relaterade värden.</span><span class="sxs-lookup"><span data-stu-id="84253-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="84253-146">För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="84253-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="84253-147">Egenskap</span><span class="sxs-lookup"><span data-stu-id="84253-147">Property</span></span> | <span data-ttu-id="84253-148">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="84253-148">Type</span></span> | <span data-ttu-id="84253-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="84253-149">Description</span></span>
-|-|-
<span data-ttu-id="84253-150">status</span><span class="sxs-lookup"><span data-stu-id="84253-150">status</span></span> | <span data-ttu-id="84253-151">Enum</span><span class="sxs-lookup"><span data-stu-id="84253-151">Enum</span></span> | <span data-ttu-id="84253-152">Anger aviseringens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="84253-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="84253-153">Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="84253-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="84253-154">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="84253-154">assignedTo</span></span> | <span data-ttu-id="84253-155">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="84253-155">string</span></span> | <span data-ttu-id="84253-156">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="84253-156">Owner of the incident.</span></span>
<span data-ttu-id="84253-157">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="84253-157">classification</span></span> | <span data-ttu-id="84253-158">Enum</span><span class="sxs-lookup"><span data-stu-id="84253-158">Enum</span></span> | <span data-ttu-id="84253-159">Specifikation av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="84253-159">Specification of the alert.</span></span> <span data-ttu-id="84253-160">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="84253-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="84253-161">bedömning</span><span class="sxs-lookup"><span data-stu-id="84253-161">determination</span></span> | <span data-ttu-id="84253-162">Enum</span><span class="sxs-lookup"><span data-stu-id="84253-162">Enum</span></span> | <span data-ttu-id="84253-163">Anger hur aviseringen ska visas.</span><span class="sxs-lookup"><span data-stu-id="84253-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="84253-164">Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="84253-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="84253-165">taggen</span><span class="sxs-lookup"><span data-stu-id="84253-165">tags</span></span> | <span data-ttu-id="84253-166">sträng lista</span><span class="sxs-lookup"><span data-stu-id="84253-166">string List</span></span> | <span data-ttu-id="84253-167">Lista över incident koder.</span><span class="sxs-lookup"><span data-stu-id="84253-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="84253-168">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="84253-168">Response</span></span>

<span data-ttu-id="84253-169">Om det lyckas returneras den här metoden `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="84253-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="84253-170">Svars texten innehåller incident-enheten med uppdaterade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="84253-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="84253-171">Om en incident med angivet ID inte hittas returneras metoden `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="84253-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="84253-172">Exempel</span><span class="sxs-lookup"><span data-stu-id="84253-172">Example</span></span>

<span data-ttu-id="84253-173">**Ställning**</span><span class="sxs-lookup"><span data-stu-id="84253-173">**Request**</span></span>

<span data-ttu-id="84253-174">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="84253-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="84253-175">**Interimssvar**</span><span class="sxs-lookup"><span data-stu-id="84253-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="84253-176">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="84253-176">Related articles</span></span>

- [<span data-ttu-id="84253-177">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84253-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="84253-178">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="84253-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="84253-179">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="84253-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="84253-180">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="84253-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="84253-181">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="84253-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="84253-182">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="84253-182">Incidents overview</span></span>](incidents-overview.md)
