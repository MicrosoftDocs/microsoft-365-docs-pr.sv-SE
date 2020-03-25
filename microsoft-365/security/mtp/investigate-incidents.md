---
title: Undersöka incidenter i Microsofts hotskydd
description: Analysera incidenter relaterade till enheter, användare och postlådor.
keywords: incident, incidenter, maskiner, enheter, användare, identiteter, e-post, e-post, brevlåda, undersökning, diagram, bevis
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928968"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="62c69-104">Undersöka incidenter i Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="62c69-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="62c69-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="62c69-105">**Applies to:**</span></span>

- <span data-ttu-id="62c69-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="62c69-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="62c69-107">Microsoft Threat Protection sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från alla dina enheter, användare och postlådor för att ge dig en omfattande titt på hela bredden av en attack.</span><span class="sxs-lookup"><span data-stu-id="62c69-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="62c69-108">Undersök aviseringar som påverkar ditt nätverk, förstå vad de betyder och samla bevis i samband med incidenter så att du kan utforma en effektiv reparationsplan.</span><span class="sxs-lookup"><span data-stu-id="62c69-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="62c69-109">Utreda en incident</span><span class="sxs-lookup"><span data-stu-id="62c69-109">Investigate an incident</span></span>

1. <span data-ttu-id="62c69-110">Välj en incident från incidentkön.</span><span class="sxs-lookup"><span data-stu-id="62c69-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="62c69-111">Detta öppnar en sidopanel och ger en förhandsgranskning av viktig information som status, allvarlighetsgrad, kategorier och påverkade entiteter.</span><span class="sxs-lookup"><span data-stu-id="62c69-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild av sidopanelen för incidenten](../../media/incident-side-panel.png)

2. <span data-ttu-id="62c69-113">Välj **Öppna incidentsida**.</span><span class="sxs-lookup"><span data-stu-id="62c69-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="62c69-114">Då öppnas incidentsidan där du hittar mer information om incidentinformation, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).</span><span class="sxs-lookup"><span data-stu-id="62c69-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="62c69-115">Granska aviseringar, enheter, användare, andra enheter som är inblandade i incidenten.</span><span class="sxs-lookup"><span data-stu-id="62c69-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="62c69-116">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="62c69-116">Incident overview</span></span>

<span data-ttu-id="62c69-117">Översiktssidan ger dig en ögonblicksbild blick i de översta sakerna att märka om händelsen.</span><span class="sxs-lookup"><span data-stu-id="62c69-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Bild av översiktssidan för incidenter](../../media/incidents-overview.png)

<span data-ttu-id="62c69-119">Attackkategorierna ger dig visuell och numerisk bild av hur avancerad attacken har utvecklats mot dödskedjan.</span><span class="sxs-lookup"><span data-stu-id="62c69-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="62c69-120">Precis som med andra Microsoft-säkerhetsprodukter är Microsoft Threat Protection anpassat till [MITRE ATT-&&trade; CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="62c69-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="62c69-121">Avsnittet Omfång ger dig en lista över de mest påverkade tillgångarna som ingår i den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="62c69-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="62c69-122">Om det finns specifik information om denna tillgång, såsom risknivå, undersökningsprioritet samt eventuell märkning på tillgångarna kommer detta också att dyka upp i detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="62c69-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="62c69-123">Tidslinjen för aviseringar ger en smygtitt på den kronologiska ordning i vilken aviseringarna inträffade, liksom orsakerna till att dessa aviseringar kopplade till den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="62c69-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="62c69-124">Och sist - bevisavsnittet ger en sammanfattning av hur många olika artefakter som ingick i incidenten och deras reparationsstatus, så att du omedelbart kan identifiera om någon åtgärd behövs på din sida.</span><span class="sxs-lookup"><span data-stu-id="62c69-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="62c69-125">Denna översikt kan hjälpa till i den första triage av händelsen genom att ge insikt i de bästa egenskaperna hos händelsen som du bör vara medveten om.</span><span class="sxs-lookup"><span data-stu-id="62c69-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="62c69-126">Varningar</span><span class="sxs-lookup"><span data-stu-id="62c69-126">Alerts</span></span>

<span data-ttu-id="62c69-127">Du kan visa alla aviseringar som är relaterade till incidenten och annan information om dem, till exempel allvarlighetsgrad, entiteter som var inblandade i aviseringen, källan till aviseringarna (Azure ATP, Microsoft Defender ATP , Office 365 ATP) och anledningen till att de var sammankopplade.</span><span class="sxs-lookup"><span data-stu-id="62c69-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span>

![Bild på sidan incidentvarningar](../../media/incident-alerts.png)

