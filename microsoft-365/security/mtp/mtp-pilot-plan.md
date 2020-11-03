---
title: Planera piloten Microsoft 365 Defender Project
description: Planera ditt pilot Microsoft 365 Defender-projekt med intressenter för att hantera förväntningar och se till att resultatet lyckades.
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
ms.openlocfilehash: ec2bfe52308231577e4f2749e1f4cdf24a36f604
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846026"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="f6a96-104">Planera piloten Microsoft 365 Defender Project</span><span class="sxs-lookup"><span data-stu-id="f6a96-104">Planning your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6a96-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f6a96-105">**Applies to:**</span></span>
- <span data-ttu-id="f6a96-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6a96-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Planera piloten Microsoft 365 Defender Project" />
      <br/><span data-ttu-id="f6a96-108">Planera</a></span><span class="sxs-lookup"><span data-stu-id="f6a96-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender" />
      <br/><span data-ttu-id="f6a96-110">Förbereda</a></span><span class="sxs-lookup"><span data-stu-id="f6a96-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Köra din Microsoft 365 Defender-attack simulering" />
     <br/><span data-ttu-id="f6a96-112">Simulera attack</a></span><span class="sxs-lookup"><span data-stu-id="f6a96-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Stänga och sammanfatta din Microsoft 365 Defender pilot" />
     <br/><span data-ttu-id="f6a96-114">Stäng och sammanfatta</a></span><span class="sxs-lookup"><span data-stu-id="f6a96-114">Close and summarize</a></span></span><br>
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

<span data-ttu-id="f6a96-115">Du befinner dig i planerings fasen.</span><span class="sxs-lookup"><span data-stu-id="f6a96-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="f6a96-116">För att se till att ditt Pilot projekt är framgångs rika är det viktigt att planera omsorgsfullt med och få godkännanden från dina intressenter i början.</span><span class="sxs-lookup"><span data-stu-id="f6a96-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="f6a96-117">Planerings element inkluderar identifierings omfattning, användnings villkor och krav på framgång.</span><span class="sxs-lookup"><span data-stu-id="f6a96-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="f6a96-118">Den här guiden hjälper dig att planera pilot projektet.</span><span class="sxs-lookup"><span data-stu-id="f6a96-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="f6a96-119">För optimalt resultat följer du pilot instruktionerna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="f6a96-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="f6a96-120">Sitt</span><span class="sxs-lookup"><span data-stu-id="f6a96-120">Scope</span></span>

