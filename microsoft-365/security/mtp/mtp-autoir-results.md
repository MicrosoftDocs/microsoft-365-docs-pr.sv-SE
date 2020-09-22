---
title: Uppgifter och resultat från en automatiserad undersökning
description: Under och efter en automatiserad undersökning kan du Visa resultat och nyckeltal
keywords: automatiserad, undersökning, resultat, analysera, uppgifter, reparation, autoair
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
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 6d3ffd9f9e28bc190093c19ce9013f9aca12d60e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198867"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="5eb67-104">Uppgifter och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="5eb67-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5eb67-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5eb67-105">**Applies to:**</span></span>
- <span data-ttu-id="5eb67-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="5eb67-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5eb67-107">När en automatisk undersökning görs med Microsoft Threat Protection är information om den undersökningen tillgängliga under och efter den automatiska gransknings processen.</span><span class="sxs-lookup"><span data-stu-id="5eb67-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="5eb67-108">Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du Visa den informationen i vyn granska information.</span><span class="sxs-lookup"><span data-stu-id="5eb67-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="5eb67-109">I vyn undersöknings Detaljer får du uppdaterade status och möjlighet att godkänna väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5eb67-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="5eb67-111">Öppna vyn gransknings Detaljer</span><span class="sxs-lookup"><span data-stu-id="5eb67-111">Open the investigation details view</span></span>

<span data-ttu-id="5eb67-112">Du kan öppna vyn gransknings Detaljer på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="5eb67-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="5eb67-113">Markera ett objekt i åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="5eb67-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="5eb67-114">Välj en undersökning på sidan information om en händelse</span><span class="sxs-lookup"><span data-stu-id="5eb67-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="5eb67-115">Markera ett objekt i åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="5eb67-115">Select an item in the Action center</span></span>

<span data-ttu-id="5eb67-116">Använd åtgärds centret för att Visa åtgärder som antingen väntar på godkännande (på fliken **förestående** ) eller som redan har godkänts (på fliken **Historik** ).</span><span class="sxs-lookup"><span data-stu-id="5eb67-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="5eb67-117">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="5eb67-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="5eb67-118">I navigerings fönstret väljer du **Åtgärds Center**.</span><span class="sxs-lookup"><span data-stu-id="5eb67-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="5eb67-119">På fliken **förestående** eller **Historik** väljer du ett objekt.</span><span class="sxs-lookup"><span data-stu-id="5eb67-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="5eb67-120">Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5eb67-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="5eb67-121">Öppna en undersökning från sidan information om en händelse</span><span class="sxs-lookup"><span data-stu-id="5eb67-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="5eb67-122">Använd en informations sida för att visa detaljerad information om en olycka, inklusive aviseringar som utlöste information om eventuella berörda enheter, användar konton eller post lådor.</span><span class="sxs-lookup"><span data-stu-id="5eb67-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="5eb67-123">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="5eb67-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="5eb67-124">Välj **incidenter**i navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="5eb67-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="5eb67-125">Välj ett objekt i listan för att öppna vyn incident information.</span><span class="sxs-lookup"><span data-stu-id="5eb67-125">Select an item in the list to open the incident details view.</span></span><br/>![Incident uppgifter](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="5eb67-127">Välj en undersökning i listan på fliken **undersökningar** .</span><span class="sxs-lookup"><span data-stu-id="5eb67-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="5eb67-128">Gransknings uppgifter</span><span class="sxs-lookup"><span data-stu-id="5eb67-128">Investigation details</span></span>

<span data-ttu-id="5eb67-129">Använd vyn granska information om du vill visa tidigare, nuvarande och väntande aktiviteter för en undersökning.</span><span class="sxs-lookup"><span data-stu-id="5eb67-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="5eb67-130">Vyn gransknings Detaljer ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="5eb67-130">The investigation details view resembles the following image:</span></span>

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

<span data-ttu-id="5eb67-132">I vyn undersöknings Detaljer kan du se information om **undersökningen**, **aviseringar**, **enheter**, **identiteter**, **viktiga resultat**, **entiteter**, **loggning**och **väntande åtgärder** , som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="5eb67-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="5eb67-133">Fliken</span><span class="sxs-lookup"><span data-stu-id="5eb67-133">Tab</span></span>    |<span data-ttu-id="5eb67-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5eb67-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="5eb67-135">Undersökning</span><span class="sxs-lookup"><span data-stu-id="5eb67-135">Investigation graph</span></span>    |<span data-ttu-id="5eb67-136">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="5eb67-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="5eb67-137">Beskriver enheter och visar en lista med hot och varningar och om åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="5eb67-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="5eb67-138">Du kan klicka på ett objekt i diagrammet för att visa mer information.</span><span class="sxs-lookup"><span data-stu-id="5eb67-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="5eb67-139">Om du till exempel klickar på ikonen **upptäckta hot** tar du till fliken **viktiga resultat** .</span><span class="sxs-lookup"><span data-stu-id="5eb67-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="5eb67-140">Varningar</span><span class="sxs-lookup"><span data-stu-id="5eb67-140">Alerts</span></span> |<span data-ttu-id="5eb67-141">Visar en lista över aviseringar som är associerade med undersökningen.</span><span class="sxs-lookup"><span data-stu-id="5eb67-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="5eb67-142">Aviseringar kan komma från hot Protection-funktioner på en användares dator, i Office-appar, Cloud App-säkerhet och andra Microsoft 365 Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="5eb67-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="5eb67-143">Anordningar</span><span class="sxs-lookup"><span data-stu-id="5eb67-143">Devices</span></span>|<span data-ttu-id="5eb67-144">Visar en lista med maskiner som ingår i undersökningen tillsammans med reparations nivå.</span><span class="sxs-lookup"><span data-stu-id="5eb67-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="5eb67-145">Nyckeltal</span><span class="sxs-lookup"><span data-stu-id="5eb67-145">Key findings</span></span>   |<span data-ttu-id="5eb67-146">Visar resultaten från undersökningen tillsammans med status och åtgärder som utförs eller väntar.</span><span class="sxs-lookup"><span data-stu-id="5eb67-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="5eb67-147">Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="5eb67-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="5eb67-148">Posterna</span><span class="sxs-lookup"><span data-stu-id="5eb67-148">Entities</span></span>   |<span data-ttu-id="5eb67-149">Visar en lista över användar aktiviteter, filer, processer, tjänster, driv rutiner, IP-adresser och beständiga metoder som är förknippade med undersökningen samt status och åtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="5eb67-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="5eb67-150">Logga in</span><span class="sxs-lookup"><span data-stu-id="5eb67-150">Log</span></span>    |<span data-ttu-id="5eb67-151">Visar en detaljerad vy av alla steg som görs under undersökningen, tillsammans med status.</span><span class="sxs-lookup"><span data-stu-id="5eb67-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="5eb67-152">Väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="5eb67-152">Pending actions</span></span>    |<span data-ttu-id="5eb67-153">Visar de objekt som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="5eb67-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="5eb67-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5eb67-154">Next steps</span></span>

- [<span data-ttu-id="5eb67-155">Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="5eb67-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

