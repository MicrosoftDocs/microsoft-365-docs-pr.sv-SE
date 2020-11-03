---
title: Enhets profil i säkerhets portalen för Microsoft 365
description: Visa risk-och exponerings nivåer för en enhet i organisationen. Analysera och presentera hot och skydda enheten med de senaste uppdateringarna.
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, Microsoft Threat Protection, MTP, säkerhets Center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Device-sida, enhets profil, dator sida, dator profil
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
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843858"
---
# <a name="device-profile-page"></a><span data-ttu-id="e3007-105">Sidan enhets profil</span><span class="sxs-lookup"><span data-stu-id="e3007-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3007-106">Med Microsoft 365-säkerhetsportalen får du en enhets profil sida så att du snabbt kan bedöma hälsa och status för enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="e3007-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3007-107">Enhets profil sidan kan verka lite annorlunda, beroende på om enheten är registrerad i Microsoft Defender för slut punkt, Microsoft Defender för identitet eller både och.</span><span class="sxs-lookup"><span data-stu-id="e3007-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="e3007-108">Om enheten är registrerad i Microsoft Defender för slut punkten kan du också använda sidan enhets profil för att utföra vanliga säkerhets uppgifter.</span><span class="sxs-lookup"><span data-stu-id="e3007-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="e3007-109">Gå till sidan enhets profil</span><span class="sxs-lookup"><span data-stu-id="e3007-109">Navigating the device profile page</span></span>

<span data-ttu-id="e3007-110">Profil sidan är uppdelad i flera breda avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e3007-110">The profile page is broken up into several broad sections.</span></span>

