---
title: Enhetsprofil i Microsoft 365-säkerhetsportalen
description: Visa risk- och exponeringsnivåer för en enhet i organisationen. Analysera tidigare och nuvarande hot och skydda enheten med de senaste uppdateringarna.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, Microsoft Threat Protection, MTP, security center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, enhetssida, enhetsprofil, maskinsida, maskinprofil
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
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517072"
---
# <a name="device-profile-page"></a><span data-ttu-id="746ff-105">Sidan Enhetsprofil</span><span class="sxs-lookup"><span data-stu-id="746ff-105">Device profile page</span></span>

<span data-ttu-id="746ff-106">Microsoft 365-säkerhetsportalen ger dig enhetsprofilsidor, så att du snabbt kan bedöma hälsotillståndet och statusen för enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="746ff-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="746ff-107">Enhetsprofilsidan kan se lite annorlunda ut, beroende på om enheten är registrerad i Microsoft Defender ATP, Azure ATP eller båda.</span><span class="sxs-lookup"><span data-stu-id="746ff-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="746ff-108">Om enheten är registrerad i Microsoft Defender ATP kan du också använda enhetsprofilsidan för att utföra några vanliga säkerhetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="746ff-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="746ff-109">Navigera på enhetsprofilsidan</span><span class="sxs-lookup"><span data-stu-id="746ff-109">Navigating the device profile page</span></span>

<span data-ttu-id="746ff-110">Profilsidan är uppdelad i flera breda avsnitt.</span><span class="sxs-lookup"><span data-stu-id="746ff-110">The profile page is broken up into several broad sections.</span></span>

