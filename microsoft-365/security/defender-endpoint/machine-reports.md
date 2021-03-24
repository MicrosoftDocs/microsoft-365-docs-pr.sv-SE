---
title: Rapport om enhetshälsa och efterlevnad i Microsoft Defender ATP
description: Spåra identifieringar av enhetens hälsa, antivirusstatus, OS-plattform och Windows 10-versioner med hjälp av hälso- och efterlevnadsrapporten för enheter
keywords: hälsotillstånd, antivirus, os-plattform, windows 10-version, version, hälsa, efterlevnad, status
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
ms.openlocfilehash: 9d41071fc5849f3a11061437af2bb88b117ec4a8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072097"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9b726-104">Rapport om enhetshälsa och efterlevnad i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b726-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b726-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9b726-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b726-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b726-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9b726-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b726-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9b726-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9b726-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b726-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9b726-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9b726-110">Statusrapporten för enheter innehåller detaljerad information om enheterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9b726-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="9b726-111">Rapporten innehåller trendinformation som visar sensorns status, antivirusstatus, OS-plattformar och Windows 10-versioner.</span><span class="sxs-lookup"><span data-stu-id="9b726-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="9b726-112">Instrumentpanelen är strukturerad i två avsnitt: ![ Bild på enhetsrapporten](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="9b726-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="9b726-113">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9b726-113">Section</span></span> | <span data-ttu-id="9b726-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b726-114">Description</span></span>
:---|:---
<span data-ttu-id="9b726-115">1</span><span class="sxs-lookup"><span data-stu-id="9b726-115">1</span></span> | <span data-ttu-id="9b726-116">Enhetstrender</span><span class="sxs-lookup"><span data-stu-id="9b726-116">Device trends</span></span>
<span data-ttu-id="9b726-117">2</span><span class="sxs-lookup"><span data-stu-id="9b726-117">2</span></span> | <span data-ttu-id="9b726-118">Enhetssammanfattning (aktuell dag)</span><span class="sxs-lookup"><span data-stu-id="9b726-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="9b726-119">Enhetstrender</span><span class="sxs-lookup"><span data-stu-id="9b726-119">Device trends</span></span> 
<span data-ttu-id="9b726-120">Som standard visar enhetstrender enhetsinformation från 30-dagarsperioden som slutar på den senaste fullständiga dagen.</span><span class="sxs-lookup"><span data-stu-id="9b726-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="9b726-121">För att få bättre perspektiv på trender i organisationen kan du finjustera rapporteringsperioden genom att justera tidsperioden som visas.</span><span class="sxs-lookup"><span data-stu-id="9b726-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="9b726-122">Om du vill justera tidsperioden väljer du ett tidsperiodintervall bland alternativen i listrutan:</span><span class="sxs-lookup"><span data-stu-id="9b726-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="9b726-123">30 dagar</span><span class="sxs-lookup"><span data-stu-id="9b726-123">30 days</span></span>
- <span data-ttu-id="9b726-124">3 månader</span><span class="sxs-lookup"><span data-stu-id="9b726-124">3 months</span></span>
- <span data-ttu-id="9b726-125">6 månader</span><span class="sxs-lookup"><span data-stu-id="9b726-125">6 months</span></span>
- <span data-ttu-id="9b726-126">Anpassad</span><span class="sxs-lookup"><span data-stu-id="9b726-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="9b726-127">Dessa filter tillämpas endast på avsnittet enhetstrender.</span><span class="sxs-lookup"><span data-stu-id="9b726-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="9b726-128">Avsnittet med enhetssammanfattningar påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="9b726-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="9b726-129">Enhetssammanfattning</span><span class="sxs-lookup"><span data-stu-id="9b726-129">Device summary</span></span> 
<span data-ttu-id="9b726-130">Även om enhetstrender visar trendande enhetsinformation, visar enhetssammanfattningen enhetsinformation begränsad till den aktuella dagen.</span><span class="sxs-lookup"><span data-stu-id="9b726-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="9b726-131">Data som återspeglas i sammanfattningsavsnittet är begränsade till 180 dagar före dagens datum.</span><span class="sxs-lookup"><span data-stu-id="9b726-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="9b726-132">Om dagens datum till exempel är den 27 mars 2019 återspeglar informationen i sammanfattningsavsnittet tal från den 28 september 2018 till den 27 mars 2019.</span><span class="sxs-lookup"><span data-stu-id="9b726-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="9b726-133">Filtret som används i avsnittet trender tillämpas inte i sammanfattningsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="9b726-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="9b726-134">I avsnittet enhetstrender kan du granska nedåt i enhetslistan och använda motsvarande filter.</span><span class="sxs-lookup"><span data-stu-id="9b726-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="9b726-135">Om du till exempel klickar på fältet Inaktiv i kortet Sensorhälsa visas listan över enheter med resultat som bara visar enheter vars sensorstatus är inaktiv.</span><span class="sxs-lookup"><span data-stu-id="9b726-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="9b726-136">Enhetsattribut</span><span class="sxs-lookup"><span data-stu-id="9b726-136">Device attributes</span></span>
<span data-ttu-id="9b726-137">Rapporten består av kort som visar följande enhetsattribut:</span><span class="sxs-lookup"><span data-stu-id="9b726-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="9b726-138">**Hälsotillstånd**: visar information om sensortillståndet på enheter, som ger en samlad vy av enheter som är aktiva, har nedsatt kommunikation, inaktiv eller där inga sensordata visas.</span><span class="sxs-lookup"><span data-stu-id="9b726-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="9b726-139">**Antivirusstatus för aktiva Windows 10-enheter**: visar antalet enheter och status för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b726-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="9b726-140">**OS-plattformar**: visar den distribution av OS-plattformar som finns i din organisation.</span><span class="sxs-lookup"><span data-stu-id="9b726-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="9b726-141">**Windows 10-versioner**: visar distributionen av Windows 10-enheter och deras versioner i din organisation.</span><span class="sxs-lookup"><span data-stu-id="9b726-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="9b726-142">Filtrera data</span><span class="sxs-lookup"><span data-stu-id="9b726-142">Filter data</span></span>
 
<span data-ttu-id="9b726-143">Använd de angivna filtren för att inkludera eller exkludera enheter med vissa attribut.</span><span class="sxs-lookup"><span data-stu-id="9b726-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="9b726-144">Du kan välja flera filter som ska användas från enhetsattributen.</span><span class="sxs-lookup"><span data-stu-id="9b726-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="9b726-145">De här filtren **gäller** för alla korten i rapporten.</span><span class="sxs-lookup"><span data-stu-id="9b726-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="9b726-146">Om du till exempel vill visa data om Windows 10-enheter med statusen Aktiv sensor:</span><span class="sxs-lookup"><span data-stu-id="9b726-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="9b726-147">Under **Filter > sensorns hälsotillstånd > Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="9b726-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="9b726-148">Välj sedan **OS-> Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="9b726-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="9b726-149">Välj **Använd**.</span><span class="sxs-lookup"><span data-stu-id="9b726-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="9b726-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9b726-150">Related topic</span></span>
- [<span data-ttu-id="9b726-151">Rapport om hotskydd</span><span class="sxs-lookup"><span data-stu-id="9b726-151">Threat protection report</span></span>](threat-protection-reports.md)
