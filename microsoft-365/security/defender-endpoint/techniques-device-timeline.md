---
title: Tekniker på enhetens tidslinje
description: Förstå enhetens tidslinje i Microsoft Defender för Slutpunkt
keywords: tidslinje, slutpunkt, MITRE, MITRE ATT&CK, tekniker, taktiker
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185473"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="c8df5-104">Tekniker på enhetens tidslinje</span><span class="sxs-lookup"><span data-stu-id="c8df5-104">Techniques in the device timeline</span></span>


<span data-ttu-id="c8df5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c8df5-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8df5-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c8df5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="c8df5-107">Du kan få mer insyn i en undersökning genom att analysera händelserna på en viss enhet.</span><span class="sxs-lookup"><span data-stu-id="c8df5-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="c8df5-108">Välj först den enhet som är intressant i [listan Enheter](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c8df5-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="c8df5-109">På enhetens sida kan du välja fliken **Tidslinje** för att visa alla händelser som inträffat på enheten.</span><span class="sxs-lookup"><span data-stu-id="c8df5-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="c8df5-110">Förstå tekniker i tidslinjen</span><span class="sxs-lookup"><span data-stu-id="c8df5-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="c8df5-111">Viss information handlar om en förhandsversion av en produkt i en offentlig förhandsversion som kan komma att ändras väsentligt innan den släpps till allmänheten.</span><span class="sxs-lookup"><span data-stu-id="c8df5-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c8df5-112">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="c8df5-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c8df5-113">I Microsoft Defender för Slutpunkt **är Tekniker** ytterligare en datatyp i händelsetidslinjen.</span><span class="sxs-lookup"><span data-stu-id="c8df5-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="c8df5-114">Tekniker ger mer insyn i aktiviteter som associeras [med MITRE ATT&CK-tekniker](https://attack.mitre.org/) eller undertekniker.</span><span class="sxs-lookup"><span data-stu-id="c8df5-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="c8df5-115">Den här funktionen förenklar undersökningsupplevelsen genom att hjälpa analytiker att förstå de aktiviteter som observerats på en enhet.</span><span class="sxs-lookup"><span data-stu-id="c8df5-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="c8df5-116">Analytiker kan sedan bestämma sig för att undersöka ytterligare.</span><span class="sxs-lookup"><span data-stu-id="c8df5-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="c8df5-117">För offentlig förhandsgranskning är Tekniker tillgängliga som standard och visas tillsammans med händelser när en enhets tidslinje visas.</span><span class="sxs-lookup"><span data-stu-id="c8df5-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Skärmbild av tekniker på tidslinjen på enheten](images/device-timeline-2.png)

<span data-ttu-id="c8df5-119">Tekniker markeras i fetstil och visas med en blå ikon till vänster.</span><span class="sxs-lookup"><span data-stu-id="c8df5-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="c8df5-120">Motsvarande MITRE ATT&CK-ID och tekniknamn visas också som taggar under Ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="c8df5-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="c8df5-121">Sök- och exportalternativ är också tillgängliga för tekniker.</span><span class="sxs-lookup"><span data-stu-id="c8df5-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="c8df5-122">Undersöka användning av sidofönstret</span><span class="sxs-lookup"><span data-stu-id="c8df5-122">Investigate using the side pane</span></span>

<span data-ttu-id="c8df5-123">Välj en teknik för att öppna motsvarande sidofönster.</span><span class="sxs-lookup"><span data-stu-id="c8df5-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="c8df5-124">Här kan du se ytterligare information och insikter som relaterade ATT&CK-tekniker, taktiker och beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="c8df5-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="c8df5-125">Välj den specifika *attacktekniken* för att öppna den relaterade att&CK-tekniksidan där du kan hitta mer information om den.</span><span class="sxs-lookup"><span data-stu-id="c8df5-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="c8df5-126">Du kan kopiera information om en enhet när du ser en blå ikon till höger.</span><span class="sxs-lookup"><span data-stu-id="c8df5-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="c8df5-127">Om du till exempel vill kopiera den relaterade filens SHA1 väljer du den blå sidikonen.</span><span class="sxs-lookup"><span data-stu-id="c8df5-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Kopiera entitetsinformation](images/techniques-side-pane-clickable.png)

<span data-ttu-id="c8df5-129">Du kan göra samma sak för kommandorader.</span><span class="sxs-lookup"><span data-stu-id="c8df5-129">You can do the same for command lines.</span></span>

![Kopiera kommandorad](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="c8df5-131">Undersöka relaterade händelser</span><span class="sxs-lookup"><span data-stu-id="c8df5-131">Investigate related events</span></span>

<span data-ttu-id="c8df5-132">Om du [vill använda avancerad](advanced-hunting-overview.md) sökning för att hitta händelser relaterade till den valda tekniken väljer du Sök efter relaterade **händelser.**</span><span class="sxs-lookup"><span data-stu-id="c8df5-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="c8df5-133">Det leder till sidan för avancerad sökning med en fråga för att hitta händelser som hör till tekniken.</span><span class="sxs-lookup"><span data-stu-id="c8df5-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Leta efter relaterade händelser](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="c8df5-135">Vid sökning med **knappen Sök** efter relaterade händelser från sidofönstret Teknik visas alla händelser som hör till den identifierade tekniken, men själva tekniken ingår inte i frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="c8df5-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="c8df5-136">Anpassa enhetens tidslinje</span><span class="sxs-lookup"><span data-stu-id="c8df5-136">Customize your device timeline</span></span>

<span data-ttu-id="c8df5-137">Längst upp till höger på enhetens tidslinje kan du välja ett datumintervall för att begränsa antalet händelser och tekniker på tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="c8df5-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="c8df5-138">Du kan anpassa vilka kolumner som ska visas.</span><span class="sxs-lookup"><span data-stu-id="c8df5-138">You can customize which columns to expose.</span></span> <span data-ttu-id="c8df5-139">Du kan också filtrera efter flaggade händelser efter datatyp eller händelsegrupp.</span><span class="sxs-lookup"><span data-stu-id="c8df5-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="c8df5-140">Välj kolumner att visa</span><span class="sxs-lookup"><span data-stu-id="c8df5-140">Choose columns to expose</span></span>
<span data-ttu-id="c8df5-141">Du kan välja vilka kolumner som ska visas i tidslinjen genom att välja **knappen Välj** kolumner.</span><span class="sxs-lookup"><span data-stu-id="c8df5-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Anpassa kolumner](images/filter-customize-columns.png)

<span data-ttu-id="c8df5-143">Därifrån kan du välja vilken informationsuppsättning som ska inkluderas.</span><span class="sxs-lookup"><span data-stu-id="c8df5-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="c8df5-144">Filter för att endast visa tekniker eller händelser</span><span class="sxs-lookup"><span data-stu-id="c8df5-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="c8df5-145">Om du bara vill visa händelser eller tekniker väljer **du Filter** på enhetens tidslinje och väljer den datatyp du vill visa.</span><span class="sxs-lookup"><span data-stu-id="c8df5-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Skärmbild av filter](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="c8df5-147">Se även</span><span class="sxs-lookup"><span data-stu-id="c8df5-147">See also</span></span>
- [<span data-ttu-id="c8df5-148">Visa och ordna Enhetslista</span><span class="sxs-lookup"><span data-stu-id="c8df5-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="c8df5-149">Händelseflaggor i Microsoft Defender för slutpunktsenhetstid</span><span class="sxs-lookup"><span data-stu-id="c8df5-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
