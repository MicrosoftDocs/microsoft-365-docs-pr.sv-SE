---
title: Skydda organisationens data med enhetskontroll
description: Övervaka organisationens datasäkerhet genom enhetskontrollrapporter.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772371"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="c8193-103">Skydda organisationens data med enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="c8193-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="c8193-104">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="c8193-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="c8193-105">Microsoft Defender för Endpoint-enhetskontroll skyddar mot dataförlust genom att övervaka och styra medieanvändningen på olika enheter i organisationen, t.ex. användning av flyttbara lagringsenheter och USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="c8193-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="c8193-106">Med enhetskontrollrapporten kan du visa händelser som är relaterade till medieanvändning, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c8193-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="c8193-107">**Granskningshändelser:** Visar antalet granskningshändelser som inträffar när externa media är anslutna.</span><span class="sxs-lookup"><span data-stu-id="c8193-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="c8193-108">**Policyhändelser:** Visar antalet principhändelser som inträffar när en enhetskontrollprincip utlöses.</span><span class="sxs-lookup"><span data-stu-id="c8193-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="c8193-109">Granskningshändelsen för att spåra medieanvändning är aktiverad som standard för enheter som är onboarded till Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c8193-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="c8193-110">Förstå granskningshändelserna</span><span class="sxs-lookup"><span data-stu-id="c8193-110">Understanding the audit events</span></span>

<span data-ttu-id="c8193-111">Granskningshändelserna omfattar:</span><span class="sxs-lookup"><span data-stu-id="c8193-111">The audit events include:</span></span>

- <span data-ttu-id="c8193-112">**USB-enhetsuppfattning och avbelopp:** Granskningshändelser som genereras när en USB-enhet ärmonterad eller oöverstiglig.</span><span class="sxs-lookup"><span data-stu-id="c8193-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="c8193-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span><span class="sxs-lookup"><span data-stu-id="c8193-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="c8193-114">Övervaka säkerheten för enhetskontroller</span><span class="sxs-lookup"><span data-stu-id="c8193-114">Monitor device control security</span></span>

<span data-ttu-id="c8193-115">Enhetskontroll i Microsoft Defender för Endpoint ger säkerhetsadministratörer möjlighet att använda verktyg som gör att de kan spåra organisationens enhetskontrollsäkerhet via rapporter.</span><span class="sxs-lookup"><span data-stu-id="c8193-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="c8193-116">Du hittar rapporten om enhetskontroll i säkerhetscentret i Microsoft 365 genom att gå till **Rapporter > Enhetsskydd**.</span><span class="sxs-lookup"><span data-stu-id="c8193-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="c8193-117">Kortet för enhetsskydd på **instrumentpanelen** Rapporter visar antalet granskningshändelser som genererats av medietyp under de senaste 180 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c8193-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8193-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="c8193-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="c8193-119">Knappen **Visa information** visar mer medieanvändningsdata på sidan med **enhetskontrollrapporten.**</span><span class="sxs-lookup"><span data-stu-id="c8193-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="c8193-120">Sidan innehåller en instrumentpanel med det samlade antalet händelser per typ och en lista över händelser.</span><span class="sxs-lookup"><span data-stu-id="c8193-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="c8193-121">Administratörer kan filtrera fram tidsintervall, mediaklassnamn och enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="c8193-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8193-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="c8193-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="c8193-123">När du väljer en händelse visas en utfällning med mer information:</span><span class="sxs-lookup"><span data-stu-id="c8193-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="c8193-124">**Allmän information:** Datum, åtgärdsläge och principen för den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="c8193-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="c8193-125">**Medieinformation:** Medieinformation omfattar Medienamn, Klassnamn, Klass-GUID, Enhets-ID, Leverantörs-ID, Volym, Serienummer och Bustyp.</span><span class="sxs-lookup"><span data-stu-id="c8193-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="c8193-126">**Platsinformation:** Enhetsnamn och MDATP enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="c8193-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8193-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="c8193-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="c8193-128">Om du vill se realtidsaktivitet för dessa medier i hela organisationen väljer du **knappen Öppna avancerad** sökning.</span><span class="sxs-lookup"><span data-stu-id="c8193-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="c8193-129">Det här inkluderar en inbäddad, fördefinierad fråga.</span><span class="sxs-lookup"><span data-stu-id="c8193-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8193-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="c8193-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="c8193-131">Om du vill se enhetens säkerhet väljer du **knappen Öppna enhetssida** på den utfällade sidan.</span><span class="sxs-lookup"><span data-stu-id="c8193-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="c8193-132">Med den här knappen öppnas sidan enhetsentitet.</span><span class="sxs-lookup"><span data-stu-id="c8193-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8193-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="c8193-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="c8193-134">Rapporteringsfördröjningar</span><span class="sxs-lookup"><span data-stu-id="c8193-134">Reporting delays</span></span>

<span data-ttu-id="c8193-135">Rapporten om enhetskontroll kan ha en fördröjning på 12 timmar från den tid en medieanslutning uppstår till den tidpunkt då händelsen återspeglas på kortet eller i domänlistan.</span><span class="sxs-lookup"><span data-stu-id="c8193-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
