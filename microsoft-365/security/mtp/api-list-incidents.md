---
title: List API för incidenter i Microsoft Threat Protection
description: Lär dig hur du felvisar API för incidenter i Microsoft Threat Protection
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195386"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="45466-104">List API för incidenter i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="45466-104">List incidents API in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45466-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="45466-105">**Applies to:**</span></span>

- <span data-ttu-id="45466-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="45466-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45466-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="45466-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="45466-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="45466-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="45466-109">API-Beskrivning</span><span class="sxs-lookup"><span data-stu-id="45466-109">API description</span></span>

<span data-ttu-id="45466-110">Med incident-API kan du sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity-svar.</span><span class="sxs-lookup"><span data-stu-id="45466-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="45466-111">Den exponerar en mängd händelser som har flaggats från enheter, e-postkonton och användare i nätverket, inom det tidsintervall som du angav i miljön.</span><span class="sxs-lookup"><span data-stu-id="45466-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="45466-112">De senaste incidenterna visas högst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="45466-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="45466-113">Varje händelse innehåller en matris med relaterade aviseringar och tillhör deras relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="45466-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="45466-114">API: et stöder följande **OData** -operatorer.</span><span class="sxs-lookup"><span data-stu-id="45466-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="45466-115">```$filter``` för: ```lastUpdateTime``` , ```createdTime``` ```status``` och ```assignedTo``` Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="45466-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="45466-116">```$top``` med max värdet **100**</span><span class="sxs-lookup"><span data-stu-id="45466-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="45466-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="45466-117">Limitations</span></span>

1. <span data-ttu-id="45466-118">Maximal sid storlek är **100-incidenter**.</span><span class="sxs-lookup"><span data-stu-id="45466-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="45466-119">Maximal taxa för förfrågningar är **50 samtal per minut** och **1500 samtal per timme**.</span><span class="sxs-lookup"><span data-stu-id="45466-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="45466-120">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="45466-120">Permissions</span></span>

<span data-ttu-id="45466-121">En av följande behörigheter krävs för att kunna ringa detta API.</span><span class="sxs-lookup"><span data-stu-id="45466-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="45466-122">Om du vill veta mer, inklusive hur du väljer behörigheter, se [åtkomst till Microsoft Threat Protection API: er](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="45466-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="45466-123">Behörighets typ</span><span class="sxs-lookup"><span data-stu-id="45466-123">Permission type</span></span> |   <span data-ttu-id="45466-124">Tillåtelse</span><span class="sxs-lookup"><span data-stu-id="45466-124">Permission</span></span>  |   <span data-ttu-id="45466-125">Visnings namn för behörighet</span><span class="sxs-lookup"><span data-stu-id="45466-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="45466-126">Program</span><span class="sxs-lookup"><span data-stu-id="45466-126">Application</span></span> |   <span data-ttu-id="45466-127">Incident. Read. all</span><span class="sxs-lookup"><span data-stu-id="45466-127">Incident.Read.All</span></span> | <span data-ttu-id="45466-128">"Läs alla händelser"</span><span class="sxs-lookup"><span data-stu-id="45466-128">'Read all incidents'</span></span>
<span data-ttu-id="45466-129">Program</span><span class="sxs-lookup"><span data-stu-id="45466-129">Application</span></span> |   <span data-ttu-id="45466-130">Incident. ReadWrite. alla</span><span class="sxs-lookup"><span data-stu-id="45466-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="45466-131">"Läs och skriv alla händelser"</span><span class="sxs-lookup"><span data-stu-id="45466-131">'Read and write all incidents'</span></span>
<span data-ttu-id="45466-132">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="45466-132">Delegated (work or school account)</span></span> | <span data-ttu-id="45466-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="45466-133">Incident.Read</span></span> | <span data-ttu-id="45466-134">"Läsfel"</span><span class="sxs-lookup"><span data-stu-id="45466-134">'Read incidents'</span></span>
<span data-ttu-id="45466-135">Delegerat (arbets-eller skol konto)</span><span class="sxs-lookup"><span data-stu-id="45466-135">Delegated (work or school account)</span></span> | <span data-ttu-id="45466-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="45466-136">Incident.ReadWrite</span></span> | <span data-ttu-id="45466-137">"Läs-och skriv händelser"</span><span class="sxs-lookup"><span data-stu-id="45466-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="45466-138">När du erhåller ett token med användar uppgifter:</span><span class="sxs-lookup"><span data-stu-id="45466-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="45466-139">Användaren måste ha behörigheten Visa för händelser i portalen.</span><span class="sxs-lookup"><span data-stu-id="45466-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="45466-140">Svaret innehåller endast händelser som användaren utsätts för.</span><span class="sxs-lookup"><span data-stu-id="45466-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="45466-141">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="45466-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="45466-142">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="45466-142">Request headers</span></span>

