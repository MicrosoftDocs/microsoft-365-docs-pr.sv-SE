---
title: Visa och ordna listan Microsoft Defender för slutpunktsenheter
description: Läs mer om de tillgängliga funktioner som du kan använda i listan Enheter, till exempel sortering, filtrering och export av listan för att förbättra undersökningar.
keywords: sortera, filtrera, exportera, CSV, enhetsnamn, domän, senast sedd, intern IP, hälsotillstånd, aktiva varningar, aktiv identifiering av skadlig kod, hotkategori, granska varningar, nätverk, anslutning, skadlig programvara, typ, lösenords stjäla, utpressningstrojan, sårbarhet, hot, allmän skadlig kod, oönskad programvara
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
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861581"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="f0ab4-104">Visa och ordna listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="f0ab4-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f0ab4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0ab4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0ab4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0ab4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0ab4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f0ab4-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f0ab4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f0ab4-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="f0ab4-110">I **listan Enheter** visas en lista med de enheter i nätverket där aviseringar har genererats.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="f0ab4-111">Som standard visar kön enheter som har setts de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="f0ab4-112">Du får snabbt tillgång till information som domän, risknivå, OS-plattform och annan information för enkel identifiering av enheter som är mest riskfyllda.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="f0ab4-113">Du kan välja mellan flera olika alternativ om du vill anpassa enheternas listvy.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="f0ab4-114">I det övre navigeringsfältet kan du:</span><span class="sxs-lookup"><span data-stu-id="f0ab4-114">On the top navigation you can:</span></span>

- <span data-ttu-id="f0ab4-115">Lägga till eller ta bort kolumner</span><span class="sxs-lookup"><span data-stu-id="f0ab4-115">Add or remove columns</span></span>
- <span data-ttu-id="f0ab4-116">Exportera hela listan i CSV-format</span><span class="sxs-lookup"><span data-stu-id="f0ab4-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="f0ab4-117">Välj hur många objekt som ska visas per sida</span><span class="sxs-lookup"><span data-stu-id="f0ab4-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="f0ab4-118">Använda filter</span><span class="sxs-lookup"><span data-stu-id="f0ab4-118">Apply filters</span></span>

