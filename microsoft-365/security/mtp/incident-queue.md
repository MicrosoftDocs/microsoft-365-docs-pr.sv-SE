---
title: Prioritera incidenter i Microsoft 365 Defender
description: Lär dig hur du filtrerar incidenter från incident kön i Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409261"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f99a2-104">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f99a2-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f99a2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f99a2-105">**Applies to:**</span></span>
- <span data-ttu-id="f99a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f99a2-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f99a2-107">Microsoft 365 Defender använder korrelations analys och aggregerar alla relaterade varningar och undersökningar från olika produkter i en olycka.</span><span class="sxs-lookup"><span data-stu-id="f99a2-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="f99a2-108">Microsoft 365 Defender utlöser också unika aviseringar för aktiviteter som endast kan identifieras som skadlig från slut punkt till slut punkt som Microsoft 365 Defender har på hela egendomen och produkt serien.</span><span class="sxs-lookup"><span data-stu-id="f99a2-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="f99a2-109">Den här vyn ger säkerhets åtgärder som analyserar den större angrepps berättelsen som hjälper dem att förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f99a2-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="f99a2-110">**Incident kön** visar en samling händelser som har flaggats från mellan enheter, användare och post lådor.</span><span class="sxs-lookup"><span data-stu-id="f99a2-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="f99a2-111">Det hjälper dig att sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="f99a2-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Bild av kön för incidenter](../../media/incidents-queue.png) 

<span data-ttu-id="f99a2-113">Som standard visar kön i Microsoft 365 säkerhets Center de händelser som visas under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f99a2-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="f99a2-114">Den senaste incidenten är högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="f99a2-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="f99a2-115">Incident kön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper för incidenten eller de inneslutna entiteterna.</span><span class="sxs-lookup"><span data-stu-id="f99a2-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="f99a2-116">Det hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.</span><span class="sxs-lookup"><span data-stu-id="f99a2-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="f99a2-117">Om du vill ha mer insyn är det lätt att ge automatisk fel sökning namn som baseras på notifieringsregler, till exempel hur många slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="f99a2-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="f99a2-118">Då kan du snabbt förstå omfattningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="f99a2-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="f99a2-119">Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="f99a2-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="f99a2-120">Händelser som fanns före installationen av automatisk incident namn har inte ändrats.</span><span class="sxs-lookup"><span data-stu-id="f99a2-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="f99a2-121">I tillbuds kön visas också flera filtrerings alternativ, som används för att göra en bred borttagning av alla befintliga incidenter i miljön eller bestämma dig för ett visst scenario eller hot.</span><span class="sxs-lookup"><span data-stu-id="f99a2-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="f99a2-122">Om du använder filter i kön för incidenter kan du avgöra vilken händelse som kräver omedelbar åtgärd.</span><span class="sxs-lookup"><span data-stu-id="f99a2-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="f99a2-123">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="f99a2-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="f99a2-124">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="f99a2-124">Assigned to</span></span>
<span data-ttu-id="f99a2-125">Du kan välja att visa meddelanden som har tilldelats dig eller de som hanteras via Automation.</span><span class="sxs-lookup"><span data-stu-id="f99a2-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="f99a2-126">Klasser</span><span class="sxs-lookup"><span data-stu-id="f99a2-126">Categories</span></span>
<span data-ttu-id="f99a2-127">Välj kategorier för att fokusera på specifika taktiker, tekniker eller angrepps komponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="f99a2-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="f99a2-128">Nomenklatur</span><span class="sxs-lookup"><span data-stu-id="f99a2-128">Classification</span></span>
<span data-ttu-id="f99a2-129">Filtrera incidenter baserat på ange klassificeringar för relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="f99a2-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="f99a2-130">Värdena inkluderar True Alerts, false Alerts eller inte.</span><span class="sxs-lookup"><span data-stu-id="f99a2-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="f99a2-131">Data känslighet</span><span class="sxs-lookup"><span data-stu-id="f99a2-131">Data sensitivity</span></span>
<span data-ttu-id="f99a2-132">Vissa attacker fokuserar på att rikta mot exfiltrate känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="f99a2-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="f99a2-133">Genom att använda ett filter för att se om känslig information är involverad i en olycka kan du snabbt avgöra om den känsliga informationen är potentiellt utsatt för att hantera dessa tillbud.</span><span class="sxs-lookup"><span data-stu-id="f99a2-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="f99a2-134">Gäller endast om Microsoft Information Protection är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="f99a2-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="f99a2-135">Enhets grupp</span><span class="sxs-lookup"><span data-stu-id="f99a2-135">Device group</span></span>
<span data-ttu-id="f99a2-136">Filtrera efter definierade enhets grupper.</span><span class="sxs-lookup"><span data-stu-id="f99a2-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="f99a2-137">Gransknings status</span><span class="sxs-lookup"><span data-stu-id="f99a2-137">Investigation state</span></span>
<span data-ttu-id="f99a2-138">Filtrera incidenter genom att automatisera den automatiska undersökningen.</span><span class="sxs-lookup"><span data-stu-id="f99a2-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="f99a2-139">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="f99a2-139">Multiple categories</span></span> 
<span data-ttu-id="f99a2-140">Du kan välja att bara se händelser som har mappats till flera kategorier och det kan leda till större skador.</span><span class="sxs-lookup"><span data-stu-id="f99a2-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="f99a2-141">Flera tjänst källor</span><span class="sxs-lookup"><span data-stu-id="f99a2-141">Multiple service sources</span></span> 
<span data-ttu-id="f99a2-142">Filtrera för att se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slut punkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="f99a2-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="f99a2-143">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="f99a2-143">OS platform</span></span>
<span data-ttu-id="f99a2-144">Begränsa vyn för incident kön efter operativ system.</span><span class="sxs-lookup"><span data-stu-id="f99a2-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="f99a2-145">Tjänste källor</span><span class="sxs-lookup"><span data-stu-id="f99a2-145">Service sources</span></span>
<span data-ttu-id="f99a2-146">Genom att välja en specifik källa kan du fokusera på händelser som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="f99a2-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="f99a2-147">Allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="f99a2-147">Severity</span></span>
<span data-ttu-id="f99a2-148">Allvarlighets graden för en olycka är att det påverkar vilken inverkan den kan ha på dina till gångar.</span><span class="sxs-lookup"><span data-stu-id="f99a2-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="f99a2-149">Ju högre allvarlighets grad desto större betydelse och det är vanligt vis mycket direkt uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="f99a2-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="f99a2-150">Status</span><span class="sxs-lookup"><span data-stu-id="f99a2-150">Status</span></span>
<span data-ttu-id="f99a2-151">Du kan välja att begränsa listan med incidenter baserat på deras status för att se vilka som är aktiva eller stängda.</span><span class="sxs-lookup"><span data-stu-id="f99a2-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="f99a2-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f99a2-152">Next steps</span></span>
<span data-ttu-id="f99a2-153">När du har fastställt vilken händelse som kräver den högsta prioriteten kan du fortsätta att göra ytterligare utredningar på en olycka.</span><span class="sxs-lookup"><span data-stu-id="f99a2-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="f99a2-154">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="f99a2-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="f99a2-155">Se även</span><span class="sxs-lookup"><span data-stu-id="f99a2-155">See also</span></span>
- [<span data-ttu-id="f99a2-156">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="f99a2-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f99a2-157">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="f99a2-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f99a2-158">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="f99a2-158">Manage incidents</span></span>](manage-incidents.md)
