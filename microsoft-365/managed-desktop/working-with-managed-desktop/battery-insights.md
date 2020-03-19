---
title: Batteriinsikter
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42810766"
---
# <a name="battery-insights"></a><span data-ttu-id="ddc57-103">Batteriinsikter</span><span class="sxs-lookup"><span data-stu-id="ddc57-103">Battery insights</span></span>
<span data-ttu-id="ddc57-104">Den här vyn innehåller energi-, batteri- och appanvändningsmått för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="ddc57-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ddc57-105">För dessa ändamål anses en app vara "i bruk" om den körs och i fokus.</span><span class="sxs-lookup"><span data-stu-id="ddc57-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="ddc57-106">Om du vill visa användningsdata väljer du fliken **Batteri.**</span><span class="sxs-lookup"><span data-stu-id="ddc57-106">To view usage data, select the **Battery** tab.</span></span>

![Batteriruta: förväntad batteritid per enhetsmodell i övre vänstra, övre energikonsumenter (efter app) i övre högra, insikter tabell över botten.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="ddc57-109">Förväntad batteritid</span><span class="sxs-lookup"><span data-stu-id="ddc57-109">Predicted battery life</span></span>

<span data-ttu-id="ddc57-110">I området **Förväntad batteritid** ger vi förutsägelser om den förväntade batteritiden för dina enheter, ordnade efter enhetsmodell.</span><span class="sxs-lookup"><span data-stu-id="ddc57-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="ddc57-111">Dessa data härleds från samplingsenergianvändning, användningstid och batterikapacitet från ett slumpmässigt <em>urval</em> av enheterna i microsofts hanterade skrivbordsdistribution som också rapporterar data.</span><span class="sxs-lookup"><span data-stu-id="ddc57-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="ddc57-112">Tabellen ger den förväntade batteritiden (i timmar), genomsnittlig batteritid för samma modeller i andra Microsoft Managed Desktop-distributioner och antalet enheter som rapporterar dessa data i din miljö.</span><span class="sxs-lookup"><span data-stu-id="ddc57-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="ddc57-113">Sortera data genom att markera kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="ddc57-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="ddc57-114">De främsta energikonsumenterna</span><span class="sxs-lookup"><span data-stu-id="ddc57-114">Top energy consumers</span></span>

<span data-ttu-id="ddc57-115">I området **Bästa energikonsumenter** hittar du de appar i din miljö som förbrukar mest energi under milliWatt-timmar (mWh).</span><span class="sxs-lookup"><span data-stu-id="ddc57-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="ddc57-116">Apparna som visas är per specifik enhet, som du väljer i avsnittet **Förväntad batteritid** till vänster.</span><span class="sxs-lookup"><span data-stu-id="ddc57-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="ddc57-117">Om du till exempel vill se förbrukningen per app för dina Microsoft Surface Book 2-enheter väljer du den raden i batteritidsområdet.</span><span class="sxs-lookup"><span data-stu-id="ddc57-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="ddc57-118">Om du inte väljer någon modell är appförbrukningsdata som visas för alla appar som vi har data för gemensamt.</span><span class="sxs-lookup"><span data-stu-id="ddc57-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="ddc57-119">För varje app visar färgade segment fördelningen av appens energianvändning mellan dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="ddc57-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="ddc57-120">Cpu</span><span class="sxs-lookup"><span data-stu-id="ddc57-120">CPU</span></span>
- <span data-ttu-id="ddc57-121">Visa</span><span class="sxs-lookup"><span data-stu-id="ddc57-121">Display</span></span>
- <span data-ttu-id="ddc57-122">Nätverk</span><span class="sxs-lookup"><span data-stu-id="ddc57-122">Network</span></span>
- <span data-ttu-id="ddc57-123">Andra</span><span class="sxs-lookup"><span data-stu-id="ddc57-123">Other</span></span>

<span data-ttu-id="ddc57-124">"Andra" kan omfatta energiförbrukning av en mängd olika källor, såsom diskaktivitet, mobilt bredband och energi som går förlorad för internt motstånd.</span><span class="sxs-lookup"><span data-stu-id="ddc57-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="ddc57-125">Du kan filtrera den här vyn så att endast förgrundsappar, bakgrundsappar eller båda visas med hjälp av menyn längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="ddc57-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="ddc57-126">Förgrundsappar är de som har haft användarinteraktion under de senaste 28 dagarna, till exempel att välja något med en mus.</span><span class="sxs-lookup"><span data-stu-id="ddc57-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="ddc57-127">Insikter</span><span class="sxs-lookup"><span data-stu-id="ddc57-127">Insights</span></span>

<span data-ttu-id="ddc57-128">**Insights-området** visar de tre största energikonsumenterna i CPU- och nätverkskategorierna.</span><span class="sxs-lookup"><span data-stu-id="ddc57-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="ddc57-129">Dessa objekt förbrukar högre energi än genomsnittet jämfört med alla Microsoft Managed Desktop-distributioner.</span><span class="sxs-lookup"><span data-stu-id="ddc57-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="ddc57-130">Vi visar inte visningsresursen eftersom den är starkt beroende av enhetens användningstid och skärmens inställningar för ljusstyrka.</span><span class="sxs-lookup"><span data-stu-id="ddc57-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="ddc57-131">Välj listorna i kolumnen **Information** om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="ddc57-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="ddc57-132">Batterioptimering</span><span class="sxs-lookup"><span data-stu-id="ddc57-132">Battery optimization</span></span>

<span data-ttu-id="ddc57-133">Windows 10 erbjuder många [enhetsinställningar](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) för att förbättra energiförbrukningen och öka batteritiden för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="ddc57-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ddc57-134">Vissa av dessa inställningar kan minska andra Windows-funktioner, så du måste också ta hänsyn till andra faktorer, till exempel enhetens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ddc57-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="ddc57-135">Windows-stöd upprätthåller en lista över dessa [batteribesparingstips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="ddc57-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="ddc57-136">Användare kan justera vissa inställningar på egen hand utan att behöva administratörshöjd eller stöd.</span><span class="sxs-lookup"><span data-stu-id="ddc57-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="ddc57-137">Andra inställningar kräver support från organisationens IT-administratör.</span><span class="sxs-lookup"><span data-stu-id="ddc57-137">Other settings require support from your organization's IT administrator.</span></span>
