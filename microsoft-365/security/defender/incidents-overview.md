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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028529"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="42e0e-104">Ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42e0e-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42e0e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="42e0e-105">**Applies to:**</span></span>
- <span data-ttu-id="42e0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42e0e-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="42e0e-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="42e0e-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="42e0e-108">Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="42e0e-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="42e0e-109">En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör storyn av en attack.</span><span class="sxs-lookup"><span data-stu-id="42e0e-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="42e0e-110">Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="42e0e-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="42e0e-111">Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack.</span><span class="sxs-lookup"><span data-stu-id="42e0e-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="42e0e-112">Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="42e0e-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="42e0e-113">Resultatet är flera aviseringar för flera enheter i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="42e0e-114">Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.</span><span class="sxs-lookup"><span data-stu-id="42e0e-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

<span data-ttu-id="42e0e-116">Titta på den här korta översikten över incidenter om Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="42e0e-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="42e0e-117">Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="42e0e-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="42e0e-118">Du kan till exempel se:</span><span class="sxs-lookup"><span data-stu-id="42e0e-118">For example, you can see:</span></span>

- <span data-ttu-id="42e0e-119">Var attacken började.</span><span class="sxs-lookup"><span data-stu-id="42e0e-119">Where the attack started.</span></span>
- <span data-ttu-id="42e0e-120">Vilka taktiker användes.</span><span class="sxs-lookup"><span data-stu-id="42e0e-120">What tactics were used.</span></span>
- <span data-ttu-id="42e0e-121">Hur långt attacken har varit i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="42e0e-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="42e0e-122">Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades.</span><span class="sxs-lookup"><span data-stu-id="42e0e-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="42e0e-123">Alla data som är associerade med attacken.</span><span class="sxs-lookup"><span data-stu-id="42e0e-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="42e0e-124">Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender automatiskt [undersöka och åtgärda](m365d-autoir.md) varningar med hjälp av automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="42e0e-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="42e0e-125">Du kan också utföra ytterligare åtgärdssteg för att lösa attacken.</span><span class="sxs-lookup"><span data-stu-id="42e0e-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="42e0e-126">Incidenter och aviseringar i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="42e0e-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="42e0e-127">Du hanterar incidenter **från & och > incidenter** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="42e0e-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="42e0e-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="42e0e-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 Defender portalen":::

<span data-ttu-id="42e0e-130">När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="42e0e-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 Defender portalen":::

