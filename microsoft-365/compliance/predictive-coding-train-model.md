---
title: Utbilda en prediktiv kodningsmodell i Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84bb34f8ec1b935dc30072e16f57b5f5665c3546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226221"
---
# <a name="train-a-predictive-coding-model-preview"></a>Utbilda en prediktiv kodningsmodell (förhandsversion)

När du har skapat en prognoskodningsmodell i Advanced eDiscovery är nästa steg att utföra den första utbildningsomgången för att utbilda modellen på vad som är relevant och icke-relevant innehåll i din granskningsuppsättning. När du har slutfört den första utbildningsomgången kan du utföra efterföljande utbildningsrundar för att förbättra modellens möjlighet att förutsäga relevant och icke relevant innehåll.

Information om hur du granskar arbetsflödet för förutsägelsekodning finns [i Lär dig mer om prediktiv kodning i Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Innan du utbildar en modell

- Under en utbildningsrunda kan du **ange** att objekten ska **vara relevanta** eller inte relevanta baserat på hur relevant innehållet i dokumentet är. Basera inte ditt beslut på värdena i metadatafälten. Om du till exempel vill skicka e Teams eller konversationer baserar du inte etikettbeslutet på meddelandedeltagarna.

## <a name="train-a-model-for-the-first-time"></a>Utbilda en modell för första gången

1. I Microsoft 365 Efterlevnadscenter öppnar du ett Advanced eDiscovery och väljer sedan **fliken Granska uppsättningar.**

2. Öppna en granskningsuppsättning och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**

3. På sidan **Prediktiv kodningsmodeller (förhandsvisning)** väljer du den modell som du vill träna.

4. Klicka på **Starta** nästa utbildningsrunda under **Avrunda 1** **på fliken Översikt.**

   Fliken **Utbildning** visas och innehåller 50 objekt som du kan lägga till etiketter för.

5. Granska varje dokument och välj sedan **knappen Relevant** eller **Inte relevant** längst ned i läsfönstret för att märka det.

   ![Märka varje dokument som relevant eller inte relevant](..\media\TrainModel1.png)

6. När du har etiketterat alla 50 objekt klickar du på **Slutför**.

    Det tar några minuter innan systemet "lär sig" av etiketterna och uppdaterar modellen. När den här processen är klar visas **statusen för Ready** för modellen på sidan **Predictive coding models (preview).**

## <a name="perform-additional-training-rounds"></a>Utföra ytterligare utbildningsrundar

När du har genomför den första utbildningsomgången kan du utföra efterföljande utbildningsrundar genom att följa stegen i föregående avsnitt. Den enda skillnaden är att numret på utbildningsomgången uppdateras på fliken **Modellöversikt.** Efter den första utbildningsomgången kan du till exempel klicka på **Starta nästa utbildningsrunda** för att starta den andra utbildningsomgången. Och så vidare.

Varje omgång med utbildning (både pågående och pågående) visas på **fliken Utbildning** för modellen. När du väljer en utbildningsrunda visas en utfällbordssida med information och mått för avrundningen.

## <a name="what-happens-after-you-perform-a-training-round"></a>Vad händer efter att du har genomför en utbildningsrunda?

När du har genomför den första utbildningsomgången startas ett jobb som gör följande:

- Modellen lär sig av dina etiketter och uppdateringar baserat på hur du har etiketterat 40 objekt i utbildningsuppsättningen för att göra den mer exakt.

- Modellen bearbetar sedan varje objekt i hela granskningsuppsättningen och tilldelar ett prognosresultat mellan **0** (inte relevant) och **1** (relevant).

- Modellen tilldelar ett förutsägelseresultat till de 10 objekten i kontrolluppsättningen som du har angett under utbildningsomgången. Modellen jämför förutsägelseresultatet för dessa 10 objekt med den faktiska etikett som du har tilldelat till objektet under utbildningsomgången. Utifrån denna jämförelse identifierar modellen följande klassificering (kallas kontrolluppsättningens förväxlingsmatris) för att bedöma modellens prognosprestanda:

  |          |Modell förutsägelser om att objekt är relevanta |Modell förutsägelser om att objekt inte är relevanta |
  |:---------|:---------|:---------|
  |**Granskaren ser objekt som relevant**| Sant positivt| Falskt positivt resultat |
  |**Granskaren ser att objektet inte är relevant**| Falskt negativt |Sant negativt |
  ||||

  Utifrån dessa jämförelser härleder modellen värden för måtten F-poäng, precision och återkallelse samt felmarginalen för var och en av dem. Resultat för dessa modellprestandamätvärden visas på en utfällbordssida för utbildningsomgången. En beskrivning av mätvärdena finns i [Prediktiv kodningsreferens](predictive-coding-reference.md).

- Slutligen avgör modellen de nästa 50 objekt som ska användas för nästa utbildningsomgång. Den här gången kan modellen välja 20 objekt i kontrolluppsättningen och 30 nya objekt från granskningsuppsättningen och ange dem som utbildningsuppsättning för nästa omgång. Samplingen för nästa utbildningsrunda sampel sker inte enhetligt. Modellen optimerar urval av objekt från granskningsuppsättningen för att välja objekt där prognosen är tvetydig, vilket innebär att prognosresultatet ligger i intervallet 0,5. Den här processen kallas för *partisk markering.*

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>Vad som händer efter att du har avrundat efterföljande kurser

När du har avrundat ytterligare utbildning (efter den första utbildningsomgången) gör modellen följande:

- Modellen uppdateras baserat på etiketterna som du har använt för utbildningsuppsättningen i den omgången av utbildningen.

- Systemet utvärderar modellens prognosresultat på objekten i kontrolluppsättningen och kontrollerar om resultatet överensstämmer med hur du etiketterade objekt i kontrolluppsättningen. Utvärderingen utförs på alla märkta objekt från kontrolluppsättningen för alla utbildningsrundar. Resultaten av den här utvärderingen har tagits med i instrumentpanelen på **fliken** Översikt för modellen.

- Den uppdaterade modellen bearbetar alla objekt i granskningsuppsättningen och tilldelar varje objekt ett uppdaterat prognosresultat.

## <a name="next-steps"></a>Nästa steg

Efter att du har genomför den första utbildningsomgången kan du utföra fler utbildningsrundar eller använda modellens resultatfilter för förutsägelseresultat för granskningsuppsättningen för att visa de objekt som modellen har prognosterat som relevanta eller inte relevanta. Mer information finns i Använda [ett filter för förutsägelseresultat i en granskningsuppsättning](predictive-coding-apply-prediction-filter.md).
