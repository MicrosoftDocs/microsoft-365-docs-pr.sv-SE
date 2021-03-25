---
title: Händelsetidslinje med hantering av hot och hot
description: Händelsetidslinje är en nyhetsfeed för risker som hjälper dig att tolka hur risker introduceras i organisationen och vilka åtgärder som har åtgärdats för att minska den.
keywords: händelsetidslinje, tidslinje för mdatp-händelse, mdatp-händelsetidslinje, hot och sårbarhetshantering, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5532e9058d7a49033f651e3fbee605e5ae39d05a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076842"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="87ddb-104">Händelsetidslinje – hantering av hot och hot</span><span class="sxs-lookup"><span data-stu-id="87ddb-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="87ddb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="87ddb-105">**Applies to:**</span></span>
- [<span data-ttu-id="87ddb-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="87ddb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="87ddb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87ddb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="87ddb-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="87ddb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="87ddb-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="87ddb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="87ddb-110">Händelsetidslinje är en nyhetsfeed som hjälper dig att tolka hur risker införs i organisationen genom nya säkerhetsproblem eller sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="87ddb-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="87ddb-111">Du kan visa händelser som kan påverka organisationens risker.</span><span class="sxs-lookup"><span data-stu-id="87ddb-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="87ddb-112">Du kan till exempel hitta nya säkerhetsproblem som har introducerats, säkerhetsproblem som blev sårbarheter, sårbarheter som lagts till i en sårbarhetssats och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="87ddb-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="87ddb-113">Händelsetidslinje berättar även om [exponeringsresultatet](tvm-exposure-score.md) och [Microsoft Secure Score för](tvm-microsoft-secure-score-devices.md) enheter så att du kan fastställa orsaken till stora förändringar.</span><span class="sxs-lookup"><span data-stu-id="87ddb-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="87ddb-114">Händelser kan påverka dina enheter eller poäng för enheter.</span><span class="sxs-lookup"><span data-stu-id="87ddb-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="87ddb-115">Minska exponeringen genom att åtgärda vad som behöver åtgärdas baserat på de prioriterade [säkerhetsrekommendationerna.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="87ddb-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="87ddb-116">E-postmeddelanden om nya sårbarhetshändelser finns i [Konfigurera e-postaviseringar om säkerhetsrisk i Microsoft Defender för slutpunkt](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="87ddb-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="87ddb-117">Gå till sidan Händelsetidslinje</span><span class="sxs-lookup"><span data-stu-id="87ddb-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="87ddb-118">Det finns också tre inledningen till instrumentpanelen för hot [och sårbarhetshantering:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="87ddb-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="87ddb-119">**Styrkort för exponering för** organisation: Hovra över händelseträffarna i diagrammet "Exponeringsresultat över tid" och välj "Visa alla händelser från den här dagen".</span><span class="sxs-lookup"><span data-stu-id="87ddb-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="87ddb-120">Händelserna motsvarar säkerhetsproblem med programvara.</span><span class="sxs-lookup"><span data-stu-id="87ddb-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="87ddb-121">**Microsoft Secure Score för enheter:** Hovra över händelseträffarna i diagrammet "Poäng för enheter över tid" och välj "Visa alla händelser från den här dagen".</span><span class="sxs-lookup"><span data-stu-id="87ddb-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="87ddb-122">Händelserna representerar nya konfigurationsutvärderingar.</span><span class="sxs-lookup"><span data-stu-id="87ddb-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="87ddb-123">**De viktigaste** evenemangskorten: Välj "Visa mer" längst ned i den översta händelsetabellen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="87ddb-124">Kortet visar de tre mest effektfulla händelserna under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="87ddb-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="87ddb-125">Effektfulla händelser kan inkludera om händelsen påverkar ett stort antal enheter eller om det är ett kritiskt problem.</span><span class="sxs-lookup"><span data-stu-id="87ddb-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="87ddb-126">Exponeringsresultat och Microsoft Secure Score för enheter</span><span class="sxs-lookup"><span data-stu-id="87ddb-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="87ddb-127">I instrumentpanelen för hantering av hot och risker hovrar du över diagrammet med exponeringsresultat för att visa de viktigaste säkerhetshändelserna för programvara från den dagen som påverkade dina enheter.</span><span class="sxs-lookup"><span data-stu-id="87ddb-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="87ddb-128">Hovra över diagrammet Microsoft Secure Score för enheter för att visa nya säkerhetskonfigurationsutvärderingar som påverkar resultatet.</span><span class="sxs-lookup"><span data-stu-id="87ddb-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="87ddb-129">Om det inte finns några händelser som påverkar dina enheter eller ditt poängresultat för enheter visas ingen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="87ddb-130">![Hovra över ](images/tvm-event-timeline-exposure-score350.png) 
 ![ exponeringsresultat för Microsoft Secure Score för enheter – hovra](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="87ddb-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="87ddb-131">Öka detalj detalj detalj för händelser från den dagen</span><span class="sxs-lookup"><span data-stu-id="87ddb-131">Drill down to events from that day</span></span>

<span data-ttu-id="87ddb-132">Om **du väljer Visa alla händelser från** den här dagen kommer du till sidan Händelsetidslinje med ett anpassat datumintervall för den dagen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Händelsetidslinje valt anpassat datumintervall](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="87ddb-134">Välj **Anpassat område** om du vill ändra datumintervallet till ett annat anpassat, eller ett förinställt tidsperiodintervall.</span><span class="sxs-lookup"><span data-stu-id="87ddb-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Datumintervallsalternativ för händelsetidslinje](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="87ddb-136">Översikt över händelsetidslinje</span><span class="sxs-lookup"><span data-stu-id="87ddb-136">Event timeline overview</span></span>

<span data-ttu-id="87ddb-137">På sidan Händelsetidslinje kan du visa all nödvändig information som är relaterad till en händelse.</span><span class="sxs-lookup"><span data-stu-id="87ddb-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="87ddb-138">Funktioner:</span><span class="sxs-lookup"><span data-stu-id="87ddb-138">Features:</span></span>

- <span data-ttu-id="87ddb-139">Anpassa kolumner</span><span class="sxs-lookup"><span data-stu-id="87ddb-139">Customize columns</span></span>
- <span data-ttu-id="87ddb-140">Filtrera efter händelsetyp eller procent av påverkade enheter</span><span class="sxs-lookup"><span data-stu-id="87ddb-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="87ddb-141">Visa 30, 50 eller 100 objekt per sida</span><span class="sxs-lookup"><span data-stu-id="87ddb-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="87ddb-142">De två stora siffrorna längst upp på sidan visar antalet nya säkerhetsproblem och sårbarheter, inte händelser.</span><span class="sxs-lookup"><span data-stu-id="87ddb-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="87ddb-143">Vissa händelser kan ha flera säkerhetsproblem, och vissa säkerhetsproblem kan ha flera händelser.</span><span class="sxs-lookup"><span data-stu-id="87ddb-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Sidan Händelsetidslinje](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="87ddb-145">Kolumner</span><span class="sxs-lookup"><span data-stu-id="87ddb-145">Columns</span></span>

- <span data-ttu-id="87ddb-146">**Datum:** månad, dag, år</span><span class="sxs-lookup"><span data-stu-id="87ddb-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="87ddb-147">**Händelse**: effektfull händelse, inklusive komponent, typ och antal påverkade enheter</span><span class="sxs-lookup"><span data-stu-id="87ddb-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="87ddb-148">**Relaterad komponent:** programvara</span><span class="sxs-lookup"><span data-stu-id="87ddb-148">**Related component**: software</span></span>
- <span data-ttu-id="87ddb-149">**Ursprungligen påverkade enheter:** antalet och procentandelen påverkade enheter när den här händelsen ursprungligen inträffade.</span><span class="sxs-lookup"><span data-stu-id="87ddb-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="87ddb-150">Du kan också filtrera efter procentandelen ursprungligen påverkade enheter, av ditt totala antal enheter.</span><span class="sxs-lookup"><span data-stu-id="87ddb-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="87ddb-151">**Enheter som för närvarande påverkas**: aktuellt antal och procentandel av enheter som den här händelsen för närvarande påverkar.</span><span class="sxs-lookup"><span data-stu-id="87ddb-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="87ddb-152">Du hittar fältet genom att välja **Anpassa kolumner.**</span><span class="sxs-lookup"><span data-stu-id="87ddb-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="87ddb-153">**Typer**: speglar tidsstämplade händelser som påverkar poängen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="87ddb-154">De kan filtreras.</span><span class="sxs-lookup"><span data-stu-id="87ddb-154">They can be filtered.</span></span>
    - <span data-ttu-id="87ddb-155">Sårbarhet tillagd i en sårbarhetssats</span><span class="sxs-lookup"><span data-stu-id="87ddb-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="87ddb-156">Sårbarhet har verifierats</span><span class="sxs-lookup"><span data-stu-id="87ddb-156">Exploit was verified</span></span>
    - <span data-ttu-id="87ddb-157">Ny offentlig sårbarhet</span><span class="sxs-lookup"><span data-stu-id="87ddb-157">New public exploit</span></span>
    - <span data-ttu-id="87ddb-158">Ny sårbarhet</span><span class="sxs-lookup"><span data-stu-id="87ddb-158">New vulnerability</span></span>
    - <span data-ttu-id="87ddb-159">Ny konfigurationsutvärdering</span><span class="sxs-lookup"><span data-stu-id="87ddb-159">New configuration assessment</span></span>
- <span data-ttu-id="87ddb-160">**Poängtrend**: trend för exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="87ddb-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="87ddb-161">Ikoner</span><span class="sxs-lookup"><span data-stu-id="87ddb-161">Icons</span></span>

<span data-ttu-id="87ddb-162">Följande ikoner visas bredvid händelser:</span><span class="sxs-lookup"><span data-stu-id="87ddb-162">The following icons show up next to events:</span></span>

- ![felikon](images/tvm-black-bug-icon.png) <span data-ttu-id="87ddb-164">Ny offentlig sårbarhet</span><span class="sxs-lookup"><span data-stu-id="87ddb-164">New public exploit</span></span>
- ![varningsikon för rapport](images/report-warning-icon.png) <span data-ttu-id="87ddb-166">Ny sårbarhet publicerades</span><span class="sxs-lookup"><span data-stu-id="87ddb-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="87ddb-168">Sårbarhet som hittas i sårbarhetskit</span><span class="sxs-lookup"><span data-stu-id="87ddb-168">Exploit found in exploit kit</span></span>
- ![felikon med varningsikon](images/bug-caution-icon2.png) <span data-ttu-id="87ddb-170">Sårbarhet verifierad</span><span class="sxs-lookup"><span data-stu-id="87ddb-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="87ddb-171">Öka detalj detalj för en viss händelse</span><span class="sxs-lookup"><span data-stu-id="87ddb-171">Drill down to a specific event</span></span>

<span data-ttu-id="87ddb-172">När du har valt en händelse visas en utfäll kant med en lista över information och aktuella CV:n som påverkar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="87ddb-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="87ddb-173">Du kan visa fler CV:er eller visa den relaterade rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="87ddb-174">Pilen under "poängtrend" hjälper dig att avgöra om händelsen eventuellt höjer eller sänker exponeringsresultatet för organisationen.</span><span class="sxs-lookup"><span data-stu-id="87ddb-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="87ddb-175">Högre exponeringsresultat innebär att enheter är mer sårbara för användning.</span><span class="sxs-lookup"><span data-stu-id="87ddb-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Utfällning av händelsetidslinje](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="87ddb-177">Därifrån väljer du Gå **till relaterad säkerhetsrekommendationer,** se rekommendationen som handlar om den nya programsäkerhetsproblemen på [sidan med säkerhetsrekommendationer.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="87ddb-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="87ddb-178">När du har läst beskrivningen och sårbarhetsinformationen i säkerhetsrekommendationern kan du skicka en begäran om åtgärder och spåra begäran på [sidan För att åtgärda.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="87ddb-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="87ddb-179">Visa tidslinjer för händelser på programvarusidor</span><span class="sxs-lookup"><span data-stu-id="87ddb-179">View Event timelines in software pages</span></span>

<span data-ttu-id="87ddb-180">Om du vill öppna en programvarusida väljer du en händelse > väljer det hyperlänkade programvarunamnet (till exempel Visual Studio 2017) i avsnittet "Related component" i den utfällbar menyn.</span><span class="sxs-lookup"><span data-stu-id="87ddb-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="87ddb-181">Läs mer om programvarusidor</span><span class="sxs-lookup"><span data-stu-id="87ddb-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="87ddb-182">En hel sida med all information om en viss programvara visas.</span><span class="sxs-lookup"><span data-stu-id="87ddb-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="87ddb-183">Håll muspekaren över diagrammet för att se tidslinjen för händelser för den specifika programvaran.</span><span class="sxs-lookup"><span data-stu-id="87ddb-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Programvarusida med ett tidslinjediagram för en händelse](images/tvm-event-timeline-software2.png)

<span data-ttu-id="87ddb-185">Gå till fliken händelsetidslinje för att visa alla händelser som hör till den programvaran.</span><span class="sxs-lookup"><span data-stu-id="87ddb-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="87ddb-186">Du kan även se säkerhetsrekommendationer, identifierade säkerhetsproblem, installerade enheter och versionsdistribution.</span><span class="sxs-lookup"><span data-stu-id="87ddb-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Programvarusida med en tidslinjeflik för en händelse](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="87ddb-188">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="87ddb-188">Related topics</span></span>

- [<span data-ttu-id="87ddb-189">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="87ddb-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="87ddb-190">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="87ddb-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="87ddb-191">Exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="87ddb-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="87ddb-192">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="87ddb-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="87ddb-193">Åtgärda säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="87ddb-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="87ddb-194">Inventering av programvara</span><span class="sxs-lookup"><span data-stu-id="87ddb-194">Software inventory</span></span>](tvm-software-inventory.md)

