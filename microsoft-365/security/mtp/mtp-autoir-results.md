---
title: Detaljer och resultat av en automatiserad undersökning
description: Under och efter en automatiserad undersökning kan du visa resultat och viktiga resultat
keywords: automatiserad, undersökning, resultat, analysera, detaljer, sanering, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 6b3bc068e5da99e02a64463891e32d137c448d64
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809704"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="c8762-104">Detaljer och resultat av en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="c8762-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="c8762-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c8762-105">**Applies to:**</span></span>
- <span data-ttu-id="c8762-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="c8762-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c8762-107">När en automatiserad undersökning inträffar i Microsoft Threat Protection finns information om den undersökningen tillgänglig under och efter den automatiska granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="c8762-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="c8762-108">Om du har [de behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du visa dessa uppgifter i en undersökningsinformationsvy.</span><span class="sxs-lookup"><span data-stu-id="c8762-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="c8762-109">Vyn Undersökningsinformation ger dig aktuell status och möjlighet att godkänna väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c8762-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detaljer om undersökningen](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="c8762-111">Öppna vyn För undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="c8762-111">Open the investigation details view</span></span>

<span data-ttu-id="c8762-112">Du kan öppna vyn undersökningsinformation med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="c8762-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="c8762-113">Markera ett objekt i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="c8762-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="c8762-114">Välj en undersökning från en incidentinformationssida</span><span class="sxs-lookup"><span data-stu-id="c8762-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="c8762-115">Markera ett objekt i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="c8762-115">Select an item in the Action center</span></span>

<span data-ttu-id="c8762-116">Använd åtgärdscentret för att visa åtgärder som antingen väntar på godkännande (på fliken **Väntande)** eller som redan har godkänts (på fliken **Historik).**</span><span class="sxs-lookup"><span data-stu-id="c8762-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="c8762-117">Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in.</span><span class="sxs-lookup"><span data-stu-id="c8762-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="c8762-118">Välj **Åtgärdscenter**i navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="c8762-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="c8762-119">Markera ett objekt på fliken **Väntande** eller **Historik.**</span><span class="sxs-lookup"><span data-stu-id="c8762-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="c8762-120">Om du har [de behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c8762-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="c8762-121">Öppna en utredning från en incidentinformationssida</span><span class="sxs-lookup"><span data-stu-id="c8762-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="c8762-122">Använd en incidentinformationssida för att visa detaljerad information om en incident, inklusive aviseringar som har utlösts information om alla berörda enheter, användarkonton eller postlådor.</span><span class="sxs-lookup"><span data-stu-id="c8762-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="c8762-123">Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in.</span><span class="sxs-lookup"><span data-stu-id="c8762-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="c8762-124">Välj **Incidenter**i navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="c8762-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="c8762-125">Markera ett objekt i listan om du vill öppna incidentinformationsvyn.</span><span class="sxs-lookup"><span data-stu-id="c8762-125">Select an item in the list to open the incident details view.</span></span><br/>![Information om incidenter](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="c8762-127">Välj en undersökning i listan på fliken **Undersökningar.**</span><span class="sxs-lookup"><span data-stu-id="c8762-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="c8762-128">Detaljer om undersökningen</span><span class="sxs-lookup"><span data-stu-id="c8762-128">Investigation details</span></span>

<span data-ttu-id="c8762-129">Använd vyn undersökningsinformation för att se tidigare, aktuell och väntande aktivitet som hör till en undersökning.</span><span class="sxs-lookup"><span data-stu-id="c8762-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="c8762-130">Undersökningens informationsvy liknar följande bild:</span><span class="sxs-lookup"><span data-stu-id="c8762-130">The investigation details view resembles the following image:</span></span>

![Detaljer om undersökningen](../../media/mtp-air-investdetails.png)

<span data-ttu-id="c8762-132">I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, **Aviseringar**, **Enheter**, **Identiteter**, Nyckelresultat , **Entiteter,** **Logg**och **Väntande åtgärder** som beskrivs i följande tabell. **Key findings**</span><span class="sxs-lookup"><span data-stu-id="c8762-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="c8762-133">Tab</span><span class="sxs-lookup"><span data-stu-id="c8762-133">Tab</span></span>    |<span data-ttu-id="c8762-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8762-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="c8762-135">Undersökning diagram</span><span class="sxs-lookup"><span data-stu-id="c8762-135">Investigation graph</span></span>    |<span data-ttu-id="c8762-136">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="c8762-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="c8762-137">Visar entiteter och listar hot som hittats, tillsammans med aviseringar och om några åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="c8762-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="c8762-138">Du kan klicka på ett objekt i diagrammet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="c8762-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="c8762-139">Om du till exempel klickar på ikonen **Hot hittades** kommer du till fliken **Nyckelresultat.**</span><span class="sxs-lookup"><span data-stu-id="c8762-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="c8762-140">Varningar</span><span class="sxs-lookup"><span data-stu-id="c8762-140">Alerts</span></span> |<span data-ttu-id="c8762-141">Visar aviseringar som är associerade med undersökningen.</span><span class="sxs-lookup"><span data-stu-id="c8762-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="c8762-142">Aviseringar kan komma från hotskyddsfunktioner på en användares dator, i Office-appar, Cloud App Security och andra Microsoft 365 Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="c8762-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="c8762-143">Enheter</span><span class="sxs-lookup"><span data-stu-id="c8762-143">Devices</span></span>|<span data-ttu-id="c8762-144">Listar maskiner som ingår i undersökningen tillsammans med saneringsnivå.</span><span class="sxs-lookup"><span data-stu-id="c8762-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="c8762-145">Viktiga resultat</span><span class="sxs-lookup"><span data-stu-id="c8762-145">Key findings</span></span>   |<span data-ttu-id="c8762-146">Visar resultat från undersökningen tillsammans med status och åtgärder som vidtagits eller väntar.</span><span class="sxs-lookup"><span data-stu-id="c8762-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="c8762-147">Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="c8762-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="c8762-148">Enheter</span><span class="sxs-lookup"><span data-stu-id="c8762-148">Entities</span></span>   |<span data-ttu-id="c8762-149">Visar användaraktiviteter, filer, processer, tjänster, drivrutiner, IP-adresser och persistensmetoder som är associerade med undersökningen, tillsammans med status och åtgärder som vidtagits.</span><span class="sxs-lookup"><span data-stu-id="c8762-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="c8762-150">Logga in</span><span class="sxs-lookup"><span data-stu-id="c8762-150">Log</span></span>    |<span data-ttu-id="c8762-151">Ger en detaljerad översikt över alla steg som vidtagits under undersökningen, tillsammans med status.</span><span class="sxs-lookup"><span data-stu-id="c8762-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="c8762-152">Väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="c8762-152">Pending actions</span></span>    |<span data-ttu-id="c8762-153">Visar en lista över objekt som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="c8762-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="c8762-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c8762-154">Next steps</span></span>

- [<span data-ttu-id="c8762-155">Få en översikt över behörigheter för Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="c8762-155">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)

- [<span data-ttu-id="c8762-156">Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="c8762-156">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

