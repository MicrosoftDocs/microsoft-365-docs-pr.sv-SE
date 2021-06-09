---
title: Microsoft 365 Api:er för Defender-incidenter och resurstypen för incidenter
description: Läs mer om metoderna och egenskaperna för resurstypen Incidenter i Microsoft 365 Defender
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
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730936"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="7befc-104">Microsoft 365 Defender-incident-API:t och resurstypen för incidenter</span><span class="sxs-lookup"><span data-stu-id="7befc-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7befc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7befc-105">**Applies to:**</span></span>

- [<span data-ttu-id="7befc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7befc-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="7befc-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="7befc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7befc-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="7befc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7befc-109">En [incident](incidents-overview.md) är en samling relaterade aviseringar som beskriver en attack.</span><span class="sxs-lookup"><span data-stu-id="7befc-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="7befc-110">Händelser från olika enheter i organisationen aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7befc-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="7befc-111">Du kan använda incident-API:t för att programmässigt få åtkomst till organisationens incidenter och relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="7befc-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="7befc-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="7befc-112">Quotas and resource allocation</span></span>

<span data-ttu-id="7befc-113">Du kan begära upp till 50 samtal per minut eller 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="7befc-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="7befc-114">Varje metod har också egna kvoter.</span><span class="sxs-lookup"><span data-stu-id="7befc-114">Each method also has its own quotas.</span></span> <span data-ttu-id="7befc-115">Mer information om metodspecifika kvoter finns i respektive artikel för den metod du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7befc-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="7befc-116">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid.</span><span class="sxs-lookup"><span data-stu-id="7befc-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="7befc-117">Svarstexten tar med tiden tills kvoten du har nått återställs.</span><span class="sxs-lookup"><span data-stu-id="7befc-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="7befc-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="7befc-118">Permissions</span></span>

<span data-ttu-id="7befc-119">För incident-API:t krävs olika typer av behörigheter för var och en av dess metoder.</span><span class="sxs-lookup"><span data-stu-id="7befc-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="7befc-120">Mer information om obligatoriska behörigheter finns i respektive metods artikel.</span><span class="sxs-lookup"><span data-stu-id="7befc-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="7befc-121">Metoder</span><span class="sxs-lookup"><span data-stu-id="7befc-121">Methods</span></span>

<span data-ttu-id="7befc-122">Metod</span><span class="sxs-lookup"><span data-stu-id="7befc-122">Method</span></span> | <span data-ttu-id="7befc-123">Returtyp</span><span class="sxs-lookup"><span data-stu-id="7befc-123">Return Type</span></span> | <span data-ttu-id="7befc-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7befc-124">Description</span></span>
-|-|-
[<span data-ttu-id="7befc-125">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="7befc-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="7befc-126">[Incidentlista](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="7befc-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="7befc-127">Få en lista över alla incidenter.</span><span class="sxs-lookup"><span data-stu-id="7befc-127">Get a list of incidents.</span></span>
[<span data-ttu-id="7befc-128">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="7befc-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="7befc-129">Incident</span><span class="sxs-lookup"><span data-stu-id="7befc-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="7befc-130">Uppdatera en specifik händelse.</span><span class="sxs-lookup"><span data-stu-id="7befc-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="7befc-131">Begärans brödtext, svar och exempel</span><span class="sxs-lookup"><span data-stu-id="7befc-131">Request body, response, and examples</span></span>

<span data-ttu-id="7befc-132">Mer information om hur du skapar en begäran eller parsar ett svar samt praktiska exempel finns i respektive metodartiklar.</span><span class="sxs-lookup"><span data-stu-id="7befc-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="7befc-133">Gemensamma egenskaper</span><span class="sxs-lookup"><span data-stu-id="7befc-133">Common properties</span></span>

<span data-ttu-id="7befc-134">Egenskap</span><span class="sxs-lookup"><span data-stu-id="7befc-134">Property</span></span> | <span data-ttu-id="7befc-135">Typ</span><span class="sxs-lookup"><span data-stu-id="7befc-135">Type</span></span> | <span data-ttu-id="7befc-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7befc-136">Description</span></span>
-|-|-
<span data-ttu-id="7befc-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="7befc-137">incidentId</span></span> | <span data-ttu-id="7befc-138">long</span><span class="sxs-lookup"><span data-stu-id="7befc-138">long</span></span> | <span data-ttu-id="7befc-139">Unikt ID för incidenter.</span><span class="sxs-lookup"><span data-stu-id="7befc-139">Incident unique ID.</span></span>
<span data-ttu-id="7befc-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="7befc-140">redirectIncidentId</span></span> | <span data-ttu-id="7befc-141">nullbar long</span><span class="sxs-lookup"><span data-stu-id="7befc-141">nullable long</span></span> | <span data-ttu-id="7befc-142">Det incident-ID som den aktuella incidenten kopplades till.</span><span class="sxs-lookup"><span data-stu-id="7befc-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="7befc-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="7befc-143">incidentName</span></span> | <span data-ttu-id="7befc-144">sträng</span><span class="sxs-lookup"><span data-stu-id="7befc-144">string</span></span> | <span data-ttu-id="7befc-145">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="7befc-145">The name of the Incident.</span></span>
<span data-ttu-id="7befc-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="7befc-146">createdTime</span></span> | <span data-ttu-id="7befc-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7befc-147">DateTimeOffset</span></span> | <span data-ttu-id="7befc-148">Datum och tid (i UTC) som incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="7befc-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="7befc-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="7befc-149">lastUpdateTime</span></span> | <span data-ttu-id="7befc-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7befc-150">DateTimeOffset</span></span> | <span data-ttu-id="7befc-151">Datum och tid (i UTC) som incidenten uppdaterades senast.</span><span class="sxs-lookup"><span data-stu-id="7befc-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="7befc-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="7befc-152">assignedTo</span></span> | <span data-ttu-id="7befc-153">sträng</span><span class="sxs-lookup"><span data-stu-id="7befc-153">string</span></span> | <span data-ttu-id="7befc-154">Ägaren till händelsen.</span><span class="sxs-lookup"><span data-stu-id="7befc-154">Owner of the Incident.</span></span>
<span data-ttu-id="7befc-155">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="7befc-155">severity</span></span> | <span data-ttu-id="7befc-156">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="7befc-156">Enum</span></span> | <span data-ttu-id="7befc-157">Incidentens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="7befc-157">Severity of the Incident.</span></span> <span data-ttu-id="7befc-158">Möjliga värden är: ```UnSpecified``` , , , och ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="7befc-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="7befc-159">status</span><span class="sxs-lookup"><span data-stu-id="7befc-159">status</span></span> | <span data-ttu-id="7befc-160">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="7befc-160">Enum</span></span> | <span data-ttu-id="7befc-161">Anger incidentens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="7befc-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="7befc-162">Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="7befc-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="7befc-163">klassificering</span><span class="sxs-lookup"><span data-stu-id="7befc-163">classification</span></span> | <span data-ttu-id="7befc-164">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="7befc-164">Enum</span></span> | <span data-ttu-id="7befc-165">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="7befc-165">Specification of the incident.</span></span> <span data-ttu-id="7befc-166">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="7befc-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="7befc-167">determination</span><span class="sxs-lookup"><span data-stu-id="7befc-167">determination</span></span> | <span data-ttu-id="7befc-168">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="7befc-168">Enum</span></span> | <span data-ttu-id="7befc-169">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="7befc-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="7befc-170">Möjliga värden är: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="7befc-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="7befc-171">taggar</span><span class="sxs-lookup"><span data-stu-id="7befc-171">tags</span></span> | <span data-ttu-id="7befc-172">stränglista</span><span class="sxs-lookup"><span data-stu-id="7befc-172">string List</span></span> | <span data-ttu-id="7befc-173">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="7befc-173">List of Incident tags.</span></span>
<span data-ttu-id="7befc-174">kommentarer</span><span class="sxs-lookup"><span data-stu-id="7befc-174">comments</span></span> | <span data-ttu-id="7befc-175">Lista över incidentkommentarer</span><span class="sxs-lookup"><span data-stu-id="7befc-175">List of incident comments</span></span> | <span data-ttu-id="7befc-176">Incidentkommentarsobjekt innehåller: kommentarssträng, createdBy-sträng och createTime-datumtid.</span><span class="sxs-lookup"><span data-stu-id="7befc-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="7befc-177">aviseringar</span><span class="sxs-lookup"><span data-stu-id="7befc-177">alerts</span></span> | <span data-ttu-id="7befc-178">Aviseringslista</span><span class="sxs-lookup"><span data-stu-id="7befc-178">Alert List</span></span> | <span data-ttu-id="7befc-179">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="7befc-179">List of related alerts.</span></span> <span data-ttu-id="7befc-180">Se exempel i [dokumentationen för API för listincidenter.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="7befc-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7befc-181">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7befc-181">Related articles</span></span>

- [<span data-ttu-id="7befc-182">Microsoft 365 Översikt över Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="7befc-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7befc-183">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="7befc-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7befc-184">API för listincidenter</span><span class="sxs-lookup"><span data-stu-id="7befc-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="7befc-185">Api för uppdatering av incident</span><span class="sxs-lookup"><span data-stu-id="7befc-185">Update incident API</span></span>](api-update-incidents.md)
