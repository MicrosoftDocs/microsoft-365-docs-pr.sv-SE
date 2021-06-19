---
title: Ärenden i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor i Microsoft 365 Defender portalen.
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
ms.openlocfilehash: 3dac22afb074a58ea2afdf842a9a62c6cee77dcc
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022792"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="c9891-104">Ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9891-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9891-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c9891-105">**Applies to:**</span></span>
- <span data-ttu-id="c9891-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9891-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="c9891-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="c9891-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="c9891-108">Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="c9891-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="c9891-109">En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör storyn av en attack.</span><span class="sxs-lookup"><span data-stu-id="c9891-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="c9891-110">Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="c9891-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="c9891-111">Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack.</span><span class="sxs-lookup"><span data-stu-id="c9891-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="c9891-112">Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="c9891-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="c9891-113">Resultatet är flera aviseringar för flera enheter i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c9891-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="c9891-114">Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.</span><span class="sxs-lookup"><span data-stu-id="c9891-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

<span data-ttu-id="c9891-116">Titta på den här korta översikten över incidenter om Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="c9891-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="c9891-117">Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="c9891-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="c9891-118">Du kan till exempel se:</span><span class="sxs-lookup"><span data-stu-id="c9891-118">For example, you can see:</span></span>

- <span data-ttu-id="c9891-119">Var attacken började.</span><span class="sxs-lookup"><span data-stu-id="c9891-119">Where the attack started.</span></span>
- <span data-ttu-id="c9891-120">Vilka taktiker användes.</span><span class="sxs-lookup"><span data-stu-id="c9891-120">What tactics were used.</span></span>
- <span data-ttu-id="c9891-121">Hur långt attacken har varit i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c9891-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="c9891-122">Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades.</span><span class="sxs-lookup"><span data-stu-id="c9891-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="c9891-123">Alla data som är associerade med attacken.</span><span class="sxs-lookup"><span data-stu-id="c9891-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="c9891-124">Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender automatiskt [undersöka och åtgärda](m365d-autoir.md) varningar med hjälp av automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="c9891-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="c9891-125">Du kan också utföra ytterligare åtgärdssteg för att lösa attacken.</span><span class="sxs-lookup"><span data-stu-id="c9891-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c9891-126">Incidenter och aviseringar i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="c9891-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c9891-127">Du hanterar incidenter **från & och > incidenter** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c9891-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="c9891-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c9891-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 Defender portalen":::

<span data-ttu-id="c9891-130">När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="c9891-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 Defender portalen":::

