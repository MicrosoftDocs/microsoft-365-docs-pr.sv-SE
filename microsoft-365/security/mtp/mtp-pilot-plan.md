---
title: Planera pilotmaterial Microsoft Threat Protection Project
description: Planera ditt pilot Microsoft Threat Protection-projekt med intressenter för att hantera förväntningar och säkerställa ett lyckat resultat.
keywords: Microsoft Threat Protection pilot, planera pilotprogram varan Microsoft Threat Protection Project, utvärdera Microsoft Threat Protection i Production, Microsoft Threat Protection Pilot-projekt, cyberterrorism-säkerhet, Avancerat, beständiga hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: e62b4ec0ee6c9d05321accf269406e8127019f5b
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418115"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="a417c-104">Planera pilotmaterial Microsoft Threat Protection Project</span><span class="sxs-lookup"><span data-stu-id="a417c-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a417c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a417c-105">**Applies to:**</span></span>
- <span data-ttu-id="a417c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a417c-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Planera ditt pilot Microsoft Threat Protection Project" />
      <br/><span data-ttu-id="a417c-108">Planera</a></span><span class="sxs-lookup"><span data-stu-id="a417c-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö" />
      <br/><span data-ttu-id="a417c-110">Förbereda</a></span><span class="sxs-lookup"><span data-stu-id="a417c-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Kör dina simuleringar av angrepps skydd för Microsoft Threats" />
     <br/><span data-ttu-id="a417c-112">Simulera attack</a></span><span class="sxs-lookup"><span data-stu-id="a417c-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Stänga och sammanfatta ditt Microsoft Threat Protection pilot" />
     <br/><span data-ttu-id="a417c-114">Stäng och sammanfatta</a></span><span class="sxs-lookup"><span data-stu-id="a417c-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="a417c-115">Du befinner dig i planerings fasen.</span><span class="sxs-lookup"><span data-stu-id="a417c-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="a417c-116">För att se till att ditt Pilot projekt är framgångs rika är det viktigt att planera omsorgsfullt med och få godkännanden från dina intressenter i början.</span><span class="sxs-lookup"><span data-stu-id="a417c-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="a417c-117">Planerings element inkluderar identifierings omfattning, användnings villkor och krav på framgång.</span><span class="sxs-lookup"><span data-stu-id="a417c-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="a417c-118">Den här guiden hjälper dig att planera pilot projektet.</span><span class="sxs-lookup"><span data-stu-id="a417c-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="a417c-119">För optimalt resultat följer du pilot instruktionerna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="a417c-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="a417c-120">Sitt</span><span class="sxs-lookup"><span data-stu-id="a417c-120">Scope</span></span>

