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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 39f6be70ad7a611f9919bb0529e8c8ed7f9dc339
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683366"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="93e13-104">Uppgifter och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="93e13-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93e13-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="93e13-105">**Applies to:**</span></span>
- <span data-ttu-id="93e13-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93e13-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="93e13-107">När en automatisk undersökning sker i Microsoft 365 Defender är det möjligt att få information om den undersökningen och efter den automatiska gransknings processen.</span><span class="sxs-lookup"><span data-stu-id="93e13-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="93e13-108">Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du Visa den informationen i vyn granska information.</span><span class="sxs-lookup"><span data-stu-id="93e13-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="93e13-109">I vyn undersöknings Detaljer får du uppdaterade status och möjlighet att godkänna väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="93e13-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="93e13-111">Öppna vyn gransknings Detaljer</span><span class="sxs-lookup"><span data-stu-id="93e13-111">Open the investigation details view</span></span>

<span data-ttu-id="93e13-112">Du kan öppna vyn gransknings Detaljer på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="93e13-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="93e13-113">Markera ett objekt i åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="93e13-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="93e13-114">Välj en undersökning på sidan information om en händelse</span><span class="sxs-lookup"><span data-stu-id="93e13-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="93e13-115">Markera ett objekt i åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="93e13-115">Select an item in the Action center</span></span>

<span data-ttu-id="93e13-116">Använd åtgärds centret för att Visa åtgärder som antingen väntar på godkännande (på fliken **förestående** ) eller som redan har godkänts (på fliken **Historik** ).</span><span class="sxs-lookup"><span data-stu-id="93e13-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="93e13-117">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="93e13-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="93e13-118">I navigerings fönstret väljer du **Åtgärds Center**.</span><span class="sxs-lookup"><span data-stu-id="93e13-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="93e13-119">På fliken **förestående** eller **Historik** väljer du ett objekt.</span><span class="sxs-lookup"><span data-stu-id="93e13-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="93e13-120">Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="93e13-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="93e13-121">Öppna en undersökning från sidan information om en händelse</span><span class="sxs-lookup"><span data-stu-id="93e13-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="93e13-122">Använd en informations sida för att visa detaljerad information om en olycka, inklusive aviseringar som utlöste information om eventuella berörda enheter, användar konton eller post lådor.</span><span class="sxs-lookup"><span data-stu-id="93e13-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="93e13-123">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="93e13-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="93e13-124">Välj **incidenter** i navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="93e13-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="93e13-125">Välj ett objekt i listan för att öppna vyn incident information.</span><span class="sxs-lookup"><span data-stu-id="93e13-125">Select an item in the list to open the incident details view.</span></span><br/>![Incident uppgifter](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="93e13-127">Välj en undersökning i listan på fliken **undersökningar** .</span><span class="sxs-lookup"><span data-stu-id="93e13-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="93e13-128">Gransknings uppgifter</span><span class="sxs-lookup"><span data-stu-id="93e13-128">Investigation details</span></span>

<span data-ttu-id="93e13-129">Använd vyn granska information om du vill visa tidigare, nuvarande och väntande aktiviteter för en undersökning.</span><span class="sxs-lookup"><span data-stu-id="93e13-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="93e13-130">Vyn gransknings Detaljer ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="93e13-130">The investigation details view resembles the following image:</span></span>

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

<span data-ttu-id="93e13-132">I vyn undersöknings Detaljer kan du se information om **undersökningen**, **aviseringar**, **enheter**, **identiteter**, **viktiga resultat**, **entiteter**, **loggning** och **väntande åtgärder** , som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="93e13-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="93e13-133">Fliken</span><span class="sxs-lookup"><span data-stu-id="93e13-133">Tab</span></span> | <span data-ttu-id="93e13-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="93e13-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="93e13-135">**Undersökning**</span><span class="sxs-lookup"><span data-stu-id="93e13-135">**Investigation graph**</span></span>   | <span data-ttu-id="93e13-136">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="93e13-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="93e13-137">Beskriver enheter och visar en lista med hot och varningar och om åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="93e13-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="93e13-138">Du kan klicka på ett objekt i diagrammet för att visa mer information.</span><span class="sxs-lookup"><span data-stu-id="93e13-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="93e13-139">Om du till exempel klickar på ikonen **upptäckta hot** tar du till fliken **viktiga resultat** .</span><span class="sxs-lookup"><span data-stu-id="93e13-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="93e13-140">**Varningar**</span><span class="sxs-lookup"><span data-stu-id="93e13-140">**Alerts**</span></span>    | <span data-ttu-id="93e13-141">Visar en lista över aviseringar som är associerade med undersökningen.</span><span class="sxs-lookup"><span data-stu-id="93e13-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="93e13-142">Aviseringar kan komma från hot Protection-funktioner på en användares dator, i Office-appar, Cloud App-säkerhet och andra Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="93e13-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="93e13-143">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="93e13-143">**Devices**</span></span> | <span data-ttu-id="93e13-144">Visar en lista med maskiner som ingår i undersökningen tillsammans med reparations nivå.</span><span class="sxs-lookup"><span data-stu-id="93e13-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="93e13-145">**Nyckeltal**</span><span class="sxs-lookup"><span data-stu-id="93e13-145">**Key findings**</span></span>  | <span data-ttu-id="93e13-146">Visar resultaten från undersökningen tillsammans med status och åtgärder som utförs eller väntar.</span><span class="sxs-lookup"><span data-stu-id="93e13-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="93e13-147">Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="93e13-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="93e13-148">**Posterna**</span><span class="sxs-lookup"><span data-stu-id="93e13-148">**Entities**</span></span>  | <span data-ttu-id="93e13-149">Visar en lista över användar aktiviteter, filer, processer, tjänster, driv rutiner, IP-adresser och beständiga metoder som är förknippade med undersökningen samt status och åtgärder som vidtas.</span><span class="sxs-lookup"><span data-stu-id="93e13-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="93e13-150">**Logga in**</span><span class="sxs-lookup"><span data-stu-id="93e13-150">**Log**</span></span>    | <span data-ttu-id="93e13-151">Visar en detaljerad vy av alla steg som görs under undersökningen, tillsammans med status.</span><span class="sxs-lookup"><span data-stu-id="93e13-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="93e13-152">**Väntande åtgärder**</span><span class="sxs-lookup"><span data-stu-id="93e13-152">**Pending actions**</span></span> | <span data-ttu-id="93e13-153">Visar de objekt som kräver godkännande för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="93e13-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="93e13-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="93e13-154">Next steps</span></span>

- [<span data-ttu-id="93e13-155">Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="93e13-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="93e13-156">Granska reparations åtgärder</span><span class="sxs-lookup"><span data-stu-id="93e13-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
