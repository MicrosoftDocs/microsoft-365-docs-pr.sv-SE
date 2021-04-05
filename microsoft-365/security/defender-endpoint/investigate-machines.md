---
title: Undersök enheter i listan Defender för slutpunktsenheter
description: Undersök berörda enheter genom att granska aviseringar, nätverksanslutningsinformation, lägga till enhetstaggar och grupper och kontrollera tjänstens hälsa.
keywords: enheter, taggar, grupper, slutpunkt, aviseringar, kö, aviseringar, enhetsnamn, domän, senast sedd, intern IP, aktiva aviseringar, hotkategori, filtrera, sortera, granska aviseringar, nätverk, anslutning, typ, lösenords stjäla, utpressningstrojaner, sårbarhet, hot, låg allvarlighetsgrad, tjänstens hälsa
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 154ecd66399b031ef2e60eef16227bb9bc2f8785
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587725"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="e0875-104">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="e0875-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e0875-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e0875-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0875-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e0875-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0875-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0875-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e0875-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e0875-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0875-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e0875-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="e0875-110">Undersök informationen om en avisering som upphöjts på en specifik enhet för att identifiera andra beteenden eller händelser som kan vara relaterade till aviseringen eller den möjliga omfattningen av intrånget.</span><span class="sxs-lookup"><span data-stu-id="e0875-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="e0875-111">Som en del av undersökningen eller svarsprocessen kan du samla in ett undersökningspaket från en enhet.</span><span class="sxs-lookup"><span data-stu-id="e0875-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="e0875-112">Gör så här: Samla [in undersökningspaket från enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="e0875-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="e0875-113">Du kan klicka på berörda enheter när du ser dem i portalen för att öppna en detaljerad rapport om enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="e0875-114">Enheter som påverkas identifieras i följande områden:</span><span class="sxs-lookup"><span data-stu-id="e0875-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="e0875-115">Enhetslista</span><span class="sxs-lookup"><span data-stu-id="e0875-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="e0875-116">Varningskö</span><span class="sxs-lookup"><span data-stu-id="e0875-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e0875-117">Instrumentpanel för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="e0875-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="e0875-118">Alla enskilda aviseringar</span><span class="sxs-lookup"><span data-stu-id="e0875-118">Any individual alert</span></span>
- <span data-ttu-id="e0875-119">Alla enskilda vy med filinformation</span><span class="sxs-lookup"><span data-stu-id="e0875-119">Any individual file details view</span></span>
- <span data-ttu-id="e0875-120">En IP-adress eller domäninformationsvy</span><span class="sxs-lookup"><span data-stu-id="e0875-120">Any IP address or domain details view</span></span>

<span data-ttu-id="e0875-121">När du undersöker en specifik enhet visas:</span><span class="sxs-lookup"><span data-stu-id="e0875-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="e0875-122">Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="e0875-122">Device details</span></span>
- <span data-ttu-id="e0875-123">Svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="e0875-123">Response actions</span></span>
- <span data-ttu-id="e0875-124">Flikar (översikt, varningar, tidslinje, säkerhetsrekommendationer, programlager, identifierade säkerhetsproblem, saknade KBS)</span><span class="sxs-lookup"><span data-stu-id="e0875-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="e0875-125">Kort (aktiva aviseringar, inloggade användare, säkerhetsbedömning)</span><span class="sxs-lookup"><span data-stu-id="e0875-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Bild på enhetsvy](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="e0875-127">Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="e0875-127">Device details</span></span>

<span data-ttu-id="e0875-128">Avsnittet med enhetsinformation innehåller information som enhetens domän, operativsystem och status.</span><span class="sxs-lookup"><span data-stu-id="e0875-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="e0875-129">Om det finns ett undersökningspaket tillgängligt på enheten visas en länk som gör att du kan ladda ned paketet.</span><span class="sxs-lookup"><span data-stu-id="e0875-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="e0875-130">Svarsåtgärder</span><span class="sxs-lookup"><span data-stu-id="e0875-130">Response actions</span></span>

<span data-ttu-id="e0875-131">Svarsåtgärder löper högst upp på en specifik enhet och omfattar:</span><span class="sxs-lookup"><span data-stu-id="e0875-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="e0875-132">Hantera taggar</span><span class="sxs-lookup"><span data-stu-id="e0875-132">Manage tags</span></span>
- <span data-ttu-id="e0875-133">Identifiera enhet</span><span class="sxs-lookup"><span data-stu-id="e0875-133">Isolate device</span></span>
- <span data-ttu-id="e0875-134">Begränsa körning av program</span><span class="sxs-lookup"><span data-stu-id="e0875-134">Restrict app execution</span></span>
- <span data-ttu-id="e0875-135">Kör antivirusgenomsökning</span><span class="sxs-lookup"><span data-stu-id="e0875-135">Run antivirus scan</span></span>
- <span data-ttu-id="e0875-136">Samla in undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="e0875-136">Collect investigation package</span></span>
- <span data-ttu-id="e0875-137">Starta Live Response-session</span><span class="sxs-lookup"><span data-stu-id="e0875-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="e0875-138">Initiera en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="e0875-138">Initiate automated investigation</span></span>
- <span data-ttu-id="e0875-139">Konsultera en hotexpert</span><span class="sxs-lookup"><span data-stu-id="e0875-139">Consult a threat expert</span></span>
- <span data-ttu-id="e0875-140">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="e0875-140">Action center</span></span>

<span data-ttu-id="e0875-141">Du kan vidta åtgärder för svar i Åtgärdscenter, på en viss enhet eller på en viss filsida.</span><span class="sxs-lookup"><span data-stu-id="e0875-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="e0875-142">Mer information om hur du vidta åtgärder på en enhet finns i [Vidta svarsåtgärder på en enhet.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="e0875-143">Mer information finns i Undersöka [användarenheter.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="e0875-144">Flikar</span><span class="sxs-lookup"><span data-stu-id="e0875-144">Tabs</span></span>

<span data-ttu-id="e0875-145">Flikarna ger relevant information om säkerhet och skydd mot hot som är relaterade till enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="e0875-146">På varje flik kan du anpassa de kolumner som visas genom att välja **Anpassa kolumner** från fältet ovanför kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="e0875-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="e0875-147">Översikt</span><span class="sxs-lookup"><span data-stu-id="e0875-147">Overview</span></span>
<span data-ttu-id="e0875-148">På **fliken** Översikt visas [korten](#cards) för aktiva aviseringar, inloggade användare och säkerhetsbedömning.</span><span class="sxs-lookup"><span data-stu-id="e0875-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Bild av översiktsfliken på sidan för enheten](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="e0875-150">Varningar</span><span class="sxs-lookup"><span data-stu-id="e0875-150">Alerts</span></span>

<span data-ttu-id="e0875-151">På **fliken** Aviseringar finns en lista med aviseringar som är associerade med enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="e0875-152">Den här listan är en [](alerts-queue.md)filtrerad version av kön Aviseringar och visar en kort beskrivning av aviseringen, allvarlighetsgraden (hög, medium, låg, information), status i kön (ny, pågående, löst), klassificering (inte inställd, falsk avisering, verklig varning), undersökningstillstånd, kategori av avisering, vem som adresserar aviseringen och den senaste aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e0875-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="e0875-153">Du kan också filtrera aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="e0875-153">You can also filter the alerts.</span></span>

![Bild på aviseringar relaterade till enheten](images/alerts-device.png)

<span data-ttu-id="e0875-155">När cirkelikonen till vänster om en avisering är markerad visas en utfällsymbol.</span><span class="sxs-lookup"><span data-stu-id="e0875-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="e0875-156">Från den här panelen kan du hantera aviseringen och visa mer information, till exempel incidentnummer och relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="e0875-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="e0875-157">Du kan välja flera aviseringar åt gången.</span><span class="sxs-lookup"><span data-stu-id="e0875-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="e0875-158">Om du vill se en helsida med en avisering som innehåller incidentdiagram och processträd väljer du aviseringens rubrik.</span><span class="sxs-lookup"><span data-stu-id="e0875-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="e0875-159">Tidslinje</span><span class="sxs-lookup"><span data-stu-id="e0875-159">Timeline</span></span>

<span data-ttu-id="e0875-160">På **fliken** Tidslinje visas en kronologisk vy över händelserna och tillhörande aviseringar som har observerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="e0875-161">Det kan hjälpa dig korrelera händelser, filer och IP-adresser i relation till enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="e0875-162">På tidslinjen kan du även selektivt granska nedåt i händelser som inträffat under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="e0875-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="e0875-163">Du kan visa tidssekvensen av händelser som inträffat på en enhet under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="e0875-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="e0875-164">Om du vill ha mer kontroll över vyn kan du filtrera efter händelsegrupper eller anpassa kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="e0875-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="e0875-165">För att brandväggshändelser ska visas måste du aktivera granskningsprincipen i Anslutning till [granskningsfiltreringsplattform.](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="e0875-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="e0875-166">Brandväggen omfattar följande händelser</span><span class="sxs-lookup"><span data-stu-id="e0875-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="e0875-167">[5025 –](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) brandväggstjänsten har stoppats</span><span class="sxs-lookup"><span data-stu-id="e0875-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="e0875-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) – programmet kan inte acceptera inkommande anslutningar i nätverket</span><span class="sxs-lookup"><span data-stu-id="e0875-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="e0875-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) – blockerad anslutning</span><span class="sxs-lookup"><span data-stu-id="e0875-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Bild av tidslinjen på enheten med händelser](images/timeline-device.png)

<span data-ttu-id="e0875-171">Några av funktionerna omfattar:</span><span class="sxs-lookup"><span data-stu-id="e0875-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="e0875-172">Söka efter specifika händelser</span><span class="sxs-lookup"><span data-stu-id="e0875-172">Search for specific events</span></span>
  - <span data-ttu-id="e0875-173">Använd sökfältet för att söka efter specifika tidslinjehändelser.</span><span class="sxs-lookup"><span data-stu-id="e0875-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="e0875-174">Filtrera händelser från ett visst datum</span><span class="sxs-lookup"><span data-stu-id="e0875-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="e0875-175">Välj kalenderikonen uppe till vänster i tabellen om du vill visa händelser under den senaste dagen, veckan, 30 dagar eller det anpassade intervallet.</span><span class="sxs-lookup"><span data-stu-id="e0875-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="e0875-176">Som standard är enhetens tidslinje inställd på att visa händelser från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="e0875-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="e0875-177">Använd tidslinjen för att hoppa till en viss tidpunkt genom att markera avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e0875-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="e0875-178">Pilarna på tidslinjens pinpoint för automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="e0875-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="e0875-179">Exportera detaljerade tidslinjehändelser för enheter</span><span class="sxs-lookup"><span data-stu-id="e0875-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="e0875-180">Exportera enhetens tidslinje för det aktuella datumet eller ett angivet datumintervall upp till sju dagar.</span><span class="sxs-lookup"><span data-stu-id="e0875-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="e0875-181">Mer information om vissa händelser finns i **avsnittet Ytterligare information.**</span><span class="sxs-lookup"><span data-stu-id="e0875-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="e0875-182">Den här informationen varierar beroende på typen av händelse, till exempel:</span><span class="sxs-lookup"><span data-stu-id="e0875-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="e0875-183">Finns av Application Guard – webbläsarhändelsen begränsades av en isolerad behållare</span><span class="sxs-lookup"><span data-stu-id="e0875-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="e0875-184">Aktiva hot upptäcktes – hotidentifieringen inträffade medan hoten kördes</span><span class="sxs-lookup"><span data-stu-id="e0875-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="e0875-185">Åtgärd lyckades inte – ett försök att åtgärda det identifierade hotet anropades men misslyckades</span><span class="sxs-lookup"><span data-stu-id="e0875-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="e0875-186">Åtgärd lyckades – det identifierade hotet har stoppats och åtgärdats</span><span class="sxs-lookup"><span data-stu-id="e0875-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="e0875-187">Varning som förbikopplats av användaren – Windows Defender SmartScreen-varningen avvisades och åsidosättdes av en användare</span><span class="sxs-lookup"><span data-stu-id="e0875-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="e0875-188">Misstänkt skript har upptäckts – ett skript som kan vara skadligt hittades när det kördes</span><span class="sxs-lookup"><span data-stu-id="e0875-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="e0875-189">Aviseringskategorin – om händelsen ledde till en avisering genereras aviseringskategorin ("T.ex. aviseringsrörelse")</span><span class="sxs-lookup"><span data-stu-id="e0875-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="e0875-190">Händelseinformation</span><span class="sxs-lookup"><span data-stu-id="e0875-190">Event details</span></span>
<span data-ttu-id="e0875-191">Välj en händelse om du vill visa relevant information om händelsen.</span><span class="sxs-lookup"><span data-stu-id="e0875-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="e0875-192">En panel visas för att visa allmän händelseinformation.</span><span class="sxs-lookup"><span data-stu-id="e0875-192">A panel displays to show general event information.</span></span> <span data-ttu-id="e0875-193">När tillämpliga data är tillgängliga visas även ett diagram som visar relaterade enheter och deras relationer.</span><span class="sxs-lookup"><span data-stu-id="e0875-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="e0875-194">Om du vill kontrollera händelsen ytterligare och relaterade händelser kan du snabbt köra en [avancerad fråga om sökning](advanced-hunting-overview.md) genom att välja Sök efter relaterade **händelser.**</span><span class="sxs-lookup"><span data-stu-id="e0875-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="e0875-195">Frågan returnerar den valda händelsen och listan med andra händelser som inträffade samtidigt på samma slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="e0875-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Bild på panelen med händelseinformation](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="e0875-197">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="e0875-197">Security recommendations</span></span>

<span data-ttu-id="e0875-198">**Säkerhetsrekommendationer** genereras från Microsoft Defender för Endpoints hot för [& Sårbarhetshantering.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="e0875-199">Om du väljer en rekommendation visas en panel där du kan se relevant information, till exempel en beskrivning av rekommendationen och potentiella risker som är förknippade med att inte anta den.</span><span class="sxs-lookup"><span data-stu-id="e0875-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="e0875-200">Mer [information finns i Säkerhetsrekommendationer.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Bild av fliken säkerhetsrekommendationer](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="e0875-202">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="e0875-202">Software inventory</span></span>

<span data-ttu-id="e0875-203">På **fliken För inventering** av programvara kan du visa programvara på enheten och se eventuella hot eller svagheter.</span><span class="sxs-lookup"><span data-stu-id="e0875-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="e0875-204">Om du markerar namnet på programvaran kommer du till sidan med programvaruinformation där du kan se säkerhetsrekommendationer, identifierade säkerhetsproblem, installerade enheter och versionsdistribution.</span><span class="sxs-lookup"><span data-stu-id="e0875-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="e0875-205">Se [Inventering av programvara](tvm-software-inventory.md) för mer information</span><span class="sxs-lookup"><span data-stu-id="e0875-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Bild på fliken för programvaruinventering](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="e0875-207">Upptäckta säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="e0875-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="e0875-208">På **fliken Identifierade säkerhetsproblem** visas namn, allvarlighetsgrad och information om hot om identifierade säkerhetsproblem på enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="e0875-209">Om du väljer specifika säkerhetsproblem visas en beskrivning och information.</span><span class="sxs-lookup"><span data-stu-id="e0875-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Fliken upptäckta säkerhetsproblem](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="e0875-211">Saknade KBs</span><span class="sxs-lookup"><span data-stu-id="e0875-211">Missing KBs</span></span>
<span data-ttu-id="e0875-212">På **fliken saknade KB** visas de säkerhetsuppdateringar som saknas för enheten.</span><span class="sxs-lookup"><span data-stu-id="e0875-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Bild på fliken kbs som saknas](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="e0875-214">Kort</span><span class="sxs-lookup"><span data-stu-id="e0875-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="e0875-215">Aktiva aviseringar</span><span class="sxs-lookup"><span data-stu-id="e0875-215">Active alerts</span></span>

<span data-ttu-id="e0875-216">**Kortet Azure Advanced Threat Protection** visar en översikt över aviseringar relaterade till enheten och deras risknivå, om du har aktiverat Azure ATP-funktionen och det finns aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="e0875-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="e0875-217">Mer information finns i den granskande detaljgranskningen "Aviseringar".</span><span class="sxs-lookup"><span data-stu-id="e0875-217">More information is available in the "Alerts" drill down.</span></span>

![Bild på aktiva varningskort](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="e0875-219">Du måste aktivera integreringen på både Azure ATP och Defender för Endpoint om du vill använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="e0875-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="e0875-220">I Defender för Slutpunkt kan du aktivera den här funktionen i avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="e0875-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="e0875-221">Mer information om hur du aktiverar avancerade funktioner finns i [Aktivera avancerade funktioner.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="e0875-222">Inloggade användare</span><span class="sxs-lookup"><span data-stu-id="e0875-222">Logged on users</span></span>

<span data-ttu-id="e0875-223">Kortet **Inloggade användare visar** hur många användare som har loggat in de senaste 30 dagarna, tillsammans med de mest och minst vanliga användarna.</span><span class="sxs-lookup"><span data-stu-id="e0875-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="e0875-224">Om du väljer länken "Visa alla användare" öppnas informationsfönstret med information som användartyp, inloggningstyp och när användaren sågs för första och sista gången.</span><span class="sxs-lookup"><span data-stu-id="e0875-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="e0875-225">Mer information finns i Undersöka [användarenheter.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="e0875-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Bild av fönstret med användarinformation](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="e0875-227">Säkerhetsutvärderingar</span><span class="sxs-lookup"><span data-stu-id="e0875-227">Security assessments</span></span>

<span data-ttu-id="e0875-228">Kortet **för säkerhetsutvärderingar** visar den totala exponeringsnivån, säkerhetsrekommendationer, installerad programvara och identifierade säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="e0875-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="e0875-229">Exponeringsnivån för en enhet bestäms av den kumulativa effekten av de väntande säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="e0875-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Bild på kortet med säkerhetsutvärderingar](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="e0875-231">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e0875-231">Related topics</span></span>

- [<span data-ttu-id="e0875-232">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="e0875-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e0875-233">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="e0875-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="e0875-234">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="e0875-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="e0875-235">Undersöka en fil som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="e0875-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="e0875-236">Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="e0875-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="e0875-237">Undersöka en domän som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="e0875-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="e0875-238">Undersöka ett användarkonto i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="e0875-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="e0875-239">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="e0875-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e0875-240">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="e0875-240">Software inventory</span></span>](tvm-software-inventory.md)
