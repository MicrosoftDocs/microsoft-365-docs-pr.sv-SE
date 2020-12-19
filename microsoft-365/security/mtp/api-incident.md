---
title: 'Microsoft 365 Defender tillbuds-API: er och resurs typen för incidenten'
description: Lär dig mer om metoderna och egenskaperna för resurs typen incident i Microsoft 365 Defender
keywords: incident, incidenter, API
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719340"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="10bea-104">Microsoft 365 Defender-incidenter API och resurs typen för incidenten</span><span class="sxs-lookup"><span data-stu-id="10bea-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="10bea-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="10bea-105">**Applies to:**</span></span>

- <span data-ttu-id="10bea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10bea-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10bea-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="10bea-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="10bea-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="10bea-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="10bea-109">En [olycka](incidents-overview.md) är en samling relaterade aviseringar som hjälper dig att beskriva en attack.</span><span class="sxs-lookup"><span data-stu-id="10bea-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="10bea-110">Händelser från olika enheter i organisationen aggregeras automatiskt efter Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="10bea-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="10bea-111">Du kan använda API-programatically för att få åtkomst till din organisations incidenter och relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="10bea-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="10bea-112">Kvoter och resurstilldelning</span><span class="sxs-lookup"><span data-stu-id="10bea-112">Quotas and resource allocation</span></span>

<span data-ttu-id="10bea-113">Du kan begära upp till 50 samtal per minut eller 1500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="10bea-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="10bea-114">Varje metod har också sina egna kvoter.</span><span class="sxs-lookup"><span data-stu-id="10bea-114">Each method also has its own quotas.</span></span> <span data-ttu-id="10bea-115">Mer information om metod specifika kvoter finns i respektive artikel för den metod du vill använda.</span><span class="sxs-lookup"><span data-stu-id="10bea-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="10bea-116">En `429` http-svarskod visar att du har nått en kvot, antingen av antalet begär Anden som skickats eller via utsatt tid för drift.</span><span class="sxs-lookup"><span data-stu-id="10bea-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="10bea-117">Svars texten inkluderar tiden tills den kvot du nådde återställs.</span><span class="sxs-lookup"><span data-stu-id="10bea-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="10bea-118">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="10bea-118">Permissions</span></span>

<span data-ttu-id="10bea-119">För incident API krävs olika typer av behörigheter för varje metod.</span><span class="sxs-lookup"><span data-stu-id="10bea-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="10bea-120">Mer information om vilka behörigheter som krävs finns i respektive metod.</span><span class="sxs-lookup"><span data-stu-id="10bea-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="10bea-121">Verifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="10bea-121">Methods</span></span>

