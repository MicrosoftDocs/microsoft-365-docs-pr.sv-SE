---
title: Undersök Microsoft Defender för slutpunktsdomäner
description: Använd undersökningsalternativen för att se om enheter och servrar har kommunicerat med skadliga domäner.
keywords: undersöker domän, domän, skadlig domän, microsoft defender atp, avisering, URL
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 3d4520c805332bac41746a39bb8b668dbfb1a570
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587497"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="104ff-104">Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="104ff-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="104ff-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="104ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="104ff-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="104ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="104ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="104ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="104ff-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="104ff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="104ff-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="104ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="104ff-110">Undersök en domän för att se om enheter och servrar i företagsnätverket har kommunicerat med en känd skadlig domän.</span><span class="sxs-lookup"><span data-stu-id="104ff-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="104ff-111">Du kan undersöka en domän med hjälp av sökfunktionen eller genom att klicka på en domänlänk från **enhetens tidslinje.**</span><span class="sxs-lookup"><span data-stu-id="104ff-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="104ff-112">Du kan se information från följande avsnitt i URL-vyn:</span><span class="sxs-lookup"><span data-stu-id="104ff-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="104ff-113">URL-information, Kontakter, Namnservrar</span><span class="sxs-lookup"><span data-stu-id="104ff-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="104ff-114">Aviseringar relaterade till url:en</span><span class="sxs-lookup"><span data-stu-id="104ff-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="104ff-115">URL i organisationen</span><span class="sxs-lookup"><span data-stu-id="104ff-115">URL in organization</span></span>
- <span data-ttu-id="104ff-116">Senaste observerade enheter med URL</span><span class="sxs-lookup"><span data-stu-id="104ff-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="104ff-117">URL globalt</span><span class="sxs-lookup"><span data-stu-id="104ff-117">URL worldwide</span></span>

<span data-ttu-id="104ff-118">I **det globala** avsnittet finns url-adressen, en länk till mer information om Whois, antalet relaterade öppna incidenter och antalet aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="104ff-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="104ff-119">Incident</span><span class="sxs-lookup"><span data-stu-id="104ff-119">Incident</span></span>

<span data-ttu-id="104ff-120">På **incidentkortet** visas ett stapeldiagram med alla aktiva aviseringar för incidenter under de senaste 180 dagarna.</span><span class="sxs-lookup"><span data-stu-id="104ff-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="104ff-121">Endeprenad</span><span class="sxs-lookup"><span data-stu-id="104ff-121">Prevalence</span></span>

<span data-ttu-id="104ff-122">Kortet **Visitkort** innehåller information om hur URL:en inom organisationen ska ut specificeras, under en angiven tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="104ff-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="104ff-123">Även om standardtiden är de senaste 30 dagarna kan du anpassa intervallet genom att välja nedåtpilen i hörnet av kortet.</span><span class="sxs-lookup"><span data-stu-id="104ff-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="104ff-124">Det kortaste tillgängliga intervallet är för den senaste dagen, medan det längsta intervallet är under de senaste 6 månaderna.</span><span class="sxs-lookup"><span data-stu-id="104ff-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="104ff-125">Varningar</span><span class="sxs-lookup"><span data-stu-id="104ff-125">Alerts</span></span>

<span data-ttu-id="104ff-126">Fliken **Aviseringar** ger en lista med aviseringar som är associerade med URL:en.</span><span class="sxs-lookup"><span data-stu-id="104ff-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="104ff-127">Tabellen som visas här är en filtrerad version av aviseringarna som visas på skärmen Aviseringskö, med endast aviseringar kopplade till domänen, deras allvarlighetsgrad, status, tillhörande incident, klassificering, undersökningstillstånd med mera.</span><span class="sxs-lookup"><span data-stu-id="104ff-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="104ff-128">Fliken Aviseringar kan justeras för att visa mer eller mindre information genom att välja **Anpassa** kolumner på åtgärdsmenyn ovanför kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="104ff-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="104ff-129">Du kan också justera antalet objekt som visas genom att välja **objekt per sida** på samma meny.</span><span class="sxs-lookup"><span data-stu-id="104ff-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="104ff-130">Observerad i organisationen</span><span class="sxs-lookup"><span data-stu-id="104ff-130">Observed in organization</span></span>

<span data-ttu-id="104ff-131">På **fliken Observerad i** organisationen finns en kronologisk vy över händelser och tillhörande aviseringar som har observerats på WEBBADRESSen.</span><span class="sxs-lookup"><span data-stu-id="104ff-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="104ff-132">Den här fliken innehåller en tidslinje och en anpassningsbar tabell med händelseinformation, till exempel tid, enhet och en kort beskrivning av vad som har hänt.</span><span class="sxs-lookup"><span data-stu-id="104ff-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="104ff-133">Du kan visa händelser från olika tidsperioder genom att ange datumen i textfälten ovanför tabellrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="104ff-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="104ff-134">Du kan också anpassa tidsperioden genom att markera olika områden på tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="104ff-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="104ff-135">**Undersöka en domän:**</span><span class="sxs-lookup"><span data-stu-id="104ff-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="104ff-136">Välj **URL** i **sökfältets** nedrullningsbar meny.</span><span class="sxs-lookup"><span data-stu-id="104ff-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="104ff-137">Ange URL-adressen i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="104ff-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="104ff-138">Klicka på sökikonen eller tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="104ff-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="104ff-139">Information om URL:en visas.</span><span class="sxs-lookup"><span data-stu-id="104ff-139">Details about the URL are displayed.</span></span> <span data-ttu-id="104ff-140">Obs! Sökresultat returneras bara för URL:er som observeras i kommunikation från enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="104ff-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="104ff-141">Använd sökfiltren för att definiera sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="104ff-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="104ff-142">Du kan också använda sökrutan för tidslinjen för att filtrera sökresultaten för alla enheter i organisationen som observerats för kommunikation med URL-adressen, filen som är kopplad till kommunikationen och det senaste observerade datumet.</span><span class="sxs-lookup"><span data-stu-id="104ff-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="104ff-143">Om du klickar på något av enhetsnamnen visas enhetens vy, där du kan fortsätta undersöka rapporterade aviseringar, beteenden och händelser.</span><span class="sxs-lookup"><span data-stu-id="104ff-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="104ff-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="104ff-144">Related topics</span></span>
- [<span data-ttu-id="104ff-145">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="104ff-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="104ff-146">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="104ff-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="104ff-147">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="104ff-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="104ff-148">Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="104ff-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="104ff-149">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="104ff-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="104ff-150">Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="104ff-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="104ff-151">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="104ff-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
