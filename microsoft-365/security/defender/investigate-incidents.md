---
title: Undersöka incidenter i Microsoft 365 Defender
description: Analysera incidenter relaterade till enheter, användare och postlådor.
keywords: incidenter, incidenter, datorer, enheter, användare, identiteter, e-post, e-post, postlåda, undersökning, diagram, bevis
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592102"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1b40d-104">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b40d-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b40d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1b40d-105">**Applies to:**</span></span>

- <span data-ttu-id="1b40d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b40d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1b40d-107">Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från olika enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.</span><span class="sxs-lookup"><span data-stu-id="1b40d-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="1b40d-108">Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla bevis som är associerade med incidenterna så att du kan skapa en gällande åtgärdsplan.</span><span class="sxs-lookup"><span data-stu-id="1b40d-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="1b40d-109">Undersöka en händelse</span><span class="sxs-lookup"><span data-stu-id="1b40d-109">Investigate an incident</span></span>

1. <span data-ttu-id="1b40d-110">Välj en incident i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="1b40d-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="1b40d-111">En sidopanel öppnas och visar en förhandsgranskning av viktig information, till exempel status, allvarlighetsgrad, kategorier och berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="1b40d-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild på sidopanelen för incidenter](../../media/incident-side-panel.png)

2. <span data-ttu-id="1b40d-113">Välj **Öppna incidentsida**.</span><span class="sxs-lookup"><span data-stu-id="1b40d-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="1b40d-114">Då öppnas incidentsidan där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).</span><span class="sxs-lookup"><span data-stu-id="1b40d-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="1b40d-115">Granska aviseringar, enheter, användare och andra enheter som är inblandade i händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="1b40d-116">Incidentöversikt</span><span class="sxs-lookup"><span data-stu-id="1b40d-116">Incident overview</span></span>

<span data-ttu-id="1b40d-117">På översiktssidan får du en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Bild på översiktssidan för incidenter](../../media/incidents-overview.png)

<span data-ttu-id="1b40d-119">Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain.</span><span class="sxs-lookup"><span data-stu-id="1b40d-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="1b40d-120">Precis som andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender i linje med [MITRE ATT&&trade; CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="1b40d-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="1b40d-121">I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="1b40d-122">Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1b40d-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="1b40d-123">På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="1b40d-124">Och sist – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du genast kan se om någon åtgärd behövs på din slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="1b40d-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="1b40d-125">Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge information om de viktigaste egenskaperna för incidenten som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="1b40d-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="1b40d-126">Varningar</span><span class="sxs-lookup"><span data-stu-id="1b40d-126">Alerts</span></span>

<span data-ttu-id="1b40d-127">Du kan visa alla aviseringar som rör händelsen och annan information om dem, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365) och orsaken till att de länkades ihop.</span><span class="sxs-lookup"><span data-stu-id="1b40d-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Bild på sidan incidentaviseringar](../../media/incident-alerts.png)

<span data-ttu-id="1b40d-129">Som standard sorteras aviseringarna kronologiskt så att du först kan se hur attacken utspelas med tiden.</span><span class="sxs-lookup"><span data-stu-id="1b40d-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="1b40d-130">Om du klickar på varje avisering kommer du till den relevanta aviseringssidan där du kan undersöka den aviseringen på djupet.</span><span class="sxs-lookup"><span data-stu-id="1b40d-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="1b40d-131">Lär dig hur du använder aviseringssidor och den enhetliga aviseringskön i [Undersöka aviseringar](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1b40d-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="1b40d-132">Enheter</span><span class="sxs-lookup"><span data-stu-id="1b40d-132">Devices</span></span>

<span data-ttu-id="1b40d-133">På fliken Enheter visas alla enheter där aviseringar om händelsen visas.</span><span class="sxs-lookup"><span data-stu-id="1b40d-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="1b40d-134">Om du klickar på namnet på den dator där attacken utfördes navigeras du till sidan Dator där du kan se aviseringar som utlöstes på den och relaterade händelser för att underlätta undersökning.</span><span class="sxs-lookup"><span data-stu-id="1b40d-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Bild på fliken datorer för ett incident](../../media/incident-machines.png)

