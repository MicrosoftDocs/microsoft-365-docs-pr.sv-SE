---
title: Microsoft 365 Api:er för defenderincidenter och incidentresurstypen
description: Lär dig mer om metoderna och egenskaperna för resurstypen Incident i Microsoft 365 Defender
keywords: incident, incidenter, api
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572591"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="6156f-104">Microsoft 365 API för defenderincidenter och incidentresurstypen</span><span class="sxs-lookup"><span data-stu-id="6156f-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6156f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6156f-105">**Applies to:**</span></span>

- <span data-ttu-id="6156f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6156f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6156f-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="6156f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6156f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="6156f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6156f-109">En [incident](incidents-overview.md) är en samling relaterade aviseringar som hjälper till att beskriva en attack.</span><span class="sxs-lookup"><span data-stu-id="6156f-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6156f-110">Händelser från olika entiteter i organisationen aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6156f-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6156f-111">Du kan använda incident-API:et för att programmässigt komma åt organisationens incidenter och relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="6156f-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6156f-112">Kvoter och resursallokering</span><span class="sxs-lookup"><span data-stu-id="6156f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6156f-113">Du kan begära upp till 50 samtal per minut eller 1500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="6156f-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6156f-114">Varje metod har också sina egna kvoter.</span><span class="sxs-lookup"><span data-stu-id="6156f-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6156f-115">Mer information om metodspecifika kvoter finns i respektive artikel för den metod som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="6156f-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6156f-116">En `429` HTTP-svarskod anger att du har nått en kvot, antingen efter antal skickade begäranden eller efter tilldelad körtid.</span><span class="sxs-lookup"><span data-stu-id="6156f-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6156f-117">Svarstexten kommer att inkludera tiden tills kvoten du nådde återställs.</span><span class="sxs-lookup"><span data-stu-id="6156f-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6156f-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6156f-118">Permissions</span></span>

<span data-ttu-id="6156f-119">Incident-API:et kräver olika typer av behörigheter för var och en av dess metoder.</span><span class="sxs-lookup"><span data-stu-id="6156f-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6156f-120">Mer information om nödvändiga behörigheter finns i respektive metods artikel.</span><span class="sxs-lookup"><span data-stu-id="6156f-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6156f-121">metoder</span><span class="sxs-lookup"><span data-stu-id="6156f-121">Methods</span></span>

