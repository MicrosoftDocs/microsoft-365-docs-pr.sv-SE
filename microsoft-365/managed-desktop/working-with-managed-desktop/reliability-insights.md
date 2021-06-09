---
title: Tillförlitlighetsinsikter
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739817"
---
# <a name="reliability-insights"></a><span data-ttu-id="f29f5-103">Tillförlitlighetsinsikter</span><span class="sxs-lookup"><span data-stu-id="f29f5-103">Reliability insights</span></span>

<span data-ttu-id="f29f5-104">Den här vyn ger dig en hälsosammanfattning av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="f29f5-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="f29f5-105">Om du vill visa tillförlitlighetsdata väljer du **fliken Tillförlitlighet.**</span><span class="sxs-lookup"><span data-stu-id="f29f5-105">To view reliability data, select the **Reliability** tab.</span></span>


![Tillförlitlighetsfönster: Tillförlitlighet på enheter i det övre vänstra hörnet, tillförlitlighet över tid, diagram över övre högra hörnet, den översta problemtabellen längst ned.](../../media/insights_reliability.png)

<span data-ttu-id="f29f5-108">I **avsnittet Tillförlitlighet** på enheter får du en snabb sammanfattning av distributionen under de senaste 14 dagarna genom att rapportera procentandel enheter som anses vara "felfria" och den genomsnittliga tiden som observerats sedan det senast rapporterade felet.</span><span class="sxs-lookup"><span data-stu-id="f29f5-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="f29f5-109">I **diagrammet Tillförlitlighet** över tid på höger sida visas antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tid.</span><span class="sxs-lookup"><span data-stu-id="f29f5-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="f29f5-110">Avsnittet **Om de viktigaste** problemen beskriver specifika identifierade problem som påverkar minst 5 % av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="f29f5-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="f29f5-111">Rapporterad information:</span><span class="sxs-lookup"><span data-stu-id="f29f5-111">Reported details include:</span></span>

- <span data-ttu-id="f29f5-112">Typ av problem</span><span class="sxs-lookup"><span data-stu-id="f29f5-112">The type of issue</span></span>
    - <span data-ttu-id="f29f5-113">Programmet kraschar, där en app slutar fungera eller oväntat slutar fungera</span><span class="sxs-lookup"><span data-stu-id="f29f5-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="f29f5-114">Programmet hänger sig där ett program slutar svara på indata</span><span class="sxs-lookup"><span data-stu-id="f29f5-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="f29f5-115">Kritiska fel som inträffar när Windows har stött på problem kan det inte återställas från</span><span class="sxs-lookup"><span data-stu-id="f29f5-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="f29f5-116">Antalet enheter som påverkas av samma problem</span><span class="sxs-lookup"><span data-stu-id="f29f5-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="f29f5-117">Procentandelen hanterade enheter som talet representerar</span><span class="sxs-lookup"><span data-stu-id="f29f5-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="f29f5-118">Det totala antalet förekomster av ett specifikt problem</span><span class="sxs-lookup"><span data-stu-id="f29f5-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="f29f5-119">Programvarukomponenten som verkar vara orsaken till problemet</span><span class="sxs-lookup"><span data-stu-id="f29f5-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="f29f5-120">Kategorin för det identifierade problemet:</span><span class="sxs-lookup"><span data-stu-id="f29f5-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="f29f5-121">Webbläsare (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="f29f5-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="f29f5-122">Okänd (komponenter som inte kommer från Microsoft)</span><span class="sxs-lookup"><span data-stu-id="f29f5-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="f29f5-123">Drivrutin (ljud, grafik eller andra drivrutiner)</span><span class="sxs-lookup"><span data-stu-id="f29f5-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="f29f5-124">Produktivitet (slack, G-Microsoft Office, tillägg och tillägg, Teams)</span><span class="sxs-lookup"><span data-stu-id="f29f5-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="f29f5-125">Media (bild-, musik- eller videoappar)</span><span class="sxs-lookup"><span data-stu-id="f29f5-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="f29f5-126">Säkerhet (Windows säkerhetskomponenter)</span><span class="sxs-lookup"><span data-stu-id="f29f5-126">Security (Windows security components)</span></span>
- <span data-ttu-id="f29f5-127">Den aktuella statusen Microsoft Hanterat skrivbord åtgärder undersöker och åtgärdar problemet</span><span class="sxs-lookup"><span data-stu-id="f29f5-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

