---
title: Undersök aviseringar i Microsoft 365 Defender
description: Undersök aviseringar som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, analyserar, svar, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365
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
ms.openlocfilehash: 567916e9e1a1d96d77bc6c187b384a1ec3be72a5
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022719"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="04968-104">Undersök aviseringar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04968-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="04968-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="04968-105">**Applies to:**</span></span>
- <span data-ttu-id="04968-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04968-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="04968-107">Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="04968-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="04968-108">Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om en händelse.</span><span class="sxs-lookup"><span data-stu-id="04968-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="04968-109">I Microsoft 365 Defender sammanförs relaterade aviseringar för [formulärincidenter.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="04968-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="04968-110">Incidenter ger alltid ett bredare sammanhang för en attack, men det kan vara värdefullt att analysera aviseringar när en djupare analys krävs.</span><span class="sxs-lookup"><span data-stu-id="04968-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="04968-111">I **kön Aviseringar** visas den aktuella uppsättningen aviseringar.</span><span class="sxs-lookup"><span data-stu-id="04968-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="04968-112">Du kommer till aviseringskön **från Incidenter & aviseringar > aviseringar** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="04968-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exempel på aviseringskön":::

<span data-ttu-id="04968-114">Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas här.</span><span class="sxs-lookup"><span data-stu-id="04968-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="04968-115">Som standard visar aviseringskön i Microsoft 365 Defender-portalen de nya och pågående aviseringarna från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="04968-115">By default, the alerts queue in the Microsoft 365 Defender portal displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="04968-116">Den senaste aviseringen visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="04968-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="04968-117">Från standardaviseringskön kan  du välja  Filter för att visa ett filterfönster där du kan ange en delmängd av aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="04968-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="04968-118">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="04968-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Exempel på filterfönstret för aviseringskön":::

<span data-ttu-id="04968-120">Du kan filtrera aviseringar enligt följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="04968-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="04968-121">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="04968-121">Severity</span></span>
- <span data-ttu-id="04968-122">Status</span><span class="sxs-lookup"><span data-stu-id="04968-122">Status</span></span>
- <span data-ttu-id="04968-123">Kategori</span><span class="sxs-lookup"><span data-stu-id="04968-123">Category</span></span>
- <span data-ttu-id="04968-124">Identifieringskälla</span><span class="sxs-lookup"><span data-stu-id="04968-124">Detection source</span></span>
- <span data-ttu-id="04968-125">Taggar</span><span class="sxs-lookup"><span data-stu-id="04968-125">Tags</span></span>
- <span data-ttu-id="04968-126">Princip</span><span class="sxs-lookup"><span data-stu-id="04968-126">Policy</span></span>
- <span data-ttu-id="04968-127">Påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="04968-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="04968-128">Analysera en avisering</span><span class="sxs-lookup"><span data-stu-id="04968-128">Analyze an alert</span></span>

<span data-ttu-id="04968-129">Markera namnet på aviseringen om du vill se huvudaviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="04968-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="04968-130">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="04968-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Microsoft 365 Defender portalen":::

<span data-ttu-id="04968-132">Du kan också välja **åtgärden Öppna huvudaviseringssidan** i **fönstret Hantera** avisering.</span><span class="sxs-lookup"><span data-stu-id="04968-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="04968-133">En aviseringssida består av följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="04968-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="04968-134">Aviseringsartikel, som är kedjan med händelser och aviseringar som är relaterade till den här aviseringen i kronologisk ordning</span><span class="sxs-lookup"><span data-stu-id="04968-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="04968-135">Sammanfattningsinformation</span><span class="sxs-lookup"><span data-stu-id="04968-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Microsoft 365 Defender portalen":::