<span data-ttu-id="c9891-132">Ytterligare flikar för en händelse är:</span><span class="sxs-lookup"><span data-stu-id="c9891-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="c9891-133">Varningar</span><span class="sxs-lookup"><span data-stu-id="c9891-133">Alerts</span></span> 

  <span data-ttu-id="c9891-134">Alla aviseringar som rör händelsen och deras information.</span><span class="sxs-lookup"><span data-stu-id="c9891-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="c9891-135">Enheter</span><span class="sxs-lookup"><span data-stu-id="c9891-135">Devices</span></span>

  <span data-ttu-id="c9891-136">Alla enheter som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c9891-137">Användare</span><span class="sxs-lookup"><span data-stu-id="c9891-137">Users</span></span>

  <span data-ttu-id="c9891-138">Alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c9891-139">Postlådor</span><span class="sxs-lookup"><span data-stu-id="c9891-139">Mailboxes</span></span>

  <span data-ttu-id="c9891-140">Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c9891-141">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="c9891-141">Investigations</span></span>

  <span data-ttu-id="c9891-142">Alla automatiserade [undersökningar som](m365d-autoir.md) utlösts av aviseringar i händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="c9891-143">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="c9891-143">Evidence and Response</span></span>

  <span data-ttu-id="c9891-144">Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="c9891-145">Graph (i förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="c9891-145">Graph (in preview)</span></span>

  <span data-ttu-id="c9891-146">En bild som visar kopplingen av aviseringar till de påverkade tillgångarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c9891-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="c9891-147">Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="c9891-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en händelse och dess data till flikarna för en händelse i Microsoft 365 Defender portalen":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="c9891-149">Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9891-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="c9891-150">Här är ett exempel på ett arbetsflöde för att svara på incidenter Microsoft 365 med Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="c9891-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

<span data-ttu-id="c9891-152">Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar.</span><span class="sxs-lookup"><span data-stu-id="c9891-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="c9891-153">Det här är en kombination av:</span><span class="sxs-lookup"><span data-stu-id="c9891-153">This is a combination of:</span></span>

- <span data-ttu-id="c9891-154">[Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.</span><span class="sxs-lookup"><span data-stu-id="c9891-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="c9891-155">[Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="c9891-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="c9891-156">Påbörja en attack och aviseringsundersökning och analys [för varje händelse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c9891-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="c9891-157">Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).</span><span class="sxs-lookup"><span data-stu-id="c9891-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="c9891-158">Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).</span><span class="sxs-lookup"><span data-stu-id="c9891-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="c9891-159">Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**</span><span class="sxs-lookup"><span data-stu-id="c9891-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="c9891-160">Se hur Microsoft 365 Defender har [löst vissa aviseringar](m365d-autoir.md) automatiskt **(fliken Undersökningar).**</span><span class="sxs-lookup"><span data-stu-id="c9891-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="c9891-161">Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).</span><span class="sxs-lookup"><span data-stu-id="c9891-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="c9891-162">Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.</span><span class="sxs-lookup"><span data-stu-id="c9891-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="c9891-163">Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.</span><span class="sxs-lookup"><span data-stu-id="c9891-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="c9891-164">[Lös](manage-incidents.md#resolve-an-incident) incidenten och ta dig tid för efter incidentinlärning att:</span><span class="sxs-lookup"><span data-stu-id="c9891-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="c9891-165">Förstå typen av attack och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="c9891-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="c9891-166">Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.</span><span class="sxs-lookup"><span data-stu-id="c9891-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="c9891-167">Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.</span><span class="sxs-lookup"><span data-stu-id="c9891-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="c9891-168">Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.</span><span class="sxs-lookup"><span data-stu-id="c9891-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="c9891-169">Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.</span><span class="sxs-lookup"><span data-stu-id="c9891-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="c9891-170">Exempel på säkerhetsåtgärder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9891-170">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="c9891-171">Här är ett exempel på säkerhetsåtgärder för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c9891-171">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

<span data-ttu-id="c9891-173">Dagliga uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="c9891-173">Daily tasks can include:</span></span>

- <span data-ttu-id="c9891-174">[Hantera](manage-incidents.md) incidenter</span><span class="sxs-lookup"><span data-stu-id="c9891-174">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="c9891-175">Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md) i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="c9891-175">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="c9891-176">Gå igenom de senaste [hotanalyserna](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="c9891-176">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="c9891-177">[Svara på](investigate-incidents.md) ärenden</span><span class="sxs-lookup"><span data-stu-id="c9891-177">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="c9891-178">Månadsvisa uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="c9891-178">Monthly tasks can include:</span></span>

- <span data-ttu-id="c9891-179">Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="c9891-179">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="c9891-180">Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="c9891-180">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="c9891-181">Rapportera till din it-säkerhetshanteringskedja</span><span class="sxs-lookup"><span data-stu-id="c9891-181">Reporting to your IT security management chain</span></span>

<span data-ttu-id="c9891-182">Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).</span><span class="sxs-lookup"><span data-stu-id="c9891-182">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="c9891-183">Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer.</span><span class="sxs-lookup"><span data-stu-id="c9891-183">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="c9891-184">Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="c9891-184">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9891-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c9891-185">Next steps</span></span>

<span data-ttu-id="c9891-186">**Om du inte har angående** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="c9891-186">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="c9891-187">I [](first-incident-overview.md) genomgången Svara på din första incident finns en guidad genomgång av en typisk process av analys, åtgärder och efter incidentgranskning i Microsoft 365 Defender-portalen med ett exempel på en attack.</span><span class="sxs-lookup"><span data-stu-id="c9891-187">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example of an attack.</span></span>

<span data-ttu-id="c9891-188">**Om du har erfarenhet av** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="c9891-188">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="c9891-189">Kom igång med incidentkön på sidan **Incidenter** i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="c9891-189">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c9891-190">Härifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="c9891-190">From here, you can:</span></span>

  - <span data-ttu-id="c9891-191">Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="c9891-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="c9891-192">[Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldelning, klassificera och lägga till taggar och kommentarer baserat på arbetsflödet för incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="c9891-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="c9891-193">Utföra [undersökningar](investigate-incidents.md) av incidenter.</span><span class="sxs-lookup"><span data-stu-id="c9891-193">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="c9891-194">I de här [spelböckerna för incidenter](/security/compass/incident-response-playbooks) finns detaljerad vägledning för attacker för nätfiske, lösenordsförsök och att bevilja åtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="c9891-194">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

