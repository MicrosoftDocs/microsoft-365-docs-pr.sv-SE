---
title: Tillförlitlighet insikter
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812268"
---
# <a name="reliability-insights"></a><span data-ttu-id="69b08-103">Tillförlitlighet insikter</span><span class="sxs-lookup"><span data-stu-id="69b08-103">Reliability insights</span></span>

<span data-ttu-id="69b08-104">Den här vyn ger dig en hälsosammanfattning av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="69b08-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="69b08-105">Om du vill visa tillförlitlighetsdata väljer du fliken **Tillförlitlighet.**</span><span class="sxs-lookup"><span data-stu-id="69b08-105">To view reliability data, select the **Reliability** tab.</span></span>


![Tillförlitlighetsruta: tillförlitlighet mellan enheter i övre vänstra, tillförlitlighet över tidsdiagram i övre högra, översta problemtabellen längst ned.](../../media/insights_reliability.png)

<span data-ttu-id="69b08-108">**Avsnittet Tillförlitlighet mellan enheter** ger en snabb hälsosammanfattning av distributionen under de senaste 14 dagarna genom att rapportera hur många procent av enheter som anses vara "felfria" och den genomsnittliga tiden som observerats sedan det senaste rapporterade felet.</span><span class="sxs-lookup"><span data-stu-id="69b08-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="69b08-109">**Diagrammet Tillförlitlighet över tid** till höger visar antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tid.</span><span class="sxs-lookup"><span data-stu-id="69b08-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="69b08-110">Avsnittet **Översta problem** innehåller specifika problem som påverkar minst 5 % av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="69b08-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="69b08-111">Rapporterade uppgifter inkluderar:</span><span class="sxs-lookup"><span data-stu-id="69b08-111">Reported details include:</span></span>

- <span data-ttu-id="69b08-112">Typ av problem</span><span class="sxs-lookup"><span data-stu-id="69b08-112">The type of issue</span></span>
    - <span data-ttu-id="69b08-113">Programmet kraschar, där en app slutar fungera eller oväntat slutar</span><span class="sxs-lookup"><span data-stu-id="69b08-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="69b08-114">Programmet låser sig, där ett program slutar svara på indata</span><span class="sxs-lookup"><span data-stu-id="69b08-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="69b08-115">Kritiska fel, som uppstår när windows har stött på ett problem som det inte kan återställa från</span><span class="sxs-lookup"><span data-stu-id="69b08-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="69b08-116">Antalet enheter som påverkas av samma problem</span><span class="sxs-lookup"><span data-stu-id="69b08-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="69b08-117">Procentandelen hanterade enheter som antalet representerar</span><span class="sxs-lookup"><span data-stu-id="69b08-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="69b08-118">Det totala antalet händelser för det specifika problemet</span><span class="sxs-lookup"><span data-stu-id="69b08-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="69b08-119">Programvarukomponenten som verkar vara källan till problemet</span><span class="sxs-lookup"><span data-stu-id="69b08-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="69b08-120">Kategorin för det upptäckta problemet:</span><span class="sxs-lookup"><span data-stu-id="69b08-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="69b08-121">Webbläsare (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="69b08-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="69b08-122">Okänd (komponenter som inte kommer från Microsoft)</span><span class="sxs-lookup"><span data-stu-id="69b08-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="69b08-123">Drivrutin (ljud, grafik eller andra drivrutiner)</span><span class="sxs-lookup"><span data-stu-id="69b08-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="69b08-124">Produktivitet (Slack, G-Suites, Microsoft Office och dess tillägg eller tillägg, Teams)</span><span class="sxs-lookup"><span data-stu-id="69b08-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="69b08-125">Medieappar (bild-, musik- eller videoappar</span><span class="sxs-lookup"><span data-stu-id="69b08-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="69b08-126">Säkerhet (Windows-säkerhetskomponenter)</span><span class="sxs-lookup"><span data-stu-id="69b08-126">Security (Windows security components)</span></span>
- <span data-ttu-id="69b08-127">Den aktuella statusen när Microsoft Managed Desktop Operations undersöker och åtgärdar problemet</span><span class="sxs-lookup"><span data-stu-id="69b08-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

