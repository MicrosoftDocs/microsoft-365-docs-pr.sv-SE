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
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950348"
---
# <a name="reliability-insights"></a><span data-ttu-id="a4d42-103">Tillförlitlighetsinsikter</span><span class="sxs-lookup"><span data-stu-id="a4d42-103">Reliability insights</span></span>

<span data-ttu-id="a4d42-104">I den här vyn får du en översikt över dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="a4d42-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="a4d42-105">Om du vill visa pålitlighets data väljer du fliken **pålitlighet** .</span><span class="sxs-lookup"><span data-stu-id="a4d42-105">To view reliability data, select the **Reliability** tab.</span></span>


![Fönstret tillförlitlighet: tillförlitlighet mellan enheter uppe till vänster, högre tillförlitlighet än tids diagram längst upp till höger, tabellen vanligaste problem nedtill.](../../media/insights_reliability.png)

<span data-ttu-id="a4d42-108">Avsnittet **tillförlitlighet i flera enheter** erbjuder en översikt över de senaste 14 dagarna genom rapportering om procent andelen av enheter som anses vara "felfri" och genomsnittlig tid som observerats sedan det senaste rapporterade felet.</span><span class="sxs-lookup"><span data-stu-id="a4d42-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="a4d42-109">Diagrammets **tillförlitlighet över tid** till höger rapporterar antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tiden.</span><span class="sxs-lookup"><span data-stu-id="a4d42-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="a4d42-110">Avsnittet **TOPY** retails visar specifika upptäckta problem som påverkar minst 5% av dina hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="a4d42-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="a4d42-111">Rapporterade uppgifter inkluderar:</span><span class="sxs-lookup"><span data-stu-id="a4d42-111">Reported details include:</span></span>

- <span data-ttu-id="a4d42-112">Typ av problem</span><span class="sxs-lookup"><span data-stu-id="a4d42-112">The type of issue</span></span>
    - <span data-ttu-id="a4d42-113">Program kraschar, där ett program slutar fungera eller oväntat stoppas</span><span class="sxs-lookup"><span data-stu-id="a4d42-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="a4d42-114">Programmet hänger sig, där ett program slutar svara för inmatning</span><span class="sxs-lookup"><span data-stu-id="a4d42-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="a4d42-115">Kritiska fel, som uppstår när ett problem har uppstått i Windows</span><span class="sxs-lookup"><span data-stu-id="a4d42-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="a4d42-116">Antalet enheter som påverkas av samma problem</span><span class="sxs-lookup"><span data-stu-id="a4d42-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="a4d42-117">Procent andelen hanterade enheter som numret representerar</span><span class="sxs-lookup"><span data-stu-id="a4d42-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="a4d42-118">Totalt antal förekomster av det specifika problemet</span><span class="sxs-lookup"><span data-stu-id="a4d42-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="a4d42-119">Program varu komponenten som verkar vara orsaken till problemet</span><span class="sxs-lookup"><span data-stu-id="a4d42-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="a4d42-120">Kategorin för det upptäckta problemet:</span><span class="sxs-lookup"><span data-stu-id="a4d42-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="a4d42-121">Webbläsare (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="a4d42-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="a4d42-122">Okända (icke-Microsoft-komponenter)</span><span class="sxs-lookup"><span data-stu-id="a4d42-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="a4d42-123">Driv rutin (ljud, grafik eller andra driv rutiner)</span><span class="sxs-lookup"><span data-stu-id="a4d42-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="a4d42-124">Produktivitet (slack, G-sviter, Microsoft Office och tillägg och tillägg, Team)</span><span class="sxs-lookup"><span data-stu-id="a4d42-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="a4d42-125">Media (bild-, musik-eller videoappar</span><span class="sxs-lookup"><span data-stu-id="a4d42-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="a4d42-126">Säkerhet (Windows säkerhets komponenter)</span><span class="sxs-lookup"><span data-stu-id="a4d42-126">Security (Windows security components)</span></span>
- <span data-ttu-id="a4d42-127">Den aktuella statusen som Microsoft Managed Desktop-operationer undersöker och åtgärdar problemet</span><span class="sxs-lookup"><span data-stu-id="a4d42-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

