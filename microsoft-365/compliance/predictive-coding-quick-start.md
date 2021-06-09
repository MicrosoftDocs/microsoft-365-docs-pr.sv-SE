---
title: Prediktiv kodning i Advanced eDiscovery – snabbstart
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
description: Lär dig hur du kommer igång med prediktiv kodningsmodulen i Advanced eDiscovery. Den här artikeln beskriver hur du kan använda förutsägelsekodning för att identifiera innehåll i en granskningsuppsättning som är mest relevant för din undersökning.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822623"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Snabbstart: Förutsägelsekodning i Advanced eDiscovery (förhandsversion)

I den här artikeln får du en snabbstart med att använda förutsägelsekodning i Advanced eDiscovery. Prediktiv kodningsmodulen i Advanced eDiscovery använder intelligenta maskininlärningsfunktionerna i Advanced eDiscovery hjälper dig att minska mängden innehåll som ska granskas. Med förutsägande kodning kan du minska och anpassa stora mängder ärendeinnehåll till en relevant uppsättning objekt som du kan prioritera för granskning. Detta sker genom att skapa och träna egna prediktiv kodningsmodeller som hjälper dig att prioritera granskningen av de mest relevanta objekten i en granskningsuppsättning.

Här är en snabb överblick över prediktiv kodningsprocess:

![Snabbstart för förutsägelsekodning](..\media\PredictiveCodingQuickStartProcess.png)

Kom igång genom att skapa en modell, etikettera så få som 50 objekt som relevanta eller inte relevanta. Sedan använder systemet den här utbildningen för att tillämpa förutsägelseresultat på alla objekt i uppsättningen med granskning. På så sätt kan du filtrera objekt baserat på förutsägelseresultatet, så att du först kan granska de mest relevanta (eller icke-relevanta) elementen. Om du vill utbilda modeller med högre precision och återkallelsefrekvenser kan du fortsätta märka objekt i efterföljande utbildning avrundar tills modellen har en högre precision. När modellen är bortfasad kan du använda det slutliga prognosfiltret och prioritera objekt att granska.

En detaljerad översikt över prediktiv kodning finns i [Lär dig mer om prediktiv kodning i Advanced eDiscovery](predictive-coding-overview.md).

## <a name="step-1-create-a-new-predictive-coding-model"></a>Steg 1: Skapa en ny prediktiv kodningsmodell

Det första steget är att skapa en ny prediktiv kodmodell i granskningsuppsättningen

1. I Microsoft 365, öppna ett ärende Advanced eDiscovery välj sedan fliken **Granska uppsättningar.**

2. Öppna en granskningsuppsättning och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**

   ![Klicka på listrutan Analysera i granskningsuppsättningen för att gå till sidan Predictive coding](..\media\ManagePredictiveCoding.png)

3. Klicka på **Ny modell på sidan Prediktiv kodningsmodeller (förhandsversion).** 

4. Ange ett namn för modellen och en valfri beskrivning på den utfällbara sidan.

5. Klicka **på** Spara för att skapa modellen.

   Det tar några minuter innan systemet har förberett modellen. När den är klar kan du utföra den första utbildningsomgången.

Mer detaljerade anvisningar finns i Skapa [en prediktiv kodningsmodell](predictive-coding-create-model.md).

## <a name="step-2-perform-the-first-training-round"></a>Steg 2: Genomför den första utbildningsomgången

När du har skapat modellen är nästa steg att slutföra den första utbildningsomgången genom att märka objekt som relevanta eller inte relevanta.

1. Öppna granskningsuppsättningen och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**

2. På sidan **Prediktiv kodningsmodeller (förhandsvisning)** väljer du den modell som du vill träna.

3. Klicka på **Starta** nästa utbildningsrunda under **Avrunda 1** **på fliken Översikt.**

   Fliken **Utbildning** visas och innehåller 50 objekt som du kan lägga till etiketter för.

4. Granska varje dokument och välj sedan **knappen Relevant** eller **Inte relevant** längst ned i läsfönstret för att märka det.

   ![Märka varje dokument som relevant eller inte relevant](..\media\TrainModel1.png)

5. När du har etiketterat alla 50 objekt klickar du på **Slutför**.

    Det tar några minuter innan systemet "lär sig" av etiketterna och uppdaterar modellen. När den här processen är klar visas **statusen för Ready** för modellen på sidan **Predictive coding models (preview).**

Mer detaljerade anvisningar finns i Utbilda [en prediktiv kodningsmodell](predictive-coding-train-model.md).

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Steg 3: Använd filtret för förutsägelseresultat för objekt i granskningsuppsättningen

När du har leasa en utbildningsrunda kan du använda filtret för förutsägelseresultat på objekt i granskningsuppsättningen. Då kan du granska de objekt som modellen har prognosterat som relevanta eller inte relevanta.   

1. Öppna granskningsuppsättningen.

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

Mer detaljerade anvisningar finns i Använda [ett prognosfilter för en granskningsuppsättning](predictive-coding-apply-prediction-filter.md).

## <a name="step-4-perform-more-training-rounds"></a>Steg 4: Genomför fler utbildningsrundar

Mer än troligt måste du utföra fler utbildningsrundar för att utbilda modulen för att bättre förutsäga relevanta och icke-relevanta objekt i granskningsuppsättningen. I allmänhet kan du träna modellen tillräckligt många gånger tills den blir tillräckligt bra för att uppfylla dina krav.

Mer information finns i Utföra [ytterligare utbildning avrundar](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Steg 5: Använd det slutliga betygsfiltret i förutsägelsen för att prioritera granskningen

Upprepa anvisningarna i steg 3 för att tillämpa det slutliga prognosresultatet på granskningsuppsättningen för att prioritera granskningen av relevanta och icke-relevanta objekt när du har slutfört alla utbildning avrundar och tillämpar modellen.
