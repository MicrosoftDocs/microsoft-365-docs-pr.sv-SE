---
title: Hantering av hot och sårbarhet
description: Den här nya funktionen använder en riskbaserad metod för att upptäcka, prioritera och åtgärda eventuella svagheter och felkonfigurationer i slutpunkten.
keywords: threat & vulnerability management, threat and vulnerability management, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, vulnerability management, vulnerability assessment, threat and vulnerability scanning, secure configuration assessment, Microsoft Defender for Endpoint, endpoint vulnerabilities, next generation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934171"
---
# <a name="threat-and-vulnerability-management"></a><span data-ttu-id="94645-104">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="94645-104">Threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94645-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="94645-105">**Applies to:**</span></span>
- [<span data-ttu-id="94645-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="94645-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94645-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94645-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="94645-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="94645-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="94645-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="94645-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="94645-110">Att effektivt identifiera, utvärdera och åtgärda slutpunktsbrister är pivotalt i att köra ett hälsosamt säkerhetsprogram och minska organisationens risk.</span><span class="sxs-lookup"><span data-stu-id="94645-110">Effectively identifying, assessing, and remediating endpoint weaknesses is pivotal in running a healthy security program and reducing organizational risk.</span></span> <span data-ttu-id="94645-111">Hantering av hot och risker fungerar som en infrastruktur för att minska exponering av organisationen, hårdnande ändpunktsyta och öka organisationens motståndskraft.</span><span class="sxs-lookup"><span data-stu-id="94645-111">Threat and vulnerability management serves as an infrastructure for reducing organizational exposure, hardening endpoint surface area, and increasing organizational resilience.</span></span>

<span data-ttu-id="94645-112">Upptäck säkerhetsproblem och felkonfigurationer i realtid med sensorerna, och utan behov av agenter eller periodiska genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="94645-112">Discover vulnerabilities and misconfigurations in real time with sensors, and without the need of agents or periodic scans.</span></span> <span data-ttu-id="94645-113">Den prioriterar säkerhetsproblem utifrån hotbildens landskap, identifieringar i organisationen, känslig information om sårbara enheter och affärskontext.</span><span class="sxs-lookup"><span data-stu-id="94645-113">It prioritizes vulnerabilities based on the threat landscape, detections in your organization, sensitive information on vulnerable devices, and business context.</span></span>

<span data-ttu-id="94645-114">Titta på den här videon för en snabb överblick över hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="94645-114">Watch this video for a quick overview of threat and vulnerability management.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a><span data-ttu-id="94645-115">Fylla arbetsflödesgaparna</span><span class="sxs-lookup"><span data-stu-id="94645-115">Bridging the workflow gaps</span></span>

<span data-ttu-id="94645-116">Hantering av hot och sårbarheter är inbyggda, i realtid och använder molnet.</span><span class="sxs-lookup"><span data-stu-id="94645-116">Threat and vulnerability management is built in, real time, and cloud powered.</span></span> <span data-ttu-id="94645-117">Det är helt integrerat med Microsoft-slutpunktssäkerhetsstacken, Microsoft Intelligent Security Graph och kunskapsbasen för programanalyser.</span><span class="sxs-lookup"><span data-stu-id="94645-117">It's fully integrated with Microsoft endpoint security stack, the Microsoft Intelligent Security Graph, and the application analytics knowledge base.</span></span>  

<span data-ttu-id="94645-118">Sårbarhetshantering är den första lösningen i branschen för att överbrygga klyftan mellan säkerhetsadministration och IT-administration under åtgärdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="94645-118">Vulnerability management is the first solution in the industry to bridge the gap between security administration and IT administration during remediation process.</span></span> <span data-ttu-id="94645-119">Skapa en säkerhetsuppgift eller -biljett genom att integrera med Microsoft Intune och Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94645-119">Create a security task or ticket by integrating with Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span>

### <a name="real-time-discovery"></a><span data-ttu-id="94645-120">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="94645-120">Real-time discovery</span></span>

<span data-ttu-id="94645-121">För att upptäcka säkerhetsproblem och felkonfigurering använder hantering av hot och risker samma inbyggda Defender för slutpunktssensorer för att minska krångliga nätverkssökningar och IT-overhead.</span><span class="sxs-lookup"><span data-stu-id="94645-121">To discover endpoint vulnerabilities and misconfiguration, threat and vulnerability management uses the same agentless built-in Defender for Endpoint sensors to reduce cumbersome network scans and IT overhead.</span></span>

<span data-ttu-id="94645-122">Den innehåller även:</span><span class="sxs-lookup"><span data-stu-id="94645-122">It also provides:</span></span>

- <span data-ttu-id="94645-123">**Lager av enheter i realtid** – Enheter som introduceras till Defender för Endpoint rapporterar automatiskt och pushar sårbarhets- och säkerhetskonfigurationsdata till instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="94645-123">**Real-time device inventory** - Devices onboarded to Defender for Endpoint automatically report and push vulnerability and security configuration data to the dashboard.</span></span>
- <span data-ttu-id="94645-124">**Insyn i programvara och säkerhetsproblem** –optisk information om organisationens lager av programvara och programvaruändringar som installationer, avinstallationer och korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="94645-124">**Visibility into software and vulnerabilities** - Optics into the organization's software inventory, and software changes like installations, uninstalls, and patches.</span></span> <span data-ttu-id="94645-125">Nyligen identifierade säkerhetsproblem rapporteras med åtgärdsbara minskningar rekommendationer för program från första och tredje part.</span><span class="sxs-lookup"><span data-stu-id="94645-125">Newly discovered vulnerabilities are reported with actionable mitigation recommendations for 1st and 3rd party applications.</span></span>
- <span data-ttu-id="94645-126">**Application runtime context** – Synlighet för programanvändningsmönster för bättre prioritering och beslut.</span><span class="sxs-lookup"><span data-stu-id="94645-126">**Application runtime context** - Visibility on application usage patterns for better prioritization and decision-making.</span></span>
- <span data-ttu-id="94645-127">**Konfigurationssäkerhet** – insyn i organisationens säkerhetskonfiguration eller felaktig konfiguration.</span><span class="sxs-lookup"><span data-stu-id="94645-127">**Configuration posture** - Visibility into organizational security configuration or misconfigurations.</span></span> <span data-ttu-id="94645-128">Problem rapporteras i instrumentpanelen med interaktiva säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="94645-128">Issues are reported in the dashboard with actionable security recommendations.</span></span>

### <a name="intelligence-driven-prioritization"></a><span data-ttu-id="94645-129">Intelligence-driven prioritering</span><span class="sxs-lookup"><span data-stu-id="94645-129">Intelligence-driven prioritization</span></span>

<span data-ttu-id="94645-130">Hantering av hot och risker hjälper kunderna att prioritera och fokusera på de svagheter som utgör den mest brådskande och högsta risken för organisationen.</span><span class="sxs-lookup"><span data-stu-id="94645-130">Threat and vulnerability management helps customers prioritize and focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="94645-131">Den måste se till att rekommendationer om säkerhet finns med dynamiska hot och affärskontext:</span><span class="sxs-lookup"><span data-stu-id="94645-131">It fuses security recommendations with dynamic threat and business context:</span></span>

- <span data-ttu-id="94645-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span><span class="sxs-lookup"><span data-stu-id="94645-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span></span> <span data-ttu-id="94645-133">Hantering av hot och risker fokuserar på säkerhetsproblem som utnyttjas för närvarande i de jokertecken och nya hot som utgör den största risken.</span><span class="sxs-lookup"><span data-stu-id="94645-133">Threat and vulnerability management focuses on vulnerabilities currently being exploited in the wild and emerging threats that pose the highest risk.</span></span>
- <span data-ttu-id="94645-134">**Pinpointing av aktiva överträdelser** – Korrelerar hot och sårbarhetshantering och EDR-insikter för att prioritera säkerhetsproblem som utnyttjas i aktiva intrång i organisationen.</span><span class="sxs-lookup"><span data-stu-id="94645-134">**Pinpointing active breaches** - Correlates threat and vulnerability management and EDR insights to prioritize vulnerabilities being exploited in an active breach within the organization.</span></span>
- <span data-ttu-id="94645-135">**Skydda tillgångar med höga värden** – Identifiera exponerade enheter med affärskritiska program, konfidentiella data eller användare med höga värden.</span><span class="sxs-lookup"><span data-stu-id="94645-135">**Protecting high-value assets** - Identify the exposed devices with business-critical applications, confidential data, or high-value users.</span></span>

### <a name="seamless-remediation"></a><span data-ttu-id="94645-136">Smidig åtgärd</span><span class="sxs-lookup"><span data-stu-id="94645-136">Seamless remediation</span></span>

<span data-ttu-id="94645-137">Med hantering av hot och sårbarhet kan säkerhetsadministratörer och IT-administratörer samarbeta smidigt för att åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="94645-137">Threat and vulnerability management allows security administrators and IT administrators to collaborate seamlessly to remediate issues.</span></span>

- <span data-ttu-id="94645-138">**Åtgärdsförfrågningar som skickas till IT** – Skapa en åtgärdsuppgift i Microsoft Intune utifrån en viss säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="94645-138">**Remediation requests sent to IT** - Create a remediation task in Microsoft Intune from a specific security recommendation.</span></span> <span data-ttu-id="94645-139">Vi planerar att utöka den här funktionen till andra plattformar för IT-säkerhetshantering.</span><span class="sxs-lookup"><span data-stu-id="94645-139">We plan to expand this capability to other IT security management platforms.</span></span>
- <span data-ttu-id="94645-140">**Alternativa åtgärder – Få** insikter om ytterligare minskningar, till exempel konfigurationsändringar som kan minska risker som är associerade med svagheter i programvaran.</span><span class="sxs-lookup"><span data-stu-id="94645-140">**Alternate mitigations** - Gain insights on additional mitigations, such as configuration changes that can reduce risk associated with software vulnerabilities.</span></span>
- <span data-ttu-id="94645-141">**Status för åtgärder i realtid** – övervakning i realtid av status och status för åtgärdsaktiviteter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="94645-141">**Real-time remediation status** - Real-time monitoring of the status and progress of remediation activities across the organization.</span></span>

## <a name="threat-and-vulnerability-management-walk-through"></a><span data-ttu-id="94645-142">Genomgång av hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="94645-142">Threat and vulnerability management walk-through</span></span>

<span data-ttu-id="94645-143">I den här videon får du en omfattande genomgång av hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="94645-143">Watch this video for a comprehensive walk-through of threat and vulnerability management.</span></span>

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a><span data-ttu-id="94645-144">Navigeringsfönstret</span><span class="sxs-lookup"><span data-stu-id="94645-144">Navigation pane</span></span>

<span data-ttu-id="94645-145">Område</span><span class="sxs-lookup"><span data-stu-id="94645-145">Area</span></span> | <span data-ttu-id="94645-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="94645-146">Description</span></span>
:---|:---
<span data-ttu-id="94645-147">**Instrumentpanelen**</span><span class="sxs-lookup"><span data-stu-id="94645-147">**Dashboard**</span></span>   | <span data-ttu-id="94645-148">Få en högnivåvy av exponeringsresultatet för organisationen, Microsoft Secure Score för enheter, exponeringsfördelning av enheter, toppsäkerhetsrekommendationer, övre sårbar programvara, toppreparationsaktiviteter och top-exponerade enhetsdata.</span><span class="sxs-lookup"><span data-stu-id="94645-148">Get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span>
[<span data-ttu-id="94645-149">**Säkerhetsrekommendationer**</span><span class="sxs-lookup"><span data-stu-id="94645-149">**Security recommendations**</span></span>](tvm-security-recommendation.md) | <span data-ttu-id="94645-150">Se listan över säkerhetsrekommendationer och relaterad information om hot.</span><span class="sxs-lookup"><span data-stu-id="94645-150">See the list of security recommendations and related threat information.</span></span> <span data-ttu-id="94645-151">När du väljer ett objekt i listan öppnas en utfällbarhetspanel med sårbarhetsinformation, en länk för att öppna programvarusidan samt alternativ för åtgärder och undantag.</span><span class="sxs-lookup"><span data-stu-id="94645-151">When you select an item from the list, a flyout panel opens with vulnerability details, a link to open the software page, and remediation and exception options.</span></span> <span data-ttu-id="94645-152">Du kan också öppna ett ärende i Intune om dina enheter är anslutna via Azure Active Directory och du har aktiverat Dina Intune-anslutningar i Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="94645-152">You can also open a ticket in Intune if your devices are joined through Azure Active Directory and you've enabled your Intune connections in Defender for Endpoint.</span></span>
[<span data-ttu-id="94645-153">**Åtgärda**</span><span class="sxs-lookup"><span data-stu-id="94645-153">**Remediation**</span></span>](tvm-remediation.md) | <span data-ttu-id="94645-154">Se åtgärder som du har skapat och undantag från rekommendation.</span><span class="sxs-lookup"><span data-stu-id="94645-154">See remediation activities you've created and recommendation exceptions.</span></span>
[<span data-ttu-id="94645-155">**Programvaruinventering**</span><span class="sxs-lookup"><span data-stu-id="94645-155">**Software inventory**</span></span>](tvm-software-inventory.md) | <span data-ttu-id="94645-156">Visa listan över sårbar programvara i organisationen, tillsammans med information om säkerhet och hot.</span><span class="sxs-lookup"><span data-stu-id="94645-156">See the list of vulnerable software in your organization, along with weakness and threat information.</span></span>
[<span data-ttu-id="94645-157">**Svagheter**</span><span class="sxs-lookup"><span data-stu-id="94645-157">**Weaknesses**</span></span>](tvm-weaknesses.md) | <span data-ttu-id="94645-158">Se listan över vanliga säkerhetsproblem och exponeringar (CVEs) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="94645-158">See the list of common vulnerabilities and exposures (CVEs) in your organization.</span></span>
[<span data-ttu-id="94645-159">**Tidlinje för händelse**</span><span class="sxs-lookup"><span data-stu-id="94645-159">**Event timeline**</span></span>](threat-and-vuln-mgt-event-timeline.md) | <span data-ttu-id="94645-160">Visa händelser som kan påverka organisationens risk.</span><span class="sxs-lookup"><span data-stu-id="94645-160">View events that may impact your organization's risk.</span></span>

## <a name="apis"></a><span data-ttu-id="94645-161">API:er</span><span class="sxs-lookup"><span data-stu-id="94645-161">APIs</span></span>

<span data-ttu-id="94645-162">Kör API-anrop som rör hot och sårbarhetshantering för att automatisera arbetsflöden för hantering av sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="94645-162">Run threat and vulnerability management-related API calls to automate vulnerability management workflows.</span></span> <span data-ttu-id="94645-163">Läs mer i det [här Microsoft Tech Community-blogginlägget](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span><span class="sxs-lookup"><span data-stu-id="94645-163">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

<span data-ttu-id="94645-164">Se följande artiklar för relaterade API:er:</span><span class="sxs-lookup"><span data-stu-id="94645-164">See the following articles for related APIs:</span></span>

- [<span data-ttu-id="94645-165">Microsoft Defender för Endpoint API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="94645-165">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="94645-166">Dator-API:er</span><span class="sxs-lookup"><span data-stu-id="94645-166">Machine APIs</span></span>](machine.md)
- [<span data-ttu-id="94645-167">API:er för rekommendation</span><span class="sxs-lookup"><span data-stu-id="94645-167">Recommendation APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="94645-168">Poäng-API:er</span><span class="sxs-lookup"><span data-stu-id="94645-168">Score APIs</span></span>](score.md)
- [<span data-ttu-id="94645-169">Programvaru-API:er</span><span class="sxs-lookup"><span data-stu-id="94645-169">Software APIs</span></span>](software.md)
- [<span data-ttu-id="94645-170">Sårbarhets-API:er</span><span class="sxs-lookup"><span data-stu-id="94645-170">Vulnerability APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="94645-171">Lista sårbarheter efter maskin och programvara</span><span class="sxs-lookup"><span data-stu-id="94645-171">List vulnerabilities by machine and software</span></span>](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a><span data-ttu-id="94645-172">Se även</span><span class="sxs-lookup"><span data-stu-id="94645-172">See also</span></span>

- [<span data-ttu-id="94645-173">Operativsystem och plattformar som stöds</span><span class="sxs-lookup"><span data-stu-id="94645-173">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="94645-174">Instrumentpanel för hantering av hot och hot</span><span class="sxs-lookup"><span data-stu-id="94645-174">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="94645-175">BLOGG: Microsofts & sårbarhetshantering hjälper nu tusentals kunder att upptäcka, prioritera och åtgärda säkerhetsproblem i realtid</span><span class="sxs-lookup"><span data-stu-id="94645-175">BLOG: Microsoft's Threat & Vulnerability Management now helps thousands of customers to discover, prioritize, and remediate vulnerabilities in real time</span></span>](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
