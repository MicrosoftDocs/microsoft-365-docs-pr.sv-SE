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
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ca023ea49a8d92123467be640a097a72233d3198
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592126"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="704a8-104">Information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="704a8-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="704a8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="704a8-105">**Applies to:**</span></span>
- <span data-ttu-id="704a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="704a8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="704a8-107">När en automatiserad undersökning körs [](m365d-autoir.md) är information om undersökningen tillgänglig både under och efter den automatiska undersökningsprocessen med Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="704a8-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="704a8-108">Om du har nödvändiga [behörigheter kan](m365d-action-center.md#required-permissions-for-action-center-tasks)du visa de uppgifterna i en vy med undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="704a8-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="704a8-109">Vyn med undersökningsinformation ger dig uppdaterad status och möjlighet att godkänna eventuella väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="704a8-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="704a8-111">(NY!) Sida för enhetlig undersökning</span><span class="sxs-lookup"><span data-stu-id="704a8-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="704a8-112">Undersökningssidan har nyligen uppdaterats för att inkludera information på dina enheter, e-post och samarbetsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="704a8-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="704a8-113">Den nya, enhetliga undersökningssidan definierar ett gemensamt språk och ger en enhetlig upplevelse för automatiska undersökningar i [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Endpoint och Microsoft Defender för [Office 365.](../office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="704a8-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="704a8-114">Välj länken i den gula banderollen som visas på sidan för enhetlig undersökning:</span><span class="sxs-lookup"><span data-stu-id="704a8-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>
- <span data-ttu-id="704a8-115">Alla undersökningssidor i Säkerhets- och & Office 365 ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="704a8-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="704a8-116">Undersökningssida i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="704a8-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="704a8-117">Alla funktioner för incidenter eller åtgärdscenter i det förbättrade säkerhetscentret i Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="704a8-117">Any incident or Action center experience in the improved Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="704a8-118">Öppna detaljvyn för undersökningen</span><span class="sxs-lookup"><span data-stu-id="704a8-118">Open the investigation details view</span></span>

<span data-ttu-id="704a8-119">Du kan öppna vyn med undersökningsinformation med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="704a8-119">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="704a8-120">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="704a8-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="704a8-121">Välj en undersökning från sidan Incidentinformation</span><span class="sxs-lookup"><span data-stu-id="704a8-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="704a8-122">Markera ett objekt i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="704a8-122">Select an item in the Action center</span></span>

