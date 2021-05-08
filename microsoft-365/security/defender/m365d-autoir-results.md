---
title: Information och resultat från en automatiserad undersökning
description: Visa resultat och viktiga resultat från automatiserad undersökning i Microsoft 365 Defender
keywords: automatiserat, undersöka, resultat, analysera, information, åtgärd, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
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
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ad774fc36f4f167cb7a4e695b9f572ceb55b968b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274682"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="2e62a-104">Information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="2e62a-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2e62a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2e62a-105">**Applies to:**</span></span>
- <span data-ttu-id="2e62a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e62a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2e62a-107">När en automatiserad undersökning körs [](m365d-autoir.md) är information om undersökningen tillgänglig både under och efter den automatiska undersökningsprocessen med Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2e62a-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="2e62a-108">Om du har nödvändiga [behörigheter kan](m365d-action-center.md#required-permissions-for-action-center-tasks)du visa de uppgifterna i en vy med undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="2e62a-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="2e62a-109">Den här vyn ger dig uppdaterad status och möjlighet att godkänna eventuella väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2e62a-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="2e62a-111">(NY!) Sida för enhetlig undersökning</span><span class="sxs-lookup"><span data-stu-id="2e62a-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="2e62a-112">Undersökningssidan har nyligen uppdaterats för att inkludera information på dina enheter, e-post och samarbetsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="2e62a-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="2e62a-113">Den nya, enhetliga undersökningssidan definierar ett gemensamt språk och ger en enhetlig upplevelse för automatiska undersökningar i [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Endpoint och Microsoft Defender för [Office 365.](../office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="2e62a-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="2e62a-114">Välj länken i den gula banderollen som visas på sidan för enhetlig undersökning:</span><span class="sxs-lookup"><span data-stu-id="2e62a-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="2e62a-115">Alla undersökningssidor i Säkerhets- och & Office 365 ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="2e62a-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="2e62a-116">Undersökningssida i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="2e62a-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="2e62a-117">Alla incident- eller åtgärdscenterupplevelser i Säkerhetscenter i Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="2e62a-117">Any incident or Action center experience in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="2e62a-118">Öppna detaljvyn för undersökningen</span><span class="sxs-lookup"><span data-stu-id="2e62a-118">Open the investigation details view</span></span>

<span data-ttu-id="2e62a-119">Du kan öppna vyn med undersökningsinformation med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="2e62a-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="2e62a-120">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="2e62a-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="2e62a-121">Välj en undersökning från sidan Incidentinformation</span><span class="sxs-lookup"><span data-stu-id="2e62a-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="2e62a-122">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="2e62a-122">Select an item in the Action center</span></span>

<span data-ttu-id="2e62a-123">I det [förbättrade åtgärdscentret](m365d-action-center.md) () samlas åtgärder på alla dina [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) enheter, e-& och samarbeta innehåll och [](m365d-remediation-actions.md) identiteter.</span><span class="sxs-lookup"><span data-stu-id="2e62a-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="2e62a-124">Åtgärder i listan omfattar åtgärder som har vidtagits automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="2e62a-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="2e62a-125">I Åtgärdscenter kan du visa åtgärder som väntar på godkännande och åtgärder som redan har godkänts eller slutförts.</span><span class="sxs-lookup"><span data-stu-id="2e62a-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="2e62a-126">Du kan också gå till mer detaljerad information, till exempel en undersökningssida.</span><span class="sxs-lookup"><span data-stu-id="2e62a-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="2e62a-127">Du måste ha [vissa behörigheter för](m365d-action-center.md#required-permissions-for-action-center-tasks) att godkänna, avvisa eller ångra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2e62a-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="2e62a-128">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="2e62a-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="2e62a-129">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="2e62a-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="2e62a-130">Välj ett **objekt på fliken** **Väntande** eller Historik.</span><span class="sxs-lookup"><span data-stu-id="2e62a-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="2e62a-131">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="2e62a-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="2e62a-132">Granska informationen i det utfällfönster som visas och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="2e62a-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="2e62a-133">Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="2e62a-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="2e62a-134">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2e62a-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="2e62a-135">Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="2e62a-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="2e62a-136">Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e62a-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="2e62a-137">Öppna en undersökning från informationssidan för en händelse</span><span class="sxs-lookup"><span data-stu-id="2e62a-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="2e62a-138">Använd sidan incidentinformation om du vill visa detaljerad information om en händelse, inklusive aviseringar som utlöstes information om berörda enheter, användarkonton eller postlådor.</span><span class="sxs-lookup"><span data-stu-id="2e62a-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="2e62a-139">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="2e62a-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="2e62a-140">I navigeringsfönstret väljer du **Incidenter &**  >  **Incidenter.**</span><span class="sxs-lookup"><span data-stu-id="2e62a-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="2e62a-141">Markera ett objekt i listan och välj sedan **Öppna incidentsida**.</span><span class="sxs-lookup"><span data-stu-id="2e62a-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="2e62a-142">Välj **fliken Undersökningar** och välj sedan en undersökning i listan.</span><span class="sxs-lookup"><span data-stu-id="2e62a-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="2e62a-143">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="2e62a-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="2e62a-144">Välj **sidan Öppna undersökning.**</span><span class="sxs-lookup"><span data-stu-id="2e62a-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="2e62a-145">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="2e62a-145">Here's an example.</span></span>

![Incidentinformation](../../media/mtp-incidentdetails-tabs.png)

## <a name="investigation-details"></a><span data-ttu-id="2e62a-147">Undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="2e62a-147">Investigation details</span></span>

<span data-ttu-id="2e62a-148">Använd vyn med undersökningsinformation för att se tidigare, aktuella och väntande aktiviteter som hör till en undersökning.</span><span class="sxs-lookup"><span data-stu-id="2e62a-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="2e62a-149">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="2e62a-149">Here's an example.</span></span>

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

<span data-ttu-id="2e62a-151">I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, Varningar, Enheter, Identiteter, Nyckelresultat, Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.       </span><span class="sxs-lookup"><span data-stu-id="2e62a-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="2e62a-152">Vilka flikar som visas på sidan med undersökningsinformation beror på vad prenumerationen innehåller.</span><span class="sxs-lookup"><span data-stu-id="2e62a-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="2e62a-153">Om din prenumeration till exempel inte omfattar Microsoft Defender för Office 365 abonnemang 2 visas inte fliken **Postlådor.**</span><span class="sxs-lookup"><span data-stu-id="2e62a-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="2e62a-154">Tabb</span><span class="sxs-lookup"><span data-stu-id="2e62a-154">Tab</span></span> | <span data-ttu-id="2e62a-155">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2e62a-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="2e62a-156">**Undersökningsdiagram**</span><span class="sxs-lookup"><span data-stu-id="2e62a-156">**Investigation graph**</span></span>   | <span data-ttu-id="2e62a-157">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="2e62a-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="2e62a-158">Visar enheter och visar hot som hittas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="2e62a-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="2e62a-159">Du kan markera ett objekt i diagrammet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="2e62a-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="2e62a-160">Om du till exempel **väljer ikonen Bevis** kommer du till fliken **Bevis** där du kan se identifierade enheter och deras bedömningar.</span><span class="sxs-lookup"><span data-stu-id="2e62a-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="2e62a-161">**Varningar**</span><span class="sxs-lookup"><span data-stu-id="2e62a-161">**Alerts**</span></span>    | <span data-ttu-id="2e62a-162">Listar aviseringar kopplade till undersökningen.</span><span class="sxs-lookup"><span data-stu-id="2e62a-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="2e62a-163">Aviseringar kan komma från skyddsfunktioner för hot på en användares enhet, i Office-appar, Microsoft Cloud App Security och andra Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="2e62a-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="2e62a-164">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="2e62a-164">**Devices**</span></span> | <span data-ttu-id="2e62a-165">Visar enheter som ingår i undersökningen tillsammans med deras åtgärdsnivå.</span><span class="sxs-lookup"><span data-stu-id="2e62a-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="2e62a-166">(Åtgärdsnivåer motsvarar [automationsnivån för enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span><span class="sxs-lookup"><span data-stu-id="2e62a-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="2e62a-167">**Postlådor**</span><span class="sxs-lookup"><span data-stu-id="2e62a-167">**Mailboxes**</span></span> |<span data-ttu-id="2e62a-168">Listar postlådor som påverkas av identifierade hot.</span><span class="sxs-lookup"><span data-stu-id="2e62a-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="2e62a-169">**Användare**</span><span class="sxs-lookup"><span data-stu-id="2e62a-169">**Users**</span></span>  | <span data-ttu-id="2e62a-170">Här listas användarkonton som påverkas av identifierade hot.</span><span class="sxs-lookup"><span data-stu-id="2e62a-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="2e62a-171">**Bevis**</span><span class="sxs-lookup"><span data-stu-id="2e62a-171">**Evidence**</span></span> | <span data-ttu-id="2e62a-172">Här listas bevis som upphöjts av varningar eller undersökningar.</span><span class="sxs-lookup"><span data-stu-id="2e62a-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="2e62a-173">Omfattar bedömningstillstånd *(Skadlig,* *Misstänkt,* Okänd eller *Inga hot hittades)* och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="2e62a-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="2e62a-174">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="2e62a-174">**Entities**</span></span>  | <span data-ttu-id="2e62a-175">Innehåller information om varje analyserad enhet, inklusive en bedömning för varje typ av enhet *(Skadlig,* Misstänkt eller *Inga hot hittades).*</span><span class="sxs-lookup"><span data-stu-id="2e62a-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="2e62a-176">**Logg**</span><span class="sxs-lookup"><span data-stu-id="2e62a-176">**Log**</span></span>    | <span data-ttu-id="2e62a-177">Visar en kronologisk, detaljerad vy av alla undersökningsåtgärder som har vidtagits efter att en avisering utlösts.</span><span class="sxs-lookup"><span data-stu-id="2e62a-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="2e62a-178">**Historik för väntande åtgärder**</span><span class="sxs-lookup"><span data-stu-id="2e62a-178">**Pending actions history**</span></span> | <span data-ttu-id="2e62a-179">En lista med objekt som måste godkännas för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2e62a-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="2e62a-180">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () för att godkänna väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2e62a-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="2e62a-181">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2e62a-181">Next steps</span></span>

- [<span data-ttu-id="2e62a-182">Visa och hantera åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="2e62a-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="2e62a-183">Läs mer om åtgärder</span><span class="sxs-lookup"><span data-stu-id="2e62a-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