<span data-ttu-id="45466-143">Namn</span><span class="sxs-lookup"><span data-stu-id="45466-143">Name</span></span> | <span data-ttu-id="45466-144">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="45466-144">Type</span></span> | <span data-ttu-id="45466-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="45466-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="45466-146">Bemyndigande</span><span class="sxs-lookup"><span data-stu-id="45466-146">Authorization</span></span> | <span data-ttu-id="45466-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="45466-147">String</span></span> | <span data-ttu-id="45466-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="45466-148">Bearer {token}.</span></span> <span data-ttu-id="45466-149">**Obligatoriskt**.</span><span class="sxs-lookup"><span data-stu-id="45466-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="45466-150">Brödtext</span><span class="sxs-lookup"><span data-stu-id="45466-150">Request body</span></span>
<span data-ttu-id="45466-151">Ingen.</span><span class="sxs-lookup"><span data-stu-id="45466-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="45466-152">Interimssvar</span><span class="sxs-lookup"><span data-stu-id="45466-152">Response</span></span>
<span data-ttu-id="45466-153">Om det lyckas returnerar den här metoden 200 OK och en lista med [incidenter](api-incident.md) i svars texten.</span><span class="sxs-lookup"><span data-stu-id="45466-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="45466-154">Schema mappning</span><span class="sxs-lookup"><span data-stu-id="45466-154">Schema mapping</span></span>