<span data-ttu-id="f0ab4-119">Under registreringsprocessen fylls **listan Enheter gradvis i** med enheter när de börjar rapportera sensordata.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="f0ab4-120">Använd den här vyn för att spåra dina inbyggda slutpunkter när de publiceras online, eller ladda ned hela slutpunktslistan som en CSV-fil för offlineanalys.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="f0ab4-121">Om du exporterar enhetslistan innehåller den alla enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="f0ab4-122">Det kan ta mycket tid att ladda ned, beroende på hur stor organisationen är.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="f0ab4-123">När du exporterar listan i CSV-format visas data på ett ofiltrerat sätt.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="f0ab4-124">CSV-filen innehåller alla enheter i organisationen, oavsett filtrering som används i själva vyn.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Bild på listan över enheter med lista över enheter](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="f0ab4-126">Sortera och filtrera enhetslistan</span><span class="sxs-lookup"><span data-stu-id="f0ab4-126">Sort and filter the device list</span></span>

<span data-ttu-id="f0ab4-127">Du kan använda följande filter för att begränsa listan med aviseringar och få en mer fokuserad vy.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="f0ab4-128">Risknivå</span><span class="sxs-lookup"><span data-stu-id="f0ab4-128">Risk level</span></span>

<span data-ttu-id="f0ab4-129">Risknivån återspeglar den övergripande riskbedömningen av enheten baserat på en kombination av faktorer, inklusive typer och allvarlighetsgrad för aktiva varningar på enheten.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="f0ab4-130">Att lösa aktiva aviseringar, godkänna åtgärdsaktiviteter och dölja efterföljande aviseringar kan sänka risknivån.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="f0ab4-131">Exponeringsnivå</span><span class="sxs-lookup"><span data-stu-id="f0ab4-131">Exposure level</span></span>

<span data-ttu-id="f0ab4-132">Exponeringsnivån återspeglar enhetens aktuella exponering baserat på den kumulativa effekten av de väntande säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="f0ab4-133">De möjliga nivåerna är låga, medelhöga och höga.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="f0ab4-134">Låg exponering innebär att enheterna är mindre sårbara för användning.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="f0ab4-135">Om exponeringsnivån säger "Inga data tillgängliga" finns det några anledningar till varför det kan vara så:</span><span class="sxs-lookup"><span data-stu-id="f0ab4-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="f0ab4-136">Enheten slutade rapportera i mer än 30 dagar – i så fall anses den vara inaktiv och exponering beräknas inte</span><span class="sxs-lookup"><span data-stu-id="f0ab4-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="f0ab4-137">Enhetens operativsystem stöds inte – se [minimikraven för Microsoft Defender för Slutpunkt](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="f0ab4-138">Enhet med inaktuell agent (mycket osannolikt)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="f0ab4-139">OS-plattform</span><span class="sxs-lookup"><span data-stu-id="f0ab4-139">OS Platform</span></span>

<span data-ttu-id="f0ab4-140">Välj bara de OS-plattformar som du är intresserad av att undersöka.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="f0ab4-141">Hälsotillstånd</span><span class="sxs-lookup"><span data-stu-id="f0ab4-141">Health state</span></span>

<span data-ttu-id="f0ab4-142">Filtrera efter följande tillstånd för enhetshälsa:</span><span class="sxs-lookup"><span data-stu-id="f0ab4-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="f0ab4-143">**Aktiv** – Enheter som aktivt rapporterar sensordata till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="f0ab4-144">**Inaktiv** – Enheter som helt slutat skicka signaler i mer än 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="f0ab4-145">**Felkonfigurerad** – Enheter som har nedsatt kommunikation med tjänsten eller inte kan skicka sensordata.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="f0ab4-146">Felkonfigurerade enheter kan klassificeras ytterligare till:</span><span class="sxs-lookup"><span data-stu-id="f0ab4-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="f0ab4-147">Inga sensordata</span><span class="sxs-lookup"><span data-stu-id="f0ab4-147">No sensor data</span></span>
  - <span data-ttu-id="f0ab4-148">Nedsatt kommunikation</span><span class="sxs-lookup"><span data-stu-id="f0ab4-148">Impaired communications</span></span>

  <span data-ttu-id="f0ab4-149">Mer information om hur du åtgärdar problem på felkonfigurerade enheter finns i [Åtgärda defekta sensor .](fix-unhealthy-sensors.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="f0ab4-150">Antivirusstatus</span><span class="sxs-lookup"><span data-stu-id="f0ab4-150">Antivirus status</span></span>

<span data-ttu-id="f0ab4-151">Filtrera enheter efter antivirusstatus.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="f0ab4-152">Gäller endast Windows 10 aktiva enheter.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="f0ab4-153">**Inaktiverad** – & skydd mot virus är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="f0ab4-154">**Rapportering inte** – & skydd mot virushot rapporterar inte.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="f0ab4-155">**Inte uppdaterat** – & skydd mot virus är inte uppdaterat.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="f0ab4-156">Mer information finns i View [the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="f0ab4-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="f0ab4-157">Status för åtgärder mot hot</span><span class="sxs-lookup"><span data-stu-id="f0ab4-157">Threat mitigation status</span></span>

<span data-ttu-id="f0ab4-158">Om du vill visa enheter som kan påverkas av ett visst hot väljer du hot i listmenyn och väljer sedan vilken säkerhetsrisk som behöver minimeras.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="f0ab4-159">Mer information om vissa hot finns i [Hotanalyser.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="f0ab4-160">Information om åtgärder finns i [& sårbarhetshantering.](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="f0ab4-161">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="f0ab4-161">Windows 10 version</span></span>

<span data-ttu-id="f0ab4-162">Markera bara de Windows 10 versioner du vill undersöka.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="f0ab4-163">Taggar & grupper</span><span class="sxs-lookup"><span data-stu-id="f0ab4-163">Tags & Groups</span></span>

<span data-ttu-id="f0ab4-164">Filtrera listan baserat på de gruppering och taggning som du har lagt till på enskilda enheter.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="f0ab4-165">Se [Skapa och hantera enhetstaggar](machine-tags.md) och Skapa och hantera [enhetsgrupper.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0ab4-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f0ab4-166">Related topics</span></span>

- [<span data-ttu-id="f0ab4-167">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="f0ab4-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
