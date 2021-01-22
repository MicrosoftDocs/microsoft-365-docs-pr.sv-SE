---
title: API:er för Microsoft 365 Defender-incidenter och resurstypen för incidenter
description: Läs mer om metoder och egenskaper för resurstypen Incident i Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928360"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="e4289-104">API för Microsoft 365 Defender-incidenter och resurstypen för incidenter</span><span class="sxs-lookup"><span data-stu-id="e4289-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e4289-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e4289-105">**Applies to:**</span></span>

- <span data-ttu-id="e4289-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4289-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4289-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="e4289-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e4289-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="e4289-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e4289-109">En [incident](incidents-overview.md) är en samling relaterade aviseringar som hjälper till att beskriva en attack.</span><span class="sxs-lookup"><span data-stu-id="e4289-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="e4289-110">Händelser från olika enheter i organisationen aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e4289-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="e4289-111">Du kan använda API för incidenter för att programmässigt få åtkomst till organisationens incidenter och relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="e4289-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="e4289-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="e4289-112">Quotas and resource allocation</span></span>

<span data-ttu-id="e4289-113">Du kan begära upp till 50 samtal per minut eller 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="e4289-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="e4289-114">Varje metod har också egna kvoter.</span><span class="sxs-lookup"><span data-stu-id="e4289-114">Each method also has its own quotas.</span></span> <span data-ttu-id="e4289-115">Mer information om metodspecifika kvoter finns i respektive artikel för den metod du vill använda.</span><span class="sxs-lookup"><span data-stu-id="e4289-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="e4289-116">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas eller `429` med tilldelad körningstid.</span><span class="sxs-lookup"><span data-stu-id="e4289-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="e4289-117">Svarstexten innehåller tiden tills kvoten du har nått återställs.</span><span class="sxs-lookup"><span data-stu-id="e4289-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="e4289-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="e4289-118">Permissions</span></span>

<span data-ttu-id="e4289-119">Api för incidenter kräver olika typer av behörigheter för var och en av dess metoder.</span><span class="sxs-lookup"><span data-stu-id="e4289-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="e4289-120">Mer information om behörigheter som krävs finns i respektive metods artikel.</span><span class="sxs-lookup"><span data-stu-id="e4289-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="e4289-121">Metoder</span><span class="sxs-lookup"><span data-stu-id="e4289-121">Methods</span></span>

