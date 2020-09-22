---
title: Prioritera incidenter i Microsoft Threat Protection
description: Lär dig hur du prioriterar incidenter från incident kön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, post låda, e-post, incidenter
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
ms.openlocfilehash: 403bf35ab976a8e309981e18c8241f1c16b63ccd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200047"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="66509-104">Prioritera incidenter i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66509-104">Prioritize incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66509-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="66509-105">**Applies to:**</span></span>
- <span data-ttu-id="66509-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="66509-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="66509-107">Microsoft Threat Protection använder korrelations analys och aggregerar alla relaterade varningar och undersökningar från olika produkter i en olycka.</span><span class="sxs-lookup"><span data-stu-id="66509-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="66509-108">Microsoft Threat Protection utlöser också unika aviseringar för aktiviteter som endast kan identifieras som skadlig från slut punkt till slut punkt som Microsoft Threat Protection har på hela egendomen och serien med produkter.</span><span class="sxs-lookup"><span data-stu-id="66509-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="66509-109">Genom att göra så får du ett hot-skydd som gör den bredare angrepps berättelsen så att en säkerhets åtgärd kan analyseras för att förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="66509-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="66509-110">**Incident kön** visar en samling händelser som har flaggats från mellan enheter, användare och post lådor.</span><span class="sxs-lookup"><span data-stu-id="66509-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="66509-111">Det hjälper dig att sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="66509-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Bild av kön för incidenter](../../media/incidents-queue.png) 

<span data-ttu-id="66509-113">Som standard visar kön i Microsoft 365 säkerhets Center de händelser som visas under de senaste 30 dagarna, med den senaste incident som visas högst upp i listan så att du kan se de senaste incidenterna först.</span><span class="sxs-lookup"><span data-stu-id="66509-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="66509-114">Incident kön visar anpassningsbara kolumner som gör att du kan visa olika egenskaper för incidenten eller de inneslutna enheterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.</span><span class="sxs-lookup"><span data-stu-id="66509-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="66509-115">Om du vill ha mer insyn är det lätt att namnge fel söknings namn baserat på notifieringsregler, till exempel hur många slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="66509-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="66509-116">Då kan du snabbt förstå omfattningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="66509-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="66509-117">Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="66509-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="66509-118">Händelser som fanns före installationen av automatisk incident namn har inte ändrats.</span><span class="sxs-lookup"><span data-stu-id="66509-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="66509-119">Incident kön visar också flera filtrerings alternativ, som när den används, gör det möjligt för dig att välja att genomföra en bred borttagning av alla befintliga incidenter i miljön eller bestämma dig för ett visst scenario eller hot.</span><span class="sxs-lookup"><span data-stu-id="66509-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="66509-120">Om du använder filter i kön för incidenter kan du avgöra vilken händelse som kräver omedelbar åtgärd.</span><span class="sxs-lookup"><span data-stu-id="66509-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="66509-121">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="66509-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="66509-122">Status</span><span class="sxs-lookup"><span data-stu-id="66509-122">Status</span></span>
<span data-ttu-id="66509-123">Du kan välja att begränsa listan med incidenter baserat på deras status för att se vilka som är aktiva eller stängda.</span><span class="sxs-lookup"><span data-stu-id="66509-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="66509-124">Allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="66509-124">Severity</span></span>
<span data-ttu-id="66509-125">Allvarlighets graden för en olycka är att det påverkar vilken inverkan den kan ha på dina till gångar.</span><span class="sxs-lookup"><span data-stu-id="66509-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="66509-126">Ju högre allvarlighets grad desto större effekt och kräver vanligt vis omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="66509-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="66509-127">Tilldelad (ägare)</span><span class="sxs-lookup"><span data-stu-id="66509-127">Assigned to (owner)</span></span>
<span data-ttu-id="66509-128">Du kan välja att filtrera listan genom att välja tilldelad till vem som helst eller som är tilldelad till dig.</span><span class="sxs-lookup"><span data-stu-id="66509-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="66509-129">Flera aviseringar</span><span class="sxs-lookup"><span data-stu-id="66509-129">Multiple alerts</span></span> 
<span data-ttu-id="66509-130">Filtrera för att se endast händelser som innehåller fler än en avisering.</span><span class="sxs-lookup"><span data-stu-id="66509-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="66509-131">Detta kan vara en indikation på ett angrepp som är mer komplicerat eller som behandlas i Kill-kedjan.</span><span class="sxs-lookup"><span data-stu-id="66509-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="66509-132">Flera tjänst källor</span><span class="sxs-lookup"><span data-stu-id="66509-132">Multiple service sources</span></span> 
<span data-ttu-id="66509-133">Filtrera för att se endast händelser som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="66509-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="66509-134">Tjänste källor</span><span class="sxs-lookup"><span data-stu-id="66509-134">Service sources</span></span>
<span data-ttu-id="66509-135">Genom att välja en specifik källa kan du fokusera på händelser som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="66509-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="66509-136">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="66509-136">Multiple categories</span></span> 
<span data-ttu-id="66509-137">Du kan välja att bara se händelser som har mappats till flera kategorier av Kill-kedjan och kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="66509-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="66509-138">Klasser</span><span class="sxs-lookup"><span data-stu-id="66509-138">Categories</span></span>
<span data-ttu-id="66509-139">Välja specifika kategorier för att fokusera på ett specifikt steg i Kill-kedjan</span><span class="sxs-lookup"><span data-stu-id="66509-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="66509-140">Data känslighet</span><span class="sxs-lookup"><span data-stu-id="66509-140">Data sensitivity</span></span>
<span data-ttu-id="66509-141">Vissa attacker fokuserar på att rikta mot exfiltrate känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="66509-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="66509-142">Genom att använda ett filter för att se om känslig information är involverad i en olycka kan du snabbt avgöra om den känsliga informationen är potentiellt utsatt för att hantera dessa tillbud.</span><span class="sxs-lookup"><span data-stu-id="66509-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="66509-143">Gäller endast om Microsoft Information Protection är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="66509-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="66509-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="66509-144">Next steps</span></span>
<span data-ttu-id="66509-145">När du har fastställt vilken händelse som kräver den högsta prioriteten kan du fortsätta att göra ytterligare utredningar på en olycka.</span><span class="sxs-lookup"><span data-stu-id="66509-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="66509-146">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="66509-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="66509-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="66509-147">Related topics</span></span>
- [<span data-ttu-id="66509-148">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="66509-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="66509-149">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="66509-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="66509-150">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="66509-150">Manage incidents</span></span>](manage-incidents.md)