<span data-ttu-id="704a8-123">I det [förbättrade åtgärdscentret](m365d-action-center.md) () samlas åtgärder på alla dina [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) enheter, e-& och samarbeta innehåll och [](m365d-remediation-actions.md) identiteter.</span><span class="sxs-lookup"><span data-stu-id="704a8-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="704a8-124">Åtgärder i listan omfattar åtgärder som har vidtagits automatiskt eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="704a8-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="704a8-125">I Åtgärdscenter kan du visa åtgärder som väntar på godkännande och åtgärder som redan har godkänts eller slutförts.</span><span class="sxs-lookup"><span data-stu-id="704a8-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="704a8-126">Du kan också gå till mer detaljerad information, till exempel en undersökningssida.</span><span class="sxs-lookup"><span data-stu-id="704a8-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="704a8-127">Du måste ha [vissa behörigheter för](m365d-action-center.md#required-permissions-for-action-center-tasks) att godkänna, avvisa eller ångra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="704a8-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="704a8-128">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="704a8-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="704a8-129">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="704a8-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="704a8-130">Välj ett **objekt på fliken** **Väntande** eller Historik.</span><span class="sxs-lookup"><span data-stu-id="704a8-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="704a8-131">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="704a8-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="704a8-132">Granska informationen i det utfällfönster som visas och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="704a8-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="704a8-133">Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.</span><span class="sxs-lookup"><span data-stu-id="704a8-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="704a8-134">Välj **Godkänn** för att påbörja en väntande åtgärd.</span><span class="sxs-lookup"><span data-stu-id="704a8-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="704a8-135">Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="704a8-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="704a8-136">Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="704a8-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="704a8-137">Öppna en undersökning från informationssidan för en händelse</span><span class="sxs-lookup"><span data-stu-id="704a8-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="704a8-138">Använd sidan incidentinformation om du vill visa detaljerad information om en händelse, inklusive aviseringar som utlöstes information om berörda enheter, användarkonton eller postlådor.</span><span class="sxs-lookup"><span data-stu-id="704a8-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

![Incidentinformation](../../media/mtp-incidentdetails-tabs.png)

1. <span data-ttu-id="704a8-140">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="704a8-140">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="704a8-141">I navigeringsfönstret väljer du **Incidenter &**  >  **Incidenter.**</span><span class="sxs-lookup"><span data-stu-id="704a8-141">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="704a8-142">Markera ett objekt i listan och välj sedan **Öppna incidentsida**.</span><span class="sxs-lookup"><span data-stu-id="704a8-142">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="704a8-143">Välj **fliken Undersökningar** och välj sedan en undersökning i listan.</span><span class="sxs-lookup"><span data-stu-id="704a8-143">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="704a8-144">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="704a8-144">Its flyout pane opens.</span></span>

5. <span data-ttu-id="704a8-145">Välj **sidan Öppna undersökning.**</span><span class="sxs-lookup"><span data-stu-id="704a8-145">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="704a8-146">Undersökningsinformation</span><span class="sxs-lookup"><span data-stu-id="704a8-146">Investigation details</span></span>

<span data-ttu-id="704a8-147">Använd vyn med undersökningsinformation för att se tidigare, aktuella och väntande aktiviteter som hör till en undersökning.</span><span class="sxs-lookup"><span data-stu-id="704a8-147">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="704a8-148">Vyn med undersökningsinformation liknar följande bild:</span><span class="sxs-lookup"><span data-stu-id="704a8-148">The investigation details view resembles the following image:</span></span>

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

<span data-ttu-id="704a8-150">I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, Varningar, Enheter, Identiteter, Nyckelresultat, Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.       </span><span class="sxs-lookup"><span data-stu-id="704a8-150">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="704a8-151">Vilka flikar som visas på sidan med undersökningsinformation beror på vad prenumerationen innehåller.</span><span class="sxs-lookup"><span data-stu-id="704a8-151">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="704a8-152">Om din prenumeration till exempel inte omfattar Microsoft Defender för Office 365 abonnemang 2 visas inte fliken **Postlådor.**</span><span class="sxs-lookup"><span data-stu-id="704a8-152">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="704a8-153">Tabb</span><span class="sxs-lookup"><span data-stu-id="704a8-153">Tab</span></span> | <span data-ttu-id="704a8-154">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="704a8-154">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="704a8-155">**Undersökningsdiagram**</span><span class="sxs-lookup"><span data-stu-id="704a8-155">**Investigation graph**</span></span>   | <span data-ttu-id="704a8-156">Ger en visuell representation av undersökningen.</span><span class="sxs-lookup"><span data-stu-id="704a8-156">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="704a8-157">Visar enheter och visar hot som hittas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.</span><span class="sxs-lookup"><span data-stu-id="704a8-157">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="704a8-158">Du kan markera ett objekt i diagrammet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="704a8-158">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="704a8-159">Om du till exempel **väljer ikonen Bevis** kommer du till fliken **Bevis** där du kan se identifierade enheter och deras bedömningar.</span><span class="sxs-lookup"><span data-stu-id="704a8-159">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="704a8-160">**Varningar**</span><span class="sxs-lookup"><span data-stu-id="704a8-160">**Alerts**</span></span>    | <span data-ttu-id="704a8-161">Listar aviseringar kopplade till undersökningen.</span><span class="sxs-lookup"><span data-stu-id="704a8-161">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="704a8-162">Varningar kan komma från skyddsfunktioner för hot på en användares enhet, i Office-appar, Cloud App Security och andra Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="704a8-162">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="704a8-163">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="704a8-163">**Devices**</span></span> | <span data-ttu-id="704a8-164">Visar enheter som ingår i undersökningen tillsammans med deras åtgärdsnivå.</span><span class="sxs-lookup"><span data-stu-id="704a8-164">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="704a8-165">(Åtgärdsnivåer motsvarar [automationsnivån för enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span><span class="sxs-lookup"><span data-stu-id="704a8-165">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="704a8-166">**Postlådor**</span><span class="sxs-lookup"><span data-stu-id="704a8-166">**Mailboxes**</span></span> |<span data-ttu-id="704a8-167">Listar postlådor som påverkas av identifierade hot.</span><span class="sxs-lookup"><span data-stu-id="704a8-167">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="704a8-168">**Användare**</span><span class="sxs-lookup"><span data-stu-id="704a8-168">**Users**</span></span>  | <span data-ttu-id="704a8-169">Här listas användarkonton som påverkas av identifierade hot.</span><span class="sxs-lookup"><span data-stu-id="704a8-169">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="704a8-170">**Bevis**</span><span class="sxs-lookup"><span data-stu-id="704a8-170">**Evidence**</span></span> | <span data-ttu-id="704a8-171">Listar bevis som upphöjts av varningar/undersökningar.</span><span class="sxs-lookup"><span data-stu-id="704a8-171">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="704a8-172">Omfattar bedömningstillstånd *(skadlig,* misstänkt *eller Inga hot hittades)* och åtgärdsstatus.</span><span class="sxs-lookup"><span data-stu-id="704a8-172">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="704a8-173">**Enheter**</span><span class="sxs-lookup"><span data-stu-id="704a8-173">**Entities**</span></span>  | <span data-ttu-id="704a8-174">Innehåller information om varje analyserad enhet, inklusive en bedömning för varje typ av enhet *(Skadlig,* Misstänkt eller *Inga hot hittades).*</span><span class="sxs-lookup"><span data-stu-id="704a8-174">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="704a8-175">**Logg**</span><span class="sxs-lookup"><span data-stu-id="704a8-175">**Log**</span></span>    | <span data-ttu-id="704a8-176">Visar en kronologisk, detaljerad vy av alla undersökningsåtgärder som har vidtagits efter att en avisering utlösts.</span><span class="sxs-lookup"><span data-stu-id="704a8-176">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="704a8-177">**Väntande åtgärder**</span><span class="sxs-lookup"><span data-stu-id="704a8-177">**Pending actions**</span></span> | <span data-ttu-id="704a8-178">En lista med objekt som måste godkännas för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="704a8-178">Lists items that require approval to proceed.</span></span> <span data-ttu-id="704a8-179">Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () för att godkänna väntande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="704a8-179">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="704a8-180">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="704a8-180">Next steps</span></span>

- [<span data-ttu-id="704a8-181">Godkänna eller avvisa åtgärder efter en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="704a8-181">Approve or reject remediation actions following an automated investigation</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="704a8-182">Läs mer om åtgärder</span><span class="sxs-lookup"><span data-stu-id="704a8-182">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
