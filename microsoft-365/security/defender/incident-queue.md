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
ms.openlocfilehash: cd571414512ce876e730199b21bf755e4c4b733f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876205"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="c220d-104">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c220d-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c220d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c220d-105">**Applies to:**</span></span>
- <span data-ttu-id="c220d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c220d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c220d-107">Microsoft 365 Defender tillämpar korrelationsanalyser och aggregerar relaterade aviseringar och automatiska undersökningar från olika produkter för ett incident.</span><span class="sxs-lookup"><span data-stu-id="c220d-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="c220d-108">Microsoft 365 Defender utlöser även unika aviseringar om aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har i hela produktsviten.</span><span class="sxs-lookup"><span data-stu-id="c220d-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="c220d-109">Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c220d-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="c220d-110">I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="c220d-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="c220d-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="c220d-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="c220d-112">Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c220d-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="c220d-114">Som standard visar incidentkön i Microsoft 365-säkerhetscentret incidenter som har setts under de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="c220d-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="c220d-115">Det senaste incidenten visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="c220d-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="c220d-116">Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="c220d-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="c220d-117">På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter för analys.</span><span class="sxs-lookup"><span data-stu-id="c220d-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="c220d-118">Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="c220d-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="c220d-119">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="c220d-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="c220d-120">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="c220d-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="c220d-121">De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.</span><span class="sxs-lookup"><span data-stu-id="c220d-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="c220d-122">I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot.</span><span class="sxs-lookup"><span data-stu-id="c220d-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="c220d-123">Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="c220d-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="c220d-124">Tillgängliga filter</span><span class="sxs-lookup"><span data-stu-id="c220d-124">Available filters</span></span>

<span data-ttu-id="c220d-125">Från standardkön för incidenter  kan du välja Filter för att visa ett filterfönster där du kan visa en filtrerad uppsättning incidenter.</span><span class="sxs-lookup"><span data-stu-id="c220d-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="c220d-126">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c220d-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exempel på filterfönstret för incidentkön":::

<span data-ttu-id="c220d-128">I den här tabellen visas de tillgängliga filternamnen.</span><span class="sxs-lookup"><span data-stu-id="c220d-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="c220d-129">Filternamn</span><span class="sxs-lookup"><span data-stu-id="c220d-129">Filter name</span></span> | <span data-ttu-id="c220d-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c220d-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="c220d-131">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="c220d-131">Assigned to</span></span> | <span data-ttu-id="c220d-132">Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c220d-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="c220d-133">Kategorier</span><span class="sxs-lookup"><span data-stu-id="c220d-133">Categories</span></span> | <span data-ttu-id="c220d-134">Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas.</span><span class="sxs-lookup"><span data-stu-id="c220d-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="c220d-135">Klassificering</span><span class="sxs-lookup"><span data-stu-id="c220d-135">Classification</span></span> | <span data-ttu-id="c220d-136">Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c220d-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="c220d-137">Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="c220d-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="c220d-138">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="c220d-138">Data sensitivity</span></span> | <span data-ttu-id="c220d-139">Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="c220d-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="c220d-140">Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.</span><span class="sxs-lookup"><span data-stu-id="c220d-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="c220d-141">Gäller endast om Microsoft informationsskydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c220d-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="c220d-142">Enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="c220d-142">Device group</span></span> | <span data-ttu-id="c220d-143">Filtrera efter definierade enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c220d-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="c220d-144">Undersökningstillstånd</span><span class="sxs-lookup"><span data-stu-id="c220d-144">Investigation state</span></span> | <span data-ttu-id="c220d-145">Filtrera ärenden efter status för automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="c220d-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="c220d-146">Flera kategorier</span><span class="sxs-lookup"><span data-stu-id="c220d-146">Multiple categories</span></span> | <span data-ttu-id="c220d-147">Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada.</span><span class="sxs-lookup"><span data-stu-id="c220d-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="c220d-148">Flera tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="c220d-148">Multiple service sources</span></span>  | <span data-ttu-id="c220d-149">Filtrera för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="c220d-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="c220d-150">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="c220d-150">OS platform</span></span> | <span data-ttu-id="c220d-151">Begränsa vyn för incidentköer efter operativsystem.</span><span class="sxs-lookup"><span data-stu-id="c220d-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="c220d-152">Tjänstkällor</span><span class="sxs-lookup"><span data-stu-id="c220d-152">Service sources</span></span> | <span data-ttu-id="c220d-153">Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan.</span><span class="sxs-lookup"><span data-stu-id="c220d-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="c220d-154">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="c220d-154">Severity</span></span> | <span data-ttu-id="c220d-155">Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar.</span><span class="sxs-lookup"><span data-stu-id="c220d-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="c220d-156">Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="c220d-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="c220d-157">Status</span><span class="sxs-lookup"><span data-stu-id="c220d-157">Status</span></span> | <span data-ttu-id="c220d-158">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="c220d-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="c220d-159">Arbetsflöde för incidentsvar</span><span class="sxs-lookup"><span data-stu-id="c220d-159">Incident response workflow</span></span>

