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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: dcfc3bd0e06e0bdca6c834e947d7d136af47fde3
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782831"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="589fe-104">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="589fe-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="589fe-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="589fe-105">**Applies to:**</span></span>

- <span data-ttu-id="589fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="589fe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="589fe-107">Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från alla dina enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.</span><span class="sxs-lookup"><span data-stu-id="589fe-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="589fe-108">Inom en incident analyserar du aviseringarna som påverkar nätverket, förstår vad de betyder och sorterar bevisen så att du kan skapa en gällande åtgärdsplan.</span><span class="sxs-lookup"><span data-stu-id="589fe-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="589fe-109">Inledande undersökning</span><span class="sxs-lookup"><span data-stu-id="589fe-109">Initial investigation</span></span>

<span data-ttu-id="589fe-110">Innan du börjar med detaljerna tar du en titt på egenskaperna och sammanfattningen av händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="589fe-111">Du börjar genom att välja incidenten i bockkolumnen.</span><span class="sxs-lookup"><span data-stu-id="589fe-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="589fe-112">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exempel på val av incident i bockkolumnen":::

<span data-ttu-id="589fe-114">När du gör det öppnas ett sammanfattningsfönster med viktig information om händelsen, till exempel allvarlighetsgrad, som den har tilldelats, och [kategorierna MITRE ATT &trade;&CK](https://attack.mitre.org/) för händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="589fe-115">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exempel på sammanfattningsfönstret för ett incident":::

<span data-ttu-id="589fe-117">Härifrån kan du välja **Öppna incidentsida.**</span><span class="sxs-lookup"><span data-stu-id="589fe-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="589fe-118">Då öppnas huvudsidan för incidenten där du hittar mer sammanfattande information och flikar för aviseringar, enheter, användare, undersökningar och bevis.</span><span class="sxs-lookup"><span data-stu-id="589fe-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="589fe-119">Du kan också öppna huvudsidan för en händelse genom att välja incidentnamnet från incidentkön.</span><span class="sxs-lookup"><span data-stu-id="589fe-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="589fe-120">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="589fe-120">Summary</span></span>

<span data-ttu-id="589fe-121">**Sammanfattningssidan** ger en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="589fe-123">Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain.</span><span class="sxs-lookup"><span data-stu-id="589fe-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="589fe-124">Precis som andra Microsoft-säkerhetsprodukter Microsoft 365 Defender i linje med [MITRE ATT &trade;&CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="589fe-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="589fe-125">I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="589fe-126">Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="589fe-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="589fe-127">På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="589fe-128">Och sista – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du direkt kan identifiera om någon åtgärd krävs av dig.</span><span class="sxs-lookup"><span data-stu-id="589fe-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="589fe-129">Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge kunskap om de viktigaste egenskaperna för incidenten som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="589fe-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="589fe-130">Varningar</span><span class="sxs-lookup"><span data-stu-id="589fe-130">Alerts</span></span>

<span data-ttu-id="589fe-131">På fliken **Avisering** kan du visa aviseringskön för aviseringar om händelsen och annan information om dem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="589fe-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="589fe-132">Allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="589fe-132">Severity.</span></span>
- <span data-ttu-id="589fe-133">Enheterna som var inblandade i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="589fe-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="589fe-134">Varningens källa (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="589fe-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="589fe-135">Orsaken till att de var länkade till varandra.</span><span class="sxs-lookup"><span data-stu-id="589fe-135">The reason they were linked together.</span></span>

<span data-ttu-id="589fe-136">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exempel på en aviseringssida för ett incident":::

<span data-ttu-id="589fe-138">Som standard sorteras aviseringarna kronologiskt så att du kan se hur händelsen spelats ut med tiden.</span><span class="sxs-lookup"><span data-stu-id="589fe-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="589fe-139">När du väljer en avisering i en Microsoft 365 Defender visas aviseringsinformation som är specifik för den övergripande händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="589fe-140">Du kan se händelser för aviseringen, vilket andra utlöste aviseringar orsakade den aktuella aviseringen och alla berörda enheter och aktiviteter som var inblandade i attacken, inklusive filer, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="589fe-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="589fe-141">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Exempel på en sida med aviseringsinformation i ett incident":::

<span data-ttu-id="589fe-143">Den här aviseringssidan för incidenter består av följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="589fe-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="589fe-144">Aviseringsartikel, som innehåller en sammanfattning av vad som har hänt</span><span class="sxs-lookup"><span data-stu-id="589fe-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="589fe-145">Relaterade händelser och aviseringar</span><span class="sxs-lookup"><span data-stu-id="589fe-145">Related events and alerts</span></span>
- <span data-ttu-id="589fe-146">Sammanfattningsinformation</span><span class="sxs-lookup"><span data-stu-id="589fe-146">Summary details</span></span>

<span data-ttu-id="589fe-147">Lär dig hur du använder aviseringskön och aviseringssidorna [i undersöker aviseringar](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="589fe-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="589fe-148">Enheter</span><span class="sxs-lookup"><span data-stu-id="589fe-148">Devices</span></span>

<span data-ttu-id="589fe-149">På **fliken** Enheter visas alla enheter som är relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="589fe-150">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Sidan Enheter för ett incident":::

<span data-ttu-id="589fe-152">Du kan markera bockmarkeringen för en enhet om du vill visa information om enheten, katalogdata, aktiva aviseringar och inloggade användare.</span><span class="sxs-lookup"><span data-stu-id="589fe-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="589fe-153">Välj namnet på enheten för att visa enhetsinformation i Microsoft Defender för endpoints enhetslager.</span><span class="sxs-lookup"><span data-stu-id="589fe-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exempel på en enhetssida för Microsoft Defender för slutpunkter":::

<span data-ttu-id="589fe-155">På sidan enhet kan du samla in ytterligare information om enheten, till exempel alla aviseringar, en tidslinje och säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="589fe-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="589fe-156">På fliken Tidslinje  kan du till exempel bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.</span><span class="sxs-lookup"><span data-stu-id="589fe-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="589fe-157">Du kan göra genomsökningar på begäran på en enhet.</span><span class="sxs-lookup"><span data-stu-id="589fe-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="589fe-158">I säkerhetscentret Microsoft 365 du Slutpunkter **för > Enhetsinventering**.</span><span class="sxs-lookup"><span data-stu-id="589fe-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="589fe-159">Välj en enhet med aviseringar och kör sedan en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="589fe-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="589fe-160">Åtgärder, till exempel antivirusskanningar, spåras och visas på sidan **Enhetsinventering.**</span><span class="sxs-lookup"><span data-stu-id="589fe-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="589fe-161">Mer information finns i [Kör Microsoft Defender Antivirus sökning på enheter](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="589fe-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="589fe-162">Användare</span><span class="sxs-lookup"><span data-stu-id="589fe-162">Users</span></span>

<span data-ttu-id="589fe-163">På **fliken** Användare visas alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="589fe-164">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

<span data-ttu-id="589fe-166">Du kan välja bockmarkeringen för en användare om du vill se information om hot om användarkontot, exponering och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="589fe-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="589fe-167">Välj användarnamnet om du vill se mer information om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="589fe-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="589fe-168">Lär dig hur du visar ytterligare användarinformation och hanterar användare av en händelse i [undersöker användare.](investigate-users.md)</span><span class="sxs-lookup"><span data-stu-id="589fe-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="589fe-169">Postlådor</span><span class="sxs-lookup"><span data-stu-id="589fe-169">Mailboxes</span></span>

<span data-ttu-id="589fe-170">På **fliken Postlådor** visas alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="589fe-171">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exempel på en postlådesida för ett incident":::

<span data-ttu-id="589fe-173">Du kan välja bockmarkeringen för en postlåda om du vill visa en lista med aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="589fe-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="589fe-174">Välj postlådans namn om du vill se ytterligare information om postlådan på sidan i Utforskaren för Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="589fe-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="589fe-175">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="589fe-175">Investigations</span></span>

<span data-ttu-id="589fe-176">På **fliken Undersökningar** finns alla automatiserade undersökningar [som](m365d-autoir.md) utlösts av aviseringar om den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="589fe-177">Undersökningarna utför åtgärder eller väntar på att analytiker har godkänt åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="589fe-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exempel på en sida för undersökningar för en incident":::

<span data-ttu-id="589fe-179">Välj en undersökning för att gå till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="589fe-179">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="589fe-180">Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.</span><span class="sxs-lookup"><span data-stu-id="589fe-180">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="589fe-181">Mer information finns i [Automatiserad undersökning och svar i Microsoft 365 Defender](m365d-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="589fe-181">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="589fe-182">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="589fe-182">Evidence and Response</span></span>

<span data-ttu-id="589fe-183">På **fliken Bevis och** svar visas alla händelser som stöds och misstänkta enheter i aviseringarna för incidenten.</span><span class="sxs-lookup"><span data-stu-id="589fe-183">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="589fe-184">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-184">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exempel på en sida med bevis och svar för ett incident":::

<span data-ttu-id="589fe-186">Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga e-postmeddelanden, filer, processer, tjänster, IP-adresser med mera.</span><span class="sxs-lookup"><span data-stu-id="589fe-186">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="589fe-187">På så sätt kan du snabbt identifiera och blockera potentiella hot i händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-187">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="589fe-188">Var och en av de analyserade enheterna är markerade med en bedömning (skadlig, misstänkt, ren) och en åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="589fe-188">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="589fe-189">På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som kan göras härnäst.</span><span class="sxs-lookup"><span data-stu-id="589fe-189">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="589fe-190">Graph (i förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="589fe-190">Graph (in preview)</span></span>

<span data-ttu-id="589fe-191">Med den **nya Graph** (i förhandsgranskningen) kan du se:</span><span class="sxs-lookup"><span data-stu-id="589fe-191">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="589fe-192">Kopplingen av aviseringar till de påverkade tillgångarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="589fe-192">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="589fe-193">Vilka enheter är relaterade till vilka aviseringar och hur de är en del av attackens historia.</span><span class="sxs-lookup"><span data-stu-id="589fe-193">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="589fe-194">Aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="589fe-194">The alerts for the incident.</span></span>

<span data-ttu-id="589fe-195">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="589fe-195">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Exempel på en Graph för ett incident":::

<span data-ttu-id="589fe-197">Med hjälp av incidentdiagrammet får du snabbt en fullständig förståelse för attacken genom att ansluta olika misstänkta enheter som är en del av attacken till sina relaterade tillgångar, till exempel användare, enheter och postlådor.</span><span class="sxs-lookup"><span data-stu-id="589fe-197">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="589fe-198">Nu kan du förstå hur attacken spridas genom nätverket över tid, var den startade och hur långt attacken gick.</span><span class="sxs-lookup"><span data-stu-id="589fe-198">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="589fe-199">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="589fe-199">Next steps</span></span>

<span data-ttu-id="589fe-200">Vid behov:</span><span class="sxs-lookup"><span data-stu-id="589fe-200">As needed:</span></span>

- [<span data-ttu-id="589fe-201">Undersök aviseringarna om en händelse</span><span class="sxs-lookup"><span data-stu-id="589fe-201">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="589fe-202">Undersöka användarna av ett problem</span><span class="sxs-lookup"><span data-stu-id="589fe-202">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="589fe-203">Se även</span><span class="sxs-lookup"><span data-stu-id="589fe-203">See also</span></span>

- [<span data-ttu-id="589fe-204">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="589fe-204">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="589fe-205">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="589fe-205">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="589fe-206">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="589fe-206">Manage incidents</span></span>](manage-incidents.md)

