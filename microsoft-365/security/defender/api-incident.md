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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888439"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="6990f-104">Microsoft 365 Defender-incident-API:t och resurstypen för incidenter</span><span class="sxs-lookup"><span data-stu-id="6990f-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6990f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6990f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6990f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6990f-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="6990f-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="6990f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6990f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="6990f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6990f-109">En [incident](incidents-overview.md) är en samling relaterade aviseringar som beskriver en attack.</span><span class="sxs-lookup"><span data-stu-id="6990f-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6990f-110">Händelser från olika enheter i organisationen aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6990f-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6990f-111">Du kan använda incident-API:t för att programmässigt få åtkomst till organisationens incidenter och relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="6990f-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6990f-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="6990f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6990f-113">Du kan begära upp till 50 samtal per minut eller 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="6990f-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6990f-114">Varje metod har också egna kvoter.</span><span class="sxs-lookup"><span data-stu-id="6990f-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6990f-115">Mer information om metodspecifika kvoter finns i respektive artikel för den metod du vill använda.</span><span class="sxs-lookup"><span data-stu-id="6990f-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6990f-116">En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid.</span><span class="sxs-lookup"><span data-stu-id="6990f-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6990f-117">Svarstexten tar med tiden tills kvoten du har nått återställs.</span><span class="sxs-lookup"><span data-stu-id="6990f-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6990f-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6990f-118">Permissions</span></span>

<span data-ttu-id="6990f-119">För incident-API:t krävs olika typer av behörigheter för var och en av dess metoder.</span><span class="sxs-lookup"><span data-stu-id="6990f-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6990f-120">Mer information om obligatoriska behörigheter finns i respektive metods artikel.</span><span class="sxs-lookup"><span data-stu-id="6990f-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6990f-121">Metoder</span><span class="sxs-lookup"><span data-stu-id="6990f-121">Methods</span></span>

