---
title: Använda filtret för förutsägelseresultat för objekt i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Använd ett filter för förutsägelseresultat för att visa objekt som en prediktiv kodmodell som förutsagd som relevant eller inte relevant.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822591"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Använda ett filter för förutsägelseresultat i en granskningsuppsättning (förhandsgranskning)

När du har skapat en prognoskodningsmodell i Advanced eDiscovery och tränat den till den punkt där den är stabil, kan du använda poängfiltret för förutsägelse för att visa granskade objekt som har fastställt av modellen är relevanta (eller inte relevanta). När du skapar en modell skapas också ett motsvarande filter för förutsägelseresultat. Du kan använda filtret för att visa objekt som tilldelats ett förutsägelseresultat inom ett visst område. I allmänhet tilldelas förutsägelser för resultat mellan **0** och **0,5** till objekt som har prognosterats i modellen. Objekt som tilldelats **förutsägelseresultat mellan 0,5** och **1,0** är objekt som modellen har prognosterat är relevanta.

Du kan använda filtret för förutsägelseresultat på två sätt:

- Prioritera granskningen av objekt i en granskningsuppsättning som modellen har prognosterat är relevant.

- Objekt från granskningsuppsättningen som modellen har prognosterat är inte relevanta. Alternativt kan du använda filtret för förutsägelseresultat för att avprioritera granskningen av icke-relevanta objekt.

## <a name="before-you-apply-a-prediction-score-filter"></a>Innan du använder ett filter för förutsägelseresultat

- Skapa en prediktiv kodningsmodell så att ett motsvarande filter för förutsägelseresultat skapas.

- Du kan använda ett filter för förutsägelseresultat efter någon av utbildningarna. Men det kan vara bra att vänta efter att ha utfört flera omgångar eller tills modellen är stabil innan du använder filtret för prognosresultat.

## <a name="apply-a-prediction-score-filter"></a>Använda ett filter för förutsägelseresultat

1. I Microsoft 365 öppnar du fliken Advanced eDiscovery, väljer fliken Granska **uppsättningar** och öppnar sedan granskningsuppsättningen.

   ![Klicka på Filter för att visa den utfällade filtersidan](..\media\PredictionScoreFilter0.png)   

   De förinstallerade standardfiltren visas högst upp på sidan för granskningsuppsättningen. Du kan låta dessa vara inställda på **Alla**.

2. Klicka **på Filter** så att den **utfällade sidan** Filter visas.

3. Expandera **analysavsnittet & förutsägelsekodning** för att visa en uppsättning filter.

      ![Filter för förutsägelseresultat i & för förutsägelsekodning](..\media\PredictionScoreFilter1.png)

   Namngivningskonventioner för resultatfilter för **förutsägelser är Förutsägelseresultat (modellnamn).** Namnet på filtret för förutsägelseresultat för en modell med namnet **Modell A** är till exempel **Prognosresultat (Modell A).**

4. Välj det filter för förutsägelseresultat som du vill använda och klicka sedan på **Klar**.

5. På sidan för granskningsuppsättningen klickar du på listrutan för filtret för förutsägelseresultat och anger minimi- och maxvärden för förutsägelseresultatintervallet. Följande skärmbild visar till exempel ett resultatintervall för förutsägelse mellan **0,5** och **1,0.**

   ![Lägsta och högsta värden för filtret för förutsägelseresultat](..\media\PredictionScoreFilter2.png)

6. Klicka utanför filtret så tillämpas filtret automatiskt på granskningsuppsättningen.

  En lista med dokument med ett förutsägelseresultat inom det angivna intervallet visas på sidan för granskningsuppsättningen. 

  > [!TIP]
  > Om du vill visa det faktiska förutsägelseresultatet för ett dokument kan du klicka på **fliken Metadata** i läsfönstret. Förutsägelseresultat för alla modeller i granskningsuppsättningen visas i **metadataegenskapen RelevanceScores.**

## <a name="more-information"></a>Mer information

- Mer information om hur du använder filter finns i [Skapa frågor och filtrera innehåll i en granskningsuppsättning](review-set-search.md).
