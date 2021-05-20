---
title: Uppdatera incident-API
description: Läs om hur du uppdaterar incidenter med Microsoft 365 Defender API
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571787"
---
# <a name="update-incident-api"></a><span data-ttu-id="fc07a-104">Uppdatera incident-API</span><span class="sxs-lookup"><span data-stu-id="fc07a-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fc07a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fc07a-105">**Applies to:**</span></span>

- <span data-ttu-id="fc07a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc07a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc07a-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="fc07a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fc07a-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="fc07a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="fc07a-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="fc07a-109">API description</span></span>

<span data-ttu-id="fc07a-110">Uppdaterar egenskaper för befintlig incident.</span><span class="sxs-lookup"><span data-stu-id="fc07a-110">Updates properties of existing incident.</span></span> <span data-ttu-id="fc07a-111">Uppdatable egenskaper är: ```status``` , , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="fc07a-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="fc07a-112">Kvoter, resursallokering och andra begränsningar</span><span class="sxs-lookup"><span data-stu-id="fc07a-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="fc07a-113">Du kan ringa upp till 50 samtal per minut eller 1500 samtal per timme innan du når begränsningströskeln.</span><span class="sxs-lookup"><span data-stu-id="fc07a-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="fc07a-114">Du kan bara ange `determination` egenskapen om `classification` den är inställd på TruePositive.</span><span class="sxs-lookup"><span data-stu-id="fc07a-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="fc07a-115">Om din begäran är strypt returneras en `429` svarskod.</span><span class="sxs-lookup"><span data-stu-id="fc07a-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="fc07a-116">Svarstexten anger när du kan börja ringa nya samtal.</span><span class="sxs-lookup"><span data-stu-id="fc07a-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="fc07a-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="fc07a-117">Permissions</span></span>

