---
title: Spåra och svara på nya hot med Microsoft Defender ATP –hotanalyser
ms.reviewer: ''
description: Lär dig mer om nya hot och attacktekniker och hur du stoppar dem. Utvärdera hur de påverkar organisationen och utvärdera organisationens motståndskraft.
keywords: hotanalyser, riskutvärderingar, åtgärder i operativsystem, mikrokodsåtgärder, minskningsstatus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f532d20e4fb7cfa101eb6b96a89a4dbc4e658956
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076858"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="05a5a-105">Spåra och svara på nya hot med hotanalyser</span><span class="sxs-lookup"><span data-stu-id="05a5a-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05a5a-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="05a5a-106">**Applies to:**</span></span>
- [<span data-ttu-id="05a5a-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="05a5a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="05a5a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05a5a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="05a5a-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="05a5a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05a5a-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="05a5a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="05a5a-111">Med mer avancerade adversaries och nya hot som dyker upp ofta och ofta är det viktigt att kunna snabbt:</span><span class="sxs-lookup"><span data-stu-id="05a5a-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="05a5a-112">Utvärdera effekterna av nya hot</span><span class="sxs-lookup"><span data-stu-id="05a5a-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="05a5a-113">Granska din motståndskraft mot eller exponering för hoten</span><span class="sxs-lookup"><span data-stu-id="05a5a-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="05a5a-114">Identifiera de åtgärder du kan vidta för att stoppa eller stoppa hoten</span><span class="sxs-lookup"><span data-stu-id="05a5a-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="05a5a-115">Hotanalyser är en uppsättning rapporter från En expert på Microsoft-säkerhet som täcker de mest relevanta hoten, bland annat:</span><span class="sxs-lookup"><span data-stu-id="05a5a-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="05a5a-116">Aktiva hot-aktör och deras kampanjer</span><span class="sxs-lookup"><span data-stu-id="05a5a-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="05a5a-117">Populära och nya attacktekniker</span><span class="sxs-lookup"><span data-stu-id="05a5a-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="05a5a-118">Kritiska säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="05a5a-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="05a5a-119">Vanliga attackytor</span><span class="sxs-lookup"><span data-stu-id="05a5a-119">Common attack surfaces</span></span>
- <span data-ttu-id="05a5a-120">Vanligast förekommande skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="05a5a-120">Prevalent malware</span></span>

<span data-ttu-id="05a5a-121">Varje rapport ger en detaljerad analys av ett hot och omfattande vägledning om hur man skyddar mot det hotet.</span><span class="sxs-lookup"><span data-stu-id="05a5a-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="05a5a-122">Dessutom införlivas data från ditt nätverk, som anger om hoten är aktiva och om du har tillämpliga skydd.</span><span class="sxs-lookup"><span data-stu-id="05a5a-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="05a5a-123">Titta på den här korta videon om du vill lära dig mer om hur hotanalyser kan hjälpa dig att spåra de senaste hoten och stoppa dem.</span><span class="sxs-lookup"><span data-stu-id="05a5a-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="05a5a-124">Visa instrumentpanelen för hotanalyser</span><span class="sxs-lookup"><span data-stu-id="05a5a-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="05a5a-125">Instrumentpanelen för hotanalyser är ett bra sätt att komma åt de rapporter som är mest relevanta för din organisation.</span><span class="sxs-lookup"><span data-stu-id="05a5a-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="05a5a-126">Den sammanfattar hoten i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="05a5a-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="05a5a-127">**De senaste hoten**– visar de senast publicerade hotrapporterna, tillsammans med antalet enheter med aktiva och lösta varningar.</span><span class="sxs-lookup"><span data-stu-id="05a5a-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="05a5a-128">**Hot med hög påverkan**– här listas de hot som har haft störst påverkan på organisationen.</span><span class="sxs-lookup"><span data-stu-id="05a5a-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="05a5a-129">I det här avsnittet rangordnas hot efter antalet enheter som har aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="05a5a-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="05a5a-130">**Sammanfattning av** hot – visar den övergripande effekten av spårade hot genom att visa antalet hot med aktiva och lösta varningar.</span><span class="sxs-lookup"><span data-stu-id="05a5a-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="05a5a-131">Välj ett hot från instrumentpanelen för att visa rapporten för det hotet.</span><span class="sxs-lookup"><span data-stu-id="05a5a-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Bild av en instrumentpanel för hotanalys](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="05a5a-133">Visa en rapport över hotanalyser</span><span class="sxs-lookup"><span data-stu-id="05a5a-133">View a threat analytics report</span></span>

<span data-ttu-id="05a5a-134">Varje rapport över hotanalyser innehåller information i tre avsnitt: **Översikt,** **Analytikerrapport** och **Minskningar.**</span><span class="sxs-lookup"><span data-stu-id="05a5a-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="05a5a-135">Översikt: Förstå snabbt hot, utvärdera dess påverkan och granska försvar</span><span class="sxs-lookup"><span data-stu-id="05a5a-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="05a5a-136">I **avsnittet** Översikt finns en förhandsgranskning av den detaljerade analytikerrapporten.</span><span class="sxs-lookup"><span data-stu-id="05a5a-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="05a5a-137">Dessutom finns diagram som belyser effekterna av risken för organisationen och exponeringen via felkonfigurerade och icke-kompatibla enheter.</span><span class="sxs-lookup"><span data-stu-id="05a5a-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="05a5a-138">![Bild av översiktsavsnittet i en rapport över hotanalyser ](images/ta-overview.png)
 _Översikt över en rapport över hotanalyser_</span><span class="sxs-lookup"><span data-stu-id="05a5a-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="05a5a-139">Utvärdera påverkan på din organisation</span><span class="sxs-lookup"><span data-stu-id="05a5a-139">Assess the impact to your organization</span></span>
<span data-ttu-id="05a5a-140">Varje rapport innehåller diagram som är utformade för att ge information om hur ett hot påverkar organisationen:</span><span class="sxs-lookup"><span data-stu-id="05a5a-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="05a5a-141">**Enheter med aviseringar**– visar det aktuella antalet distinkta enheter som har påverkats av risken.</span><span class="sxs-lookup"><span data-stu-id="05a5a-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="05a5a-142">En enhet kategoriseras som **Aktiv** om det finns minst  en  avisering kopplad till det hotet och löst om alla aviseringar som är associerade med hoten på enheten har lösts.</span><span class="sxs-lookup"><span data-stu-id="05a5a-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="05a5a-143">**Enheter med aviseringar över tid**– visar antalet distinkta enheter med aktiva **och** **lösta** aviseringar över tid.</span><span class="sxs-lookup"><span data-stu-id="05a5a-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="05a5a-144">Antalet lösta aviseringar anger hur snabbt din organisation svarar på aviseringar som är associerade med ett hot.</span><span class="sxs-lookup"><span data-stu-id="05a5a-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="05a5a-145">Under idealiska tider ska diagrammet visa aviseringar som lösts inom några dagar.</span><span class="sxs-lookup"><span data-stu-id="05a5a-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="05a5a-146">Granska motståndskraften hos säkerhet och utvärdering</span><span class="sxs-lookup"><span data-stu-id="05a5a-146">Review security resilience and posture</span></span>
<span data-ttu-id="05a5a-147">Varje rapport innehåller diagram som ger en översikt över hur flexibel din organisation är mot ett givet hot:</span><span class="sxs-lookup"><span data-stu-id="05a5a-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="05a5a-148">**Säkerhetskonfigurationsstatus**– visar antalet enheter som har tillämpat de rekommenderade säkerhetsinställningarna som kan hjälpa till att minska risken.</span><span class="sxs-lookup"><span data-stu-id="05a5a-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="05a5a-149">Enheter anses vara **säkra** om de har _tillämpat alla_ spårade inställningar.</span><span class="sxs-lookup"><span data-stu-id="05a5a-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="05a5a-150">**Status för sårbarhetskorrigering**– visar antalet enheter som har tillämpat säkerhetsuppdateringar eller korrigeringar som säkerhetsproblem utnyttjas av hoten.</span><span class="sxs-lookup"><span data-stu-id="05a5a-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="05a5a-151">Analytikerrapport: Få expertinsikter från Microsoft-säkerhetsanalytiker</span><span class="sxs-lookup"><span data-stu-id="05a5a-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="05a5a-152">Gå till avsnittet **analysrapport för** att läsa igenom den detaljerade expertens uppskrivning.</span><span class="sxs-lookup"><span data-stu-id="05a5a-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="05a5a-153">De flesta rapporter ger detaljerade beskrivningar av attackkedjor, inklusive taktiker och tekniker som mappats till MITRE ATT&CK-ramverket, uttömmande listor med rekommendationer och kraftfulla vägledningar för hot [efter](advanced-hunting-overview.md) hot.</span><span class="sxs-lookup"><span data-stu-id="05a5a-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="05a5a-154">Läs mer om analytiker</span><span class="sxs-lookup"><span data-stu-id="05a5a-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="05a5a-155">Minskningar: Granska en lista över åtgärder och status för dina enheter</span><span class="sxs-lookup"><span data-stu-id="05a5a-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="05a5a-156">Granska listan **över specifika åtgärdsbara** rekommendationer i avsnittet Minskningar som kan hjälpa dig att öka organisationens motståndskraft mot risken.</span><span class="sxs-lookup"><span data-stu-id="05a5a-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="05a5a-157">Listan över spårade åtgärder omfattar:</span><span class="sxs-lookup"><span data-stu-id="05a5a-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="05a5a-158">**Säkerhetsuppdateringar**– distribution av säkerhetsuppdateringar eller korrigeringar för säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="05a5a-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="05a5a-159">**Inställningar för Microsoft Defender Antivirus**</span><span class="sxs-lookup"><span data-stu-id="05a5a-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="05a5a-160">Säkerhetsintelligensversion</span><span class="sxs-lookup"><span data-stu-id="05a5a-160">Security intelligence version</span></span>
  - <span data-ttu-id="05a5a-161">Moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="05a5a-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="05a5a-162">Potentiellt oönskat programskydd (PUA)</span><span class="sxs-lookup"><span data-stu-id="05a5a-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="05a5a-163">Realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="05a5a-163">Real-time protection</span></span>
 
<span data-ttu-id="05a5a-164">I information om åtgärder i det här avsnittet ingår data från hantering av hot och [risker,](next-gen-threat-and-vuln-mgt.md)som också innehåller detaljerad information om åtgärder från olika länkar i rapporten.</span><span class="sxs-lookup"><span data-stu-id="05a5a-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="05a5a-165">![Bild av avsnittet om åtgärder i en rapport om hotanalys ](images/ta-mitigations.png)
 _i avsnittet Åtgärder i en rapport om hotanalys_</span><span class="sxs-lookup"><span data-stu-id="05a5a-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="05a5a-166">Ytterligare rapportinformation och begränsningar</span><span class="sxs-lookup"><span data-stu-id="05a5a-166">Additional report details and limitations</span></span>
<span data-ttu-id="05a5a-167">När du använder rapporterna ska du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="05a5a-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="05a5a-168">Data omfattas av din rollbaserade åtkomstkontroll ( RBAC).</span><span class="sxs-lookup"><span data-stu-id="05a5a-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="05a5a-169">Du ser statusen för enheter i grupper [som du kan komma åt.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="05a5a-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="05a5a-170">Diagram återspeglar endast minskningar som spåras.</span><span class="sxs-lookup"><span data-stu-id="05a5a-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="05a5a-171">Kontrollera rapportens översikt för ytterligare åtgärder som inte visas i diagrammen.</span><span class="sxs-lookup"><span data-stu-id="05a5a-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="05a5a-172">Minskningar garanterar inte fullständig motståndskraft.</span><span class="sxs-lookup"><span data-stu-id="05a5a-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="05a5a-173">Tillhandahållna minskningar återspeglar bästa möjliga åtgärder som krävs för att förbättra motståndskraften.</span><span class="sxs-lookup"><span data-stu-id="05a5a-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="05a5a-174">Enheter räknas som "inte tillgängliga" om de inte har överfört data till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="05a5a-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="05a5a-175">Antivirusrelaterad statistik baseras på inställningarna för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="05a5a-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="05a5a-176">Enheter med antiviruslösningar från tredje part kan visas som "exponerade".</span><span class="sxs-lookup"><span data-stu-id="05a5a-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="05a5a-177">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="05a5a-177">Related topics</span></span>
- [<span data-ttu-id="05a5a-178">Hitta hot proaktivt med avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="05a5a-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="05a5a-179">Förstå analytikernas rapportavsnitt</span><span class="sxs-lookup"><span data-stu-id="05a5a-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="05a5a-180">Utvärdera och lösa säkerhetsbrister och exponeringar</span><span class="sxs-lookup"><span data-stu-id="05a5a-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)