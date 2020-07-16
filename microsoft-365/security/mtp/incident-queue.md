---
title: Prioritera incidenter i Microsofts hotskydd
description: Lär dig hur du prioriterar incidenter från incidentkön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, brevlåda, e-post, incidenter
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
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148142"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="1bd64-104">Prioritera incidenter i Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="1bd64-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="1bd64-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="1bd64-105">**Applies to:**</span></span>
- <span data-ttu-id="1bd64-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="1bd64-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="1bd64-107">Microsoft Threat Protection tillämpar korrelationsanalys och sammanställer alla relaterade aviseringar och undersökningar från olika produkter till en incident.</span><span class="sxs-lookup"><span data-stu-id="1bd64-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="1bd64-108">Microsoft Threat Protection utlöser också unika aviseringar om aktiviteter som endast kan identifieras som skadliga med tanke på den heltäckande synlighet som Microsoft Threat Protection har över hela dödsboet och produktpaketet.</span><span class="sxs-lookup"><span data-stu-id="1bd64-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="1bd64-109">På så sätt berättar Microsoft Threat Protection den bredare attackhistorien, vilket gör det möjligt för en säkerhetsoperationsanalytiker att förstå och hantera komplexa hot i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="1bd64-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="1bd64-110">**I kön Incidenter** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="1bd64-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="1bd64-111">Det hjälper dig att sortera igenom incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhetssvar.</span><span class="sxs-lookup"><span data-stu-id="1bd64-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Bild av incidentkö](../../media/incidents-queue.png) 

<span data-ttu-id="1bd64-113">Som standard visar kön i Säkerhetscentret Microsoft 365 incidenter som har setts under de senaste 30 dagarna, med den senaste incidenten som visas högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.</span><span class="sxs-lookup"><span data-stu-id="1bd64-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="1bd64-114">Incidentkön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper hos incidenten eller de inneslutna entiteterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.</span><span class="sxs-lookup"><span data-stu-id="1bd64-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="1bd64-115">För ytterligare synlighet via ett ögonkast genererar automatisk incidentnamn, som för närvarande finns i offentlig förhandsversion, incidentnamn baserat på varningsattribut som antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="1bd64-115">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="1bd64-116">På så sätt kan du snabbt förstå omfattningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="1bd64-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1bd64-117">Till exempel: *Flerstegsincident på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="1bd64-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1bd64-118">Incidenter som fanns före utrullningen av automatisk incidentnamn kommer inte att få sitt namn ändrat.</span><span class="sxs-lookup"><span data-stu-id="1bd64-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1bd64-119">Läs mer om [hur du aktiverar förhandsgranskningsfunktioner](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="1bd64-119">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

<span data-ttu-id="1bd64-120">Incidentkön visar också flera filtreringsalternativ, som när du används, gör att du kan välja att utföra ett brett svep av alla befintliga incidenter i din miljö, eller besluta att fokusera på ett visst scenario eller hot.</span><span class="sxs-lookup"><span data-stu-id="1bd64-120">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1bd64-121">Om du använder filter i incidentkön kan du avgöra vilken incident som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="1bd64-121">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1bd64-122">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="1bd64-122">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="1bd64-123">Status</span><span class="sxs-lookup"><span data-stu-id="1bd64-123">Status</span></span>
<span data-ttu-id="1bd64-124">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="1bd64-124">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="1bd64-125">Svårighetsgrad</span><span class="sxs-lookup"><span data-stu-id="1bd64-125">Severity</span></span>
<span data-ttu-id="1bd64-126">Hur allvarlig en incident är är ett tecken på vilken inverkan den kan ha i dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="1bd64-126">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="1bd64-127">Ju högre svårighetsgrad desto större inverkan och vanligtvis kräver den mest omedelbara uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="1bd64-127">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="1bd64-128">Tilldelad till (ägare)</span><span class="sxs-lookup"><span data-stu-id="1bd64-128">Assigned to (owner)</span></span>
<span data-ttu-id="1bd64-129">Du kan välja att filtrera listan genom att välja tilldelad till någon eller de som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="1bd64-129">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="1bd64-130">Flera aviseringar</span><span class="sxs-lookup"><span data-stu-id="1bd64-130">Multiple alerts</span></span> 
<span data-ttu-id="1bd64-131">Filtrera om du bara vill visa incidenter som innehåller mer än en avisering.</span><span class="sxs-lookup"><span data-stu-id="1bd64-131">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="1bd64-132">Detta kan vara en indikation på en attack som är mer komplex eller utvecklats i dödskedjan.</span><span class="sxs-lookup"><span data-stu-id="1bd64-132">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="1bd64-133">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="1bd64-133">Multiple service sources</span></span> 
<span data-ttu-id="1bd64-134">Filter för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="1bd64-134">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="1bd64-135">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="1bd64-135">Service sources</span></span>
<span data-ttu-id="1bd64-136">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="1bd64-136">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="1bd64-137">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="1bd64-137">Multiple categories</span></span> 
<span data-ttu-id="1bd64-138">Du kan välja att bara se incidenter som har mappats till flera kategorier av dödskedjan och som potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="1bd64-138">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="1bd64-139">Kategorier</span><span class="sxs-lookup"><span data-stu-id="1bd64-139">Categories</span></span>
<span data-ttu-id="1bd64-140">Välj specifika kategorier för att fokusera på ett visst steg i dödskedjan</span><span class="sxs-lookup"><span data-stu-id="1bd64-140">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1bd64-141">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="1bd64-141">Data sensitivity</span></span>
<span data-ttu-id="1bd64-142">Vissa attacker fokuserar på inriktning för att exfiltrate känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="1bd64-142">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1bd64-143">Genom att använda ett filter för att se om känsliga data är inblandade i incidenten kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioritera att åtgärda dessa incidenter.</span><span class="sxs-lookup"><span data-stu-id="1bd64-143">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="1bd64-144">Gäller endast om Microsofts informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="1bd64-144">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="1bd64-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1bd64-145">Next steps</span></span>
<span data-ttu-id="1bd64-146">När du har fastställt vilken incident som kräver högsta prioritet kan du fortsätta att utföra ytterligare utredningsarbete om en incident.</span><span class="sxs-lookup"><span data-stu-id="1bd64-146">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="1bd64-147">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="1bd64-147">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="1bd64-148">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1bd64-148">Related topics</span></span>
- [<span data-ttu-id="1bd64-149">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="1bd64-149">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1bd64-150">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="1bd64-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1bd64-151">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="1bd64-151">Manage incidents</span></span>](manage-incidents.md)
