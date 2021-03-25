---
title: Rapport om hotskydd i Microsoft Defender ATP
description: Spåra aviseringsidentifiering, kategorier och allvarlighetsgrad med hjälp av rapporten om skydd mot hot
keywords: aviseringsidentifiering, källa, avisering efter kategori, allvarlighetsgrad för avisering, aviseringsklassificering, avgörande
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 104548314b8ef0ceb15d8d2683dad552233a509f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072906"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9725a-104">Rapport om hotskydd i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="9725a-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9725a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9725a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9725a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9725a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9725a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9725a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9725a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9725a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9725a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9725a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="9725a-110">Rapporten om skydd mot hot ger information på hög nivå om aviseringar som genereras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9725a-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="9725a-111">Rapporten innehåller trendinformation som visar identifieringskällor, kategorier, allvarlighetsgrad, status, klassificeringar och avgöranden för aviseringar över tid.</span><span class="sxs-lookup"><span data-stu-id="9725a-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="9725a-112">Instrumentpanelen är strukturerad i två avsnitt:</span><span class="sxs-lookup"><span data-stu-id="9725a-112">The dashboard is structured into two sections:</span></span>

![Bild av rapporten om skydd mot hot](images/threat-protection-reports.png)

<span data-ttu-id="9725a-114">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9725a-114">Section</span></span> | <span data-ttu-id="9725a-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9725a-115">Description</span></span> 
:---|:---
<span data-ttu-id="9725a-116">1</span><span class="sxs-lookup"><span data-stu-id="9725a-116">1</span></span> | <span data-ttu-id="9725a-117">Aviseringstrender</span><span class="sxs-lookup"><span data-stu-id="9725a-117">Alerts trends</span></span>
<span data-ttu-id="9725a-118">2</span><span class="sxs-lookup"><span data-stu-id="9725a-118">2</span></span> | <span data-ttu-id="9725a-119">Sammanfattning av aviseringar</span><span class="sxs-lookup"><span data-stu-id="9725a-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="9725a-120">Aviseringstrender</span><span class="sxs-lookup"><span data-stu-id="9725a-120">Alert trends</span></span>
<span data-ttu-id="9725a-121">Som standard visar aviseringstrenderna aviseringsinformation från 30-dagarsperioden som slutar på den senaste fullständiga dagen.</span><span class="sxs-lookup"><span data-stu-id="9725a-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="9725a-122">För att få bättre perspektiv på trender i organisationen kan du finjustera rapporteringsperioden genom att justera tidsperioden som visas.</span><span class="sxs-lookup"><span data-stu-id="9725a-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="9725a-123">Om du vill justera tidsperioden väljer du ett tidsperiodintervall bland alternativen i listrutan:</span><span class="sxs-lookup"><span data-stu-id="9725a-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="9725a-124">30 dagar</span><span class="sxs-lookup"><span data-stu-id="9725a-124">30 days</span></span>
- <span data-ttu-id="9725a-125">3 månader</span><span class="sxs-lookup"><span data-stu-id="9725a-125">3 months</span></span>
- <span data-ttu-id="9725a-126">6 månader</span><span class="sxs-lookup"><span data-stu-id="9725a-126">6 months</span></span>
- <span data-ttu-id="9725a-127">Anpassad</span><span class="sxs-lookup"><span data-stu-id="9725a-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="9725a-128">Dessa filter tillämpas endast på avsnittet aviseringstrender.</span><span class="sxs-lookup"><span data-stu-id="9725a-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="9725a-129">Det påverkar inte sammanfattningsavsnittet för aviseringar.</span><span class="sxs-lookup"><span data-stu-id="9725a-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="9725a-130">Sammanfattning av aviseringar</span><span class="sxs-lookup"><span data-stu-id="9725a-130">Alert summary</span></span>
<span data-ttu-id="9725a-131">Även om aviseringstrender visar trendande aviseringsinformation, visar sammanfattningen av aviseringsinformation begränsad till den aktuella dagen.</span><span class="sxs-lookup"><span data-stu-id="9725a-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="9725a-132">I sammanfattningen av aviseringar kan du granska nedåt till en viss aviseringskö med motsvarande filter tillämpat på den.</span><span class="sxs-lookup"><span data-stu-id="9725a-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="9725a-133">Om du till exempel klickar på EDR-fältet i kortet Identifieringskällor kommer du till aviseringskön med resultat som bara visar aviseringar som genererats från EDR-identifieringar.</span><span class="sxs-lookup"><span data-stu-id="9725a-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="9725a-134">Data som återspeglas i sammanfattningsavsnittet är begränsade till 180 dagar före dagens datum.</span><span class="sxs-lookup"><span data-stu-id="9725a-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="9725a-135">Om dagens datum till exempel är 5 november 2019 visar informationen i sammanfattningsavsnittet tal från den 5 maj 2019 till den 5 november 2019.</span><span class="sxs-lookup"><span data-stu-id="9725a-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="9725a-136">Filtret som används i avsnittet trender tillämpas inte i sammanfattningsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="9725a-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="9725a-137">Aviseringsattribut</span><span class="sxs-lookup"><span data-stu-id="9725a-137">Alert attributes</span></span>
<span data-ttu-id="9725a-138">Rapporten består av kort som visar följande aviseringsattribut:</span><span class="sxs-lookup"><span data-stu-id="9725a-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="9725a-139">**Identifieringskällor:** Visar information om de sensor- och identifieringstekniker som tillhandahåller de data som används av Microsoft Defender för Slutpunkten för att utlösa varningar.</span><span class="sxs-lookup"><span data-stu-id="9725a-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="9725a-140">**Hotkategorier:** Visar de typer av hot eller attackaktiviteter som utlöste aviseringar, som anger möjliga fokusområden för dina säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="9725a-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="9725a-141">**Allvarlighetsgrad**: visar varningens allvarlighetsnivå, som visar den samlade potentiella påverkan på hot för organisationen och den svarsnivå som behövs för att hantera dem.</span><span class="sxs-lookup"><span data-stu-id="9725a-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="9725a-142">**Status:** Visar lösningens status för aviseringar, vilket anger effektiviteten i dina manuella aviseringssvar och automatiserad åtgärd (om aktiverat).</span><span class="sxs-lookup"><span data-stu-id="9725a-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="9725a-143">**Klassificering & avgörande:** visar hur du har klassificerat aviseringar vid en lösning, om du har klassificerat dem som faktiska hot (faktiska varningar) eller som felaktiga identifieringar (falska aviseringar).</span><span class="sxs-lookup"><span data-stu-id="9725a-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="9725a-144">De här korten visar också att lösta aviseringar är avgörande, vilket ger ytterligare insyn, till exempel vilka typer av faktiska hot som hittas eller legitima aktiviteter som identifierats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="9725a-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="9725a-145">Filtrera data</span><span class="sxs-lookup"><span data-stu-id="9725a-145">Filter data</span></span>

<span data-ttu-id="9725a-146">Använd de angivna filtren för att inkludera eller exkludera aviseringar med vissa attribut.</span><span class="sxs-lookup"><span data-stu-id="9725a-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="9725a-147">De här filtren **gäller** för alla korten i rapporten.</span><span class="sxs-lookup"><span data-stu-id="9725a-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="9725a-148">Om du till exempel endast vill visa data om varningar med hög allvarlighetsgrad:</span><span class="sxs-lookup"><span data-stu-id="9725a-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="9725a-149">Under **Filter > allvarlighetsgrad** väljer du **Hög**</span><span class="sxs-lookup"><span data-stu-id="9725a-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="9725a-150">Kontrollera att alla andra alternativ under **Allvarlighetsgrad** är avmarkerade.</span><span class="sxs-lookup"><span data-stu-id="9725a-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="9725a-151">Välj **Använd**.</span><span class="sxs-lookup"><span data-stu-id="9725a-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="9725a-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9725a-152">Related topic</span></span>
- [<span data-ttu-id="9725a-153">Rapport om enhetshälsa och efterlevnad</span><span class="sxs-lookup"><span data-stu-id="9725a-153">Device health and compliance report</span></span>](machine-reports.md)