<span data-ttu-id="10bea-122">Metod</span><span class="sxs-lookup"><span data-stu-id="10bea-122">Method</span></span> | <span data-ttu-id="10bea-123">Returtyp</span><span class="sxs-lookup"><span data-stu-id="10bea-123">Return Type</span></span> | <span data-ttu-id="10bea-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="10bea-124">Description</span></span>
-|-|-
[<span data-ttu-id="10bea-125">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="10bea-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="10bea-126">[Incident](api-incident.md) lista</span><span class="sxs-lookup"><span data-stu-id="10bea-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="10bea-127">Få en lista över incidenter.</span><span class="sxs-lookup"><span data-stu-id="10bea-127">Get a list of incidents.</span></span>
[<span data-ttu-id="10bea-128">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="10bea-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="10bea-129">Händelse</span><span class="sxs-lookup"><span data-stu-id="10bea-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="10bea-130">Uppdatera en specifik olycka.</span><span class="sxs-lookup"><span data-stu-id="10bea-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="10bea-131">Begära brödtext, svar och exempel</span><span class="sxs-lookup"><span data-stu-id="10bea-131">Request body, response, and examples</span></span>

<span data-ttu-id="10bea-132">Se de olika metod artiklarna för att få mer information om hur man skapar en begäran eller tolkar ett svar samt för praktiska exempel.</span><span class="sxs-lookup"><span data-stu-id="10bea-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="10bea-133">Gemensamma egenskaper</span><span class="sxs-lookup"><span data-stu-id="10bea-133">Common properties</span></span>

<span data-ttu-id="10bea-134">Egenskap</span><span class="sxs-lookup"><span data-stu-id="10bea-134">Property</span></span> | <span data-ttu-id="10bea-135">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="10bea-135">Type</span></span> | <span data-ttu-id="10bea-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="10bea-136">Description</span></span>
-|-|-
<span data-ttu-id="10bea-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="10bea-137">incidentId</span></span> | <span data-ttu-id="10bea-138">tids</span><span class="sxs-lookup"><span data-stu-id="10bea-138">long</span></span> | <span data-ttu-id="10bea-139">Unikt ID för incidenten.</span><span class="sxs-lookup"><span data-stu-id="10bea-139">Incident unique ID.</span></span>
<span data-ttu-id="10bea-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="10bea-140">redirectIncidentId</span></span> | <span data-ttu-id="10bea-141">null-värde långa</span><span class="sxs-lookup"><span data-stu-id="10bea-141">nullable long</span></span> | <span data-ttu-id="10bea-142">Incident-ID för den aktuella incidenten slogs samman till.</span><span class="sxs-lookup"><span data-stu-id="10bea-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="10bea-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="10bea-143">incidentName</span></span> | <span data-ttu-id="10bea-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="10bea-144">string</span></span> | <span data-ttu-id="10bea-145">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="10bea-145">The name of the Incident.</span></span>
<span data-ttu-id="10bea-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="10bea-146">createdTime</span></span> | <span data-ttu-id="10bea-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="10bea-147">DateTimeOffset</span></span> | <span data-ttu-id="10bea-148">Datum och tid (i UTC) då incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="10bea-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="10bea-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="10bea-149">lastUpdateTime</span></span> | <span data-ttu-id="10bea-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="10bea-150">DateTimeOffset</span></span> | <span data-ttu-id="10bea-151">Datum och tid (i UTC) då incidenten senast uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="10bea-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="10bea-152">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="10bea-152">assignedTo</span></span> | <span data-ttu-id="10bea-153">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="10bea-153">string</span></span> | <span data-ttu-id="10bea-154">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="10bea-154">Owner of the Incident.</span></span>
<span data-ttu-id="10bea-155">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="10bea-155">severity</span></span> | <span data-ttu-id="10bea-156">Enum</span><span class="sxs-lookup"><span data-stu-id="10bea-156">Enum</span></span> | <span data-ttu-id="10bea-157">Allvarlighets grad för incidenten.</span><span class="sxs-lookup"><span data-stu-id="10bea-157">Severity of the Incident.</span></span> <span data-ttu-id="10bea-158">Möjliga värden är: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` och ```High``` .</span><span class="sxs-lookup"><span data-stu-id="10bea-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="10bea-159">status</span><span class="sxs-lookup"><span data-stu-id="10bea-159">status</span></span> | <span data-ttu-id="10bea-160">Enum</span><span class="sxs-lookup"><span data-stu-id="10bea-160">Enum</span></span> | <span data-ttu-id="10bea-161">Anger den aktuella statusen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="10bea-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="10bea-162">Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="10bea-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="10bea-163">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="10bea-163">classification</span></span> | <span data-ttu-id="10bea-164">Enum</span><span class="sxs-lookup"><span data-stu-id="10bea-164">Enum</span></span> | <span data-ttu-id="10bea-165">Specifikation av felet.</span><span class="sxs-lookup"><span data-stu-id="10bea-165">Specification of the incident.</span></span> <span data-ttu-id="10bea-166">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="10bea-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="10bea-167">bedömning</span><span class="sxs-lookup"><span data-stu-id="10bea-167">determination</span></span> | <span data-ttu-id="10bea-168">Enum</span><span class="sxs-lookup"><span data-stu-id="10bea-168">Enum</span></span> | <span data-ttu-id="10bea-169">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="10bea-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="10bea-170">Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="10bea-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="10bea-171">taggen</span><span class="sxs-lookup"><span data-stu-id="10bea-171">tags</span></span> | <span data-ttu-id="10bea-172">sträng lista</span><span class="sxs-lookup"><span data-stu-id="10bea-172">string List</span></span> | <span data-ttu-id="10bea-173">Lista över incident koder.</span><span class="sxs-lookup"><span data-stu-id="10bea-173">List of Incident tags.</span></span>
<span data-ttu-id="10bea-174">larm</span><span class="sxs-lookup"><span data-stu-id="10bea-174">alerts</span></span> | <span data-ttu-id="10bea-175">Aviserings lista</span><span class="sxs-lookup"><span data-stu-id="10bea-175">Alert List</span></span> | <span data-ttu-id="10bea-176">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="10bea-176">List of related alerts.</span></span> <span data-ttu-id="10bea-177">Se exemplen på API-dokumentation för [samtal](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="10bea-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="10bea-178">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="10bea-178">Related articles</span></span>

- [<span data-ttu-id="10bea-179">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="10bea-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="10bea-180">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="10bea-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="10bea-181">API för List frågor</span><span class="sxs-lookup"><span data-stu-id="10bea-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="10bea-182">Uppdatera API för incident</span><span class="sxs-lookup"><span data-stu-id="10bea-182">Update incident API</span></span>](api-update-incidents.md)
