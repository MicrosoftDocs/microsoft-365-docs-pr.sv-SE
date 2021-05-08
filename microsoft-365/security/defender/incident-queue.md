---
title: Prioritera ärenden i Microsoft 365 Defender
description: Lär dig hur du filtrerar incidenter från incidentkön i Microsoft 365 Defender
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter, analysera, svara
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 47d066fa20abe963f7afaa3b88cecc96fa6e87fc
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259609"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5d670-104">Prioritera ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d670-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5d670-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5d670-105">**Applies to:**</span></span>
- <span data-ttu-id="5d670-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d670-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5d670-107">Microsoft 365 Defender tillämpar korrelationsanalyser och sammanställer relaterade aviseringar och automatiska undersökningar från olika produkter till ett incident.</span><span class="sxs-lookup"><span data-stu-id="5d670-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="5d670-108">Microsoft 365 Defender utlöser även unika aviseringar för aktiviteter som bara kan identifieras som skadliga givet den synlighet från end-to-end som Microsoft 365 Defender har i hela produktsviten.</span><span class="sxs-lookup"><span data-stu-id="5d670-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="5d670-109">Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d670-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="5d670-110">I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="5d670-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="5d670-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="5d670-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="5d670-112">Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Microsoft 365 säkerhetscenter [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5d670-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5d670-113">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5d670-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="5d670-115">I **avsnittet Senaste incidenter och aviseringar** visas ett diagram över antalet aviseringar som tagits emot och incidenter som skapats de senaste 24 timmarna.</span><span class="sxs-lookup"><span data-stu-id="5d670-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="5d670-116">Som standard visar incidentkön i säkerhetscentret Microsoft 365 incidenter som har inträffat under de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="5d670-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="5d670-117">Det senaste incidenten visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="5d670-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5d670-118">Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="5d670-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="5d670-119">På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter för analys.</span><span class="sxs-lookup"><span data-stu-id="5d670-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="5d670-120">Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="5d670-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5d670-121">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="5d670-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5d670-122">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="5d670-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5d670-123">De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.</span><span class="sxs-lookup"><span data-stu-id="5d670-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5d670-124">I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot.</span><span class="sxs-lookup"><span data-stu-id="5d670-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5d670-125">Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="5d670-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5d670-126">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="5d670-126">Available filters</span></span>

<span data-ttu-id="5d670-127">Från standardkön för incidenter  kan du välja Filter för att visa ett filterfönster där du kan visa en filtrerad uppsättning incidenter.</span><span class="sxs-lookup"><span data-stu-id="5d670-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="5d670-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5d670-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exempel på filterfönstret för incidentkön":::

<span data-ttu-id="5d670-130">I den här tabellen visas de tillgängliga filternamnen.</span><span class="sxs-lookup"><span data-stu-id="5d670-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="5d670-131">Filternamn</span><span class="sxs-lookup"><span data-stu-id="5d670-131">Filter name</span></span> | <span data-ttu-id="5d670-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5d670-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5d670-133">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="5d670-133">Assigned to</span></span> | <span data-ttu-id="5d670-134">Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5d670-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="5d670-135">Kategorier</span><span class="sxs-lookup"><span data-stu-id="5d670-135">Categories</span></span> | <span data-ttu-id="5d670-136">Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="5d670-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="5d670-137">Klassificering</span><span class="sxs-lookup"><span data-stu-id="5d670-137">Classification</span></span> | <span data-ttu-id="5d670-138">Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5d670-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5d670-139">Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="5d670-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="5d670-140">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="5d670-140">Data sensitivity</span></span> | <span data-ttu-id="5d670-141">Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="5d670-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5d670-142">Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.</span><span class="sxs-lookup"><span data-stu-id="5d670-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="5d670-143">Gäller endast om Microsoft informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5d670-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="5d670-144">Enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="5d670-144">Device group</span></span> | <span data-ttu-id="5d670-145">Filtrera efter definierade enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5d670-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="5d670-146">Undersökningstillstånd</span><span class="sxs-lookup"><span data-stu-id="5d670-146">Investigation state</span></span> | <span data-ttu-id="5d670-147">Filtrera ärenden efter status för automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="5d670-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="5d670-148">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="5d670-148">Multiple categories</span></span> | <span data-ttu-id="5d670-149">Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="5d670-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="5d670-150">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="5d670-150">Multiple service sources</span></span>  | <span data-ttu-id="5d670-151">Filtrera för att bara se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="5d670-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="5d670-152">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="5d670-152">OS platform</span></span> | <span data-ttu-id="5d670-153">Begränsa vyn för incidentköer efter operativsystem.</span><span class="sxs-lookup"><span data-stu-id="5d670-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="5d670-154">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="5d670-154">Service sources</span></span> | <span data-ttu-id="5d670-155">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="5d670-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="5d670-156">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="5d670-156">Severity</span></span> | <span data-ttu-id="5d670-157">Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="5d670-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5d670-158">Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="5d670-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="5d670-159">Status</span><span class="sxs-lookup"><span data-stu-id="5d670-159">Status</span></span> | <span data-ttu-id="5d670-160">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="5d670-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="5d670-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5d670-161">Next step</span></span>

<span data-ttu-id="5d670-162">När du har fastställt vilken händelse som kräver högsta prioritet markerar du den och påbörjar [analysen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5d670-162">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d670-163">Se även</span><span class="sxs-lookup"><span data-stu-id="5d670-163">See also</span></span>
- [<span data-ttu-id="5d670-164">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="5d670-164">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5d670-165">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="5d670-165">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5d670-166">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="5d670-166">Manage incidents</span></span>](manage-incidents.md)
