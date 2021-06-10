---
title: Skydd mot hot (Windows 10)
description: Microsoft Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar.
keywords: Skydd mot hot, Microsoft Defender för Endpoint, minskning av attackytan, nästa generations skydd, identifiering och åtgärd på slutpunkt, automatisk undersökning och svar, Microsoft Threat-experter, Microsoft Secure Score för enheter, avancerad sökning, sökning efter cyberhot, skydd mot webbhot
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841000"
---
# <a name="threat-protection"></a><span data-ttu-id="99d71-104">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="99d71-104">Threat Protection</span></span>
<span data-ttu-id="99d71-105">[Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar.</span><span class="sxs-lookup"><span data-stu-id="99d71-105">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="99d71-106">Defender för Endpoint skyddar slutpunkter mot cyberhot, identifierar avancerade attacker och databrott, automatiserar säkerhetstillbud och förbättrar säkerhetsriskerna.</span><span class="sxs-lookup"><span data-stu-id="99d71-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="99d71-107">Gör det enkelt för användarna att få tillgång till molntjänster och lokala program och möjliggöra moderna hanteringsfunktioner för alla enheter.</span><span class="sxs-lookup"><span data-stu-id="99d71-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="99d71-108">Mer information finns i Skydda [din fjärranslutna arbetsstyrka.](/enterprise-mobility-security/remote-work/)</span><span class="sxs-lookup"><span data-stu-id="99d71-108">For more information, see [Secure your remote workforce](/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="99d71-109">Microsoft Defender för Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="99d71-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="99d71-110"><b>Hot & hantering av säkerhetsrisker</b></center></a></span><span class="sxs-lookup"><span data-stu-id="99d71-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="99d71-111"><b>Minskning av attackytan</b></center></a></span><span class="sxs-lookup"><span data-stu-id="99d71-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="99d71-112"><b>Nästa generations skydd</b></a></center></span><span class="sxs-lookup"><span data-stu-id="99d71-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="99d71-113"><b>Identifiering och svar av slutpunkter</b></a></center></span><span class="sxs-lookup"><span data-stu-id="99d71-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="99d71-114"><b>Automatiserad undersökning och åtgärder</b></a></center></span><span class="sxs-lookup"><span data-stu-id="99d71-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="99d71-115"><b>Microsoft Hotexperter</b></a></center></span><span class="sxs-lookup"><span data-stu-id="99d71-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="99d71-116">
<a href="#apis"><center><b>Centraliserad konfiguration och administration, API:er</a></span><span class="sxs-lookup"><span data-stu-id="99d71-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="99d71-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="99d71-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="99d71-118">**[Hot och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="99d71-119">Den inbyggda funktionen använder en spelförändrande riskbaserad metod för identifiering, prioritering och åtgärd av svagheter och felkonfigurationer i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="99d71-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="99d71-120">Översikt över & hantering av säkerhetsrisker hot</span><span class="sxs-lookup"><span data-stu-id="99d71-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="99d71-121">Komma igång</span><span class="sxs-lookup"><span data-stu-id="99d71-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="99d71-122">Komma åt din säkerhet</span><span class="sxs-lookup"><span data-stu-id="99d71-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="99d71-123">Förbättra säkerheten och minska risken</span><span class="sxs-lookup"><span data-stu-id="99d71-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="99d71-124">Förstå sårbarhet på dina enheter</span><span class="sxs-lookup"><span data-stu-id="99d71-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="99d71-125">**[Minskning av attackytan](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="99d71-126">Minskningsuppsättningen för attackytan ger den första försvarslinjen i högen.</span><span class="sxs-lookup"><span data-stu-id="99d71-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="99d71-127">Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.</span><span class="sxs-lookup"><span data-stu-id="99d71-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="99d71-128">Maskinvarubaserad avgränsning</span><span class="sxs-lookup"><span data-stu-id="99d71-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="99d71-129">Applikationskontroll</span><span class="sxs-lookup"><span data-stu-id="99d71-129">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="99d71-130">Enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="99d71-130">Device control</span></span>](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="99d71-131">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="99d71-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="99d71-132">[Nätverksskydd](network-protection.md), [webbskydd](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="99d71-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="99d71-133">Kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="99d71-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="99d71-134">Nätverksbrandvägg</span><span class="sxs-lookup"><span data-stu-id="99d71-134">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="99d71-135">Regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="99d71-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="99d71-136">**[Nästa generations skydd](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="99d71-136">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="99d71-137">För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="99d71-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="99d71-138">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="99d71-138">Behavior monitoring</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="99d71-139">Molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="99d71-139">Cloud-based protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="99d71-140">Maskininlärning</span><span class="sxs-lookup"><span data-stu-id="99d71-140">Machine learning</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="99d71-141">URL-skydd</span><span class="sxs-lookup"><span data-stu-id="99d71-141">URL Protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="99d71-142">Automatiserad begränsat lägestjänst</span><span class="sxs-lookup"><span data-stu-id="99d71-142">Automated sandbox service</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="99d71-143">**[Identifiering och svar för slutpunkt](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="99d71-144">Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och svara på intrångsförsök och aktiva intrång.</span><span class="sxs-lookup"><span data-stu-id="99d71-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="99d71-145">Med Avancerad sökning har du ett frågebaserat verktyg för hotsökning som gör att du proaktivt kan hitta överträdelser och skapa anpassade identifieringar.</span><span class="sxs-lookup"><span data-stu-id="99d71-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="99d71-146">Varningar</span><span class="sxs-lookup"><span data-stu-id="99d71-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="99d71-147">Historiska slutpunktsdata</span><span class="sxs-lookup"><span data-stu-id="99d71-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="99d71-148">Svarsreaktion</span><span class="sxs-lookup"><span data-stu-id="99d71-148">Response orchestration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="99d71-149">Samlingen Collection Collection</span><span class="sxs-lookup"><span data-stu-id="99d71-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="99d71-150">Hotinformation</span><span class="sxs-lookup"><span data-stu-id="99d71-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="99d71-151">Avancerad detonation- och analystjänst</span><span class="sxs-lookup"><span data-stu-id="99d71-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="99d71-152">Avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="99d71-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="99d71-153">Anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="99d71-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="99d71-154">**[Automatiserad undersökning och åtgärder](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="99d71-155">Förutom att snabbt svara på avancerade attacker erbjuder Microsoft Defender för Endpoint funktioner för automatisk undersökning och åtgärder som hjälper till att minska mängden aviseringar i minuter i skala.</span><span class="sxs-lookup"><span data-stu-id="99d71-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="99d71-156">Automatiserad undersökning och åtgärder</span><span class="sxs-lookup"><span data-stu-id="99d71-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="99d71-157">Visa detaljer och resultat av automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="99d71-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="99d71-158">Visa och godkänna reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="99d71-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="99d71-159">**[Microsoft Hotexperter](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="99d71-160">Med Microsoft Defender för Endpoints nya tjänst för att hantera hot får du proaktiva produkter, prioritering samt ytterligare kontext och insikter.</span><span class="sxs-lookup"><span data-stu-id="99d71-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="99d71-161">Microsoft Hotexperter ytterligare möjligheter för säkerhetscenter (SOCs) att identifiera och reagera på hot snabbt och korrekt.</span><span class="sxs-lookup"><span data-stu-id="99d71-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="99d71-162">Riktad attackavisering</span><span class="sxs-lookup"><span data-stu-id="99d71-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="99d71-163">Experter på begäran</span><span class="sxs-lookup"><span data-stu-id="99d71-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="99d71-164">Konfigurera den hanterade Microsoft 365 i Defender</span><span class="sxs-lookup"><span data-stu-id="99d71-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="99d71-165">**[Centraliserad konfiguration och administration, API:er](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="99d71-166">Integrera Microsoft Defender för Slutpunkt i dina befintliga arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="99d71-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="99d71-167">Introduktioner</span><span class="sxs-lookup"><span data-stu-id="99d71-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="99d71-168">API- och SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="99d71-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="99d71-169">Exponerade API:er</span><span class="sxs-lookup"><span data-stu-id="99d71-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="99d71-170">Rollbaserad åtkomstkontroll (RBAC)</span><span class="sxs-lookup"><span data-stu-id="99d71-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="99d71-171">Rapportering och trender</span><span class="sxs-lookup"><span data-stu-id="99d71-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="99d71-172">**[Integrering med Microsoft-lösningar](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="99d71-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="99d71-173">Microsoft Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar, bland annat:</span><span class="sxs-lookup"><span data-stu-id="99d71-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="99d71-174">Intune</span><span class="sxs-lookup"><span data-stu-id="99d71-174">Intune</span></span>
- <span data-ttu-id="99d71-175">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="99d71-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="99d71-176">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="99d71-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="99d71-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="99d71-177">Azure Defender</span></span>
- <span data-ttu-id="99d71-178">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="99d71-178">Skype for Business</span></span>
- <span data-ttu-id="99d71-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="99d71-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="99d71-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="99d71-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="99d71-181">Med Microsoft 365 Defender skapar Microsoft Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit efter intrång som integreras inbyggt i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt svara på avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="99d71-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
