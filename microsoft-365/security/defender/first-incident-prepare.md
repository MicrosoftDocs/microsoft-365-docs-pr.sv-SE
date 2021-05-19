---
title: Förbered säkerheten för den första händelsen
description: Konfigurera din Microsoft 365 säkerhet för den första incidenten i Microsoft 365 Defender.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
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
ms.openlocfilehash: 4fc124bf8787d5880d78a4f5208bd66329da07a0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539041"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="3229d-104">Förbered säkerheten för den första händelsen</span><span class="sxs-lookup"><span data-stu-id="3229d-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3229d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3229d-105">**Applies to:**</span></span>
- <span data-ttu-id="3229d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3229d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3229d-107">Förberedelse för incidenthantering omfattar att konfigurera tillräckligt skydd av organisationens nätverk från olika typer av säkerhetsincidenter.</span><span class="sxs-lookup"><span data-stu-id="3229d-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="3229d-108">För att minska risken för säkerhetsincidenter rekommenderar National Institute of Standards and Technology (NIST) flera säkerhetsmetoder, bland annat riskbedömning, hårdnande värdsäkerhet, konfigurera nätverk säkert och förhindra skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="3229d-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="3229d-109">Microsoft 365 Defender kan åtgärda flera aspekter av incidentskydd:</span><span class="sxs-lookup"><span data-stu-id="3229d-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="3229d-110">Implementera ett [Zero Trust Framework](https://docs.microsoft.com/security/zero-trust/)</span><span class="sxs-lookup"><span data-stu-id="3229d-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="3229d-111">Fastställa din säkerhet genom att tilldela ett poäng med [Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="3229d-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="3229d-112">Förhindra hot genom sårbarhetsutvärderingar i [hot- och sårbarhetshantering](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="3229d-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="3229d-113">Förstå de senaste säkerhetshoten så att du kan förbereda dem</span><span class="sxs-lookup"><span data-stu-id="3229d-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="3229d-114">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="3229d-114">Step 1.</span></span> <span data-ttu-id="3229d-115">Implementera nollförtroende</span><span class="sxs-lookup"><span data-stu-id="3229d-115">Implement Zero Trust</span></span>

<span data-ttu-id="3229d-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) är en integrerad säkerhetsstrategi som tar hänsyn till hur komplex en modern miljö är, inklusive den mobila arbetsstyrkan och användare, enheter, program och data, var de än befinner sig.</span><span class="sxs-lookup"><span data-stu-id="3229d-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="3229d-117">Genom att ha ett enda fönster med fönster för att hantera alla identifieringar på ett konsekvent sätt [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) kan Microsoft 365 Defender göra det enklare för din säkerhetsgrupp att implementera de vägledande principerna för Zero Trust.</span><span class="sxs-lookup"><span data-stu-id="3229d-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="3229d-118">Komponenter i Microsoft 365 Defender kan visa överträdelser av regler som har implementerats för att upprätta villkorsstyrda åtkomstprinciper för Zero Trust genom att integrera data från Microsoft Defender för slutpunkt (MDE) eller andra mobila säkerhetsleverantörer som en informationskälla för principer för enhetsefterlevnad och implementering av enhetsbaserade villkorsbaserade principer.</span><span class="sxs-lookup"><span data-stu-id="3229d-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="3229d-119">Enhetsrisker påverkar direkt vilka resurser som är tillgängliga för användaren av enheten.</span><span class="sxs-lookup"><span data-stu-id="3229d-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="3229d-120">Denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span><span class="sxs-lookup"><span data-stu-id="3229d-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="3229d-121">Till exempel kan Microsoft 365 Defender tillhandahålla programvaruversionsnivån för en enhet via sidan Threat and Vulnerability Management medan villkorsstyrd åtkomst begränsar enheter som har inaktuella eller sårbara versioner.</span><span class="sxs-lookup"><span data-stu-id="3229d-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="3229d-122">Automation är en viktig del i implementeringen och underhållet av en nollförtroendemiljö samtidigt som antalet aviseringar som potentiellt skulle leda till incidentåtgärdshändelser (IR-händelser) minskar.</span><span class="sxs-lookup"><span data-stu-id="3229d-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="3229d-123">Komponenter i Microsoft 365 Defender kan automatiseras, till exempel åtgärder [(kallas](m365d-autoir.md) undersökningar för en incident i säkerhetscentret i Microsoft 365), aviseringsåtgärder och till och med skapandet av supportärenden i [ServiceNow.](https://microsoft.service-now.com/sp/)</span><span class="sxs-lookup"><span data-stu-id="3229d-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="3229d-124">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="3229d-124">Step 2.</span></span> <span data-ttu-id="3229d-125">Fastställa säkerheten i din organisation</span><span class="sxs-lookup"><span data-stu-id="3229d-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="3229d-126">Därefter kan organisationer använda [Microsoft Secure Score](microsoft-secure-score.md) i Microsoft 365 Defender för att avgöra vilken säkerhetsrisk du har och fundera på rekommendationer om hur du kan förbättra den.</span><span class="sxs-lookup"><span data-stu-id="3229d-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="3229d-127">Ju högre poäng desto fler säkerhetsrekommendationer och förbättringsåtgärder har genomförts av organisationen.</span><span class="sxs-lookup"><span data-stu-id="3229d-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="3229d-128">Rekommendationer om Secure Score kan användas i olika produkter och organisationer kan höja sina resultat ännu högre.</span><span class="sxs-lookup"><span data-stu-id="3229d-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Exempel på Microsoft Secure Score i Microsofts säkerhetscenter":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="3229d-130">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="3229d-130">Step 3.</span></span> <span data-ttu-id="3229d-131">Utvärdera exponering av risker för din organisation</span><span class="sxs-lookup"><span data-stu-id="3229d-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="3229d-132">Att förhindra incidenter kan effektivisera arbetet med säkerhetsåtgärder för att fokusera på viktiga säkerhetsincidenter som är viktiga i det här processen.</span><span class="sxs-lookup"><span data-stu-id="3229d-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="3229d-133">Säkerhetsproblem av programvara är ofta en startpunkt som kan förhindras för attacker som kan leda till datastöld, dataförlust eller störningar i affärsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="3229d-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="3229d-134">Om inga attacker är i gång måste säkerhetsåtgärder strävar efter att uppnå och upprätthålla en godtagbar nivå av [exponering](../defender-endpoint/tvm-exposure-score.md) av sårbarheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3229d-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="3229d-135">Om du vill kontrollera förloppet [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) för programkorrigeringar går du till sidan Hantering av hot och sårbarhet i Defender för slutpunkt, som du kan komma åt från Microsoft 365 Defender på **fliken Fler** resurser.</span><span class="sxs-lookup"><span data-stu-id="3229d-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Exempel på sidan Hot och sårbarhet i Microsofts säkerhetscenter"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="3229d-137">4. Förstå nya hot</span><span class="sxs-lookup"><span data-stu-id="3229d-137">4. Understand emerging threats</span></span>

<span data-ttu-id="3229d-138">Använd [hotanalyser](threat-analytics.md) i Microsoft 365 säkerhetscenter för att hålla dig uppdaterad om de aktuella hot landskapen.</span><span class="sxs-lookup"><span data-stu-id="3229d-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="3229d-139">En expert som Microsoft-säkerhetsexpert skapar rapporter som beskriver de senaste cyberhoten i detalj så att du förstår hur de kan påverka Microsoft 365 prenumeration, enheter och användare.</span><span class="sxs-lookup"><span data-stu-id="3229d-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="3229d-140">Dessa rapporter kan innehålla:</span><span class="sxs-lookup"><span data-stu-id="3229d-140">These reports can include:</span></span>

- <span data-ttu-id="3229d-141">Aktiva hot-aktör och deras kampanjer</span><span class="sxs-lookup"><span data-stu-id="3229d-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="3229d-142">Populära och nya attacktekniker</span><span class="sxs-lookup"><span data-stu-id="3229d-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="3229d-143">Kritiska säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="3229d-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="3229d-144">Vanliga attackytor</span><span class="sxs-lookup"><span data-stu-id="3229d-144">Common attack surfaces</span></span>
- <span data-ttu-id="3229d-145">Vanligast förekommande skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="3229d-145">Prevalent malware</span></span>

<span data-ttu-id="3229d-146">Hotanalyser tittar också på din konfiguration och aviseringar för att fastställa hur riskabel du är och om det finns aktiva aviseringar som gäller för en rapport.</span><span class="sxs-lookup"><span data-stu-id="3229d-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="3229d-147">Du kan implementera rekommendationerna om ett framväxande hot för att stärka din säkerhetsrisk och minimera ditt attackområde.</span><span class="sxs-lookup"><span data-stu-id="3229d-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="3229d-148">Se till att ha tid i schemat för att [regelbundet kontrollera avsnittet om](threat-analytics.md) hotanalys Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="3229d-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="3229d-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3229d-149">Next step</span></span>

<span data-ttu-id="3229d-150">[![Steg 1: Lär dig att undersöka och analysera incidenter](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="3229d-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="3229d-151">Lär dig att [undersöka och analysera incidenter.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="3229d-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3229d-152">Se även</span><span class="sxs-lookup"><span data-stu-id="3229d-152">See also</span></span>

- [<span data-ttu-id="3229d-153">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="3229d-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3229d-154">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="3229d-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="3229d-155">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="3229d-155">Manage incidents</span></span>](manage-incidents.md)