<span data-ttu-id="62c69-129">Som standard ordnas aviseringarna kronologiskt så att du först kan se hur attacken utspelade sig över tid.</span><span class="sxs-lookup"><span data-stu-id="62c69-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="62c69-130">Om du klickar på varje avisering leder du till den relevanta aviseringssidan där du kan göra en fördjupad undersökning av den aviseringen.</span><span class="sxs-lookup"><span data-stu-id="62c69-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="62c69-131">Enheter</span><span class="sxs-lookup"><span data-stu-id="62c69-131">Devices</span></span>

<span data-ttu-id="62c69-132">På fliken Enheter visas alla enheter där aviseringar relaterade till incidenten visas.</span><span class="sxs-lookup"><span data-stu-id="62c69-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="62c69-133">Om du klickar på namnet på den dator där attacken utfördes navigerar du till dess maskinsida där du kan se aviseringar som utlöstes på den och relaterade händelser som tillhandahålls för att underlätta undersökningen.</span><span class="sxs-lookup"><span data-stu-id="62c69-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Bild av datorer fliken för en incident](../../media/incident-machines.png)

<span data-ttu-id="62c69-135">Om du väljer fliken Tidslinje kan du bläddra igenom maskinens tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, varvat med aviseringarna upp.</span><span class="sxs-lookup"><span data-stu-id="62c69-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="62c69-136">Användare</span><span class="sxs-lookup"><span data-stu-id="62c69-136">Users</span></span>

<span data-ttu-id="62c69-137">Se användare som har identifierats vara en del av eller relaterade till en viss incident.</span><span class="sxs-lookup"><span data-stu-id="62c69-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="62c69-138">Om du klickar på användarnamnet navigeras du till användarens Cloud App Security-sida där ytterligare undersökningar kan utföras.</span><span class="sxs-lookup"><span data-stu-id="62c69-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Bild på fliken användare i en incident](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="62c69-140">Postlådor</span><span class="sxs-lookup"><span data-stu-id="62c69-140">Mailboxes</span></span>

<span data-ttu-id="62c69-141">Undersök postlådor som har identifierats för att vara en del av eller relaterade till en incident.</span><span class="sxs-lookup"><span data-stu-id="62c69-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="62c69-142">Om du vill utföra ytterligare utredningsarbete öppnas Office 365 Advanced Threat Protection där du kan vidta åtgärder för att upptäcka e-postrelaterade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="62c69-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>

![Bild på fliken postlåda för en incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="62c69-144">Utredningar</span><span class="sxs-lookup"><span data-stu-id="62c69-144">Investigations</span></span>

<span data-ttu-id="62c69-145">Välj **Undersökningar om** du vill se alla automatiserade undersökningar som utlöses av varningar i den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="62c69-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="62c69-146">Undersökningarna utför reparationsåtgärder eller väntar på analytikergodkännande av åtgärder, beroende på hur du konfigurerade dina automatiska undersökningar för att köras i Microsoft Defender ATP och Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="62c69-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![Bild av utredningar fliken av en incident](../../media/incident-investigations.png)

<span data-ttu-id="62c69-148">Välj en undersökning för att navigera till sidan Undersökningsinformation för att få fullständig information om undersöknings- och reparationsstatus.</span><span class="sxs-lookup"><span data-stu-id="62c69-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="62c69-149">Om det finns några åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av incidentens reparation.</span><span class="sxs-lookup"><span data-stu-id="62c69-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="62c69-150">Bevis</span><span class="sxs-lookup"><span data-stu-id="62c69-150">Evidence</span></span>

<span data-ttu-id="62c69-151">Microsoft Threat Protection undersöker automatiskt alla incidenters händelser som stöds och misstänkta entiteter i aviseringarna, vilket ger dig automatisk respons och information om viktiga filer, processer, tjänster, e-postmeddelanden med mera.</span><span class="sxs-lookup"><span data-stu-id="62c69-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="62c69-152">Detta hjälper till att snabbt upptäcka och blockera potentiella hot i incidenten.</span><span class="sxs-lookup"><span data-stu-id="62c69-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Bild på fliken bevis för en incident](../../media/incident-evidence.png)

<span data-ttu-id="62c69-154">Var och en av de analyserade entiteterna markeras med en dom (Skadlig, Misstänkt, Ren) samt en reparationsstatus.</span><span class="sxs-lookup"><span data-stu-id="62c69-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="62c69-155">Detta hjälper dig att förstå saneringsstatus för hela incidenten och vilka är de nästa steg som kan vidtas för att ytterligare åtgärda.</span><span class="sxs-lookup"><span data-stu-id="62c69-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="62c69-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="62c69-156">Related topics</span></span>

- [<span data-ttu-id="62c69-157">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="62c69-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="62c69-158">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="62c69-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="62c69-159">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="62c69-159">Manage incidents</span></span>](manage-incidents.md)

