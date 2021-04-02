---
title: Visa och ordna incidentkö
ms.reviewer: ''
description: Se listan över incidenter och lär dig hur du använder filter för att begränsa listan och få en mer fokuserad vy.
keywords: visa, organisera, incidenter, aggregera, undersökningar, kö, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499940"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="7bc49-104">Visa och ordna kön Microsoft Defender för slutpunktsincidenter</span><span class="sxs-lookup"><span data-stu-id="7bc49-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7bc49-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7bc49-105">**Applies to:**</span></span>
- [<span data-ttu-id="7bc49-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7bc49-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7bc49-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bc49-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7bc49-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7bc49-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7bc49-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7bc49-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="7bc49-110">I **kön Incidenter** visas en samling incidenter som har flaggats från enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="7bc49-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="7bc49-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="7bc49-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="7bc49-112">Som standard visar kön incidenter som visats de senaste 30 dagarna, med det senaste incidenten högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.</span><span class="sxs-lookup"><span data-stu-id="7bc49-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7bc49-113">Du kan välja mellan flera alternativ för att anpassa vyn Incidentköer.</span><span class="sxs-lookup"><span data-stu-id="7bc49-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="7bc49-114">I det övre navigeringsfältet kan du:</span><span class="sxs-lookup"><span data-stu-id="7bc49-114">On the top navigation you can:</span></span>
- <span data-ttu-id="7bc49-115">Anpassa kolumner för att lägga till eller ta bort kolumner</span><span class="sxs-lookup"><span data-stu-id="7bc49-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="7bc49-116">Ändra antalet objekt som ska visas per sida</span><span class="sxs-lookup"><span data-stu-id="7bc49-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="7bc49-117">Markera de objekt som ska visas per sida</span><span class="sxs-lookup"><span data-stu-id="7bc49-117">Select the items to show per page</span></span>
- <span data-ttu-id="7bc49-118">Batchvälj de incidenter du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="7bc49-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="7bc49-119">Navigera mellan sidor</span><span class="sxs-lookup"><span data-stu-id="7bc49-119">Navigate between pages</span></span>
- <span data-ttu-id="7bc49-120">Använda filter</span><span class="sxs-lookup"><span data-stu-id="7bc49-120">Apply filters</span></span>

![Bild på incidentköer](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="7bc49-122">Sortera och filtrera incidentkön</span><span class="sxs-lookup"><span data-stu-id="7bc49-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="7bc49-123">Du kan använda följande filter för att begränsa listan över incidenter och få en mer fokuserad vy.</span><span class="sxs-lookup"><span data-stu-id="7bc49-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="7bc49-124">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="7bc49-124">Severity</span></span>

<span data-ttu-id="7bc49-125">Incidentens allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="7bc49-125">Incident severity</span></span> | <span data-ttu-id="7bc49-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7bc49-126">Description</span></span>
:---|:---
<span data-ttu-id="7bc49-127">Högsta</span><span class="sxs-lookup"><span data-stu-id="7bc49-127">High</span></span> </br><span data-ttu-id="7bc49-128">(Röd)</span><span class="sxs-lookup"><span data-stu-id="7bc49-128">(Red)</span></span> | <span data-ttu-id="7bc49-129">Hot som ofta associeras med avancerade fortlöpande hot (APT).</span><span class="sxs-lookup"><span data-stu-id="7bc49-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="7bc49-130">De här incidenterna anger en hög risk på grund av hur allvarlig skada de kan orsaka på enheter.</span><span class="sxs-lookup"><span data-stu-id="7bc49-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="7bc49-131">Medel</span><span class="sxs-lookup"><span data-stu-id="7bc49-131">Medium</span></span> </br><span data-ttu-id="7bc49-132">(Orange)</span><span class="sxs-lookup"><span data-stu-id="7bc49-132">(Orange)</span></span> | <span data-ttu-id="7bc49-133">Hot som sällan observeras i organisationen, till exempel avvikande registerändring, körning av misstänkta filer och observerade beteenden som är typiska för attackfaser.</span><span class="sxs-lookup"><span data-stu-id="7bc49-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="7bc49-134">Låg</span><span class="sxs-lookup"><span data-stu-id="7bc49-134">Low</span></span> </br><span data-ttu-id="7bc49-135">(Gul)</span><span class="sxs-lookup"><span data-stu-id="7bc49-135">(Yellow)</span></span> | <span data-ttu-id="7bc49-136">Hot som är associerade med vanlig skadlig programvara och hack-verktyg som inte nödvändigtvis indikerar ett avancerat hot som riktar sig till organisationen.</span><span class="sxs-lookup"><span data-stu-id="7bc49-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="7bc49-137">Information</span><span class="sxs-lookup"><span data-stu-id="7bc49-137">Informational</span></span> </br><span data-ttu-id="7bc49-138">(Grå)</span><span class="sxs-lookup"><span data-stu-id="7bc49-138">(Grey)</span></span> | <span data-ttu-id="7bc49-139">Informationstillbud anses kanske inte vara skadliga för nätverket men de kan vara bra att hålla reda på.</span><span class="sxs-lookup"><span data-stu-id="7bc49-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="7bc49-140">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="7bc49-140">Assigned to</span></span>
<span data-ttu-id="7bc49-141">Du kan välja att filtrera listan genom att välja tilldelade till alla eller sådana som har tilldelats till dig.</span><span class="sxs-lookup"><span data-stu-id="7bc49-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="7bc49-142">Kategori</span><span class="sxs-lookup"><span data-stu-id="7bc49-142">Category</span></span>
<span data-ttu-id="7bc49-143">Incidenter kategoriseras utifrån beskrivningen av det steg i vilket man ligger med en killkedja för cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="7bc49-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="7bc49-144">Den här vyn hjälper hotanalytiker att fastställa prioritet, brådskande och motsvarande svarsstrategi för distribution utifrån kontext.</span><span class="sxs-lookup"><span data-stu-id="7bc49-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="7bc49-145">Status</span><span class="sxs-lookup"><span data-stu-id="7bc49-145">Status</span></span>
<span data-ttu-id="7bc49-146">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="7bc49-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7bc49-147">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="7bc49-147">Data sensitivity</span></span>
<span data-ttu-id="7bc49-148">Använd det här filtret för att visa incidenter som innehåller känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="7bc49-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="7bc49-149">Namn på incidenter</span><span class="sxs-lookup"><span data-stu-id="7bc49-149">Incident naming</span></span>

<span data-ttu-id="7bc49-150">För att du snabbt ska förstå incidentens omfattning genereras incidentnamn automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="7bc49-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="7bc49-151">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="7bc49-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7bc49-152">Incidenter som tidigare fanns före automatisk namngivning för incidenter behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="7bc49-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="7bc49-153">Se även</span><span class="sxs-lookup"><span data-stu-id="7bc49-153">See also</span></span>
- [<span data-ttu-id="7bc49-154">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="7bc49-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="7bc49-155">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="7bc49-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="7bc49-156">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="7bc49-156">Investigate incidents</span></span>](investigate-incidents.md)