<span data-ttu-id="c220d-160">Här är ett vanligt arbetsflöde för att svara på incidenter:</span><span class="sxs-lookup"><span data-stu-id="c220d-160">Here's the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="c220d-161">Identifiera och prioritera ärenden med högst prioritet för undersökning och lösning.</span><span class="sxs-lookup"><span data-stu-id="c220d-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="c220d-162">Påbörja en undersökning för varje incident med hög [prioritet:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c220d-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="c220d-163">a.</span><span class="sxs-lookup"><span data-stu-id="c220d-163">a.</span></span> <span data-ttu-id="c220d-164">Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).</span><span class="sxs-lookup"><span data-stu-id="c220d-164">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="c220d-165">b.</span><span class="sxs-lookup"><span data-stu-id="c220d-165">b.</span></span> <span data-ttu-id="c220d-166">Börja titta på aviseringarna för att förstå deras ursprung, omfattning och allvarlighetsgrad **(fliken Aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="c220d-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="c220d-167">c.</span><span class="sxs-lookup"><span data-stu-id="c220d-167">c.</span></span> <span data-ttu-id="c220d-168">Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**</span><span class="sxs-lookup"><span data-stu-id="c220d-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="c220d-169">d.</span><span class="sxs-lookup"><span data-stu-id="c220d-169">d.</span></span> <span data-ttu-id="c220d-170">Se hur Microsoft 365 Defender automatiskt har löst vissa aviseringar **(fliken Undersökningar).**</span><span class="sxs-lookup"><span data-stu-id="c220d-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="c220d-171">e.</span><span class="sxs-lookup"><span data-stu-id="c220d-171">e.</span></span> <span data-ttu-id="c220d-172">Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).</span><span class="sxs-lookup"><span data-stu-id="c220d-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

   <span data-ttu-id="c220d-173">När du undersöker bör du vara orolig:</span><span class="sxs-lookup"><span data-stu-id="c220d-173">As you investigate, you should be concerned with:</span></span>

   - <span data-ttu-id="c220d-174">Inneslutning: Minska eventuella ytterligare påverkan på klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c220d-174">Containment: Reducing any additional impact on your tenant.</span></span>
   - <span data-ttu-id="c220d-175">Överflödigt: Ta bort säkerhetshotet.</span><span class="sxs-lookup"><span data-stu-id="c220d-175">Eradication: Removing the security threat.</span></span>
   - <span data-ttu-id="c220d-176">Återställning: Återställa klientorganisationens resurser till det läge de var i före attacken.</span><span class="sxs-lookup"><span data-stu-id="c220d-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

3. <span data-ttu-id="c220d-177">När du har löst problemet bör du ta dig tid att:</span><span class="sxs-lookup"><span data-stu-id="c220d-177">After you resolve the incident, take the time to:</span></span>

   - <span data-ttu-id="c220d-178">Förstå typen av attack och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="c220d-178">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="c220d-179">Undersöka säkerhetsgemenskapen efter en trend för säkerhetsattacker.</span><span class="sxs-lookup"><span data-stu-id="c220d-179">Research the attack in the security community for a security attack trend.</span></span>
   - <span data-ttu-id="c220d-180">Återkalla arbetsflödet som du använde för att lösa problemet och uppdatera standardarbetsflöden och spelböcker efter behov.</span><span class="sxs-lookup"><span data-stu-id="c220d-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>
   - <span data-ttu-id="c220d-181">Bestäm om ändringar i din säkerhetssäkerhet behövs och vidta åtgärder för att implementera dem.</span><span class="sxs-lookup"><span data-stu-id="c220d-181">Determine whether changes in your security posture are needed and take the steps to implement them.</span></span>

<span data-ttu-id="c220d-182">Här följer en sammanfattning av grunderna.</span><span class="sxs-lookup"><span data-stu-id="c220d-182">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Grundläggande process för att undersöka ärenden":::

## <a name="next-step"></a><span data-ttu-id="c220d-184">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c220d-184">Next step</span></span>

<span data-ttu-id="c220d-185">När du har fastställt vilken händelse som kräver högsta prioritet markerar du den och påbörjar [din undersökning](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="c220d-185">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c220d-186">Se även</span><span class="sxs-lookup"><span data-stu-id="c220d-186">See also</span></span>
- [<span data-ttu-id="c220d-187">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="c220d-187">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c220d-188">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="c220d-188">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c220d-189">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="c220d-189">Manage incidents</span></span>](manage-incidents.md)