<span data-ttu-id="04968-137">På en aviseringssida kan du välja punkterna (**...**) bredvid en enhet för att se tillgängliga åtgärder, till exempel öppna aviseringssidan eller länka aviseringen till en annan händelse.</span><span class="sxs-lookup"><span data-stu-id="04968-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="04968-138">Aviseringskällor</span><span class="sxs-lookup"><span data-stu-id="04968-138">Alert sources</span></span>
<span data-ttu-id="04968-139">Microsoft 365 Defender kan komma från lösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="04968-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="04968-140">Du kanske lägger märke till aviseringar med in prepended characters i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="04968-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="04968-141">Följande tabell innehåller vägledning för att hjälpa dig att förstå mappningen av aviseringskällor baserat på det tecken som ska förberedas i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="04968-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="04968-142">De ursprungliga GUID:erna är endast specifika för enhetliga upplevelser, till exempel enhetlig aviseringskö, sida för enhetliga aviseringar, enhetlig undersökning och enhetlig incident.</span><span class="sxs-lookup"><span data-stu-id="04968-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="04968-143">Det in prepended-tecknet ändrar inte GUID för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="04968-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="04968-144">Den enda ändringen i GUID är den in prepended component.</span><span class="sxs-lookup"><span data-stu-id="04968-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="04968-145">Aviseringskälla</span><span class="sxs-lookup"><span data-stu-id="04968-145">Alert source</span></span> | <span data-ttu-id="04968-146">Insnabbtecken</span><span class="sxs-lookup"><span data-stu-id="04968-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="04968-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="04968-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="04968-148">Exempel: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="04968-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="04968-149">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="04968-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="04968-150">`da` eller `ed` för aviseringar om anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="04968-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="04968-151">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="04968-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="04968-152">Exempel: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="04968-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="04968-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="04968-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="04968-154">Exempel: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="04968-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 

### <a name="analyze-affected-assets"></a><span data-ttu-id="04968-155">Analysera påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="04968-155">Analyze affected assets</span></span>

<span data-ttu-id="04968-156">Avsnittet **Åtgärder som** vidtas har en lista över påverkade tillgångar, till exempel postlådor, enheter och användare som påverkas av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="04968-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="04968-157">Du kan också välja **Visa i åtgärdscenter** för att visa **fliken** Historik **i Åtgärdscenter** Microsoft 365 Defender administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="04968-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 Defender portal.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="04968-158">Spåra en aviserings roll i aviseringsartikeln</span><span class="sxs-lookup"><span data-stu-id="04968-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="04968-159">I aviseringsartikeln visas alla tillgångar eller enheter som är relaterade till aviseringen i en processträdvy.</span><span class="sxs-lookup"><span data-stu-id="04968-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="04968-160">Aviseringen i rubriken är den som är i fokus när du först kommer till den valda aviseringens sida.</span><span class="sxs-lookup"><span data-stu-id="04968-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="04968-161">Tillgångar i aviseringsartikeln är expanderbara och klickbara.</span><span class="sxs-lookup"><span data-stu-id="04968-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="04968-162">De ger ytterligare information och underlättar ditt svar genom att göra det möjligt för dig att vidta åtgärder direkt i samband med aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="04968-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="04968-163">Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.</span><span class="sxs-lookup"><span data-stu-id="04968-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="04968-164">Visa mer aviseringsinformation på informationssidan</span><span class="sxs-lookup"><span data-stu-id="04968-164">View more alert information on the details page</span></span>

<span data-ttu-id="04968-165">På informationssidan visas information om den valda aviseringen, med information och relaterade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="04968-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="04968-166">Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationssidan för att ge sammanhangsberoende information och åtgärder för det valda objektet.</span><span class="sxs-lookup"><span data-stu-id="04968-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="04968-167">När du har valt en intresseenhet ändras informationssidan för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och alternativ för att vidta åtgärder på den här enheten direkt från aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="04968-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="04968-168">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="04968-168">Manage alerts</span></span>

<span data-ttu-id="04968-169">Om du vill hantera en avisering markerar du aviseringen i kön med aviseringar på raden så att fönstret **Hantera avisering** visas.</span><span class="sxs-lookup"><span data-stu-id="04968-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="04968-170">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="04968-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Exempel på sammanfattningsfönstret för en avisering":::

