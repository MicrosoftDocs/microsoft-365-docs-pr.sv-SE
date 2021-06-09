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
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844232"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="82842-104">Visa och ordna kön Microsoft Defender för slutpunktsincidenter</span><span class="sxs-lookup"><span data-stu-id="82842-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82842-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="82842-105">**Applies to:**</span></span>
- [<span data-ttu-id="82842-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="82842-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="82842-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82842-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="82842-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="82842-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82842-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="82842-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="82842-110">I **kön Incidenter** visas en samling incidenter som har flaggats från enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="82842-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="82842-111">Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="82842-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="82842-112">Som standard visar kön incidenter som visats de senaste 30 dagarna, med det senaste incidenten högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.</span><span class="sxs-lookup"><span data-stu-id="82842-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="82842-113">Du kan välja mellan flera alternativ för att anpassa vyn Incidentköer.</span><span class="sxs-lookup"><span data-stu-id="82842-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="82842-114">I det övre navigeringsfältet kan du:</span><span class="sxs-lookup"><span data-stu-id="82842-114">On the top navigation you can:</span></span>
- <span data-ttu-id="82842-115">Anpassa kolumner för att lägga till eller ta bort kolumner</span><span class="sxs-lookup"><span data-stu-id="82842-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="82842-116">Ändra antalet objekt som ska visas per sida</span><span class="sxs-lookup"><span data-stu-id="82842-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="82842-117">Markera de objekt som ska visas per sida</span><span class="sxs-lookup"><span data-stu-id="82842-117">Select the items to show per page</span></span>
- <span data-ttu-id="82842-118">Batchvälj de incidenter du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="82842-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="82842-119">Navigera mellan sidor</span><span class="sxs-lookup"><span data-stu-id="82842-119">Navigate between pages</span></span>
- <span data-ttu-id="82842-120">Använda filter</span><span class="sxs-lookup"><span data-stu-id="82842-120">Apply filters</span></span>

![Bild på incidentköer](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="82842-122">Sortera och filtrera incidentkön</span><span class="sxs-lookup"><span data-stu-id="82842-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="82842-123">Du kan använda följande filter för att begränsa listan över incidenter och få en mer fokuserad vy.</span><span class="sxs-lookup"><span data-stu-id="82842-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="82842-124">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="82842-124">Severity</span></span>

<span data-ttu-id="82842-125">Incidentens allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="82842-125">Incident severity</span></span> | <span data-ttu-id="82842-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="82842-126">Description</span></span>
:---|:---
<span data-ttu-id="82842-127">Högsta</span><span class="sxs-lookup"><span data-stu-id="82842-127">High</span></span> </br><span data-ttu-id="82842-128">(Röd)</span><span class="sxs-lookup"><span data-stu-id="82842-128">(Red)</span></span> | <span data-ttu-id="82842-129">Hot som ofta associeras med avancerade fortlöpande hot (APT).</span><span class="sxs-lookup"><span data-stu-id="82842-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="82842-130">De här incidenterna anger en hög risk på grund av hur allvarlig skada de kan orsaka på enheter.</span><span class="sxs-lookup"><span data-stu-id="82842-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="82842-131">Medel</span><span class="sxs-lookup"><span data-stu-id="82842-131">Medium</span></span> </br><span data-ttu-id="82842-132">(Orange)</span><span class="sxs-lookup"><span data-stu-id="82842-132">(Orange)</span></span> | <span data-ttu-id="82842-133">Hot som sällan observeras i organisationen, till exempel avvikande registerändring, körning av misstänkta filer och observerade beteenden som är typiska för attackfaser.</span><span class="sxs-lookup"><span data-stu-id="82842-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="82842-134">Låg</span><span class="sxs-lookup"><span data-stu-id="82842-134">Low</span></span> </br><span data-ttu-id="82842-135">(Gul)</span><span class="sxs-lookup"><span data-stu-id="82842-135">(Yellow)</span></span> | <span data-ttu-id="82842-136">Hot som är associerade med vanlig skadlig programvara och hack-verktyg som inte nödvändigtvis indikerar ett avancerat hot som riktar sig till organisationen.</span><span class="sxs-lookup"><span data-stu-id="82842-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="82842-137">Informativ</span><span class="sxs-lookup"><span data-stu-id="82842-137">Informational</span></span> </br><span data-ttu-id="82842-138">(Grå)</span><span class="sxs-lookup"><span data-stu-id="82842-138">(Grey)</span></span> | <span data-ttu-id="82842-139">Informationstillbud anses kanske inte vara skadliga för nätverket men de kan vara bra att hålla reda på.</span><span class="sxs-lookup"><span data-stu-id="82842-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="82842-140">Tilldelad till</span><span class="sxs-lookup"><span data-stu-id="82842-140">Assigned to</span></span>
<span data-ttu-id="82842-141">Du kan välja att filtrera listan genom att välja tilldelade till alla eller sådana som har tilldelats till dig.</span><span class="sxs-lookup"><span data-stu-id="82842-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="82842-142">Kategori</span><span class="sxs-lookup"><span data-stu-id="82842-142">Category</span></span>
<span data-ttu-id="82842-143">Incidenter kategoriseras utifrån beskrivningen av det steg i vilket man ligger med en killkedja för cybersäkerhet.</span><span class="sxs-lookup"><span data-stu-id="82842-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="82842-144">Den här vyn hjälper hotanalytiker att fastställa prioritet, brådskande och motsvarande svarsstrategi för distribution utifrån kontext.</span><span class="sxs-lookup"><span data-stu-id="82842-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="82842-145">Status</span><span class="sxs-lookup"><span data-stu-id="82842-145">Status</span></span>
<span data-ttu-id="82842-146">Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.</span><span class="sxs-lookup"><span data-stu-id="82842-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="82842-147">Datakänslighet</span><span class="sxs-lookup"><span data-stu-id="82842-147">Data sensitivity</span></span>
<span data-ttu-id="82842-148">Använd det här filtret för att visa incidenter som innehåller känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="82842-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="82842-149">Namn på incidenter</span><span class="sxs-lookup"><span data-stu-id="82842-149">Incident naming</span></span>

<span data-ttu-id="82842-150">För att du snabbt ska förstå incidentens omfattning genereras incidentnamn automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="82842-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="82842-151">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="82842-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="82842-152">Incidenter som tidigare fanns före automatisk namngivning för incidenter behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="82842-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="82842-153">Se även</span><span class="sxs-lookup"><span data-stu-id="82842-153">See also</span></span>
- [<span data-ttu-id="82842-154">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="82842-154">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="82842-155">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="82842-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="82842-156">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="82842-156">Investigate incidents</span></span>](investigate-incidents.md)

