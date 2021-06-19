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
ms.openlocfilehash: 1240fbb8fb24b7231733db25e9a1859b2a84fd41
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022751"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="8df0a-104">Prioritera ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8df0a-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8df0a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8df0a-105">**Applies to:**</span></span>
- <span data-ttu-id="8df0a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8df0a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8df0a-107">Microsoft 365 Defender tillämpar korrelationsanalys och sammanställer relaterade aviseringar och automatiska undersökningar från olika produkter för ett incident.</span><span class="sxs-lookup"><span data-stu-id="8df0a-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="8df0a-108">Microsoft 365 Defender utlöser även unika aviseringar för aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har i hela produktpaketet.</span><span class="sxs-lookup"><span data-stu-id="8df0a-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="8df0a-109">Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8df0a-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="8df0a-110">I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="8df0a-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="8df0a-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="8df0a-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="8df0a-112">Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8df0a-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="8df0a-113">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="8df0a-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="8df0a-115">I **avsnittet Senaste incidenter och aviseringar** visas ett diagram över antalet aviseringar som tagits emot och incidenter som skapats de senaste 24 timmarna.</span><span class="sxs-lookup"><span data-stu-id="8df0a-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="8df0a-116">Som standard visar incidentkön i Microsoft 365 Defender-portalen incidenter som har setts de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="8df0a-116">By default, the incident queue in the Microsoft 365 Defender portal displays incidents seen in the last six months.</span></span> <span data-ttu-id="8df0a-117">Det senaste incidenten visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="8df0a-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="8df0a-118">Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="8df0a-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="8df0a-119">På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter för analys.</span><span class="sxs-lookup"><span data-stu-id="8df0a-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="8df0a-120">Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="8df0a-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="8df0a-121">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="8df0a-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="8df0a-122">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="8df0a-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="8df0a-123">De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.</span><span class="sxs-lookup"><span data-stu-id="8df0a-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="8df0a-124">I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot.</span><span class="sxs-lookup"><span data-stu-id="8df0a-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="8df0a-125">Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="8df0a-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="8df0a-126">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="8df0a-126">Available filters</span></span>

<span data-ttu-id="8df0a-127">Från standardkön för incidenter  kan du välja Filter för att visa ett filterfönster där du kan visa en filtrerad uppsättning incidenter.</span><span class="sxs-lookup"><span data-stu-id="8df0a-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="8df0a-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="8df0a-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exempel på filterfönstret för incidentkön":::

<span data-ttu-id="8df0a-130">I den här tabellen visas de tillgängliga filternamnen.</span><span class="sxs-lookup"><span data-stu-id="8df0a-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="8df0a-131">Filternamn</span><span class="sxs-lookup"><span data-stu-id="8df0a-131">Filter name</span></span> | <span data-ttu-id="8df0a-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8df0a-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="8df0a-133">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="8df0a-133">Assigned to</span></span> | <span data-ttu-id="8df0a-134">Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8df0a-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="8df0a-135">Kategorier</span><span class="sxs-lookup"><span data-stu-id="8df0a-135">Categories</span></span> | <span data-ttu-id="8df0a-136">Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="8df0a-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="8df0a-137">Klassificering</span><span class="sxs-lookup"><span data-stu-id="8df0a-137">Classification</span></span> | <span data-ttu-id="8df0a-138">Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8df0a-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="8df0a-139">Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="8df0a-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="8df0a-140">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="8df0a-140">Data sensitivity</span></span> | <span data-ttu-id="8df0a-141">Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="8df0a-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="8df0a-142">Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.</span><span class="sxs-lookup"><span data-stu-id="8df0a-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="8df0a-143">Endast tillämpligt om Microsoft Information Protection är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="8df0a-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="8df0a-144">Enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="8df0a-144">Device group</span></span> | <span data-ttu-id="8df0a-145">Filtrera efter definierade enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="8df0a-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="8df0a-146">Undersökningstillstånd</span><span class="sxs-lookup"><span data-stu-id="8df0a-146">Investigation state</span></span> | <span data-ttu-id="8df0a-147">Filtrera ärenden efter status för automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="8df0a-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="8df0a-148">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="8df0a-148">Multiple categories</span></span> | <span data-ttu-id="8df0a-149">Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="8df0a-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="8df0a-150">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="8df0a-150">Multiple service sources</span></span>  | <span data-ttu-id="8df0a-151">Filtrera för att bara se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="8df0a-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="8df0a-152">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="8df0a-152">OS platform</span></span> | <span data-ttu-id="8df0a-153">Begränsa vyn för incidentköer efter operativsystem.</span><span class="sxs-lookup"><span data-stu-id="8df0a-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="8df0a-154">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="8df0a-154">Service sources</span></span> | <span data-ttu-id="8df0a-155">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="8df0a-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="8df0a-156">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="8df0a-156">Severity</span></span> | <span data-ttu-id="8df0a-157">Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="8df0a-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="8df0a-158">Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="8df0a-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="8df0a-159">Status</span><span class="sxs-lookup"><span data-stu-id="8df0a-159">Status</span></span> | <span data-ttu-id="8df0a-160">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="8df0a-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="save-defined-filters-as-urls"></a><span data-ttu-id="8df0a-161">Spara definierade filter som URL-adresser</span><span class="sxs-lookup"><span data-stu-id="8df0a-161">Save defined filters as URLs</span></span>