<span data-ttu-id="f6a96-121">Omfattningen av piloten bestämmer hur breda testet kommer att vara, baserat på din miljö och acceptabla test metoder.</span><span class="sxs-lookup"><span data-stu-id="f6a96-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="f6a96-122">Här följer några exempel på omfattningar:</span><span class="sxs-lookup"><span data-stu-id="f6a96-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="f6a96-123">Utvecklings-eller test miljö som inkluderar slut punkter, servrar, domänkontrollanter.</span><span class="sxs-lookup"><span data-stu-id="f6a96-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="f6a96-124">Produktions miljö med Microsoft 365, Azure, Active Directory-tjänster, slut punkter och servrar</span><span class="sxs-lookup"><span data-stu-id="f6a96-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="f6a96-125">Om du inte har de fullständiga licenserna ännu kan du få prov licenser för [utvärdering av Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – planera, förbereda, konfigurera och köra ett pilot projekt.</span><span class="sxs-lookup"><span data-stu-id="f6a96-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="f6a96-126">Dina intressenter spelar en stor roll för att under lätta processen från början till slut.</span><span class="sxs-lookup"><span data-stu-id="f6a96-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="f6a96-127">Vilka typer av operativ system som ska utvärderas ska också definieras baserat på organisationens makeup.</span><span class="sxs-lookup"><span data-stu-id="f6a96-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="f6a96-128">Det kan vara följande: [Mac-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servrar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="f6a96-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="f6a96-129">Användnings fall</span><span class="sxs-lookup"><span data-stu-id="f6a96-129">Use cases</span></span>

<span data-ttu-id="f6a96-130">Användnings fall utgör en översikt över hur verktyget testas är avsett att förbrukas av dess avsedda användare.</span><span class="sxs-lookup"><span data-stu-id="f6a96-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="f6a96-131">Dessa kan formuleras som användar berättelser från en viss person, till exempel en SOC analytiker.</span><span class="sxs-lookup"><span data-stu-id="f6a96-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="f6a96-132">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f6a96-132">For example:</span></span>
- <span data-ttu-id="f6a96-133">Som SOC analytiker måste jag visa, korrelera, bedöma och hantera aviseringar och händelser mellan enheter, användare och post lådor i mitt nätverk.</span><span class="sxs-lookup"><span data-stu-id="f6a96-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="f6a96-134">[Ärende hantering]</span><span class="sxs-lookup"><span data-stu-id="f6a96-134">[Incident management]</span></span>
- <span data-ttu-id="f6a96-135">Som SOC analytiker måste jag ha verktyget och processen för att automatiskt undersöka och reagera på illvilliga händelser i nätverket.</span><span class="sxs-lookup"><span data-stu-id="f6a96-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="f6a96-136">[Auto-IR]</span><span class="sxs-lookup"><span data-stu-id="f6a96-136">[Auto IR]</span></span>
- <span data-ttu-id="f6a96-137">Som SOC analytiker måste jag söka data från min miljö för att hitta kända och potentiella hot samt misstänkta aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="f6a96-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="f6a96-138">[Avancerad jakt]</span><span class="sxs-lookup"><span data-stu-id="f6a96-138">[Advanced Hunting]</span></span>

<span data-ttu-id="f6a96-139">Kom ihåg att dessa användnings fall ska skapas i parametrarna för det definierade omfånget.</span><span class="sxs-lookup"><span data-stu-id="f6a96-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="f6a96-140">Om test omfattningen inte inkluderar en utvärdering av verktyg som Microsoft Cloud App Security, ska du använda ärenden som är beroende av detta som data källa.</span><span class="sxs-lookup"><span data-stu-id="f6a96-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="f6a96-141">Krav</span><span class="sxs-lookup"><span data-stu-id="f6a96-141">Requirements</span></span>

<span data-ttu-id="f6a96-142">I listan över användnings fall kan du börja skapa krav.</span><span class="sxs-lookup"><span data-stu-id="f6a96-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="f6a96-143">Kraven inkluderar funktioner som ett verktyg måste uppfylla för användnings fall.</span><span class="sxs-lookup"><span data-stu-id="f6a96-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="f6a96-144">Dessa krav kan delas upp i kategorier som konfiguration och underhåll, support för integreringar och särskilda krav som jakt möjligheter och möjlighet att bygga anpassade larm.</span><span class="sxs-lookup"><span data-stu-id="f6a96-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="f6a96-145">Test plan</span><span class="sxs-lookup"><span data-stu-id="f6a96-145">Test plan</span></span>

<span data-ttu-id="f6a96-146">Beroende på kraven kan de olika test metoderna vara lämpliga.</span><span class="sxs-lookup"><span data-stu-id="f6a96-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="f6a96-147">Om behovet är att utvärdera hur automatisk reparation fungerar måste test planen innehålla instruktioner för att generera de beteenden som skulle utlösa en automatisk reparations åtgärd i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f6a96-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft 365 Defender.</span></span> <span data-ttu-id="f6a96-148">Om behovet är att upptäcka ett visst beteende eller en attack kan testet innehålla fler steg.</span><span class="sxs-lookup"><span data-stu-id="f6a96-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="f6a96-149">Det är bara att planera ett abonnemang mot dina behov.</span><span class="sxs-lookup"><span data-stu-id="f6a96-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="f6a96-150">Villkor för framgång</span><span class="sxs-lookup"><span data-stu-id="f6a96-150">Success criteria</span></span>

<span data-ttu-id="f6a96-151">Villkoren för framgång är i sista hand för att mäta det du testar.</span><span class="sxs-lookup"><span data-stu-id="f6a96-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="f6a96-152">Oavsett om du testar Microsoft 365 Defender (eller någon annan teknik) mot andra verktyg eller själv, måste det finnas vissa kriterier för att avgöra vilket värde verktyget erbjuder.</span><span class="sxs-lookup"><span data-stu-id="f6a96-152">Whether you are testing Microsoft 365 Defender (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="f6a96-153">Utifrån omfattning, krav och test plan bestämmer villkoren för framgång hur du ska räkna med testet.</span><span class="sxs-lookup"><span data-stu-id="f6a96-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="f6a96-154">Detta bör vara mindre av ett pass eller fel och mer av viktat poäng baserat på dina behov.</span><span class="sxs-lookup"><span data-stu-id="f6a96-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="f6a96-155">För att lyckas kan ett verktyg behöva gå över 80% i vissa kritiska områden som du anger.</span><span class="sxs-lookup"><span data-stu-id="f6a96-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="f6a96-156">Styrkort</span><span class="sxs-lookup"><span data-stu-id="f6a96-156">Scorecard</span></span>

<span data-ttu-id="f6a96-157">Ett sätt att samla ihop alla element i planen är att skapa ett styrkort.</span><span class="sxs-lookup"><span data-stu-id="f6a96-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="f6a96-158">Visa ett exempel på ett styrkort nedan:</span><span class="sxs-lookup"><span data-stu-id="f6a96-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="f6a96-159">Användnings fall</span><span class="sxs-lookup"><span data-stu-id="f6a96-159">Use case</span></span> | <span data-ttu-id="f6a96-160">Krav</span><span class="sxs-lookup"><span data-stu-id="f6a96-160">Requirements</span></span> | <span data-ttu-id="f6a96-161">Konfigurations krav</span><span class="sxs-lookup"><span data-stu-id="f6a96-161">Configuration requirements</span></span> | <span data-ttu-id="f6a96-162">Test plan</span><span class="sxs-lookup"><span data-stu-id="f6a96-162">Test plan</span></span> | <span data-ttu-id="f6a96-163">Förväntat resultat</span><span class="sxs-lookup"><span data-stu-id="f6a96-163">Expected outcome</span></span> | <span data-ttu-id="f6a96-164">Test status</span><span class="sxs-lookup"><span data-stu-id="f6a96-164">Test status</span></span> | <span data-ttu-id="f6a96-165">Poäng</span><span class="sxs-lookup"><span data-stu-id="f6a96-165">Score</span></span> | <span data-ttu-id="f6a96-166">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f6a96-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="f6a96-167">Ärende hantering</span><span class="sxs-lookup"><span data-stu-id="f6a96-167">Incident management</span></span>|<span data-ttu-id="f6a96-168">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6a96-168">-  Microsoft 365 Defender</span></span>  </br></br><span data-ttu-id="f6a96-169">-Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="f6a96-169">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="f6a96-170">-Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="f6a96-170">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="f6a96-171">-Säkerhet för Microsoft Cloud App (valfritt)</span><span class="sxs-lookup"><span data-stu-id="f6a96-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="f6a96-172">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="f6a96-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="f6a96-173">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="f6a96-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="f6a96-174">Undersök problemet</span><span class="sxs-lookup"><span data-stu-id="f6a96-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="f6a96-175">Prövare kan förstå omfattningen och konsekvenserna av incidenten och hantera händelsen</span><span class="sxs-lookup"><span data-stu-id="f6a96-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="f6a96-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="f6a96-176">AutoIR</span></span>|<span data-ttu-id="f6a96-177">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6a96-177">-   Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="f6a96-178">-Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="f6a96-178">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="f6a96-179">-Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="f6a96-179">- Microsoft Defender for Endpoint</span></span> |<span data-ttu-id="f6a96-180">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="f6a96-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="f6a96-181">Aktivera AutoIR</span><span class="sxs-lookup"><span data-stu-id="f6a96-181">Enable AutoIR</span></span>  |[<span data-ttu-id="f6a96-182">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="f6a96-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="f6a96-183">Automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="f6a96-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="f6a96-184">Aviseringar och händelser åtgärdas automatiskt av Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6a96-184">Alerts and incidents are automatically remediated by Microsoft 365 Defender</span></span>||||
|<span data-ttu-id="f6a96-185">Avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f6a96-185">Advanced hunting</span></span>|<span data-ttu-id="f6a96-186">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6a96-186">- Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="f6a96-187">-Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="f6a96-187">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="f6a96-188">-Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f6a96-188">-Microsoft Defender for Office 365</span></span> |<span data-ttu-id="f6a96-189">Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information</span><span class="sxs-lookup"><span data-stu-id="f6a96-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="f6a96-190">Avancerat jakt scenario</span><span class="sxs-lookup"><span data-stu-id="f6a96-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="f6a96-191">Prövare kan hitta data genom avancerad jakt, pivotering till förverkningarade enheter och genom att skapa anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="f6a96-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="f6a96-192">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f6a96-192">Next step</span></span>
|<span data-ttu-id="f6a96-193">![Förberedelse fas](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="f6a96-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="f6a96-194">Förberedelse fas</span><span class="sxs-lookup"><span data-stu-id="f6a96-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="f6a96-195">Förbereda din Microsoft 365 Defender pilot miljö</span><span class="sxs-lookup"><span data-stu-id="f6a96-195">Prepare your Microsoft 365 Defender pilot environment</span></span>
|:-------|:-----|