![Bild av enhetsprofilsida med (1) Tabbområde (2) Sidofält och (3) Åtgärder markerade i rött](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="746ff-112">Sidofältet (1) listar grundläggande detaljer om enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="746ff-113">Huvudinnehållsområdet (2) innehåller flikar som du kan växla igenom för att visa olika typer av information om enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="746ff-114">Om enheten är registrerad i Microsoft Defender ATP visas också en lista över svarsåtgärder (3).</span><span class="sxs-lookup"><span data-stu-id="746ff-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="746ff-115">Med svarsåtgärder kan du utföra vanliga säkerhetsrelaterade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="746ff-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="746ff-116">Sidofältet</span><span class="sxs-lookup"><span data-stu-id="746ff-116">Sidebar</span></span>

<span data-ttu-id="746ff-117">Bredvid huvudinnehållsområdet på enhetens profilsida finns sidofältet.</span><span class="sxs-lookup"><span data-stu-id="746ff-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Bild på fliken sidofält för enhetsprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="746ff-119">Sidofältet listar enhetens fullständiga namn och exponeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="746ff-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="746ff-120">Det ger också några viktiga grundläggande information i små underavsnitt som kan växlas öppna eller stängda, till exempel:</span><span class="sxs-lookup"><span data-stu-id="746ff-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="746ff-121">**Taggar** – Alla Microsoft Defender ATP-, Azure ATP- eller anpassade taggar som är associerade med enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="746ff-122">Taggar från Azure ATP kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="746ff-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="746ff-123">**Säkerhetsinformation** - Öppna incidenter och aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="746ff-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="746ff-124">Enheter som är registrerade i Microsoft Defender ATP visar också exponeringsnivå och risknivå.</span><span class="sxs-lookup"><span data-stu-id="746ff-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="746ff-125">Exponeringsnivån relaterar till hur mycket enheten följer säkerhetsrekommendationer, medan risknivån beräknas baserat på ett antal faktorer, inklusive typer och allvarlighetsgrad för aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="746ff-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="746ff-126">**Enhetsinformation** - Domän, OS, tidsstämpel för när enheten först sågs, IP-adresser, resurser.</span><span class="sxs-lookup"><span data-stu-id="746ff-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="746ff-127">Enheter som är registrerade i Microsoft Defender ATP visar också hälsotillstånd.</span><span class="sxs-lookup"><span data-stu-id="746ff-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="746ff-128">Enheter som registrerats i Azure ATP visar SAM-namn och en tidsstämpel för när enheten först skapades.</span><span class="sxs-lookup"><span data-stu-id="746ff-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="746ff-129">**Nätverksaktivitet** - Tidsstämplar för första gången och sista gången enheten sågs i nätverket.</span><span class="sxs-lookup"><span data-stu-id="746ff-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="746ff-130">**Katalogdata** (*endast för enheter som är registrerade i Azure ATP*) - [UAC-flaggor,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)och gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="746ff-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="746ff-131">Svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="746ff-131">Response actions</span></span>

<span data-ttu-id="746ff-132">Svarsåtgärder erbjuder ett snabbt sätt att försvara sig mot och analysera hot.</span><span class="sxs-lookup"><span data-stu-id="746ff-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Bild av åtgärdsfältet för enhetsprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="746ff-134">[Svarsåtgärder](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) är endast tillgängliga om enheten är registrerad i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="746ff-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="746ff-135">Enheter som är registrerade i Microsoft Defender ATP kan visa olika antal svarsåtgärder, baserat på enhetens operativsystem och versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="746ff-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="746ff-136">Åtgärder som är tillgängliga på enhetens profilsida är:</span><span class="sxs-lookup"><span data-stu-id="746ff-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="746ff-137">**Hantera taggar** – Uppdaterar anpassade taggar som du har använt på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="746ff-138">**Isolera enheten** – isolerar enheten från organisationens nätverk samtidigt som den är ansluten till Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="746ff-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="746ff-139">Du kan välja att låta Outlook, Teams och Skype för företag köras medan enheten är isolerad, i kommunikationssyfte.</span><span class="sxs-lookup"><span data-stu-id="746ff-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="746ff-140">**Åtgärdscenter** - Visa status för inskickade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="746ff-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="746ff-141">Endast tillgänglig om en annan åtgärd redan har valts.</span><span class="sxs-lookup"><span data-stu-id="746ff-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="746ff-142">**Begränsa appkörning** - Förhindrar att program som inte är signerade av Microsoft körs.</span><span class="sxs-lookup"><span data-stu-id="746ff-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="746ff-143">**Kör antivirussökning** - Uppdaterar Windows Defender Antivirus definitioner och omedelbart kör en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="746ff-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="746ff-144">Välj mellan Snabbsökning eller Fullständig genomsökning.</span><span class="sxs-lookup"><span data-stu-id="746ff-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="746ff-145">**Samla in undersökningspaket** - Samlar in information om enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="746ff-146">När undersökningen är klar kan du hämta den.</span><span class="sxs-lookup"><span data-stu-id="746ff-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="746ff-147">**Initiera live-svarssession** - Laddar ett fjärrskal på enheten för [djupgående säkerhetsutredningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="746ff-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="746ff-148">**Initiera automatisk undersökning** - [Undersöker och åtgärdar automatiskt hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="746ff-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="746ff-149">Även om du manuellt kan utlösa automatiska undersökningar för att köras från den här sidan utlöser [vissa varningsprinciper](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) automatiska undersökningar på egen hand.</span><span class="sxs-lookup"><span data-stu-id="746ff-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="746ff-150">**Åtgärdscenter** - Visar information om eventuella svarsåtgärder som körs för tillfället.</span><span class="sxs-lookup"><span data-stu-id="746ff-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="746ff-151">Avsnittet Flikar</span><span class="sxs-lookup"><span data-stu-id="746ff-151">Tabs section</span></span>

<span data-ttu-id="746ff-152">Med enhetsprofilflikarna kan du växla igenom en översikt över säkerhetsinformation om enheten och tabeller som innehåller en lista med aviseringar.</span><span class="sxs-lookup"><span data-stu-id="746ff-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="746ff-153">Enheter som är registrerade i Microsoft Defender ATP visar också flikar som har en tidslinje, en lista över säkerhetsrekommendationer, en programvaruinventering, en lista över upptäckta säkerhetsproblem och saknade KBs (säkerhetsuppdateringar).</span><span class="sxs-lookup"><span data-stu-id="746ff-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="746ff-154">Fliken Översikt</span><span class="sxs-lookup"><span data-stu-id="746ff-154">Overview tab</span></span>

<span data-ttu-id="746ff-155">Standardfliken är **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="746ff-155">The default tab is **Overview**.</span></span> <span data-ttu-id="746ff-156">Det ger en snabb titt på det viktigaste säkerhetsfaktat om enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-156">It provides a quick look at the most important security fact about the device.</span></span>

![Bild av översiktsfliken för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="746ff-158">Här kan du få en snabb titt på enhetens aktiva aviseringar och alla som för närvarande är inloggade på användare.</span><span class="sxs-lookup"><span data-stu-id="746ff-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="746ff-159">Om enheten är registrerad i Microsoft Defender ATP ser du även enhetens risknivå och alla tillgängliga data om säkerhetsbedömningar.</span><span class="sxs-lookup"><span data-stu-id="746ff-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="746ff-160">Säkerhetsbedömningarna beskriver enhetens exponeringsnivå, ger säkerhetsrekommendationer och listar programvara som påverkas och upptäcker sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="746ff-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="746ff-161">Fliken Aviseringar</span><span class="sxs-lookup"><span data-stu-id="746ff-161">Alerts tab</span></span>

<span data-ttu-id="746ff-162">Fliken **Aviseringar** innehåller en lista över aviseringar som har höjts på enheten, från både Azure ATP och Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="746ff-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![Bild på fliken aviseringar för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="746ff-164">Du kan anpassa antalet objekt som visas, samt vilka kolumner som visas för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="746ff-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="746ff-165">Standardbeteendet är att lista trettio objekt per sida.</span><span class="sxs-lookup"><span data-stu-id="746ff-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="746ff-166">Kolumnerna på den här fliken innehåller information om allvarlighetsgraden för det hot som utlöste aviseringen, samt status, undersökningstillstånd och vem aviseringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="746ff-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="746ff-167">Kolumnen *påverkade entiteter* refererar till den enhet (entitet) vars profil du för närvarande visar, plus alla andra enheter i nätverket som påverkas.</span><span class="sxs-lookup"><span data-stu-id="746ff-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="746ff-168">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt som innehåller ännu mer information om den valda aviseringen.</span><span class="sxs-lookup"><span data-stu-id="746ff-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="746ff-169">Den här listan kan filtreras efter allvarlighetsgrad, status eller vem aviseringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="746ff-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="746ff-170">Fliken Tidslinje</span><span class="sxs-lookup"><span data-stu-id="746ff-170">Timeline tab</span></span>

<span data-ttu-id="746ff-171">Fliken **Tidslinje** innehåller ett interaktivt, kronologiskt diagram över alla händelser som utlöses på enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="746ff-172">Genom att flytta det markerade området i diagrammet åt vänster eller höger kan du visa händelser över olika tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="746ff-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="746ff-173">Du kan också välja ett anpassat datumintervall från rullgardinsmenyn mellan det interaktiva diagrammet och listan över händelser.</span><span class="sxs-lookup"><span data-stu-id="746ff-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="746ff-174">Nedanför diagrammet finns en lista över händelser för det valda datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="746ff-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Bild på fliken tidslinje för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="746ff-176">Antalet objekt som visas och kolumnerna i listan kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="746ff-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="746ff-177">Standardkolumnerna listar händelsetid, aktiv användare, åtgärdstyp, entiteter (processer) och ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="746ff-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="746ff-178">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt som visar ett diagram över en entiteter för händelser som visar de överordnade och underordnade processer som är involverade i händelsen.</span><span class="sxs-lookup"><span data-stu-id="746ff-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="746ff-179">Listan kan filtreras efter den specifika typen av händelse. till exempel registerhändelser eller smartskärmshändelser.</span><span class="sxs-lookup"><span data-stu-id="746ff-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="746ff-180">Listan kan också exporteras till en CSV-fil, för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="746ff-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="746ff-181">Även om filen inte begränsas av antalet händelser, är det maximala tidsintervallet du kan välja att exportera sju dagar.</span><span class="sxs-lookup"><span data-stu-id="746ff-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="746ff-182">Fliken Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="746ff-182">Security recommendations tab</span></span>

<span data-ttu-id="746ff-183">På fliken **Säkerhetsrekommendationer** visas åtgärder som du kan vidta för att skydda enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="746ff-184">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt där du kan få instruktioner om hur du tillämpar rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="746ff-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Bild på fliken säkerhetsrekommendationer för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="746ff-186">Precis som med föregående flikar kan antalet objekt som visas per sida, samt vilka kolumner som är synliga, anpassas.</span><span class="sxs-lookup"><span data-stu-id="746ff-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="746ff-187">Standardvyn innehåller kolumner som beskriver de säkerhetsbrister som åtgärdats, det associerade hotet, den relaterade komponenten eller programvaran som påverkas av hotet med mera.</span><span class="sxs-lookup"><span data-stu-id="746ff-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="746ff-188">Artiklar kan filtreras efter rekommendationens status.</span><span class="sxs-lookup"><span data-stu-id="746ff-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="746ff-189">Inventering av programvara</span><span class="sxs-lookup"><span data-stu-id="746ff-189">Software inventory</span></span>

<span data-ttu-id="746ff-190">På fliken **Programvaruinventering** visas programvara som är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Bild av fliken inventering av programvara för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="746ff-192">Standardvyn visar programvaruleverantören, installerat versionsnummer, antal kända programvarubrister, hotinsikter, produktkod och taggar.</span><span class="sxs-lookup"><span data-stu-id="746ff-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="746ff-193">Antalet objekt som visas och vilka kolumner som visas kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="746ff-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="746ff-194">Om du väljer ett objekt från den här listan öppnas ett utfällbart objekt som innehåller mer information om den valda programvaran, samt sökvägen och tidsstämpeln för den senaste gången programvaran hittades.</span><span class="sxs-lookup"><span data-stu-id="746ff-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="746ff-195">Den här listan kan filtreras efter produktkod.</span><span class="sxs-lookup"><span data-stu-id="746ff-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="746ff-196">Fliken Upptäckta säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="746ff-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="746ff-197">På fliken **Identifierade säkerhetsproblem** visas alla vanliga sårbarheter och Ã¤r Ã¤nder (CVE) som kan påverka enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Bild av fliken upptäckta säkerhetsproblem för enhetsprofilen](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="746ff-199">Standardvyn visar allvarlighetsgraden för CVE, CVS (Common Vulnerability Score), programvaran som är relaterad till CVE, när CVE publicerades, när CVE senast uppdaterades och hot som är associerade med CVE.</span><span class="sxs-lookup"><span data-stu-id="746ff-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="746ff-200">Precis som med föregående flikar kan antalet objekt som visas och vilka kolumner som är synliga anpassas.</span><span class="sxs-lookup"><span data-stu-id="746ff-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="746ff-201">Om du väljer ett objekt i den här listan öppnas ett utfällbart objekt som beskriver CVE.</span><span class="sxs-lookup"><span data-stu-id="746ff-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="746ff-202">KBs saknas</span><span class="sxs-lookup"><span data-stu-id="746ff-202">Missing KBs</span></span>

<span data-ttu-id="746ff-203">På fliken **Saknade KBs** visas alla Microsoft-uppdateringar som ännu inte har tillämpats på enheten.</span><span class="sxs-lookup"><span data-stu-id="746ff-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="746ff-204">De "KBs" i fråga är [Knowledge Base artiklar](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) som beskriver dessa uppdateringar; till exempel [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="746ff-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Bild på fliken saknade kbs för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="746ff-206">Standardvyn visar bulletinen som innehåller uppdateringar, OS-version, berörda produkter, CVEs-adresserade, KB-numret och taggarna.</span><span class="sxs-lookup"><span data-stu-id="746ff-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="746ff-207">Antalet objekt som visas per sida och vilka kolumner som visas kan anpassas.</span><span class="sxs-lookup"><span data-stu-id="746ff-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="746ff-208">Om du väljer ett objekt öppnas ett utfällbart objekt som länkar till uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="746ff-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="746ff-209">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="746ff-209">Related topics</span></span>

* [<span data-ttu-id="746ff-210">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="746ff-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="746ff-211">Aktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="746ff-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="746ff-212">Undersöka entiteter på enheter med hjälp av live-svar</span><span class="sxs-lookup"><span data-stu-id="746ff-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="746ff-213">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="746ff-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
