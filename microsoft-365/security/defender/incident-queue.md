---
title: Prioritera incidenter i Microsoft 365 Defender
description: Läs om hur du filtrerar incidentköer i Microsoft 365 Defender
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
ms.openlocfilehash: c3efff1e7ebb3a5e868ede018512d12cf38e38fc
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939712"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="4c54c-104">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c54c-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4c54c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4c54c-105">**Applies to:**</span></span>
- <span data-ttu-id="4c54c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c54c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4c54c-107">Microsoft 365 Defender tillämpar korrelationsanalyser och aggregerar relaterade aviseringar och automatiska undersökningar från olika produkter för ett incident.</span><span class="sxs-lookup"><span data-stu-id="4c54c-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="4c54c-108">Microsoft 365 Defender utlöser även unika aviseringar om aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har i hela produktsviten.</span><span class="sxs-lookup"><span data-stu-id="4c54c-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="4c54c-109">Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4c54c-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="4c54c-110">I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="4c54c-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="4c54c-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="4c54c-112">Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4c54c-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="4c54c-114">Som standard visar incidentkön i Microsoft 365-säkerhetscentret incidenter som har setts under de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="4c54c-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="4c54c-115">Det senaste incidenten visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="4c54c-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="4c54c-116">Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="4c54c-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="4c54c-117">På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter för analys.</span><span class="sxs-lookup"><span data-stu-id="4c54c-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="4c54c-118">Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="4c54c-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="4c54c-119">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="4c54c-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="4c54c-120">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="4c54c-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="4c54c-121">De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.</span><span class="sxs-lookup"><span data-stu-id="4c54c-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="4c54c-122">I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot.</span><span class="sxs-lookup"><span data-stu-id="4c54c-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="4c54c-123">Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="4c54c-124">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="4c54c-124">Available filters</span></span>

<span data-ttu-id="4c54c-125">Från standardkön för incidenter  kan du välja Filter för att visa ett filterfönster där du kan visa en filtrerad uppsättning incidenter.</span><span class="sxs-lookup"><span data-stu-id="4c54c-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="4c54c-126">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="4c54c-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exempel på filterfönstret för incidentkön":::

<span data-ttu-id="4c54c-128">I den här tabellen visas de tillgängliga filternamnen.</span><span class="sxs-lookup"><span data-stu-id="4c54c-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="4c54c-129">Filternamn</span><span class="sxs-lookup"><span data-stu-id="4c54c-129">Filter name</span></span> | <span data-ttu-id="4c54c-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4c54c-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="4c54c-131">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="4c54c-131">Assigned to</span></span> | <span data-ttu-id="4c54c-132">Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4c54c-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="4c54c-133">Kategorier</span><span class="sxs-lookup"><span data-stu-id="4c54c-133">Categories</span></span> | <span data-ttu-id="4c54c-134">Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="4c54c-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="4c54c-135">Klassificering</span><span class="sxs-lookup"><span data-stu-id="4c54c-135">Classification</span></span> | <span data-ttu-id="4c54c-136">Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="4c54c-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="4c54c-137">Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="4c54c-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="4c54c-138">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="4c54c-138">Data sensitivity</span></span> | <span data-ttu-id="4c54c-139">Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="4c54c-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="4c54c-140">Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.</span><span class="sxs-lookup"><span data-stu-id="4c54c-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="4c54c-141">Gäller endast om Microsoft informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="4c54c-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="4c54c-142">Enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="4c54c-142">Device group</span></span> | <span data-ttu-id="4c54c-143">Filtrera efter definierade enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="4c54c-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="4c54c-144">Undersökningstillstånd</span><span class="sxs-lookup"><span data-stu-id="4c54c-144">Investigation state</span></span> | <span data-ttu-id="4c54c-145">Filtrera ärenden efter status för automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="4c54c-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="4c54c-146">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="4c54c-146">Multiple categories</span></span> | <span data-ttu-id="4c54c-147">Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="4c54c-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="4c54c-148">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="4c54c-148">Multiple service sources</span></span>  | <span data-ttu-id="4c54c-149">Filtrera för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="4c54c-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="4c54c-150">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="4c54c-150">OS platform</span></span> | <span data-ttu-id="4c54c-151">Begränsa vyn för incidentköer efter operativsystem.</span><span class="sxs-lookup"><span data-stu-id="4c54c-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="4c54c-152">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="4c54c-152">Service sources</span></span> | <span data-ttu-id="4c54c-153">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="4c54c-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="4c54c-154">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="4c54c-154">Severity</span></span> | <span data-ttu-id="4c54c-155">Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4c54c-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="4c54c-156">Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="4c54c-157">Status</span><span class="sxs-lookup"><span data-stu-id="4c54c-157">Status</span></span> | <span data-ttu-id="4c54c-158">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="4c54c-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="4c54c-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4c54c-159">Next step</span></span>

<span data-ttu-id="4c54c-160">När du har fastställt vilken händelse som kräver högsta prioritet markerar du den och påbörjar [analysen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="4c54c-160">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c54c-161">Se även</span><span class="sxs-lookup"><span data-stu-id="4c54c-161">See also</span></span>
- [<span data-ttu-id="4c54c-162">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="4c54c-162">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4c54c-163">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="4c54c-163">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4c54c-164">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="4c54c-164">Manage incidents</span></span>](manage-incidents.md)
