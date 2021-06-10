---
title: Beslut baserat på resultaten i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Läs om hur du hittar data Advanced eDiscovery fliken Bestämmer i Advanced eDiscovery som kan hjälpa dig att avgöra rätt storlek på granskningsuppsättningen med ärendefiler.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161773"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="e1d57-103">Beslut baserade på relevansresultat i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e1d57-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="e1d57-104">I modulen Relevans i Advanced eDiscovery på fliken Bestämmer finns mer information för att visa och använda statistik för beslutssupport för att fastställa storleken på granskningsuppsättningen av ärendefiler.</span><span class="sxs-lookup"><span data-stu-id="e1d57-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="e1d57-105">Använda fliken Bestämmer</span><span class="sxs-lookup"><span data-stu-id="e1d57-105">Using the Decide tab</span></span>

![Relevans Bestäm](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="e1d57-107">Den här fliken innehåller följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="e1d57-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="e1d57-108">**Problem:** Härifrån kan du välja intressefrågan i listan.</span><span class="sxs-lookup"><span data-stu-id="e1d57-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="e1d57-109">**Review-recall ratio**: Jämförelser av Advanced eDiscovery granska i enlighet med relevansresultat.</span><span class="sxs-lookup"><span data-stu-id="e1d57-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="e1d57-110">Brytpunkten i diagrammet representerar procentandelen filer att granska, mappade till ett relevansresultat.</span><span class="sxs-lookup"><span data-stu-id="e1d57-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="e1d57-111">Det här används i fasen Relevanstest och som ett exporttröskelvärde för testning.</span><span class="sxs-lookup"><span data-stu-id="e1d57-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="e1d57-112">Som standard är saldot mellan Återkallelse och Precision optimalt för antalet filer som ska granskas.</span><span class="sxs-lookup"><span data-stu-id="e1d57-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="e1d57-113">Den faktiska brytpunkten ska fastställas av användaren beroende på mål och kostnads kompromiss (%review) och risk (%recall).</span><span class="sxs-lookup"><span data-stu-id="e1d57-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="e1d57-114">Med skjutreglaget kan du justera brytpunkten och se effekten på diagrammet och parametrarna, när du justerar hur många procent av relevanta filer som ska hämtas och innan du verifierar ett beslut.</span><span class="sxs-lookup"><span data-stu-id="e1d57-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="e1d57-115">**Parametrar:** Granska, Återkalla, Nästa relevanta parametrar och Parametrar för totalkostnad är ackumulerad beräknad statistik som hör till granskningsuppsättningen i relation till samlingen för hela ärendet.</span><span class="sxs-lookup"><span data-stu-id="e1d57-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="e1d57-116">Definitioner för dessa parametrar är följande:</span><span class="sxs-lookup"><span data-stu-id="e1d57-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="e1d57-117">**Granska:** Procentandel av filer som ska granskas baserat på den här brytningen.</span><span class="sxs-lookup"><span data-stu-id="e1d57-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="e1d57-118">**Återkalla:** Procentandel av relevanta filer i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e1d57-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="e1d57-119">**Nästa relevanta**: Kostnad för granskning och identifiera en annan relevant fil som inte finns med i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e1d57-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="e1d57-120">**Total kostnad:** Kostnad för att granska denna procent av ärendefilerna.</span><span class="sxs-lookup"><span data-stu-id="e1d57-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="e1d57-121">Kostnadsparameterinställningar kan anges av ärendehanteraren.</span><span class="sxs-lookup"><span data-stu-id="e1d57-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="e1d57-122">**Fördelning efter relevansresultat:** Filer i den mörkgrå visningen till vänster är under brytresultatet.</span><span class="sxs-lookup"><span data-stu-id="e1d57-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="e1d57-123">I en verktygstips visas Relevansresultat och den relaterade procentandelen filer i granskningsfilen som angetts i förhållande till det totala antalet filer.</span><span class="sxs-lookup"><span data-stu-id="e1d57-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="e1d57-124">I det utökade **informationsfönstret** visas mer information.</span><span class="sxs-lookup"><span data-stu-id="e1d57-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="e1d57-125">Filer på samlingsfigurer omfattar inte tomma eller nebulous-filer.</span><span class="sxs-lookup"><span data-stu-id="e1d57-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="e1d57-126">Familjefiler representerar filer som inte lästs in i Relevans, men fortfarande räknas som en del av familjen.</span><span class="sxs-lookup"><span data-stu-id="e1d57-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