<span data-ttu-id="6990f-122">Metod</span><span class="sxs-lookup"><span data-stu-id="6990f-122">Method</span></span> | <span data-ttu-id="6990f-123">Returtyp</span><span class="sxs-lookup"><span data-stu-id="6990f-123">Return Type</span></span> | <span data-ttu-id="6990f-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6990f-124">Description</span></span>
-|-|-
[<span data-ttu-id="6990f-125">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="6990f-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6990f-126">[Incidentlista](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="6990f-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6990f-127">Få en lista över alla incidenter.</span><span class="sxs-lookup"><span data-stu-id="6990f-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6990f-128">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="6990f-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6990f-129">Incident</span><span class="sxs-lookup"><span data-stu-id="6990f-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6990f-130">Uppdatera en specifik händelse.</span><span class="sxs-lookup"><span data-stu-id="6990f-130">Update a specific incident.</span></span>
[<span data-ttu-id="6990f-131">Hämta incident</span><span class="sxs-lookup"><span data-stu-id="6990f-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="6990f-132">Incident</span><span class="sxs-lookup"><span data-stu-id="6990f-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="6990f-133">Få en enda incident.</span><span class="sxs-lookup"><span data-stu-id="6990f-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6990f-134">Begärans brödtext, svar och exempel</span><span class="sxs-lookup"><span data-stu-id="6990f-134">Request body, response, and examples</span></span>

<span data-ttu-id="6990f-135">Mer information om hur du skapar en begäran eller parsar ett svar samt praktiska exempel finns i respektive metodartiklar.</span><span class="sxs-lookup"><span data-stu-id="6990f-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6990f-136">Gemensamma egenskaper</span><span class="sxs-lookup"><span data-stu-id="6990f-136">Common properties</span></span>

<span data-ttu-id="6990f-137">Egenskap</span><span class="sxs-lookup"><span data-stu-id="6990f-137">Property</span></span> | <span data-ttu-id="6990f-138">Typ</span><span class="sxs-lookup"><span data-stu-id="6990f-138">Type</span></span> | <span data-ttu-id="6990f-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6990f-139">Description</span></span>
-|-|-
<span data-ttu-id="6990f-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="6990f-140">incidentId</span></span> | <span data-ttu-id="6990f-141">long</span><span class="sxs-lookup"><span data-stu-id="6990f-141">long</span></span> | <span data-ttu-id="6990f-142">Unikt ID för incidenter.</span><span class="sxs-lookup"><span data-stu-id="6990f-142">Incident unique ID.</span></span>
<span data-ttu-id="6990f-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6990f-143">redirectIncidentId</span></span> | <span data-ttu-id="6990f-144">nullbar long</span><span class="sxs-lookup"><span data-stu-id="6990f-144">nullable long</span></span> | <span data-ttu-id="6990f-145">Det incident-ID som den aktuella incidenten kopplades till.</span><span class="sxs-lookup"><span data-stu-id="6990f-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6990f-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="6990f-146">incidentName</span></span> | <span data-ttu-id="6990f-147">sträng</span><span class="sxs-lookup"><span data-stu-id="6990f-147">string</span></span> | <span data-ttu-id="6990f-148">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="6990f-148">The name of the Incident.</span></span>
<span data-ttu-id="6990f-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="6990f-149">createdTime</span></span> | <span data-ttu-id="6990f-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6990f-150">DateTimeOffset</span></span> | <span data-ttu-id="6990f-151">Datum och tid (i UTC) som incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="6990f-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6990f-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6990f-152">lastUpdateTime</span></span> | <span data-ttu-id="6990f-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6990f-153">DateTimeOffset</span></span> | <span data-ttu-id="6990f-154">Datum och tid (i UTC) som incidenten uppdaterades senast.</span><span class="sxs-lookup"><span data-stu-id="6990f-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6990f-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6990f-155">assignedTo</span></span> | <span data-ttu-id="6990f-156">sträng</span><span class="sxs-lookup"><span data-stu-id="6990f-156">string</span></span> | <span data-ttu-id="6990f-157">Ägaren till händelsen.</span><span class="sxs-lookup"><span data-stu-id="6990f-157">Owner of the Incident.</span></span>
<span data-ttu-id="6990f-158">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="6990f-158">severity</span></span> | <span data-ttu-id="6990f-159">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6990f-159">Enum</span></span> | <span data-ttu-id="6990f-160">Incidentens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="6990f-160">Severity of the Incident.</span></span> <span data-ttu-id="6990f-161">Möjliga värden är: ```UnSpecified``` , , , och ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="6990f-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6990f-162">status</span><span class="sxs-lookup"><span data-stu-id="6990f-162">status</span></span> | <span data-ttu-id="6990f-163">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6990f-163">Enum</span></span> | <span data-ttu-id="6990f-164">Anger incidentens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="6990f-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="6990f-165">Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="6990f-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6990f-166">klassificering</span><span class="sxs-lookup"><span data-stu-id="6990f-166">classification</span></span> | <span data-ttu-id="6990f-167">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6990f-167">Enum</span></span> | <span data-ttu-id="6990f-168">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="6990f-168">Specification of the incident.</span></span> <span data-ttu-id="6990f-169">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="6990f-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6990f-170">determination</span><span class="sxs-lookup"><span data-stu-id="6990f-170">determination</span></span> | <span data-ttu-id="6990f-171">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="6990f-171">Enum</span></span> | <span data-ttu-id="6990f-172">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="6990f-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="6990f-173">Möjliga värden är: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="6990f-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6990f-174">taggar</span><span class="sxs-lookup"><span data-stu-id="6990f-174">tags</span></span> | <span data-ttu-id="6990f-175">stränglista</span><span class="sxs-lookup"><span data-stu-id="6990f-175">string List</span></span> | <span data-ttu-id="6990f-176">Lista över incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="6990f-176">List of Incident tags.</span></span>
<span data-ttu-id="6990f-177">kommentarer</span><span class="sxs-lookup"><span data-stu-id="6990f-177">comments</span></span> | <span data-ttu-id="6990f-178">Lista över incidentkommentarer</span><span class="sxs-lookup"><span data-stu-id="6990f-178">List of incident comments</span></span> | <span data-ttu-id="6990f-179">Incidentkommentarsobjekt innehåller: kommentarssträng, createdBy-sträng och createTime-datumtid.</span><span class="sxs-lookup"><span data-stu-id="6990f-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="6990f-180">aviseringar</span><span class="sxs-lookup"><span data-stu-id="6990f-180">alerts</span></span> | <span data-ttu-id="6990f-181">Aviseringslista</span><span class="sxs-lookup"><span data-stu-id="6990f-181">Alert List</span></span> | <span data-ttu-id="6990f-182">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="6990f-182">List of related alerts.</span></span> <span data-ttu-id="6990f-183">Se exempel i [dokumentationen för API för listincidenter.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="6990f-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6990f-184">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6990f-184">Related articles</span></span>

- [<span data-ttu-id="6990f-185">Microsoft 365 Översikt över Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="6990f-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6990f-186">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="6990f-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6990f-187">API för listincidenter</span><span class="sxs-lookup"><span data-stu-id="6990f-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6990f-188">Api för uppdatering av incident</span><span class="sxs-lookup"><span data-stu-id="6990f-188">Update incident API</span></span>](api-update-incidents.md)
