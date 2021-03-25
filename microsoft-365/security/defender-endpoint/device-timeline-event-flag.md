---
title: Händelseflaggor i Microsoft Defender för slutpunktsenhetstid
description: Använd Microsoft Defender för händelseflaggor på slutpunktsenhetens tidslinje för att
keywords: Defender för slutpunktsenhetstidslinje, händelseflaggor
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165159"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="fcfd2-104">Händelseflaggor i Microsoft Defender för slutpunktsenhetstid</span><span class="sxs-lookup"><span data-stu-id="fcfd2-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fcfd2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fcfd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="fcfd2-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fcfd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fcfd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcfd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fcfd2-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fcfd2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fcfd2-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fcfd2-110">Med händelseflaggor i Defender för slutpunktsenhetens tidslinje får du hjälp att filtrera och ordna specifika händelser när du undersöker potentiella attacker.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="fcfd2-111">Defender för Endpoint-enhetens tidslinje ger en kronologisk vy av händelserna och tillhörande aviseringar som observeras på en enhet.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="fcfd2-112">Den här listan med händelser ger full insyn i händelser, filer och IP-adresser som observerats på enheten.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="fcfd2-113">Listan kan ibland vara lång.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="fcfd2-114">Med händelseflaggor på enhetstidslinjen kan du hålla reda på händelser som kan vara relaterade.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="fcfd2-115">När du har gått igenom en tidslinje på en enhet kan du sortera, filtrera och exportera specifika händelser som du har flaggat.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="fcfd2-116">När du navigerar på enhetens tidslinje kan du söka efter och filtrera efter specifika händelser.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="fcfd2-117">Du kan ange händelseflaggor genom att:</span><span class="sxs-lookup"><span data-stu-id="fcfd2-117">You can set event flags by:</span></span> 

- <span data-ttu-id="fcfd2-118">Markera de viktigaste händelserna</span><span class="sxs-lookup"><span data-stu-id="fcfd2-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="fcfd2-119">Markera händelser som kräver djupdykning</span><span class="sxs-lookup"><span data-stu-id="fcfd2-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="fcfd2-120">Skapa en tidslinje med ett rent intrång</span><span class="sxs-lookup"><span data-stu-id="fcfd2-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="fcfd2-121">Flagga en händelse</span><span class="sxs-lookup"><span data-stu-id="fcfd2-121">Flag an event</span></span>
1. <span data-ttu-id="fcfd2-122">Hitta den händelse som du vill flagga</span><span class="sxs-lookup"><span data-stu-id="fcfd2-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="fcfd2-123">Klicka på flaggikonen i kolumnen Flagga.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="fcfd2-124">![Bild av tidslinjeflaggan på enheten](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="fcfd2-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="fcfd2-125">Visa flaggade händelser</span><span class="sxs-lookup"><span data-stu-id="fcfd2-125">View flagged events</span></span>  
1. <span data-ttu-id="fcfd2-126">Aktivera Flaggade **händelser** i avsnittet **Filter på tidslinjen.**</span><span class="sxs-lookup"><span data-stu-id="fcfd2-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="fcfd2-127">Klicka på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-127">Click **Apply**.</span></span> <span data-ttu-id="fcfd2-128">Endast flaggade händelser visas.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="fcfd2-129">Du kan tillämpa ytterligare filter genom att klicka på tidsstapeln.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="fcfd2-130">Då visas bara händelser före den flaggade händelsen.</span><span class="sxs-lookup"><span data-stu-id="fcfd2-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="fcfd2-131">![Bild av enhetens tidslinjeflagga med filter på](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="fcfd2-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
