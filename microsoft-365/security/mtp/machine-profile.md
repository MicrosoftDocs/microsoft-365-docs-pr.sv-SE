---
title: Maskinprofil i Microsoft 365-säkerhetsportalen
description: Visa risk- och exponeringsnivåer för en enhet i organisationen. Analysera tidigare och nuvarande hot och skydda maskinen med de senaste uppdateringarna.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, Microsoft Threat Protection, MTP, security center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, maskinsida, maskinlista, datorprofil
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895469"
---
# <a name="machine-profile-page"></a><span data-ttu-id="faf7e-105">Sidan Maskinprofil</span><span class="sxs-lookup"><span data-stu-id="faf7e-105">Machine profile page</span></span>

<span data-ttu-id="faf7e-106">Microsoft 365-säkerhetsportalen ger dig datorprofilsidor, så att du kan bedöma hälsotillståndet och statusen för enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="faf7e-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="faf7e-107">Varje datorprofilsida innehåller en mängd information om enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="faf7e-108">Du kan granska djupgående information om vilken programvara den kör, eventuella tidigare och nuvarande säkerhetshändelser eller varningar och hitta länkar till relevanta programkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="faf7e-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="faf7e-109">Du kan också använda datorprofilen för att utföra vanliga säkerhetsrelaterade uppgifter och snabbt granska grundläggande information om enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="faf7e-110">Navigera på profilsidan För maskin</span><span class="sxs-lookup"><span data-stu-id="faf7e-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="faf7e-111">Maskinprofilsidan är uppdelad i tre sektioner.</span><span class="sxs-lookup"><span data-stu-id="faf7e-111">The machine profile page is broken up into three sections.</span></span>