![Bild av sidan enhets profil med (1) flik (2) marginal list och (3) åtgärder markerade i rött](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="e3007-112">Marginal listen (1) visar grundläggande information om enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="e3007-113">Huvud innehålls området (2) innehåller flikar som du kan växla mellan för att visa olika typer av information om enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="e3007-114">Om enheten är registrerad i Microsoft Defender för slut punkt visas även en lista med svars åtgärder (3).</span><span class="sxs-lookup"><span data-stu-id="e3007-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="e3007-115">Med svars åtgärder kan du utföra vanliga säkerhetsrelaterade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="e3007-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="e3007-116">Sido fältet</span><span class="sxs-lookup"><span data-stu-id="e3007-116">Sidebar</span></span>

<span data-ttu-id="e3007-117">Bredvid huvud innehålls området på sidan enhets profil visas marginal listen.</span><span class="sxs-lookup"><span data-stu-id="e3007-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Bild av fliken sidofält för enhets profil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="e3007-119">I list rutan visas enhetens fullständiga namn och exponerings nivå.</span><span class="sxs-lookup"><span data-stu-id="e3007-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="e3007-120">Den innehåller också viktig grundläggande information i små underavsnitt som kan växlas öppen eller stängd, till exempel:</span><span class="sxs-lookup"><span data-stu-id="e3007-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="e3007-121">**Taggar** – alla Microsoft Defender för slut punkter, Microsoft Defender för identiteter och anpassade taggar som är associerade med enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="e3007-122">Taggar från Microsoft Defender för identitet är inte redigerbara.</span><span class="sxs-lookup"><span data-stu-id="e3007-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="e3007-123">**Säkerhets information** – öppna incidenter och aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="e3007-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="e3007-124">Enheter som är registrerade i Microsoft Defender för slut punkter visar även exponerings nivå och risk nivå.</span><span class="sxs-lookup"><span data-stu-id="e3007-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="e3007-125">Exponerings nivå handlar om hur mycket enheten uppfyller säkerhets rekommendationerna, samtidigt som risk nivån beräknas baserat på ett antal faktorer, bland annat typer och allvarlighets grad för aktiva varningar.</span><span class="sxs-lookup"><span data-stu-id="e3007-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="e3007-126">**Enhets uppgifter** – domän, OS, tidsstämpel för när enheten först visades, IP-adresser, resurser.</span><span class="sxs-lookup"><span data-stu-id="e3007-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="e3007-127">Enheter som är registrerade i Microsoft Defender för slut punkter visar också hälso tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e3007-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="e3007-128">Enheter som är registrerade i Microsoft Defender för identitet visar SAM-namn och en tidstämpel för när enheten först skapades.</span><span class="sxs-lookup"><span data-stu-id="e3007-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="e3007-129">**Nätverks aktivitet** -tidsstämplar för första gången och när enheten senast visades i nätverket.</span><span class="sxs-lookup"><span data-stu-id="e3007-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="e3007-130">**Katalog data** ( *endast för enheter som är registrerade i Microsoft Defender för identitet* )- [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) -flaggor, [SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)och grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="e3007-130">**Directory data** ( *only for devices enrolled in Microsoft Defender for Identity* ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="e3007-131">Svars åtgärder</span><span class="sxs-lookup"><span data-stu-id="e3007-131">Response actions</span></span>

<span data-ttu-id="e3007-132">Svars åtgärder är ett snabbt sätt att försvara sig mot och analysera hot.</span><span class="sxs-lookup"><span data-stu-id="e3007-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Bild av åtgärds fältet för enhets profil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="e3007-134">[Svars åtgärder](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) är bara tillgängliga om enheten är registrerad i Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="e3007-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="e3007-135">Enheter som är registrerade i Microsoft Defender för slut punkter kan visa olika antal svars åtgärder baserat på enhetens operativ system och versions nummer.</span><span class="sxs-lookup"><span data-stu-id="e3007-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="e3007-136">Tillgängliga åtgärder på enhets profil sidan är bland annat:</span><span class="sxs-lookup"><span data-stu-id="e3007-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="e3007-137">**Hantera Taggar** – uppdaterar anpassade taggar som du har använt på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="e3007-138">**Isolera enhet** -isolerar enheten från organisationens nätverk samtidigt som den hålls ansluten till Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="e3007-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e3007-139">Du kan välja att tillåta att Outlook, teams och Skype för företag körs medan enheten är isolerad, i syfte att kommunicera.</span><span class="sxs-lookup"><span data-stu-id="e3007-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="e3007-140">**Åtgärds Center** – Visa statusen för skickade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e3007-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="e3007-141">Endast tillgängligt om en annan åtgärd redan har valts.</span><span class="sxs-lookup"><span data-stu-id="e3007-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="e3007-142">**Begränsa program körning** -förhindrar att program som inte är signerade av Microsoft körs.</span><span class="sxs-lookup"><span data-stu-id="e3007-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="e3007-143">**Kör antivirus genomsökning** -uppdatera definitioner för Windows Defender Antivirus och kör en virus genomsökning omedelbart.</span><span class="sxs-lookup"><span data-stu-id="e3007-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="e3007-144">Välj mellan snabb sökning eller fullständig sökning.</span><span class="sxs-lookup"><span data-stu-id="e3007-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="e3007-145">**Samla in undersöknings paket** – samlar in information om enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="e3007-146">När undersökningen är klar kan du ladda ned den.</span><span class="sxs-lookup"><span data-stu-id="e3007-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="e3007-147">**Starta Live-svarsomgången** -laddar ett fjärrgränssnitt på enheten för [djupgående säkerhets undersökningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="e3007-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="e3007-148">**Starta automatisk undersökning** – [undersöker och reparerar hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e3007-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="e3007-149">Även om du manuellt kan utlösa automatiska utredningar att köra från den här sidan, Utlös [vissa notifieringsregler](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) automatiska utredningar.</span><span class="sxs-lookup"><span data-stu-id="e3007-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="e3007-150">**Åtgärds Center** – visar information om alla svars åtgärder som körs för närvarande.</span><span class="sxs-lookup"><span data-stu-id="e3007-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="e3007-151">Avsnittet flikar</span><span class="sxs-lookup"><span data-stu-id="e3007-151">Tabs section</span></span>

<span data-ttu-id="e3007-152">Med flikarna för enhets profil kan du växla via en översikt över säkerhets information om enheten och tabeller som innehåller en lista med aviseringar.</span><span class="sxs-lookup"><span data-stu-id="e3007-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="e3007-153">Enheter som är registrerade i Microsoft Defender för slut punkter visar även flikar som innehåller en tids linje, en lista över säkerhets rekommendationer, en program inventering, en lista över upptäckta säkerhets problem och saknade KBs (säkerhets uppdateringar).</span><span class="sxs-lookup"><span data-stu-id="e3007-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="e3007-154">Fliken Översikt</span><span class="sxs-lookup"><span data-stu-id="e3007-154">Overview tab</span></span>

<span data-ttu-id="e3007-155">Standard-fliken är **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="e3007-155">The default tab is **Overview**.</span></span> <span data-ttu-id="e3007-156">Det ger en snabb överblick över de viktigaste säkerhets faktumet på enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-156">It provides a quick look at the most important security fact about the device.</span></span>

![Bild av fliken Översikt för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="e3007-158">Här kan du få en snabb överblick över enhetens aktiva aviseringar och alla användare som är inloggade.</span><span class="sxs-lookup"><span data-stu-id="e3007-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="e3007-159">Om enheten är registrerad i Microsoft Defender för slut punkten kan du även se enhetens risk nivå och alla tillgängliga data om säkerhets utvärderingar.</span><span class="sxs-lookup"><span data-stu-id="e3007-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="e3007-160">Säkerhets utvärderingarna beskriver enhetens exponerings nivå, tillhandahåller säkerhets rekommendationer och visar en lista över program vara och upptäckta säkerhets problem.</span><span class="sxs-lookup"><span data-stu-id="e3007-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="e3007-161">Fliken aviseringar</span><span class="sxs-lookup"><span data-stu-id="e3007-161">Alerts tab</span></span>

<span data-ttu-id="e3007-162">Fliken **aviseringar** innehåller en lista med aviseringar som har upphöjts till enheten från både Microsoft Defender för identitet och Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="e3007-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Bild av fliken aviseringar för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="e3007-164">Du kan anpassa hur många objekt som visas och vilka kolumner som ska visas för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="e3007-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="e3007-165">Standardinställningen är att lista halv objekt per sida.</span><span class="sxs-lookup"><span data-stu-id="e3007-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="e3007-166">Kolumnerna på den här fliken innehåller information om hur allvarligt hotet som utlöste aviseringen, samt status, undersöknings status och vem som har tilldelats notifieringen.</span><span class="sxs-lookup"><span data-stu-id="e3007-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="e3007-167">Kolumnen *påverkade entiteter* refererar till den enhet (entitet) vars profil du för tillfället visar, samt eventuella andra enheter i nätverket som påverkas.</span><span class="sxs-lookup"><span data-stu-id="e3007-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="e3007-168">Om du väljer ett objekt från listan öppnas en utfällbar lista med mer information om den valda aviseringen.</span><span class="sxs-lookup"><span data-stu-id="e3007-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="e3007-169">Den här listan kan filtreras efter allvarlighets grad, status eller vem notifieringen har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="e3007-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="e3007-170">Fliken tids linje</span><span class="sxs-lookup"><span data-stu-id="e3007-170">Timeline tab</span></span>

<span data-ttu-id="e3007-171">Fliken **tids linje** innehåller ett interaktivt, kronologiskt diagram över alla händelser som är aktiverade på enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="e3007-172">Genom att flytta det markerade området i diagrammet åt vänster eller höger kan du Visa händelser under olika tids perioder.</span><span class="sxs-lookup"><span data-stu-id="e3007-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="e3007-173">Du kan också välja ett eget datum intervall i den nedrullningsbara menyn mellan det interaktiva diagrammet och listan med händelser.</span><span class="sxs-lookup"><span data-stu-id="e3007-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="e3007-174">Under diagrammet finns en lista över händelser för det markerade datum intervallet.</span><span class="sxs-lookup"><span data-stu-id="e3007-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Bild av fliken tids linje för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="e3007-176">Antalet objekt som visas och kolumnerna i listan kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="e3007-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="e3007-177">I standard kolumnerna listas händelse tid, aktiv användare, åtgärds typ, enheter (processer) och ytterligare information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3007-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="e3007-178">Om du väljer ett objekt från den här listan öppnas en utfällbar diagram som visar de överordnade och underordnade processerna i händelsen.</span><span class="sxs-lookup"><span data-stu-id="e3007-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="e3007-179">Listan kan filtreras efter den speciella typen av händelse; till exempel register händelser eller händelser för smart skärm.</span><span class="sxs-lookup"><span data-stu-id="e3007-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="e3007-180">Listan kan också exporteras till en CSV-fil för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="e3007-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="e3007-181">Även om filen inte begränsas av antalet händelser är det maximala tidsintervallet du kan välja att exportera sju dagar.</span><span class="sxs-lookup"><span data-stu-id="e3007-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="e3007-182">Fliken säkerhets rekommendationer</span><span class="sxs-lookup"><span data-stu-id="e3007-182">Security recommendations tab</span></span>

<span data-ttu-id="e3007-183">På fliken **säkerhets rekommendationer** visas de åtgärder du kan vidta för att skydda enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="e3007-184">Om du markerar ett objekt i den här listan öppnas en utfällbar lista där du kan få anvisningar om hur du använder rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="e3007-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Bild av fliken säkerhets rekommendationer för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="e3007-186">Precis som med föregående flikar kan du anpassa antalet objekt som visas per sida samt vilka kolumner som ska visas.</span><span class="sxs-lookup"><span data-stu-id="e3007-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="e3007-187">Standardvyn innehåller kolumner med information om säkerhets svagheter, tillhör ande hot, den relaterade komponenten eller program varan som påverkas av hotet och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="e3007-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="e3007-188">Objekt kan filtreras enligt rekommendationens status.</span><span class="sxs-lookup"><span data-stu-id="e3007-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="e3007-189">Program varu inventering</span><span class="sxs-lookup"><span data-stu-id="e3007-189">Software inventory</span></span>

<span data-ttu-id="e3007-190">På fliken **program varu inventering** visas program vara installerat på enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Bild av fliken program varu inventering för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="e3007-192">I standardvyn visas program varu leverantören, det installerade versions numret, antalet kända program svagheter, Hot insikter, produkt kod och taggar.</span><span class="sxs-lookup"><span data-stu-id="e3007-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="e3007-193">Antalet objekt som visas och vilka kolumner som visas kan båda anpassas.</span><span class="sxs-lookup"><span data-stu-id="e3007-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="e3007-194">Om du väljer ett objekt från den här listan öppnas en utfällbar lista med mer information om den valda program varan samt sökväg och tidsstämpel för den senaste gången program varan hittades.</span><span class="sxs-lookup"><span data-stu-id="e3007-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="e3007-195">Den här listan kan filtreras efter produkt kod.</span><span class="sxs-lookup"><span data-stu-id="e3007-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="e3007-196">Fliken upptäckta säkerhets problem</span><span class="sxs-lookup"><span data-stu-id="e3007-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="e3007-197">Fliken **upptäckta säkerhets problem** visar eventuella vanliga säkerhets problem och utnyttjanden (CVEs) som kan påverka enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Bild av fliken upptäckta säkerhets problem för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="e3007-199">I standardvyn visas allvarlighets graden för CVE, det vanligaste säkerhets problemet (CVS), program varan som är relaterad till CVE, när CVE publicerades, när CVE senast uppdaterades och hot kopplade till CVE.</span><span class="sxs-lookup"><span data-stu-id="e3007-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="e3007-200">Precis som med föregående flikar kan du anpassa antalet objekt som visas och vilka kolumner som ska visas.</span><span class="sxs-lookup"><span data-stu-id="e3007-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="e3007-201">Om du väljer ett objekt i den här listan öppnas en utfällare som beskriver CVE.</span><span class="sxs-lookup"><span data-stu-id="e3007-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="e3007-202">KBs saknas</span><span class="sxs-lookup"><span data-stu-id="e3007-202">Missing KBs</span></span>

<span data-ttu-id="e3007-203">I den **saknade KBS** -fliken visas alla uppdateringar som ännu inte har installerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="e3007-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="e3007-204">"KBs" i fråga är [kunskaps bas artiklar](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) som beskriver dessa uppdateringar. till exempel [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="e3007-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Bild av fliken KBS saknas för enhets profil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="e3007-206">I standardvyn visas den bulletin som innehåller uppdateringarna, OS-versionen, de produkter som påverkas, CVEs adresser, KB-nummer och taggar.</span><span class="sxs-lookup"><span data-stu-id="e3007-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="e3007-207">Antalet objekt som visas per sida och vilka kolumner som visas kan anpassas.</span><span class="sxs-lookup"><span data-stu-id="e3007-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="e3007-208">Om du markerar ett objekt öppnas en utfällbar länk till uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="e3007-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3007-209">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e3007-209">Related topics</span></span>

* [<span data-ttu-id="e3007-210">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3007-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="e3007-211">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3007-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="e3007-212">Undersök enheter på enheter, med Live Response</span><span class="sxs-lookup"><span data-stu-id="e3007-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="e3007-213">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="e3007-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
