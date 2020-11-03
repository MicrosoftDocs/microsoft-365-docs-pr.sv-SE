---
title: Undersök incidenter i Microsoft 365 Defender
description: Analysera händelser relaterade till enheter, användare och post lådor.
keywords: incident, händelser, datorer, enheter, användare, identiteter, e-post, e-post, brev låda, undersökning, Graf, bevis
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846754"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="dc7a6-104">Undersök incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc7a6-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dc7a6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="dc7a6-105">**Applies to:**</span></span>

- <span data-ttu-id="dc7a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc7a6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dc7a6-107">Microsoft 365 Defender aggregerar alla relaterade aviseringar, till gångar, undersökningar och fakta från enheter, användare och post lådor för att ge dig en omfattande titt på hela bredden på en attack.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="dc7a6-108">Undersök vilka aviseringar som påverkar ditt nätverk, förstå vad de betyder och samla in bevis som är kopplade till incidenterna så att du kan utforma en effektiv reparations plan.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="dc7a6-109">Undersök en olycka</span><span class="sxs-lookup"><span data-stu-id="dc7a6-109">Investigate an incident</span></span>

1. <span data-ttu-id="dc7a6-110">Välj en incident från incident kön.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="dc7a6-111">En sido panel öppnas och en förhands granskning av viktig information som status, allvarlighets grad, kategorier och berörda enheter visas.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild av panelen tillbud](../../media/incident-side-panel.png)

2. <span data-ttu-id="dc7a6-113">Välj **Open incident-sida**.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="dc7a6-114">Då öppnas sidan incident där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, notifieringar, enheter, användare, undersökningar, bevis).</span><span class="sxs-lookup"><span data-stu-id="dc7a6-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="dc7a6-115">Granska aviseringar, enheter, användare, andra enheter inblandade i incidenten.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="dc7a6-116">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="dc7a6-116">Incident overview</span></span>

<span data-ttu-id="dc7a6-117">Med översikts sidan kan du snabbt och enkelt se en ögonblicks bild.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Bild av översikts sidan för incidenter](../../media/incidents-overview.png)

<span data-ttu-id="dc7a6-119">I angrepps kategorierna får du en visuell och numerisk vy över hur avancerade angreppen har gått mot Kill-kedjan.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="dc7a6-120">Som med andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender till [&&trade; Mitre](https://attack.mitre.org/) as-ramverket.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="dc7a6-121">I avsnittet omfattning får du en lista över de mest berörda till gångarna som är en del av den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="dc7a6-122">Om det finns specifik information om den här till gången, till exempel risk nivå, undersöknings prioritet och eventuella taggning på till gångar, visas även i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="dc7a6-123">Tids linjen för påminnelser ger en förhandstitt på den kronologiska ordning i vilken aviseringarna inträffade, samt orsakerna till att dessa varningar är länkade till denna incident.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="dc7a6-124">Och sist-beviset visar en sammanfattning av hur många olika artefakter som ingår i incidenten och deras reparations status, så att du omedelbart kan avgöra om en åtgärd krävs för ditt slut.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="dc7a6-125">Denna översikt kan hjälpa till med den inledande postsortering av incidenten genom att ge insyn i de viktigaste egenskaperna hos den olycka som du bör vara medveten om.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="dc7a6-126">Varningar</span><span class="sxs-lookup"><span data-stu-id="dc7a6-126">Alerts</span></span>

<span data-ttu-id="dc7a6-127">Du kan visa alla aviseringar om felet och annan information om dem, till exempel allvarlighets grad, enheter som ingick i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slut punkt, Microsoft Defender för Office 365) och anledningen till att de sammanlänkade.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Bild av sidan incident aviseringar](../../media/incident-alerts.png)

