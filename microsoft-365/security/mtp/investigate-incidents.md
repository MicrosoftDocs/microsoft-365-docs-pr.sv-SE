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
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
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
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926900"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="87fbb-104">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87fbb-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87fbb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="87fbb-105">**Applies to:**</span></span>

- <span data-ttu-id="87fbb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87fbb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="87fbb-107">Microsoft 365 Defender sammanställer alla relaterade varningar, tillgångar, undersökningar och bevis från dina enheter, användare och postlådor för att ge dig en fullständig översikt över hela bredden på en attack.</span><span class="sxs-lookup"><span data-stu-id="87fbb-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="87fbb-108">Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla in bevis som är associerade med incidenterna så att du kan skapa en effektiv åtgärdsplan.</span><span class="sxs-lookup"><span data-stu-id="87fbb-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="87fbb-109">Undersöka en händelse</span><span class="sxs-lookup"><span data-stu-id="87fbb-109">Investigate an incident</span></span>

1. <span data-ttu-id="87fbb-110">Välj en incident från incidentkön.</span><span class="sxs-lookup"><span data-stu-id="87fbb-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="87fbb-111">En sidopanel öppnas och visar en förhandsgranskning av viktig information, till exempel status, allvarlighetsgrad, kategorier och berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="87fbb-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild av sidopanelen för incidenter](../../media/incident-side-panel.png)

2. <span data-ttu-id="87fbb-113">Välj **Sidan Öppna incident.**</span><span class="sxs-lookup"><span data-stu-id="87fbb-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="87fbb-114">Då öppnas incidentsidan där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).</span><span class="sxs-lookup"><span data-stu-id="87fbb-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="87fbb-115">Granska aviseringar, enheter, användare och andra enheter som är inblandade i händelsen.</span><span class="sxs-lookup"><span data-stu-id="87fbb-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="87fbb-116">Incidentöversikt</span><span class="sxs-lookup"><span data-stu-id="87fbb-116">Incident overview</span></span>

<span data-ttu-id="87fbb-117">Översiktssidan ger en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.</span><span class="sxs-lookup"><span data-stu-id="87fbb-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Bild av sidan med en översikt över incidenter](../../media/incidents-overview.png)

<span data-ttu-id="87fbb-119">Attackkategorierna ger dig en visuell och numerisk bild av hur avancerad attacken har fortskridt mot avvisningskedjan.</span><span class="sxs-lookup"><span data-stu-id="87fbb-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="87fbb-120">Precis som andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender i linje med [MITRE ATT&&trade; CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="87fbb-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="87fbb-121">I omfattningsavsnittet visas en lista över de mest påverkade tillgångarna som är en del av den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="87fbb-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="87fbb-122">Om det finns specifik information om den här tillgången, t.ex. risknivå, undersökningsprioritet och taggning av tillgångarna, visas detta även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="87fbb-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="87fbb-123">Tidslinjen för aviseringar ger en förhandstitt på den kronologiska ordningen som aviseringarna inträffade i, samt orsakerna till att dessa aviseringar är kopplade till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="87fbb-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="87fbb-124">Och sista - bevisavsnittet ger en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du direkt kan se om någon åtgärd behövs på din slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="87fbb-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="87fbb-125">Den här översikten kan hjälpa dig med den initiala triangeln av incidenten genom att ge information om de viktigaste egenskaperna för incidenten som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="87fbb-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="87fbb-126">Varningar</span><span class="sxs-lookup"><span data-stu-id="87fbb-126">Alerts</span></span>

<span data-ttu-id="87fbb-127">Du kan visa alla aviseringar som rör incidenten och annan information om dem, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365) och orsaken till att de länkades ihop.</span><span class="sxs-lookup"><span data-stu-id="87fbb-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Bild på sidan incidentaviseringar](../../media/incident-alerts.png)

