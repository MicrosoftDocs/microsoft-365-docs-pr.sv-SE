---
title: Api:et för listincidenter i Microsoft 365 Defender
description: Läs om hur du listar API för incidenter i Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572159"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="7ba7f-104">Api:et för listincidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba7f-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ba7f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-105">**Applies to:**</span></span>

- <span data-ttu-id="7ba7f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba7f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ba7f-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7ba7f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="7ba7f-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-109">API description</span></span>

<span data-ttu-id="7ba7f-110">Api:et för listincidenter låter dig sortera igenom incidenter för att skapa ett informerat cybersäkerhetssvar.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="7ba7f-111">Den visar en samling incidenter som har flaggats i nätverket inom det tidsintervall som du angav i principen för miljö kvarhållning.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="7ba7f-112">De senaste incidenterna visas högst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="7ba7f-113">Varje incident innehåller en matris med relaterade aviseringar och deras relaterade entiteter.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="7ba7f-114">API:et stöder följande **OData-operatorer:**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="7ba7f-115">`$filter` på `lastUpdateTime` , `createdTime` , och `status` `assignedTo` egenskaper</span><span class="sxs-lookup"><span data-stu-id="7ba7f-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="7ba7f-116">`$top`, med ett maximalt värde på **100**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="7ba7f-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="7ba7f-117">Limitations</span></span>

1. <span data-ttu-id="7ba7f-118">Maximal sidstorlek är **100 incidenter**.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="7ba7f-119">Maximal frekvens för förfrågningar är **50 samtal per minut och** **1500 samtal per timme**.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="7ba7f-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-120">Permissions</span></span>

<span data-ttu-id="7ba7f-121">En av följande behörigheter krävs för att anropa det här API:et.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7ba7f-122">Mer information om hur du väljer behörigheter finns i [Access Microsoft 365 Defender API:er](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="7ba7f-123">Typ av behörighet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-123">Permission type</span></span> | <span data-ttu-id="7ba7f-124">Behörighet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-124">Permission</span></span> | <span data-ttu-id="7ba7f-125">Namn på behörighetsvisning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="7ba7f-126">Program</span><span class="sxs-lookup"><span data-stu-id="7ba7f-126">Application</span></span> | <span data-ttu-id="7ba7f-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="7ba7f-127">Incident.Read.All</span></span> | <span data-ttu-id="7ba7f-128">Läs alla incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-128">Read all incidents</span></span>
<span data-ttu-id="7ba7f-129">Program</span><span class="sxs-lookup"><span data-stu-id="7ba7f-129">Application</span></span> | <span data-ttu-id="7ba7f-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7ba7f-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="7ba7f-131">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-131">Read and write all incidents</span></span>
<span data-ttu-id="7ba7f-132">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-132">Delegated (work or school account)</span></span> | <span data-ttu-id="7ba7f-133">Incident.Läs</span><span class="sxs-lookup"><span data-stu-id="7ba7f-133">Incident.Read</span></span> | <span data-ttu-id="7ba7f-134">Läs incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-134">Read incidents</span></span>
<span data-ttu-id="7ba7f-135">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-135">Delegated (work or school account)</span></span> | <span data-ttu-id="7ba7f-136">Incident.ReadWrite (på plats)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-136">Incident.ReadWrite</span></span> | <span data-ttu-id="7ba7f-137">Läsa och skriva incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="7ba7f-138">När du skaffar en token med användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="7ba7f-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="7ba7f-139">Användaren måste ha visningsbehörighet för incidenter i portalen.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="7ba7f-140">Svaret kommer endast att innehålla incidenter som användaren utsätts för.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="7ba7f-141">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="7ba7f-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="7ba7f-142">Begär rubriker</span><span class="sxs-lookup"><span data-stu-id="7ba7f-142">Request headers</span></span>

