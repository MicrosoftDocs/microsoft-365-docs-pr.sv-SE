---
title: Instrumentpanel för Säkerhetscenter-åtgärder i Microsoft Defender Säkerhetscenter
description: Använd instrumentpanelen för att identifiera enheter som är riskerade, håll reda på status för tjänsten och se statistik och information om enheter och aviseringar.
keywords: instrumentpanel, aviseringar, ny, pågående, löst, risk, enheter för risk, rapportering, statistik, diagram, diagram, hälsa, active malware detections, hotkategori, kategorier, lösenords stjäla, utpressningstrojaner, sårbarhet, hot, låg allvarlighetsgrad, aktiv skadlig kod
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072953"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="14036-104">Instrumentpanel för Säkerhetscenter-åtgärder i Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="14036-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="14036-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="14036-105">**Applies to:**</span></span>
- [<span data-ttu-id="14036-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="14036-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="14036-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="14036-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="14036-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="14036-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="14036-109">Instrumentpanelen **för säkerhetsåtgärder** är den plats där funktionerna för identifiering av slutpunkter och svar visas.</span><span class="sxs-lookup"><span data-stu-id="14036-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="14036-110">Den ger en översikt över var identifieringar har setts och markerar var svarsåtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="14036-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="14036-111">Instrumentpanelen visar en ögonblicksbild av:</span><span class="sxs-lookup"><span data-stu-id="14036-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="14036-112">Aktiva aviseringar</span><span class="sxs-lookup"><span data-stu-id="14036-112">Active alerts</span></span>
- <span data-ttu-id="14036-113">Enheter som är riskfyllda</span><span class="sxs-lookup"><span data-stu-id="14036-113">Devices at risk</span></span>
- <span data-ttu-id="14036-114">Sensorhälsa</span><span class="sxs-lookup"><span data-stu-id="14036-114">Sensor health</span></span>
- <span data-ttu-id="14036-115">Tjänstens hälsa</span><span class="sxs-lookup"><span data-stu-id="14036-115">Service health</span></span>
- <span data-ttu-id="14036-116">Daglig rapportering om enheter</span><span class="sxs-lookup"><span data-stu-id="14036-116">Daily devices reporting</span></span>
- <span data-ttu-id="14036-117">Aktiva automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="14036-117">Active automated investigations</span></span>
- <span data-ttu-id="14036-118">Automatisera undersökningar – statistik</span><span class="sxs-lookup"><span data-stu-id="14036-118">Automated investigations statistics</span></span>
- <span data-ttu-id="14036-119">Användare i riskabelt-för-</span><span class="sxs-lookup"><span data-stu-id="14036-119">Users at risk</span></span>
- <span data-ttu-id="14036-120">Misstänkta aktiviteter</span><span class="sxs-lookup"><span data-stu-id="14036-120">Suspicious activities</span></span>


![Bild av instrumentpanelen för säkerhetsåtgärder](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="14036-122">Du kan utforska och undersöka aviseringar och enheter för att snabbt avgöra om, var och när misstänkta aktiviteter inträffade i nätverket för att hjälpa dig att förstå kontexten de visades i.</span><span class="sxs-lookup"><span data-stu-id="14036-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="14036-123">Från **instrumentpanelen för säkerhetsåtgärder** ser du aggregerade händelser för att underlätta identifiering av viktiga händelser eller beteenden på en enhet.</span><span class="sxs-lookup"><span data-stu-id="14036-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="14036-124">Du kan också öka detaljnivån för detaljerade händelser och indikatorer på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="14036-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="14036-125">Den har också klickbara paneler som ger visuella ledtrådar om organisationens allmänna status.</span><span class="sxs-lookup"><span data-stu-id="14036-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="14036-126">Varje panel öppnar en detaljerad vy av motsvarande översikt.</span><span class="sxs-lookup"><span data-stu-id="14036-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="14036-127">Aktiva aviseringar</span><span class="sxs-lookup"><span data-stu-id="14036-127">Active alerts</span></span>
<span data-ttu-id="14036-128">Du kan visa det totala antalet aktiva aviseringar från de senaste 30 dagarna i nätverket från panelen.</span><span class="sxs-lookup"><span data-stu-id="14036-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="14036-129">Aviseringar grupperas i **Nytt** och **Pågående**.</span><span class="sxs-lookup"><span data-stu-id="14036-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Klicka på varje sektor eller allvarlighetsgrad för att se en lista med aviseringar från de senaste 30 dagarna](images/active-alerts-tile.png)

<span data-ttu-id="14036-131">Varje grupp kategoriseras ytterligare i motsvarande allvarlighetsnivå för aviseringar.</span><span class="sxs-lookup"><span data-stu-id="14036-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="14036-132">Klicka på antalet aviseringar i varje aviseringsring om du vill se en sorterad vy av den kategorins kö **(Ny** eller **Pågår).**</span><span class="sxs-lookup"><span data-stu-id="14036-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="14036-133">Mer information finns i Översikt [över aviseringar.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="14036-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="14036-134">Varje rad innehåller en kategori med en aviserings allvarlighetsgrad och en kort beskrivning av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="14036-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="14036-135">Du kan klicka på en avisering om du vill se den detaljerade vyn.</span><span class="sxs-lookup"><span data-stu-id="14036-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="14036-136">Mer information finns i Undersök [Microsoft Defender för slutpunktsaviseringar och](investigate-alerts.md) [översikten Aviseringar.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="14036-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="14036-137">Enheter som är riskfyllda</span><span class="sxs-lookup"><span data-stu-id="14036-137">Devices at risk</span></span>
<span data-ttu-id="14036-138">På panelen visas en lista över enheter med det högsta antalet aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="14036-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="14036-139">Det totala antalet aviseringar för varje enhet visas i en cirkel bredvid enhetens namn och kategoriseras ytterligare efter allvarlighetsnivå längst ut i panelen (hovra över varje allvarlighetsfält om du vill se dess etikett).</span><span class="sxs-lookup"><span data-stu-id="14036-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![På panelen Enheter vid risk visas en lista över enheter med det högsta antalet aviseringar och en uppdelning av varningarnas allvarlighetsgrad](images/devices-at-risk-tile.png)

<span data-ttu-id="14036-141">Klicka på enhetens namn om du vill se information om den enheten.</span><span class="sxs-lookup"><span data-stu-id="14036-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="14036-142">Mer information finns i Undersöka [enheter i listan Microsoft Defender för slutpunktsenheter.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="14036-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="14036-143">Du kan också klicka **på Listan** Enheter högst upp på panelen för att gå direkt till listan Enheter **,** sorterad efter antalet aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="14036-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="14036-144">Mer information finns i Undersöka [enheter i listan Microsoft Defender för slutpunktsenheter.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="14036-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="14036-145">Enheter med sensorproblem</span><span class="sxs-lookup"><span data-stu-id="14036-145">Devices with sensor issues</span></span>
<span data-ttu-id="14036-146">Panelen **Enheter med sensorproblem** ger information om den enskilda enhetens möjlighet att ge sensordata till Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="14036-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="14036-147">Den rapporterar hur många enheter som kräver uppmärksamhet och hjälper dig att identifiera problematiska enheter.</span><span class="sxs-lookup"><span data-stu-id="14036-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Panelen enheter med sensorproblem](images/atp-tile-sensor-health.png)

<span data-ttu-id="14036-149">Det finns två statusindikatorer med information om antalet enheter som inte rapporterar korrekt till tjänsten:</span><span class="sxs-lookup"><span data-stu-id="14036-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="14036-150">**Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Microsoft Defender för Slutpunkt-tjänsten och kan ha konfigurationsfel som behöver korrigeras.</span><span class="sxs-lookup"><span data-stu-id="14036-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="14036-151">**Inaktiva** – Enheter som har slutat rapportera till Microsoft Defender för slutpunktstjänsten under mer än sju dagar den senaste månaden.</span><span class="sxs-lookup"><span data-stu-id="14036-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="14036-152">När du klickar på någon av grupperna dirigeras du till listan över enheter, filtrerade enligt ditt val.</span><span class="sxs-lookup"><span data-stu-id="14036-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="14036-153">Mer information finns i Kontrollera [sensortillståndet](check-sensor-status.md) och [Undersöka enheter.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="14036-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="14036-154">Tjänstens hälsa</span><span class="sxs-lookup"><span data-stu-id="14036-154">Service health</span></span>
<span data-ttu-id="14036-155">Panelen **Tjänstens** hälsa informerar dig om tjänsten är aktiv eller om det är problem.</span><span class="sxs-lookup"><span data-stu-id="14036-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![Panelen Tjänstens hälsa visar en övergripande indikator på tjänsten](images/status-tile.png)

<span data-ttu-id="14036-157">Mer information om tjänstens hälsa finns i [Kontrollera tjänstens hälsa för Microsoft Defender.](service-status.md)</span><span class="sxs-lookup"><span data-stu-id="14036-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="14036-158">Daglig rapportering om enheter</span><span class="sxs-lookup"><span data-stu-id="14036-158">Daily devices reporting</span></span>
<span data-ttu-id="14036-159">På **panelen för daglig rapportering** visas ett stapeldiagram som representerar antalet enheter som rapporterar dagligen under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="14036-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="14036-160">Hovra över enskilda staplar i diagrammet för att se det exakta antalet enheter som rapporterar varje dag.</span><span class="sxs-lookup"><span data-stu-id="14036-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Bild på rapportpanel för dagliga enheter](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="14036-162">Aktiva automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="14036-162">Active automated investigations</span></span>
<span data-ttu-id="14036-163">Du kan visa det totala antalet automatiserade undersökningar från de senaste 30 dagarna i nätverket från panelen för **automatiska aktiv undersökningar.**</span><span class="sxs-lookup"><span data-stu-id="14036-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="14036-164">Undersökningar grupperas i **Väntande åtgärd**, **Väntar på enhet** och **Körs**.</span><span class="sxs-lookup"><span data-stu-id="14036-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Drift av aktiva automatiserade undersökningar](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="14036-166">Automatisera undersökningar – statistik</span><span class="sxs-lookup"><span data-stu-id="14036-166">Automated investigations statistics</span></span>
<span data-ttu-id="14036-167">I panelen visas statistik som är relaterad till automatiserade undersökningar de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="14036-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="14036-168">Den visar antalet undersökningar som slutförts, antalet slutförda undersökningar, den genomsnittliga väntande tiden det tar för en undersökning att initieras, den genomsnittliga tiden det tar att åtgärda en avisering, antalet aviseringar som undersökts och antalet timmar av automatisering som sparats från en vanlig manuell undersökning.</span><span class="sxs-lookup"><span data-stu-id="14036-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Bild av automatiserad statistik för undersökningar](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="14036-170">Du kan klicka på  **Automatiserade** undersökningar, **åtgärdade** undersökningar och aviseringar som har **undersökts** för att navigera till sidan Undersökningar, filtrerad efter lämplig kategori.</span><span class="sxs-lookup"><span data-stu-id="14036-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="14036-171">På så sätt kan du se en detaljerad uppdelning av undersökningar i sammanhanget.</span><span class="sxs-lookup"><span data-stu-id="14036-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="14036-172">Användare i riskabelt-för-</span><span class="sxs-lookup"><span data-stu-id="14036-172">Users at risk</span></span>
<span data-ttu-id="14036-173">Panelen visar en lista över användarkonton med de mest aktiva aviseringarna och antalet aviseringar som visas på höga, medelstora eller låga aviseringar.</span><span class="sxs-lookup"><span data-stu-id="14036-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![Användarkonton på riskpanelen visar en lista över användarkonton med det högsta antalet aviseringar och en uppdelning av varningarnas allvarlighetsgrad](images/atp-users-at-risk.png)

<span data-ttu-id="14036-175">Klicka på användarkontot om du vill se mer information om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="14036-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="14036-176">Mer information finns i [Undersöka ett användarkonto.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="14036-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="14036-177">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="14036-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="14036-178">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="14036-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="14036-179">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="14036-179">Related topics</span></span>
- [<span data-ttu-id="14036-180">Förstå Microsoft Defender för Slutpunktsportalen</span><span class="sxs-lookup"><span data-stu-id="14036-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="14036-181">Portalöversikt</span><span class="sxs-lookup"><span data-stu-id="14036-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="14036-182">Visa instrumentpanelen för & Sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="14036-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="14036-183">Visa instrumentpanelen för hotanalyser och vidta rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="14036-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
