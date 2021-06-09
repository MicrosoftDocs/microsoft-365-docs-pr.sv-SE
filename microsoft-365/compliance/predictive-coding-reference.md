---
title: Prediktiv kodningsreferens
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
ms.openlocfilehash: 90c76fade54c109fc02e145a49bbe93d11ad8b79
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822590"
---
# <a name="predictive-coding-reference-preview"></a>Referens för prediktiv kodning (förhandsversion)

I den här artikeln beskrivs viktiga begrepp och mätvärden i verktyget för prediktiv kodning i Advanced eDiscovery. Avsnitten i artikeln visas i alfabetisk ordning.

## <a name="confidence-level"></a>Konfidensnivå

Konfidensnivån är en avancerad inställning när du skapar en prediktiv kodningsmodell. Den definierar att modellens prestandamått (till exempel richness, precision och recall) faller inom ett angivet intervall (som bestäms av felmarginalen som definierats för modellen) som är representativ för de sanna värdena i förutsägelseresultatet som modellen tilldelar till objekt i granskningsuppsättningen. Värdena för konfidensnivån och marginalen för fel hjälper också till att avgöra hur många objekt som ingår i kontrolluppsättningen. Standardvärdet för konfidensnivån är 0,95 eller 95 %.

## <a name="control-set"></a>Kontrolluppsättning

En kontrolluppsättning används under utbildningsprocessen för en prediktiv kodningsmodell. Kontrolluppsättningen är att beräkna de resultat i prognoser som modellen tilldelar till objekt med etiketten som du utför under utbildning avrundas. Storleken på kontrolluppsättningen baseras på antalet objekt i granskningsuppsättningen och konfidensnivån och marginalen för felvärden som anges när modellen skapas. Objekten i kontrollen ändras aldrig och kan inte identifieras av användarna. Det totala antalet objekt i kontrolluppsättningen visas på den utfällbordssidan under en utbildningsrunda.

## <a name="control-set-confusion-matrix"></a>Kontrolluppsättningsmatris för förvirring

När du har slutfört en utbildningsomgång tilldelar modellen ett förutsägelseresultat till de 10 objekten i kontrolluppsättningen som du har etiketterat under utbildningsomgången. Modellen jämför förutsägelseresultatet för dessa 10 objekt med den faktiska etikett som du har tilldelat till objektet under utbildningsomgången. Utifrån den här jämförelsen identifierar modellen följande klassificeringar för att bedöma modellens prognosprestanda:
  
  |          |Modell förutsägelser om att objekt är relevanta |Modell förutsägelser om att objekt inte är relevanta |
  |:---------|:---------|:---------|
  |**Granskaren ser objekt som relevant**| Sant positivt| Falskt positivt resultat |
  |**Granskaren ser att objektet inte är relevant**| Falskt negativt |Sant negativt |
  ||||

  Utifrån dessa jämförelser härleder modellen värden för måtten F-poäng, precision och återkallelse samt felmarginalen för var och en av dem. Antalet förväxlingstyper i matrisen visas på den utfällade sidan i en utbildningsrunda.

## <a name="f-score"></a>F-poäng

F-poäng är ett viktat medelvärde av poäng för precisions- och återkallelsemått.  Resultatintervallet för det här värdet är **från 0** till **1.** En poäng som ligger **närmare 1** anger att modellen identifierar relevanta objekt mer exakt. Måttet F-poäng visas på instrumentpanelen för modellen och på den utfällbaserade sidan för varje utbildningsrunda.

## <a name="margin-of-error"></a>Felmarginal

Felmarginalen är en avancerad inställning när du skapar ett prediktivt kodningsläge. Den anger graden av fel i prestandamått (till exempel richness, precision och recall) som härleds från det slumpmässiga samplingen av objekt i din kontrolluppsättning. En lägre marginal för fel kräver en större kontrolluppsättning för att säkerställa att modellens prestandamått faller inom ett mindre intervall. Värdena för felmarginalen och konfidensnivån hjälper också till att avgöra hur många objekt som ingår i kontrolluppsättningen. Standardvärdet för felmarginalen är 0,05 eller 5 %.

## <a name="model-stability"></a>Modellstabilitet

Modellstabiliteten anger modellens förmåga att exakt förutsäga om ett dokument i en granskningsuppsättning är relevant eller inte relevant. När en modell är instabil kan fler utbildningsrundar behöva utföras för att inkludera modellens stabilitet. När modellen är stabil kan det hända att inga fler utbildningsrundar behöver utföras. Modellinstrumentpanel visar den aktuella statusen för modellens stabilitet. När en modell är stabil har prestandamätvärden nått en nivå som matchar inställningarna för konfidensnivå och marginal för fel.

