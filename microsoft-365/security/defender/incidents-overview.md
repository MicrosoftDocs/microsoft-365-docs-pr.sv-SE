---
title: Incidenter i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor Microsoft 365 säkerhetscenter.
keywords: incidenter, aviseringar, undersöker, analyserar, svar, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
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
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114288"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="e3caf-104">Incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3caf-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3caf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e3caf-105">**Applies to:**</span></span>
- <span data-ttu-id="e3caf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3caf-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="e3caf-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e3caf-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="e3caf-108">Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="e3caf-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="e3caf-109">En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör en attacks historia.</span><span class="sxs-lookup"><span data-stu-id="e3caf-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="e3caf-110">Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="e3caf-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="e3caf-111">Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack.</span><span class="sxs-lookup"><span data-stu-id="e3caf-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="e3caf-112">Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="e3caf-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="e3caf-113">Resultatet är flera aviseringar för flera enheter i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="e3caf-114">Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack, sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.</span><span class="sxs-lookup"><span data-stu-id="e3caf-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

<span data-ttu-id="e3caf-116">Titta på den här korta översikten över incidenter i Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="e3caf-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="e3caf-117">Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="e3caf-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="e3caf-118">Du kan till exempel se:</span><span class="sxs-lookup"><span data-stu-id="e3caf-118">For example, you can see:</span></span>

- <span data-ttu-id="e3caf-119">Var attacken började.</span><span class="sxs-lookup"><span data-stu-id="e3caf-119">Where the attack started.</span></span>
- <span data-ttu-id="e3caf-120">Vilka taktiker användes.</span><span class="sxs-lookup"><span data-stu-id="e3caf-120">What tactics were used.</span></span>
- <span data-ttu-id="e3caf-121">Hur långt attacken har varit i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e3caf-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="e3caf-122">Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades.</span><span class="sxs-lookup"><span data-stu-id="e3caf-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="e3caf-123">Alla data som är associerade med attacken.</span><span class="sxs-lookup"><span data-stu-id="e3caf-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="e3caf-124">Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender undersöka och åtgärda varningar automatiskt och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="e3caf-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="e3caf-125">Du kan också utföra ytterligare åtgärdssteg för att lösa attacken.</span><span class="sxs-lookup"><span data-stu-id="e3caf-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="e3caf-126">Incidenter och aviseringar på Microsoft 365 säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="e3caf-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="e3caf-127">Du hanterar incidenter **från & och > incidenter** i snabbstarten av säkerhetscentret i Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e3caf-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="e3caf-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="e3caf-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="e3caf-130">När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="e3caf-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="e3caf-132">Ytterligare flikar för en händelse är:</span><span class="sxs-lookup"><span data-stu-id="e3caf-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="e3caf-133">Varningar</span><span class="sxs-lookup"><span data-stu-id="e3caf-133">Alerts</span></span> 

  <span data-ttu-id="e3caf-134">Alla aviseringar som rör händelsen och deras information.</span><span class="sxs-lookup"><span data-stu-id="e3caf-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="e3caf-135">Enheter</span><span class="sxs-lookup"><span data-stu-id="e3caf-135">Devices</span></span>

  <span data-ttu-id="e3caf-136">Alla enheter som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="e3caf-137">Användare</span><span class="sxs-lookup"><span data-stu-id="e3caf-137">Users</span></span>

  <span data-ttu-id="e3caf-138">Alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="e3caf-139">Postlådor</span><span class="sxs-lookup"><span data-stu-id="e3caf-139">Mailboxes</span></span>

  <span data-ttu-id="e3caf-140">Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="e3caf-141">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="e3caf-141">Investigations</span></span>

  <span data-ttu-id="e3caf-142">Alla automatiserade undersökningar som utlösts av aviseringar i händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="e3caf-143">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="e3caf-143">Evidence and Response</span></span>

  <span data-ttu-id="e3caf-144">Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="e3caf-145">Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="e3caf-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en incident och dess data till flikarna för en händelse i Microsoft 365 säkerhetscenter":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="e3caf-147">Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3caf-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="e3caf-148">Här är ett exempel på ett arbetsflöde för att svara på incidenter i Microsoft 365 med Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="e3caf-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

<span data-ttu-id="e3caf-150">Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar.</span><span class="sxs-lookup"><span data-stu-id="e3caf-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="e3caf-151">Det här är en kombination av:</span><span class="sxs-lookup"><span data-stu-id="e3caf-151">This is a combination of:</span></span>