<span data-ttu-id="7ba7f-143">Namn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-143">Name</span></span> | <span data-ttu-id="7ba7f-144">Typ</span><span class="sxs-lookup"><span data-stu-id="7ba7f-144">Type</span></span> | <span data-ttu-id="7ba7f-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-145">Description</span></span>
-|-|-
<span data-ttu-id="7ba7f-146">tillstånd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-146">Authorization</span></span> | <span data-ttu-id="7ba7f-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ba7f-147">String</span></span> | <span data-ttu-id="7ba7f-148">Bärare {token}.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-148">Bearer {token}.</span></span> <span data-ttu-id="7ba7f-149">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="7ba7f-150">Begär brödtext</span><span class="sxs-lookup"><span data-stu-id="7ba7f-150">Request body</span></span>

<span data-ttu-id="7ba7f-151">ingen.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="7ba7f-152">svar</span><span class="sxs-lookup"><span data-stu-id="7ba7f-152">Response</span></span>

<span data-ttu-id="7ba7f-153">Om den här metoden lyckas returneras `200 OK` den och en lista över incidenter [i](api-incident.md) svarstexten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="7ba7f-154">Schemamappning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="7ba7f-155">Metadata för incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-155">Incident metadata</span></span>

<span data-ttu-id="7ba7f-156">fältnamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-156">Field name</span></span> | <span data-ttu-id="7ba7f-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-157">Description</span></span> | <span data-ttu-id="7ba7f-158">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="7ba7f-158">Example value</span></span>
-|-|-
<span data-ttu-id="7ba7f-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-159">incidentId</span></span> | <span data-ttu-id="7ba7f-160">Unik identifierare som representerar incidenten</span><span class="sxs-lookup"><span data-stu-id="7ba7f-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="7ba7f-161">924565</span><span class="sxs-lookup"><span data-stu-id="7ba7f-161">924565</span></span>
<span data-ttu-id="7ba7f-162">omdirigeraIncidentId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-162">redirectIncidentId</span></span> | <span data-ttu-id="7ba7f-163">Endast ifyllt om en incident grupperas tillsammans med en annan incident, som en del av incident bearbetnings logiken.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="7ba7f-164">924569</span><span class="sxs-lookup"><span data-stu-id="7ba7f-164">924569</span></span>
<span data-ttu-id="7ba7f-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-165">incidentName</span></span> | <span data-ttu-id="7ba7f-166">Strängvärde tillgängligt för varje incident.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-166">String value available for every incident.</span></span> | <span data-ttu-id="7ba7f-167">Ransomware-aktivitet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-167">Ransomware activity</span></span>
<span data-ttu-id="7ba7f-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-168">createdTime</span></span> | <span data-ttu-id="7ba7f-169">Tid då incidenten först skapades.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-169">Time when incident was first created.</span></span> | <span data-ttu-id="7ba7f-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="7ba7f-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-171">lastUpdateTime</span></span> | <span data-ttu-id="7ba7f-172">Tid då incidenten senast uppdaterades på backend.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="7ba7f-173">Det här fältet kan användas när du anger parametern för begäran för det tidsintervall som incidenter hämtas.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="7ba7f-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="7ba7f-175">tilldeladTill</span><span class="sxs-lookup"><span data-stu-id="7ba7f-175">assignedTo</span></span> | <span data-ttu-id="7ba7f-176">Ägare till incidenten, eller *null* om ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="7ba7f-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-177">secop2@contoso.com</span></span>
<span data-ttu-id="7ba7f-178">klassificering</span><span class="sxs-lookup"><span data-stu-id="7ba7f-178">classification</span></span> | <span data-ttu-id="7ba7f-179">Specifikationen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-179">The specification for the incident.</span></span> <span data-ttu-id="7ba7f-180">Egenskapsvärdena är: *Okänd*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="7ba7f-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="7ba7f-181">Okänd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-181">Unknown</span></span>
<span data-ttu-id="7ba7f-182">beslutsamhet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-182">determination</span></span> | <span data-ttu-id="7ba7f-183">Anger bestämningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="7ba7f-184">Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="7ba7f-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="7ba7f-185">Intetillgänglig</span><span class="sxs-lookup"><span data-stu-id="7ba7f-185">NotAvailable</span></span>
<span data-ttu-id="7ba7f-186">status</span><span class="sxs-lookup"><span data-stu-id="7ba7f-186">status</span></span> | <span data-ttu-id="7ba7f-187">Kategorisera incidenter (som aktiva *eller* *lösta*).</span><span class="sxs-lookup"><span data-stu-id="7ba7f-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="7ba7f-188">Det kan hjälpa dig att organisera och hantera ditt svar på incidenter.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="7ba7f-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="7ba7f-189">Active</span></span>
<span data-ttu-id="7ba7f-190">stränghet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-190">severity</span></span> | <span data-ttu-id="7ba7f-191">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="7ba7f-192">Ju högre svårighetsgrad desto större blir effekten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="7ba7f-193">Vanligtvis kräver objekt med högre allvarlighetsgrad den mest omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="7ba7f-194">Ett av följande värden: *Information ,* *Låg*, \*Medel och *Hög*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="7ba7f-195">Medel</span><span class="sxs-lookup"><span data-stu-id="7ba7f-195">Medium</span></span>
<span data-ttu-id="7ba7f-196">Taggar</span><span class="sxs-lookup"><span data-stu-id="7ba7f-196">tags</span></span> | <span data-ttu-id="7ba7f-197">Matris med anpassade taggar som är associerade med en incident, till exempel för att flagga en grupp incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="7ba7f-198">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7ba7f-198">comments</span></span> | <span data-ttu-id="7ba7f-199">Matris med kommentarer som skapats av secops när incidenten hanterades, till exempel ytterligare information om klassificeringsvalet.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="7ba7f-200">Varningar</span><span class="sxs-lookup"><span data-stu-id="7ba7f-200">alerts</span></span> | <span data-ttu-id="7ba7f-201">Matris som innehåller alla aviseringar relaterade till incidenten, plus annan information, till exempel allvarlighetsgrad, entiteter som var involverade i aviseringen och källan till aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="7ba7f-202">\[\] (se detaljer om varningsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="7ba7f-203">Aviseringar metadata</span><span class="sxs-lookup"><span data-stu-id="7ba7f-203">Alerts metadata</span></span>

