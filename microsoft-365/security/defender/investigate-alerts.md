---
title: Analysera aviseringar i Microsoft 365 Defender
description: Analysera aviseringar som visas på olika enheter, användare och postlådor.
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
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939548"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a><span data-ttu-id="c7a99-104">Analysera aviseringar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7a99-104">Analyze alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c7a99-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c7a99-105">**Applies to:**</span></span>
- <span data-ttu-id="c7a99-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7a99-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c7a99-107">Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="c7a99-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="c7a99-108">Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om en händelse.</span><span class="sxs-lookup"><span data-stu-id="c7a99-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="c7a99-109">I Microsoft 365 Defender sammanställs relaterade aviseringar till [formulärincidenter](incidents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7a99-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="c7a99-110">Incidenter ger alltid ett bredare sammanhang för en attack, men det kan vara värdefullt att analysera aviseringar när en djupare analys krävs.</span><span class="sxs-lookup"><span data-stu-id="c7a99-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="c7a99-111">I **kön Aviseringar** visas den aktuella uppsättningen aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c7a99-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="c7a99-112">Du kommer till aviseringskön från **incidenter &** aviseringar > aviseringar i snabbstarten av säkerhetscentret för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c7a99-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exempel på aviseringskön":::

<span data-ttu-id="c7a99-114">Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas här.</span><span class="sxs-lookup"><span data-stu-id="c7a99-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="c7a99-115">Som standard visar aviseringskön i Säkerhetscenter för Microsoft 365 de nya och pågående aviseringarna från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c7a99-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="c7a99-116">Den senaste aviseringen visas högst upp i listan så att du kan se den först.</span><span class="sxs-lookup"><span data-stu-id="c7a99-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="c7a99-117">Från standardaviseringskön kan  du välja  Filter för att visa ett filterfönster där du kan ange en delmängd av aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="c7a99-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="c7a99-118">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c7a99-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Exempel på filterfönstret för aviseringskön":::

<span data-ttu-id="c7a99-120">Du kan filtrera aviseringar enligt följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="c7a99-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="c7a99-121">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="c7a99-121">Severity</span></span>
- <span data-ttu-id="c7a99-122">Status</span><span class="sxs-lookup"><span data-stu-id="c7a99-122">Status</span></span>
- <span data-ttu-id="c7a99-123">Kategori</span><span class="sxs-lookup"><span data-stu-id="c7a99-123">Category</span></span>
- <span data-ttu-id="c7a99-124">Identifieringskälla</span><span class="sxs-lookup"><span data-stu-id="c7a99-124">Detection source</span></span>
- <span data-ttu-id="c7a99-125">Taggar</span><span class="sxs-lookup"><span data-stu-id="c7a99-125">Tags</span></span>
- <span data-ttu-id="c7a99-126">Princip</span><span class="sxs-lookup"><span data-stu-id="c7a99-126">Policy</span></span>
- <span data-ttu-id="c7a99-127">Påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="c7a99-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="c7a99-128">Analysera en avisering</span><span class="sxs-lookup"><span data-stu-id="c7a99-128">Analyze an alert</span></span>

<span data-ttu-id="c7a99-129">Markera namnet på aviseringen om du vill se huvudaviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="c7a99-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="c7a99-130">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c7a99-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="c7a99-132">Du kan också välja **åtgärden Öppna huvudaviseringssidan** i **fönstret Hantera** avisering.</span><span class="sxs-lookup"><span data-stu-id="c7a99-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="c7a99-133">En aviseringssida består av följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="c7a99-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="c7a99-134">Aviseringsartikel</span><span class="sxs-lookup"><span data-stu-id="c7a99-134">Alert story</span></span>
- <span data-ttu-id="c7a99-135">Åtgärder som vidtas (inklusive påverkade tillgångar)</span><span class="sxs-lookup"><span data-stu-id="c7a99-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="c7a99-136">Relaterade händelser</span><span class="sxs-lookup"><span data-stu-id="c7a99-136">Related events</span></span>
- <span data-ttu-id="c7a99-137">Sammanfattningsinformation</span><span class="sxs-lookup"><span data-stu-id="c7a99-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="c7a99-139">På en aviseringssida kan du välja ellipsen (**...**) bredvid en enhet för att se tillgängliga åtgärder, till exempel öppna sidan för specifika tillgångar eller vidta specifika åtgärdssteg.</span><span class="sxs-lookup"><span data-stu-id="c7a99-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="c7a99-140">Analysera påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="c7a99-140">Analyze affected assets</span></span>

<span data-ttu-id="c7a99-141">Avsnittet **Åtgärder som** vidtas har en lista över påverkade tillgångar, till exempel postlådor, enheter och användare som påverkas av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c7a99-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="c7a99-142">Du kan också välja Visa i  **åtgärdscenter** för att visa fliken Historik i Åtgärdscenter  i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7a99-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="c7a99-143">Spåra en aviserings roll i aviseringsartikeln</span><span class="sxs-lookup"><span data-stu-id="c7a99-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="c7a99-144">I aviseringsartikeln visas alla tillgångar eller enheter som är relaterade till aviseringen i en processträdvy.</span><span class="sxs-lookup"><span data-stu-id="c7a99-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="c7a99-145">Aviseringen i rubriken är den som är i fokus när du först kommer till den valda aviseringens sida.</span><span class="sxs-lookup"><span data-stu-id="c7a99-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="c7a99-146">Tillgångar i aviseringsartikeln är expanderbara och klickbara.</span><span class="sxs-lookup"><span data-stu-id="c7a99-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="c7a99-147">De ger ytterligare information och underlättar ditt svar genom att göra det möjligt för dig att vidta åtgärder direkt i samband med aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="c7a99-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="c7a99-148">Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.</span><span class="sxs-lookup"><span data-stu-id="c7a99-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="c7a99-149">Visa mer aviseringsinformation på informationssidan</span><span class="sxs-lookup"><span data-stu-id="c7a99-149">View more alert information on the details page</span></span>

<span data-ttu-id="c7a99-150">På informationssidan visas information om den valda aviseringen, med information och relaterade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c7a99-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="c7a99-151">Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationssidan för att ge sammanhangsberoende information och åtgärder för det valda objektet.</span><span class="sxs-lookup"><span data-stu-id="c7a99-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="c7a99-152">När du har valt en intresseenhet ändras informationssidan för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och alternativ för att vidta åtgärder på den här enheten direkt från aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="c7a99-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="c7a99-153">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="c7a99-153">Manage alerts</span></span>

<span data-ttu-id="c7a99-154">Om du vill hantera en avisering markerar du aviseringen i kön med aviseringar på raden så att fönstret **Hantera avisering** visas.</span><span class="sxs-lookup"><span data-stu-id="c7a99-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="c7a99-155">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c7a99-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Exempel på sammanfattningsfönstret för en avisering":::

<span data-ttu-id="c7a99-157">I **aviseringsfönstret** Hantera kan du ange:</span><span class="sxs-lookup"><span data-stu-id="c7a99-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="c7a99-158">Aviseringsstatus (Ny, Löst, Pågår).</span><span class="sxs-lookup"><span data-stu-id="c7a99-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="c7a99-159">Aviseringens klassificering (Inte inställd, Sant meddelande, Falsk avisering).</span><span class="sxs-lookup"><span data-stu-id="c7a99-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="c7a99-160">För klassificering som en verklig avisering anger du typen av hot för aviseringen i **fältet Determination** .</span><span class="sxs-lookup"><span data-stu-id="c7a99-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="c7a99-161">En kommentar om aviseringen.</span><span class="sxs-lookup"><span data-stu-id="c7a99-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="c7a99-162">Ett sätt att hantera aviseringar via taggar.</span><span class="sxs-lookup"><span data-stu-id="c7a99-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="c7a99-163">Taggningsfunktioner för Microsoft Defender för Office 365 distribueras stegvis och är för närvarande i förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="c7a99-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="c7a99-164">För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="c7a99-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="c7a99-165">Aviseringar som har genererats innan ändringen återspeglar inte det uppdaterade taggnamnet.</span><span class="sxs-lookup"><span data-stu-id="c7a99-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="c7a99-166">Från det här fönstret kan du även utföra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="c7a99-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="c7a99-167">Öppna huvudaviseringssidan</span><span class="sxs-lookup"><span data-stu-id="c7a99-167">Open the main alert page</span></span>
- <span data-ttu-id="c7a99-168">Kontakta en Microsoft-expert på hot</span><span class="sxs-lookup"><span data-stu-id="c7a99-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="c7a99-169">Visa inskickat material</span><span class="sxs-lookup"><span data-stu-id="c7a99-169">View submission</span></span>
- <span data-ttu-id="c7a99-170">Länka till ett annat incident</span><span class="sxs-lookup"><span data-stu-id="c7a99-170">Link to another incident</span></span>
- <span data-ttu-id="c7a99-171">Se aviseringen på en tidslinje</span><span class="sxs-lookup"><span data-stu-id="c7a99-171">See the alert in a timeline</span></span>
- <span data-ttu-id="c7a99-172">Skapa en regel för en regel</span><span class="sxs-lookup"><span data-stu-id="c7a99-172">Create a suppression rule</span></span>

<span data-ttu-id="c7a99-173">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="c7a99-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exempel på åtgärder för en avisering i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="c7a99-175">Listan med ytterligare åtgärder beror på typen av avisering.</span><span class="sxs-lookup"><span data-stu-id="c7a99-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="c7a99-176">Lösa en avisering</span><span class="sxs-lookup"><span data-stu-id="c7a99-176">Resolve an alert</span></span>

<span data-ttu-id="c7a99-177">När du är klar med att analysera en avisering  och den kan lösas går du  till fönstret Hantera avisering för aviseringen och markerar dess status som Löst och klassificerar den som en **falsk** avisering eller **Sant-avisering.**</span><span class="sxs-lookup"><span data-stu-id="c7a99-177">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="c7a99-178">För verkliga varningar anger du aviseringens hottyp i **fältet Determination.**</span><span class="sxs-lookup"><span data-stu-id="c7a99-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="c7a99-179">Genom att klassificera aviseringar och ange deras avgörande hjälper du Microsoft 365 Defender att tillhandahålla mer sanna aviseringar och mindre falska aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c7a99-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7a99-180">Se även</span><span class="sxs-lookup"><span data-stu-id="c7a99-180">See also</span></span>

- [<span data-ttu-id="c7a99-181">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="c7a99-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c7a99-182">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="c7a99-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="c7a99-183">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="c7a99-183">Analyze incidents</span></span>](investigate-incidents.md)
