---
title: Undersöka incidenter i Microsoft 365 Defender
description: Undersök incidenter relaterade till enheter, användare och postlådor.
keywords: incidenter, incidenter, analysera, svar, datorer, enheter, användare, identiteter, e-post, e-post, postlåda, undersökning, diagram, bevis
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
ms.openlocfilehash: 7abc99a14ec538afea8cdbd4d8f3b4940bcccd9f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300091"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="0e252-104">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e252-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0e252-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0e252-105">**Applies to:**</span></span>

- <span data-ttu-id="0e252-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e252-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0e252-107">Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från alla dina enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.</span><span class="sxs-lookup"><span data-stu-id="0e252-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="0e252-108">Inom en incident analyserar du aviseringarna som påverkar nätverket, förstår vad de betyder och sorterar bevisen så att du kan skapa en gällande åtgärdsplan.</span><span class="sxs-lookup"><span data-stu-id="0e252-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="0e252-109">Inledande undersökning</span><span class="sxs-lookup"><span data-stu-id="0e252-109">Initial investigation</span></span>

<span data-ttu-id="0e252-110">Innan du börjar med detaljerna tar du en titt på egenskaperna och sammanfattningen av händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="0e252-111">Du börjar genom att välja incidenten i bockkolumnen.</span><span class="sxs-lookup"><span data-stu-id="0e252-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="0e252-112">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exempel på val av incident i bockkolumnen":::

