---
title: API för listincidenter i Microsoft 365 Defender
description: Lär dig hur du listar incident-API i Microsoft 365 Defender
keywords: lista, incident, incidenter, api
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
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932076"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="5b08b-104">API för listincidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b08b-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b08b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5b08b-105">**Applies to:**</span></span>

- <span data-ttu-id="5b08b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b08b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b08b-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="5b08b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5b08b-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="5b08b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="5b08b-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-109">API description</span></span>

<span data-ttu-id="5b08b-110">Med API:t för listincidenter kan du sortera olika incidenter för att skapa en välinformerad cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="5b08b-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="5b08b-111">Här visas en samling incidenter som har flaggats i nätverket, inom det angivna tidsperioden i din miljöbevarandeprincip.</span><span class="sxs-lookup"><span data-stu-id="5b08b-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="5b08b-112">De senaste incidenterna visas högst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="5b08b-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="5b08b-113">Varje incident innehåller en matris med relaterade aviseringar och deras relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="5b08b-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="5b08b-114">API:t stöder följande **OData-operatorer:**</span><span class="sxs-lookup"><span data-stu-id="5b08b-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="5b08b-115">`$filter` på `lastUpdateTime` fliken `createdTime` `status` , och `assignedTo` egenskaperna</span><span class="sxs-lookup"><span data-stu-id="5b08b-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="5b08b-116">`$top`, med maximalt **värde 100**</span><span class="sxs-lookup"><span data-stu-id="5b08b-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="5b08b-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="5b08b-117">Limitations</span></span>

1. <span data-ttu-id="5b08b-118">Maximal sidstorlek är **100 ärenden.**</span><span class="sxs-lookup"><span data-stu-id="5b08b-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="5b08b-119">Maximalt antal förfrågningar är **50 samtal per minut och** **1 500 samtal per timme.**</span><span class="sxs-lookup"><span data-stu-id="5b08b-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="5b08b-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5b08b-120">Permissions</span></span>