<span data-ttu-id="7ba7f-204">fältnamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-204">Field name</span></span> | <span data-ttu-id="7ba7f-205">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-205">Description</span></span> | <span data-ttu-id="7ba7f-206">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="7ba7f-206">Example value</span></span>
-|-|-
<span data-ttu-id="7ba7f-207">alertId (på-)alertId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-207">alertId</span></span> | <span data-ttu-id="7ba7f-208">Unik identifierare som representerar aviseringen</span><span class="sxs-lookup"><span data-stu-id="7ba7f-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="7ba7f-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="7ba7f-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="7ba7f-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-210">incidentId</span></span> | <span data-ttu-id="7ba7f-211">Unik identifierare som representerar incidenten som aviseringen är associerad med</span><span class="sxs-lookup"><span data-stu-id="7ba7f-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="7ba7f-212">924565</span><span class="sxs-lookup"><span data-stu-id="7ba7f-212">924565</span></span>
<span data-ttu-id="7ba7f-213">tjänstKälla</span><span class="sxs-lookup"><span data-stu-id="7ba7f-213">serviceSource</span></span> | <span data-ttu-id="7ba7f-214">Tjänst som aviseringen kommer från, till exempel Microsoft Defender för Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity eller Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="7ba7f-215">MicrosoftCloudAppSäkerhet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="7ba7f-216">skapaTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-216">creationTime</span></span> | <span data-ttu-id="7ba7f-217">Tid då aviseringen först skapades.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-217">Time when alert was first created.</span></span> | <span data-ttu-id="7ba7f-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="7ba7f-219">senasteUppdateradeTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-219">lastUpdatedTime</span></span> | <span data-ttu-id="7ba7f-220">Tid då aviseringen senast uppdaterades i backend.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="7ba7f-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="7ba7f-222">löstTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-222">resolvedTime</span></span> | <span data-ttu-id="7ba7f-223">Tid då aviseringen löstes.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-223">Time when alert was resolved.</span></span> | <span data-ttu-id="7ba7f-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="7ba7f-225">förstaAktivitet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-225">firstActivity</span></span> | <span data-ttu-id="7ba7f-226">Tid då aviseringen först rapporterade att aktiviteten uppdaterades i backend.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="7ba7f-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="7ba7f-228">titel</span><span class="sxs-lookup"><span data-stu-id="7ba7f-228">title</span></span> | <span data-ttu-id="7ba7f-229">Kort identifiering av strängvärde som är tillgängligt för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="7ba7f-230">Ransomware-aktivitet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-230">Ransomware activity</span></span>
<span data-ttu-id="7ba7f-231">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-231">description</span></span> | <span data-ttu-id="7ba7f-232">Strängvärde som beskriver varje avisering.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-232">String value describing each alert.</span></span> | <span data-ttu-id="7ba7f-233">Användaren Test User2 (testUser2@contoso.com) manipulerade 99 filer med flera tillägg som slutade med den ovanliga *förlängningen herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="7ba7f-234">Detta är ett ovanligt antal filmanipulationer och tyder på en potentiell ransomware-attack.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="7ba7f-235">kategori</span><span class="sxs-lookup"><span data-stu-id="7ba7f-235">category</span></span> | <span data-ttu-id="7ba7f-236">Visuell och numerisk bild av hur långt attacken har kommit längs dödskedjan.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="7ba7f-237">Anpassad till [MITRE ATT&CK™ ramverk .](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="7ba7f-238">Påverkan</span><span class="sxs-lookup"><span data-stu-id="7ba7f-238">Impact</span></span>
<span data-ttu-id="7ba7f-239">status</span><span class="sxs-lookup"><span data-stu-id="7ba7f-239">status</span></span> | <span data-ttu-id="7ba7f-240">Kategorisera aviseringar (som *nya,* aktiva *eller* *lösta*).</span><span class="sxs-lookup"><span data-stu-id="7ba7f-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="7ba7f-241">Det kan hjälpa dig att organisera och hantera ditt svar på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="7ba7f-242">Ny</span><span class="sxs-lookup"><span data-stu-id="7ba7f-242">New</span></span>
<span data-ttu-id="7ba7f-243">stränghet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-243">severity</span></span> | <span data-ttu-id="7ba7f-244">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="7ba7f-245">Ju högre svårighetsgrad desto större blir effekten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="7ba7f-246">Vanligtvis kräver objekt med högre allvarlighetsgrad den mest omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="7ba7f-247">Ett av följande värden: *Information ,* *Låg*, \*Medel och *Hög*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="7ba7f-248">Medel</span><span class="sxs-lookup"><span data-stu-id="7ba7f-248">Medium</span></span>
<span data-ttu-id="7ba7f-249">utredningId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-249">investigationId</span></span> | <span data-ttu-id="7ba7f-250">Det automatiska undersöknings-ID:t som utlöses av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="7ba7f-251">1234</span><span class="sxs-lookup"><span data-stu-id="7ba7f-251">1234</span></span>
<span data-ttu-id="7ba7f-252">undersökningState</span><span class="sxs-lookup"><span data-stu-id="7ba7f-252">investigationState</span></span> | <span data-ttu-id="7ba7f-253">Information om utredningens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-253">Information on the investigation's current status.</span></span> <span data-ttu-id="7ba7f-254">Något av följande värden: *Okänd*, *Avslutad*, *FramgångsriktRemediated*, *Benign*, *Misslyckades*, *DelvisRemediated*, *Kör*, *PendingApproval*, *PendingResource*, *Delvisinvesterad*, *AvslutadByUser*, *TerminatedBySystem*, *Köad*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="7ba7f-255">AlertType som inte stöds</span><span class="sxs-lookup"><span data-stu-id="7ba7f-255">UnsupportedAlertType</span></span>
<span data-ttu-id="7ba7f-256">klassificering</span><span class="sxs-lookup"><span data-stu-id="7ba7f-256">classification</span></span> | <span data-ttu-id="7ba7f-257">Specifikationen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-257">The specification for the incident.</span></span> <span data-ttu-id="7ba7f-258">Egenskapsvärdena är: *Okänd*, *FalsePositive*, *TruePositive* eller *null*</span><span class="sxs-lookup"><span data-stu-id="7ba7f-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="7ba7f-259">Okänd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-259">Unknown</span></span>
<span data-ttu-id="7ba7f-260">beslutsamhet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-260">determination</span></span> | <span data-ttu-id="7ba7f-261">Anger bestämningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="7ba7f-262">Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span><span class="sxs-lookup"><span data-stu-id="7ba7f-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="7ba7f-263">Apt.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-263">Apt</span></span>
<span data-ttu-id="7ba7f-264">tilldeladTill</span><span class="sxs-lookup"><span data-stu-id="7ba7f-264">assignedTo</span></span> | <span data-ttu-id="7ba7f-265">Ägare till incidenten, eller *null* om ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="7ba7f-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-266">secop2@contoso.com</span></span>
<span data-ttu-id="7ba7f-267">skådespelareName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-267">actorName</span></span> | <span data-ttu-id="7ba7f-268">Aktivitetsgruppen, om sådan finns, är associerad med den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="7ba7f-269">bor</span><span class="sxs-lookup"><span data-stu-id="7ba7f-269">BORON</span></span>
<span data-ttu-id="7ba7f-270">hotFamilyName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-270">threatFamilyName</span></span> | <span data-ttu-id="7ba7f-271">Hotfamilj som är associerad med den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="7ba7f-272">noll</span><span class="sxs-lookup"><span data-stu-id="7ba7f-272">null</span></span>
<span data-ttu-id="7ba7f-273">mitreTeknik</span><span class="sxs-lookup"><span data-stu-id="7ba7f-273">mitreTechniques</span></span> | <span data-ttu-id="7ba7f-274">Attackteknikerna, i linje med [MITRE ATT&CK](https://attack.mitre.org/)™ ramverk.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="7ba7f-275">Enheter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-275">devices</span></span> | <span data-ttu-id="7ba7f-276">Alla enheter där aviseringar relaterade till incidenten skickades.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="7ba7f-277">\[\] (se information om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="7ba7f-278">Enhetsformat</span><span class="sxs-lookup"><span data-stu-id="7ba7f-278">Device format</span></span>

<span data-ttu-id="7ba7f-279">fältnamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-279">Field name</span></span> | <span data-ttu-id="7ba7f-280">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-280">Description</span></span> | <span data-ttu-id="7ba7f-281">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="7ba7f-281">Example value</span></span>
-|-|-
<span data-ttu-id="7ba7f-282">DeviceId (på alla)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-282">DeviceId</span></span> | <span data-ttu-id="7ba7f-283">Enhets-ID:t som anges i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="7ba7f-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="7ba7f-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="7ba7f-285">aadDeviceId (på 1997)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-285">aadDeviceId</span></span> |  <span data-ttu-id="7ba7f-286">Enhets-ID:t enligt [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="7ba7f-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="7ba7f-287">Endast tillgängligt för domänakade enheter.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="7ba7f-288">noll</span><span class="sxs-lookup"><span data-stu-id="7ba7f-288">null</span></span>
<span data-ttu-id="7ba7f-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-289">deviceDnsName</span></span> | <span data-ttu-id="7ba7f-290">Enhetens fullständigt kvalificerade domännamn.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="7ba7f-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="7ba7f-292">osPlatform (på något sätt)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-292">osPlatform</span></span> | <span data-ttu-id="7ba7f-293">OS-plattformen som enheten kör.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-293">The OS platform the device is running.</span></span>| <span data-ttu-id="7ba7f-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="7ba7f-294">WindowsServer2016</span></span>
<span data-ttu-id="7ba7f-295">osByggd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-295">osBuild</span></span> | <span data-ttu-id="7ba7f-296">Byggversionen för operativsystemet som enheten kör.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="7ba7f-297">14393</span><span class="sxs-lookup"><span data-stu-id="7ba7f-297">14393</span></span>
<span data-ttu-id="7ba7f-298">rbacGroupName (på)rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-298">rbacGroupName</span></span> | <span data-ttu-id="7ba7f-299">Den [rollbaserade åtkomstkontrollgruppen](/azure/role-based-access-control/overview) (RBAC) som är associerad med enheten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="7ba7f-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="7ba7f-300">WDATP-Ring0</span></span>
<span data-ttu-id="7ba7f-301">förstSeen</span><span class="sxs-lookup"><span data-stu-id="7ba7f-301">firstSeen</span></span> | <span data-ttu-id="7ba7f-302">Tid då enheten först sågs.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-302">Time when device was first seen.</span></span> | <span data-ttu-id="7ba7f-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="7ba7f-304">hälsaStatus</span><span class="sxs-lookup"><span data-stu-id="7ba7f-304">healthStatus</span></span> | <span data-ttu-id="7ba7f-305">Enhetens hälsotillstånd.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-305">The health state of the device.</span></span> | <span data-ttu-id="7ba7f-306">Aktiv</span><span class="sxs-lookup"><span data-stu-id="7ba7f-306">Active</span></span>
<span data-ttu-id="7ba7f-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="7ba7f-307">riskScore</span></span> | <span data-ttu-id="7ba7f-308">Risk poängen för enheten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-308">The risk score for the  device.</span></span> | <span data-ttu-id="7ba7f-309">Högsta</span><span class="sxs-lookup"><span data-stu-id="7ba7f-309">High</span></span>
<span data-ttu-id="7ba7f-310">enheter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-310">entities</span></span> | <span data-ttu-id="7ba7f-311">Alla entiteter som har identifierats som en del av eller relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="7ba7f-312">\[\] (se information om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="7ba7f-313">Entitetsformat</span><span class="sxs-lookup"><span data-stu-id="7ba7f-313">Entity Format</span></span>

<span data-ttu-id="7ba7f-314">fältnamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-314">Field name</span></span> | <span data-ttu-id="7ba7f-315">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ba7f-315">Description</span></span> | <span data-ttu-id="7ba7f-316">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="7ba7f-316">Example value</span></span>
-|-|-
<span data-ttu-id="7ba7f-317">entityType (på)entitet</span><span class="sxs-lookup"><span data-stu-id="7ba7f-317">entityType</span></span> | <span data-ttu-id="7ba7f-318">Entiteter som har identifierats som en del av eller relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="7ba7f-319">Egenskapsvärdena är: *Användare*, *Ip*, *Url*, *Fil*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Register*</span><span class="sxs-lookup"><span data-stu-id="7ba7f-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="7ba7f-320">Användare</span><span class="sxs-lookup"><span data-stu-id="7ba7f-320">User</span></span>
<span data-ttu-id="7ba7f-321">sha1 (sha1)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-321">sha1</span></span> | <span data-ttu-id="7ba7f-322">Tillgänglig om entityType är *fil*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="7ba7f-323">Filhhhh för aviseringar som är associerade med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="7ba7f-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="7ba7f-325">sha256 (på 256)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-325">sha256</span></span> | <span data-ttu-id="7ba7f-326">Tillgänglig om entityType är *fil*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="7ba7f-327">Filhhhh för aviseringar som är associerade med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="7ba7f-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="7ba7f-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="7ba7f-329">filnamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-329">fileName</span></span> | <span data-ttu-id="7ba7f-330">Tillgänglig om entityType är *fil*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="7ba7f-331">Filnamnet för aviseringar som är associerade med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="7ba7f-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="7ba7f-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="7ba7f-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="7ba7f-333">filePath (på 100</span><span class="sxs-lookup"><span data-stu-id="7ba7f-333">filePath</span></span> | <span data-ttu-id="7ba7f-334">Tillgänglig om entityType är *fil*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="7ba7f-335">Filsökvägen för aviseringar som är associerade med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="7ba7f-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="7ba7f-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="7ba7f-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="7ba7f-337">processId (på alla)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-337">processId</span></span> | <span data-ttu-id="7ba7f-338">Tillgänglig om entityType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="7ba7f-339">24348</span><span class="sxs-lookup"><span data-stu-id="7ba7f-339">24348</span></span>
<span data-ttu-id="7ba7f-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="7ba7f-340">processCommandLine</span></span> | <span data-ttu-id="7ba7f-341">Tillgänglig om entityType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="7ba7f-342">"Din fil är redo att laddas \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="7ba7f-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="7ba7f-343">processSkapaTid</span><span class="sxs-lookup"><span data-stu-id="7ba7f-343">processCreationTime</span></span> | <span data-ttu-id="7ba7f-344">Tillgänglig om entityType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="7ba7f-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="7ba7f-346">överordnadProcessId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-346">parentProcessId</span></span> | <span data-ttu-id="7ba7f-347">Tillgänglig om entityType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="7ba7f-348">16840</span><span class="sxs-lookup"><span data-stu-id="7ba7f-348">16840</span></span>
<span data-ttu-id="7ba7f-349">överordnadProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="7ba7f-349">parentProcessCreationTime</span></span> | <span data-ttu-id="7ba7f-350">Tillgänglig om entityType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="7ba7f-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="7ba7f-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="7ba7f-352">ipAddress (på 5000)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-352">ipAddress</span></span> | <span data-ttu-id="7ba7f-353">Tillgänglig om entityType är *Ip*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="7ba7f-354">IP-adress för aviseringar som är associerade med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksmål*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="7ba7f-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="7ba7f-355">62.216.203.204</span></span>
<span data-ttu-id="7ba7f-356">URL</span><span class="sxs-lookup"><span data-stu-id="7ba7f-356">url</span></span> | <span data-ttu-id="7ba7f-357">Tillgänglig om entityType är *Url*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="7ba7f-358">Url för aviseringar som är associerade med nätverkshändelser, till exempel *Kommunikation till ett skadligt nätverksmål*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="7ba7f-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-359">down.esales360.cn</span></span>
<span data-ttu-id="7ba7f-360">kontoNamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-360">accountName</span></span> | <span data-ttu-id="7ba7f-361">Tillgänglig om entityType är *användare*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="7ba7f-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="7ba7f-362">testUser2</span></span>
<span data-ttu-id="7ba7f-363">domänNamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-363">domainName</span></span> | <span data-ttu-id="7ba7f-364">Tillgänglig om entityType är *användare*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="7ba7f-365">europa.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="7ba7f-365">europe.corp.contoso</span></span>
<span data-ttu-id="7ba7f-366">userSid</span><span class="sxs-lookup"><span data-stu-id="7ba7f-366">userSid</span></span> | <span data-ttu-id="7ba7f-367">Tillgänglig om entityType är *användare*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="7ba7f-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="7ba7f-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="7ba7f-369">aadUserId (på alla)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-369">aadUserId</span></span> | <span data-ttu-id="7ba7f-370">Tillgänglig om entityType är *användare*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="7ba7f-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="7ba7f-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="7ba7f-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-372">userPrincipalName</span></span> | <span data-ttu-id="7ba7f-373">Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="7ba7f-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-374">testUser2@contoso.com</span></span>
<span data-ttu-id="7ba7f-375">postlådaDisplayName</span><span class="sxs-lookup"><span data-stu-id="7ba7f-375">mailboxDisplayName</span></span> | <span data-ttu-id="7ba7f-376">Tillgänglig om entityType är *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="7ba7f-377">testa användare2</span><span class="sxs-lookup"><span data-stu-id="7ba7f-377">test User2</span></span>
<span data-ttu-id="7ba7f-378">brevlådaAdress</span><span class="sxs-lookup"><span data-stu-id="7ba7f-378">mailboxAddress</span></span> | <span data-ttu-id="7ba7f-379">Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="7ba7f-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-380">testUser2@contoso.com</span></span>
<span data-ttu-id="7ba7f-381">klusterBy</span><span class="sxs-lookup"><span data-stu-id="7ba7f-381">clusterBy</span></span> | <span data-ttu-id="7ba7f-382">Tillgänglig om entityType är  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="7ba7f-383">Angående; P2SenderDomain; ContentType (på 800</span><span class="sxs-lookup"><span data-stu-id="7ba7f-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="7ba7f-384">avsändare</span><span class="sxs-lookup"><span data-stu-id="7ba7f-384">sender</span></span> | <span data-ttu-id="7ba7f-385">Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="7ba7f-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="7ba7f-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="7ba7f-387">mottagare</span><span class="sxs-lookup"><span data-stu-id="7ba7f-387">recipient</span></span> | <span data-ttu-id="7ba7f-388">Tillgängligt om entityType är *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="7ba7f-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7ba7f-389">testUser2@contoso.com</span></span>
<span data-ttu-id="7ba7f-390">subjekt</span><span class="sxs-lookup"><span data-stu-id="7ba7f-390">subject</span></span> | <span data-ttu-id="7ba7f-391">Tillgängligt om entityType är *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="7ba7f-392">\[EXTERN \] UPPMÄRKSAMHET</span><span class="sxs-lookup"><span data-stu-id="7ba7f-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="7ba7f-393">leveransÅtgärder</span><span class="sxs-lookup"><span data-stu-id="7ba7f-393">deliveryAction</span></span> | <span data-ttu-id="7ba7f-394">Tillgängligt om entityType är *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="7ba7f-395">Levereras</span><span class="sxs-lookup"><span data-stu-id="7ba7f-395">Delivered</span></span>
<span data-ttu-id="7ba7f-396">säkerhetGroupId</span><span class="sxs-lookup"><span data-stu-id="7ba7f-396">securityGroupId</span></span> | <span data-ttu-id="7ba7f-397">Tillgängligt om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="7ba7f-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="7ba7f-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="7ba7f-399">säkerhetsgruppNamn</span><span class="sxs-lookup"><span data-stu-id="7ba7f-399">securityGroupName</span></span> | <span data-ttu-id="7ba7f-400">Tillgängligt om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="7ba7f-401">Operatörer av nätverkskonfiguration</span><span class="sxs-lookup"><span data-stu-id="7ba7f-401">Network Configuration Operators</span></span>
<span data-ttu-id="7ba7f-402">registryHive (registretHive)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-402">registryHive</span></span> | <span data-ttu-id="7ba7f-403">Tillgänglig om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="7ba7f-404">HKEY \_ LOKAL \_ MASKIN</span><span class="sxs-lookup"><span data-stu-id="7ba7f-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="7ba7f-405">registryKey (registernyckel)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-405">registryKey</span></span> | <span data-ttu-id="7ba7f-406">Tillgänglig om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="7ba7f-407">PROGRAMVARA\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="7ba7f-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="7ba7f-408">registerValueType</span><span class="sxs-lookup"><span data-stu-id="7ba7f-408">registryValueType</span></span> | <span data-ttu-id="7ba7f-409">Tillgänglig om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="7ba7f-410">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ba7f-410">String</span></span>
<span data-ttu-id="7ba7f-411">registerValuta</span><span class="sxs-lookup"><span data-stu-id="7ba7f-411">registryValue</span></span> | <span data-ttu-id="7ba7f-412">Tillgänglig om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="7ba7f-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="7ba7f-413">31-00-00-00</span></span>
<span data-ttu-id="7ba7f-414">deviceId (på 100</span><span class="sxs-lookup"><span data-stu-id="7ba7f-414">deviceId</span></span> | <span data-ttu-id="7ba7f-415">ID:t, om det finns något, för den enhet som är relaterad till entiteten.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="7ba7f-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="7ba7f-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="7ba7f-417">Exempel</span><span class="sxs-lookup"><span data-stu-id="7ba7f-417">Example</span></span>

<span data-ttu-id="7ba7f-418">**begäran**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="7ba7f-419">**svar**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-419">**Response**</span></span>

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

## <a name="related-articles"></a><span data-ttu-id="7ba7f-420">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7ba7f-420">Related articles</span></span>

- [<span data-ttu-id="7ba7f-421">Komma åt Microsoft 365 Defender API:erna</span><span class="sxs-lookup"><span data-stu-id="7ba7f-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7ba7f-422">Lär dig mer om API-gränser och licensiering</span><span class="sxs-lookup"><span data-stu-id="7ba7f-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="7ba7f-423">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="7ba7f-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="7ba7f-424">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="7ba7f-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7ba7f-425">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="7ba7f-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="7ba7f-426">Uppdatera incident-API</span><span class="sxs-lookup"><span data-stu-id="7ba7f-426">Update incident API</span></span>](api-update-incidents.md)