<span data-ttu-id="0e252-114">När du gör det öppnas ett sammanfattningsfönster med viktig information om händelsen, till exempel allvarlighetsgrad, som den har tilldelats, och [kategorierna MITRE ATT &trade;&CK](https://attack.mitre.org/) för händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="0e252-115">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exempel på sammanfattningsfönstret för ett incident":::

<span data-ttu-id="0e252-117">Härifrån kan du välja **Öppna incidentsida.**</span><span class="sxs-lookup"><span data-stu-id="0e252-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="0e252-118">Då öppnas huvudsidan för incidenten där du hittar mer sammanfattande information och flikar för aviseringar, enheter, användare, undersökningar och bevis.</span><span class="sxs-lookup"><span data-stu-id="0e252-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="0e252-119">Du kan också öppna huvudsidan för en händelse genom att välja incidentnamnet från incidentkön.</span><span class="sxs-lookup"><span data-stu-id="0e252-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="0e252-120">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="0e252-120">Summary</span></span>

<span data-ttu-id="0e252-121">**Sammanfattningssidan** ger en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="0e252-123">Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain.</span><span class="sxs-lookup"><span data-stu-id="0e252-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="0e252-124">Precis som andra Microsoft-säkerhetsprodukter Microsoft 365 Defender i linje med [MITRE ATT &trade;&CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="0e252-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="0e252-125">I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="0e252-126">Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0e252-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="0e252-127">På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="0e252-128">Och sista – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du direkt kan identifiera om någon åtgärd krävs av dig.</span><span class="sxs-lookup"><span data-stu-id="0e252-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="0e252-129">Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge kunskap om de viktigaste egenskaperna för incidenten som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="0e252-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="0e252-130">Varningar</span><span class="sxs-lookup"><span data-stu-id="0e252-130">Alerts</span></span>

<span data-ttu-id="0e252-131">På fliken **Avisering** kan du visa aviseringskön för aviseringar om händelsen och annan information om dem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="0e252-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="0e252-132">Allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="0e252-132">Severity.</span></span>
- <span data-ttu-id="0e252-133">Enheterna som var inblandade i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="0e252-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="0e252-134">Varningens källa (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="0e252-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="0e252-135">Orsaken till att de var länkade till varandra.</span><span class="sxs-lookup"><span data-stu-id="0e252-135">The reason they were linked together.</span></span>

<span data-ttu-id="0e252-136">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exempel på en aviseringssida för ett incident":::

<span data-ttu-id="0e252-138">Som standard sorteras aviseringarna kronologiskt så att du kan se hur händelsen spelats ut med tiden.</span><span class="sxs-lookup"><span data-stu-id="0e252-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="0e252-139">Om du markerar varje avisering kommer du till huvudsidan för den aviseringen, där du kan göra en detaljerad analys av den aviseringen.</span><span class="sxs-lookup"><span data-stu-id="0e252-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="0e252-140">Lär dig hur du använder aviseringskön och aviseringssidorna [i undersöker aviseringar](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="0e252-140">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="0e252-141">Enheter</span><span class="sxs-lookup"><span data-stu-id="0e252-141">Devices</span></span>

<span data-ttu-id="0e252-142">På **fliken** Enheter visas alla enheter som är relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="0e252-143">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Sidan Enheter för ett incident":::

<span data-ttu-id="0e252-145">Du kan markera bockmarkeringen för en enhet om du vill visa information om enheten, katalogdata, aktiva aviseringar och inloggade användare.</span><span class="sxs-lookup"><span data-stu-id="0e252-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="0e252-146">Välj namnet på enheten för att visa enhetsinformation i Microsoft Defender för endpoints enhetslager.</span><span class="sxs-lookup"><span data-stu-id="0e252-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exempel på en enhetssida för Microsoft Defender för slutpunkter":::

<span data-ttu-id="0e252-148">På sidan enhet kan du samla in ytterligare information om enheten, till exempel alla aviseringar, en tidslinje och säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="0e252-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="0e252-149">På fliken Tidslinje  kan du till exempel bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.</span><span class="sxs-lookup"><span data-stu-id="0e252-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="0e252-150">Du kan göra genomsökningar på begäran på en enhet.</span><span class="sxs-lookup"><span data-stu-id="0e252-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="0e252-151">I säkerhetscentret Microsoft 365 du Slutpunkter **för > Enhetsinventering**.</span><span class="sxs-lookup"><span data-stu-id="0e252-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="0e252-152">Välj en enhet med aviseringar och kör sedan en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="0e252-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="0e252-153">Åtgärder, till exempel antivirusskanningar, spåras och visas på sidan **Enhetsinventering.**</span><span class="sxs-lookup"><span data-stu-id="0e252-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="0e252-154">Mer information finns i [Kör Microsoft Defender Antivirus sökning på enheter](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="0e252-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="0e252-155">Användare</span><span class="sxs-lookup"><span data-stu-id="0e252-155">Users</span></span>

<span data-ttu-id="0e252-156">På **fliken** Användare visas alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="0e252-157">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

<span data-ttu-id="0e252-159">Du kan välja bockmarkeringen för en användare om du vill se information om hot om användarkontot, exponering och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="0e252-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="0e252-160">Välj användarnamnet om du vill se mer information om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="0e252-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="0e252-161">Postlådor</span><span class="sxs-lookup"><span data-stu-id="0e252-161">Mailboxes</span></span>

<span data-ttu-id="0e252-162">På **fliken Postlådor** visas alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="0e252-163">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exempel på en postlådesida för ett incident":::

<span data-ttu-id="0e252-165">Du kan välja bockmarkeringen för en postlåda om du vill visa en lista med aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="0e252-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="0e252-166">Välj postlådans namn om du vill se ytterligare information om postlådan på sidan i Utforskaren för Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e252-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="0e252-167">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="0e252-167">Investigations</span></span>

<span data-ttu-id="0e252-168">På **fliken Undersökningar** finns alla automatiserade undersökningar [som](m365d-autoir.md) utlösts av aviseringar om den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-168">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="0e252-169">Undersökningarna utför åtgärder eller väntar på att analytiker har godkänt åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e252-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exempel på en sida för undersökningar för en incident":::

<span data-ttu-id="0e252-171">Välj en undersökning för att gå till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="0e252-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="0e252-172">Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.</span><span class="sxs-lookup"><span data-stu-id="0e252-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="0e252-173">Mer information finns i [Automatiserad undersökning och svar i Microsoft 365 Defender](m365d-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="0e252-173">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="0e252-174">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="0e252-174">Evidence and Response</span></span>

<span data-ttu-id="0e252-175">På **fliken Bevis och** svar visas alla händelser som stöds och misstänkta enheter i aviseringarna för incidenten.</span><span class="sxs-lookup"><span data-stu-id="0e252-175">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="0e252-176">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-176">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exempel på en sida med bevis och svar för ett incident":::

<span data-ttu-id="0e252-178">Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga e-postmeddelanden, filer, processer, tjänster, IP-adresser med mera.</span><span class="sxs-lookup"><span data-stu-id="0e252-178">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="0e252-179">På så sätt kan du snabbt identifiera och blockera potentiella hot i händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-179">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="0e252-180">Var och en av de analyserade enheterna är markerade med en bedömning (skadlig, misstänkt, ren) och en åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="0e252-180">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="0e252-181">På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som kan göras härnäst.</span><span class="sxs-lookup"><span data-stu-id="0e252-181">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="0e252-182">Graph (i förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="0e252-182">Graph (in preview)</span></span>

<span data-ttu-id="0e252-183">Med den **nya Graph** (i förhandsgranskningen) kan du se:</span><span class="sxs-lookup"><span data-stu-id="0e252-183">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="0e252-184">Kopplingen av aviseringar till de påverkade tillgångarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0e252-184">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="0e252-185">Vilka enheter är relaterade till vilka aviseringar och hur de är en del av attackens historia.</span><span class="sxs-lookup"><span data-stu-id="0e252-185">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="0e252-186">Aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="0e252-186">The alerts for the incident.</span></span>

<span data-ttu-id="0e252-187">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0e252-187">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Exempel på en Graph för ett incident":::

<span data-ttu-id="0e252-189">Med hjälp av incidentdiagrammet får du snabbt en fullständig förståelse för attacken genom att ansluta olika misstänkta enheter som är en del av attacken till sina relaterade tillgångar, till exempel användare, enheter och postlådor.</span><span class="sxs-lookup"><span data-stu-id="0e252-189">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="0e252-190">Nu kan du förstå hur attacken spridas genom nätverket över tid, var den startade och hur långt attacken gick.</span><span class="sxs-lookup"><span data-stu-id="0e252-190">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0e252-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0e252-191">Next steps</span></span>

<span data-ttu-id="0e252-192">Vid behov:</span><span class="sxs-lookup"><span data-stu-id="0e252-192">As needed:</span></span>

- [<span data-ttu-id="0e252-193">Undersök aviseringarna om en händelse</span><span class="sxs-lookup"><span data-stu-id="0e252-193">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="0e252-194">Undersöka användarna av ett problem</span><span class="sxs-lookup"><span data-stu-id="0e252-194">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="0e252-195">Se även</span><span class="sxs-lookup"><span data-stu-id="0e252-195">See also</span></span>

- [<span data-ttu-id="0e252-196">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="0e252-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0e252-197">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="0e252-197">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="0e252-198">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="0e252-198">Manage incidents</span></span>](manage-incidents.md)

