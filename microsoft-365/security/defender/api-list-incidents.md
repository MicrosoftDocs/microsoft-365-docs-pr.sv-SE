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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4488a552475121adc4a439106bc0bf0d97cb509a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070081"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="96c79-104">API för listincidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96c79-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="96c79-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="96c79-105">**Applies to:**</span></span>

- <span data-ttu-id="96c79-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96c79-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96c79-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="96c79-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="96c79-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="96c79-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="96c79-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-109">API description</span></span>

<span data-ttu-id="96c79-110">Med API:t för listincidenter kan du sortera incidenter för att skapa en informerad cybersäkerhetssvar.</span><span class="sxs-lookup"><span data-stu-id="96c79-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="96c79-111">Här visas en samling incidenter som har flaggats i nätverket, inom det angivna intervallet i din miljöbevarandeprincip.</span><span class="sxs-lookup"><span data-stu-id="96c79-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="96c79-112">De senaste incidenterna visas högst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="96c79-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="96c79-113">Varje incident innehåller en matris med relaterade aviseringar och deras relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="96c79-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="96c79-114">API:t stöder följande **OData-operatorer:**</span><span class="sxs-lookup"><span data-stu-id="96c79-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="96c79-115">`$filter` i `lastUpdateTime` , `createdTime` `status` , och `assignedTo` egenskaper</span><span class="sxs-lookup"><span data-stu-id="96c79-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="96c79-116">`$top`, med maxvärdet **100**</span><span class="sxs-lookup"><span data-stu-id="96c79-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="96c79-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="96c79-117">Limitations</span></span>

1. <span data-ttu-id="96c79-118">Maximal sidstorlek är **100 ärenden.**</span><span class="sxs-lookup"><span data-stu-id="96c79-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="96c79-119">Max hastigheten för förfrågningar är **50 samtal per minut** och **1 500 samtal per timme.**</span><span class="sxs-lookup"><span data-stu-id="96c79-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="96c79-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="96c79-120">Permissions</span></span>

<span data-ttu-id="96c79-121">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="96c79-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="96c79-122">Mer information, inklusive hur du väljer behörigheter, finns i [Access-API:er för Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="96c79-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="96c79-123">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="96c79-123">Permission type</span></span> | <span data-ttu-id="96c79-124">Behörighet</span><span class="sxs-lookup"><span data-stu-id="96c79-124">Permission</span></span> | <span data-ttu-id="96c79-125">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="96c79-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="96c79-126">Program</span><span class="sxs-lookup"><span data-stu-id="96c79-126">Application</span></span> | <span data-ttu-id="96c79-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="96c79-127">Incident.Read.All</span></span> | <span data-ttu-id="96c79-128">Läs alla ärenden</span><span class="sxs-lookup"><span data-stu-id="96c79-128">Read all incidents</span></span>
<span data-ttu-id="96c79-129">Program</span><span class="sxs-lookup"><span data-stu-id="96c79-129">Application</span></span> | <span data-ttu-id="96c79-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="96c79-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="96c79-131">Läsa och skriva alla incidenter</span><span class="sxs-lookup"><span data-stu-id="96c79-131">Read and write all incidents</span></span>
<span data-ttu-id="96c79-132">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="96c79-132">Delegated (work or school account)</span></span> | <span data-ttu-id="96c79-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="96c79-133">Incident.Read</span></span> | <span data-ttu-id="96c79-134">Läsa ärenden</span><span class="sxs-lookup"><span data-stu-id="96c79-134">Read incidents</span></span>
<span data-ttu-id="96c79-135">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="96c79-135">Delegated (work or school account)</span></span> | <span data-ttu-id="96c79-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="96c79-136">Incident.ReadWrite</span></span> | <span data-ttu-id="96c79-137">Läs- och skrivincidenter</span><span class="sxs-lookup"><span data-stu-id="96c79-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="96c79-138">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="96c79-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="96c79-139">Användaren måste ha visningsbehörighet för incidenter i portalen.</span><span class="sxs-lookup"><span data-stu-id="96c79-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="96c79-140">Svaret inkluderar endast incidenter som användaren exponeras för.</span><span class="sxs-lookup"><span data-stu-id="96c79-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="96c79-141">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="96c79-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="96c79-142">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="96c79-142">Request headers</span></span>