<span data-ttu-id="e4289-122">Metod</span><span class="sxs-lookup"><span data-stu-id="e4289-122">Method</span></span> | <span data-ttu-id="e4289-123">Returtyp</span><span class="sxs-lookup"><span data-stu-id="e4289-123">Return Type</span></span> | <span data-ttu-id="e4289-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e4289-124">Description</span></span>
-|-|-
[<span data-ttu-id="e4289-125">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="e4289-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="e4289-126">[Incidentlista](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="e4289-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="e4289-127">Skapa en lista över incidenter.</span><span class="sxs-lookup"><span data-stu-id="e4289-127">Get a list of incidents.</span></span>
[<span data-ttu-id="e4289-128">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="e4289-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="e4289-129">Incident</span><span class="sxs-lookup"><span data-stu-id="e4289-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="e4289-130">Uppdatera en specifik händelse.</span><span class="sxs-lookup"><span data-stu-id="e4289-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="e4289-131">Begäran om brödtext, svar och exempel</span><span class="sxs-lookup"><span data-stu-id="e4289-131">Request body, response, and examples</span></span>

<span data-ttu-id="e4289-132">I respektive metodartiklar finns mer information om hur du skapar en begäran eller parsar ett svar och praktiska exempel.</span><span class="sxs-lookup"><span data-stu-id="e4289-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="e4289-133">Vanliga egenskaper</span><span class="sxs-lookup"><span data-stu-id="e4289-133">Common properties</span></span>

<span data-ttu-id="e4289-134">Egenskap</span><span class="sxs-lookup"><span data-stu-id="e4289-134">Property</span></span> | <span data-ttu-id="e4289-135">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="e4289-135">Type</span></span> | <span data-ttu-id="e4289-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e4289-136">Description</span></span>
-|-|-
<span data-ttu-id="e4289-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="e4289-137">incidentId</span></span> | <span data-ttu-id="e4289-138">long</span><span class="sxs-lookup"><span data-stu-id="e4289-138">long</span></span> | <span data-ttu-id="e4289-139">Unikt ID för incidenter.</span><span class="sxs-lookup"><span data-stu-id="e4289-139">Incident unique ID.</span></span>
<span data-ttu-id="e4289-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="e4289-140">redirectIncidentId</span></span> | <span data-ttu-id="e4289-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="e4289-141">nullable long</span></span> | <span data-ttu-id="e4289-142">Det incident-ID som den aktuella incidenten kopplades till.</span><span class="sxs-lookup"><span data-stu-id="e4289-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="e4289-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="e4289-143">incidentName</span></span> | <span data-ttu-id="e4289-144">sträng</span><span class="sxs-lookup"><span data-stu-id="e4289-144">string</span></span> | <span data-ttu-id="e4289-145">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="e4289-145">The name of the Incident.</span></span>
<span data-ttu-id="e4289-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="e4289-146">createdTime</span></span> | <span data-ttu-id="e4289-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e4289-147">DateTimeOffset</span></span> | <span data-ttu-id="e4289-148">Datum och tid (i UTC) händelsen skapades.</span><span class="sxs-lookup"><span data-stu-id="e4289-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="e4289-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e4289-149">lastUpdateTime</span></span> | <span data-ttu-id="e4289-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e4289-150">DateTimeOffset</span></span> | <span data-ttu-id="e4289-151">Datum och tid (i UTC) incidenten uppdaterades senast.</span><span class="sxs-lookup"><span data-stu-id="e4289-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="e4289-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e4289-152">assignedTo</span></span> | <span data-ttu-id="e4289-153">sträng</span><span class="sxs-lookup"><span data-stu-id="e4289-153">string</span></span> | <span data-ttu-id="e4289-154">Ägaren av incidenten.</span><span class="sxs-lookup"><span data-stu-id="e4289-154">Owner of the Incident.</span></span>
<span data-ttu-id="e4289-155">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="e4289-155">severity</span></span> | <span data-ttu-id="e4289-156">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="e4289-156">Enum</span></span> | <span data-ttu-id="e4289-157">Incidentens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="e4289-157">Severity of the Incident.</span></span> <span data-ttu-id="e4289-158">Möjliga värden är: ```UnSpecified``` ```Informational``` , , och ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="e4289-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="e4289-159">status</span><span class="sxs-lookup"><span data-stu-id="e4289-159">status</span></span> | <span data-ttu-id="e4289-160">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="e4289-160">Enum</span></span> | <span data-ttu-id="e4289-161">Anger den aktuella statusen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="e4289-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="e4289-162">Möjliga värden är: ```Active``` ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="e4289-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e4289-163">klassificering</span><span class="sxs-lookup"><span data-stu-id="e4289-163">classification</span></span> | <span data-ttu-id="e4289-164">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="e4289-164">Enum</span></span> | <span data-ttu-id="e4289-165">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="e4289-165">Specification of the incident.</span></span> <span data-ttu-id="e4289-166">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="e4289-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e4289-167">determination</span><span class="sxs-lookup"><span data-stu-id="e4289-167">determination</span></span> | <span data-ttu-id="e4289-168">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="e4289-168">Enum</span></span> | <span data-ttu-id="e4289-169">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="e4289-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="e4289-170">Möjliga värden är: ```NotAvailable``` , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="e4289-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e4289-171">taggar</span><span class="sxs-lookup"><span data-stu-id="e4289-171">tags</span></span> | <span data-ttu-id="e4289-172">stränglista</span><span class="sxs-lookup"><span data-stu-id="e4289-172">string List</span></span> | <span data-ttu-id="e4289-173">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="e4289-173">List of Incident tags.</span></span>
<span data-ttu-id="e4289-174">aviseringar</span><span class="sxs-lookup"><span data-stu-id="e4289-174">alerts</span></span> | <span data-ttu-id="e4289-175">Aviseringslista</span><span class="sxs-lookup"><span data-stu-id="e4289-175">Alert List</span></span> | <span data-ttu-id="e4289-176">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="e4289-176">List of related alerts.</span></span> <span data-ttu-id="e4289-177">Se exempel i [API-dokumentationen för](api-list-incidents.md) listincidenter.</span><span class="sxs-lookup"><span data-stu-id="e4289-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e4289-178">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="e4289-178">Related articles</span></span>

- [<span data-ttu-id="e4289-179">Översikt över API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4289-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e4289-180">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="e4289-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e4289-181">API för listincidenter</span><span class="sxs-lookup"><span data-stu-id="e4289-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e4289-182">API för uppdateringshändelse</span><span class="sxs-lookup"><span data-stu-id="e4289-182">Update incident API</span></span>](api-update-incidents.md)
