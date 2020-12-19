---
title: Lista över incident API i Microsoft 365 Defender
description: 'Lär dig hur du visar API: er i Microsoft 365 Defender'
keywords: lista, incident, incidenter, API
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719434"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="ac12d-104">Lista över incident API i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac12d-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac12d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ac12d-105">**Applies to:**</span></span>

- <span data-ttu-id="ac12d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac12d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac12d-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="ac12d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ac12d-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="ac12d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="ac12d-109">API-Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-109">API description</span></span>

<span data-ttu-id="ac12d-110">Med API: er för incidenter kan du sortera genom händelser för att skapa ett underordnat Cybersecurity-svar.</span><span class="sxs-lookup"><span data-stu-id="ac12d-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="ac12d-111">Den exponerar en mängd händelser som har flaggats i nätverket, inom det tidsintervall som du angav i din miljö bevarande princip.</span><span class="sxs-lookup"><span data-stu-id="ac12d-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="ac12d-112">De senaste incidenterna visas högst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="ac12d-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="ac12d-113">Varje händelse innehåller en matris med relaterade aviseringar och tillhör deras relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="ac12d-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="ac12d-114">API: et stöder följande **OData** -operatorer.</span><span class="sxs-lookup"><span data-stu-id="ac12d-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="ac12d-115">`$filter`i `lastUpdateTime` egenskaperna, `createdTime` , `status` , och `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="ac12d-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="ac12d-116">`$top`, med maximalt **100**</span><span class="sxs-lookup"><span data-stu-id="ac12d-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="ac12d-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="ac12d-117">Limitations</span></span>

1. <span data-ttu-id="ac12d-118">Maximal sid storlek är **100-incidenter**.</span><span class="sxs-lookup"><span data-stu-id="ac12d-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="ac12d-119">Maximal taxa för förfrågningar är **50 samtal per minut** och **1500 samtal per timme**.</span><span class="sxs-lookup"><span data-stu-id="ac12d-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="ac12d-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="ac12d-120">Permissions</span></span>

