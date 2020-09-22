---
title: Uppdatera incident API
description: Lär dig hur du uppdaterar incidenter med hjälp av Microsoft Threat Protection API
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203646"
---
# <a name="update-incidents-api"></a><span data-ttu-id="4f9f2-104">Uppdatera incident API</span><span class="sxs-lookup"><span data-stu-id="4f9f2-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4f9f2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4f9f2-105">**Applies to:**</span></span>
- <span data-ttu-id="4f9f2-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="4f9f2-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="4f9f2-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4f9f2-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="4f9f2-109">API-Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f9f2-109">API description</span></span>
<span data-ttu-id="4f9f2-110">Uppdaterar egenskaper för befintlig incident.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="4f9f2-111">Uppdaterings bara egenskaper är: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` och ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="4f9f2-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="4f9f2-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="4f9f2-112">Limitations</span></span>
1. <span data-ttu-id="4f9f2-113">Pris begränsningar för detta API är 50 samtal per minut och 1500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="4f9f2-114">Du kan endast ange ```determination``` om klassificeringen är inställd på TruePositive.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="4f9f2-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="4f9f2-115">Permissions</span></span>
<span data-ttu-id="4f9f2-116">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4f9f2-117">Om du vill veta mer, inklusive hur du väljer behörigheter, kan du läsa [gå till Microsoft Threat Protection API: er](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="4f9f2-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="4f9f2-118">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="4f9f2-118">Permission type</span></span> |   <span data-ttu-id="4f9f2-119">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="4f9f2-119">Permission</span></span>  |   <span data-ttu-id="4f9f2-120">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="4f9f2-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4f9f2-121">Program</span><span class="sxs-lookup"><span data-stu-id="4f9f2-121">Application</span></span> |   <span data-ttu-id="4f9f2-122">Incident. ReadWrite. alla</span><span class="sxs-lookup"><span data-stu-id="4f9f2-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="4f9f2-123">"Läs och skriv alla händelser"</span><span class="sxs-lookup"><span data-stu-id="4f9f2-123">'Read and write all incidents'</span></span>
<span data-ttu-id="4f9f2-124">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="4f9f2-124">Delegated (work or school account)</span></span> | <span data-ttu-id="4f9f2-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4f9f2-125">Incident.ReadWrite</span></span> | <span data-ttu-id="4f9f2-126">"Läs-och skriv händelser"</span><span class="sxs-lookup"><span data-stu-id="4f9f2-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="4f9f2-127">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="4f9f2-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4f9f2-128">Användaren måste ha behörighet att uppdatera händelsen i portalen.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="4f9f2-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="4f9f2-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="4f9f2-130">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="4f9f2-130">Request headers</span></span>

<span data-ttu-id="4f9f2-131">Namn</span><span class="sxs-lookup"><span data-stu-id="4f9f2-131">Name</span></span> | <span data-ttu-id="4f9f2-132">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="4f9f2-132">Type</span></span> | <span data-ttu-id="4f9f2-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f9f2-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="4f9f2-134">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="4f9f2-134">Authorization</span></span> | <span data-ttu-id="4f9f2-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="4f9f2-135">String</span></span> | <span data-ttu-id="4f9f2-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-136">Bearer {token}.</span></span> <span data-ttu-id="4f9f2-137">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-137">**Required**.</span></span>
<span data-ttu-id="4f9f2-138">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="4f9f2-138">Content-Type</span></span> | <span data-ttu-id="4f9f2-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="4f9f2-139">String</span></span> | <span data-ttu-id="4f9f2-140">Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-140">application/json.</span></span> <span data-ttu-id="4f9f2-141">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4f9f2-142">Brödtext</span><span class="sxs-lookup"><span data-stu-id="4f9f2-142">Request body</span></span>
<span data-ttu-id="4f9f2-143">Ange värdena för de relevanta fält som ska uppdateras i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="4f9f2-144">Befintliga egenskaper som inte är inkluderade i kravet på brödtext bibehåller sina tidigare värden eller omräknas om till ändringar i andra egenskaps värden.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="4f9f2-145">För bästa prestanda bör du inte ta med befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="4f9f2-146">Egenskap</span><span class="sxs-lookup"><span data-stu-id="4f9f2-146">Property</span></span> | <span data-ttu-id="4f9f2-147">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="4f9f2-147">Type</span></span> | <span data-ttu-id="4f9f2-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f9f2-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="4f9f2-149">status</span><span class="sxs-lookup"><span data-stu-id="4f9f2-149">status</span></span> | <span data-ttu-id="4f9f2-150">Enum</span><span class="sxs-lookup"><span data-stu-id="4f9f2-150">Enum</span></span> | <span data-ttu-id="4f9f2-151">Anger aviseringens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="4f9f2-152">Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="4f9f2-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="4f9f2-153">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="4f9f2-153">assignedTo</span></span> | <span data-ttu-id="4f9f2-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4f9f2-154">string</span></span> | <span data-ttu-id="4f9f2-155">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-155">Owner of the incident.</span></span>
<span data-ttu-id="4f9f2-156">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="4f9f2-156">classification</span></span> | <span data-ttu-id="4f9f2-157">Enum</span><span class="sxs-lookup"><span data-stu-id="4f9f2-157">Enum</span></span> | <span data-ttu-id="4f9f2-158">Specifikation av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-158">Specification of the alert.</span></span> <span data-ttu-id="4f9f2-159">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="4f9f2-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="4f9f2-160">bedömning</span><span class="sxs-lookup"><span data-stu-id="4f9f2-160">determination</span></span> | <span data-ttu-id="4f9f2-161">Enum</span><span class="sxs-lookup"><span data-stu-id="4f9f2-161">Enum</span></span> | <span data-ttu-id="4f9f2-162">Anger hur aviseringen ska visas.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="4f9f2-163">Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="4f9f2-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="4f9f2-164">taggen</span><span class="sxs-lookup"><span data-stu-id="4f9f2-164">tags</span></span> | <span data-ttu-id="4f9f2-165">sträng lista</span><span class="sxs-lookup"><span data-stu-id="4f9f2-165">string List</span></span> | <span data-ttu-id="4f9f2-166">Lista över incident koder.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="4f9f2-167">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="4f9f2-167">Response</span></span>
<span data-ttu-id="4f9f2-168">Om det lyckas returnerar den här metoden 200 OK och incidenten i svars texten med de uppdaterade egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="4f9f2-169">Om det inte finns någon incident med det angivna ID: t hittas inte 404.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4f9f2-170">Exempel</span><span class="sxs-lookup"><span data-stu-id="4f9f2-170">Example</span></span>

<span data-ttu-id="4f9f2-171">**Ställning**</span><span class="sxs-lookup"><span data-stu-id="4f9f2-171">**Request**</span></span>

<span data-ttu-id="4f9f2-172">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="4f9f2-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="4f9f2-173">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="4f9f2-173">Related topic</span></span>
- [<span data-ttu-id="4f9f2-174">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="4f9f2-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="4f9f2-175">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="4f9f2-175">List incidents</span></span>](api-list-incidents.md)