<span data-ttu-id="42e0e-132">Ytterligare flikar för en händelse är:</span><span class="sxs-lookup"><span data-stu-id="42e0e-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="42e0e-133">Varningar</span><span class="sxs-lookup"><span data-stu-id="42e0e-133">Alerts</span></span> 

  <span data-ttu-id="42e0e-134">Alla aviseringar som rör händelsen och deras information.</span><span class="sxs-lookup"><span data-stu-id="42e0e-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="42e0e-135">Enheter</span><span class="sxs-lookup"><span data-stu-id="42e0e-135">Devices</span></span>

  <span data-ttu-id="42e0e-136">Alla enheter som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="42e0e-137">Användare</span><span class="sxs-lookup"><span data-stu-id="42e0e-137">Users</span></span>

  <span data-ttu-id="42e0e-138">Alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="42e0e-139">Postlådor</span><span class="sxs-lookup"><span data-stu-id="42e0e-139">Mailboxes</span></span>

  <span data-ttu-id="42e0e-140">Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="42e0e-141">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="42e0e-141">Investigations</span></span>

  <span data-ttu-id="42e0e-142">Alla automatiserade [undersökningar som](m365d-autoir.md) utlösts av aviseringar i händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="42e0e-143">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="42e0e-143">Evidence and Response</span></span>

  <span data-ttu-id="42e0e-144">Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="42e0e-145">Graph (i förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="42e0e-145">Graph (in preview)</span></span>

  <span data-ttu-id="42e0e-146">En bild som visar kopplingen av aviseringar till de påverkade tillgångarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="42e0e-147">Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en händelse och dess data till flikarna för en händelse i Microsoft 365 Defender portalen":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="42e0e-149">Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42e0e-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="42e0e-150">Här är ett exempel på ett arbetsflöde för att svara på incidenter Microsoft 365 med Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

<span data-ttu-id="42e0e-152">Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar.</span><span class="sxs-lookup"><span data-stu-id="42e0e-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="42e0e-153">Det här är en kombination av:</span><span class="sxs-lookup"><span data-stu-id="42e0e-153">This is a combination of:</span></span>

- <span data-ttu-id="42e0e-154">[Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.</span><span class="sxs-lookup"><span data-stu-id="42e0e-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="42e0e-155">[Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="42e0e-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="42e0e-156">Påbörja en attack och aviseringsundersökning och analys [för varje händelse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="42e0e-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="42e0e-157">Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).</span><span class="sxs-lookup"><span data-stu-id="42e0e-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="42e0e-158">Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).</span><span class="sxs-lookup"><span data-stu-id="42e0e-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="42e0e-159">Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**</span><span class="sxs-lookup"><span data-stu-id="42e0e-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="42e0e-160">Se hur Microsoft 365 Defender har [löst vissa aviseringar](m365d-autoir.md) automatiskt **(fliken Undersökningar).**</span><span class="sxs-lookup"><span data-stu-id="42e0e-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="42e0e-161">Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).</span><span class="sxs-lookup"><span data-stu-id="42e0e-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="42e0e-162">Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.</span><span class="sxs-lookup"><span data-stu-id="42e0e-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="42e0e-163">Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="42e0e-164">[Lös](manage-incidents.md#resolve-an-incident) incidenten och ta dig tid för efter incidentinlärning att:</span><span class="sxs-lookup"><span data-stu-id="42e0e-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="42e0e-165">Förstå typen av attack och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="42e0e-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="42e0e-166">Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.</span><span class="sxs-lookup"><span data-stu-id="42e0e-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="42e0e-167">Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.</span><span class="sxs-lookup"><span data-stu-id="42e0e-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="42e0e-168">Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.</span><span class="sxs-lookup"><span data-stu-id="42e0e-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="42e0e-169">Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.</span><span class="sxs-lookup"><span data-stu-id="42e0e-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

<span data-ttu-id="42e0e-170">Mer information om åtgärder vid incidenter i microsoft-produkter finns i [den här artikeln.](/security/compass/incident-response-overview)</span><span class="sxs-lookup"><span data-stu-id="42e0e-170">For more information about incident response across Microsoft products, see [this article](/security/compass/incident-response-overview).</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="42e0e-171">Exempel på säkerhetsåtgärder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42e0e-171">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="42e0e-172">Här är ett exempel på säkerhetsåtgärder (SecOps) för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="42e0e-172">Here's an example of security operations (SecOps) for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

<span data-ttu-id="42e0e-174">Dagliga uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="42e0e-174">Daily tasks can include:</span></span>

- <span data-ttu-id="42e0e-175">[Hantera](manage-incidents.md) incidenter</span><span class="sxs-lookup"><span data-stu-id="42e0e-175">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="42e0e-176">Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md) i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="42e0e-176">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="42e0e-177">Gå igenom de senaste [hotanalyserna](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="42e0e-177">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="42e0e-178">[Svara på](investigate-incidents.md) ärenden</span><span class="sxs-lookup"><span data-stu-id="42e0e-178">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="42e0e-179">Månadsvisa uppgifter kan omfatta:</span><span class="sxs-lookup"><span data-stu-id="42e0e-179">Monthly tasks can include:</span></span>

- <span data-ttu-id="42e0e-180">Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="42e0e-180">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="42e0e-181">Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="42e0e-181">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="42e0e-182">Rapportera till din it-säkerhetshanteringskedja</span><span class="sxs-lookup"><span data-stu-id="42e0e-182">Reporting to your IT security management chain</span></span>

<span data-ttu-id="42e0e-183">Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).</span><span class="sxs-lookup"><span data-stu-id="42e0e-183">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="42e0e-184">Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer.</span><span class="sxs-lookup"><span data-stu-id="42e0e-184">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="42e0e-185">Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="42e0e-185">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

### <a name="secops-resources-across-microsoft-products"></a><span data-ttu-id="42e0e-186">SecOps-resurser i alla Microsoft-produkter</span><span class="sxs-lookup"><span data-stu-id="42e0e-186">SecOps resources across Microsoft products</span></span>

<span data-ttu-id="42e0e-187">Mer information om SecOps i Microsofts produkter finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="42e0e-187">For more information about SecOps across Microsoft's products, see these resources:</span></span>

- [<span data-ttu-id="42e0e-188">Kapaciteter</span><span class="sxs-lookup"><span data-stu-id="42e0e-188">Capabilities</span></span>](/security/compass/security-operations-capabilities)
- [<span data-ttu-id="42e0e-189">Metodtips</span><span class="sxs-lookup"><span data-stu-id="42e0e-189">Best practices</span></span>](/security/compass/security-operations)
- [<span data-ttu-id="42e0e-190">Videor och bilder</span><span class="sxs-lookup"><span data-stu-id="42e0e-190">Videos and slides</span></span>](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a><span data-ttu-id="42e0e-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="42e0e-191">Next steps</span></span>

<span data-ttu-id="42e0e-192">**Om du inte har angående** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="42e0e-192">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="42e0e-193">I [genomgången](first-incident-overview.md) Svara på din första incident finns en guidad genomgång av en typisk process av analys, åtgärder och granskning efter incident i Microsoft 365 Defender-portalen med ett exempel på en attack.</span><span class="sxs-lookup"><span data-stu-id="42e0e-193">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example attack.</span></span>

<span data-ttu-id="42e0e-194">**Om du har erfarenhet av** säkerhetsanalys och incidentsvar:</span><span class="sxs-lookup"><span data-stu-id="42e0e-194">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="42e0e-195">Kom igång med incidentkön på sidan **Incidenter** i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="42e0e-195">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="42e0e-196">Härifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="42e0e-196">From here, you can:</span></span>

  - <span data-ttu-id="42e0e-197">Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="42e0e-197">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="42e0e-198">[Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldela, klassificera och lägga till taggar och kommentarer baserat på arbetsflödet för hantering av incidenter.</span><span class="sxs-lookup"><span data-stu-id="42e0e-198">[Manage incidents](manage-incidents.md), which includes renaming, assigning, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="42e0e-199">Utföra [undersökningar](investigate-incidents.md) av incidenter.</span><span class="sxs-lookup"><span data-stu-id="42e0e-199">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="42e0e-200">I de här [spelböckerna för incidenter](/security/compass/incident-response-playbooks) finns detaljerad vägledning för attacker för nätfiske, lösenordsförsök och att bevilja åtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="42e0e-200">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

