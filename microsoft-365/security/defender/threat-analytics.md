---
title: Spåra och svara på nya hot med hotanalyser
ms.reviewer: ''
description: Lär dig mer om nya hot och attacktekniker och hur du stoppar dem. Utvärdera hur de påverkar organisationen och utvärdera organisationens motståndskraft.
keywords: hotanalyser, riskutvärdering, Microsoft 365 Defender, M365D, minskningsstatus, säker konfiguration, Microsoft Defender för Office 365, Microsoft Defender för Office 365 hotanalyser, MDO-hotanalyser, integrerade MDE- och MDO-hotanalysdata, data för hotanalyser, integrerad Microsoft 365 Defender-hotanalys
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f7f1453e840d3c709bcabdb67d7d2dc048ea443
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076282"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="8f4f7-105">Spåra och svara på nya hot med hotanalyser</span><span class="sxs-lookup"><span data-stu-id="8f4f7-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8f4f7-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-106">**Applies to:**</span></span>
- <span data-ttu-id="8f4f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f4f7-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="8f4f7-108">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8f4f7-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="8f4f7-109">Du kan [utvärdera den i en labbmiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller köra [pilotprojektet i produktion.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="8f4f7-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


<span data-ttu-id="8f4f7-110">Hotanalyser är vår in-product threat intelligence-lösning från en expert på Microsoft-säkerhet som utformats för att hjälpa säkerhetsteam att bli så effektiva som möjligt samtidigt som de står inför nya hot, inklusive:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="8f4f7-111">Aktiva hot-aktör och deras kampanjer</span><span class="sxs-lookup"><span data-stu-id="8f4f7-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="8f4f7-112">Populära och nya attacktekniker</span><span class="sxs-lookup"><span data-stu-id="8f4f7-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="8f4f7-113">Kritiska säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="8f4f7-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="8f4f7-114">Vanliga attackytor</span><span class="sxs-lookup"><span data-stu-id="8f4f7-114">Common attack surfaces</span></span>
- <span data-ttu-id="8f4f7-115">Vanligast förekommande skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="8f4f7-115">Prevalent malware</span></span>

