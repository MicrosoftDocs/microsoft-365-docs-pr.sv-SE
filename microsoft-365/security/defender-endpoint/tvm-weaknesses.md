---
title: Säkerhetsproblem i min organisation – hantering av hot och risker
description: Här listas vanliga säkerhetsproblem och exponeringar (CVE) för svagheter i den programvara som körs i organisationen. Upptäcks av Microsoft Defender för funktioner för slutpunktshot och sårbarhetshantering.
keywords: Microsoft Defender för slutpunktshot & sårbarhetshantering, hot och sårbarhetshantering, Microsoft Defender för Endpoint tvm-sida för att hitta svagheter via tvm, tvm-sårbarhetslista, sårbarhetsinformation i tvm
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8039a06dc58c31158f90d39857ffbeba92138d5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933079"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="5e059-105">Säkerhetsproblem i min organisation – hantering av hot och risker</span><span class="sxs-lookup"><span data-stu-id="5e059-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5e059-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5e059-106">**Applies to:**</span></span>
- [<span data-ttu-id="5e059-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5e059-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5e059-108">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="5e059-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5e059-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e059-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5e059-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5e059-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5e059-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5e059-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="5e059-112">Hantering av hot och risker använder samma signaler i Defender för Endpoints slutpunktsskydd för att söka igenom och upptäcka svagheter.</span><span class="sxs-lookup"><span data-stu-id="5e059-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="5e059-113">På **sidan Svagheter** visas svagheter i programvaran som dina enheter exponeras för genom att lista CVE-ID (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="5e059-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="5e059-114">Du kan också se allvarlighetsgrad, CVSS-klassificering (Common Vulnerability Rating System), aktuella uppgifter i organisationen, motsvarande intrång, hotinsikter med mera.</span><span class="sxs-lookup"><span data-stu-id="5e059-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="5e059-115">Om det inte finns någon officiell CVE-ID tilldelad till en sårbarhet, tilldelas sårbarhetsnamnet med hjälp av hantering av hot och sårbarhet.</span><span class="sxs-lookup"><span data-stu-id="5e059-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="5e059-116">E-postmeddelanden om nya sårbarhetshändelser finns i [Konfigurera e-postaviseringar om säkerhetsrisk i Microsoft Defender för slutpunkt](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="5e059-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="5e059-117">Gå till sidan Svagheter</span><span class="sxs-lookup"><span data-stu-id="5e059-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="5e059-118">Gå till sidan Svagheter på ett par olika sätt:</span><span class="sxs-lookup"><span data-stu-id="5e059-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="5e059-119">Välja **Känslighet** från navigeringsmenyn för hot och sårbarhetshantering i [Microsoft Defender Säkerhetscenter](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5e059-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="5e059-120">Global sökning</span><span class="sxs-lookup"><span data-stu-id="5e059-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="5e059-121">Navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="5e059-121">Navigation menu</span></span>

<span data-ttu-id="5e059-122">Gå till navigeringsmenyn för hot och sårbarhetshantering och välj **Svagheter** för att öppna listan över CV:er.</span><span class="sxs-lookup"><span data-stu-id="5e059-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="5e059-123">Säkerhetsproblem i global sökning</span><span class="sxs-lookup"><span data-stu-id="5e059-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="5e059-124">Gå till den nedrullningsmenyn för global sökning.</span><span class="sxs-lookup"><span data-stu-id="5e059-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="5e059-125">Välj **Sårbarhet** och nyckel i det vanliga säkerhetsproblem och exponerings-ID (CVE) som du letar efter och välj sedan sökikonen.</span><span class="sxs-lookup"><span data-stu-id="5e059-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="5e059-126">Sidan **Bevarande** öppnas med den CVE-information som du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5e059-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="5e059-127">![Global sökruta med listrutan "sårbarhet" markerat och ett exempel på CVE.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="5e059-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="5e059-128">Välj CVE för att öppna en utfällbarhetspanel med mer information, inklusive sårbarhetsbeskrivning, information om hot, hotinsikter och exponerade enheter.</span><span class="sxs-lookup"><span data-stu-id="5e059-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="5e059-129">Om du vill se resten av svagheterna på sidan **Förvarna** skriver du CVE och väljer sedan sök.</span><span class="sxs-lookup"><span data-stu-id="5e059-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="5e059-130">Översikt över svagheter</span><span class="sxs-lookup"><span data-stu-id="5e059-130">Weaknesses overview</span></span>

<span data-ttu-id="5e059-131">Åtgärda säkerhetsproblem i exponerade enheter för att minska risken för tillgångar och organisation.</span><span class="sxs-lookup"><span data-stu-id="5e059-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="5e059-132">Om kolumnen **Exponerade** enheter visar 0, innebär det att du inte är i riskabelt fall.</span><span class="sxs-lookup"><span data-stu-id="5e059-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Svagheter på startsidan.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="5e059-134">Insikter om intrång och hot</span><span class="sxs-lookup"><span data-stu-id="5e059-134">Breach and threat insights</span></span>

<span data-ttu-id="5e059-135">Visa eventuella relaterade insikter om intrång och hot **i kolumnen** Hot när ikonerna är röda.</span><span class="sxs-lookup"><span data-stu-id="5e059-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="5e059-136">Prioritera alltid rekommendationer som är associerade med pågående hot.</span><span class="sxs-lookup"><span data-stu-id="5e059-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="5e059-137">Dessa rekommendationer markeras med ikonen för ![ hotinsikter Enkel ritning av ett rött fel.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="5e059-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="5e059-138">och insiktsikonen ![ Enkel ritning av en pil som ska nå ett ](images/tvm_alert_icon.png) mål. .</span><span class="sxs-lookup"><span data-stu-id="5e059-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="5e059-139">Ikonen för intrångsinformation markeras om det finns en säkerhetsrisk i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5e059-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="5e059-140">![Exempel på text med intrångsinformation som kan visas när du hovrar över en ikon.</span><span class="sxs-lookup"><span data-stu-id="5e059-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="5e059-141">Den här säger "möjlig aktiv avisering är kopplad till den här rekommendationen.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="5e059-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="5e059-142">Ikonen för hotinsikter markeras om det finns associerade sårbarheter i den sårbarhet som finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5e059-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="5e059-143">Hovra över ikonen för att se om risken är en del av en sårbarhetssats eller kopplad till specifika avancerade beständiga kampanjer eller aktivitetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5e059-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="5e059-144">När rapporten är tillgänglig finns det en länk till en rapport om hotanalys där det inte finns några dagars användningsnyheter, avslöjanden eller relaterade säkerhetsrådgivare.</span><span class="sxs-lookup"><span data-stu-id="5e059-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Text med hotinsikter som kan visas när du hovrar över en ikon.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="5e059-147">Få sårbarhetsinsikter</span><span class="sxs-lookup"><span data-stu-id="5e059-147">Gain vulnerability insights</span></span>

<span data-ttu-id="5e059-148">Om du väljer en CVE öppnas en utfällbarhetspanel med mer information, till exempel sårbarhetsbeskrivning, information, information om hot och exponerade enheter.</span><span class="sxs-lookup"><span data-stu-id="5e059-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="5e059-149">Kategorin "OS-funktion" visas i relevanta scenarier</span><span class="sxs-lookup"><span data-stu-id="5e059-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="5e059-150">Du kan gå till relaterad säkerhetsrekommendationer för varje CVE med exponerade enheter</span><span class="sxs-lookup"><span data-stu-id="5e059-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Det utfällfälle exemplet Flygblad.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="5e059-152">Programvara som inte stöds</span><span class="sxs-lookup"><span data-stu-id="5e059-152">Software that isn't supported</span></span>

<span data-ttu-id="5e059-153">CV:er för programvara som för närvarande inte stöds av & sårbarhetshantering finns fortfarande på sidan Förskanning.</span><span class="sxs-lookup"><span data-stu-id="5e059-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="5e059-154">Eftersom programvaran inte stöds är endast begränsade data tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="5e059-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="5e059-155">Information om exponerade enheter kommer inte att vara tillgänglig för CV:er med programvara som inte stöds.</span><span class="sxs-lookup"><span data-stu-id="5e059-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="5e059-156">Filtrera efter programvara som inte stöds genom att välja alternativet "Inte tillgängligt" i avsnittet "Exponerade enheter".</span><span class="sxs-lookup"><span data-stu-id="5e059-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Filtrera exponerade enheter.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="5e059-158">Visa vanliga säkerhetsproblem och exponeringar (CVE) på andra platser</span><span class="sxs-lookup"><span data-stu-id="5e059-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="5e059-159">Mest sårbar programvara på instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="5e059-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="5e059-160">Gå till [instrumentpanelen för hot och sårbarhetshantering](tvm-dashboard-insights.md) och rulla ned till den **mest sårbara programvaruwidgeten.**</span><span class="sxs-lookup"><span data-stu-id="5e059-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="5e059-161">Du kommer att se antalet svagheter i varje programvara, tillsammans med information om hot och en detaljerad bild av exponering av enheter över tid.</span><span class="sxs-lookup"><span data-stu-id="5e059-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Övre sårbara programvarukort med fyra kolumner: programvara, svagheter, hot, exponerade enheter.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="5e059-163">Välj den programvara du vill undersöka för att gå till en sida med en detaljgranskning.</span><span class="sxs-lookup"><span data-stu-id="5e059-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="5e059-164">Välj fliken **Identifierade säkerhetsproblem.**</span><span class="sxs-lookup"><span data-stu-id="5e059-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="5e059-165">Välj det säkerhetsproblem du vill undersöka för mer information om sårbarhetsinformation</span><span class="sxs-lookup"><span data-stu-id="5e059-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Windows Server 2019 – granska nedåt – översikt.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="5e059-167">Upptäck säkerhetsproblem på enhetssidan</span><span class="sxs-lookup"><span data-stu-id="5e059-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="5e059-168">Visa relaterad information om svagheter på enhetens sida.</span><span class="sxs-lookup"><span data-stu-id="5e059-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="5e059-169">Gå till menyraden för navigering i Microsoft Defender Säkerhetscenter och välj sedan enhetsikonen.</span><span class="sxs-lookup"><span data-stu-id="5e059-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="5e059-170">Sidan **Enheter öppnas.**</span><span class="sxs-lookup"><span data-stu-id="5e059-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="5e059-171">På sidan **Enheter väljer** du namnet på enheten som du vill undersöka.</span><span class="sxs-lookup"><span data-stu-id="5e059-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Enhetslista med vald enhet att undersöka.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="5e059-173">Enhetens sida öppnas med information och svarsalternativ för den enhet du vill undersöka.</span><span class="sxs-lookup"><span data-stu-id="5e059-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="5e059-174">Välj **Identifierade säkerhetsproblem**.</span><span class="sxs-lookup"><span data-stu-id="5e059-174">Select **Discovered vulnerabilities**.</span></span>

    ![Sida för enhet med information och svarsalternativ.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="5e059-176">Välj det sårbarhet som du vill undersöka för att öppna en utfällbarhetspanel med CVE-information, till exempel: sårbarhetsbeskrivning, hotinsikter och identifieringslogik.</span><span class="sxs-lookup"><span data-stu-id="5e059-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="5e059-177">Logik för identifiering av CVE</span><span class="sxs-lookup"><span data-stu-id="5e059-177">CVE Detection logic</span></span>

<span data-ttu-id="5e059-178">I likhet med programvarubevisen visar vi nu den identifieringslogik vi använt på en enhet för att visa att den är sårbar.</span><span class="sxs-lookup"><span data-stu-id="5e059-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="5e059-179">Det nya avsnittet kallas "Identifieringslogik" (i alla identifierade problem på enhetssidan) och visar identifieringslogiken och källan.</span><span class="sxs-lookup"><span data-stu-id="5e059-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="5e059-180">Kategorin "OS-funktion" visas också i relevanta scenarier.</span><span class="sxs-lookup"><span data-stu-id="5e059-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="5e059-181">En CVE skulle påverka enheter som kör ett sårbart operativsystem endast om en specifik OS-komponent är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="5e059-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="5e059-182">Anta att Windows Server 2019 har en säkerhetsrisk i DNS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="5e059-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="5e059-183">Med den här nya funktionen kommer vi bara att ansluta denna CVE till Windows Server 2019-enheter med DNS-funktionen aktiverad i operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="5e059-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Exempel på identifieringslogik med den programvara som upptäckts på enheten och KB:er.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="5e059-185">Rapportera felaktigheter</span><span class="sxs-lookup"><span data-stu-id="5e059-185">Report inaccuracy</span></span>

<span data-ttu-id="5e059-186">Rapportera en falsk positiv när du ser någon vag, felaktig eller ofullständig information.</span><span class="sxs-lookup"><span data-stu-id="5e059-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="5e059-187">Du kan också rapportera säkerhetsrekommendationer som redan har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="5e059-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="5e059-188">Öppna CVE på sidan Försv.</span><span class="sxs-lookup"><span data-stu-id="5e059-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="5e059-189">Välj **Rapportens felaktigheter så** öppnas ett utfällt fönster.</span><span class="sxs-lookup"><span data-stu-id="5e059-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="5e059-190">Välj kategorin felaktigheter i den nedrullningrullningsmenyn och fyll i din e-postadress och information om felaktigheter.</span><span class="sxs-lookup"><span data-stu-id="5e059-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="5e059-191">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="5e059-191">Select **Submit**.</span></span> <span data-ttu-id="5e059-192">Din feedback skickas omedelbart till experter på hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="5e059-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5e059-193">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5e059-193">Related articles</span></span>

- [<span data-ttu-id="5e059-194">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="5e059-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5e059-195">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="5e059-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="5e059-196">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="5e059-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="5e059-197">Instrumentpanelsinsikter</span><span class="sxs-lookup"><span data-stu-id="5e059-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="5e059-198">Visa och ordna listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="5e059-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
