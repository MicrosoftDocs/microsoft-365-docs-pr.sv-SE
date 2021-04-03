---
title: Undersöka aviseringar i Microsoft 365 Defender
description: Undersök aviseringar som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
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
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500938"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="15d89-104">Undersöka aviseringar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15d89-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="15d89-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="15d89-105">**Applies to:**</span></span>
- <span data-ttu-id="15d89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15d89-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="15d89-107">Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="15d89-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="15d89-108">Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om ett incidenter.</span><span class="sxs-lookup"><span data-stu-id="15d89-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="15d89-109">I Microsoft 365 Defender sammanställs relaterade aviseringar till formulärincidenter.</span><span class="sxs-lookup"><span data-stu-id="15d89-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="15d89-110">Incidenter ger alltid en bredare kontext för en attack, men det kan vara värdefullt att undersöka aviseringar när en djupare analys krävs.</span><span class="sxs-lookup"><span data-stu-id="15d89-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="15d89-111">Med aviseringssidor i undersökningar</span><span class="sxs-lookup"><span data-stu-id="15d89-111">Using alert pages in investigations</span></span>

<span data-ttu-id="15d89-112">Om du markerar en avisering på fliken Aviseringar på sidan Incidenter kommer du till de enskilda aviseringssidorna.</span><span class="sxs-lookup"><span data-stu-id="15d89-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="15d89-113">En aviseringssida består av tre avsnitt: påverkade tillgångar, aviseringsavsnitt och informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="15d89-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Bild på exempelaviseringssida](../../media/new-alert-page2.png)

<span data-ttu-id="15d89-115">På en aviseringssida kan du välja ikonen med tre punkter (**...**) bredvid en enhet så att du kan se tillgängliga åtgärder som att öppna en specifik tillgångssida eller utföra specifika åtgärdssteg.</span><span class="sxs-lookup"><span data-stu-id="15d89-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="15d89-116">Analysera påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="15d89-116">Analyze affected assets</span></span>
<span data-ttu-id="15d89-117">I avsnittet berörda tillgångar visas postlådor, enheter och användare som påverkas av den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="15d89-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="15d89-118">Om du markerar något av resurskorten fylls informationsfönstret i med information, inklusive andra aviseringar som rör tillgångarna, om det finns några.</span><span class="sxs-lookup"><span data-stu-id="15d89-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="15d89-119">Spåra en aviserings roll i aviseringsartikeln</span><span class="sxs-lookup"><span data-stu-id="15d89-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="15d89-120">I aviseringsartikeln visas alla tillgångar eller enheter som är relaterade till aviseringen i en processträdvy.</span><span class="sxs-lookup"><span data-stu-id="15d89-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="15d89-121">Aviseringen i rubriken är den som är i fokus när du först kommer till den valda aviseringens sida.</span><span class="sxs-lookup"><span data-stu-id="15d89-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="15d89-122">Tillgångar i aviseringsartikeln är expanderbara och klickbara.</span><span class="sxs-lookup"><span data-stu-id="15d89-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="15d89-123">De ger ytterligare information och snabb respons genom att göra det möjligt för dig att vidta åtgärder direkt i kontexten för aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="15d89-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="15d89-124">Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.</span><span class="sxs-lookup"><span data-stu-id="15d89-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="15d89-125">Visa mer aviseringsinformation i informationsfönstret</span><span class="sxs-lookup"><span data-stu-id="15d89-125">View more alert information in the details pane</span></span>

<span data-ttu-id="15d89-126">I informationsfönstret visas först information om den markerade aviseringen med information och relaterade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="15d89-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="15d89-127">Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationsfönstret för att ge sammanhangsberoende information och åtgärder för det valda objektet.</span><span class="sxs-lookup"><span data-stu-id="15d89-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="15d89-128">När du har valt en intresseenhet ändras informationsfönstret för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och alternativ för att vidta åtgärder på den här enheten direkt från aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="15d89-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="15d89-129">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="15d89-129">Manage alerts</span></span>

