---
title: Undersöka incidenter i Microsoft Defender för Slutpunkt
description: Se associerade aviseringar, hantera händelsen och se metadata för aviseringar som hjälper dig att undersöka en händelse
keywords: undersöker, incident, aviseringar, metadata, risk, identifieringskälla, påverkade enheter, mönster, korrelation
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
ms.technology: mde
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845084"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="89d87-104">Undersöka incidenter i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="89d87-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89d87-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="89d87-105">**Applies to:**</span></span>
- [<span data-ttu-id="89d87-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="89d87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89d87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89d87-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="89d87-108">Undersök incidenter som påverkar nätverket, förstå vad de betyder och samla bevis för att lösa dem.</span><span class="sxs-lookup"><span data-stu-id="89d87-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="89d87-109">När du undersöker en händelse ser du:</span><span class="sxs-lookup"><span data-stu-id="89d87-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="89d87-110">Incidentinformation</span><span class="sxs-lookup"><span data-stu-id="89d87-110">Incident details</span></span>
- <span data-ttu-id="89d87-111">Incidentkommentarer och åtgärder</span><span class="sxs-lookup"><span data-stu-id="89d87-111">Incident comments and actions</span></span>
- <span data-ttu-id="89d87-112">Flikar (aviseringar, enheter, undersökningar, bevis, diagram)</span><span class="sxs-lookup"><span data-stu-id="89d87-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="89d87-113">Analysera incidentinformation</span><span class="sxs-lookup"><span data-stu-id="89d87-113">Analyze incident details</span></span> 
<span data-ttu-id="89d87-114">Klicka på en incident om du vill **visa fönstret Incident.**</span><span class="sxs-lookup"><span data-stu-id="89d87-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="89d87-115">Välj **Öppna incidentsida om** du vill se incidentinformation och relaterad information (aviseringar, enheter, undersökningar, bevis, graf).</span><span class="sxs-lookup"><span data-stu-id="89d87-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Bild på incidentinformation1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="89d87-117">Varningar</span><span class="sxs-lookup"><span data-stu-id="89d87-117">Alerts</span></span>
<span data-ttu-id="89d87-118">Du kan undersöka aviseringarna och se hur de länkades ihop vid en incident.</span><span class="sxs-lookup"><span data-stu-id="89d87-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="89d87-119">Aviseringar grupperas i incidenter baserat på följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="89d87-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="89d87-120">Automatisk undersökning – Den automatiska undersökningen utlöste den länkade aviseringen när den ursprungliga aviseringen undersöks</span><span class="sxs-lookup"><span data-stu-id="89d87-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="89d87-121">Filegenskaper – De filer som är associerade med aviseringen har liknande egenskaper</span><span class="sxs-lookup"><span data-stu-id="89d87-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="89d87-122">Manuell koppling – En användare länkade aviseringarna manuellt</span><span class="sxs-lookup"><span data-stu-id="89d87-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="89d87-123">Proximatisk tid – Aviseringarna utlöstes på samma enhet inom en viss tidsperiod</span><span class="sxs-lookup"><span data-stu-id="89d87-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="89d87-124">Samma fil – Filerna som är associerade med aviseringen är exakt likadana</span><span class="sxs-lookup"><span data-stu-id="89d87-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="89d87-125">Samma URL – URL:en som utlöste aviseringen är exakt samma</span><span class="sxs-lookup"><span data-stu-id="89d87-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Bild av fliken Aviseringar med sidan Incidentinformation som visar orsakerna till att aviseringarna har länkats ihop till händelsen](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="89d87-127">Du kan också hantera en avisering och se metadata för aviseringar tillsammans med annan information.</span><span class="sxs-lookup"><span data-stu-id="89d87-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="89d87-128">Mer information finns i [Undersöka aviseringar](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="89d87-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="89d87-129">Enheter</span><span class="sxs-lookup"><span data-stu-id="89d87-129">Devices</span></span>
<span data-ttu-id="89d87-130">Du kan också undersöka vilka enheter som är en del av eller relaterade till en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="89d87-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="89d87-131">Mer information finns i [Undersöka enheter](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="89d87-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Bild på fliken Enheter på sidan incidentinformation](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="89d87-133">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="89d87-133">Investigations</span></span>
<span data-ttu-id="89d87-134">Välj **Undersökningar** om du vill se alla automatiska undersökningar som startats av systemet som svar på incidentaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="89d87-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Bild på fliken undersökningar på incidentinformationssidan](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="89d87-136">Gå igenom bevisen</span><span class="sxs-lookup"><span data-stu-id="89d87-136">Going through the evidence</span></span>
<span data-ttu-id="89d87-137">Microsoft Defender för slutpunkt undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga filer, processer, tjänster och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="89d87-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="89d87-138">Alla analyserade enheter markeras som smittade, åtgärdade eller misstänkta.</span><span class="sxs-lookup"><span data-stu-id="89d87-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Bild av bevisfliken på sidan incidentinformation](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="89d87-140">Visualisera associerade hot mot cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="89d87-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="89d87-141">Microsoft Defender för Endpoint sammanställer hotinformationen till en incident så att du kan se de mönster och korrelationer som kommer in från olika datapunkter.</span><span class="sxs-lookup"><span data-stu-id="89d87-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="89d87-142">Du kan visa en sådan korrelation via incidentdiagrammet.</span><span class="sxs-lookup"><span data-stu-id="89d87-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="89d87-143">Incidentdiagram</span><span class="sxs-lookup"><span data-stu-id="89d87-143">Incident graph</span></span>
<span data-ttu-id="89d87-144">The **Graph** berättar om cybersäkerhetsattacken.</span><span class="sxs-lookup"><span data-stu-id="89d87-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="89d87-145">Den visar till exempel vad som var startpunkten, vilken indikator på kompromettering eller aktivitet som observerats på vilken enhet.</span><span class="sxs-lookup"><span data-stu-id="89d87-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="89d87-146">o.s.v.</span><span class="sxs-lookup"><span data-stu-id="89d87-146">etc.</span></span>

![Bild av incidentdiagrammet](images/atp-incident-graph-tab.png)

<span data-ttu-id="89d87-148">Du kan klicka på cirklarna i incidentdiagrammet för att visa information om skadliga filer, associerade filidentifieringar, hur många förekomster som har gjorts i hela världen, om det har observerats i organisationen, i så fall hur många instanser.</span><span class="sxs-lookup"><span data-stu-id="89d87-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Bild på incidentinformation](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="89d87-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="89d87-150">Related topics</span></span>
- [<span data-ttu-id="89d87-151">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="89d87-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="89d87-152">Undersöka incidenter i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="89d87-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="89d87-153">Hantera Microsoft Defender för slutpunktsincidenter</span><span class="sxs-lookup"><span data-stu-id="89d87-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)
