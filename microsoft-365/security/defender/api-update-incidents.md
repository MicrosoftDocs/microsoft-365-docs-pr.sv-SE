---
title: Api för uppdatering av incident
description: Lär dig hur du uppdaterar incidenter med hjälp Microsoft 365 Defender API
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
ms.openlocfilehash: 60f1209331862eb21d3b1949265f0873dcf2e5a7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287825"
---
# <a name="update-incidents-api"></a><span data-ttu-id="71a5d-104">API för uppdatering av incidenter</span><span class="sxs-lookup"><span data-stu-id="71a5d-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71a5d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="71a5d-105">**Applies to:**</span></span>

- [<span data-ttu-id="71a5d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71a5d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="71a5d-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="71a5d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="71a5d-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="71a5d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="71a5d-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="71a5d-109">API description</span></span>

<span data-ttu-id="71a5d-110">Uppdaterar egenskaper för befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="71a5d-110">Updates properties of existing incident.</span></span> <span data-ttu-id="71a5d-111">Egenskaper som kan uppdateras är: ```status``` , , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="71a5d-112">Kvoter, resurstilldelning och andra villkor</span><span class="sxs-lookup"><span data-stu-id="71a5d-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="71a5d-113">Du kan ringa upp till 50 samtal per minut eller 1 500 samtal per timme innan du kommer till begränsningströskeln.</span><span class="sxs-lookup"><span data-stu-id="71a5d-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="71a5d-114">Du kan bara ange `determination` egenskapen om är Inställd på `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="71a5d-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="71a5d-115">Om din begäran begränsas returneras en `429` svarskod.</span><span class="sxs-lookup"><span data-stu-id="71a5d-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="71a5d-116">Svarstexten anger när du kan börja ringa nya samtal.</span><span class="sxs-lookup"><span data-stu-id="71a5d-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="71a5d-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="71a5d-117">Permissions</span></span>

<span data-ttu-id="71a5d-118">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="71a5d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="71a5d-119">Mer information, inklusive hur du väljer behörigheter, finns i [Komma åt Microsoft 365 Defender-API:er.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="71a5d-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="71a5d-120">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="71a5d-120">Permission type</span></span> | <span data-ttu-id="71a5d-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="71a5d-121">Permission</span></span> | <span data-ttu-id="71a5d-122">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="71a5d-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="71a5d-123">Program</span><span class="sxs-lookup"><span data-stu-id="71a5d-123">Application</span></span> | <span data-ttu-id="71a5d-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="71a5d-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="71a5d-125">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="71a5d-125">Read and write all incidents</span></span>
<span data-ttu-id="71a5d-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="71a5d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="71a5d-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="71a5d-127">Incident.ReadWrite</span></span> | <span data-ttu-id="71a5d-128">Läs- och skrivincidenter</span><span class="sxs-lookup"><span data-stu-id="71a5d-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="71a5d-129">När användaren skaffar en token med användarautentiseringsuppgifter måste han eller hon ha behörighet att uppdatera incidenten i portalen.</span><span class="sxs-lookup"><span data-stu-id="71a5d-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="71a5d-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="71a5d-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="71a5d-131">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="71a5d-131">Request headers</span></span>

<span data-ttu-id="71a5d-132">Namn</span><span class="sxs-lookup"><span data-stu-id="71a5d-132">Name</span></span> | <span data-ttu-id="71a5d-133">Typ</span><span class="sxs-lookup"><span data-stu-id="71a5d-133">Type</span></span> | <span data-ttu-id="71a5d-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="71a5d-134">Description</span></span>
-|-|-
<span data-ttu-id="71a5d-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="71a5d-135">Authorization</span></span> | <span data-ttu-id="71a5d-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a5d-136">String</span></span> | <span data-ttu-id="71a5d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="71a5d-137">Bearer {token}.</span></span> <span data-ttu-id="71a5d-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="71a5d-138">**Required**.</span></span>
<span data-ttu-id="71a5d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="71a5d-139">Content-Type</span></span> | <span data-ttu-id="71a5d-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a5d-140">String</span></span> | <span data-ttu-id="71a5d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="71a5d-141">application/json.</span></span> <span data-ttu-id="71a5d-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="71a5d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="71a5d-143">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="71a5d-143">Request body</span></span>

<span data-ttu-id="71a5d-144">Ange värden för fälten som ska uppdateras i brödtexten för begäran.</span><span class="sxs-lookup"><span data-stu-id="71a5d-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="71a5d-145">Befintliga egenskaper som inte finns i begärans brödtext bibehåller sina värden, såvida de inte behöver beräknas om på grund av ändringar av relaterade värden.</span><span class="sxs-lookup"><span data-stu-id="71a5d-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="71a5d-146">För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="71a5d-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="71a5d-147">Egenskap</span><span class="sxs-lookup"><span data-stu-id="71a5d-147">Property</span></span> | <span data-ttu-id="71a5d-148">Typ</span><span class="sxs-lookup"><span data-stu-id="71a5d-148">Type</span></span> | <span data-ttu-id="71a5d-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="71a5d-149">Description</span></span>
-|-|-
<span data-ttu-id="71a5d-150">status</span><span class="sxs-lookup"><span data-stu-id="71a5d-150">status</span></span> | <span data-ttu-id="71a5d-151">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="71a5d-151">Enum</span></span> | <span data-ttu-id="71a5d-152">Anger incidentens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="71a5d-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="71a5d-153">Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="71a5d-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="71a5d-154">assignedTo</span></span> | <span data-ttu-id="71a5d-155">sträng</span><span class="sxs-lookup"><span data-stu-id="71a5d-155">string</span></span> | <span data-ttu-id="71a5d-156">Ägaren till händelsen.</span><span class="sxs-lookup"><span data-stu-id="71a5d-156">Owner of the incident.</span></span>
<span data-ttu-id="71a5d-157">klassificering</span><span class="sxs-lookup"><span data-stu-id="71a5d-157">classification</span></span> | <span data-ttu-id="71a5d-158">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="71a5d-158">Enum</span></span> | <span data-ttu-id="71a5d-159">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="71a5d-159">Specification of the incident.</span></span> <span data-ttu-id="71a5d-160">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="71a5d-161">determination</span><span class="sxs-lookup"><span data-stu-id="71a5d-161">determination</span></span> | <span data-ttu-id="71a5d-162">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="71a5d-162">Enum</span></span> | <span data-ttu-id="71a5d-163">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="71a5d-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="71a5d-164">Möjliga värden är: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="71a5d-165">taggar</span><span class="sxs-lookup"><span data-stu-id="71a5d-165">tags</span></span> | <span data-ttu-id="71a5d-166">stränglista</span><span class="sxs-lookup"><span data-stu-id="71a5d-166">string List</span></span> | <span data-ttu-id="71a5d-167">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="71a5d-167">List of Incident tags.</span></span>
<span data-ttu-id="71a5d-168">kommentar</span><span class="sxs-lookup"><span data-stu-id="71a5d-168">comment</span></span> | <span data-ttu-id="71a5d-169">sträng</span><span class="sxs-lookup"><span data-stu-id="71a5d-169">string</span></span> | <span data-ttu-id="71a5d-170">Kommentar som ska läggas till i incidenten.</span><span class="sxs-lookup"><span data-stu-id="71a5d-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="71a5d-171">Svar</span><span class="sxs-lookup"><span data-stu-id="71a5d-171">Response</span></span>

<span data-ttu-id="71a5d-172">Om det lyckas returnerar den här metoden `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="71a5d-173">Svarstexten innehåller incidententitet med uppdaterade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="71a5d-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="71a5d-174">Om en incident med det angivna ID:t inte hittas returnerar metoden `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="71a5d-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="71a5d-175">Exempel</span><span class="sxs-lookup"><span data-stu-id="71a5d-175">Example</span></span>

<span data-ttu-id="71a5d-176">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="71a5d-176">**Request**</span></span>

<span data-ttu-id="71a5d-177">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="71a5d-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="71a5d-178">**Svar**</span><span class="sxs-lookup"><span data-stu-id="71a5d-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="71a5d-179">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="71a5d-179">Related articles</span></span>

- [<span data-ttu-id="71a5d-180">Få åtkomst Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="71a5d-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="71a5d-181">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="71a5d-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="71a5d-182">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="71a5d-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="71a5d-183">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="71a5d-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="71a5d-184">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="71a5d-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="71a5d-185">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="71a5d-185">Incidents overview</span></span>](incidents-overview.md)