<span data-ttu-id="6156f-122">Metod</span><span class="sxs-lookup"><span data-stu-id="6156f-122">Method</span></span> | <span data-ttu-id="6156f-123">Returtyp</span><span class="sxs-lookup"><span data-stu-id="6156f-123">Return Type</span></span> | <span data-ttu-id="6156f-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6156f-124">Description</span></span>
-|-|-
[<span data-ttu-id="6156f-125">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="6156f-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6156f-126">[Incidentlista](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="6156f-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6156f-127">Få en lista över incidenter.</span><span class="sxs-lookup"><span data-stu-id="6156f-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6156f-128">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="6156f-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6156f-129">händelse</span><span class="sxs-lookup"><span data-stu-id="6156f-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6156f-130">Uppdatera en specifik incident.</span><span class="sxs-lookup"><span data-stu-id="6156f-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6156f-131">Begär brödtext, svar och exempel</span><span class="sxs-lookup"><span data-stu-id="6156f-131">Request body, response, and examples</span></span>

<span data-ttu-id="6156f-132">Mer information om hur du konstruerar en begäran eller tolkning av ett svar finns i respektive metodartiklar och för praktiska exempel.</span><span class="sxs-lookup"><span data-stu-id="6156f-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6156f-133">Vanliga egenskaper</span><span class="sxs-lookup"><span data-stu-id="6156f-133">Common properties</span></span>

<span data-ttu-id="6156f-134">Egenskap</span><span class="sxs-lookup"><span data-stu-id="6156f-134">Property</span></span> | <span data-ttu-id="6156f-135">Typ</span><span class="sxs-lookup"><span data-stu-id="6156f-135">Type</span></span> | <span data-ttu-id="6156f-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6156f-136">Description</span></span>
-|-|-
<span data-ttu-id="6156f-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="6156f-137">incidentId</span></span> | <span data-ttu-id="6156f-138">lång</span><span class="sxs-lookup"><span data-stu-id="6156f-138">long</span></span> | <span data-ttu-id="6156f-139">Incident unikt ID.</span><span class="sxs-lookup"><span data-stu-id="6156f-139">Incident unique ID.</span></span>
<span data-ttu-id="6156f-140">omdirigeraIncidentId</span><span class="sxs-lookup"><span data-stu-id="6156f-140">redirectIncidentId</span></span> | <span data-ttu-id="6156f-141">nullable lång</span><span class="sxs-lookup"><span data-stu-id="6156f-141">nullable long</span></span> | <span data-ttu-id="6156f-142">Incident-ID:t som den aktuella incidenten kopplades till.</span><span class="sxs-lookup"><span data-stu-id="6156f-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6156f-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="6156f-143">incidentName</span></span> | <span data-ttu-id="6156f-144">sträng</span><span class="sxs-lookup"><span data-stu-id="6156f-144">string</span></span> | <span data-ttu-id="6156f-145">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="6156f-145">The name of the Incident.</span></span>
<span data-ttu-id="6156f-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="6156f-146">createdTime</span></span> | <span data-ttu-id="6156f-147">DatumTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6156f-147">DateTimeOffset</span></span> | <span data-ttu-id="6156f-148">Datum och tid (i UTC) incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="6156f-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6156f-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6156f-149">lastUpdateTime</span></span> | <span data-ttu-id="6156f-150">DatumTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6156f-150">DateTimeOffset</span></span> | <span data-ttu-id="6156f-151">Datum och tid (i UTC) incidenten uppdaterades senast.</span><span class="sxs-lookup"><span data-stu-id="6156f-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6156f-152">tilldeladTill</span><span class="sxs-lookup"><span data-stu-id="6156f-152">assignedTo</span></span> | <span data-ttu-id="6156f-153">sträng</span><span class="sxs-lookup"><span data-stu-id="6156f-153">string</span></span> | <span data-ttu-id="6156f-154">Ägare av incidenten.</span><span class="sxs-lookup"><span data-stu-id="6156f-154">Owner of the Incident.</span></span>
<span data-ttu-id="6156f-155">stränghet</span><span class="sxs-lookup"><span data-stu-id="6156f-155">severity</span></span> | <span data-ttu-id="6156f-156">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6156f-156">Enum</span></span> | <span data-ttu-id="6156f-157">Incidentens allvar.</span><span class="sxs-lookup"><span data-stu-id="6156f-157">Severity of the Incident.</span></span> <span data-ttu-id="6156f-158">Möjliga värden är: ```UnSpecified``` , , , och ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="6156f-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6156f-159">status</span><span class="sxs-lookup"><span data-stu-id="6156f-159">status</span></span> | <span data-ttu-id="6156f-160">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6156f-160">Enum</span></span> | <span data-ttu-id="6156f-161">Anger incidentens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="6156f-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="6156f-162">Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="6156f-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6156f-163">klassificering</span><span class="sxs-lookup"><span data-stu-id="6156f-163">classification</span></span> | <span data-ttu-id="6156f-164">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6156f-164">Enum</span></span> | <span data-ttu-id="6156f-165">Specifikation av incidenten.</span><span class="sxs-lookup"><span data-stu-id="6156f-165">Specification of the incident.</span></span> <span data-ttu-id="6156f-166">Möjliga värden är: ```Unknown``` , ```FalsePositive``` ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="6156f-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6156f-167">beslutsamhet</span><span class="sxs-lookup"><span data-stu-id="6156f-167">determination</span></span> | <span data-ttu-id="6156f-168">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6156f-168">Enum</span></span> | <span data-ttu-id="6156f-169">Anger bestämningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="6156f-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="6156f-170">Möjliga värden är: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="6156f-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6156f-171">Taggar</span><span class="sxs-lookup"><span data-stu-id="6156f-171">tags</span></span> | <span data-ttu-id="6156f-172">stränglista</span><span class="sxs-lookup"><span data-stu-id="6156f-172">string List</span></span> | <span data-ttu-id="6156f-173">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="6156f-173">List of Incident tags.</span></span>
<span data-ttu-id="6156f-174">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6156f-174">comments</span></span> | <span data-ttu-id="6156f-175">Lista över incidentkommentarer</span><span class="sxs-lookup"><span data-stu-id="6156f-175">List of incident comments</span></span> | <span data-ttu-id="6156f-176">Objektet Incidentkommentar innehåller: kommentarsträng, skapad av sträng och createTime-datumtid.</span><span class="sxs-lookup"><span data-stu-id="6156f-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="6156f-177">Varningar</span><span class="sxs-lookup"><span data-stu-id="6156f-177">alerts</span></span> | <span data-ttu-id="6156f-178">Aviseringslista</span><span class="sxs-lookup"><span data-stu-id="6156f-178">Alert List</span></span> | <span data-ttu-id="6156f-179">Lista över relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="6156f-179">List of related alerts.</span></span> <span data-ttu-id="6156f-180">Se exempel på [API-dokumentation för](api-list-incidents.md) listincidenter.</span><span class="sxs-lookup"><span data-stu-id="6156f-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6156f-181">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6156f-181">Related articles</span></span>

- [<span data-ttu-id="6156f-182">Microsoft 365 Översikt över Defender API:er</span><span class="sxs-lookup"><span data-stu-id="6156f-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6156f-183">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="6156f-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6156f-184">API för listincidenter</span><span class="sxs-lookup"><span data-stu-id="6156f-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6156f-185">Uppdatera incident-API</span><span class="sxs-lookup"><span data-stu-id="6156f-185">Update incident API</span></span>](api-update-incidents.md)