<span data-ttu-id="96c79-143">Namn</span><span class="sxs-lookup"><span data-stu-id="96c79-143">Name</span></span> | <span data-ttu-id="96c79-144">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="96c79-144">Type</span></span> | <span data-ttu-id="96c79-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-145">Description</span></span>
-|-|-
<span data-ttu-id="96c79-146">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="96c79-146">Authorization</span></span> | <span data-ttu-id="96c79-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="96c79-147">String</span></span> | <span data-ttu-id="96c79-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="96c79-148">Bearer {token}.</span></span> <span data-ttu-id="96c79-149">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="96c79-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="96c79-150">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="96c79-150">Request body</span></span>

<span data-ttu-id="96c79-151">Ingen.</span><span class="sxs-lookup"><span data-stu-id="96c79-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="96c79-152">Svar</span><span class="sxs-lookup"><span data-stu-id="96c79-152">Response</span></span>

<span data-ttu-id="96c79-153">Om det lyckas returnerar den här `200 OK` metoden och en lista över [incidenter](api-incident.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="96c79-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="96c79-154">Schemamappning</span><span class="sxs-lookup"><span data-stu-id="96c79-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="96c79-155">Incidentmetadata</span><span class="sxs-lookup"><span data-stu-id="96c79-155">Incident metadata</span></span>

<span data-ttu-id="96c79-156">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="96c79-156">Field name</span></span> | <span data-ttu-id="96c79-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-157">Description</span></span> | <span data-ttu-id="96c79-158">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="96c79-158">Example value</span></span>
-|-|-
<span data-ttu-id="96c79-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="96c79-159">incidentId</span></span> | <span data-ttu-id="96c79-160">Unikt ID som representerar incidenten</span><span class="sxs-lookup"><span data-stu-id="96c79-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="96c79-161">924565</span><span class="sxs-lookup"><span data-stu-id="96c79-161">924565</span></span>
<span data-ttu-id="96c79-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="96c79-162">redirectIncidentId</span></span> | <span data-ttu-id="96c79-163">Fylls bara i om en händelse grupperas tillsammans med en annan incident, som en del av logiken för incidentbearbetning.</span><span class="sxs-lookup"><span data-stu-id="96c79-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="96c79-164">924569</span><span class="sxs-lookup"><span data-stu-id="96c79-164">924569</span></span>
<span data-ttu-id="96c79-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="96c79-165">incidentName</span></span> | <span data-ttu-id="96c79-166">Tillgängliga strängvärden för varje incident.</span><span class="sxs-lookup"><span data-stu-id="96c79-166">String value available for every incident.</span></span> | <span data-ttu-id="96c79-167">Utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="96c79-167">Ransomware activity</span></span>
<span data-ttu-id="96c79-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="96c79-168">createdTime</span></span> | <span data-ttu-id="96c79-169">Tidpunkten när incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="96c79-169">Time when incident was first created.</span></span> | <span data-ttu-id="96c79-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="96c79-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="96c79-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="96c79-171">lastUpdateTime</span></span> | <span data-ttu-id="96c79-172">Tid när incidenten uppdaterades senast på backend.</span><span class="sxs-lookup"><span data-stu-id="96c79-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="96c79-173">Det här fältet kan användas när du anger parametern för begäran i det intervall som incidenterna har hämtats.</span><span class="sxs-lookup"><span data-stu-id="96c79-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="96c79-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="96c79-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="96c79-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="96c79-175">assignedTo</span></span> | <span data-ttu-id="96c79-176">Ägaren av händelsen, eller *null om* ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="96c79-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="96c79-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-177">secop2@contoso.com</span></span>
<span data-ttu-id="96c79-178">klassificering</span><span class="sxs-lookup"><span data-stu-id="96c79-178">classification</span></span> | <span data-ttu-id="96c79-179">Specifikationen för händelsen.</span><span class="sxs-lookup"><span data-stu-id="96c79-179">The specification for the incident.</span></span> <span data-ttu-id="96c79-180">Egenskapsvärdena *är: Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="96c79-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="96c79-181">Okänd</span><span class="sxs-lookup"><span data-stu-id="96c79-181">Unknown</span></span>
<span data-ttu-id="96c79-182">determination</span><span class="sxs-lookup"><span data-stu-id="96c79-182">determination</span></span> | <span data-ttu-id="96c79-183">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="96c79-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="96c79-184">Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="96c79-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="96c79-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="96c79-185">NotAvailable</span></span>
<span data-ttu-id="96c79-186">status</span><span class="sxs-lookup"><span data-stu-id="96c79-186">status</span></span> | <span data-ttu-id="96c79-187">Kategorisera ärenden (som *aktiva* eller *lösta*).</span><span class="sxs-lookup"><span data-stu-id="96c79-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="96c79-188">Det kan hjälpa dig att organisera och hantera dina svar på incidenter.</span><span class="sxs-lookup"><span data-stu-id="96c79-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="96c79-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="96c79-189">Active</span></span>
<span data-ttu-id="96c79-190">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="96c79-190">severity</span></span> | <span data-ttu-id="96c79-191">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="96c79-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="96c79-192">Ju högre allvarlighetsgrad, desto större påverkan.</span><span class="sxs-lookup"><span data-stu-id="96c79-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="96c79-193">I regel krävs det mest omedelbar uppmärksamhet för objekt med högre allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="96c79-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="96c79-194">Ett av följande värden: *Information,* \*Låg,\*\*Medel och *Hög.*</span><span class="sxs-lookup"><span data-stu-id="96c79-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="96c79-195">Medel</span><span class="sxs-lookup"><span data-stu-id="96c79-195">Medium</span></span>
<span data-ttu-id="96c79-196">taggar</span><span class="sxs-lookup"><span data-stu-id="96c79-196">tags</span></span> | <span data-ttu-id="96c79-197">Matris med anpassade taggar kopplade till en händelse, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="96c79-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="96c79-198">aviseringar</span><span class="sxs-lookup"><span data-stu-id="96c79-198">alerts</span></span> | <span data-ttu-id="96c79-199">Matris med alla aviseringar som är relaterade till händelsen samt annan information, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen och källan till aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="96c79-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="96c79-200">\[\] (mer information om aviseringsfält finns nedan)</span><span class="sxs-lookup"><span data-stu-id="96c79-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="96c79-201">Metadata för aviseringar</span><span class="sxs-lookup"><span data-stu-id="96c79-201">Alerts metadata</span></span>

<span data-ttu-id="96c79-202">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="96c79-202">Field name</span></span> | <span data-ttu-id="96c79-203">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-203">Description</span></span> | <span data-ttu-id="96c79-204">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="96c79-204">Example value</span></span>
-|-|-
<span data-ttu-id="96c79-205">alertid</span><span class="sxs-lookup"><span data-stu-id="96c79-205">alertId</span></span> | <span data-ttu-id="96c79-206">Unik identifierare som representerar aviseringen</span><span class="sxs-lookup"><span data-stu-id="96c79-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="96c79-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="96c79-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="96c79-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="96c79-208">incidentId</span></span> | <span data-ttu-id="96c79-209">Unikt ID som representerar den händelse som den här aviseringen är associerad med</span><span class="sxs-lookup"><span data-stu-id="96c79-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="96c79-210">924565</span><span class="sxs-lookup"><span data-stu-id="96c79-210">924565</span></span>
<span data-ttu-id="96c79-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="96c79-211">serviceSource</span></span> | <span data-ttu-id="96c79-212">Tjänst som aviseringen kommer från, till exempel Microsoft Defender för Slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet eller Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="96c79-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="96c79-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="96c79-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="96c79-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="96c79-214">creationTime</span></span> | <span data-ttu-id="96c79-215">Tidpunkt när aviseringen skapades.</span><span class="sxs-lookup"><span data-stu-id="96c79-215">Time when alert was first created.</span></span> | <span data-ttu-id="96c79-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="96c79-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="96c79-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="96c79-217">lastUpdatedTime</span></span> | <span data-ttu-id="96c79-218">Tid när aviseringen uppdaterades senast på backend.</span><span class="sxs-lookup"><span data-stu-id="96c79-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="96c79-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="96c79-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="96c79-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="96c79-220">resolvedTime</span></span> | <span data-ttu-id="96c79-221">Tid när aviseringen löstes.</span><span class="sxs-lookup"><span data-stu-id="96c79-221">Time when alert was resolved.</span></span> | <span data-ttu-id="96c79-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="96c79-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="96c79-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="96c79-223">firstActivity</span></span> | <span data-ttu-id="96c79-224">Tid när aviseringen först rapporterade att aktiviteten uppdaterades på backend.</span><span class="sxs-lookup"><span data-stu-id="96c79-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="96c79-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="96c79-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="96c79-226">rubrik</span><span class="sxs-lookup"><span data-stu-id="96c79-226">title</span></span> | <span data-ttu-id="96c79-227">Kort identifiering av strängvärde som är tillgängligt för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="96c79-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="96c79-228">Utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="96c79-228">Ransomware activity</span></span>
<span data-ttu-id="96c79-229">beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-229">description</span></span> | <span data-ttu-id="96c79-230">Strängvärde som beskriver varje avisering.</span><span class="sxs-lookup"><span data-stu-id="96c79-230">String value describing each alert.</span></span> | <span data-ttu-id="96c79-231">Användaren Test User2 (testUser2@contoso.com) har hanterat 99 filer med flera tillägg som slutar med den ovanliga filnamnstillägget *herunterladen.*</span><span class="sxs-lookup"><span data-stu-id="96c79-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="96c79-232">Det här är ett ovanligt antal filmanipuleringar och är en potentiell utpressningstrojanattack.</span><span class="sxs-lookup"><span data-stu-id="96c79-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="96c79-233">kategori</span><span class="sxs-lookup"><span data-stu-id="96c79-233">category</span></span> | <span data-ttu-id="96c79-234">Visuell och numerisk vy över hur långt attacken har fortskridt längs killkedja.</span><span class="sxs-lookup"><span data-stu-id="96c79-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="96c79-235">I linje med [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="96c79-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="96c79-236">Påverkan</span><span class="sxs-lookup"><span data-stu-id="96c79-236">Impact</span></span>
<span data-ttu-id="96c79-237">status</span><span class="sxs-lookup"><span data-stu-id="96c79-237">status</span></span> | <span data-ttu-id="96c79-238">Kategorisera aviseringar (som *Ny,* *Aktiv* eller *Löst*).</span><span class="sxs-lookup"><span data-stu-id="96c79-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="96c79-239">Det kan hjälpa dig att organisera och hantera dina svar på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="96c79-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="96c79-240">Ny</span><span class="sxs-lookup"><span data-stu-id="96c79-240">New</span></span>
<span data-ttu-id="96c79-241">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="96c79-241">severity</span></span> | <span data-ttu-id="96c79-242">Anger den möjliga påverkan på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="96c79-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="96c79-243">Ju högre allvarlighetsgrad, desto större påverkan.</span><span class="sxs-lookup"><span data-stu-id="96c79-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="96c79-244">I regel krävs det mest omedelbar uppmärksamhet för objekt med högre allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="96c79-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="96c79-245">Ett av följande värden: *Information,* \*Låg,\*\*Medel och *Hög.*</span><span class="sxs-lookup"><span data-stu-id="96c79-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="96c79-246">Medel</span><span class="sxs-lookup"><span data-stu-id="96c79-246">Medium</span></span>
<span data-ttu-id="96c79-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="96c79-247">investigationId</span></span> | <span data-ttu-id="96c79-248">Det automatiska undersöknings-ID som utlösts av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="96c79-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="96c79-249">1234</span><span class="sxs-lookup"><span data-stu-id="96c79-249">1234</span></span>
<span data-ttu-id="96c79-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="96c79-250">investigationState</span></span> | <span data-ttu-id="96c79-251">Information om undersökningens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="96c79-251">Information on the investigation's current status.</span></span> <span data-ttu-id="96c79-252">Ett av följande värden: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Suppress*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure,* *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="96c79-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="96c79-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="96c79-253">UnsupportedAlertType</span></span>
<span data-ttu-id="96c79-254">klassificering</span><span class="sxs-lookup"><span data-stu-id="96c79-254">classification</span></span> | <span data-ttu-id="96c79-255">Specifikationen för händelsen.</span><span class="sxs-lookup"><span data-stu-id="96c79-255">The specification for the incident.</span></span> <span data-ttu-id="96c79-256">Egenskapsvärdena *är: Unknown*, *FalsePositive,* *TruePositive* eller *null*</span><span class="sxs-lookup"><span data-stu-id="96c79-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="96c79-257">Okänd</span><span class="sxs-lookup"><span data-stu-id="96c79-257">Unknown</span></span>
<span data-ttu-id="96c79-258">determination</span><span class="sxs-lookup"><span data-stu-id="96c79-258">determination</span></span> | <span data-ttu-id="96c79-259">Anger incidentens avgörande.</span><span class="sxs-lookup"><span data-stu-id="96c79-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="96c79-260">Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* eller  *null*</span><span class="sxs-lookup"><span data-stu-id="96c79-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="96c79-261">Apt</span><span class="sxs-lookup"><span data-stu-id="96c79-261">Apt</span></span>
<span data-ttu-id="96c79-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="96c79-262">assignedTo</span></span> | <span data-ttu-id="96c79-263">Ägaren av händelsen, eller *null om* ingen ägare har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="96c79-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="96c79-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-264">secop2@contoso.com</span></span>
<span data-ttu-id="96c79-265">actorName</span><span class="sxs-lookup"><span data-stu-id="96c79-265">actorName</span></span> | <span data-ttu-id="96c79-266">Aktivitetsgruppen, om någon, är kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="96c79-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="96c79-267">BORON</span><span class="sxs-lookup"><span data-stu-id="96c79-267">BORON</span></span>
<span data-ttu-id="96c79-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="96c79-268">threatFamilyName</span></span> | <span data-ttu-id="96c79-269">Hotfamilj kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="96c79-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="96c79-270">null</span><span class="sxs-lookup"><span data-stu-id="96c79-270">null</span></span>
<span data-ttu-id="96c79-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="96c79-271">mitreTechniques</span></span> | <span data-ttu-id="96c79-272">Attacktekniker, i enlighet med [MITRE ATT-&CK-™](https://attack.mitre.org/)ramverket.</span><span class="sxs-lookup"><span data-stu-id="96c79-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="96c79-273">enheter</span><span class="sxs-lookup"><span data-stu-id="96c79-273">devices</span></span> | <span data-ttu-id="96c79-274">Alla enheter där aviseringar om incidenten har skickats.</span><span class="sxs-lookup"><span data-stu-id="96c79-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="96c79-275">\[\] (mer information om entitetsfälten finns nedan)</span><span class="sxs-lookup"><span data-stu-id="96c79-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="96c79-276">Enhetsformat</span><span class="sxs-lookup"><span data-stu-id="96c79-276">Device format</span></span>

<span data-ttu-id="96c79-277">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="96c79-277">Field name</span></span> | <span data-ttu-id="96c79-278">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-278">Description</span></span> | <span data-ttu-id="96c79-279">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="96c79-279">Example value</span></span>
-|-|-
<span data-ttu-id="96c79-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="96c79-280">DeviceId</span></span> | <span data-ttu-id="96c79-281">Enhets-ID:t som angetts i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="96c79-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="96c79-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="96c79-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="96c79-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="96c79-283">aadDeviceId</span></span> |  <span data-ttu-id="96c79-284">Det enhets-ID som angetts [i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="96c79-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="96c79-285">Endast tillgängligt för domän anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="96c79-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="96c79-286">null</span><span class="sxs-lookup"><span data-stu-id="96c79-286">null</span></span>
<span data-ttu-id="96c79-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="96c79-287">deviceDnsName</span></span> | <span data-ttu-id="96c79-288">Det fullständigt kvalificerade domännamnet för enheten.</span><span class="sxs-lookup"><span data-stu-id="96c79-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="96c79-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="96c79-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="96c79-290">osPlatform</span></span> | <span data-ttu-id="96c79-291">Den OS-plattform som enheten körs på.</span><span class="sxs-lookup"><span data-stu-id="96c79-291">The OS platform the device is running.</span></span>| <span data-ttu-id="96c79-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="96c79-292">WindowsServer2016</span></span>
<span data-ttu-id="96c79-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="96c79-293">osBuild</span></span> | <span data-ttu-id="96c79-294">Versionsversionen för operativsystemet som enheten kör.</span><span class="sxs-lookup"><span data-stu-id="96c79-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="96c79-295">14393</span><span class="sxs-lookup"><span data-stu-id="96c79-295">14393</span></span>
<span data-ttu-id="96c79-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="96c79-296">rbacGroupName</span></span> | <span data-ttu-id="96c79-297">Den [rollbaserade åtkomstkontrollgruppen](/azure/role-based-access-control/overview) (RBAC) som är kopplad till enheten.</span><span class="sxs-lookup"><span data-stu-id="96c79-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="96c79-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="96c79-298">WDATP-Ring0</span></span>
<span data-ttu-id="96c79-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="96c79-299">firstSeen</span></span> | <span data-ttu-id="96c79-300">Tid när enheten sågs första gången.</span><span class="sxs-lookup"><span data-stu-id="96c79-300">Time when device was first seen.</span></span> | <span data-ttu-id="96c79-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="96c79-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="96c79-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="96c79-302">healthStatus</span></span> | <span data-ttu-id="96c79-303">Status för enheten.</span><span class="sxs-lookup"><span data-stu-id="96c79-303">The health state of the device.</span></span> | <span data-ttu-id="96c79-304">Aktiv</span><span class="sxs-lookup"><span data-stu-id="96c79-304">Active</span></span>
<span data-ttu-id="96c79-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="96c79-305">riskScore</span></span> | <span data-ttu-id="96c79-306">Riskresultatet för enheten.</span><span class="sxs-lookup"><span data-stu-id="96c79-306">The risk score for the  device.</span></span> | <span data-ttu-id="96c79-307">Högsta</span><span class="sxs-lookup"><span data-stu-id="96c79-307">High</span></span>
<span data-ttu-id="96c79-308">enheter</span><span class="sxs-lookup"><span data-stu-id="96c79-308">entities</span></span> | <span data-ttu-id="96c79-309">Alla enheter som har identifierats vara en del av eller relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="96c79-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="96c79-310">\[\] (mer information om entitetsfälten finns nedan)</span><span class="sxs-lookup"><span data-stu-id="96c79-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="96c79-311">Enhetsformat</span><span class="sxs-lookup"><span data-stu-id="96c79-311">Entity Format</span></span>

<span data-ttu-id="96c79-312">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="96c79-312">Field name</span></span> | <span data-ttu-id="96c79-313">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96c79-313">Description</span></span> | <span data-ttu-id="96c79-314">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="96c79-314">Example value</span></span>
-|-|-
<span data-ttu-id="96c79-315">entityType</span><span class="sxs-lookup"><span data-stu-id="96c79-315">entityType</span></span> | <span data-ttu-id="96c79-316">Enheter som har identifierats vara en del av eller relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="96c79-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="96c79-317">Egenskapsvärdena är: *Användare*, *Ip*, *URL*, *Fil*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="96c79-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="96c79-318">Användare</span><span class="sxs-lookup"><span data-stu-id="96c79-318">User</span></span>
<span data-ttu-id="96c79-319">sha1</span><span class="sxs-lookup"><span data-stu-id="96c79-319">sha1</span></span> | <span data-ttu-id="96c79-320">Tillgängligt om entitetType är *File*.</span><span class="sxs-lookup"><span data-stu-id="96c79-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="96c79-321">Filhash för aviseringar som associeras med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="96c79-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="96c79-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="96c79-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="96c79-323">sha256</span><span class="sxs-lookup"><span data-stu-id="96c79-323">sha256</span></span> | <span data-ttu-id="96c79-324">Tillgängligt om entitetType är *File*.</span><span class="sxs-lookup"><span data-stu-id="96c79-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="96c79-325">Filhash för aviseringar som associeras med en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="96c79-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="96c79-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="96c79-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="96c79-327">fileName</span><span class="sxs-lookup"><span data-stu-id="96c79-327">fileName</span></span> | <span data-ttu-id="96c79-328">Tillgängligt om entitetType är *File*.</span><span class="sxs-lookup"><span data-stu-id="96c79-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="96c79-329">Filnamnet för aviseringar som associeras med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="96c79-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="96c79-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="96c79-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="96c79-331">filePath</span><span class="sxs-lookup"><span data-stu-id="96c79-331">filePath</span></span> | <span data-ttu-id="96c79-332">Tillgängligt om entitetType är *File*.</span><span class="sxs-lookup"><span data-stu-id="96c79-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="96c79-333">Filsökvägen för aviseringar som associeras med en fil eller process</span><span class="sxs-lookup"><span data-stu-id="96c79-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="96c79-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="96c79-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="96c79-335">processId</span><span class="sxs-lookup"><span data-stu-id="96c79-335">processId</span></span> | <span data-ttu-id="96c79-336">Tillgängligt om entitetType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="96c79-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="96c79-337">24348</span><span class="sxs-lookup"><span data-stu-id="96c79-337">24348</span></span>
<span data-ttu-id="96c79-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="96c79-338">processCommandLine</span></span> | <span data-ttu-id="96c79-339">Tillgängligt om entitetType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="96c79-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="96c79-340">"Filen är klar att ladda ned \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="96c79-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="96c79-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="96c79-341">processCreationTime</span></span> | <span data-ttu-id="96c79-342">Tillgängligt om entitetType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="96c79-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="96c79-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="96c79-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="96c79-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="96c79-344">parentProcessId</span></span> | <span data-ttu-id="96c79-345">Tillgängligt om entitetType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="96c79-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="96c79-346">16840</span><span class="sxs-lookup"><span data-stu-id="96c79-346">16840</span></span>
<span data-ttu-id="96c79-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="96c79-347">parentProcessCreationTime</span></span> | <span data-ttu-id="96c79-348">Tillgängligt om entitetType är *Process*.</span><span class="sxs-lookup"><span data-stu-id="96c79-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="96c79-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="96c79-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="96c79-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="96c79-350">ipAddress</span></span> | <span data-ttu-id="96c79-351">Tillgängligt om entitetType är *Ip*.</span><span class="sxs-lookup"><span data-stu-id="96c79-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="96c79-352">IP-adress för aviseringar som associeras med nätverkshändelser, till *exempel kommunikation till en skadlig nätverksdestination.*</span><span class="sxs-lookup"><span data-stu-id="96c79-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="96c79-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="96c79-353">62.216.203.204</span></span>
<span data-ttu-id="96c79-354">url</span><span class="sxs-lookup"><span data-stu-id="96c79-354">url</span></span> | <span data-ttu-id="96c79-355">Tillgängligt om entitetType är *URL*.</span><span class="sxs-lookup"><span data-stu-id="96c79-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="96c79-356">URL för aviseringar kopplade till nätverkshändelser, till exempel kommunikation *till en skadlig nätverksdestination*.</span><span class="sxs-lookup"><span data-stu-id="96c79-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="96c79-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="96c79-357">down.esales360.cn</span></span>
<span data-ttu-id="96c79-358">accountName</span><span class="sxs-lookup"><span data-stu-id="96c79-358">accountName</span></span> | <span data-ttu-id="96c79-359">Tillgängligt om entitetType är *Användare*.</span><span class="sxs-lookup"><span data-stu-id="96c79-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="96c79-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="96c79-360">testUser2</span></span>
<span data-ttu-id="96c79-361">domainName</span><span class="sxs-lookup"><span data-stu-id="96c79-361">domainName</span></span> | <span data-ttu-id="96c79-362">Tillgängligt om entitetType är *Användare*.</span><span class="sxs-lookup"><span data-stu-id="96c79-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="96c79-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="96c79-363">europe.corp.contoso</span></span>
<span data-ttu-id="96c79-364">userSid</span><span class="sxs-lookup"><span data-stu-id="96c79-364">userSid</span></span> | <span data-ttu-id="96c79-365">Tillgängligt om entitetType är *Användare*.</span><span class="sxs-lookup"><span data-stu-id="96c79-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="96c79-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="96c79-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="96c79-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="96c79-367">aadUserId</span></span> | <span data-ttu-id="96c79-368">Tillgängligt om entitetType är *Användare*.</span><span class="sxs-lookup"><span data-stu-id="96c79-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="96c79-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="96c79-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="96c79-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="96c79-370">userPrincipalName</span></span> | <span data-ttu-id="96c79-371">Tillgängligt om entitetType *är User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="96c79-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-372">testUser2@contoso.com</span></span>
<span data-ttu-id="96c79-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="96c79-373">mailboxDisplayName</span></span> | <span data-ttu-id="96c79-374">Tillgängligt om entitetType *är MailBox*.</span><span class="sxs-lookup"><span data-stu-id="96c79-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="96c79-375">testa användare2</span><span class="sxs-lookup"><span data-stu-id="96c79-375">test User2</span></span>
<span data-ttu-id="96c79-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="96c79-376">mailboxAddress</span></span> | <span data-ttu-id="96c79-377">Tillgängligt om entitetType *är User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="96c79-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-378">testUser2@contoso.com</span></span>
<span data-ttu-id="96c79-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="96c79-379">clusterBy</span></span> | <span data-ttu-id="96c79-380">Tillgängligt om entitetType  *är MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="96c79-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="96c79-381">Ämne; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="96c79-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="96c79-382">avsändare</span><span class="sxs-lookup"><span data-stu-id="96c79-382">sender</span></span> | <span data-ttu-id="96c79-383">Tillgängligt om entitetType *är User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="96c79-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="96c79-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="96c79-385">mottagare</span><span class="sxs-lookup"><span data-stu-id="96c79-385">recipient</span></span> | <span data-ttu-id="96c79-386">Tillgängligt om entitetType *är MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="96c79-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96c79-387">testUser2@contoso.com</span></span>
<span data-ttu-id="96c79-388">ämne</span><span class="sxs-lookup"><span data-stu-id="96c79-388">subject</span></span> | <span data-ttu-id="96c79-389">Tillgängligt om entitetType *är MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="96c79-390">\[EXTERN \] uppmärksamhet</span><span class="sxs-lookup"><span data-stu-id="96c79-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="96c79-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="96c79-391">deliveryAction</span></span> | <span data-ttu-id="96c79-392">Tillgängligt om entitetType *är MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="96c79-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="96c79-393">Levererad</span><span class="sxs-lookup"><span data-stu-id="96c79-393">Delivered</span></span>
<span data-ttu-id="96c79-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="96c79-394">securityGroupId</span></span> | <span data-ttu-id="96c79-395">Tillgängligt om entitetType  *är SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="96c79-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="96c79-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="96c79-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="96c79-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="96c79-397">securityGroupName</span></span> | <span data-ttu-id="96c79-398">Tillgängligt om entitetType  *är SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="96c79-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="96c79-399">Nätverkskonfigurationsoperatorer</span><span class="sxs-lookup"><span data-stu-id="96c79-399">Network Configuration Operators</span></span>
<span data-ttu-id="96c79-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="96c79-400">registryHive</span></span> | <span data-ttu-id="96c79-401">Tillgängligt om entitetType  *är register*.</span><span class="sxs-lookup"><span data-stu-id="96c79-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="96c79-402">HKEY \_ LOCAL \_ MACHINE</span><span class="sxs-lookup"><span data-stu-id="96c79-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="96c79-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="96c79-403">registryKey</span></span> | <span data-ttu-id="96c79-404">Tillgängligt om entitetType  *är register*.</span><span class="sxs-lookup"><span data-stu-id="96c79-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="96c79-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="96c79-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="96c79-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="96c79-406">registryValueType</span></span> | <span data-ttu-id="96c79-407">Tillgängligt om entitetType  *är register*.</span><span class="sxs-lookup"><span data-stu-id="96c79-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="96c79-408">Sträng</span><span class="sxs-lookup"><span data-stu-id="96c79-408">String</span></span>
<span data-ttu-id="96c79-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="96c79-409">registryValue</span></span> | <span data-ttu-id="96c79-410">Tillgängligt om entitetType  *är register*.</span><span class="sxs-lookup"><span data-stu-id="96c79-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="96c79-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="96c79-411">31-00-00-00</span></span>
<span data-ttu-id="96c79-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="96c79-412">deviceId</span></span> | <span data-ttu-id="96c79-413">ID:t, om det finns något, för enheten som är relaterad till enheten.</span><span class="sxs-lookup"><span data-stu-id="96c79-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="96c79-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="96c79-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="96c79-415">Exempel</span><span class="sxs-lookup"><span data-stu-id="96c79-415">Example</span></span>

<span data-ttu-id="96c79-416">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="96c79-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="96c79-417">**Svar**</span><span class="sxs-lookup"><span data-stu-id="96c79-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="96c79-418">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="96c79-418">Related articles</span></span>

- [<span data-ttu-id="96c79-419">Åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="96c79-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="96c79-420">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="96c79-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="96c79-421">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="96c79-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="96c79-422">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="96c79-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="96c79-423">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="96c79-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="96c79-424">Api för uppdatering av incident</span><span class="sxs-lookup"><span data-stu-id="96c79-424">Update incident API</span></span>](api-update-incidents.md)