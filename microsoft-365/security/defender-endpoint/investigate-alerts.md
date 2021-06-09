---
title: Undersöka Microsoft Defender för slutpunktsaviseringar
description: Använd alternativen för undersökning för att få information om aviseringar påverkar nätverket, vad de betyder och hur du kan lösa dem.
keywords: undersök, undersökning, enheter, enhet, aviseringar, instrumentpanel, IP-adress, fil, skicka, inskickade data, djupanalys, tidslinje, sökning, domän, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841096"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7f3c-104">Undersöka aviseringar i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="b7f3c-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7f3c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b7f3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7f3c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7f3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7f3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7f3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b7f3c-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b7f3c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7f3c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="b7f3c-110">Undersök aviseringar som påverkar nätverket, förstå vad de betyder och hur du löser dem.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="b7f3c-111">Välj en avisering från aviseringskön för att gå till aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="b7f3c-112">Den här vyn innehåller aviseringsrubriken, de berörda tillgångarna, informationsfönstret och aviseringsartikeln.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="b7f3c-113">Från aviseringssidan börjar du din undersökning genom att välja de berörda tillgångarna eller någon av enheterna under trädvyn för aviseringsartikeln.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="b7f3c-114">Informationsfönstret fylls automatiskt i med ytterligare information om det du har markerat.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="b7f3c-115">Om du vill se vilken typ av information du kan visa här kan du läsa [Granska aviseringar i Microsoft Defender för slutpunkt.](/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="b7f3c-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="b7f3c-116">Undersök användning av aviseringsartikeln</span><span class="sxs-lookup"><span data-stu-id="b7f3c-116">Investigate using the alert story</span></span>

<span data-ttu-id="b7f3c-117">Information om aviseringsinformationen varför aviseringen utlöstes, relaterade händelser som inträffat före och efter, samt andra relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="b7f3c-118">Enheter är klickbara och alla enheter som inte är en avisering kan utökas med hjälp av expanderikonen på höger sida av enhetens kort.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="b7f3c-119">Enheten i fokus anges med ett blått band till vänster om enhetens kort, med varningen i fokus först.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="b7f3c-120">Utöka enheterna för att få en snabb överblick över informationen.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="b7f3c-121">När du väljer en entitet växlas kontexten för informationsfönstret till den här enheten och du kan granska ytterligare information och hantera den enheten.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="b7f3c-122">Om *du markerar ...* till höger om entitetskortet visas alla åtgärder som är tillgängliga för den enheten.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="b7f3c-123">Samma åtgärder visas i informationsfönstret när entiteten är i fokus.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="b7f3c-124">Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Ett exempel på en aviseringsartikel med en varning i fokus och några expanderade kort](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="b7f3c-126">Vidta åtgärder från informationsfönstret</span><span class="sxs-lookup"><span data-stu-id="b7f3c-126">Take action from the details pane</span></span>

<span data-ttu-id="b7f3c-127">När du har valt en intresseenhet ändras informationsfönstret för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och erbjuder kontroller för att vidta åtgärder på den här enheten direkt från aviseringssidan. </span><span class="sxs-lookup"><span data-stu-id="b7f3c-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="b7f3c-128">När du har undersökt klart går du tillbaka till den avisering  du började med, markerar aviseringens status som Löst och klassificerar den som antingen **Falsk avisering** eller **Sant-avisering.**</span><span class="sxs-lookup"><span data-stu-id="b7f3c-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="b7f3c-129">Klassificera aviseringar hjälper till att finjustera den här funktionen för att ge mer sanna aviseringar och mindre falska aviseringar.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="b7f3c-130">Om du klassificerar det som en verklig varning kan du också välja ett avgörande, som visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Ett avsnitt av informationsfönstret med en löst avisering och den expanderade listrutan för determination](images/alert-details-resolved-true.png)

<span data-ttu-id="b7f3c-132">Om du får en falsk avisering med ett affärsprogram skapar du en regel för att undvika den här typen av avisering i framtiden.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![åtgärder och klassificering i informationsfönstret med regeln markerad](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="b7f3c-134">Om du har problem som inte beskrivs ovan kan du använda knappen för 🙂 att ge feedback eller öppna ett supportärenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b7f3c-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b7f3c-135">Related topics</span></span>
- [<span data-ttu-id="b7f3c-136">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="b7f3c-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="b7f3c-137">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="b7f3c-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="b7f3c-138">Undersöka en fil som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="b7f3c-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="b7f3c-139">Undersök enheter i listan Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="b7f3c-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="b7f3c-140">Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="b7f3c-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="b7f3c-141">Undersöka en domän som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="b7f3c-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="b7f3c-142">Undersöka ett användarkonto i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="b7f3c-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