- <span data-ttu-id="e3caf-152">[Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.</span><span class="sxs-lookup"><span data-stu-id="e3caf-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="e3caf-153">[Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="e3caf-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="e3caf-154">Påbörja en analys av en attack [och avisering för varje incident:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="e3caf-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="e3caf-155">a.</span><span class="sxs-lookup"><span data-stu-id="e3caf-155">a.</span></span> <span data-ttu-id="e3caf-156">Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).</span><span class="sxs-lookup"><span data-stu-id="e3caf-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="e3caf-157">b.</span><span class="sxs-lookup"><span data-stu-id="e3caf-157">b.</span></span> <span data-ttu-id="e3caf-158">Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).</span><span class="sxs-lookup"><span data-stu-id="e3caf-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="e3caf-159">c.</span><span class="sxs-lookup"><span data-stu-id="e3caf-159">c.</span></span> <span data-ttu-id="e3caf-160">Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**</span><span class="sxs-lookup"><span data-stu-id="e3caf-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="e3caf-161">d.</span><span class="sxs-lookup"><span data-stu-id="e3caf-161">d.</span></span> <span data-ttu-id="e3caf-162">Se hur Microsoft 365 Defender automatiskt har löst vissa aviseringar **(fliken Undersökningar).**</span><span class="sxs-lookup"><span data-stu-id="e3caf-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="e3caf-163">e.</span><span class="sxs-lookup"><span data-stu-id="e3caf-163">e.</span></span> <span data-ttu-id="e3caf-164">Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).</span><span class="sxs-lookup"><span data-stu-id="e3caf-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="e3caf-165">Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.</span><span class="sxs-lookup"><span data-stu-id="e3caf-165">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="e3caf-166">Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3caf-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="e3caf-167">[Lös](manage-incidents.md#resolve-incident) incidenten och ta dig tid för efter incidentinlärning att:</span><span class="sxs-lookup"><span data-stu-id="e3caf-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="e3caf-168">Förstå typen av attack och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="e3caf-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="e3caf-169">Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.</span><span class="sxs-lookup"><span data-stu-id="e3caf-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="e3caf-170">Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.</span><span class="sxs-lookup"><span data-stu-id="e3caf-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="e3caf-171">Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.</span><span class="sxs-lookup"><span data-stu-id="e3caf-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="e3caf-172">Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.</span><span class="sxs-lookup"><span data-stu-id="e3caf-172">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="e3caf-173">Exempel på säkerhetsåtgärder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3caf-173">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="e3caf-174">Här är ett exempel på säkerhetsåtgärder för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e3caf-174">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

<span data-ttu-id="e3caf-176">Dagliga uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="e3caf-176">Daily tasks can include:</span></span>

- <span data-ttu-id="e3caf-177">[Hantera](manage-incidents.md) incidenter</span><span class="sxs-lookup"><span data-stu-id="e3caf-177">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="e3caf-178">Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="e3caf-178">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="e3caf-179">Gå igenom de senaste [hotanalyserna](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="e3caf-179">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="e3caf-180">[Svara på](investigate-incidents.md) ärenden</span><span class="sxs-lookup"><span data-stu-id="e3caf-180">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="e3caf-181">Månadsvisa uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="e3caf-181">Monthly tasks can include:</span></span>

- <span data-ttu-id="e3caf-182">Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="e3caf-182">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="e3caf-183">Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="e3caf-183">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="e3caf-184">Rapportera till din it-säkerhetshanteringskedja</span><span class="sxs-lookup"><span data-stu-id="e3caf-184">Reporting to your IT security management chain</span></span>

<span data-ttu-id="e3caf-185">Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).</span><span class="sxs-lookup"><span data-stu-id="e3caf-185">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="e3caf-186">Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer.</span><span class="sxs-lookup"><span data-stu-id="e3caf-186">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="e3caf-187">Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e3caf-187">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3caf-188">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e3caf-188">Next steps</span></span>

<span data-ttu-id="e3caf-189">I incidentkön på **sidan Incidenter** visas de senaste incidenterna.</span><span class="sxs-lookup"><span data-stu-id="e3caf-189">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="e3caf-190">Härifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="e3caf-190">From here, you can:</span></span>

- <span data-ttu-id="e3caf-191">Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="e3caf-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="e3caf-192">[Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldelning, klassificera och lägga till taggar och kommentarer för arbetsflödet för incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="e3caf-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="e3caf-193">Utföra en [analys](investigate-incidents.md) av en händelse.</span><span class="sxs-lookup"><span data-stu-id="e3caf-193">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
