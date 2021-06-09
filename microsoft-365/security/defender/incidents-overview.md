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
ms.openlocfilehash: 9970bb6d410f39ff5d796dec678a750342f0f599
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842032"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="ceef8-104">Incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceef8-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ceef8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ceef8-105">**Applies to:**</span></span>
- <span data-ttu-id="ceef8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceef8-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="ceef8-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="ceef8-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="ceef8-108">Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="ceef8-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="ceef8-109">En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör en attacks historia.</span><span class="sxs-lookup"><span data-stu-id="ceef8-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="ceef8-110">Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="ceef8-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="ceef8-111">Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack.</span><span class="sxs-lookup"><span data-stu-id="ceef8-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="ceef8-112">Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="ceef8-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="ceef8-113">Resultatet är flera aviseringar för flera enheter i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="ceef8-114">Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack, sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.</span><span class="sxs-lookup"><span data-stu-id="ceef8-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

<span data-ttu-id="ceef8-116">Titta på den här korta översikten över incidenter i Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="ceef8-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="ceef8-117">Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="ceef8-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="ceef8-118">Du kan till exempel se:</span><span class="sxs-lookup"><span data-stu-id="ceef8-118">For example, you can see:</span></span>

- <span data-ttu-id="ceef8-119">Var attacken började.</span><span class="sxs-lookup"><span data-stu-id="ceef8-119">Where the attack started.</span></span>
- <span data-ttu-id="ceef8-120">Vilka taktiker användes.</span><span class="sxs-lookup"><span data-stu-id="ceef8-120">What tactics were used.</span></span>
- <span data-ttu-id="ceef8-121">Hur långt attacken har varit i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="ceef8-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="ceef8-122">Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades.</span><span class="sxs-lookup"><span data-stu-id="ceef8-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="ceef8-123">Alla data som är associerade med attacken.</span><span class="sxs-lookup"><span data-stu-id="ceef8-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="ceef8-124">Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender [undersöka och åtgärda](m365d-autoir.md) varningar automatiskt och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="ceef8-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="ceef8-125">Du kan också utföra ytterligare åtgärdssteg för att lösa attacken.</span><span class="sxs-lookup"><span data-stu-id="ceef8-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="ceef8-126">Incidenter och aviseringar på Microsoft 365 säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="ceef8-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="ceef8-127">Du hanterar incidenter **från & och > incidenter** i snabbstarten av säkerhetscentret i Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ceef8-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="ceef8-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ceef8-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="ceef8-130">När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="ceef8-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="ceef8-132">Ytterligare flikar för en händelse är:</span><span class="sxs-lookup"><span data-stu-id="ceef8-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="ceef8-133">Varningar</span><span class="sxs-lookup"><span data-stu-id="ceef8-133">Alerts</span></span> 

  <span data-ttu-id="ceef8-134">Alla aviseringar som rör händelsen och deras information.</span><span class="sxs-lookup"><span data-stu-id="ceef8-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="ceef8-135">Enheter</span><span class="sxs-lookup"><span data-stu-id="ceef8-135">Devices</span></span>

  <span data-ttu-id="ceef8-136">Alla enheter som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ceef8-137">Användare</span><span class="sxs-lookup"><span data-stu-id="ceef8-137">Users</span></span>

  <span data-ttu-id="ceef8-138">Alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ceef8-139">Postlådor</span><span class="sxs-lookup"><span data-stu-id="ceef8-139">Mailboxes</span></span>

  <span data-ttu-id="ceef8-140">Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="ceef8-141">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="ceef8-141">Investigations</span></span>

  <span data-ttu-id="ceef8-142">Alla automatiserade [undersökningar som](m365d-autoir.md) utlösts av aviseringar i händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="ceef8-143">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="ceef8-143">Evidence and Response</span></span>

  <span data-ttu-id="ceef8-144">Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="ceef8-145">Graph (i förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="ceef8-145">Graph (in preview)</span></span>

  <span data-ttu-id="ceef8-146">En bild som visar kopplingen av aviseringar till de påverkade tillgångarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="ceef8-147">Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ceef8-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en incident och dess data till flikarna för en händelse i Microsoft 365 säkerhetscenter":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="ceef8-149">Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceef8-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="ceef8-150">Här är ett exempel på ett arbetsflöde för att svara på incidenter i Microsoft 365 med Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ceef8-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

<span data-ttu-id="ceef8-152">Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar.</span><span class="sxs-lookup"><span data-stu-id="ceef8-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="ceef8-153">Det här är en kombination av:</span><span class="sxs-lookup"><span data-stu-id="ceef8-153">This is a combination of:</span></span>

- <span data-ttu-id="ceef8-154">[Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.</span><span class="sxs-lookup"><span data-stu-id="ceef8-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="ceef8-155">[Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="ceef8-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="ceef8-156">Påbörja en attack och aviseringsundersökning och analys [för varje händelse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="ceef8-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="ceef8-157">a.</span><span class="sxs-lookup"><span data-stu-id="ceef8-157">a.</span></span> <span data-ttu-id="ceef8-158">Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).</span><span class="sxs-lookup"><span data-stu-id="ceef8-158">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="ceef8-159">b.</span><span class="sxs-lookup"><span data-stu-id="ceef8-159">b.</span></span> <span data-ttu-id="ceef8-160">Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).</span><span class="sxs-lookup"><span data-stu-id="ceef8-160">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="ceef8-161">c.</span><span class="sxs-lookup"><span data-stu-id="ceef8-161">c.</span></span> <span data-ttu-id="ceef8-162">Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**</span><span class="sxs-lookup"><span data-stu-id="ceef8-162">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="ceef8-163">d.</span><span class="sxs-lookup"><span data-stu-id="ceef8-163">d.</span></span> <span data-ttu-id="ceef8-164">Se hur Microsoft 365 Defender har [löst vissa aviseringar automatiskt](m365d-autoir.md) **(fliken Undersökningar).**</span><span class="sxs-lookup"><span data-stu-id="ceef8-164">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="ceef8-165">e.</span><span class="sxs-lookup"><span data-stu-id="ceef8-165">e.</span></span> <span data-ttu-id="ceef8-166">Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).</span><span class="sxs-lookup"><span data-stu-id="ceef8-166">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="ceef8-167">Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.</span><span class="sxs-lookup"><span data-stu-id="ceef8-167">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="ceef8-168">Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.</span><span class="sxs-lookup"><span data-stu-id="ceef8-168">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="ceef8-169">[Lös](manage-incidents.md#resolve-an-incident) incidenten och ta dig tid för efter incidentinlärning att:</span><span class="sxs-lookup"><span data-stu-id="ceef8-169">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="ceef8-170">Förstå typen av attack och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="ceef8-170">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="ceef8-171">Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.</span><span class="sxs-lookup"><span data-stu-id="ceef8-171">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="ceef8-172">Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.</span><span class="sxs-lookup"><span data-stu-id="ceef8-172">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="ceef8-173">Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.</span><span class="sxs-lookup"><span data-stu-id="ceef8-173">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="ceef8-174">Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.</span><span class="sxs-lookup"><span data-stu-id="ceef8-174">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="ceef8-175">Exempel på säkerhetsåtgärder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceef8-175">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="ceef8-176">Här är ett exempel på säkerhetsåtgärder för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ceef8-176">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

<span data-ttu-id="ceef8-178">Dagliga uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="ceef8-178">Daily tasks can include:</span></span>

- <span data-ttu-id="ceef8-179">[Hantera](manage-incidents.md) incidenter</span><span class="sxs-lookup"><span data-stu-id="ceef8-179">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="ceef8-180">Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md) i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="ceef8-180">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="ceef8-181">Gå igenom de senaste [hotanalyserna](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="ceef8-181">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="ceef8-182">[Svara på](investigate-incidents.md) ärenden</span><span class="sxs-lookup"><span data-stu-id="ceef8-182">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="ceef8-183">Månadsvisa uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="ceef8-183">Monthly tasks can include:</span></span>

- <span data-ttu-id="ceef8-184">Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="ceef8-184">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="ceef8-185">Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="ceef8-185">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="ceef8-186">Rapportera till din it-säkerhetshanteringskedja</span><span class="sxs-lookup"><span data-stu-id="ceef8-186">Reporting to your IT security management chain</span></span>

<span data-ttu-id="ceef8-187">Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).</span><span class="sxs-lookup"><span data-stu-id="ceef8-187">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="ceef8-188">Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer.</span><span class="sxs-lookup"><span data-stu-id="ceef8-188">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="ceef8-189">Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="ceef8-189">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ceef8-190">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ceef8-190">Next steps</span></span>

<span data-ttu-id="ceef8-191">**Om du inte har angående** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="ceef8-191">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="ceef8-192">I [](first-incident-overview.md) genomgången Svara på din första incident finns en guidad genomgång av en typisk process av analys, åtgärder och efter incidentgranskning i säkerhetscentret i Microsoft 365 med ett exempel på en attack.</span><span class="sxs-lookup"><span data-stu-id="ceef8-192">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 security center with an example of an attack.</span></span>

<span data-ttu-id="ceef8-193">**Om du har erfarenhet av** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="ceef8-193">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="ceef8-194">Kom igång med incidentkön på sidan **Incidenter** Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ceef8-194">Get started with the incident queue from the **Incidents** page of the Microsoft 365 security center.</span></span> <span data-ttu-id="ceef8-195">Härifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="ceef8-195">From here, you can:</span></span>

  - <span data-ttu-id="ceef8-196">Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="ceef8-196">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="ceef8-197">[Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldelning, klassificera och lägga till taggar och kommentarer baserat på arbetsflödet för incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="ceef8-197">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="ceef8-198">Utföra [undersökningar](investigate-incidents.md) av incidenter.</span><span class="sxs-lookup"><span data-stu-id="ceef8-198">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="ceef8-199">I de här [spelböckerna för incidenter](/security/compass/incident-response-playbooks) finns detaljerad vägledning för attacker för nätfiske, lösenordsförsök och att bevilja åtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="ceef8-199">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

