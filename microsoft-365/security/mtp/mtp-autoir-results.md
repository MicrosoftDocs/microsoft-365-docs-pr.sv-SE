---
title: Information och resultat från en automatiserad undersökning
description: Du kan visa resultaten och viktiga resultat under och efter en automatiserad undersökning
keywords: automatisera, undersöka, resultat, analysera, information, åtgärd, autoair
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930372"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="22252-104">Information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="22252-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22252-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="22252-105">**Applies to:**</span></span>
- <span data-ttu-id="22252-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22252-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="22252-107">När en automatiserad undersökning görs i Microsoft 365 Defender finns det information om undersökningen tillgänglig under och efter den automatiska undersökningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="22252-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="22252-108">Om du har den [behörighet som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du visa den informationen i en vy med undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="22252-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="22252-109">I vyn med undersökningsinformation får du aktuell status och möjlighet att godkänna eventuella väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="22252-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="22252-111">Öppna vyn med undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="22252-111">Open the investigation details view</span></span>

<span data-ttu-id="22252-112">Du kan öppna vyn med undersökningsinformation med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="22252-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="22252-113">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="22252-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="22252-114">Välj en undersökning från sidan incidentinformation</span><span class="sxs-lookup"><span data-stu-id="22252-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="22252-115">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="22252-115">Select an item in the Action center</span></span>

<span data-ttu-id="22252-116">Använd Åtgärdscenter för att visa åtgärder som  antingen väntar på godkännande (på fliken Väntande) eller redan har godkänts (på **fliken** Historik).</span><span class="sxs-lookup"><span data-stu-id="22252-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="22252-117">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="22252-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="22252-118">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="22252-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="22252-119">Välj ett **objekt på** fliken **Väntande** eller Historik.</span><span class="sxs-lookup"><span data-stu-id="22252-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="22252-120">Om du har den [behörighet som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="22252-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="22252-121">Öppna en undersökning från sidan incidentinformation</span><span class="sxs-lookup"><span data-stu-id="22252-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="22252-122">Använd en sida med incidentinformation om du vill visa detaljerad information om en händelse, inklusive aviseringar som utlöstes information om enheter, användarkonton eller postlådor som påverkas.</span><span class="sxs-lookup"><span data-stu-id="22252-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="22252-123">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="22252-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="22252-124">Välj Incidenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="22252-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="22252-125">Markera ett objekt i listan för att öppna vyn incidentinformation.</span><span class="sxs-lookup"><span data-stu-id="22252-125">Select an item in the list to open the incident details view.</span></span><br/>![Incidentinformation](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="22252-127">Välj **en undersökning** i listan på fliken Undersökningar.</span><span class="sxs-lookup"><span data-stu-id="22252-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="22252-128">Undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="22252-128">Investigation details</span></span>

<span data-ttu-id="22252-129">Använd vyn med undersökningsinformation för att se tidigare, aktuell och väntande aktivitet som hör till en undersökning.</span><span class="sxs-lookup"><span data-stu-id="22252-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="22252-130">Vyn med undersökningsinformation liknar följande bild:</span><span class="sxs-lookup"><span data-stu-id="22252-130">The investigation details view resembles the following image:</span></span>

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

<span data-ttu-id="22252-132">I vyn Undersökningsinformation kan du se information om **åtgärdsflikarna** **Undersökning,**  **Varningar,** **Enheter,** Identiteter,  **Enheter,** Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="22252-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="22252-133">Tabb</span><span class="sxs-lookup"><span data-stu-id="22252-133">Tab</span></span> | <span data-ttu-id="22252-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="22252-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="22252-135">**Undersökningsdiagram**</span><span class="sxs-lookup"><span data-stu-id="22252-135">**Investigation graph**</span></span>   | <span data-ttu-id="22252-136">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="22252-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="22252-137">Visar enheter och visar hot som påträffas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="22252-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="22252-138">Du kan klicka på ett objekt i diagrammet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="22252-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="22252-139">Om du till exempel klickar **på ikonen Hittade** hot kommer du till fliken **Viktiga** resultat.</span><span class="sxs-lookup"><span data-stu-id="22252-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="22252-140">**Varningar**</span><span class="sxs-lookup"><span data-stu-id="22252-140">**Alerts**</span></span>    | <span data-ttu-id="22252-141">Listar aviseringar som är associerade med undersökningen.</span><span class="sxs-lookup"><span data-stu-id="22252-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="22252-142">Varningar kan komma från skyddsfunktioner för hot på en användares dator, i Office-appar, Cloud App Security och andra Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="22252-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="22252-143">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="22252-143">**Devices**</span></span> | <span data-ttu-id="22252-144">Visar datorer som ingår i undersökningen tillsammans med åtgärdsnivån.</span><span class="sxs-lookup"><span data-stu-id="22252-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="22252-145">**Viktiga resultat**</span><span class="sxs-lookup"><span data-stu-id="22252-145">**Key findings**</span></span>  | <span data-ttu-id="22252-146">Listor med resultat från undersökningen tillsammans med status och åtgärder som vidtas eller väntar.</span><span class="sxs-lookup"><span data-stu-id="22252-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="22252-147">Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="22252-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="22252-148">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="22252-148">**Entities**</span></span>  | <span data-ttu-id="22252-149">Visar användaraktiviteter, filer, processer, tjänster, drivrutiner, IP-adresser och beständighetsmetoder associerade med undersökningen, tillsammans med status och åtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="22252-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="22252-150">**Logg**</span><span class="sxs-lookup"><span data-stu-id="22252-150">**Log**</span></span>    | <span data-ttu-id="22252-151">Ger en detaljerad bild av alla steg som vidtas under undersökningen, tillsammans med status.</span><span class="sxs-lookup"><span data-stu-id="22252-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="22252-152">**Väntande åtgärder**</span><span class="sxs-lookup"><span data-stu-id="22252-152">**Pending actions**</span></span> | <span data-ttu-id="22252-153">En lista med objekt som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="22252-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="22252-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="22252-154">Next steps</span></span>

- [<span data-ttu-id="22252-155">Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="22252-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="22252-156">Granska åtgärder</span><span class="sxs-lookup"><span data-stu-id="22252-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