![Bild av maskinprofilsida med (1) Tabbområde (2) Sidofält och (3) Åtgärder markerade i rött](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="faf7e-113">Huvudinnehållsområdet (1) innehåller sju flikar som du kan växla igenom för att visa olika typer av information om maskinen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-113">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="faf7e-114">Sidofältet (2) listar grundläggande detaljer om maskinen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-114">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="faf7e-115">Det finns också svarsåtgärder som är tillgängliga i ett sidhuvud (3) före sidofältet och huvudinnehållsavsnitten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-115">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="faf7e-116">Du kan använda åtgärderna i det här huvudet för att utföra vanliga säkerhetsrelaterade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="faf7e-116">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="faf7e-117">Avsnittet Flikar</span><span class="sxs-lookup"><span data-stu-id="faf7e-117">Tabs section</span></span>

<span data-ttu-id="faf7e-118">Med flikarna Maskinprofil kan du växla genom en översikt över säkerhetsinformation om datorn och tabeller som innehåller en lista med aviseringar, en tidslinje, en lista över säkerhetsrekommendationer, en programvaruinventering, en lista över identifierade sårbarheter och saknas KBs (säkerhetsuppdateringar).</span><span class="sxs-lookup"><span data-stu-id="faf7e-118">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="faf7e-119">Fliken Översikt</span><span class="sxs-lookup"><span data-stu-id="faf7e-119">Overview tab</span></span>

<span data-ttu-id="faf7e-120">Standardfliken är **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="faf7e-120">The default tab is **Overview**.</span></span> <span data-ttu-id="faf7e-121">Det ger en snabb titt på det viktigaste säkerhetsfaktat om enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-121">It provides a quick look at the most important security fact about the device.</span></span>

![Bild av översiktsfliken för Datorprofil](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="faf7e-123">Här kan du hitta ett diagram över enhetens risknivå och aktiva varningar, alla som för närvarande är inloggade på användare, en kort lista över de flesta och minst frekventa användare och säkerhetsbedömningar som beskriver enhetens exponeringsnivå, säkerhetsrekommendationer, påverkad programvara och upptäckta sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="faf7e-123">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="faf7e-124">Fliken Aviseringar</span><span class="sxs-lookup"><span data-stu-id="faf7e-124">Alerts tab</span></span>

<span data-ttu-id="faf7e-125">Fliken **Aviseringar** innehåller en lista över aviseringar som har rapporterats på enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-125">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![Bild på fliken aviseringar för datorprofil](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="faf7e-127">Du kan anpassa antalet objekt som visas, samt vilka kolumner som visas för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="faf7e-127">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="faf7e-128">Standardbeteendet är att lista 30 objekt per sida och att 11 kolumner växlas på att visas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-128">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="faf7e-129">Kolumnerna på den här fliken innehåller information om allvarlighetsgraden för det hot som utlöste aviseringen, samt status, undersökningstillstånd och vem om någon aviseringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="faf7e-129">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="faf7e-130">Kolumnen *påverkade entiteter* refererar till den dator (entitet) vars profil du för närvarande visar, plus alla andra datorer i nätverket som påverkas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-130">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="faf7e-131">Om du väljer ett objekt i den här listan öppnas en länk till den valda aviseringen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-131">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="faf7e-132">Den här listan kan filtreras efter allvarlighetsgrad, status eller mottagare.</span><span class="sxs-lookup"><span data-stu-id="faf7e-132">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="faf7e-133">Fliken Tidslinje</span><span class="sxs-lookup"><span data-stu-id="faf7e-133">Timeline tab</span></span>

<span data-ttu-id="faf7e-134">Fliken **Tidslinje** innehåller ett interaktivt, kronologiskt diagram över händelser som lyfts upp på enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-134">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="faf7e-135">Genom att flytta det markerade området i diagrammet kan du visa händelser över olika tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="faf7e-135">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="faf7e-136">Du kan också skriva in ett anpassat datumintervall.</span><span class="sxs-lookup"><span data-stu-id="faf7e-136">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="faf7e-137">Nedanför diagrammet finns en lista över händelser för det valda datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="faf7e-137">Below the chart is a list of events for the selected range of dates.</span></span>

![Bild på fliken Tidslinje för Datorprofil](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="faf7e-139">Antalet objekt som visas och kolumnerna i listan kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-139">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="faf7e-140">Standardkolumnerna listar händelsetid, aktiv användare, åtgärdstyp, entiteter (processer) och ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-140">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="faf7e-141">Om du väljer ett objekt i listan öppnas ett utfällbart objekt som visar ett diagram över en entiteter för händelser som visar de överordnade och underordnade processer som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-141">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="faf7e-142">Den här listan kan filtreras efter den specifika typen av händelse. till exempel registerhändelser eller smartskärmshändelser.</span><span class="sxs-lookup"><span data-stu-id="faf7e-142">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="faf7e-143">Fliken Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="faf7e-143">Security recommendations tab</span></span>

<span data-ttu-id="faf7e-144">På fliken **Säkerhetsrekommendationer** visas åtgärder som du kan vidta för att skydda enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-144">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="faf7e-145">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt där du kan få instruktioner om hur du tillämpar rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-145">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Bild av fliken säkerhetsrekommendationer för datorprofil](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="faf7e-147">Precis som med föregående flikar kan antalet objekt som visas per sida och vilka kolumner som är synliga anpassas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-147">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="faf7e-148">Standardvyn innehåller kolumner som beskriver de säkerhetsbrister som åtgärdats, det associerade hotet, den relaterade komponenten eller programvaran som påverkas av hotet med mera.</span><span class="sxs-lookup"><span data-stu-id="faf7e-148">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="faf7e-149">Artiklar kan filtreras efter rekommendationens status.</span><span class="sxs-lookup"><span data-stu-id="faf7e-149">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="faf7e-150">Inventering av programvara</span><span class="sxs-lookup"><span data-stu-id="faf7e-150">Software inventory</span></span>

<span data-ttu-id="faf7e-151">På fliken **Programvaruinventering** visas programvara som är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-151">The **Software inventory** tab lists software installed on the device.</span></span>

![Bild av fliken inventering av programvara för maskinprofil](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="faf7e-153">Standardvyn visar programvaruleverantören, installerat versionsnummer, antal kända programvarubrister, hotinsikter, produktkod och taggar.</span><span class="sxs-lookup"><span data-stu-id="faf7e-153">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="faf7e-154">Antalet objekt som visas och vilka kolumner som visas kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-154">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="faf7e-155">Om du väljer ett objekt från den här listan öppnas ett utfällbart objekt som innehåller mer information om den valda programvaran, samt sökvägen och tidsstämpeln för den senaste gången programvaran hittades.</span><span class="sxs-lookup"><span data-stu-id="faf7e-155">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="faf7e-156">Den här listan kan filtreras efter produktkod.</span><span class="sxs-lookup"><span data-stu-id="faf7e-156">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="faf7e-157">Fliken Upptäckta säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="faf7e-157">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="faf7e-158">På fliken **Identifierade säkerhetsproblem** visas alla vanliga sårbarheter och Ã¤r Ã¤nder (CVE) som kan påverka enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-158">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Bild av fliken upptäckta sårbarheter för datorprofil](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="faf7e-160">Standardvyn visar allvarlighetsgraden för CVE, CVS (Common Vulnerability Score), programvaran som är relaterad till CVE, när CVE publicerades, när CVE senast uppdaterades och hot som är associerade med CVE.</span><span class="sxs-lookup"><span data-stu-id="faf7e-160">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="faf7e-161">Precis som med föregående flikar kan antalet objekt som visas och vilka kolumner som är synliga anpassas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-161">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="faf7e-162">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt som beskriver CVE.</span><span class="sxs-lookup"><span data-stu-id="faf7e-162">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="faf7e-163">KBs saknas</span><span class="sxs-lookup"><span data-stu-id="faf7e-163">Missing KBs</span></span>

<span data-ttu-id="faf7e-164">På fliken **Saknade KBs** visas alla Microsoft-uppdateringar som ännu inte har tillämpats på datorn.</span><span class="sxs-lookup"><span data-stu-id="faf7e-164">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="faf7e-165">De "KBs" i fråga är [Knowledge Base artiklar](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) som beskriver dessa uppdateringar; till exempel [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="faf7e-165">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Bild på fliken saknade kbs för datorprofil](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="faf7e-167">Standardvyn visar bulletinen som innehåller uppdateringar, OS-version, berörda produkter, CVEs-adresserade, KB-numret och taggarna.</span><span class="sxs-lookup"><span data-stu-id="faf7e-167">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="faf7e-168">Antalet objekt som visas per sida och vilka kolumner som visas kan anpassas.</span><span class="sxs-lookup"><span data-stu-id="faf7e-168">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="faf7e-169">Om du väljer ett objekt öppnas ett utfällbart objekt som länkar till uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-169">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="faf7e-170">Sidofältet</span><span class="sxs-lookup"><span data-stu-id="faf7e-170">Sidebar</span></span>

<span data-ttu-id="faf7e-171">Bredvid huvudinnehållsområdet på sidan Maskinprofil är sidofältet.</span><span class="sxs-lookup"><span data-stu-id="faf7e-171">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![Bild på fliken sidofält för Datorprofil](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="faf7e-173">Sidofältet ger viktig grundläggande information i små underavsnitt som kan växlas öppna eller stängda:</span><span class="sxs-lookup"><span data-stu-id="faf7e-173">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="faf7e-174">**Taggar** - Alla taggar som är associerade med enheten</span><span class="sxs-lookup"><span data-stu-id="faf7e-174">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="faf7e-175">**Säkerhetsinformation** - Öppna incidenter, aktiva varningar, exponeringsnivå och risknivå</span><span class="sxs-lookup"><span data-stu-id="faf7e-175">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="faf7e-176">**Enhetsinformation** - Domän-, OS-, tillgångsgrupp, hälsotillstånd, datakänslighet och IP-adresser</span><span class="sxs-lookup"><span data-stu-id="faf7e-176">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="faf7e-177">**Nätverksaktivitet** - Tidsstämplar för första gången och sista gången enheten sågs i nätverket</span><span class="sxs-lookup"><span data-stu-id="faf7e-177">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="faf7e-178">Det här avsnittet innehåller också enhetens namn och exponeringsnivå och en ikon som anger om den för närvarande är aktiv i nätverket.</span><span class="sxs-lookup"><span data-stu-id="faf7e-178">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="faf7e-179">Svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="faf7e-179">Response actions</span></span>

<span data-ttu-id="faf7e-180">Svarsåtgärder erbjuder ett snabbt sätt att försvara sig mot och analysera hot.</span><span class="sxs-lookup"><span data-stu-id="faf7e-180">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Bild på fliken sidofält för Datorprofil](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="faf7e-182">De svarsåtgärder som är tillgängliga för dig här inkluderar:</span><span class="sxs-lookup"><span data-stu-id="faf7e-182">The response actions available to you here include:</span></span>

* <span data-ttu-id="faf7e-183">**Hantera taggar** – Uppdaterar anpassade taggar som du har använt på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="faf7e-183">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="faf7e-184">**Isolera datorn** – isolerar datorn från organisationens nätverk samtidigt som den är ansluten till Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="faf7e-184">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="faf7e-185">Du kan välja att låta Outlook, Teams och Skype för företag köras medan maskinen är isolerad, i kommunikationssyfte.</span><span class="sxs-lookup"><span data-stu-id="faf7e-185">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="faf7e-186">**Begränsa appkörning** - Förhindrar att program som inte är signerade av Microsoft körs</span><span class="sxs-lookup"><span data-stu-id="faf7e-186">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="faf7e-187">**Kör antivirussökning** - Uppdaterar Windows Defender Antivirus definitioner och omedelbart kör en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="faf7e-187">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="faf7e-188">Välj mellan Snabbsökning eller Fullständig genomsökning.</span><span class="sxs-lookup"><span data-stu-id="faf7e-188">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="faf7e-189">**Samla in undersökningspaket** - Samlar in information om maskinen.</span><span class="sxs-lookup"><span data-stu-id="faf7e-189">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="faf7e-190">När undersökningen är klar kan du hämta den.</span><span class="sxs-lookup"><span data-stu-id="faf7e-190">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="faf7e-191">**Initiera livesvarssession** - Laddar ett fjärrskal på maskinen för [djupgående säkerhetsutredningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="faf7e-191">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="faf7e-192">**Initiera automatisk undersökning** - [Undersöker och åtgärdar automatiskt hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="faf7e-192">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="faf7e-193">Även om du manuellt kan utlösa automatiska undersökningar för att köras från den här sidan utlöser [vissa varningsprinciper](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) automatiska undersökningar på egen hand.</span><span class="sxs-lookup"><span data-stu-id="faf7e-193">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="faf7e-194">**Åtgärdscenter** - Visa status för inskickade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="faf7e-194">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="faf7e-195">Endast tillgänglig om en annan åtgärd redan har valts.</span><span class="sxs-lookup"><span data-stu-id="faf7e-195">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="faf7e-196">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="faf7e-196">Related topics</span></span>

* [<span data-ttu-id="faf7e-197">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="faf7e-197">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="faf7e-198">Aktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="faf7e-198">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="faf7e-199">Undersök entiteter på datorer med live-svar</span><span class="sxs-lookup"><span data-stu-id="faf7e-199">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="faf7e-200">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="faf7e-200">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