<span data-ttu-id="dc7a6-129">Som standard ordnas aviseringarna kronologiskt, så att du kan se hur angreppet spelas upp med tiden.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="dc7a6-130">Om du klickar på varje varning kommer du till relevant aviserings sida där du kan genomföra en djupgående undersökning av den aviseringen.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="dc7a6-131">Anordningar</span><span class="sxs-lookup"><span data-stu-id="dc7a6-131">Devices</span></span>

<span data-ttu-id="dc7a6-132">På fliken enheter visas alla enheter där aviseringar som rör händelsen är synliga.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="dc7a6-133">Om du klickar på namnet på den dator där angreppet har gjorts navigerar du till dess dator sida där du kan se de meddelanden som utlöstes med den och relaterade händelser för att under lätta undersökningen.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Fliken dator med en olycka](../../media/incident-machines.png)

<span data-ttu-id="dc7a6-135">Om du väljer fliken tids linje kan du bläddra igenom datorns tids linje och Visa alla händelser och funktioner som observerats på datorn i kronologisk ordning, direkt med aviseringar.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="dc7a6-136">Användare</span><span class="sxs-lookup"><span data-stu-id="dc7a6-136">Users</span></span>

<span data-ttu-id="dc7a6-137">Se vilka användare som har identifierats som en del av eller är relaterade till en viss olycka.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="dc7a6-138">Om du klickar på användar namnet navigerar du till användarens moln program säkerhets sida där ytterligare undersökningar kan genomföras.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Bild av fliken användare i en händelse](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="dc7a6-140">Post lådor</span><span class="sxs-lookup"><span data-stu-id="dc7a6-140">Mailboxes</span></span>

<span data-ttu-id="dc7a6-141">Undersök brev lådor som har identifierats som en del av eller är relaterade till en olycka.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="dc7a6-142">Om du vill göra ytterligare utrednings arbete och välja den e-postrelaterade varningen öppnas Microsoft Defender för Office 365 där du kan utföra reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Bild av fliken post låda med en olycka](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="dc7a6-144">Utredningar</span><span class="sxs-lookup"><span data-stu-id="dc7a6-144">Investigations</span></span>

<span data-ttu-id="dc7a6-145">Välj **undersökningar** för att se alla automatiserade utredningar som utlöstes av notifieringar under den här incidenten.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="dc7a6-146">Undersökningen utför reparations åtgärder eller väntar på att godkänna godkännande av åtgärder, beroende på hur du har konfigurerat dina automatiserade utredningar att köra i Microsoft Defender för slut punkt och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Bild av fliken undersökningar under en olycka](../../media/incident-investigations.png)

<span data-ttu-id="dc7a6-148">Välj en undersökning för att gå till sidan med gransknings informationen för att få fullständig information om undersökningen och reparations status.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="dc7a6-149">Om det finns några åtgärder som väntar på godkännande som en del av undersökningen kommer de att visas på fliken väntande åtgärder. Vidta en åtgärd som en del av incident åtgärden.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="dc7a6-150">Läggs</span><span class="sxs-lookup"><span data-stu-id="dc7a6-150">Evidence</span></span>

<span data-ttu-id="dc7a6-151">I Microsoft 365 Defender kontrol leras automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig svar och information om viktiga filer, processer, tjänster, e-postmeddelanden och annat.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="dc7a6-152">Det gör det enkelt att upptäcka och blockera potentiella hot i olyckan.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Bild av fliken bevis för en olycka](../../media/incident-evidence.png)

<span data-ttu-id="dc7a6-154">Alla analyserade enheter markeras med en Verdict (skadlig, misstänkt, ren) och en reparations status.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="dc7a6-155">Det här hjälper dig att förstå reparations status för hela incidenten och vilka som är nästa steg som kan åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc7a6-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="dc7a6-156">Related topics</span></span>

- [<span data-ttu-id="dc7a6-157">Incident översikt</span><span class="sxs-lookup"><span data-stu-id="dc7a6-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="dc7a6-158">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="dc7a6-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="dc7a6-159">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="dc7a6-159">Manage incidents</span></span>](manage-incidents.md)

