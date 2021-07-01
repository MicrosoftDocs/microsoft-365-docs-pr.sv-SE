---
title: Enhetsprofil i Microsoft 365 säkerhetsportal
description: Visa risk- och exponeringsnivåer för en enhet i organisationen. Analysera tidigare och aktuella hot och skydda enheten med de senaste uppdateringarna.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, Microsoft 365 Defender, säkerhetscenter, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Defender för identitet, enhet, enhetsprofil, datorsida, datorprofil
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 47b25ba541264d79216748753e9f41fb7435fc10
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229485"
---
# <a name="device-profile-page"></a><span data-ttu-id="1d7a0-105">Profilsida för enhet</span><span class="sxs-lookup"><span data-stu-id="1d7a0-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d7a0-106">På Microsoft 365 säkerhetsportalen hittar du profilsidor för enheter, så att du snabbt kan bedöma status och status för enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d7a0-107">Sidan med enhetsprofilen kan se något annorlunda ut beroende på om enheten är registrerad i Microsoft Defender för Slutpunkt, Microsoft Defender för identitet eller båda.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="1d7a0-108">Om enheten är registrerad i Microsoft Defender för Endpoint kan du också använda sidan med enhetsprofilen för att utföra några vanliga säkerhetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="1d7a0-109">Navigera på enhetens profilsida</span><span class="sxs-lookup"><span data-stu-id="1d7a0-109">Navigating the device profile page</span></span>

<span data-ttu-id="1d7a0-110">Profilsidan är uppdelad i flera breda avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-110">The profile page is broken up into several broad sections.</span></span>