<span data-ttu-id="15d89-130">När du har undersökt aviseringarna kan du gå tillbaka till den avisering du började med, markera aviseringens status som Löst och klassificera den som en falsk avisering eller Sant-avisering.</span><span class="sxs-lookup"><span data-stu-id="15d89-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="15d89-131">Klassificera aviseringar hjälper till att finjustera produkten och ge mer sanna aviseringar och mindre falska aviseringar.</span><span class="sxs-lookup"><span data-stu-id="15d89-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="15d89-132">Ett sätt att hantera aviseringar via taggar.</span><span class="sxs-lookup"><span data-stu-id="15d89-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="15d89-133">Taggningsfunktioner för Microsoft Defender för Office 365 distribueras stegvis och är för närvarande i förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="15d89-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="15d89-134">För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="15d89-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="15d89-135">Aviseringar som skapades innan ändringen återspeglar inte det uppdaterade taggnamnet.</span><span class="sxs-lookup"><span data-stu-id="15d89-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="15d89-136">Hantera den enhetliga aviseringskön</span><span class="sxs-lookup"><span data-stu-id="15d89-136">Manage the unified alert queue</span></span>

<span data-ttu-id="15d89-137">Om du väljer Aviseringar & incidenter i navigeringsfönstret för Microsoft 365 säkerhetscenter kommer du till den enhetliga aviseringskön.</span><span class="sxs-lookup"><span data-stu-id="15d89-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="15d89-138">Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="15d89-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Bild av exempelaviseringssida](../../media/unified-alert-queue.png)

<span data-ttu-id="15d89-140">I kön Aviseringar visas en lista med aviseringar som har flaggats i nätverket.</span><span class="sxs-lookup"><span data-stu-id="15d89-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="15d89-141">Som standard visar kön aviseringar som har setts de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="15d89-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="15d89-142">De senaste aviseringarna visas högst upp i listan, vilket hjälper dig att se de senaste aviseringarna först.</span><span class="sxs-lookup"><span data-stu-id="15d89-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="15d89-143">Vid start har den enhetliga aviseringskön bara sju dagars tillgängligt aviseringar för Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="15d89-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="15d89-144">Kön fortsätter att byggas med tiden.</span><span class="sxs-lookup"><span data-stu-id="15d89-144">The queue will continue to build over time.</span></span> <span data-ttu-id="15d89-145">Om du behöver prioritera aviseringar innan den enhetliga aviseringskön startas använder du kön aviseringar i [Säkerhets- och efterlevnadscenter.](https://protection.office.com/viewalerts)</span><span class="sxs-lookup"><span data-stu-id="15d89-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="15d89-146">I det övre navigeringsfältet kan du:</span><span class="sxs-lookup"><span data-stu-id="15d89-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="15d89-147">Använda filter</span><span class="sxs-lookup"><span data-stu-id="15d89-147">Apply filters</span></span>
- <span data-ttu-id="15d89-148">Anpassa kolumner för att lägga till eller ta bort kolumner</span><span class="sxs-lookup"><span data-stu-id="15d89-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="15d89-149">Exportera data</span><span class="sxs-lookup"><span data-stu-id="15d89-149">Export data</span></span>

<span data-ttu-id="15d89-150">Du kan också filtrera aviseringar enligt olika villkor:</span><span class="sxs-lookup"><span data-stu-id="15d89-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="15d89-151">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="15d89-151">Severity</span></span>
- <span data-ttu-id="15d89-152">Status</span><span class="sxs-lookup"><span data-stu-id="15d89-152">Status</span></span>
- <span data-ttu-id="15d89-153">Kategori</span><span class="sxs-lookup"><span data-stu-id="15d89-153">Category</span></span>
- <span data-ttu-id="15d89-154">Identifieringskälla</span><span class="sxs-lookup"><span data-stu-id="15d89-154">Detection source</span></span>
- <span data-ttu-id="15d89-155">Princip</span><span class="sxs-lookup"><span data-stu-id="15d89-155">Policy</span></span>
- <span data-ttu-id="15d89-156">Påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="15d89-156">Impacted assets</span></span>
- <span data-ttu-id="15d89-157">Första aktiviteten</span><span class="sxs-lookup"><span data-stu-id="15d89-157">First activity</span></span>
- <span data-ttu-id="15d89-158">Senaste aktivitet</span><span class="sxs-lookup"><span data-stu-id="15d89-158">Last activity</span></span>


<span data-ttu-id="15d89-159">Information om hur du startar en undersökning av en händelse finns [i Undersöka incidenter i Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="15d89-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="15d89-160">Se även</span><span class="sxs-lookup"><span data-stu-id="15d89-160">See also</span></span>

- [<span data-ttu-id="15d89-161">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="15d89-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="15d89-162">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="15d89-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="15d89-163">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="15d89-163">Manage incidents</span></span>](manage-incidents.md)
