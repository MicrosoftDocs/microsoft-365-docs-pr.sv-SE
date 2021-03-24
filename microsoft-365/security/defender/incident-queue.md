---
title: Prioritera incidenter i Microsoft 365 Defender
description: Läs om hur du filtrerar incidentköer i Microsoft 365 Defender
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070058"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="214e8-104">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="214e8-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="214e8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="214e8-105">**Applies to:**</span></span>
- <span data-ttu-id="214e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="214e8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="214e8-107">Microsoft 365 Defender tillämpar korrelationsanalyser och lägger till alla relaterade aviseringar och undersökningar från olika produkter i ett incident.</span><span class="sxs-lookup"><span data-stu-id="214e8-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="214e8-108">Microsoft 365 Defender utlöser även unika aviseringar om aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har över hela webbplatsen och produktsviten.</span><span class="sxs-lookup"><span data-stu-id="214e8-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="214e8-109">Den här vyn ger din säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="214e8-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="214e8-110">I **kön Incidenter** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="214e8-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="214e8-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="214e8-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Bild på incidentköer](../../media/incidents-queue.png) 

<span data-ttu-id="214e8-113">Som standard visar kön i Microsoft 365 säkerhetscenter incidenter som har setts de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="214e8-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="214e8-114">Det senaste incidenten visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="214e8-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="214e8-115">Incidentkön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper för incidenten eller de enheter som finns.</span><span class="sxs-lookup"><span data-stu-id="214e8-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="214e8-116">På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter som ska hanteras.</span><span class="sxs-lookup"><span data-stu-id="214e8-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="214e8-117">Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="214e8-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="214e8-118">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="214e8-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="214e8-119">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="214e8-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="214e8-120">De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.</span><span class="sxs-lookup"><span data-stu-id="214e8-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="214e8-121">I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot.</span><span class="sxs-lookup"><span data-stu-id="214e8-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="214e8-122">Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="214e8-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="214e8-123">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="214e8-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="214e8-124">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="214e8-124">Assigned to</span></span>
<span data-ttu-id="214e8-125">Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="214e8-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="214e8-126">Kategorier</span><span class="sxs-lookup"><span data-stu-id="214e8-126">Categories</span></span>
<span data-ttu-id="214e8-127">Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="214e8-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="214e8-128">Klassificering</span><span class="sxs-lookup"><span data-stu-id="214e8-128">Classification</span></span>
<span data-ttu-id="214e8-129">Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="214e8-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="214e8-130">Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="214e8-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="214e8-131">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="214e8-131">Data sensitivity</span></span>
<span data-ttu-id="214e8-132">Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="214e8-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="214e8-133">Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.</span><span class="sxs-lookup"><span data-stu-id="214e8-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="214e8-134">Gäller endast om Microsoft informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="214e8-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="214e8-135">Enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="214e8-135">Device group</span></span>
<span data-ttu-id="214e8-136">Filtrera efter definierade enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="214e8-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="214e8-137">Undersökningstillstånd</span><span class="sxs-lookup"><span data-stu-id="214e8-137">Investigation state</span></span>
<span data-ttu-id="214e8-138">Filtrera ärenden efter status för automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="214e8-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="214e8-139">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="214e8-139">Multiple categories</span></span> 
<span data-ttu-id="214e8-140">Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="214e8-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="214e8-141">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="214e8-141">Multiple service sources</span></span> 
<span data-ttu-id="214e8-142">Filtrera för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="214e8-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="214e8-143">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="214e8-143">OS platform</span></span>
<span data-ttu-id="214e8-144">Begränsa vyn för incidentköer efter operativsystem.</span><span class="sxs-lookup"><span data-stu-id="214e8-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="214e8-145">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="214e8-145">Service sources</span></span>
<span data-ttu-id="214e8-146">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="214e8-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="214e8-147">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="214e8-147">Severity</span></span>
<span data-ttu-id="214e8-148">Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="214e8-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="214e8-149">Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="214e8-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="214e8-150">Status</span><span class="sxs-lookup"><span data-stu-id="214e8-150">Status</span></span>
<span data-ttu-id="214e8-151">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="214e8-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="214e8-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="214e8-152">Next steps</span></span>
<span data-ttu-id="214e8-153">När du har fastställt vilken händelse som kräver högsta prioritet kan du fortsätta att undersöka en händelse ytterligare.</span><span class="sxs-lookup"><span data-stu-id="214e8-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="214e8-154">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="214e8-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="214e8-155">Se även</span><span class="sxs-lookup"><span data-stu-id="214e8-155">See also</span></span>
- [<span data-ttu-id="214e8-156">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="214e8-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="214e8-157">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="214e8-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="214e8-158">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="214e8-158">Manage incidents</span></span>](manage-incidents.md)