<span data-ttu-id="5b08b-121">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="5b08b-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5b08b-122">Mer information, inklusive hur du väljer behörigheter, finns i [Access-API:er för Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="5b08b-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="5b08b-123">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="5b08b-123">Permission type</span></span> | <span data-ttu-id="5b08b-124">Behörighet</span><span class="sxs-lookup"><span data-stu-id="5b08b-124">Permission</span></span> | <span data-ttu-id="5b08b-125">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="5b08b-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="5b08b-126">Program</span><span class="sxs-lookup"><span data-stu-id="5b08b-126">Application</span></span> | <span data-ttu-id="5b08b-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="5b08b-127">Incident.Read.All</span></span> | <span data-ttu-id="5b08b-128">Läs alla incidenter</span><span class="sxs-lookup"><span data-stu-id="5b08b-128">Read all incidents</span></span>
<span data-ttu-id="5b08b-129">Program</span><span class="sxs-lookup"><span data-stu-id="5b08b-129">Application</span></span> | <span data-ttu-id="5b08b-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5b08b-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="5b08b-131">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="5b08b-131">Read and write all incidents</span></span>
<span data-ttu-id="5b08b-132">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5b08b-132">Delegated (work or school account)</span></span> | <span data-ttu-id="5b08b-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="5b08b-133">Incident.Read</span></span> | <span data-ttu-id="5b08b-134">Läs incidenter</span><span class="sxs-lookup"><span data-stu-id="5b08b-134">Read incidents</span></span>
<span data-ttu-id="5b08b-135">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5b08b-135">Delegated (work or school account)</span></span> | <span data-ttu-id="5b08b-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5b08b-136">Incident.ReadWrite</span></span> | <span data-ttu-id="5b08b-137">Läs- och skrivincidenter</span><span class="sxs-lookup"><span data-stu-id="5b08b-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="5b08b-138">När du skaffar ett token med användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="5b08b-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="5b08b-139">Användaren måste ha visningsbehörighet för ärenden i portalen.</span><span class="sxs-lookup"><span data-stu-id="5b08b-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="5b08b-140">Svaret inkluderar bara incidenter som användaren exponeras för.</span><span class="sxs-lookup"><span data-stu-id="5b08b-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="5b08b-141">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5b08b-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="5b08b-142">Begär sidhuvuden</span><span class="sxs-lookup"><span data-stu-id="5b08b-142">Request headers</span></span>

<span data-ttu-id="5b08b-143">Namn</span><span class="sxs-lookup"><span data-stu-id="5b08b-143">Name</span></span> | <span data-ttu-id="5b08b-144">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="5b08b-144">Type</span></span> | <span data-ttu-id="5b08b-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-145">Description</span></span>
-|-|-
<span data-ttu-id="5b08b-146">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5b08b-146">Authorization</span></span> | <span data-ttu-id="5b08b-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="5b08b-147">String</span></span> | <span data-ttu-id="5b08b-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5b08b-148">Bearer {token}.</span></span> <span data-ttu-id="5b08b-149">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5b08b-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="5b08b-150">Begärandetext</span><span class="sxs-lookup"><span data-stu-id="5b08b-150">Request body</span></span>

<span data-ttu-id="5b08b-151">Inget.</span><span class="sxs-lookup"><span data-stu-id="5b08b-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="5b08b-152">Svar</span><span class="sxs-lookup"><span data-stu-id="5b08b-152">Response</span></span>

<span data-ttu-id="5b08b-153">Om det lyckas returneras den `200 OK` här metoden och en lista över [incidenter](api-incident.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="5b08b-154">Schemamappning</span><span class="sxs-lookup"><span data-stu-id="5b08b-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="5b08b-155">Incidentmetadata</span><span class="sxs-lookup"><span data-stu-id="5b08b-155">Incident metadata</span></span>

<span data-ttu-id="5b08b-156">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="5b08b-156">Field name</span></span> | <span data-ttu-id="5b08b-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-157">Description</span></span> | <span data-ttu-id="5b08b-158">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="5b08b-158">Example value</span></span>
-|-|-
<span data-ttu-id="5b08b-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="5b08b-159">incidentId</span></span> | <span data-ttu-id="5b08b-160">Unikt ID som representerar incidenten</span><span class="sxs-lookup"><span data-stu-id="5b08b-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="5b08b-161">924565</span><span class="sxs-lookup"><span data-stu-id="5b08b-161">924565</span></span>
<span data-ttu-id="5b08b-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="5b08b-162">redirectIncidentId</span></span> | <span data-ttu-id="5b08b-163">Fylls bara i om en incident grupperas tillsammans med en annan incident, som en del av händelsebearbetningslogiken.</span><span class="sxs-lookup"><span data-stu-id="5b08b-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="5b08b-164">924569</span><span class="sxs-lookup"><span data-stu-id="5b08b-164">924569</span></span>
<span data-ttu-id="5b08b-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="5b08b-165">incidentName</span></span> | <span data-ttu-id="5b08b-166">Ett strängvärde som är tillgängligt för varje incident.</span><span class="sxs-lookup"><span data-stu-id="5b08b-166">String value available for every incident.</span></span> | <span data-ttu-id="5b08b-167">Utpressningstrojanaktivitet</span><span class="sxs-lookup"><span data-stu-id="5b08b-167">Ransomware activity</span></span>
<span data-ttu-id="5b08b-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-168">createdTime</span></span> | <span data-ttu-id="5b08b-169">Tidpunkt när incidenten skapades först.</span><span class="sxs-lookup"><span data-stu-id="5b08b-169">Time when incident was first created.</span></span> | <span data-ttu-id="5b08b-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="5b08b-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-171">lastUpdateTime</span></span> | <span data-ttu-id="5b08b-172">Tid då incidenten uppdaterades senast på backend.</span><span class="sxs-lookup"><span data-stu-id="5b08b-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="5b08b-173">Det här fältet kan användas när du anger parametern för begäran för det tidsintervall som incidenterna ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="5b08b-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="5b08b-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="5b08b-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="5b08b-175">assignedTo</span></span> | <span data-ttu-id="5b08b-176">Ägaren till incidenten, eller *null* om ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="5b08b-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="5b08b-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-177">secop2@contoso.com</span></span>
<span data-ttu-id="5b08b-178">klassificering</span><span class="sxs-lookup"><span data-stu-id="5b08b-178">classification</span></span> | <span data-ttu-id="5b08b-179">Specifikationen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-179">The specification for the incident.</span></span> <span data-ttu-id="5b08b-180">Egenskapsvärdena är: *Okänt, FalsktPositive,* *TruePositive* </span><span class="sxs-lookup"><span data-stu-id="5b08b-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="5b08b-181">Okänd</span><span class="sxs-lookup"><span data-stu-id="5b08b-181">Unknown</span></span>
<span data-ttu-id="5b08b-182">determination</span><span class="sxs-lookup"><span data-stu-id="5b08b-182">determination</span></span> | <span data-ttu-id="5b08b-183">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="5b08b-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="5b08b-184">Egenskapsvärdena är: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other*</span><span class="sxs-lookup"><span data-stu-id="5b08b-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="5b08b-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="5b08b-185">NotAvailable</span></span>
<span data-ttu-id="5b08b-186">status</span><span class="sxs-lookup"><span data-stu-id="5b08b-186">status</span></span> | <span data-ttu-id="5b08b-187">Kategorisera incidenter (som *aktiva* eller *lösta).*</span><span class="sxs-lookup"><span data-stu-id="5b08b-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="5b08b-188">Det kan hjälpa dig att organisera och hantera dina svar på incidenter.</span><span class="sxs-lookup"><span data-stu-id="5b08b-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="5b08b-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="5b08b-189">Active</span></span>
<span data-ttu-id="5b08b-190">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="5b08b-190">severity</span></span> | <span data-ttu-id="5b08b-191">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="5b08b-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="5b08b-192">Ju högre allvarlighetsgrad desto större påverkan.</span><span class="sxs-lookup"><span data-stu-id="5b08b-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="5b08b-193">Vanligtvis kräver objekt med högre allvarlighetsgrad mest omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="5b08b-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="5b08b-194">Ett av följande värden: *Information,* \*Låg,\*\*Medel och *Hög.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="5b08b-195">Medel</span><span class="sxs-lookup"><span data-stu-id="5b08b-195">Medium</span></span>
<span data-ttu-id="5b08b-196">taggar</span><span class="sxs-lookup"><span data-stu-id="5b08b-196">tags</span></span> | <span data-ttu-id="5b08b-197">Matris med anpassade taggar kopplade till en incident, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="5b08b-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="5b08b-198">aviseringar</span><span class="sxs-lookup"><span data-stu-id="5b08b-198">alerts</span></span> | <span data-ttu-id="5b08b-199">Matris som innehåller alla aviseringar som är relaterade till händelsen samt annan information, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen och källan till aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="5b08b-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="5b08b-200">\[\] (se information om aviseringsfälten nedan)</span><span class="sxs-lookup"><span data-stu-id="5b08b-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="5b08b-201">Aviseringsmetadata</span><span class="sxs-lookup"><span data-stu-id="5b08b-201">Alerts metadata</span></span>

<span data-ttu-id="5b08b-202">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="5b08b-202">Field name</span></span> | <span data-ttu-id="5b08b-203">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-203">Description</span></span> | <span data-ttu-id="5b08b-204">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="5b08b-204">Example value</span></span>
-|-|-
<span data-ttu-id="5b08b-205">alertid</span><span class="sxs-lookup"><span data-stu-id="5b08b-205">alertId</span></span> | <span data-ttu-id="5b08b-206">Unik identifierare som representerar aviseringen</span><span class="sxs-lookup"><span data-stu-id="5b08b-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="5b08b-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="5b08b-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="5b08b-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="5b08b-208">incidentId</span></span> | <span data-ttu-id="5b08b-209">Unikt ID som representerar den händelse som den här aviseringen är associerad med</span><span class="sxs-lookup"><span data-stu-id="5b08b-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="5b08b-210">924565</span><span class="sxs-lookup"><span data-stu-id="5b08b-210">924565</span></span>
<span data-ttu-id="5b08b-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="5b08b-211">serviceSource</span></span> | <span data-ttu-id="5b08b-212">Tjänst som aviseringen kommer från, till exempel Microsoft Defender för Slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet eller Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b08b-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="5b08b-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="5b08b-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="5b08b-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-214">creationTime</span></span> | <span data-ttu-id="5b08b-215">Tidpunkt när aviseringen skapades.</span><span class="sxs-lookup"><span data-stu-id="5b08b-215">Time when alert was first created.</span></span> | <span data-ttu-id="5b08b-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="5b08b-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-217">lastUpdatedTime</span></span> | <span data-ttu-id="5b08b-218">Tid när aviseringen senast uppdaterades på backend.</span><span class="sxs-lookup"><span data-stu-id="5b08b-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="5b08b-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="5b08b-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-220">resolvedTime</span></span> | <span data-ttu-id="5b08b-221">Tid när aviseringen löstes.</span><span class="sxs-lookup"><span data-stu-id="5b08b-221">Time when alert was resolved.</span></span> | <span data-ttu-id="5b08b-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="5b08b-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="5b08b-223">firstActivity</span></span> | <span data-ttu-id="5b08b-224">Tid när aviseringen först rapporterade att aktiviteten uppdaterades på backend.</span><span class="sxs-lookup"><span data-stu-id="5b08b-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="5b08b-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="5b08b-226">rubrik</span><span class="sxs-lookup"><span data-stu-id="5b08b-226">title</span></span> | <span data-ttu-id="5b08b-227">Kort identifiering av strängvärdet som är tillgängligt för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="5b08b-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="5b08b-228">Utpressningstrojanaktivitet</span><span class="sxs-lookup"><span data-stu-id="5b08b-228">Ransomware activity</span></span>
<span data-ttu-id="5b08b-229">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-229">description</span></span> | <span data-ttu-id="5b08b-230">Strängvärde som beskriver varje avisering.</span><span class="sxs-lookup"><span data-stu-id="5b08b-230">String value describing each alert.</span></span> | <span data-ttu-id="5b08b-231">Användaren Test User2 (testUser2@contoso.com) har manipulerat 99 filer med flera tillägg som slutar med den ovanliga filnamnstillägget *herunterladen.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="5b08b-232">Det här är ett ovanligt antal filmanipuleringar och är därför en potentiell utpressningstrojanattack.</span><span class="sxs-lookup"><span data-stu-id="5b08b-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="5b08b-233">kategori</span><span class="sxs-lookup"><span data-stu-id="5b08b-233">category</span></span> | <span data-ttu-id="5b08b-234">Visuell och numerisk vy över hur långt attacken har fortskridt längs kill chain.</span><span class="sxs-lookup"><span data-stu-id="5b08b-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="5b08b-235">I linje med [MITRE ATT&CK™ framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="5b08b-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="5b08b-236">Påverkan</span><span class="sxs-lookup"><span data-stu-id="5b08b-236">Impact</span></span>
<span data-ttu-id="5b08b-237">status</span><span class="sxs-lookup"><span data-stu-id="5b08b-237">status</span></span> | <span data-ttu-id="5b08b-238">Kategorisera aviseringar (som *Ny,* *Aktiv* eller *Matchad).*</span><span class="sxs-lookup"><span data-stu-id="5b08b-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="5b08b-239">Det kan hjälpa dig att organisera och hantera dina svar på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5b08b-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="5b08b-240">Ny</span><span class="sxs-lookup"><span data-stu-id="5b08b-240">New</span></span>
<span data-ttu-id="5b08b-241">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="5b08b-241">severity</span></span> | <span data-ttu-id="5b08b-242">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="5b08b-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="5b08b-243">Ju högre allvarlighetsgrad desto större påverkan.</span><span class="sxs-lookup"><span data-stu-id="5b08b-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="5b08b-244">Vanligtvis kräver objekt med högre allvarlighetsgrad mest omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="5b08b-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="5b08b-245">Ett av följande värden: *Information,* \*Låg,\*\*Medel och *Hög.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="5b08b-246">Medel</span><span class="sxs-lookup"><span data-stu-id="5b08b-246">Medium</span></span>
<span data-ttu-id="5b08b-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="5b08b-247">investigationId</span></span> | <span data-ttu-id="5b08b-248">Detta är det automatiska undersöknings-ID som utlöses av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5b08b-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="5b08b-249">1234</span><span class="sxs-lookup"><span data-stu-id="5b08b-249">1234</span></span>
<span data-ttu-id="5b08b-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="5b08b-250">investigationState</span></span> | <span data-ttu-id="5b08b-251">Information om undersökningens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="5b08b-251">Information on the investigation's current status.</span></span> <span data-ttu-id="5b08b-252">Ett av följande *värden:* *Okänt,* Avslutat, *Lyckades,*  *Misslyckades,* Delvis åtgärdat, Körs, *VäntandeApproval,* *PendingResource,* *DelvisInvesterat,* *AvslutatByUser,* *TerminatedBySystem,* *Queued,* *InnerFailure,* *PreexistingAlert,* *UnsupportedOs,* *UnsupportedAlertType,* *SuppressedAlert.*  </span><span class="sxs-lookup"><span data-stu-id="5b08b-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="5b08b-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="5b08b-253">UnsupportedAlertType</span></span>
<span data-ttu-id="5b08b-254">klassificering</span><span class="sxs-lookup"><span data-stu-id="5b08b-254">classification</span></span> | <span data-ttu-id="5b08b-255">Specifikationen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-255">The specification for the incident.</span></span> <span data-ttu-id="5b08b-256">Egenskapsvärdena *är:* *Okänt, FalsktPositive,* *TruePositive* eller *null*</span><span class="sxs-lookup"><span data-stu-id="5b08b-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="5b08b-257">Okänd</span><span class="sxs-lookup"><span data-stu-id="5b08b-257">Unknown</span></span>
<span data-ttu-id="5b08b-258">determination</span><span class="sxs-lookup"><span data-stu-id="5b08b-258">determination</span></span> | <span data-ttu-id="5b08b-259">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="5b08b-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="5b08b-260">Egenskapsvärdena är: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* eller  *null*</span><span class="sxs-lookup"><span data-stu-id="5b08b-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="5b08b-261">Apt</span><span class="sxs-lookup"><span data-stu-id="5b08b-261">Apt</span></span>
<span data-ttu-id="5b08b-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="5b08b-262">assignedTo</span></span> | <span data-ttu-id="5b08b-263">Ägaren till händelsen, eller *null om* ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="5b08b-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="5b08b-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-264">secop2@contoso.com</span></span>
<span data-ttu-id="5b08b-265">actorName</span><span class="sxs-lookup"><span data-stu-id="5b08b-265">actorName</span></span> | <span data-ttu-id="5b08b-266">Om det finns en aktivitetsgrupp som är kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5b08b-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="5b08b-267">BORON</span><span class="sxs-lookup"><span data-stu-id="5b08b-267">BORON</span></span>
<span data-ttu-id="5b08b-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="5b08b-268">threatFamilyName</span></span> | <span data-ttu-id="5b08b-269">Hotfamilj kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5b08b-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="5b08b-270">null</span><span class="sxs-lookup"><span data-stu-id="5b08b-270">null</span></span>
<span data-ttu-id="5b08b-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="5b08b-271">mitreTechniques</span></span> | <span data-ttu-id="5b08b-272">Attacktekniker, i enlighet med [MITRE ATT&CK-™](https://attack.mitre.org/)ramverket.</span><span class="sxs-lookup"><span data-stu-id="5b08b-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="5b08b-273">enheter</span><span class="sxs-lookup"><span data-stu-id="5b08b-273">devices</span></span> | <span data-ttu-id="5b08b-274">Alla enheter där aviseringar om händelsen har skickats.</span><span class="sxs-lookup"><span data-stu-id="5b08b-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="5b08b-275">\[\] (se information om entitetsfälten nedan)</span><span class="sxs-lookup"><span data-stu-id="5b08b-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="5b08b-276">Enhetsformat</span><span class="sxs-lookup"><span data-stu-id="5b08b-276">Device format</span></span>

<span data-ttu-id="5b08b-277">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="5b08b-277">Field name</span></span> | <span data-ttu-id="5b08b-278">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-278">Description</span></span> | <span data-ttu-id="5b08b-279">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="5b08b-279">Example value</span></span>
-|-|-
<span data-ttu-id="5b08b-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="5b08b-280">DeviceId</span></span> | <span data-ttu-id="5b08b-281">Enhets-ID:t som angetts i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="5b08b-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="5b08b-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="5b08b-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="5b08b-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="5b08b-283">aadDeviceId</span></span> |  <span data-ttu-id="5b08b-284">Det enhets-ID som angetts [i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="5b08b-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="5b08b-285">Endast tillgängligt för domän anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="5b08b-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="5b08b-286">null</span><span class="sxs-lookup"><span data-stu-id="5b08b-286">null</span></span>
<span data-ttu-id="5b08b-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="5b08b-287">deviceDnsName</span></span> | <span data-ttu-id="5b08b-288">Det fullständigt kvalificerade domännamnet för enheten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="5b08b-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="5b08b-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="5b08b-290">osPlatform</span></span> | <span data-ttu-id="5b08b-291">Den OS-plattform som enheten körs på.</span><span class="sxs-lookup"><span data-stu-id="5b08b-291">The OS platform the device is running.</span></span>| <span data-ttu-id="5b08b-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="5b08b-292">WindowsServer2016</span></span>
<span data-ttu-id="5b08b-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="5b08b-293">osBuild</span></span> | <span data-ttu-id="5b08b-294">Versionsversionen för operativsystemet som enheten kör.</span><span class="sxs-lookup"><span data-stu-id="5b08b-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="5b08b-295">14393</span><span class="sxs-lookup"><span data-stu-id="5b08b-295">14393</span></span>
<span data-ttu-id="5b08b-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="5b08b-296">rbacGroupName</span></span> | <span data-ttu-id="5b08b-297">Den [rollbaserade åtkomstkontrollgruppen](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) som är kopplad till enheten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="5b08b-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="5b08b-298">WDATP-Ring0</span></span>
<span data-ttu-id="5b08b-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="5b08b-299">firstSeen</span></span> | <span data-ttu-id="5b08b-300">Tid när enheten sågs för första gången.</span><span class="sxs-lookup"><span data-stu-id="5b08b-300">Time when device was first seen.</span></span> | <span data-ttu-id="5b08b-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="5b08b-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="5b08b-302">healthStatus</span></span> | <span data-ttu-id="5b08b-303">Status för enheten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-303">The health state of the device.</span></span> | <span data-ttu-id="5b08b-304">Aktiv</span><span class="sxs-lookup"><span data-stu-id="5b08b-304">Active</span></span>
<span data-ttu-id="5b08b-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="5b08b-305">riskScore</span></span> | <span data-ttu-id="5b08b-306">Riskresultatet för enheten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-306">The risk score for the  device.</span></span> | <span data-ttu-id="5b08b-307">Högsta</span><span class="sxs-lookup"><span data-stu-id="5b08b-307">High</span></span>
<span data-ttu-id="5b08b-308">enheter</span><span class="sxs-lookup"><span data-stu-id="5b08b-308">entities</span></span> | <span data-ttu-id="5b08b-309">Alla enheter som har identifierats som en del av, eller relaterade till, en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="5b08b-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="5b08b-310">\[\] (se information om entitetsfälten nedan)</span><span class="sxs-lookup"><span data-stu-id="5b08b-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="5b08b-311">Entitetsformat</span><span class="sxs-lookup"><span data-stu-id="5b08b-311">Entity Format</span></span>

<span data-ttu-id="5b08b-312">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="5b08b-312">Field name</span></span> | <span data-ttu-id="5b08b-313">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5b08b-313">Description</span></span> | <span data-ttu-id="5b08b-314">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="5b08b-314">Example value</span></span>
-|-|-
<span data-ttu-id="5b08b-315">entityType</span><span class="sxs-lookup"><span data-stu-id="5b08b-315">entityType</span></span> | <span data-ttu-id="5b08b-316">Enheter som har identifierats som en del av eller relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="5b08b-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="5b08b-317">Egenskapsvärdena är: *Användare,* *Ip,* *URL,* *Fil,* *Process,* *MailBox,* *MailMessage,* *MailCluster,* *Registry*</span><span class="sxs-lookup"><span data-stu-id="5b08b-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="5b08b-318">Användare</span><span class="sxs-lookup"><span data-stu-id="5b08b-318">User</span></span>
<span data-ttu-id="5b08b-319">sha1</span><span class="sxs-lookup"><span data-stu-id="5b08b-319">sha1</span></span> | <span data-ttu-id="5b08b-320">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="5b08b-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="5b08b-321">Filhash för aviseringar som associeras med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="5b08b-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="5b08b-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="5b08b-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="5b08b-323">sha256</span><span class="sxs-lookup"><span data-stu-id="5b08b-323">sha256</span></span> | <span data-ttu-id="5b08b-324">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="5b08b-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="5b08b-325">Filhash för aviseringar som associeras med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="5b08b-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="5b08b-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="5b08b-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="5b08b-327">fileName</span><span class="sxs-lookup"><span data-stu-id="5b08b-327">fileName</span></span> | <span data-ttu-id="5b08b-328">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="5b08b-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="5b08b-329">Filnamnet för aviseringar som associeras med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="5b08b-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="5b08b-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="5b08b-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="5b08b-331">filePath</span><span class="sxs-lookup"><span data-stu-id="5b08b-331">filePath</span></span> | <span data-ttu-id="5b08b-332">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="5b08b-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="5b08b-333">Filsökvägen för aviseringar som associeras med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="5b08b-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="5b08b-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="5b08b-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="5b08b-335">processId</span><span class="sxs-lookup"><span data-stu-id="5b08b-335">processId</span></span> | <span data-ttu-id="5b08b-336">Tillgängligt om entityType är *Process.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="5b08b-337">24348</span><span class="sxs-lookup"><span data-stu-id="5b08b-337">24348</span></span>
<span data-ttu-id="5b08b-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="5b08b-338">processCommandLine</span></span> | <span data-ttu-id="5b08b-339">Tillgängligt om entityType är *Process.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="5b08b-340">"Filen är klar att laddas ned \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="5b08b-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="5b08b-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-341">processCreationTime</span></span> | <span data-ttu-id="5b08b-342">Tillgängligt om entityType är *Process.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="5b08b-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="5b08b-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="5b08b-344">parentProcessId</span></span> | <span data-ttu-id="5b08b-345">Tillgängligt om entityType är *Process.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="5b08b-346">16840</span><span class="sxs-lookup"><span data-stu-id="5b08b-346">16840</span></span>
<span data-ttu-id="5b08b-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="5b08b-347">parentProcessCreationTime</span></span> | <span data-ttu-id="5b08b-348">Tillgängligt om entityType är *Process.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="5b08b-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="5b08b-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="5b08b-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="5b08b-350">ipAddress</span></span> | <span data-ttu-id="5b08b-351">Tillgängligt om entityType är *IP.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="5b08b-352">IP-adress för aviseringar som associeras med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksdestination.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="5b08b-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="5b08b-353">62.216.203.204</span></span>
<span data-ttu-id="5b08b-354">url</span><span class="sxs-lookup"><span data-stu-id="5b08b-354">url</span></span> | <span data-ttu-id="5b08b-355">Tillgängligt om entityType är *URL.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="5b08b-356">URL för aviseringar som är associerade med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksdestination.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="5b08b-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="5b08b-357">down.esales360.cn</span></span>
<span data-ttu-id="5b08b-358">accountName</span><span class="sxs-lookup"><span data-stu-id="5b08b-358">accountName</span></span> | <span data-ttu-id="5b08b-359">Tillgängligt om entityType är *Användare.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="5b08b-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="5b08b-360">testUser2</span></span>
<span data-ttu-id="5b08b-361">domainName</span><span class="sxs-lookup"><span data-stu-id="5b08b-361">domainName</span></span> | <span data-ttu-id="5b08b-362">Tillgängligt om entityType är *User.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="5b08b-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="5b08b-363">europe.corp.contoso</span></span>
<span data-ttu-id="5b08b-364">userSid</span><span class="sxs-lookup"><span data-stu-id="5b08b-364">userSid</span></span> | <span data-ttu-id="5b08b-365">Tillgängligt om entityType är *User.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="5b08b-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="5b08b-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="5b08b-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="5b08b-367">aadUserId</span></span> | <span data-ttu-id="5b08b-368">Tillgängligt om entityType är *User.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="5b08b-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="5b08b-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="5b08b-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5b08b-370">userPrincipalName</span></span> | <span data-ttu-id="5b08b-371">Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="5b08b-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-372">testUser2@contoso.com</span></span>
<span data-ttu-id="5b08b-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="5b08b-373">mailboxDisplayName</span></span> | <span data-ttu-id="5b08b-374">Tillgängligt om entityType är *MailBox.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="5b08b-375">testa Användare2</span><span class="sxs-lookup"><span data-stu-id="5b08b-375">test User2</span></span>
<span data-ttu-id="5b08b-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="5b08b-376">mailboxAddress</span></span> | <span data-ttu-id="5b08b-377">Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="5b08b-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-378">testUser2@contoso.com</span></span>
<span data-ttu-id="5b08b-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="5b08b-379">clusterBy</span></span> | <span data-ttu-id="5b08b-380">Tillgängligt om entityType är *MailCluster.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="5b08b-381">Ämne; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="5b08b-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="5b08b-382">avsändare</span><span class="sxs-lookup"><span data-stu-id="5b08b-382">sender</span></span> | <span data-ttu-id="5b08b-383">Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="5b08b-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="5b08b-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="5b08b-385">mottagare</span><span class="sxs-lookup"><span data-stu-id="5b08b-385">recipient</span></span> | <span data-ttu-id="5b08b-386">Tillgängligt om entityType är *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="5b08b-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b08b-387">testUser2@contoso.com</span></span>
<span data-ttu-id="5b08b-388">ämne</span><span class="sxs-lookup"><span data-stu-id="5b08b-388">subject</span></span> | <span data-ttu-id="5b08b-389">Tillgängligt om entityType är *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="5b08b-390">\[EXTERN \] uppmärksamhet</span><span class="sxs-lookup"><span data-stu-id="5b08b-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="5b08b-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="5b08b-391">deliveryAction</span></span> | <span data-ttu-id="5b08b-392">Tillgängligt om entityType är *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="5b08b-393">Levererad</span><span class="sxs-lookup"><span data-stu-id="5b08b-393">Delivered</span></span>
<span data-ttu-id="5b08b-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="5b08b-394">securityGroupId</span></span> | <span data-ttu-id="5b08b-395">Tillgängligt om entityType är *SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="5b08b-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="5b08b-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="5b08b-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="5b08b-397">securityGroupName</span></span> | <span data-ttu-id="5b08b-398">Tillgängligt om entityType är *SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="5b08b-399">Nätverkskonfigurationsoperatorer</span><span class="sxs-lookup"><span data-stu-id="5b08b-399">Network Configuration Operators</span></span>
<span data-ttu-id="5b08b-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="5b08b-400">registryHive</span></span> | <span data-ttu-id="5b08b-401">Tillgängligt om entityType är *register.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="5b08b-402">HKEY \_ LOCAL \_ MACHINE</span><span class="sxs-lookup"><span data-stu-id="5b08b-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="5b08b-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="5b08b-403">registryKey</span></span> | <span data-ttu-id="5b08b-404">Tillgängligt om entityType är *register.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="5b08b-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="5b08b-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="5b08b-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="5b08b-406">registryValueType</span></span> | <span data-ttu-id="5b08b-407">Tillgängligt om entityType är *register.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="5b08b-408">Sträng</span><span class="sxs-lookup"><span data-stu-id="5b08b-408">String</span></span>
<span data-ttu-id="5b08b-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="5b08b-409">registryValue</span></span> | <span data-ttu-id="5b08b-410">Tillgängligt om entityType är *register.*</span><span class="sxs-lookup"><span data-stu-id="5b08b-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="5b08b-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="5b08b-411">31-00-00-00</span></span>
<span data-ttu-id="5b08b-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="5b08b-412">deviceId</span></span> | <span data-ttu-id="5b08b-413">EVENTUELLA ID:n för enheten som är relaterad till enheten.</span><span class="sxs-lookup"><span data-stu-id="5b08b-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="5b08b-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="5b08b-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="5b08b-415">Exempel</span><span class="sxs-lookup"><span data-stu-id="5b08b-415">Example</span></span>

<span data-ttu-id="5b08b-416">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="5b08b-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="5b08b-417">**Svar**</span><span class="sxs-lookup"><span data-stu-id="5b08b-417">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="5b08b-418">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5b08b-418">Related articles</span></span>

- [<span data-ttu-id="5b08b-419">Få åtkomst till API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b08b-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5b08b-420">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="5b08b-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5b08b-421">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="5b08b-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="5b08b-422">Incidentöversikt</span><span class="sxs-lookup"><span data-stu-id="5b08b-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5b08b-423">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="5b08b-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="5b08b-424">API för uppdateringshändelse</span><span class="sxs-lookup"><span data-stu-id="5b08b-424">Update incident API</span></span>](api-update-incidents.md)
