---
title: Batteriinsikter
description: En rapport som visar data om förutsagd batterilivslängd och toppkraftskonsumenter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579716"
---
# <a name="battery-insights"></a><span data-ttu-id="3c17c-104">Batteriinsikter</span><span class="sxs-lookup"><span data-stu-id="3c17c-104">Battery insights</span></span>
<span data-ttu-id="3c17c-105">Den här vyn ger mått för energi, batteri och appanvändning för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="3c17c-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3c17c-106">För dessa ändamål anses en app vara "i bruk" om den körs och är i fokus.</span><span class="sxs-lookup"><span data-stu-id="3c17c-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="3c17c-107">Om du vill visa användningsdata väljer **du fliken** Batteri.</span><span class="sxs-lookup"><span data-stu-id="3c17c-107">To view usage data, select the **Battery** tab.</span></span>

![Batterifönstret: prognostterat batterilivslängd per enhetsmodell i övre vänstra hörnet, de främsta energikonsumenterna (efter app) i det övre högra hörnet, insights-tabellen längst ned.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="3c17c-110">Förutsagd batteritid</span><span class="sxs-lookup"><span data-stu-id="3c17c-110">Predicted battery life</span></span>

<span data-ttu-id="3c17c-111">I området **prognostiserade batteritiden** tillhandahåller vi prognoser för den förväntade batterilivslängden för dina enheter, ordnade efter enhetsmodell.</span><span class="sxs-lookup"><span data-stu-id="3c17c-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="3c17c-112">Dessa data härleds från sampling av energianvändning, <em></em> användningstid och batterikapacitet från ett slumpmässigt urval av enheter i distributionen av Microsoft Managed Desktop som även rapporterar data.</span><span class="sxs-lookup"><span data-stu-id="3c17c-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="3c17c-113">Tabellen ger förutsägelser om batterilivslängd (i timmar), genomsnittlig batteritid för samma modeller i andra distributioner av Microsoft Managed Desktop och antalet enheter som rapporterar dessa data i din miljö.</span><span class="sxs-lookup"><span data-stu-id="3c17c-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="3c17c-114">Sortera data genom att markera kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="3c17c-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="3c17c-115">De främsta energikonsumenterna</span><span class="sxs-lookup"><span data-stu-id="3c17c-115">Top energy consumers</span></span>

<span data-ttu-id="3c17c-116">I **området De största** energikonsumenterna hittar du de appar i din miljö som använder mest energi i snavaWatt-timmar (mWh).</span><span class="sxs-lookup"><span data-stu-id="3c17c-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="3c17c-117">Apparna som visas visas per specifik enhet, som du väljer i **avsnittet Prognosterad batteritid** till vänster.</span><span class="sxs-lookup"><span data-stu-id="3c17c-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="3c17c-118">Om du till exempel vill visa förbrukning per app för Microsoft Surface Book 2-enheter markerar du den raden i batterilivslängdsområdet.</span><span class="sxs-lookup"><span data-stu-id="3c17c-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="3c17c-119">Om du inte väljer någon modell visas data om appanvändningen för alla appar som vi har data för gemensamt.</span><span class="sxs-lookup"><span data-stu-id="3c17c-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="3c17c-120">För varje app visar färgade segment fördelningen av appens energianvändning bland dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="3c17c-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="3c17c-121">CPU</span><span class="sxs-lookup"><span data-stu-id="3c17c-121">CPU</span></span>
- <span data-ttu-id="3c17c-122">Visning</span><span class="sxs-lookup"><span data-stu-id="3c17c-122">Display</span></span>
- <span data-ttu-id="3c17c-123">Nätverk</span><span class="sxs-lookup"><span data-stu-id="3c17c-123">Network</span></span>
- <span data-ttu-id="3c17c-124">Annat</span><span class="sxs-lookup"><span data-stu-id="3c17c-124">Other</span></span>

<span data-ttu-id="3c17c-125">"Andra" kan inkludera energiförbrukning från olika källor, till exempel diskaktivitet, mobil bredbandsanvändning och energi som går förlorad till internt arbete.</span><span class="sxs-lookup"><span data-stu-id="3c17c-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="3c17c-126">Du kan filtrera vyn så att den bara visar förgrundsappar, bakgrundsappar eller både och med hjälp av menyn längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="3c17c-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="3c17c-127">Förgrundsappar är sådana som interagerat med användare under de senaste 28 dagarna, till exempel genom att markera något med en mus.</span><span class="sxs-lookup"><span data-stu-id="3c17c-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="3c17c-128">Insikter</span><span class="sxs-lookup"><span data-stu-id="3c17c-128">Insights</span></span>

<span data-ttu-id="3c17c-129">I **området** Insikter visas de tre främsta energikonsumenterna i cpu- och nätverkskategorierna.</span><span class="sxs-lookup"><span data-stu-id="3c17c-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="3c17c-130">De här objekten använder en energi som är högre än genomsnittet jämfört med alla distributioner av Hanterad microsoft-dator.</span><span class="sxs-lookup"><span data-stu-id="3c17c-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="3c17c-131">Vi visar inte visningsresursen eftersom den är beroende av enhetens användningstid och ljusstyrka.</span><span class="sxs-lookup"><span data-stu-id="3c17c-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="3c17c-132">Välj listerna i kolumnen **Information** för mer information.</span><span class="sxs-lookup"><span data-stu-id="3c17c-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="3c17c-133">Batterioptimering</span><span class="sxs-lookup"><span data-stu-id="3c17c-133">Battery optimization</span></span>

<span data-ttu-id="3c17c-134">I Windows 10 finns [flera olika enhetsinställningar](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) som förbättrar strömförsörjningen och ökar batterilivslängden för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="3c17c-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3c17c-135">Vissa av de här inställningarna kan minska andra Windows-funktioner, så du måste också tänka på andra faktorer, till exempel enhetens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c17c-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="3c17c-136">Windows-supporten har en lista över de här [tipsen för att spara batteri](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="3c17c-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="3c17c-137">Användare kan justera vissa inställningar på egen hand utan att behöva höjd för administratör eller support.</span><span class="sxs-lookup"><span data-stu-id="3c17c-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="3c17c-138">Andra inställningar kräver stöd från din organisations IT-administratör.</span><span class="sxs-lookup"><span data-stu-id="3c17c-138">Other settings require support from your organization's IT administrator.</span></span>
