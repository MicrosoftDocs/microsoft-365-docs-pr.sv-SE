---
title: Kontrollera sensorns hälsotillstånd i Microsoft Defender för Slutpunkt
description: Kontrollera sensorhälsan på enheter för att identifiera vilka som är felkonfigurerade, inaktiva eller inte rapporterar sensordata.
keywords: sensor, sensorhälsa, felkonfigurerad, inaktiv, inga sensordata, sensordata, nedsatt kommunikation, kommunikation
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904170"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ba3a8-104">Kontrollera sensorhälsan i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba3a8-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ba3a8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ba3a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="ba3a8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba3a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ba3a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba3a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ba3a8-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ba3a8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ba3a8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="ba3a8-110">Panelen **Enheter med sensorproblem** finns på instrumentpanelen Säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="ba3a8-111">Den här panelen ger information om den enskilda enhetens möjlighet att tillhandahålla sensordata och kommunicera med Defender för slutpunkt-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="ba3a8-112">Den rapporterar hur många enheter som kräver uppmärksamhet och hjälper dig att identifiera problematiska enheter och vidta åtgärder för att korrigera kända problem.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="ba3a8-113">Det finns två statusindikatorer på panelen som tillhandahåller information om antalet enheter som inte rapporterar korrekt till tjänsten:</span><span class="sxs-lookup"><span data-stu-id="ba3a8-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="ba3a8-114">**Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Defender för Slutpunkt-tjänsten och kan ha konfigurationsfel som behöver korrigeras.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="ba3a8-115">**Inaktiva** – Enheter som har slutat rapportera till Defender för slutpunktstjänsten under mer än sju dagar den senaste månaden.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="ba3a8-116">Om du klickar på någon av grupperna dirigeras du **till listan Enheter**, filtrerad efter ditt val.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Skärmbild av panelen Enheter med sensorproblem](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="ba3a8-118">I **listan Enheter** kan du filtrera hälsostatuslistan efter följande status:</span><span class="sxs-lookup"><span data-stu-id="ba3a8-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="ba3a8-119">**Aktiv** – Enheter som aktivt rapporterar till Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="ba3a8-120">**Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Defender för Slutpunkt-tjänsten men har konfigurationsfel som behöver korrigeras.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="ba3a8-121">Felkonfigurerade enheter kan ha en eller en kombination av följande problem:</span><span class="sxs-lookup"><span data-stu-id="ba3a8-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="ba3a8-122">**Inga sensordata** – Enheterna har slutat skicka sensordata.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="ba3a8-123">Begränsade aviseringar kan utlösas från enheten.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="ba3a8-124">**Nedsatt kommunikation –** Möjligheten att kommunicera med en enhet är försämrad.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="ba3a8-125">Det kan hända att det inte fungerar att skicka filer för djupanalys, blockera filer, isolera enheten från nätverket och andra åtgärder som kräver kommunikation med enheten.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="ba3a8-126">**Inaktiv** – Enheter som har stoppat rapporteringen till Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="ba3a8-127">Du kan också ladda ned hela listan i CSV-format med **hjälp av funktionen** Exportera.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="ba3a8-128">Mer information om filter finns i [Visa och ordna listan Enheter.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ba3a8-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="ba3a8-129">Exportera listan i CSV-format om du vill visa ofiltrerade data.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="ba3a8-130">CSV-filen innehåller alla enheter i organisationen, oavsett vilken filtrering som används i vyn och kan ta mycket tid att ladda ned, beroende på hur stor din organisation är.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Skärmbild av listsidan Enheter](images/atp-devices-list-page.png)

<span data-ttu-id="ba3a8-132">Du kan visa enhetsinformationen när du klickar på en felkonfigurerad eller inaktiv enhet.</span><span class="sxs-lookup"><span data-stu-id="ba3a8-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="ba3a8-133">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="ba3a8-133">Related topic</span></span>
- [<span data-ttu-id="ba3a8-134">Åtgärda defekta sensorer i Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba3a8-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
