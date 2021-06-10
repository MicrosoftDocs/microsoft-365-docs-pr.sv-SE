---
title: Microsoft Defender för Endpoint
description: Microsoft Defender för Endpoint är en plattform för säkerhet för företagsslutpunkter som hjälper dem att försvara sig mot avancerade fortlöpande hot.
keywords: introduktion till Microsoft Defender för Endpoint, introduktion till Microsoft Defender för Endpoint, cybersäkerhet, avancerade fortlöpande hot, företagssäkerhet, sensor för maskinbeteende, molnsäkerhet, analys, hotinformation, minskning av hotytan, nästa generations skydd, automatisk undersökning och åtgärd, microsoft threat-experter, säker poäng, avancerad sökning, Microsoft 365 Defender, cyberhotssäkerhet
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3bab9d0248a2ed8e83807f3c38215e653cba26eb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843560"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="74049-104">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74049-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74049-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74049-105">**Applies to:**</span></span>
- [<span data-ttu-id="74049-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74049-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74049-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74049-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74049-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="74049-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74049-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="74049-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="74049-110">Mer information om Windows 10 Enterprise Edition-funktioner finns i [Windows 10 Enterprise utgåva.](https://www.microsoft.com/WindowsForBusiness/buy)</span><span class="sxs-lookup"><span data-stu-id="74049-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="74049-111">Microsoft Defender för Endpoint är en säkerhetsplattform för företag som utformats för att hjälpa företagsnätverk att förhindra, upptäcka, undersöka och hantera avancerade hot.</span><span class="sxs-lookup"><span data-stu-id="74049-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="74049-112">Defender för Endpoint använder följande kombination av teknik som är inbyggd i Windows 10 och Microsofts robusta molntjänst:</span><span class="sxs-lookup"><span data-stu-id="74049-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="74049-113">**Slutpunktsbeteendesensorer:** Inbäddade i Windows 10 samlar dessa sensorer in och processbeteendesignaler från operativsystemet och skickar sensordata till din privata, isolerade molninstans av Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="74049-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="74049-114">Molnsäkerhetsanalyser: Utnyttja stora data, enhetsinlärning och unik Microsoft-optisk användning över Windows-ekosystem, företagmolnprodukter (till exempel Office 365) och onlinetillgångar, funktionssignaler översättas till insikter, identifieringar och rekommenderade svar på avancerade hot.</span><span class="sxs-lookup"><span data-stu-id="74049-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="74049-115">**Hotinformation:** Genereras av Microsoft-säkerhetsteam, säkerhetsteam och utökas av hotinformation som tillhandahålls av partner, och med hjälp av hotinformation kan Defender för Endpoint identifiera attackersverktyg, tekniker och procedurer, och generera aviseringar när de observeras i insamlade sensordata.</span><span class="sxs-lookup"><span data-stu-id="74049-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="74049-116">Microsoft Defender för Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="74049-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="74049-117"><b>Hot & sårbarhetshantering</b></center></a></span><span class="sxs-lookup"><span data-stu-id="74049-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="74049-118"><b>Minskning av attackytan</b></center></a></span><span class="sxs-lookup"><span data-stu-id="74049-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="74049-119"><b>Nästa generations skydd</b></a></center></span><span class="sxs-lookup"><span data-stu-id="74049-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="74049-120"><b>Identifiering och svar av slutpunkter</b></a></center></span><span class="sxs-lookup"><span data-stu-id="74049-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="74049-121"><b>Automatiserad undersökning och åtgärder</b></a></center></span><span class="sxs-lookup"><span data-stu-id="74049-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="74049-122"><b>Microsoft Hotexperter</b></a></center></span><span class="sxs-lookup"><span data-stu-id="74049-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="74049-123">
<a href="#apis"><center><b>Centraliserad konfiguration och administration, API:er</a></span><span class="sxs-lookup"><span data-stu-id="74049-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="74049-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="74049-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="74049-125">Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Nyheter i Microsoft Defender för slutpunkt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="74049-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="74049-126">Microsoft Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="74049-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="74049-127">Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="74049-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="74049-128">**[Hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="74049-129">Den inbyggda funktionen använder en spelförändrande riskbaserad metod för identifiering, prioritering och åtgärd av svagheter och felkonfigurationer i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="74049-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="74049-130">**[Minskning av attackytan](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="74049-131">Minskningsuppsättningen för attackytan ger den första försvarslinjen i högen.</span><span class="sxs-lookup"><span data-stu-id="74049-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="74049-132">Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kan funktionerna motarbeta angrepp och användning.</span><span class="sxs-lookup"><span data-stu-id="74049-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="74049-133">Den här uppsättningen funktioner omfattar även [nätverksskydd och](network-protection.md) [webbskydd, som](web-protection-overview.md)reglerar åtkomsten till skadliga IP-adresser, domäner och URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="74049-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="74049-134">**[Nästa generations skydd](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="74049-134">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="74049-135">För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="74049-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="74049-136">**[Identifiering och svar för slutpunkt](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="74049-137">Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och hantera avancerade hot som kan ha gjort det förbi de två första säkerhetspelarna.</span><span class="sxs-lookup"><span data-stu-id="74049-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="74049-138">[Avancerad sökning](advanced-hunting-overview.md) är ett frågebaserat verktyg för hotsökning som gör att du proaktivt kan hitta överträdelser och skapa anpassade identifieringar.</span><span class="sxs-lookup"><span data-stu-id="74049-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="74049-139">**[Automatiserad undersökning och åtgärder](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="74049-140">I kombination med att snabbt kunna svara på avancerade attacker erbjuder Microsoft Defender för Endpoint funktioner för automatisk undersökning och åtgärder som hjälper till att minska mängden aviseringar i minuter i skala.</span><span class="sxs-lookup"><span data-stu-id="74049-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="74049-141">**[Microsoft Secure Score för enheter](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="74049-142">Defender för Endpoint innehåller Microsoft Secure Score för enheter som hjälper dig att dynamiskt bedöma företagsnätverkets säkerhetstillstånd, identifiera oskyddade system och vidta rekommenderade åtgärder för att förbättra organisationens övergripande säkerhet.</span><span class="sxs-lookup"><span data-stu-id="74049-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="74049-143">**[Microsoft Hotexperter](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="74049-144">Med Microsoft Defender för Endpoints nya tjänst för att hantera hot kan du proaktiva produkter, prioritera samt ytterligare kontext och insikter som ytterligare ger säkerhetscenter (SOCs) möjlighet att identifiera och reagera på hot snabbt och korrekt.</span><span class="sxs-lookup"><span data-stu-id="74049-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="74049-145">Defender för Endpoint-kunder måste söka efter Microsoft Hotexperter-tjänsten för hanterade hot för att få proaktiva riktade attackmeddelanden och samarbeta med experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="74049-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="74049-146">Experter på begäran är en tilläggstjänst.</span><span class="sxs-lookup"><span data-stu-id="74049-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="74049-147">Riktade attackmeddelanden inkluderas alltid när du har godkänts för Microsoft Hotexperter av hot efter hot.</span><span class="sxs-lookup"><span data-stu-id="74049-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="74049-148">Om du inte är registrerad ännu och vill uppleva fördelarna går du till fliken <b>Allmänna Inställningar</b> > <b></b> > <b>som du</b> > <b>Microsoft Hotexperter</b> använda.</span><span class="sxs-lookup"><span data-stu-id="74049-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="74049-149">När du accepterat, får du fördelarna med riktade attackmeddelanden och påbörja en 90-dagars utvärderingsversion av experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="74049-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="74049-150">Kontakta din Microsoft-representant för att få en fullständig prenumeration för Experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="74049-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="74049-151">**[Centraliserad konfiguration och administration, API:er](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="74049-152">Integrera Microsoft Defender för Slutpunkt i dina befintliga arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="74049-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="74049-153">**[Integrering med Microsoft-lösningar](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="74049-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="74049-154">Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar, bland annat:</span><span class="sxs-lookup"><span data-stu-id="74049-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="74049-155">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="74049-155">Azure Defender</span></span>
- <span data-ttu-id="74049-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="74049-156">Azure Sentinel</span></span>
- <span data-ttu-id="74049-157">Intune</span><span class="sxs-lookup"><span data-stu-id="74049-157">Intune</span></span>
- <span data-ttu-id="74049-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74049-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="74049-159">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="74049-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="74049-160">Microsoft Defender för Office</span><span class="sxs-lookup"><span data-stu-id="74049-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="74049-161">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="74049-161">Skype for Business</span></span>

<span data-ttu-id="74049-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="74049-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="74049-163">Med Microsoft 365 Defender skapar Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit efter intrång som inbyggt integreras i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt reagera på avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="74049-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="74049-164">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="74049-164">Related topic</span></span>
[<span data-ttu-id="74049-165">Microsoft Defender för Slutpunkt hjälper till att identifiera avancerade hot</span><span class="sxs-lookup"><span data-stu-id="74049-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
