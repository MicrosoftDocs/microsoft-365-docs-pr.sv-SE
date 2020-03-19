---
title: Prioritera incidenter i Microsoft Threat Protection
description: Läs om hur du prioriterar incidenter från incidentkön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter
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
ms.openlocfilehash: ef10eede38128bbf9b23537d860113b71f603089
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810762"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="609d0-104">Prioritera incidenter i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="609d0-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="609d0-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="609d0-105">**Applies to:**</span></span>
- <span data-ttu-id="609d0-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="609d0-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="609d0-107">Microsoft Threat Protection tillämpar korrelationsanalys och sammanställer alla relaterade aviseringar och undersökningar från olika produkter till en incident.</span><span class="sxs-lookup"><span data-stu-id="609d0-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="609d0-108">Microsoft Threat Protection utlöser också unika varningar om aktiviteter som endast kan identifieras som skadliga med tanke på den synlighet som Microsoft Threat Protection har över hela egendomen och produktsviten.</span><span class="sxs-lookup"><span data-stu-id="609d0-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="609d0-109">Genom att göra så berättar Microsoft Threat Protection den bredare attackhistorien, vilket gör det möjligt för en säkerhetsverksamhetanalytiker att förstå och hantera komplexa hot i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="609d0-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="609d0-110">**I kön Tillbud** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="609d0-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="609d0-111">Det hjälper dig att sortera igenom incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="609d0-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Bild av incidenter kö](../../media/incidents-queue.png) 

<span data-ttu-id="609d0-113">Som standard visar kön i Microsoft 365 security center incidenter som setts under de senaste 30 dagarna, med den senaste incidenten som visas högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.</span><span class="sxs-lookup"><span data-stu-id="609d0-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="609d0-114">Incidentkön exponerar anpassningsbara kolumner som ger dig insyn i olika egenskaper hos incidenten eller de innehållna entiteterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.</span><span class="sxs-lookup"><span data-stu-id="609d0-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="609d0-115">Incidentkön exponerar också flera filtreringsalternativ, som när den används, gör att du kan välja att utföra ett brett svep av alla befintliga incidenter i din miljö, eller besluta att fokusera på ett visst scenario eller hot.</span><span class="sxs-lookup"><span data-stu-id="609d0-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="609d0-116">Om du använder filter i incidentkön kan du avgöra vilken incident som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="609d0-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="609d0-117">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="609d0-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="609d0-118">Status</span><span class="sxs-lookup"><span data-stu-id="609d0-118">Status</span></span>
<span data-ttu-id="609d0-119">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="609d0-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="609d0-120">Svårighetsgrad</span><span class="sxs-lookup"><span data-stu-id="609d0-120">Severity</span></span>
<span data-ttu-id="609d0-121">Allvarligheten av en incident är ett tecken på vilken inverkan det kan ha i dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="609d0-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="609d0-122">Ju högre svårighetsgrad desto större inverkan och vanligtvis kräver den mest omedelbara uppmärksamheten.</span><span class="sxs-lookup"><span data-stu-id="609d0-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="609d0-123">Tilldelad (ägare)</span><span class="sxs-lookup"><span data-stu-id="609d0-123">Assigned to (owner)</span></span>
<span data-ttu-id="609d0-124">Du kan välja att filtrera listan genom att välja tilldelat till alla eller de som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="609d0-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="609d0-125">Flera aviseringar</span><span class="sxs-lookup"><span data-stu-id="609d0-125">Multiple alerts</span></span> 
<span data-ttu-id="609d0-126">Filtrera om du bara vill se incidenter som innehåller mer än en avisering.</span><span class="sxs-lookup"><span data-stu-id="609d0-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="609d0-127">Detta kan vara en indikation för en attack som är mer komplex eller utvecklats i dödskedjan.</span><span class="sxs-lookup"><span data-stu-id="609d0-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="609d0-128">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="609d0-128">Multiple service sources</span></span> 
<span data-ttu-id="609d0-129">Filtrera om du bara vill se incidenter som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="609d0-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="609d0-130">Servicekällor</span><span class="sxs-lookup"><span data-stu-id="609d0-130">Service sources</span></span>
<span data-ttu-id="609d0-131">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="609d0-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="609d0-132">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="609d0-132">Multiple categories</span></span> 
<span data-ttu-id="609d0-133">Du kan välja att bara se incidenter som har mappats till flera kategorier av dödskedjan och kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="609d0-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="609d0-134">Kategorier</span><span class="sxs-lookup"><span data-stu-id="609d0-134">Categories</span></span>
<span data-ttu-id="609d0-135">Välj specifika kategorier att fokusera på ett specifikt steg i dödskedjan</span><span class="sxs-lookup"><span data-stu-id="609d0-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="609d0-136">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="609d0-136">Data sensitivity</span></span>
<span data-ttu-id="609d0-137">Vissa attacker fokuserar på att rikta för att exfiltrera känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="609d0-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="609d0-138">Genom att använda ett filter för att se om känsliga data är inblandade i incidenten kan du snabbt avgöra om känslig information eventuellt har komprometterats och prioritera att hantera dessa incidenter.</span><span class="sxs-lookup"><span data-stu-id="609d0-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="609d0-139">Gäller endast om MicrosoftS informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="609d0-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="609d0-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="609d0-140">Next steps</span></span>
<span data-ttu-id="609d0-141">När du har fastställt vilken händelse som kräver högsta prioritet kan du fortsätta att göra ytterligare utredningsarbete med en incident.</span><span class="sxs-lookup"><span data-stu-id="609d0-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="609d0-142">Utreda incidenter</span><span class="sxs-lookup"><span data-stu-id="609d0-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="609d0-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="609d0-143">Related topics</span></span>
- [<span data-ttu-id="609d0-144">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="609d0-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="609d0-145">Utreda incidenter</span><span class="sxs-lookup"><span data-stu-id="609d0-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="609d0-146">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="609d0-146">Manage incidents</span></span>](manage-incidents.md)