## <a name="overturn-rate"></a>Overturn rate

Overturn rate is the percentage of items in the review set where the prediction score changed between training rounds. En modell anses vara stabil när omräkningen är mindre än 5 %. Måttet för overturn rate visas på modellinstrumentpanelen och på den utfällliga sidan för varje utbildningsrunda. Overturn rate for the first training round is zero because there isn't a previous prediction score to overturn.

## <a name="precision"></a>Precision

Precisionsmåttet mäter andelen av objekt som faktiskt är relevanta bland de objekt som modellen förutsagt var relevanta. Det innebär att elementen i kontrolluppsättningen där etiketten är relevant av granskaren och förutsägs som relevant av modellen. Resultatintervallet för det här värdet är **från 0** till **1.** En poäng som ligger **närmare 1** anger att modellen identifierar färre objekt som inte är relevanta. Precisionsmåttet visas på modellinstrumentpanelen och på den utfällbordssidan för varje utbildningsrunda.

## <a name="prediction-score"></a>Förutsägelseresultat

Det här är den poäng som en modell tilldelar till varje dokument i en granskningsuppsättning. Poängen baseras på dokumentets relevans jämfört med hur modellen utbildar sig genom utbildningarna. I allmänhet anses objekt med förutsägelseresultat **mellan 0** och **0,5** inte vara relevanta och objekt med förutsägelseresultat mellan **0,5** och **1** anses vara relevanta. Prognosresultatet finns i ett dokumentmetadatafält. Du kan använda ett prognosfilter för att visa objekten i en granskningsuppsättning som faller inom ett visst prognosområde.

## <a name="recall"></a>Återkalla

Återkallelsemåttet mäter andelen av objekt som modellen förutsagt var relevant bland objekt som faktiskt är relevanta. Det innebär att elementen i kontrolluppsättningen som den prognosterade modellen var relevant även har märkts som relevanta av granskaren. Resultatintervallet för det här värdet är **från 0** till **1.** En poäng som ligger **närmare 1** anger att modellen identifierar en större del relevanta objekt. Återkallelsemåttet visas på modellinstrumentpanelen och på den utfällbordssidan för varje utbildningsrunda.

## <a name="review-set"></a>Granskningsuppsättning

En granskningsuppsättning utgör omfattningen av en prediktiv kodningsmodell. När du skapar en ny modell för granskningsuppsättningen markeras objekt för kontrolluppsättningen och utbildningsuppsättningarna i granskningsuppsättningen. När modellen tilldelar resultat tilldelas de resultat som objekten i granskningen. Du måste lägga till alla objekt i granskningsuppsättningen innan du skapar en prognoskodningsmodell. Om du lägger till objekt efter att du har skapat en modell tilldelas de objekten inte något prognosresultat.

## <a name="richness"></a>Richness

Måttet för relevansmått mäter procentandelen granskningsobjekt som modellen förutsäger som relevanta. Resultatintervallet för det här värdet är **från 0** till **1.** Måttet för användbarhet visas på instrumentpanelen för modellen.

## <a name="sampled-items"></a>Exempelobjekt

Termen *exempelobjekt* är en referens till slumpmässiga urval av objekt i en granskningsuppsättning (som innehåller text) som markeras och associeras med kontrolluppsättningen när du skapar en prediktiv kodningsmodell. Ett slumpmässigt urval av objekt väljs också för varje utbildningsrunda. Objekt som har valts för kontrolluppsättningen för en modell ingår aldrig i en utbildningsuppsättning för samma modell. Det omvända är också sant: utbildningsuppsättningsobjekt ingår aldrig i kontrolluppsättningen.

## <a name="training-set"></a>Utbildningsuppsättning

Modellen väljer objekt från granskningsuppsättningen slumpmässigt och lägger till dem i en utbildningsuppsättning. Under en utbildningsrunda visas objekt från utbildningsuppsättningen (förutom objekt från kontrolluppsättningen) så att du kan märka varje objekt som antingen "relevant" eller "inte relevant". Den här märknings- eller utbildningsprocessen hjälper modellen att förutse vilka objekt i granskningen som är relevanta eller inte relevanta. Varje gång du genomför en utbildningsrunda väljer modellen fler objekt från granskningen och lägger till dem i utbildningsuppsättningen för den utbildningsomgången. Objekt från kontrolluppsättningen markeras aldrig för en utbildningsuppsättning.