<span data-ttu-id="87fbb-129">Som standard ordnas aviseringarna kronologiskt så att du först kan se hur attacken utspelas med tiden.</span><span class="sxs-lookup"><span data-stu-id="87fbb-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="87fbb-130">Om du klickar på varje avisering kommer du till den relevanta aviseringssidan där du kan göra en detaljerad undersökning av den aviseringen.</span><span class="sxs-lookup"><span data-stu-id="87fbb-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="87fbb-131">Enheter</span><span class="sxs-lookup"><span data-stu-id="87fbb-131">Devices</span></span>

<span data-ttu-id="87fbb-132">På fliken enheter visas alla enheter där aviseringar om händelsen visas.</span><span class="sxs-lookup"><span data-stu-id="87fbb-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="87fbb-133">Om du klickar på namnet på den dator där attacken utfördes kommer du till sidan Dator där du kan se aviseringar som utlösts för den och relaterade händelser för att underlätta undersökning.</span><span class="sxs-lookup"><span data-stu-id="87fbb-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Bild på fliken Datorer för ett incident](../../media/incident-machines.png)

<span data-ttu-id="87fbb-135">Om du väljer fliken Tidslinje kan du bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.</span><span class="sxs-lookup"><span data-stu-id="87fbb-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="87fbb-136">Användare</span><span class="sxs-lookup"><span data-stu-id="87fbb-136">Users</span></span>

<span data-ttu-id="87fbb-137">Se användare som har identifierats vara en del av eller relaterade till en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="87fbb-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="87fbb-138">Om du klickar på användarnamnet kommer du till sidan Molnappsäkerhet där ytterligare undersökning kan utföras.</span><span class="sxs-lookup"><span data-stu-id="87fbb-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Bild på fliken Användare för ett incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="87fbb-140">Postlådor</span><span class="sxs-lookup"><span data-stu-id="87fbb-140">Mailboxes</span></span>

<span data-ttu-id="87fbb-141">Undersök postlådor som har identifierats som en del av eller som är relaterade till en händelse.</span><span class="sxs-lookup"><span data-stu-id="87fbb-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="87fbb-142">För att det ska fungera ytterligare kan du välja den e-postrelaterade aviseringen och öppna Microsoft Defender för Office 365 där du kan vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="87fbb-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Bild av fliken Postlåda för ett incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="87fbb-144">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="87fbb-144">Investigations</span></span>

<span data-ttu-id="87fbb-145">Välj **Undersökningar** för att se alla automatiserade undersökningar som utlösts av varningar i den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="87fbb-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="87fbb-146">Undersökningarna utförs åtgärdsåtgärder eller väntar på analytikers godkännande av åtgärder, beroende på hur du konfigurerat dina automatiserade undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="87fbb-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Bild av fliken undersökningar för en incident](../../media/incident-investigations.png)

<span data-ttu-id="87fbb-148">Välj en undersökning för att navigera till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="87fbb-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="87fbb-149">Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.</span><span class="sxs-lookup"><span data-stu-id="87fbb-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="87fbb-150">Bevis</span><span class="sxs-lookup"><span data-stu-id="87fbb-150">Evidence</span></span>

<span data-ttu-id="87fbb-151">Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig autosvar samt information om viktiga filer, processer, tjänster, e-postmeddelanden med mera.</span><span class="sxs-lookup"><span data-stu-id="87fbb-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="87fbb-152">Det här hjälper snabbt till att identifiera och blockera potentiella hot i incidenten.</span><span class="sxs-lookup"><span data-stu-id="87fbb-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Bild av bevisfliken för en händelse](../../media/incident-evidence.png)

<span data-ttu-id="87fbb-154">Var och en av de analyserade enheterna markeras med en bedömning (skadlig, misstänkt, ren) samt en åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="87fbb-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="87fbb-155">På så sätt får du en bättre förståelse för åtgärdsstatusen för hela händelsen och vilka nästa steg du kan vidta för att åtgärda ytterligare.</span><span class="sxs-lookup"><span data-stu-id="87fbb-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="87fbb-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="87fbb-156">Related topics</span></span>

- [<span data-ttu-id="87fbb-157">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="87fbb-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="87fbb-158">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="87fbb-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="87fbb-159">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="87fbb-159">Manage incidents</span></span>](manage-incidents.md)