<span data-ttu-id="8df0a-162">När du har konfigurerat ett användbart filter i kön med incidenter kan du bokmärka URL-adressen till webbläsarfliken eller på annat sätt spara den som en länk på en webbsida, ett Word-dokument eller en valfri plats.</span><span class="sxs-lookup"><span data-stu-id="8df0a-162">Once you have configured a useful filter in the incidents queue, you can bookmark the URL of the browser tab or otherwise save it as a link on a Web page, a Word document, or a place of your choice.</span></span> <span data-ttu-id="8df0a-163">Det ger dig enkelklicksåtkomst till viktiga vyer av incidentkön, till exempel:</span><span class="sxs-lookup"><span data-stu-id="8df0a-163">This will give you single-click access to key views of the incident queue, such as:</span></span>

- <span data-ttu-id="8df0a-164">Nya ärenden</span><span class="sxs-lookup"><span data-stu-id="8df0a-164">New incidents</span></span>
- <span data-ttu-id="8df0a-165">Incidenter med hög allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="8df0a-165">High-severity incidents</span></span>
- <span data-ttu-id="8df0a-166">Incidenter som inte tilldelats</span><span class="sxs-lookup"><span data-stu-id="8df0a-166">Unassigned incidents</span></span>
- <span data-ttu-id="8df0a-167">Hög allvarlighetsgrad, incidenter som inte tilldelats</span><span class="sxs-lookup"><span data-stu-id="8df0a-167">High-severity, unassigned incidents</span></span>
- <span data-ttu-id="8df0a-168">Incidenter som tilldelats till mig</span><span class="sxs-lookup"><span data-stu-id="8df0a-168">Incidents assigned to me</span></span>
- <span data-ttu-id="8df0a-169">Incidenter som tilldelats till mig och för Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8df0a-169">Incidents assigned to me and for Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8df0a-170">Ärenden med en viss tagg eller taggar</span><span class="sxs-lookup"><span data-stu-id="8df0a-170">Incidents with a specific tag or tags</span></span>
- <span data-ttu-id="8df0a-171">Ärenden med en specifik hotkategori</span><span class="sxs-lookup"><span data-stu-id="8df0a-171">Incidents with a specific threat category</span></span>
- <span data-ttu-id="8df0a-172">Ärenden med specifika associerade hot</span><span class="sxs-lookup"><span data-stu-id="8df0a-172">Incidents with a specific associated threat</span></span>
- <span data-ttu-id="8df0a-173">Incidenter med en specifik aktör</span><span class="sxs-lookup"><span data-stu-id="8df0a-173">Incidents with a specific actor</span></span>

<span data-ttu-id="8df0a-174">När du har sammanställt och lagrat listan med användbara filtervyer som URL-adresser [](manage-incidents.md) kan du använda den för att snabbt bearbeta och prioritera incidenterna i kön och hantera dem för efterföljande analys.</span><span class="sxs-lookup"><span data-stu-id="8df0a-174">Once you have compiled and stored your list of useful filter views as URLs, you can use it quickly process and prioritize the incidents in your queue and [manage](manage-incidents.md) them for subsequent analysis.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8df0a-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8df0a-175">Next steps</span></span>

<span data-ttu-id="8df0a-176">När du har fastställt vilken händelse som kräver högst prioritet, markerar du den och gör följande:</span><span class="sxs-lookup"><span data-stu-id="8df0a-176">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="8df0a-177">[Hantera](manage-incidents.md) egenskaperna för incidenten för taggar, tilldelning, omedelbar lösning för falska positiva incidenter och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="8df0a-177">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="8df0a-178">Påbörja din [undersökningar](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="8df0a-178">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8df0a-179">Se även</span><span class="sxs-lookup"><span data-stu-id="8df0a-179">See also</span></span>
- [<span data-ttu-id="8df0a-180">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="8df0a-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8df0a-181">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="8df0a-181">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="8df0a-182">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="8df0a-182">Investigate incidents</span></span>](investigate-incidents.md)
