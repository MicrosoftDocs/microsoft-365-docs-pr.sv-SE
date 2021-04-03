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
ms.openlocfilehash: f6b085f200d3b0c71bb3608f8e5ba9ed85632676
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500330"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="470f6-104">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="470f6-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="470f6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="470f6-105">**Applies to:**</span></span>

- <span data-ttu-id="470f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="470f6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="470f6-107">Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från olika enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.</span><span class="sxs-lookup"><span data-stu-id="470f6-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="470f6-108">Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla bevis som är associerade med incidenterna så att du kan skapa en gällande åtgärdsplan.</span><span class="sxs-lookup"><span data-stu-id="470f6-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="470f6-109">Undersöka en händelse</span><span class="sxs-lookup"><span data-stu-id="470f6-109">Investigate an incident</span></span>

1. <span data-ttu-id="470f6-110">Välj en incident i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="470f6-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="470f6-111">En sidopanel öppnas och visar en förhandsgranskning av viktig information, till exempel status, allvarlighetsgrad, kategorier och berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="470f6-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild på sidopanelen för incidenter](../../media/incident-side-panel.png)

2. <span data-ttu-id="470f6-113">Välj **Öppna incidentsida**.</span><span class="sxs-lookup"><span data-stu-id="470f6-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="470f6-114">Då öppnas incidentsidan där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).</span><span class="sxs-lookup"><span data-stu-id="470f6-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="470f6-115">Granska aviseringar, enheter, användare och andra enheter som är inblandade i händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="470f6-116">Incidentöversikt</span><span class="sxs-lookup"><span data-stu-id="470f6-116">Incident overview</span></span>

<span data-ttu-id="470f6-117">På översiktssidan får du en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Bild på översiktssidan för incidenter](../../media/incidents-overview.png)

<span data-ttu-id="470f6-119">Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain.</span><span class="sxs-lookup"><span data-stu-id="470f6-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="470f6-120">Precis som andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender i linje med [MITRE ATT&&trade; CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="470f6-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="470f6-121">I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="470f6-122">Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="470f6-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="470f6-123">På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="470f6-124">Och sist – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du genast kan se om någon åtgärd behövs på din slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="470f6-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="470f6-125">Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge information om de viktigaste egenskaperna för incidenten som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="470f6-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="470f6-126">Varningar</span><span class="sxs-lookup"><span data-stu-id="470f6-126">Alerts</span></span>

<span data-ttu-id="470f6-127">Du kan visa alla aviseringar som rör händelsen och annan information om dem, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365) och orsaken till att de länkades ihop.</span><span class="sxs-lookup"><span data-stu-id="470f6-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Bild på sidan incidentaviseringar](../../media/incident-alerts.png)

<span data-ttu-id="470f6-129">Som standard sorteras aviseringarna kronologiskt så att du först kan se hur attacken utspelas med tiden.</span><span class="sxs-lookup"><span data-stu-id="470f6-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="470f6-130">Om du klickar på varje avisering kommer du till den relevanta aviseringssidan där du kan undersöka den aviseringen på djupet.</span><span class="sxs-lookup"><span data-stu-id="470f6-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="470f6-131">Lär dig hur du använder aviseringssidor och den enhetliga aviseringskön i [Undersöka aviseringar](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="470f6-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="470f6-132">Enheter</span><span class="sxs-lookup"><span data-stu-id="470f6-132">Devices</span></span>

<span data-ttu-id="470f6-133">På fliken Enheter visas alla enheter där aviseringar om händelsen visas.</span><span class="sxs-lookup"><span data-stu-id="470f6-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="470f6-134">Om du klickar på namnet på den dator där attacken utfördes navigeras du till sidan Dator där du kan se aviseringar som utlöstes på den och relaterade händelser för att underlätta undersökning.</span><span class="sxs-lookup"><span data-stu-id="470f6-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Bild på fliken datorer för ett incident](../../media/incident-machines.png)

<span data-ttu-id="470f6-136">Genom att välja fliken Tidslinje kan du bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.</span><span class="sxs-lookup"><span data-stu-id="470f6-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="470f6-137">Användare</span><span class="sxs-lookup"><span data-stu-id="470f6-137">Users</span></span>

<span data-ttu-id="470f6-138">Se användare som har identifierats vara en del av eller relaterade till en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="470f6-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="470f6-139">När du klickar på användarnamnet navigeras du till sidan Säkerhet i Molnappen där vidare undersökning kan genomföras.</span><span class="sxs-lookup"><span data-stu-id="470f6-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Bild på fliken Användare för ett incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="470f6-141">Postlådor</span><span class="sxs-lookup"><span data-stu-id="470f6-141">Mailboxes</span></span>

<span data-ttu-id="470f6-142">Undersök postlådor som har identifierats som en del av eller relaterade till ett problem.</span><span class="sxs-lookup"><span data-stu-id="470f6-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="470f6-143">Om du vill utföra ytterligare åtgärder kan du välja den e-postrelaterade aviseringen för att öppna Microsoft Defender för Office 365, där du kan vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="470f6-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Bild av postlådefliken för ett incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="470f6-145">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="470f6-145">Investigations</span></span>

<span data-ttu-id="470f6-146">Välj **Undersökningar** om du vill se alla automatiserade undersökningar som utlösts av aviseringar om den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="470f6-147">Undersökningarna utför åtgärder eller väntar på analytikernas godkännande av åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="470f6-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Bild på fliken för undersökningar för ett incident](../../media/incident-investigations.png)

<span data-ttu-id="470f6-149">Välj en undersökning för att gå till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="470f6-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="470f6-150">Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.</span><span class="sxs-lookup"><span data-stu-id="470f6-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="470f6-151">Bevis</span><span class="sxs-lookup"><span data-stu-id="470f6-151">Evidence</span></span>

<span data-ttu-id="470f6-152">Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga filer, processer, tjänster, e-postmeddelanden med mera.</span><span class="sxs-lookup"><span data-stu-id="470f6-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="470f6-153">Det här hjälper dig att snabbt identifiera och blockera potentiella hot i händelsen.</span><span class="sxs-lookup"><span data-stu-id="470f6-153">This helps quickly detect and block potential threats in the incident.</span></span>

![Bild av bevisfliken för en händelse](../../media/incident-evidence.png)

<span data-ttu-id="470f6-155">Var och en av de analyserade enheterna markeras med en bedömning (skadlig, misstänkt, ren) samt en åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="470f6-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="470f6-156">På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som är nästa steg som kan åtgärdas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="470f6-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="470f6-157">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="470f6-157">Related topics</span></span>

- [<span data-ttu-id="470f6-158">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="470f6-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="470f6-159">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="470f6-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="470f6-160">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="470f6-160">Manage incidents</span></span>](manage-incidents.md)