![Bild av enhetens profilsida med (1) tabbområde (2) sidofält och (3) åtgärder markerade i rött](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="1d7a0-112">I sidofältet (1) finns grundläggande information om enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="1d7a0-113">Huvudinnehållsområdet (2) innehåller flikar som du kan växla mellan för att visa olika typer av information om enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="1d7a0-114">Om enheten är registrerad i Microsoft Defender för Endpoint visas även en lista över svarsåtgärder (3).</span><span class="sxs-lookup"><span data-stu-id="1d7a0-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="1d7a0-115">Med svarsåtgärder kan du utföra vanliga säkerhetsrelaterade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="1d7a0-116">Sidofält</span><span class="sxs-lookup"><span data-stu-id="1d7a0-116">Sidebar</span></span>

<span data-ttu-id="1d7a0-117">Bredvid huvudinnehållsområdet på sidan med enhetsprofilen finns sidofältet.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Bild av fliken sidofält för enhetsprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="1d7a0-119">I sidofältet visas enhetens fullständiga namn och exponeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="1d7a0-120">Den innehåller även viktig grundläggande information i små avsnitt som kan vara öppna eller stängda, till exempel:</span><span class="sxs-lookup"><span data-stu-id="1d7a0-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="1d7a0-121">**Taggar** – Alla Microsoft Defender för Slutpunkt, Microsoft Defender för identitet eller anpassade taggar som är kopplade till enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="1d7a0-122">Taggar från Microsoft Defender för identitet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="1d7a0-123">**Säkerhetsinformation** – Öppna incidenter och aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="1d7a0-124">Enheter som är registrerade i Microsoft Defender för Endpoint visar också exponeringsnivå och risknivå.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="1d7a0-125">Exponeringsnivån relaterar till hur mycket enheten uppfyller säkerhetsrekommendationer, medan risknivån beräknas utifrån ett antal faktorer, inklusive typer och allvarlighetsgrad för aktiva varningar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="1d7a0-126">**Enhetsinformation** – domän, OS, tidsstämpel för när enheten först sågs, IP-adresser, resurser.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="1d7a0-127">Enheter som är registrerade i Microsoft Defender för Endpoint visar även hälsotillstånd.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="1d7a0-128">Enheter som är registrerade i Microsoft Defender för identitet visar SAM-namn och en tidsstämpel för när enheten skapades första gången.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="1d7a0-129">**Nätverksaktivitet** – Tidsstämplar för första och senaste gången enheten sågs i nätverket.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="1d7a0-130">**Katalogdata** (*endast för enheter som är registrerade i Microsoft Defender för* identitet) – [UAC-flaggor,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN:er](/windows/win32/ad/service-principal-names)och gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="1d7a0-131">Svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="1d7a0-131">Response actions</span></span>

<span data-ttu-id="1d7a0-132">Svarsåtgärder är ett snabbt sätt att försvara sig mot och analysera hot.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Bild av åtgärdsfältet för enhetsprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="1d7a0-134">[Svarsåtgärder](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) är bara tillgängliga om enheten är registrerad i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="1d7a0-135">Enheter som är registrerade i Microsoft Defender för Endpoint kan visa olika antal svarsåtgärder, baserat på enhetens operativsystem och versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="1d7a0-136">Åtgärder som är tillgängliga på sidan med enhetsprofilen är:</span><span class="sxs-lookup"><span data-stu-id="1d7a0-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="1d7a0-137">**Hantera taggar** – Uppdaterar anpassade taggar som du har tillämpat på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="1d7a0-138">**Identifiera enhet** – Isolerar enheten från organisationens nätverk samtidigt som den håller den ansluten till Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1d7a0-139">Du kan välja att Outlook, Teams och Skype för företag körs medan enheten är isolerad i kommunikationssyfte.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="1d7a0-140">**Åtgärdscenter** – visa status för skickade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="1d7a0-141">Endast tillgängligt om en annan åtgärd redan har markerats.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="1d7a0-142">**Begränsa programkörning** – Förhindrar att program som inte är signerade av Microsoft körs.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="1d7a0-143">**Kör antivirussökning** – uppdateringar Windows Defender Antivirus definitioner och kör genast en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="1d7a0-144">Välj mellan Snabbsökning eller Fullständig sökning.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="1d7a0-145">**Paket för insamling** av undersökning – samlar in information om enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="1d7a0-146">När undersökningen är klar kan du ladda ned den.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="1d7a0-147">**Initiera Live Response-session** – Läser in ett fjärrgränssnitt på enheten [för ingående säkerhetsundersökning.](/microsoft-365/security/defender-endpoint/live-response)</span><span class="sxs-lookup"><span data-stu-id="1d7a0-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="1d7a0-148">**Initiera automatisk undersökning** – [undersöker och åtgärdar automatiskt hot.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="1d7a0-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="1d7a0-149">Även om du manuellt kan utlösta automatiska undersökningar från den här sidan [utlöser](../../compliance/alert-policies.md#default-alert-policies) vissa aviseringsprinciper automatiska undersökningar på egen hand.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="1d7a0-150">**Åtgärdscenter** – Visar information om alla svarsåtgärder som körs för närvarande.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="1d7a0-151">Avsnittet Flikar</span><span class="sxs-lookup"><span data-stu-id="1d7a0-151">Tabs section</span></span>

<span data-ttu-id="1d7a0-152">Med flikarna för enhetsprofilen kan du växla mellan en översikt över säkerhetsinformation om enheten och tabeller som innehåller en lista med aviseringar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="1d7a0-153">Enheter som är registrerade i Microsoft Defender för Endpoint visar även flikar som innehåller en tidslinje, en lista med säkerhetsrekommendationer, en inventering av programvara, en lista över identifierade säkerhetsproblem och saknade KBs (säkerhetsuppdateringar).</span><span class="sxs-lookup"><span data-stu-id="1d7a0-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="1d7a0-154">Fliken Översikt</span><span class="sxs-lookup"><span data-stu-id="1d7a0-154">Overview tab</span></span>

<span data-ttu-id="1d7a0-155">Standardfliken är **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="1d7a0-155">The default tab is **Overview**.</span></span> <span data-ttu-id="1d7a0-156">Den ger en snabb översikt över den viktigaste säkerhets information om enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-156">It provides a quick look at the most important security fact about the device.</span></span>

![Bild av översiktsfliken för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="1d7a0-158">Här kan du snabbt se enhetens aktiva aviseringar och inloggade användare.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="1d7a0-159">Om enheten är registrerad i Microsoft Defender för Endpoint visas även enhetens risknivå och alla tillgängliga data om säkerhetsutvärderingar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="1d7a0-160">Säkerhetsutvärderingarna beskriver enhetens exponeringsnivå, ger säkerhetsrekommendationer och listar påverkade program samt upptäckta svagheter.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="1d7a0-161">Fliken Aviseringar</span><span class="sxs-lookup"><span data-stu-id="1d7a0-161">Alerts tab</span></span>

<span data-ttu-id="1d7a0-162">Fliken **Aviseringar** innehåller en lista med aviseringar som har höjts på enheten från både Microsoft Defender för identitet och Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Bild på fliken Aviseringar för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="1d7a0-164">Du kan anpassa antalet objekt som visas och vilka kolumner som visas för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="1d7a0-165">Standardbeteendet är att lista trettio objekt per sida.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="1d7a0-166">Kolumnerna på den här fliken innehåller information om allvarlighetsgraden för det hot som utlöste aviseringen, samt status, undersökningsstatus och vem aviseringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="1d7a0-167">Kolumnen *påverkade enheter* refererar till den enhet (entitet) vars profil du visar för närvarande, plus alla andra enheter i nätverket som påverkas.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="1d7a0-168">Om du väljer ett objekt i den här listan öppnas en utfällande meny som innehåller ännu mer information om den markerade aviseringen.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="1d7a0-169">Listan kan filtreras efter allvarlighetsgrad, status eller vem aviseringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="1d7a0-170">Fliken Tidslinje</span><span class="sxs-lookup"><span data-stu-id="1d7a0-170">Timeline tab</span></span>

<span data-ttu-id="1d7a0-171">Fliken **Tidslinje** innehåller ett interaktivt, kronologiskt diagram över alla händelser upphöjda på enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="1d7a0-172">Genom att flytta det markerade området i diagrammet åt vänster eller höger kan du visa händelser över olika tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="1d7a0-173">Du kan också välja ett anpassat datumintervall i den nedrullningsbara menyn mellan det interaktiva diagrammet och listan med händelser.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="1d7a0-174">Under diagrammet finns en lista med händelser för det valda datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Bild av fliken Tidslinje för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="1d7a0-176">Både antalet objekt som visas och kolumnerna i listan kan anpassas.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="1d7a0-177">I standardkolumnerna visas händelsetiden, aktiv användare, åtgärdstyp, enheter (processer) och ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="1d7a0-178">Om du väljer ett objekt i den här listan öppnas en utfällningslistebild som visar diagrammet Händelseenheter, som visar de överordnade och underordnade processerna som ingår i händelsen.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="1d7a0-179">Listan kan filtreras efter den specifika typen av händelse. Till exempel registerhändelser eller smartskärmshändelser.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="1d7a0-180">Listan kan också exporteras till en CSV-fil för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="1d7a0-181">Även om filen inte begränsas av antalet händelser är det maximala intervallet du kan välja att exportera sju dagar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="1d7a0-182">Fliken Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="1d7a0-182">Security recommendations tab</span></span>

<span data-ttu-id="1d7a0-183">Fliken **Säkerhetsrekommendationer** innehåller åtgärder du kan vidta för att skydda enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="1d7a0-184">Om du väljer ett objekt i den här listan öppnas en utfällad meny där du hittar anvisningar om hur du använder rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Bild av fliken säkerhetsrekommendationer för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="1d7a0-186">Precis som på föregående flikar går det att anpassa antalet objekt som visas per sida och vilka kolumner som är synliga.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="1d7a0-187">Standardvyn innehåller kolumner som beskriver säkerheten, det associerade hotet, den relaterade komponent eller programvara som påverkas av hotet och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="1d7a0-188">Objekt kan filtreras efter rekommendationens status.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="1d7a0-189">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="1d7a0-189">Software inventory</span></span>

<span data-ttu-id="1d7a0-190">På **fliken För inventering** av programvara visas programvara som är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Bild på fliken för programvaruinventering för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="1d7a0-192">I standardvyn visas programvaruleverantören, installerat versionsnummer, antal kända programvaruinsikter, hotinsikter, produktkod och taggar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="1d7a0-193">Antalet objekt som visas och vilka kolumner som visas kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="1d7a0-194">Om du väljer ett objekt från den här listan öppnas en utfällning med mer information om den valda programvaran samt sökväg och tidsstämpel för den senaste gången programvaran hittades.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="1d7a0-195">Den här listan kan filtreras efter produktkod.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="1d7a0-196">Flik för upptäckta säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="1d7a0-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="1d7a0-197">På **fliken Identifierade säkerhetsproblem** visas eventuella vanliga säkerhetsproblem och sårbarheter (CVEs) som kan påverka enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Bild av fliken för identifierade säkerhetsproblem för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="1d7a0-199">I standardvyn visas allvarlighetsgraden för CVE, Common Vulnerability Score (CVS), programvaran relaterad till CVE, när CVE publicerades, när CVE uppdaterades senast och hot kopplade till CVE.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="1d7a0-200">Precis som på föregående flikar kan du anpassa antalet objekt som visas och vilka kolumner som är synliga.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="1d7a0-201">Om du väljer ett objekt i den här listan öppnas en utfällning som beskriver CVE.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="1d7a0-202">Saknade KBs</span><span class="sxs-lookup"><span data-stu-id="1d7a0-202">Missing KBs</span></span>

<span data-ttu-id="1d7a0-203">På **fliken Saknade KB** visas alla Microsoft-uppdateringar som ännu inte har tillämpats på enheten.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="1d7a0-204">De "KBs" som är i fråga [är Knowledge Base-artiklar](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) som beskriver dessa uppdateringar. till exempel [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="1d7a0-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Bild på fliken kbs som saknas för enhetsprofilen](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="1d7a0-206">I standardvyn visas anslagsbulletin som innehåller uppdateringarna, OS-versionen, berörda produkter, cv:er som är adresserade, KB-nummer och taggar.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="1d7a0-207">Antalet objekt som visas per sida och vilka kolumner som visas kan anpassas.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="1d7a0-208">Om du markerar ett objekt öppnas en utfällblad som länkar till uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="1d7a0-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d7a0-209">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1d7a0-209">Related topics</span></span>

* [<span data-ttu-id="1d7a0-210">Microsoft 365 Defender översikt</span><span class="sxs-lookup"><span data-stu-id="1d7a0-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="1d7a0-211">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d7a0-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="1d7a0-212">Undersök enheter på enheter med hjälp av live-svar</span><span class="sxs-lookup"><span data-stu-id="1d7a0-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="1d7a0-213">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="1d7a0-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