<span data-ttu-id="04968-172">I **aviseringsfönstret** Hantera kan du ange:</span><span class="sxs-lookup"><span data-stu-id="04968-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="04968-173">Aviseringsstatus (Ny, Löst, Pågår).</span><span class="sxs-lookup"><span data-stu-id="04968-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="04968-174">Aviseringens klassificering (Inte inställd, Sant meddelande, Falsk avisering).</span><span class="sxs-lookup"><span data-stu-id="04968-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="04968-175">För klassificering som en verklig avisering anger du typen av hot för aviseringen i **fältet Determination** .</span><span class="sxs-lookup"><span data-stu-id="04968-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="04968-176">En kommentar om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="04968-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="04968-177">Ett sätt att hantera aviseringar via taggar.</span><span class="sxs-lookup"><span data-stu-id="04968-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="04968-178">Taggningsfunktioner för Microsoft Defender för Office 365 stegvis distribueras och är för närvarande i förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="04968-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="04968-179">För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="04968-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="04968-180">Aviseringar som har genererats innan ändringen återspeglar inte det uppdaterade taggnamnet.</span><span class="sxs-lookup"><span data-stu-id="04968-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="04968-181">Från det här fönstret kan du även utföra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="04968-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="04968-182">Öppna huvudaviseringssidan</span><span class="sxs-lookup"><span data-stu-id="04968-182">Open the main alert page</span></span>
- <span data-ttu-id="04968-183">Kontakta en Microsoft-expert på hot</span><span class="sxs-lookup"><span data-stu-id="04968-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="04968-184">Visa inskickat material</span><span class="sxs-lookup"><span data-stu-id="04968-184">View submission</span></span>
- <span data-ttu-id="04968-185">Länka till ett annat incident</span><span class="sxs-lookup"><span data-stu-id="04968-185">Link to another incident</span></span>
- <span data-ttu-id="04968-186">Se aviseringen på en tidslinje</span><span class="sxs-lookup"><span data-stu-id="04968-186">See the alert in a timeline</span></span>
- <span data-ttu-id="04968-187">Skapa en regel för en regel</span><span class="sxs-lookup"><span data-stu-id="04968-187">Create a suppression rule</span></span>

<span data-ttu-id="04968-188">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="04968-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exempel på åtgärder på en avisering i Microsoft 365 Defender portalen":::

<span data-ttu-id="04968-190">Listan med ytterligare åtgärder beror på typen av avisering.</span><span class="sxs-lookup"><span data-stu-id="04968-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="04968-191">Lösa en avisering</span><span class="sxs-lookup"><span data-stu-id="04968-191">Resolve an alert</span></span>

<span data-ttu-id="04968-192">När du är klar med att analysera en avisering  och den kan lösas går du  till fönstret Hantera avisering för aviseringen och markerar dess status som Löst och klassificerar den som en **falsk** avisering eller **Sant-avisering.**</span><span class="sxs-lookup"><span data-stu-id="04968-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="04968-193">För verkliga varningar anger du aviseringens hottyp i **fältet Determination.**</span><span class="sxs-lookup"><span data-stu-id="04968-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="04968-194">Genom att klassificera aviseringar och ange deras avgörande hjälper du Microsoft 365 Defender att tillhandahålla mer sanna aviseringar och mindre falska aviseringar.</span><span class="sxs-lookup"><span data-stu-id="04968-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04968-195">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="04968-195">Next steps</span></span>

<span data-ttu-id="04968-196">Fortsätt din undersökning om det behövs för händelser i [processen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="04968-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04968-197">Se även</span><span class="sxs-lookup"><span data-stu-id="04968-197">See also</span></span>

- [<span data-ttu-id="04968-198">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="04968-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="04968-199">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="04968-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="04968-200">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="04968-200">Investigate incidents</span></span>](investigate-incidents.md)