<span data-ttu-id="1b40d-136">Genom att välja fliken Tidslinje kan du bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.</span><span class="sxs-lookup"><span data-stu-id="1b40d-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="1b40d-137">Du kan göra genomsökningar på begäran på en enhet.</span><span class="sxs-lookup"><span data-stu-id="1b40d-137">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="1b40d-138">I Säkerhetscenter för Microsoft 365 väljer du **Enhetsinventering**.</span><span class="sxs-lookup"><span data-stu-id="1b40d-138">In the Microsoft 365 security center, choose **Device inventory**.</span></span> <span data-ttu-id="1b40d-139">Välj en enhet med aviseringar och kör sedan en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="1b40d-139">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="1b40d-140">Åtgärder, till exempel antivirusskanningar, spåras och visas på sidan **Enhetsinventering.**</span><span class="sxs-lookup"><span data-stu-id="1b40d-140">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="1b40d-141">Mer information finns i Kör [sökning efter Microsoft Defender Antivirus på enheter.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="1b40d-141">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>


## <a name="users"></a><span data-ttu-id="1b40d-142">Användare</span><span class="sxs-lookup"><span data-stu-id="1b40d-142">Users</span></span>

<span data-ttu-id="1b40d-143">Se användare som har identifierats vara en del av eller relaterade till en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="1b40d-143">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="1b40d-144">När du klickar på användarnamnet navigeras du till sidan Säkerhet i Molnappen där vidare undersökning kan genomföras.</span><span class="sxs-lookup"><span data-stu-id="1b40d-144">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Bild på fliken Användare för ett incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="1b40d-146">Postlådor</span><span class="sxs-lookup"><span data-stu-id="1b40d-146">Mailboxes</span></span>

<span data-ttu-id="1b40d-147">Undersök postlådor som har identifierats som en del av eller relaterade till ett problem.</span><span class="sxs-lookup"><span data-stu-id="1b40d-147">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="1b40d-148">Om du vill utföra ytterligare åtgärder kan du välja den e-postrelaterade aviseringen för att öppna Microsoft Defender för Office 365, där du kan vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1b40d-148">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Bild av postlådefliken för ett incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="1b40d-150">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="1b40d-150">Investigations</span></span>

<span data-ttu-id="1b40d-151">Välj **Undersökningar** om du vill se alla automatiserade undersökningar som utlösts av aviseringar om den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-151">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="1b40d-152">Undersökningarna utför åtgärder eller väntar på analytikernas godkännande av åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b40d-152">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Bild på fliken för undersökningar för ett incident](../../media/incident-investigations.png)

<span data-ttu-id="1b40d-154">Välj en undersökning för att gå till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="1b40d-154">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="1b40d-155">Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.</span><span class="sxs-lookup"><span data-stu-id="1b40d-155">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="1b40d-156">Bevis</span><span class="sxs-lookup"><span data-stu-id="1b40d-156">Evidence</span></span>

<span data-ttu-id="1b40d-157">Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga filer, processer, tjänster, e-postmeddelanden med mera.</span><span class="sxs-lookup"><span data-stu-id="1b40d-157">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="1b40d-158">Det här hjälper dig att snabbt identifiera och blockera potentiella hot i händelsen.</span><span class="sxs-lookup"><span data-stu-id="1b40d-158">This helps quickly detect and block potential threats in the incident.</span></span>

![Bild av bevisfliken för en händelse](../../media/incident-evidence.png)

<span data-ttu-id="1b40d-160">Var och en av de analyserade enheterna markeras med en bedömning (skadlig, misstänkt, ren) samt en åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="1b40d-160">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="1b40d-161">På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som är nästa steg som kan åtgärdas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="1b40d-161">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b40d-162">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1b40d-162">Related topics</span></span>

- [<span data-ttu-id="1b40d-163">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="1b40d-163">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1b40d-164">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="1b40d-164">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="1b40d-165">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="1b40d-165">Manage incidents</span></span>](manage-incidents.md)