<span data-ttu-id="ac12d-121">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="ac12d-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ac12d-122">Mer information om hur du väljer behörigheter finns i [Access Microsoft 365 Defender API: er](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="ac12d-123">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="ac12d-123">Permission type</span></span> | <span data-ttu-id="ac12d-124">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="ac12d-124">Permission</span></span> | <span data-ttu-id="ac12d-125">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="ac12d-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="ac12d-126">Program</span><span class="sxs-lookup"><span data-stu-id="ac12d-126">Application</span></span> | <span data-ttu-id="ac12d-127">Incident. Read. all</span><span class="sxs-lookup"><span data-stu-id="ac12d-127">Incident.Read.All</span></span> | <span data-ttu-id="ac12d-128">Läs alla händelser</span><span class="sxs-lookup"><span data-stu-id="ac12d-128">Read all incidents</span></span>
<span data-ttu-id="ac12d-129">Program</span><span class="sxs-lookup"><span data-stu-id="ac12d-129">Application</span></span> | <span data-ttu-id="ac12d-130">Incident. ReadWrite. alla</span><span class="sxs-lookup"><span data-stu-id="ac12d-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="ac12d-131">Läsa och skriva alla händelser</span><span class="sxs-lookup"><span data-stu-id="ac12d-131">Read and write all incidents</span></span>
<span data-ttu-id="ac12d-132">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="ac12d-132">Delegated (work or school account)</span></span> | <span data-ttu-id="ac12d-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="ac12d-133">Incident.Read</span></span> | <span data-ttu-id="ac12d-134">Läs händelser</span><span class="sxs-lookup"><span data-stu-id="ac12d-134">Read incidents</span></span>
<span data-ttu-id="ac12d-135">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="ac12d-135">Delegated (work or school account)</span></span> | <span data-ttu-id="ac12d-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ac12d-136">Incident.ReadWrite</span></span> | <span data-ttu-id="ac12d-137">Läs-och skriv händelser</span><span class="sxs-lookup"><span data-stu-id="ac12d-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="ac12d-138">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="ac12d-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="ac12d-139">Användaren måste ha behörigheten Visa för händelser i portalen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="ac12d-140">Svaret innehåller endast händelser som användaren utsätts för.</span><span class="sxs-lookup"><span data-stu-id="ac12d-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="ac12d-141">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="ac12d-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="ac12d-142">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="ac12d-142">Request headers</span></span>

<span data-ttu-id="ac12d-143">Namn</span><span class="sxs-lookup"><span data-stu-id="ac12d-143">Name</span></span> | <span data-ttu-id="ac12d-144">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="ac12d-144">Type</span></span> | <span data-ttu-id="ac12d-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-145">Description</span></span>
-|-|-
<span data-ttu-id="ac12d-146">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="ac12d-146">Authorization</span></span> | <span data-ttu-id="ac12d-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="ac12d-147">String</span></span> | <span data-ttu-id="ac12d-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ac12d-148">Bearer {token}.</span></span> <span data-ttu-id="ac12d-149">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="ac12d-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="ac12d-150">Brödtext</span><span class="sxs-lookup"><span data-stu-id="ac12d-150">Request body</span></span>

<span data-ttu-id="ac12d-151">Ingen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="ac12d-152">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="ac12d-152">Response</span></span>

<span data-ttu-id="ac12d-153">Om det lyckas returnerar den här metoden `200 OK` och en lista med [incidenter](api-incident.md) i svars texten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="ac12d-154">Schema mappning</span><span class="sxs-lookup"><span data-stu-id="ac12d-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="ac12d-155">Metadata för incident</span><span class="sxs-lookup"><span data-stu-id="ac12d-155">Incident metadata</span></span>

<span data-ttu-id="ac12d-156">Fält namn</span><span class="sxs-lookup"><span data-stu-id="ac12d-156">Field name</span></span> | <span data-ttu-id="ac12d-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-157">Description</span></span> | <span data-ttu-id="ac12d-158">Exempel värde</span><span class="sxs-lookup"><span data-stu-id="ac12d-158">Example value</span></span>
-|-|-
<span data-ttu-id="ac12d-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="ac12d-159">incidentId</span></span> | <span data-ttu-id="ac12d-160">Unik identifierare som representerar incidenten</span><span class="sxs-lookup"><span data-stu-id="ac12d-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="ac12d-161">924565</span><span class="sxs-lookup"><span data-stu-id="ac12d-161">924565</span></span>
<span data-ttu-id="ac12d-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="ac12d-162">redirectIncidentId</span></span> | <span data-ttu-id="ac12d-163">Endast i händelse av att en olycka grupperas tillsammans med en annan incident, som en del av bearbetnings logiken för olyckor.</span><span class="sxs-lookup"><span data-stu-id="ac12d-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="ac12d-164">924569</span><span class="sxs-lookup"><span data-stu-id="ac12d-164">924569</span></span>
<span data-ttu-id="ac12d-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="ac12d-165">incidentName</span></span> | <span data-ttu-id="ac12d-166">Ett sträng värde är tillgängligt för alla händelser.</span><span class="sxs-lookup"><span data-stu-id="ac12d-166">String value available for every incident.</span></span> | <span data-ttu-id="ac12d-167">Utpressnings tro aktivitet</span><span class="sxs-lookup"><span data-stu-id="ac12d-167">Ransomware activity</span></span>
<span data-ttu-id="ac12d-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-168">createdTime</span></span> | <span data-ttu-id="ac12d-169">Tidpunkt då incidenten först skapades.</span><span class="sxs-lookup"><span data-stu-id="ac12d-169">Time when incident was first created.</span></span> | <span data-ttu-id="ac12d-170">2020 – 09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="ac12d-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-171">lastUpdateTime</span></span> | <span data-ttu-id="ac12d-172">Tid när händelsen senast uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="ac12d-173">Det här fältet kan användas när du ställer in parametern request för det tidsintervall som incidenter hämtas.</span><span class="sxs-lookup"><span data-stu-id="ac12d-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="ac12d-174">2020 – 09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="ac12d-175">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="ac12d-175">assignedTo</span></span> | <span data-ttu-id="ac12d-176">Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.</span><span class="sxs-lookup"><span data-stu-id="ac12d-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="ac12d-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-177">secop2@contoso.com</span></span>
<span data-ttu-id="ac12d-178">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="ac12d-178">classification</span></span> | <span data-ttu-id="ac12d-179">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-179">The specification for the incident.</span></span> <span data-ttu-id="ac12d-180">Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="ac12d-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="ac12d-181">Okänd</span><span class="sxs-lookup"><span data-stu-id="ac12d-181">Unknown</span></span>
<span data-ttu-id="ac12d-182">bedömning</span><span class="sxs-lookup"><span data-stu-id="ac12d-182">determination</span></span> | <span data-ttu-id="ac12d-183">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="ac12d-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="ac12d-184">Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *övrigt*</span><span class="sxs-lookup"><span data-stu-id="ac12d-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="ac12d-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="ac12d-185">NotAvailable</span></span>
<span data-ttu-id="ac12d-186">status</span><span class="sxs-lookup"><span data-stu-id="ac12d-186">status</span></span> | <span data-ttu-id="ac12d-187">Kategorisera incidenter (som *aktiva* eller *löst*).</span><span class="sxs-lookup"><span data-stu-id="ac12d-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="ac12d-188">Den kan hjälpa dig att organisera och hantera ditt svar på tillbud.</span><span class="sxs-lookup"><span data-stu-id="ac12d-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="ac12d-189">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ac12d-189">Active</span></span>
<span data-ttu-id="ac12d-190">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="ac12d-190">severity</span></span> | <span data-ttu-id="ac12d-191">Anger möjlig påverkan på till gångar.</span><span class="sxs-lookup"><span data-stu-id="ac12d-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="ac12d-192">Ju högre allvarlighets grad desto större effekt.</span><span class="sxs-lookup"><span data-stu-id="ac12d-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="ac12d-193">Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="ac12d-194">Något av följande värden: *information*, *Low*, \* medium och *High*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="ac12d-195">Risk</span><span class="sxs-lookup"><span data-stu-id="ac12d-195">Medium</span></span>
<span data-ttu-id="ac12d-196">taggen</span><span class="sxs-lookup"><span data-stu-id="ac12d-196">tags</span></span> | <span data-ttu-id="ac12d-197">Matris med anpassade taggar som är kopplade till en olycka, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="ac12d-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="ac12d-198">larm</span><span class="sxs-lookup"><span data-stu-id="ac12d-198">alerts</span></span> | <span data-ttu-id="ac12d-199">Matris som innehåller alla notifieringar relaterade till incidenten plus annan information, till exempel allvarlighets grad, enheter som ingick i aviseringen och källan till aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="ac12d-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="ac12d-200">\[\] (se informationen om aviserings fälten nedan)</span><span class="sxs-lookup"><span data-stu-id="ac12d-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="ac12d-201">Metadata för aviseringar</span><span class="sxs-lookup"><span data-stu-id="ac12d-201">Alerts metadata</span></span>

<span data-ttu-id="ac12d-202">Fält namn</span><span class="sxs-lookup"><span data-stu-id="ac12d-202">Field name</span></span> | <span data-ttu-id="ac12d-203">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-203">Description</span></span> | <span data-ttu-id="ac12d-204">Exempel värde</span><span class="sxs-lookup"><span data-stu-id="ac12d-204">Example value</span></span>
-|-|-
<span data-ttu-id="ac12d-205">alertId</span><span class="sxs-lookup"><span data-stu-id="ac12d-205">alertId</span></span> | <span data-ttu-id="ac12d-206">Unik identifierare som representerar aviseringen</span><span class="sxs-lookup"><span data-stu-id="ac12d-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="ac12d-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="ac12d-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="ac12d-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="ac12d-208">incidentId</span></span> | <span data-ttu-id="ac12d-209">Unik identifierare som representerar den incident som aviseringen är associerad med</span><span class="sxs-lookup"><span data-stu-id="ac12d-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="ac12d-210">924565</span><span class="sxs-lookup"><span data-stu-id="ac12d-210">924565</span></span>
<span data-ttu-id="ac12d-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="ac12d-211">serviceSource</span></span> | <span data-ttu-id="ac12d-212">Tjänsten som aviseringen härstammar från, till exempel Microsoft Defender för slut punkt, Microsoft Cloud App Security, Microsoft Defender för identitet eller Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac12d-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="ac12d-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="ac12d-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="ac12d-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-214">creationTime</span></span> | <span data-ttu-id="ac12d-215">Tid då aviseringen först skapades.</span><span class="sxs-lookup"><span data-stu-id="ac12d-215">Time when alert was first created.</span></span> | <span data-ttu-id="ac12d-216">2020 – 09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="ac12d-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-217">lastUpdatedTime</span></span> | <span data-ttu-id="ac12d-218">Tid när aviseringen senast uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="ac12d-219">2020 – 09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="ac12d-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-220">resolvedTime</span></span> | <span data-ttu-id="ac12d-221">Tid då aviseringen löstes.</span><span class="sxs-lookup"><span data-stu-id="ac12d-221">Time when alert was resolved.</span></span> | <span data-ttu-id="ac12d-222">2020 – 09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="ac12d-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="ac12d-223">firstActivity</span></span> | <span data-ttu-id="ac12d-224">Tid när aviseringen först rapporterades om att aktiviteten uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="ac12d-225">2020 – 09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="ac12d-226">titelfält</span><span class="sxs-lookup"><span data-stu-id="ac12d-226">title</span></span> | <span data-ttu-id="ac12d-227">Ett kort värde som är tillgängligt för varje varning.</span><span class="sxs-lookup"><span data-stu-id="ac12d-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="ac12d-228">Utpressnings tro aktivitet</span><span class="sxs-lookup"><span data-stu-id="ac12d-228">Ransomware activity</span></span>
<span data-ttu-id="ac12d-229">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-229">description</span></span> | <span data-ttu-id="ac12d-230">Sträng värde som beskriver varje varning.</span><span class="sxs-lookup"><span data-stu-id="ac12d-230">String value describing each alert.</span></span> | <span data-ttu-id="ac12d-231">User test user2 (testUser2@contoso.com) manipulerar 99-filer med flera tillägg som slutar med det ovanliga tillägget *Herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="ac12d-232">Det här är ett ovanligt antal fil ändringar och är ett exempel på en potentiell utpressnings tro Jan attack.</span><span class="sxs-lookup"><span data-stu-id="ac12d-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="ac12d-233">typ</span><span class="sxs-lookup"><span data-stu-id="ac12d-233">category</span></span> | <span data-ttu-id="ac12d-234">Visuell och numerisk vy av hur långt angreppet har gått under Kill-kedjan.</span><span class="sxs-lookup"><span data-stu-id="ac12d-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="ac12d-235">Justerad till [MITREn att&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="ac12d-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="ac12d-236">Påverkan</span><span class="sxs-lookup"><span data-stu-id="ac12d-236">Impact</span></span>
<span data-ttu-id="ac12d-237">status</span><span class="sxs-lookup"><span data-stu-id="ac12d-237">status</span></span> | <span data-ttu-id="ac12d-238">Kategorisera aviseringar (som *nya*, *aktiva* eller *stängda*).</span><span class="sxs-lookup"><span data-stu-id="ac12d-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="ac12d-239">Den kan hjälpa dig att organisera och hantera dina svar på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="ac12d-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="ac12d-240">Nya</span><span class="sxs-lookup"><span data-stu-id="ac12d-240">New</span></span>
<span data-ttu-id="ac12d-241">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="ac12d-241">severity</span></span> | <span data-ttu-id="ac12d-242">Anger möjlig påverkan på till gångar.</span><span class="sxs-lookup"><span data-stu-id="ac12d-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="ac12d-243">Ju högre allvarlighets grad desto större effekt.</span><span class="sxs-lookup"><span data-stu-id="ac12d-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="ac12d-244">Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="ac12d-245">Något av följande värden: *information*, *Low*, \* medium och *High*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="ac12d-246">Risk</span><span class="sxs-lookup"><span data-stu-id="ac12d-246">Medium</span></span>
<span data-ttu-id="ac12d-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="ac12d-247">investigationId</span></span> | <span data-ttu-id="ac12d-248">Det automatiska undersöknings-ID: t som utlöste den här varningen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="ac12d-249">1234</span><span class="sxs-lookup"><span data-stu-id="ac12d-249">1234</span></span>
<span data-ttu-id="ac12d-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="ac12d-250">investigationState</span></span> | <span data-ttu-id="ac12d-251">Information om utredningens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="ac12d-251">Information on the investigation's current status.</span></span> <span data-ttu-id="ac12d-252">Något av följande värden: *Okänt*, *avslutat*, *SuccessfullyRemediated*, *ofarligt*, *misslyckat*, *PartiallyRemediated*, *pågående*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *köade*, *InnerFailure*, *PreexistingAlert*, *,* *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="ac12d-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="ac12d-253">UnsupportedAlertType</span></span>
<span data-ttu-id="ac12d-254">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="ac12d-254">classification</span></span> | <span data-ttu-id="ac12d-255">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-255">The specification for the incident.</span></span> <span data-ttu-id="ac12d-256">Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive*, eller *Null*</span><span class="sxs-lookup"><span data-stu-id="ac12d-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="ac12d-257">Okänd</span><span class="sxs-lookup"><span data-stu-id="ac12d-257">Unknown</span></span>
<span data-ttu-id="ac12d-258">bedömning</span><span class="sxs-lookup"><span data-stu-id="ac12d-258">determination</span></span> | <span data-ttu-id="ac12d-259">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="ac12d-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="ac12d-260">Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* eller  *Null*</span><span class="sxs-lookup"><span data-stu-id="ac12d-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="ac12d-261">Apt</span><span class="sxs-lookup"><span data-stu-id="ac12d-261">Apt</span></span>
<span data-ttu-id="ac12d-262">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="ac12d-262">assignedTo</span></span> | <span data-ttu-id="ac12d-263">Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.</span><span class="sxs-lookup"><span data-stu-id="ac12d-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="ac12d-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-264">secop2@contoso.com</span></span>
<span data-ttu-id="ac12d-265">actorName</span><span class="sxs-lookup"><span data-stu-id="ac12d-265">actorName</span></span> | <span data-ttu-id="ac12d-266">Aktivitets gruppen, om den är kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="ac12d-267">UTTRYCKT</span><span class="sxs-lookup"><span data-stu-id="ac12d-267">BORON</span></span>
<span data-ttu-id="ac12d-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="ac12d-268">threatFamilyName</span></span> | <span data-ttu-id="ac12d-269">Hot familj som är associerad med den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="ac12d-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="ac12d-270">kan</span><span class="sxs-lookup"><span data-stu-id="ac12d-270">null</span></span>
<span data-ttu-id="ac12d-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="ac12d-271">mitreTechniques</span></span> | <span data-ttu-id="ac12d-272">Angrepps metoderna, som är justerade med [MITREn att&CK](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="ac12d-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="ac12d-273">anordningar</span><span class="sxs-lookup"><span data-stu-id="ac12d-273">devices</span></span> | <span data-ttu-id="ac12d-274">Alla enheter där aviseringar relaterade till händelsen skickades.</span><span class="sxs-lookup"><span data-stu-id="ac12d-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="ac12d-275">\[\] (se informationen om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="ac12d-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="ac12d-276">Enhets format</span><span class="sxs-lookup"><span data-stu-id="ac12d-276">Device format</span></span>

<span data-ttu-id="ac12d-277">Fält namn</span><span class="sxs-lookup"><span data-stu-id="ac12d-277">Field name</span></span> | <span data-ttu-id="ac12d-278">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-278">Description</span></span> | <span data-ttu-id="ac12d-279">Exempel värde</span><span class="sxs-lookup"><span data-stu-id="ac12d-279">Example value</span></span>
-|-|-
<span data-ttu-id="ac12d-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="ac12d-280">DeviceId</span></span> | <span data-ttu-id="ac12d-281">Enhets-ID enligt Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="ac12d-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="ac12d-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="ac12d-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="ac12d-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="ac12d-283">aadDeviceId</span></span> |  <span data-ttu-id="ac12d-284">Enhets-ID enligt [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="ac12d-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="ac12d-285">Endast tillgängligt för domänanslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="ac12d-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="ac12d-286">kan</span><span class="sxs-lookup"><span data-stu-id="ac12d-286">null</span></span>
<span data-ttu-id="ac12d-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="ac12d-287">deviceDnsName</span></span> | <span data-ttu-id="ac12d-288">Det fullt kvalificerade domän namnet för enheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="ac12d-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="ac12d-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="ac12d-290">osPlatform</span></span> | <span data-ttu-id="ac12d-291">Den OS-plattform enheten körs på.</span><span class="sxs-lookup"><span data-stu-id="ac12d-291">The OS platform the device is running.</span></span>| <span data-ttu-id="ac12d-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="ac12d-292">WindowsServer2016</span></span>
<span data-ttu-id="ac12d-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="ac12d-293">osBuild</span></span> | <span data-ttu-id="ac12d-294">Versions versionen för det OS-enheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="ac12d-295">14393</span><span class="sxs-lookup"><span data-stu-id="ac12d-295">14393</span></span>
<span data-ttu-id="ac12d-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="ac12d-296">rbacGroupName</span></span> | <span data-ttu-id="ac12d-297">Den [rollbaserad åtkomst kontroll](https://docs.microsoft.com/azure/role-based-access-control/overview) gruppen som är associerad med enheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="ac12d-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="ac12d-298">WDATP-Ring0</span></span>
<span data-ttu-id="ac12d-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="ac12d-299">firstSeen</span></span> | <span data-ttu-id="ac12d-300">Tid då enheten först visades.</span><span class="sxs-lookup"><span data-stu-id="ac12d-300">Time when device was first seen.</span></span> | <span data-ttu-id="ac12d-301">2020 – 02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="ac12d-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="ac12d-302">healthStatus</span></span> | <span data-ttu-id="ac12d-303">Enhetens hälso status.</span><span class="sxs-lookup"><span data-stu-id="ac12d-303">The health state of the device.</span></span> | <span data-ttu-id="ac12d-304">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ac12d-304">Active</span></span>
<span data-ttu-id="ac12d-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="ac12d-305">riskScore</span></span> | <span data-ttu-id="ac12d-306">Risk poängen för enheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-306">The risk score for the  device.</span></span> | <span data-ttu-id="ac12d-307">Högsta</span><span class="sxs-lookup"><span data-stu-id="ac12d-307">High</span></span>
<span data-ttu-id="ac12d-308">posterna</span><span class="sxs-lookup"><span data-stu-id="ac12d-308">entities</span></span> | <span data-ttu-id="ac12d-309">Alla enheter som har identifierats som en del av eller är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="ac12d-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="ac12d-310">\[\] (se informationen om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="ac12d-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="ac12d-311">Enhets format</span><span class="sxs-lookup"><span data-stu-id="ac12d-311">Entity Format</span></span>

<span data-ttu-id="ac12d-312">Fält namn</span><span class="sxs-lookup"><span data-stu-id="ac12d-312">Field name</span></span> | <span data-ttu-id="ac12d-313">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ac12d-313">Description</span></span> | <span data-ttu-id="ac12d-314">Exempel värde</span><span class="sxs-lookup"><span data-stu-id="ac12d-314">Example value</span></span>
-|-|-
<span data-ttu-id="ac12d-315">Angiven</span><span class="sxs-lookup"><span data-stu-id="ac12d-315">entityType</span></span> | <span data-ttu-id="ac12d-316">Enheter som har identifierats som en del av eller är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="ac12d-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="ac12d-317">Egenskaps värden är: *användare*, *IP*, *URL*, *fil*, *process*, *post låda, e*- *postmeddelande*, *kluster*, *register*</span><span class="sxs-lookup"><span data-stu-id="ac12d-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="ac12d-318">Användare</span><span class="sxs-lookup"><span data-stu-id="ac12d-318">User</span></span>
<span data-ttu-id="ac12d-319">SHA1</span><span class="sxs-lookup"><span data-stu-id="ac12d-319">sha1</span></span> | <span data-ttu-id="ac12d-320">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="ac12d-321">Fil-hash för aviseringar som är kopplade till en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="ac12d-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="ac12d-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="ac12d-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="ac12d-323">sha256</span><span class="sxs-lookup"><span data-stu-id="ac12d-323">sha256</span></span> | <span data-ttu-id="ac12d-324">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="ac12d-325">Fil-hash för aviseringar som är kopplade till en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="ac12d-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="ac12d-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="ac12d-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="ac12d-327">Datafil</span><span class="sxs-lookup"><span data-stu-id="ac12d-327">fileName</span></span> | <span data-ttu-id="ac12d-328">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="ac12d-329">Fil namnet för aviseringar som är kopplade till en fil eller process</span><span class="sxs-lookup"><span data-stu-id="ac12d-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="ac12d-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="ac12d-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="ac12d-331">Skript</span><span class="sxs-lookup"><span data-stu-id="ac12d-331">filePath</span></span> | <span data-ttu-id="ac12d-332">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="ac12d-333">Fil Sök vägen för aviseringar som är kopplade till en fil eller process</span><span class="sxs-lookup"><span data-stu-id="ac12d-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="ac12d-334">C: \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54. \ out</span><span class="sxs-lookup"><span data-stu-id="ac12d-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="ac12d-335">processId</span><span class="sxs-lookup"><span data-stu-id="ac12d-335">processId</span></span> | <span data-ttu-id="ac12d-336">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="ac12d-337">24348</span><span class="sxs-lookup"><span data-stu-id="ac12d-337">24348</span></span>
<span data-ttu-id="ac12d-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="ac12d-338">processCommandLine</span></span> | <span data-ttu-id="ac12d-339">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="ac12d-340">"Filen är klar för nedladdning \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="ac12d-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="ac12d-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-341">processCreationTime</span></span> | <span data-ttu-id="ac12d-342">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="ac12d-343">2020 – 07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="ac12d-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="ac12d-344">parentProcessId</span></span> | <span data-ttu-id="ac12d-345">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="ac12d-346">16840</span><span class="sxs-lookup"><span data-stu-id="ac12d-346">16840</span></span>
<span data-ttu-id="ac12d-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="ac12d-347">parentProcessCreationTime</span></span> | <span data-ttu-id="ac12d-348">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="ac12d-349">2020 – 07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="ac12d-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="ac12d-350">IP</span><span class="sxs-lookup"><span data-stu-id="ac12d-350">ipAddress</span></span> | <span data-ttu-id="ac12d-351">Tillgängligt om entityType är *IP*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="ac12d-352">IP-adress för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till ett skadligt nätverk*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="ac12d-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="ac12d-353">62.216.203.204</span></span>
<span data-ttu-id="ac12d-354">:</span><span class="sxs-lookup"><span data-stu-id="ac12d-354">url</span></span> | <span data-ttu-id="ac12d-355">Tillgängligt om entityType är *URL*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="ac12d-356">URL för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till en illvillig nätverks destination*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="ac12d-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="ac12d-357">down.esales360.cn</span></span>
<span data-ttu-id="ac12d-358">Konto</span><span class="sxs-lookup"><span data-stu-id="ac12d-358">accountName</span></span> | <span data-ttu-id="ac12d-359">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="ac12d-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="ac12d-360">testUser2</span></span>
<span data-ttu-id="ac12d-361">domainName</span><span class="sxs-lookup"><span data-stu-id="ac12d-361">domainName</span></span> | <span data-ttu-id="ac12d-362">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="ac12d-363">Europa. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="ac12d-363">europe.corp.contoso</span></span>
<span data-ttu-id="ac12d-364">userSid</span><span class="sxs-lookup"><span data-stu-id="ac12d-364">userSid</span></span> | <span data-ttu-id="ac12d-365">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="ac12d-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="ac12d-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="ac12d-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="ac12d-367">aadUserId</span></span> | <span data-ttu-id="ac12d-368">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="ac12d-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="ac12d-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="ac12d-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="ac12d-370">userPrincipalName</span></span> | <span data-ttu-id="ac12d-371">Tillgänglig om EntityType är  / *e*- / *postmeddelandet* med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="ac12d-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="ac12d-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-372">testUser2@contoso.com</span></span>
<span data-ttu-id="ac12d-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="ac12d-373">mailboxDisplayName</span></span> | <span data-ttu-id="ac12d-374">Tillgänglig om entityType är *post låda*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="ac12d-375">testa user2</span><span class="sxs-lookup"><span data-stu-id="ac12d-375">test User2</span></span>
<span data-ttu-id="ac12d-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="ac12d-376">mailboxAddress</span></span> | <span data-ttu-id="ac12d-377">Tillgänglig om EntityType är  / *e*- / *postmeddelandet* med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="ac12d-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="ac12d-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-378">testUser2@contoso.com</span></span>
<span data-ttu-id="ac12d-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="ac12d-379">clusterBy</span></span> | <span data-ttu-id="ac12d-380">Tillgängligt om entityType är ett  *multicluster*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="ac12d-381">Satt P2SenderDomain; Innehålls</span><span class="sxs-lookup"><span data-stu-id="ac12d-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="ac12d-382">avsändare</span><span class="sxs-lookup"><span data-stu-id="ac12d-382">sender</span></span> | <span data-ttu-id="ac12d-383">Tillgänglig om EntityType är  / *e*- / *postmeddelandet* med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="ac12d-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="ac12d-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="ac12d-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="ac12d-385">Recipient</span><span class="sxs-lookup"><span data-stu-id="ac12d-385">recipient</span></span> | <span data-ttu-id="ac12d-386">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="ac12d-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac12d-387">testUser2@contoso.com</span></span>
<span data-ttu-id="ac12d-388">satt</span><span class="sxs-lookup"><span data-stu-id="ac12d-388">subject</span></span> | <span data-ttu-id="ac12d-389">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="ac12d-390">\[EXTERN \] uppmärksamhet</span><span class="sxs-lookup"><span data-stu-id="ac12d-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="ac12d-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="ac12d-391">deliveryAction</span></span> | <span data-ttu-id="ac12d-392">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="ac12d-393">Levereras</span><span class="sxs-lookup"><span data-stu-id="ac12d-393">Delivered</span></span>
<span data-ttu-id="ac12d-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="ac12d-394">securityGroupId</span></span> | <span data-ttu-id="ac12d-395">Tillgänglig om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="ac12d-396">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="ac12d-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="ac12d-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="ac12d-397">securityGroupName</span></span> | <span data-ttu-id="ac12d-398">Tillgänglig om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="ac12d-399">Operatörer för nätverks konfiguration</span><span class="sxs-lookup"><span data-stu-id="ac12d-399">Network Configuration Operators</span></span>
<span data-ttu-id="ac12d-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="ac12d-400">registryHive</span></span> | <span data-ttu-id="ac12d-401">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="ac12d-402">lokala HKEY- \_ \_ datorer</span><span class="sxs-lookup"><span data-stu-id="ac12d-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="ac12d-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="ac12d-403">registryKey</span></span> | <span data-ttu-id="ac12d-404">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="ac12d-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="ac12d-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="ac12d-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="ac12d-406">registryValueType</span></span> | <span data-ttu-id="ac12d-407">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="ac12d-408">Sträng</span><span class="sxs-lookup"><span data-stu-id="ac12d-408">String</span></span>
<span data-ttu-id="ac12d-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="ac12d-409">registryValue</span></span> | <span data-ttu-id="ac12d-410">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="ac12d-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="ac12d-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="ac12d-411">31-00-00-00</span></span>
<span data-ttu-id="ac12d-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="ac12d-412">deviceId</span></span> | <span data-ttu-id="ac12d-413">ID, om sådant finns, för enheten som är relaterad till enheten.</span><span class="sxs-lookup"><span data-stu-id="ac12d-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="ac12d-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="ac12d-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="ac12d-415">Exempel</span><span class="sxs-lookup"><span data-stu-id="ac12d-415">Example</span></span>

<span data-ttu-id="ac12d-416">**Ställning**</span><span class="sxs-lookup"><span data-stu-id="ac12d-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="ac12d-417">**Interimssvar**</span><span class="sxs-lookup"><span data-stu-id="ac12d-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="ac12d-418">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ac12d-418">Related articles</span></span>

- [<span data-ttu-id="ac12d-419">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac12d-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ac12d-420">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="ac12d-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ac12d-421">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="ac12d-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ac12d-422">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="ac12d-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ac12d-423">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="ac12d-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="ac12d-424">Uppdatera API för incident</span><span class="sxs-lookup"><span data-stu-id="ac12d-424">Update incident API</span></span>](api-update-incidents.md)
