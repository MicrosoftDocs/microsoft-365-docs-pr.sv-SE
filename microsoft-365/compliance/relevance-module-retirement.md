---
title: Relevansmodulen i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Relevansmodulen i Advanced eDiscovery dras tillbaka den 10 mars 2021. I den här artikeln förklaras vad du kan göra innan Relevans dras tillbaka. Mer specifikt kan du avsluta alla oavslutade modeller genom att köra batchberäkningar så att du kan behålla metadata från modellen.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822003"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Relevansmodulen i Advanced eDiscovery

Den 10 mars 2021 drar vi tillbaka relevansmodulen i Advanced eDiscovery. Det innebär att organisationer inte längre har tillgång till relevansmodulen (genom att gå till Hantera granskningsuppsättning relevans i ett Advanced eDiscovery fall) eller kan komma åt befintliga  >   relevansmodeller. Den aktuella relevansmodulen som dras tillbaka ersätts med en ny prediktiv kodningslösning i Q2 CY 2021. Med de nya funktionerna kan organisationer skapa egna prediktiv kodningsmodeller i ett enklare och mer intuitivt arbetsflöde.

För att förbereda för den här kommande ingången rekommenderar vi att organisationer som använder relevansmodulen exporterar sina modellers utdata innan utgångsdatumet genom att köra en batchberäkning för alla befintliga modeller. Alla relevansresultat från din modell lagras permanent i motsvarande granskningsuppsättning och är tillgängliga när dokument exporteras. Relevansresultat sparas också som metadata i inläsningsfilen. Du kan också fortfarande filtrera innehåll i granskningsuppsättningen baserat på relevansresultat och få åtkomst till alla metadata som skapas av dina relevansmodeller.

## <a name="complete-unfinished-models"></a>Slutföra oavslutade modeller

För alla oavslutade relevansmodeller bör du utföra en utvärdering, utbildning och batchberäkning så att du kan använda modellen på dokumenten i en granskningsuppsättning. När du slutför batchberäkningen behålls informationen efter att relevansmodulen har avslutats.

Här är stegen för att slutföra alla oavslutade modeller:

1. Utbilda modellen tills den har omts och är redo för batchberäkning. Se [Tagga och relevansutbildning.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   På följande skärmbild visas en modul som är redo för en batchberäkning. Lägg märke till att utvärdering och utbildning är klar och att nästa steg är att köra Batchberäkning.

   ![Skärmbild av modell klar för batchberäkning](../media/ReadyForBatchCalculation.png)

2. Kör batchberäkningen. Mer information [finns i Utföra batchberäkningar.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Kontrollera att batchberäkningen har lyckats. Läs [Batchberäkningsresultat](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).

Om du behöver hjälp med att slutföra oavslutade relevansmodeller kontaktar du Microsoft Support.