| <span data-ttu-id="45466-155">Fält namn</span><span class="sxs-lookup"><span data-stu-id="45466-155">Field name</span></span>                                | <span data-ttu-id="45466-156">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="45466-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-157">Exempel värde</span><span class="sxs-lookup"><span data-stu-id="45466-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="45466-158">**Metadata för incident**</span><span class="sxs-lookup"><span data-stu-id="45466-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="45466-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="45466-159">incidentId</span></span>                                | <span data-ttu-id="45466-160">Unik identifierare som representerar incidenten.</span><span class="sxs-lookup"><span data-stu-id="45466-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-161">924565</span><span class="sxs-lookup"><span data-stu-id="45466-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="45466-162">redirectIncidentId</span></span>                        | <span data-ttu-id="45466-163">Endast i händelse av att en olycka grupperas tillsammans med en annan incident, som en del av bearbetnings logiken för olyckor.</span><span class="sxs-lookup"><span data-stu-id="45466-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="45466-164">924569</span><span class="sxs-lookup"><span data-stu-id="45466-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="45466-165">incidentName</span></span>                              | <span data-ttu-id="45466-166">Ett sträng värde är tillgängligt för alla händelser.</span><span class="sxs-lookup"><span data-stu-id="45466-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="45466-167">Utpressnings tro aktivitet</span><span class="sxs-lookup"><span data-stu-id="45466-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="45466-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="45466-168">createdTime</span></span>                               | <span data-ttu-id="45466-169">Tidpunkt då incidenten först skapades.</span><span class="sxs-lookup"><span data-stu-id="45466-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="45466-170">2020 – 09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="45466-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="45466-171">lastUpdateTime</span></span>                            | <span data-ttu-id="45466-172">Tidpunkt då incidenten senast uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="45466-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="45466-173">Det här fältet kan användas när du ställer in parametern request för det tidsintervall som incidenter hämtas.</span><span class="sxs-lookup"><span data-stu-id="45466-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="45466-174">2020 – 09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="45466-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="45466-175">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="45466-175">assignedTo</span></span>                                | <span data-ttu-id="45466-176">Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.</span><span class="sxs-lookup"><span data-stu-id="45466-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="45466-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="45466-178">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="45466-178">classification</span></span>                            | <span data-ttu-id="45466-179">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="45466-179">The specification for the incident.</span></span> <span data-ttu-id="45466-180">Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="45466-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="45466-181">Okänd</span><span class="sxs-lookup"><span data-stu-id="45466-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="45466-182">bedömning</span><span class="sxs-lookup"><span data-stu-id="45466-182">determination</span></span>                             | <span data-ttu-id="45466-183">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="45466-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="45466-184">Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *övrigt*</span><span class="sxs-lookup"><span data-stu-id="45466-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="45466-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="45466-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-186">status</span><span class="sxs-lookup"><span data-stu-id="45466-186">status</span></span>                                    | <span data-ttu-id="45466-187">Kategorisera incidenter (som *aktiva*eller *löst*).</span><span class="sxs-lookup"><span data-stu-id="45466-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="45466-188">Det hjälper dig att organisera och hantera ditt svar på tillbud.</span><span class="sxs-lookup"><span data-stu-id="45466-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="45466-189">Aktiva</span><span class="sxs-lookup"><span data-stu-id="45466-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-190">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="45466-190">severity</span></span>                                  | <span data-ttu-id="45466-191">Anger möjlig påverkan på till gångar.</span><span class="sxs-lookup"><span data-stu-id="45466-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="45466-192">Ju högre allvarlighets grad desto större effekt.</span><span class="sxs-lookup"><span data-stu-id="45466-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="45466-193">Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="45466-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="45466-194">Något av följande värden: *information*, *Low*, \* medium och *High*.</span><span class="sxs-lookup"><span data-stu-id="45466-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="45466-195">Risk</span><span class="sxs-lookup"><span data-stu-id="45466-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-196">taggen</span><span class="sxs-lookup"><span data-stu-id="45466-196">tags</span></span>                                      | <span data-ttu-id="45466-197">Matris med anpassade taggar som är kopplade till en olycka, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="45466-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-198">larm</span><span class="sxs-lookup"><span data-stu-id="45466-198">alerts</span></span>                                    | <span data-ttu-id="45466-199">Lista över alla aviseringar som är relaterade till incidenten och annan information, till exempel allvarlighets grad, enheter som ingick i aviseringen, källan till aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="45466-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="45466-200">\[\] (se informationen om aviserings fälten nedan)</span><span class="sxs-lookup"><span data-stu-id="45466-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="45466-201">**Metadata för aviseringar**</span><span class="sxs-lookup"><span data-stu-id="45466-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="45466-202">alertId</span><span class="sxs-lookup"><span data-stu-id="45466-202">alertId</span></span>                                   | <span data-ttu-id="45466-203">Unik identifierare som representerar aviseringen</span><span class="sxs-lookup"><span data-stu-id="45466-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="45466-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="45466-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="45466-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="45466-205">incidentId</span></span>                                | <span data-ttu-id="45466-206">Unik identifierare som representerar den incident som aviseringen är associerad med</span><span class="sxs-lookup"><span data-stu-id="45466-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="45466-207">924565</span><span class="sxs-lookup"><span data-stu-id="45466-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="45466-208">serviceSource</span></span>                             | <span data-ttu-id="45466-209">Tjänsten som aviseringen kommer från, till exempel Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP eller Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="45466-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="45466-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="45466-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="45466-211">creationTime</span></span>                              | <span data-ttu-id="45466-212">Tid då aviseringen först skapades.</span><span class="sxs-lookup"><span data-stu-id="45466-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="45466-213">2020 – 09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="45466-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="45466-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="45466-215">Tid när aviseringen senast uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="45466-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="45466-216">2020 – 09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="45466-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="45466-217">resolvedTime</span></span>                              | <span data-ttu-id="45466-218">Tid då aviseringen löstes.</span><span class="sxs-lookup"><span data-stu-id="45466-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="45466-219">2020 – 09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="45466-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="45466-220">firstActivity</span></span>                             | <span data-ttu-id="45466-221">Tid när aviseringen först rapporterades om att aktiviteten uppdaterades på Server delen.</span><span class="sxs-lookup"><span data-stu-id="45466-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="45466-222">2020 – 09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="45466-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-223">titelfält</span><span class="sxs-lookup"><span data-stu-id="45466-223">title</span></span>                                     | <span data-ttu-id="45466-224">Ett kort värde som är tillgängligt för varje varning.</span><span class="sxs-lookup"><span data-stu-id="45466-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-225">Utpressnings tro aktivitet</span><span class="sxs-lookup"><span data-stu-id="45466-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="45466-226">beskrivning</span><span class="sxs-lookup"><span data-stu-id="45466-226">description</span></span>                               | <span data-ttu-id="45466-227">Sträng värde som beskriver varje varning.</span><span class="sxs-lookup"><span data-stu-id="45466-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-228">User test user2 (testUser2@contoso.com) manipulerar 99-filer med flera tillägg som slutar med det ovanliga tillägget *Herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="45466-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="45466-229">Det här är ett ovanligt antal fil ändringar och är ett exempel på en potentiell utpressnings tro Jan attack.</span><span class="sxs-lookup"><span data-stu-id="45466-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="45466-230">typ</span><span class="sxs-lookup"><span data-stu-id="45466-230">category</span></span>                                  | <span data-ttu-id="45466-231">Visuell och numerisk vy av hur långt angreppet har gått under Kill-kedjan.</span><span class="sxs-lookup"><span data-stu-id="45466-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="45466-232">Justerad till [MITREn att&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="45466-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="45466-233">Påverkan</span><span class="sxs-lookup"><span data-stu-id="45466-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-234">status</span><span class="sxs-lookup"><span data-stu-id="45466-234">status</span></span>                                    | <span data-ttu-id="45466-235">Kategorisera aviseringar (som *nya*, *aktiva*eller *stängda*).</span><span class="sxs-lookup"><span data-stu-id="45466-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="45466-236">Det hjälper dig att organisera och hantera dina svar på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="45466-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="45466-237">Nya</span><span class="sxs-lookup"><span data-stu-id="45466-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="45466-238">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="45466-238">severity</span></span>                                  | <span data-ttu-id="45466-239">Anger möjlig påverkan på till gångar.</span><span class="sxs-lookup"><span data-stu-id="45466-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="45466-240">Ju högre allvarlighets grad desto större effekt.</span><span class="sxs-lookup"><span data-stu-id="45466-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="45466-241">Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="45466-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="45466-242">Något av följande värden: *information*, *Low*, \* medium och *High*.</span><span class="sxs-lookup"><span data-stu-id="45466-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="45466-243">Risk</span><span class="sxs-lookup"><span data-stu-id="45466-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="45466-244">investigationId</span></span>                           | <span data-ttu-id="45466-245">Det automatiska undersöknings-ID: t som utlöste den här varningen.</span><span class="sxs-lookup"><span data-stu-id="45466-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-246">1234</span><span class="sxs-lookup"><span data-stu-id="45466-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="45466-247">investigationState</span></span>                        | <span data-ttu-id="45466-248">Information om utredningens aktuella status.</span><span class="sxs-lookup"><span data-stu-id="45466-248">Information on the investigation's current status.</span></span> <span data-ttu-id="45466-249">Något av följande: *Okänt*, *avslutat*, *SuccessfullyRemediated*, *ofarligt*, *misslyckat*, *PartiallyRemediated*, *pågående*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *köade*, *InnerFailure*, *PreexistingAlert*, *,* *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="45466-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="45466-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="45466-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-251">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="45466-251">classification</span></span>                            | <span data-ttu-id="45466-252">Specifikation för incidenten.</span><span class="sxs-lookup"><span data-stu-id="45466-252">The specification for the incident.</span></span> <span data-ttu-id="45466-253">Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive* eller *Null*</span><span class="sxs-lookup"><span data-stu-id="45466-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="45466-254">Okänd</span><span class="sxs-lookup"><span data-stu-id="45466-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="45466-255">bedömning</span><span class="sxs-lookup"><span data-stu-id="45466-255">determination</span></span>                             | <span data-ttu-id="45466-256">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="45466-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="45466-257">Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* eller  *Null*</span><span class="sxs-lookup"><span data-stu-id="45466-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="45466-258">Apt</span><span class="sxs-lookup"><span data-stu-id="45466-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="45466-259">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="45466-259">assignedTo</span></span>                                | <span data-ttu-id="45466-260">Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.</span><span class="sxs-lookup"><span data-stu-id="45466-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="45466-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="45466-262">actorName</span><span class="sxs-lookup"><span data-stu-id="45466-262">actorName</span></span>                                 | <span data-ttu-id="45466-263">Aktivitets gruppen, om den är kopplad till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="45466-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-264">UTTRYCKT</span><span class="sxs-lookup"><span data-stu-id="45466-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="45466-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="45466-265">threatFamilyName</span></span>                          | <span data-ttu-id="45466-266">Hot familj som är associerad med den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="45466-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="45466-267">kan</span><span class="sxs-lookup"><span data-stu-id="45466-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="45466-268">mitreTechniques</span></span>                           | <span data-ttu-id="45466-269">Angrepps metoderna, som är justerade med [MITREn att&CK](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="45466-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-270">anordningar</span><span class="sxs-lookup"><span data-stu-id="45466-270">devices</span></span>                                   | <span data-ttu-id="45466-271">Alla enheter där aviseringar relaterade till händelsen skickades.</span><span class="sxs-lookup"><span data-stu-id="45466-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-272">\[\] (se informationen om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="45466-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="45466-273">**Enhets format**</span><span class="sxs-lookup"><span data-stu-id="45466-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="45466-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="45466-274">DeviceId</span></span>                                  | <span data-ttu-id="45466-275">Enhets-ID enligt Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="45466-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="45466-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="45466-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="45466-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="45466-277">aadDeviceId</span></span>                               |  <span data-ttu-id="45466-278">Enhets-ID enligt [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span><span class="sxs-lookup"><span data-stu-id="45466-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="45466-279">Endast tillgängligt för domänanslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="45466-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="45466-280">kan</span><span class="sxs-lookup"><span data-stu-id="45466-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="45466-281">deviceDnsName</span></span>                             | <span data-ttu-id="45466-282">Det fullt kvalificerade domän namnet för enheten.</span><span class="sxs-lookup"><span data-stu-id="45466-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="45466-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="45466-284">osPlatform</span></span>                                | <span data-ttu-id="45466-285">Den OS-plattform enheten körs på.</span><span class="sxs-lookup"><span data-stu-id="45466-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="45466-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="45466-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="45466-287">osBuild</span></span>                                   | <span data-ttu-id="45466-288">Versions versionen för det OS-enheten.</span><span class="sxs-lookup"><span data-stu-id="45466-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-289">14393</span><span class="sxs-lookup"><span data-stu-id="45466-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="45466-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="45466-290">rbacGroupName</span></span>                             | <span data-ttu-id="45466-291">Den [rollbaserad åtkomst kontroll](https://docs.microsoft.com/azure/role-based-access-control/overview) gruppen som är associerad med enheten.</span><span class="sxs-lookup"><span data-stu-id="45466-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="45466-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="45466-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="45466-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="45466-293">firstSeen</span></span>                                 | <span data-ttu-id="45466-294">Tid då enheten först visades.</span><span class="sxs-lookup"><span data-stu-id="45466-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="45466-295">2020 – 02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="45466-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="45466-296">healthStatus</span></span>                              | <span data-ttu-id="45466-297">Enhetens hälso status.</span><span class="sxs-lookup"><span data-stu-id="45466-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-298">Aktiva</span><span class="sxs-lookup"><span data-stu-id="45466-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="45466-299">riskScore</span></span>                                 | <span data-ttu-id="45466-300">Risk poängen för enheten.</span><span class="sxs-lookup"><span data-stu-id="45466-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="45466-301">Högsta</span><span class="sxs-lookup"><span data-stu-id="45466-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-302">posterna</span><span class="sxs-lookup"><span data-stu-id="45466-302">entities</span></span>                                  | <span data-ttu-id="45466-303">Alla enheter som har identifierats som en del av eller är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="45466-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-304">\[\] (se informationen om entitetsfält nedan)</span><span class="sxs-lookup"><span data-stu-id="45466-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="45466-305">**Enhets format**</span><span class="sxs-lookup"><span data-stu-id="45466-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="45466-306">Angiven</span><span class="sxs-lookup"><span data-stu-id="45466-306">entityType</span></span>                                | <span data-ttu-id="45466-307">Enheter som har identifierats som en del av eller är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="45466-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="45466-308">Egenskaps värden är: *användare*, *IP*, *URL*, *fil*, *process*, *post låda, e*- *postmeddelande*, *kluster*, *register*</span><span class="sxs-lookup"><span data-stu-id="45466-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="45466-309">Användare</span><span class="sxs-lookup"><span data-stu-id="45466-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="45466-310">sha1</span></span>                                      | <span data-ttu-id="45466-311">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="45466-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="45466-312">Fil-hash för aviseringar som är kopplade till en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="45466-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="45466-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="45466-314">sha256</span><span class="sxs-lookup"><span data-stu-id="45466-314">sha256</span></span>                                    | <span data-ttu-id="45466-315">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="45466-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="45466-316">Fil-hash för aviseringar som är kopplade till en fil eller process.</span><span class="sxs-lookup"><span data-stu-id="45466-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="45466-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="45466-318">Datafil</span><span class="sxs-lookup"><span data-stu-id="45466-318">fileName</span></span>                                  | <span data-ttu-id="45466-319">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="45466-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="45466-320">Fil namnet för aviseringar som är kopplade till en fil eller process</span><span class="sxs-lookup"><span data-stu-id="45466-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="45466-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-322">Skript</span><span class="sxs-lookup"><span data-stu-id="45466-322">filePath</span></span>                                  | <span data-ttu-id="45466-323">Tillgängligt om entityType är *File*.</span><span class="sxs-lookup"><span data-stu-id="45466-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="45466-324">Fil Sök vägen för aviseringar som är kopplade till en fil eller process</span><span class="sxs-lookup"><span data-stu-id="45466-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-325">C: \\ \\ agenten \\ \\ \_ fungerar \\ \\ \_ Temp \\ \\ distribuera \_ system 2020-09-06 12 \_ 14 \_ 54 \\ \\ ut</span><span class="sxs-lookup"><span data-stu-id="45466-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="45466-326">processId</span><span class="sxs-lookup"><span data-stu-id="45466-326">processId</span></span>                                 | <span data-ttu-id="45466-327">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="45466-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-328">24348</span><span class="sxs-lookup"><span data-stu-id="45466-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="45466-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="45466-329">processCommandLine</span></span>                        | <span data-ttu-id="45466-330">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="45466-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-331">" \\ " Filen är klar för nedladdning \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="45466-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="45466-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="45466-332">processCreationTime</span></span>                       | <span data-ttu-id="45466-333">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="45466-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-334">2020 – 07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="45466-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="45466-335">parentProcessId</span></span>                           | <span data-ttu-id="45466-336">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="45466-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="45466-337">16840</span><span class="sxs-lookup"><span data-stu-id="45466-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="45466-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="45466-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="45466-339">Tillgängligt om entityType är *process*.</span><span class="sxs-lookup"><span data-stu-id="45466-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-340">2020 – 07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="45466-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="45466-341">IP</span><span class="sxs-lookup"><span data-stu-id="45466-341">ipAddress</span></span>                                 | <span data-ttu-id="45466-342">Tillgängligt om entityType är *IP*.</span><span class="sxs-lookup"><span data-stu-id="45466-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="45466-343">IP-adress för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till ett skadligt nätverk*.</span><span class="sxs-lookup"><span data-stu-id="45466-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="45466-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="45466-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="45466-345">:</span><span class="sxs-lookup"><span data-stu-id="45466-345">url</span></span>                                       | <span data-ttu-id="45466-346">Tillgängligt om entityType är *URL*.</span><span class="sxs-lookup"><span data-stu-id="45466-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="45466-347">URL för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till en illvillig nätverks destination*.</span><span class="sxs-lookup"><span data-stu-id="45466-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="45466-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="45466-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="45466-349">Konto</span><span class="sxs-lookup"><span data-stu-id="45466-349">accountName</span></span>                               | <span data-ttu-id="45466-350">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="45466-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="45466-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="45466-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="45466-352">domainName</span><span class="sxs-lookup"><span data-stu-id="45466-352">domainName</span></span>                                | <span data-ttu-id="45466-353">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="45466-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-354">Europa. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="45466-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-355">userSid</span><span class="sxs-lookup"><span data-stu-id="45466-355">userSid</span></span>                                   | <span data-ttu-id="45466-356">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="45466-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="45466-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="45466-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="45466-358">aadUserId</span></span>                                 | <span data-ttu-id="45466-359">Tillgänglig om entityType är *User*.</span><span class="sxs-lookup"><span data-stu-id="45466-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="45466-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="45466-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="45466-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="45466-361">userPrincipalName</span></span>                         | <span data-ttu-id="45466-362">Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="45466-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="45466-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="45466-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="45466-365">Tillgänglig om entityType är *post låda*.</span><span class="sxs-lookup"><span data-stu-id="45466-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-366">testa user2</span><span class="sxs-lookup"><span data-stu-id="45466-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="45466-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="45466-367">mailboxAddress</span></span>                            | <span data-ttu-id="45466-368">Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="45466-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="45466-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="45466-370">clusterBy</span></span>                                 | <span data-ttu-id="45466-371">Tillgängligt om entityType är ett  *multicluster*.</span><span class="sxs-lookup"><span data-stu-id="45466-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="45466-372">Satt P2SenderDomain; Innehålls</span><span class="sxs-lookup"><span data-stu-id="45466-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="45466-373">avsändare</span><span class="sxs-lookup"><span data-stu-id="45466-373">sender</span></span>                                    | <span data-ttu-id="45466-374">Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.</span><span class="sxs-lookup"><span data-stu-id="45466-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="45466-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="45466-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="45466-376">Recipient</span><span class="sxs-lookup"><span data-stu-id="45466-376">recipient</span></span>                                 | <span data-ttu-id="45466-377">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="45466-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="45466-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="45466-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="45466-379">satt</span><span class="sxs-lookup"><span data-stu-id="45466-379">subject</span></span>                                   | <span data-ttu-id="45466-380">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="45466-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="45466-381">\[EXTERN \] uppmärksamhet</span><span class="sxs-lookup"><span data-stu-id="45466-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="45466-382">deliveryAction</span></span>                            | <span data-ttu-id="45466-383">Tillgängligt om entityType är ett *meddelande*.</span><span class="sxs-lookup"><span data-stu-id="45466-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="45466-384">Levereras</span><span class="sxs-lookup"><span data-stu-id="45466-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="45466-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="45466-385">securityGroupId</span></span>                           | <span data-ttu-id="45466-386">Tillgänglig om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="45466-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="45466-387">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="45466-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="45466-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="45466-388">securityGroupName</span></span>                         | <span data-ttu-id="45466-389">Tillgänglig om entityType är  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="45466-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="45466-390">Operatörer för nätverks konfiguration</span><span class="sxs-lookup"><span data-stu-id="45466-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="45466-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="45466-391">registryHive</span></span>                              | <span data-ttu-id="45466-392">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="45466-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-393">lokala HKEY- \_ \_ datorer</span><span class="sxs-lookup"><span data-stu-id="45466-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="45466-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="45466-394">registryKey</span></span>                               | <span data-ttu-id="45466-395">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="45466-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="45466-396">PROGRAM vara \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="45466-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="45466-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="45466-397">registryValueType</span></span>                         | <span data-ttu-id="45466-398">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="45466-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-399">Sträng</span><span class="sxs-lookup"><span data-stu-id="45466-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="45466-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="45466-400">registryValue</span></span>                             | <span data-ttu-id="45466-401">Tillgängligt om entityType är  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="45466-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="45466-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="45466-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="45466-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="45466-403">deviceId</span></span>                                  | <span data-ttu-id="45466-404">ID, om sådant finns, för enheten som är relaterad till enheten.</span><span class="sxs-lookup"><span data-stu-id="45466-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="45466-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="45466-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="45466-406">Exempel</span><span class="sxs-lookup"><span data-stu-id="45466-406">Example</span></span>

<span data-ttu-id="45466-407">**Ställning**</span><span class="sxs-lookup"><span data-stu-id="45466-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="45466-408">**Interimssvar**</span><span class="sxs-lookup"><span data-stu-id="45466-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="45466-409">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="45466-409">Related topic</span></span>
- [<span data-ttu-id="45466-410">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="45466-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="45466-411">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="45466-411">Update incident</span></span>](api-update-incidents.md)