<span data-ttu-id="8f4f7-116">Titta på den här korta videon om du vill lära dig mer om hur hotanalyser kan hjälpa dig att spåra de senaste hoten och stoppa dem.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="8f4f7-117">Du kan komma åt hotanalyser antingen från den övre vänstra sidan i Microsoft 365-säkerhetsportalens navigeringsfält eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten i din organisation. Att få insyn i aktiva eller pågående kampanjer och veta vad du kan göra med hjälp av hotanalyser kan hjälpa din säkerhetsgrupp att hantera välgrundade beslut.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Bild på instrumentpanelen för hotanalyser](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="8f4f7-119">_Var du kan komma åt hotanalyser_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="8f4f7-120">Med mer avancerade adversaries och nya hot som dyker upp ofta och ofta är det viktigt att kunna snabbt:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="8f4f7-121">Identifiera och reagera på nya hot</span><span class="sxs-lookup"><span data-stu-id="8f4f7-121">Identify and react to emerging threats</span></span> 
- <span data-ttu-id="8f4f7-122">Ta reda på om du är under attack</span><span class="sxs-lookup"><span data-stu-id="8f4f7-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="8f4f7-123">Utvärdera effekterna av hoten på dina tillgångar</span><span class="sxs-lookup"><span data-stu-id="8f4f7-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="8f4f7-124">Granska din motståndskraft mot eller exponering för hoten</span><span class="sxs-lookup"><span data-stu-id="8f4f7-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="8f4f7-125">Identifiera åtgärder för minskning, återställning eller förebyggande åtgärder som du kan vidta för att stoppa eller begränsa hoten</span><span class="sxs-lookup"><span data-stu-id="8f4f7-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="8f4f7-126">Varje rapport innehåller en analys av ett spårat hot och omfattande vägledning om hur man skyddar mot dessa hot.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="8f4f7-127">Dessutom införlivas data från ditt nätverk, som anger om hoten är aktiva och om du har tillämpliga skydd.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="8f4f7-128">Visa instrumentpanelen för hotanalyser</span><span class="sxs-lookup"><span data-stu-id="8f4f7-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="8f4f7-129">Instrumentpanelen för hotanalys[(security.microsoft.com/threatanalytics3)](https://security.microsoft.com/threatanalytics3)markerar de rapporter som är mest relevanta för din organisation.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="8f4f7-130">Den sammanfattar hoten i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="8f4f7-131">**De senaste hoten**– visar de senast publicerade eller uppdaterade hotrapporterna, tillsammans med antalet aktiva och lösta varningar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="8f4f7-132">**Hot med stor påverkan**– här listas de hot som påverkar din organisation mest.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="8f4f7-133">I det här avsnittet visas hot med det högsta antalet aktiva och lösta aviseringar först.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="8f4f7-134">**Sammanfattning av** hot – ger den övergripande effekten av alla spårade hot genom att visa antalet hot med aktiva och lösta varningar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="8f4f7-135">Välj ett hot från instrumentpanelen för att visa rapporten för det hotet.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Skärmbild av instrumentpanelen för hotanalyser](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="8f4f7-137">_Instrumentpanel för hotanalyser. Du kan också klicka på sökikonen för att hitta ett nyckelord som är relaterat till den rapport över hotanalyser som du vill läsa._</span><span class="sxs-lookup"><span data-stu-id="8f4f7-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="8f4f7-138">Visa en rapport över hotanalyser</span><span class="sxs-lookup"><span data-stu-id="8f4f7-138">View a threat analytics report</span></span>

<span data-ttu-id="8f4f7-139">Varje rapport om hotanalyser innehåller information i flera avsnitt:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-139">Each threat analytics report provides information in several sections:</span></span> 

- [<span data-ttu-id="8f4f7-140">**Översikt**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [<span data-ttu-id="8f4f7-141">**Analytiker**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="8f4f7-142">**Relaterade ärenden**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="8f4f7-143">**Påverkade tillgångar**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="8f4f7-144">**Förhindrade e-postförsök**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="8f4f7-145">**Minskningar**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="8f4f7-146">Översikt: Förstå snabbt hot, utvärdera dess påverkan och granska försvar</span><span class="sxs-lookup"><span data-stu-id="8f4f7-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="8f4f7-147">I **avsnittet** Översikt finns en förhandsgranskning av den detaljerade analytikerrapporten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="8f4f7-148">Dessutom finns diagram som belyser effekterna av risken för organisationen och exponeringen via felkonfigurerade och icke-kompatibla enheter.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Bild av översiktsavsnittet i en rapport om hotanalys](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="8f4f7-150">_Översiktsavsnitt i en rapport om hotanalyser_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="8f4f7-151">Utvärdera påverkan på organisationen</span><span class="sxs-lookup"><span data-stu-id="8f4f7-151">Assess impact on your organization</span></span>
<span data-ttu-id="8f4f7-152">Varje rapport innehåller diagram som är utformade för att ge information om hur ett hot påverkar organisationen:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="8f4f7-153">**Relaterade incidenter**– ger en översikt över effekterna av de spårade hoten för din organisation med följande data:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="8f4f7-154">Antalet aktiva aviseringar och antalet aktiva incidenter de är associerade med</span><span class="sxs-lookup"><span data-stu-id="8f4f7-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="8f4f7-155">Allvarlighetsgrad för aktiva incidenter</span><span class="sxs-lookup"><span data-stu-id="8f4f7-155">Severity of active incidents</span></span>
- <span data-ttu-id="8f4f7-156">**Aviseringar över tid**– visar antalet relaterade aviseringar **som är aktiva** och **lösta** över tid.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="8f4f7-157">Antalet lösta aviseringar anger hur snabbt din organisation svarar på aviseringar som är associerade med ett hot.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="8f4f7-158">Under idealiska tider ska diagrammet visa aviseringar som lösts inom några dagar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="8f4f7-159">**Påverkade tillgångar –** visar antalet distinkta enheter och e-postkonton (postlådor) som för närvarande har minst en aktiv avisering kopplad till de spårade hoten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="8f4f7-160">Aviseringar utlöses för postlådor som har fått e-postmeddelanden om hot.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="8f4f7-161">Läs både organisations- och användarprinciper om åsidosättningar som orsakar leverans av hotmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="8f4f7-162">**Förhindrade e-postförsök**– visar antalet e-postmeddelanden från de senaste sju dagarna som antingen har blockerats före leveransen eller levererats till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="8f4f7-163">Granska motståndskraften hos säkerhet och utvärdering</span><span class="sxs-lookup"><span data-stu-id="8f4f7-163">Review security resilience and posture</span></span>
<span data-ttu-id="8f4f7-164">Varje rapport innehåller diagram som ger en översikt över hur flexibel din organisation är mot ett givet hot:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="8f4f7-165">**Säker konfigurationsstatus**– visar antalet enheter med felkonfigurerade säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="8f4f7-166">Använd de rekommenderade säkerhetsinställningarna för att minska risken.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="8f4f7-167">Enheter anses vara **säkra** om de har _tillämpat alla_ spårade inställningar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="8f4f7-168">**Status för sårbarhetskorrigering**– visar antalet sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="8f4f7-169">Tillämpa säkerhetsuppdateringar eller korrigeringar för att åtgärda säkerhetsproblem som utnyttjas av risken.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="8f4f7-170">Analytikerrapport: Få expertinsikter från Microsoft-säkerhetsanalytiker</span><span class="sxs-lookup"><span data-stu-id="8f4f7-170">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="8f4f7-171">I avsnittet **Analytikerrapport** kan du läsa igenom den detaljerade expertens uppskrivning.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-171">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="8f4f7-172">De flesta rapporter ger detaljerade beskrivningar av attackkedjor, inklusive taktiker och tekniker som mappats till MITRE ATT&CK-ramverket, uttömmande listor med rekommendationer och kraftfulla vägledningar för hot [efter](advanced-hunting-overview.md) hot.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-172">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="8f4f7-173">Läs mer om analytiker</span><span class="sxs-lookup"><span data-stu-id="8f4f7-173">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="8f4f7-174">Relaterade ärenden: Visa och hantera relaterade ärenden</span><span class="sxs-lookup"><span data-stu-id="8f4f7-174">Related incidents: View and manage related incidents</span></span>
<span data-ttu-id="8f4f7-175">På **fliken Relaterade** incidenter visas en lista över alla incidenter som är relaterade till de spårade hoten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-175">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="8f4f7-176">Du kan tilldela incidenter eller hantera aviseringar som är kopplade till varje incident.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-176">You can assign incidents or manage alerts linked to each incident.</span></span> 

![Bild av avsnittet relaterade incidenter i en rapport om hotanalys](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="8f4f7-178">_Avsnittet relaterade incidenter i en rapport om hotanalys_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-178">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="8f4f7-179">Påverkade tillgångar: Hämta en lista över påverkade enheter och postlådor</span><span class="sxs-lookup"><span data-stu-id="8f4f7-179">Impacted assets: Get list of impacted devices and mailboxes</span></span>
<span data-ttu-id="8f4f7-180">En tillgång anses påverkas om den påverkas av en aktiv, omatchad avisering.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-180">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="8f4f7-181">På **fliken Påverkade tillgångar** visas följande typer av påverkade tillgångar:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-181">The **Impacted assets** tab lists the following types of impacted assets:</span></span>
- <span data-ttu-id="8f4f7-182">**Påverkade enheter –** slutpunkter som har omatchade Microsoft Defender för slutpunktsaviseringar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-182">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="8f4f7-183">Dessa varningar kan i regel uppmärksamma syn på kända hotindikatorer och -aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-183">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="8f4f7-184">**Påverkade postlådor – postlådor** som har tagit emot e-postmeddelanden som har utlöst Microsoft Defender för Office 365-aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-184">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="8f4f7-185">Även om de flesta meddelanden som utlöser aviseringar vanligtvis blockeras, kan principer på användar- eller organisationsnivå åsidosätta filter.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-185">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Bild av avsnittet om påverkade tillgångar i en rapport om hotanalys](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="8f4f7-187">_Avsnittet Påverkade tillgångar i en rapport om hotanalys_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-187">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="8f4f7-188">Förhindrade e-postförsök: Visa blockerade eller skräppostade hotmeddelanden</span><span class="sxs-lookup"><span data-stu-id="8f4f7-188">Prevented email attempts: View blocked or junked threat emails</span></span>
<span data-ttu-id="8f4f7-189">Microsoft Defender för Office 365 blockerar vanligtvis e-postmeddelanden med kända hotindikatorer, inklusive skadliga länkar eller bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-189">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="8f4f7-190">I vissa fall kommer proaktiva filtreringsmetoder som söker efter misstänkt innehåll i stället att skicka e-postmeddelanden med hot till skräppostmappen.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-190">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="8f4f7-191">I båda fallen minskar risken för att skadlig kod ska startas på enheten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-191">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="8f4f7-192">På **fliken Förhindrade e-postförsök** visas alla e-postmeddelanden som antingen har blockerats före leveransen eller skickats till skräppostmappen av Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-192">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Bild av avsnittet om förhindrade e-postförsök i en rapport om hotanalyser](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="8f4f7-194">_Avsnittet Förhindrade e-postförsök i en rapport om hotanalyser_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-194">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="8f4f7-195">Minskningar: Granska en lista över åtgärder och status för dina enheter</span><span class="sxs-lookup"><span data-stu-id="8f4f7-195">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="8f4f7-196">Granska listan **över specifika åtgärdsbara** rekommendationer i avsnittet Minskningar som kan hjälpa dig att öka organisationens motståndskraft mot risken.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-196">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="8f4f7-197">Listan över spårade åtgärder omfattar:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-197">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="8f4f7-198">**Säkerhetsuppdateringar**– distribution av säkerhetsuppdateringar av programvara som stöds för säkerhetsproblem som påträffas på enheter som är ombord</span><span class="sxs-lookup"><span data-stu-id="8f4f7-198">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="8f4f7-199">**Säkerhetskonfigurationer som stöds**</span><span class="sxs-lookup"><span data-stu-id="8f4f7-199">**Supported security configurations**</span></span>
  - <span data-ttu-id="8f4f7-200">Moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="8f4f7-200">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="8f4f7-201">Potentiellt oönskat programskydd (PUA)</span><span class="sxs-lookup"><span data-stu-id="8f4f7-201">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="8f4f7-202">Realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="8f4f7-202">Real-time protection</span></span>
 
<span data-ttu-id="8f4f7-203">I information om åtgärder i det här avsnittet ingår data från hantering av hot och [risker,](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)som också innehåller detaljerad information om åtgärder från olika länkar i rapporten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-203">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="8f4f7-204">![Bild av avsnittet åtgärder i en rapport om hotanalys som visar säker konfigurationsinformation Bild av avsnittet om åtgärder i en rapport om hotanalys som visar information om ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ problemet](../../media/threat-analytics/ta_mitigations_mtp2.png)</span><span class="sxs-lookup"><span data-stu-id="8f4f7-204">![Image of the mitigations section of a threat analytics report showing secure configuration details](../../media/threat-analytics/ta_mitigations_mtp.png)
![Image of the mitigations section of a threat analytics report showing vulnerability details](../../media/threat-analytics/ta_mitigations_mtp2.png)</span></span>

<span data-ttu-id="8f4f7-205">_Avsnittet Åtgärder i en rapport om hotanalys_</span><span class="sxs-lookup"><span data-stu-id="8f4f7-205">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="8f4f7-206">Ytterligare rapportinformation och begränsningar</span><span class="sxs-lookup"><span data-stu-id="8f4f7-206">Additional report details and limitations</span></span>
>[!NOTE]
><span data-ttu-id="8f4f7-207">Som en del av den enhetliga säkerhetsupplevelsen är hotanalyser nu inte bara tillgängliga för Microsoft Defender för Endpoint, utan även för Microsoft Defender för Office E5-licensinnehavare.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-207">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
><span data-ttu-id="8f4f7-208">Om du inte använder Microsoft 365-säkerhetsportalen (Microsoft 365 Defender) kan du även se rapportinformationen (utan Microsoft Defender för Office-data) i Microsoft Defender Säkerhetscenter-portalen (Microsoft Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="8f4f7-208">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span> 

<span data-ttu-id="8f4f7-209">För att komma åt rapporten över hotanalyser behöver du vissa roller och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-209">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="8f4f7-210">Mer [information finns i Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8f4f7-210">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>
  - <span data-ttu-id="8f4f7-211">Om du vill visa aviseringar, incidenter eller data om påverkade tillgångar måste du ha behörighet till Microsoft Defender för Office eller Microsoft Defender för data om slutpunktsaviseringar eller båda.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-211">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
  - <span data-ttu-id="8f4f7-212">Om du vill visa förhindrade e-postförsök måste du ha behörighet till Microsoft Defender för Office för att kunna söka efter data.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-212">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
  - <span data-ttu-id="8f4f7-213">Om du vill visa minskningar måste du ha behörighet till data om hot och sårbarhetshantering i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-213">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8f4f7-214">När du tittar på data från hotanalyser ska du tänka på följande faktorer:</span><span class="sxs-lookup"><span data-stu-id="8f4f7-214">When looking at the threat analytics data, remember the following factors:</span></span>
- <span data-ttu-id="8f4f7-215">Diagram återspeglar endast minskningar som spåras.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-215">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="8f4f7-216">Kontrollera rapportens översikt för ytterligare åtgärder som inte visas i diagrammen.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-216">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="8f4f7-217">Minskningar garanterar inte fullständig motståndskraft.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-217">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="8f4f7-218">Tillhandahållna minskningar återspeglar bästa möjliga åtgärder som krävs för att förbättra motståndskraften.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-218">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="8f4f7-219">Enheter räknas som "inte tillgängliga" om de inte har överfört data till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-219">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="8f4f7-220">Antivirusrelaterad statistik baseras på inställningarna för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8f4f7-220">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="8f4f7-221">Enheter med antiviruslösningar från tredje part kan visas som "exponerade".</span><span class="sxs-lookup"><span data-stu-id="8f4f7-221">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f4f7-222">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8f4f7-222">Related topics</span></span>
- [<span data-ttu-id="8f4f7-223">Hitta hot proaktivt med avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="8f4f7-223">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="8f4f7-224">Förstå analytikernas rapportavsnitt</span><span class="sxs-lookup"><span data-stu-id="8f4f7-224">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="8f4f7-225">Utvärdera och lösa säkerhetsbrister och exponeringar</span><span class="sxs-lookup"><span data-stu-id="8f4f7-225">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)