<span data-ttu-id="fc07a-118">En av följande behörigheter krävs för att anropa det här API:et.</span><span class="sxs-lookup"><span data-stu-id="fc07a-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fc07a-119">Mer information om hur du väljer behörigheter finns i Komma [åt Microsoft 365 Defender API:er](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="fc07a-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="fc07a-120">Typ av behörighet</span><span class="sxs-lookup"><span data-stu-id="fc07a-120">Permission type</span></span> | <span data-ttu-id="fc07a-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="fc07a-121">Permission</span></span> | <span data-ttu-id="fc07a-122">Namn på behörighetsvisning</span><span class="sxs-lookup"><span data-stu-id="fc07a-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="fc07a-123">Program</span><span class="sxs-lookup"><span data-stu-id="fc07a-123">Application</span></span> | <span data-ttu-id="fc07a-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fc07a-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="fc07a-125">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="fc07a-125">Read and write all incidents</span></span>
<span data-ttu-id="fc07a-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="fc07a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="fc07a-127">Incident.ReadWrite (på plats)</span><span class="sxs-lookup"><span data-stu-id="fc07a-127">Incident.ReadWrite</span></span> | <span data-ttu-id="fc07a-128">Läsa och skriva incidenter</span><span class="sxs-lookup"><span data-stu-id="fc07a-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="fc07a-129">När du skaffar en token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera incidenten i portalen.</span><span class="sxs-lookup"><span data-stu-id="fc07a-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="fc07a-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="fc07a-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="fc07a-131">Begär rubriker</span><span class="sxs-lookup"><span data-stu-id="fc07a-131">Request headers</span></span>

<span data-ttu-id="fc07a-132">Namn</span><span class="sxs-lookup"><span data-stu-id="fc07a-132">Name</span></span> | <span data-ttu-id="fc07a-133">Typ</span><span class="sxs-lookup"><span data-stu-id="fc07a-133">Type</span></span> | <span data-ttu-id="fc07a-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fc07a-134">Description</span></span>
-|-|-
<span data-ttu-id="fc07a-135">tillstånd</span><span class="sxs-lookup"><span data-stu-id="fc07a-135">Authorization</span></span> | <span data-ttu-id="fc07a-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="fc07a-136">String</span></span> | <span data-ttu-id="fc07a-137">Bärare {token}.</span><span class="sxs-lookup"><span data-stu-id="fc07a-137">Bearer {token}.</span></span> <span data-ttu-id="fc07a-138">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="fc07a-138">**Required**.</span></span>
<span data-ttu-id="fc07a-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="fc07a-139">Content-Type</span></span> | <span data-ttu-id="fc07a-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="fc07a-140">String</span></span> | <span data-ttu-id="fc07a-141">ansökan/json.</span><span class="sxs-lookup"><span data-stu-id="fc07a-141">application/json.</span></span> <span data-ttu-id="fc07a-142">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="fc07a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fc07a-143">Begär brödtext</span><span class="sxs-lookup"><span data-stu-id="fc07a-143">Request body</span></span>

<span data-ttu-id="fc07a-144">Ange värdena för de fält som ska uppdateras i förfrågningstexten.</span><span class="sxs-lookup"><span data-stu-id="fc07a-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="fc07a-145">Befintliga egenskaper som inte ingår i begärandetexten behåller sina värden, såvida de inte måste beräknas om på grund av ändringar i relaterade värden.</span><span class="sxs-lookup"><span data-stu-id="fc07a-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="fc07a-146">För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="fc07a-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="fc07a-147">Egenskap</span><span class="sxs-lookup"><span data-stu-id="fc07a-147">Property</span></span> | <span data-ttu-id="fc07a-148">Typ</span><span class="sxs-lookup"><span data-stu-id="fc07a-148">Type</span></span> | <span data-ttu-id="fc07a-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fc07a-149">Description</span></span>
-|-|-
<span data-ttu-id="fc07a-150">status</span><span class="sxs-lookup"><span data-stu-id="fc07a-150">status</span></span> | <span data-ttu-id="fc07a-151">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="fc07a-151">Enum</span></span> | <span data-ttu-id="fc07a-152">Anger incidentens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="fc07a-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="fc07a-153">Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="fc07a-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="fc07a-154">tilldeladTill</span><span class="sxs-lookup"><span data-stu-id="fc07a-154">assignedTo</span></span> | <span data-ttu-id="fc07a-155">sträng</span><span class="sxs-lookup"><span data-stu-id="fc07a-155">string</span></span> | <span data-ttu-id="fc07a-156">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="fc07a-156">Owner of the incident.</span></span>
<span data-ttu-id="fc07a-157">klassificering</span><span class="sxs-lookup"><span data-stu-id="fc07a-157">classification</span></span> | <span data-ttu-id="fc07a-158">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="fc07a-158">Enum</span></span> | <span data-ttu-id="fc07a-159">Specifikation av incidenten.</span><span class="sxs-lookup"><span data-stu-id="fc07a-159">Specification of the incident.</span></span> <span data-ttu-id="fc07a-160">Möjliga värden är: ```Unknown``` , ```FalsePositive``` ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="fc07a-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="fc07a-161">beslutsamhet</span><span class="sxs-lookup"><span data-stu-id="fc07a-161">determination</span></span> | <span data-ttu-id="fc07a-162">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="fc07a-162">Enum</span></span> | <span data-ttu-id="fc07a-163">Anger bestämningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="fc07a-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="fc07a-164">Möjliga värden är: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="fc07a-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="fc07a-165">Taggar</span><span class="sxs-lookup"><span data-stu-id="fc07a-165">tags</span></span> | <span data-ttu-id="fc07a-166">stränglista</span><span class="sxs-lookup"><span data-stu-id="fc07a-166">string List</span></span> | <span data-ttu-id="fc07a-167">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="fc07a-167">List of Incident tags.</span></span>
<span data-ttu-id="fc07a-168">kommentar</span><span class="sxs-lookup"><span data-stu-id="fc07a-168">comment</span></span> | <span data-ttu-id="fc07a-169">sträng</span><span class="sxs-lookup"><span data-stu-id="fc07a-169">string</span></span> | <span data-ttu-id="fc07a-170">Kommentar som ska läggas till i incidenten.</span><span class="sxs-lookup"><span data-stu-id="fc07a-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="fc07a-171">svar</span><span class="sxs-lookup"><span data-stu-id="fc07a-171">Response</span></span>

<span data-ttu-id="fc07a-172">Om den här metoden lyckas returneras `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="fc07a-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="fc07a-173">Svarstexten innehåller incidententiteten med uppdaterade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="fc07a-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="fc07a-174">Om en incident med det angivna ID:t inte hittades returneras metoden `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="fc07a-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="fc07a-175">Exempel</span><span class="sxs-lookup"><span data-stu-id="fc07a-175">Example</span></span>

<span data-ttu-id="fc07a-176">**begäran**</span><span class="sxs-lookup"><span data-stu-id="fc07a-176">**Request**</span></span>

<span data-ttu-id="fc07a-177">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="fc07a-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="fc07a-178">**svar**</span><span class="sxs-lookup"><span data-stu-id="fc07a-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="fc07a-179">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="fc07a-179">Related articles</span></span>

- [<span data-ttu-id="fc07a-180">Komma åt Microsoft 365 Defender API:erna</span><span class="sxs-lookup"><span data-stu-id="fc07a-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="fc07a-181">Lär dig mer om API-gränser och licensiering</span><span class="sxs-lookup"><span data-stu-id="fc07a-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="fc07a-182">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="fc07a-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="fc07a-183">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="fc07a-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="fc07a-184">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="fc07a-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="fc07a-185">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="fc07a-185">Incidents overview</span></span>](incidents-overview.md)