<span data-ttu-id="a417c-121">Omfattningen av piloten bestämmer hur breda testet kommer att vara, baserat på din miljö och acceptabla test metoder.</span><span class="sxs-lookup"><span data-stu-id="a417c-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="a417c-122">Här följer några exempel på omfattningar:</span><span class="sxs-lookup"><span data-stu-id="a417c-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="a417c-123">Utvecklings-eller test miljö som inkluderar slut punkter, servrar, domänkontrollanter.</span><span class="sxs-lookup"><span data-stu-id="a417c-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="a417c-124">Produktions miljö med Microsoft 365, Azure, Active Directory-tjänster, slut punkter och servrar</span><span class="sxs-lookup"><span data-stu-id="a417c-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="a417c-125">Om du inte har alla licenser ännu kan du få prov licenser för utvärdering av [Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – planera, förbereda, konfigurera och starta ett pilot projekt.</span><span class="sxs-lookup"><span data-stu-id="a417c-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="a417c-126">Dina intressenter spelar en stor roll för att under lätta processen från början till slut.</span><span class="sxs-lookup"><span data-stu-id="a417c-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="a417c-127">Vilka typer av operativ system som ska utvärderas ska också definieras baserat på organisationens makeup.</span><span class="sxs-lookup"><span data-stu-id="a417c-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="a417c-128">Det kan vara följande: [Mac-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servrar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="a417c-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="a417c-129">Användnings fall</span><span class="sxs-lookup"><span data-stu-id="a417c-129">Use cases</span></span>

<span data-ttu-id="a417c-130">Användnings fall utgör en översikt över hur verktyget testas är avsett att förbrukas av dess avsedda användare.</span><span class="sxs-lookup"><span data-stu-id="a417c-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="a417c-131">Dessa kan formuleras som användar berättelser från en viss person, till exempel en SOC analytiker.</span><span class="sxs-lookup"><span data-stu-id="a417c-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="a417c-132">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="a417c-132">For example:</span></span>
- <span data-ttu-id="a417c-133">Som SOC analytiker måste jag visa, korrelera, bedöma och hantera aviseringar och händelser mellan enheter, användare och post lådor i mitt nätverk.</span><span class="sxs-lookup"><span data-stu-id="a417c-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="a417c-134">[Ärende hantering]</span><span class="sxs-lookup"><span data-stu-id="a417c-134">[Incident management]</span></span>
- <span data-ttu-id="a417c-135">Som SOC analytiker måste jag ha verktyget och processen för att automatiskt undersöka och reagera på illvilliga händelser i nätverket.</span><span class="sxs-lookup"><span data-stu-id="a417c-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="a417c-136">[Auto-IR]</span><span class="sxs-lookup"><span data-stu-id="a417c-136">[Auto IR]</span></span>
- <span data-ttu-id="a417c-137">Som SOC analytiker måste jag söka data från min miljö för att hitta kända och potentiella hot samt misstänkta aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="a417c-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="a417c-138">[Avancerad jakt]</span><span class="sxs-lookup"><span data-stu-id="a417c-138">[Advanced Hunting]</span></span>

<span data-ttu-id="a417c-139">Kom ihåg att dessa användnings fall ska skapas i parametrarna för det definierade omfånget.</span><span class="sxs-lookup"><span data-stu-id="a417c-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="a417c-140">Om test omfattningen inte inkluderar en utvärdering av verktyg som Microsoft Cloud App Security, ska du använda ärenden som är beroende av detta som data källa.</span><span class="sxs-lookup"><span data-stu-id="a417c-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="a417c-141">Krav</span><span class="sxs-lookup"><span data-stu-id="a417c-141">Requirements</span></span>

<span data-ttu-id="a417c-142">I listan över användnings fall kan du börja skapa krav.</span><span class="sxs-lookup"><span data-stu-id="a417c-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="a417c-143">Kraven inkluderar funktioner som ett verktyg måste uppfylla för användnings fall.</span><span class="sxs-lookup"><span data-stu-id="a417c-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="a417c-144">Dessa krav kan delas upp i kategorier som konfiguration och underhåll, support för integreringar och särskilda krav som jakt möjligheter och möjlighet att bygga anpassade larm.</span><span class="sxs-lookup"><span data-stu-id="a417c-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="a417c-145">Test plan</span><span class="sxs-lookup"><span data-stu-id="a417c-145">Test plan</span></span>

<span data-ttu-id="a417c-146">Beroende på kraven kan de olika test metoderna vara lämpliga.</span><span class="sxs-lookup"><span data-stu-id="a417c-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="a417c-147">Om behovet är att utvärdera hur automatisk reparation fungerar måste test planen innehålla instruktioner för att generera de beteenden som skulle utlösa en automatisk reparations åtgärd inom Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a417c-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="a417c-148">Om behovet är att upptäcka ett visst beteende eller en attack kan testet innehålla fler steg.</span><span class="sxs-lookup"><span data-stu-id="a417c-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="a417c-149">Det är bara att planera ett abonnemang mot dina behov.</span><span class="sxs-lookup"><span data-stu-id="a417c-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="a417c-150">Villkor för framgång</span><span class="sxs-lookup"><span data-stu-id="a417c-150">Success criteria</span></span>

<span data-ttu-id="a417c-151">Villkoren för framgång är i sista hand för att mäta det du testar.</span><span class="sxs-lookup"><span data-stu-id="a417c-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="a417c-152">Oavsett om du testar skydd mot Microsoft Threat (eller någon annan teknik) mot andra verktyg eller för sig själv, måste det finnas vissa kriterier för att avgöra vilket värde verktyget erbjuder.</span><span class="sxs-lookup"><span data-stu-id="a417c-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="a417c-153">Utifrån omfattning, krav och test plan bestämmer villkoren för framgång hur du ska räkna med testet.</span><span class="sxs-lookup"><span data-stu-id="a417c-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="a417c-154">Detta bör vara mindre av ett pass eller fel och mer av viktat poäng baserat på dina behov.</span><span class="sxs-lookup"><span data-stu-id="a417c-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="a417c-155">För att lyckas kan ett verktyg behöva gå över 80% i vissa kritiska områden som du anger.</span><span class="sxs-lookup"><span data-stu-id="a417c-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="a417c-156">Styrkort</span><span class="sxs-lookup"><span data-stu-id="a417c-156">Scorecard</span></span>

<span data-ttu-id="a417c-157">Ett sätt att samla ihop alla element i planen är att skapa ett styrkort.</span><span class="sxs-lookup"><span data-stu-id="a417c-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="a417c-158">Visa ett exempel på ett styrkort nedan:</span><span class="sxs-lookup"><span data-stu-id="a417c-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="a417c-159">Användnings fall</span><span class="sxs-lookup"><span data-stu-id="a417c-159">Use case</span></span> | <span data-ttu-id="a417c-160">Krav</span><span class="sxs-lookup"><span data-stu-id="a417c-160">Requirements</span></span> | <span data-ttu-id="a417c-161">Konfigurations krav</span><span class="sxs-lookup"><span data-stu-id="a417c-161">Configuration requirements</span></span> | <span data-ttu-id="a417c-162">Test plan</span><span class="sxs-lookup"><span data-stu-id="a417c-162">Test plan</span></span> | <span data-ttu-id="a417c-163">Förväntat resultat</span><span class="sxs-lookup"><span data-stu-id="a417c-163">Expected outcome</span></span> | <span data-ttu-id="a417c-164">Test status</span><span class="sxs-lookup"><span data-stu-id="a417c-164">Test status</span></span> | <span data-ttu-id="a417c-165">Poäng</span><span class="sxs-lookup"><span data-stu-id="a417c-165">Score</span></span> | <span data-ttu-id="a417c-166">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a417c-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="a417c-167">Ärende hantering</span><span class="sxs-lookup"><span data-stu-id="a417c-167">Incident management</span></span>|<span data-ttu-id="a417c-168">-Skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="a417c-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="a417c-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-169">- Azure ATP</span></span> </br></br><span data-ttu-id="a417c-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="a417c-171">-Säkerhet för Microsoft Cloud App (valfritt)</span><span class="sxs-lookup"><span data-stu-id="a417c-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="a417c-172">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="a417c-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="a417c-173">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="a417c-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="a417c-174">Undersök problemet</span><span class="sxs-lookup"><span data-stu-id="a417c-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="a417c-175">Prövare kan förstå omfattningen och konsekvenserna av incidenten och hantera händelsen</span><span class="sxs-lookup"><span data-stu-id="a417c-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="a417c-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="a417c-176">AutoIR</span></span>|<span data-ttu-id="a417c-177">-Skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="a417c-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="a417c-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-178">- Azure ATP</span></span> </br></br><span data-ttu-id="a417c-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="a417c-180">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="a417c-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="a417c-181">Aktivera AutoIR</span><span class="sxs-lookup"><span data-stu-id="a417c-181">Enable AutoIR</span></span>  |[<span data-ttu-id="a417c-182">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="a417c-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="a417c-183">Automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="a417c-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="a417c-184">Aviseringar och händelser åtgärdas automatiskt av skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="a417c-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="a417c-185">Avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="a417c-185">Advanced hunting</span></span>|<span data-ttu-id="a417c-186">-Skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="a417c-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="a417c-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="a417c-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a417c-188">- Office 365 ATP</span></span>   |<span data-ttu-id="a417c-189">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="a417c-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="a417c-190">Avancerat jakt scenario</span><span class="sxs-lookup"><span data-stu-id="a417c-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="a417c-191">Prövare kan hitta data genom avancerad jakt, pivotering till förverkningarade enheter och genom att skapa anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="a417c-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="a417c-192">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a417c-192">Next step</span></span>
|<span data-ttu-id="a417c-193">![Förberedelse fas](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="a417c-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="a417c-194">Förberedelse fas</span><span class="sxs-lookup"><span data-stu-id="a417c-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="a417c-195">Förbereda din pilot miljö för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a417c-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
