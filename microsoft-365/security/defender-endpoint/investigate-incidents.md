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
ms.openlocfilehash: 1d8f4452273047684a30db3b18d1281f40f46378
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903304"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a3a7f-104">Undersöka incidenter i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="a3a7f-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3a7f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a3a7f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a3a7f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a7f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a3a7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3a7f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="a3a7f-108">Undersök incidenter som påverkar nätverket, förstå vad de betyder och samla bevis för att lösa dem.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="a3a7f-109">När du undersöker en händelse ser du:</span><span class="sxs-lookup"><span data-stu-id="a3a7f-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="a3a7f-110">Incidentinformation</span><span class="sxs-lookup"><span data-stu-id="a3a7f-110">Incident details</span></span>
- <span data-ttu-id="a3a7f-111">Incidentkommentarer och åtgärder</span><span class="sxs-lookup"><span data-stu-id="a3a7f-111">Incident comments and actions</span></span>
- <span data-ttu-id="a3a7f-112">Flikar (aviseringar, enheter, undersökningar, bevis, diagram)</span><span class="sxs-lookup"><span data-stu-id="a3a7f-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="a3a7f-113">Analysera incidentinformation</span><span class="sxs-lookup"><span data-stu-id="a3a7f-113">Analyze incident details</span></span> 
<span data-ttu-id="a3a7f-114">Klicka på en incident om du vill **visa fönstret Incident.**</span><span class="sxs-lookup"><span data-stu-id="a3a7f-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="a3a7f-115">Välj **Öppna incidentsida om** du vill se incidentinformation och relaterad information (aviseringar, enheter, undersökningar, bevis, graf).</span><span class="sxs-lookup"><span data-stu-id="a3a7f-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Bild på incidentinformation1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="a3a7f-117">Varningar</span><span class="sxs-lookup"><span data-stu-id="a3a7f-117">Alerts</span></span>
<span data-ttu-id="a3a7f-118">Du kan undersöka aviseringarna och se hur de länkades ihop vid en incident.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="a3a7f-119">Aviseringar grupperas i incidenter baserat på följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="a3a7f-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="a3a7f-120">Automatisk undersökning – Den automatiska undersökningen utlöste den länkade aviseringen när den ursprungliga aviseringen undersöks</span><span class="sxs-lookup"><span data-stu-id="a3a7f-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="a3a7f-121">Filegenskaper – De filer som är associerade med aviseringen har liknande egenskaper</span><span class="sxs-lookup"><span data-stu-id="a3a7f-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="a3a7f-122">Manuell koppling – En användare länkade aviseringarna manuellt</span><span class="sxs-lookup"><span data-stu-id="a3a7f-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="a3a7f-123">Proximatisk tid – Aviseringarna utlöstes på samma enhet inom en viss tidsperiod</span><span class="sxs-lookup"><span data-stu-id="a3a7f-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="a3a7f-124">Samma fil – Filerna som är associerade med aviseringen är exakt likadana</span><span class="sxs-lookup"><span data-stu-id="a3a7f-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="a3a7f-125">Samma URL – URL:en som utlöste aviseringen är exakt samma</span><span class="sxs-lookup"><span data-stu-id="a3a7f-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Bild av fliken Aviseringar med sidan Incidentinformation som visar orsakerna till att aviseringarna har länkats ihop till händelsen](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="a3a7f-127">Du kan också hantera en avisering och se metadata för aviseringar tillsammans med annan information.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="a3a7f-128">Mer information finns i [Undersöka aviseringar](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="a3a7f-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="a3a7f-129">Enheter</span><span class="sxs-lookup"><span data-stu-id="a3a7f-129">Devices</span></span>
<span data-ttu-id="a3a7f-130">Du kan också undersöka vilka enheter som är en del av eller relaterade till en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="a3a7f-131">Mer information finns i [Undersöka enheter](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="a3a7f-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Bild på fliken Enheter på sidan incidentinformation](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="a3a7f-133">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="a3a7f-133">Investigations</span></span>
<span data-ttu-id="a3a7f-134">Välj **Undersökningar** om du vill se alla automatiska undersökningar som startats av systemet som svar på incidentaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Bild på fliken undersökningar på incidentinformationssidan](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="a3a7f-136">Gå igenom bevisen</span><span class="sxs-lookup"><span data-stu-id="a3a7f-136">Going through the evidence</span></span>
<span data-ttu-id="a3a7f-137">Microsoft Defender för slutpunkt undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga filer, processer, tjänster och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="a3a7f-138">Alla analyserade enheter markeras som smittade, åtgärdade eller misstänkta.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Bild av bevisfliken på sidan incidentinformation](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="a3a7f-140">Visualisera associerade hot mot cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="a3a7f-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="a3a7f-141">Microsoft Defender för Endpoint sammanställer hotinformationen till en incident så att du kan se de mönster och korrelationer som kommer in från olika datapunkter.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="a3a7f-142">Du kan visa en sådan korrelation via incidentdiagrammet.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="a3a7f-143">Incidentdiagram</span><span class="sxs-lookup"><span data-stu-id="a3a7f-143">Incident graph</span></span>
<span data-ttu-id="a3a7f-144">Graph **berättar** om cybersäkerhetsattacken.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="a3a7f-145">Den visar till exempel vad som var startpunkten, vilken indikator på kompromettering eller aktivitet som observerats på vilken enhet.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="a3a7f-146">o.s.v.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-146">etc.</span></span>

![Bild av incidentdiagrammet](images/atp-incident-graph-tab.png)

<span data-ttu-id="a3a7f-148">Du kan klicka på cirklarna i incidentdiagrammet för att visa information om skadliga filer, associerade filidentifieringar, hur många förekomster som har gjorts i hela världen, om det har observerats i organisationen, i så fall hur många instanser.</span><span class="sxs-lookup"><span data-stu-id="a3a7f-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Bild på incidentinformation](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="a3a7f-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a3a7f-150">Related topics</span></span>
- [<span data-ttu-id="a3a7f-151">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="a3a7f-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="a3a7f-152">Undersöka incidenter i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="a3a7f-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="a3a7f-153">Hantera Microsoft Defender för slutpunktsincidenter</span><span class="sxs-lookup"><span data-stu-id="a3a7f-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
