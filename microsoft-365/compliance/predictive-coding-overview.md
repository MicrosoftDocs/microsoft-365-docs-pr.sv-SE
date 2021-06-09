---
title: Prediktiv kodningsmodul för Advanced eDiscovery (förhandsversion)
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
description: Den nya prediktiv kodningsmodulen i Advanced eDiscovery använder maskininlärning för att analysera objekt i en granskningsuppsättning för att förutsäga vilka objekt som är relevanta för ditt ärende eller din undersökning.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822048"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Lär dig mer om prediktiv kodning i Advanced eDiscovery (förhandsversion)

I prediktiv kodningsmodulen i Advanced eDiscovery intelligenta maskininlärningsfunktioner som hjälper dig att minska mängden innehåll som ska granskas. Med förutsägande kodning kan du minska och anpassa stora mängder ärendeinnehåll till en relevant uppsättning objekt som du kan prioritera för granskning. Detta sker genom att skapa och träna egna prediktiv kodningsmodeller som hjälper dig att prioritera granskningen av de mest relevanta objekten i en granskningsuppsättning.

Prediktiv kodningsmodulen är utformad för att effektivisera komplexiteten hos hantering av en modell inom en granskningsuppsättning och ge en iterativ metod för att lära ut din modell så att du kan komma igång snabbare med funktionerna för maskininlärning i Advanced eDiscovery. För att komma igång kan du skapa en modell, etikettera så få som 50 objekt som relevanta eller inte relevanta. Den här utbildningen används för att använda förutsägelseresultat för alla objekt i granskningsuppsättningen. På så sätt kan du filtrera objekt baserat på förutsägelseresultatet, så att du först kan granska de mest relevanta (eller icke-relevanta) elementen. Om du vill utbilda modeller med högre precision och återkallelsefrekvenser kan du fortsätta märka objekt i efterföljande utbildning avrundar tills modellen har en högre precision.  

## <a name="the-predictive-coding-workflow"></a>Arbetsflödet för förutsägelsekodning

Här är en översikt och beskrivning av varje steg i ett prediktivt kodningsarbetsflöde. En mer detaljerad beskrivning av begrepp och terminologi för prediktiv kodningsprocess finns i [Referens för prediktiv kodning.](predictive-coding-reference.md)

![Arbetsflöde för förutsägelsekodning](..\media\PredictiveCodingWorkflow.png)

1. **Skapa en ny prediktiv kodningsmodell i granskningsuppsättningen**. Det första steget är att skapa en ny prediktiv kodningsmodell i granskningsuppsättningen. Du måste ha minst 2 000 objekt i granskningsuppsättningen för att skapa en modell. När du har skapat en modell bestämmer systemet hur många objekt som ska användas som *kontrolluppsättning*. Kontrolluppsättningen används under utbildningsprocessen för att utvärdera de förutsägelseresultat som modellen tilldelar till objekt med den etikett som du utför under utbildning avrundas. Storleken på kontrolluppsättningen baseras på antalet objekt i granskningsuppsättningen och konfidensnivån och marginalen för felvärden som anges när modellen skapas. Objekten i kontrollen ändras aldrig och kan inte identifieras av användarna.

   Mer information finns i Skapa [en prediktiv kodningsmodell](predictive-coding-create-model.md).

2. **Slutför den första utbildningsomgången genom att ange att objekten är relevanta eller inte relevanta.** Nästa steg är att utbilda modellen genom att starta den första utbildningsomgången. När du startar en utbildningsrunda väljer modellen slumpmässigt ytterligare objekt från granskningsuppsättningen, som kallas *för utbildningsuppsättningen*. De här objekten (både från kontrolluppsättningen och utbildningsuppsättningen) visas för dig så att du kan märka dem som antingen "relevanta" eller "inte relevanta". Relevansen baseras på innehållet i objektet och inte på någon metadata för dokumentet. När du har slutfört etikettprocessen i utbildningsprocessen lär sig modellen baserat på hur du har etiketterat objekten i utbildningsuppsättningen. Baserat på den här utbildningen bearbetar modellen objekten i granskningsuppsättningen och tillämpar ett förutsägelseresultat på var och en.

   Mer information finns i Utbilda [en prediktiv kodningsmodell](predictive-coding-train-model.md).

3. **Använda filtret för förutsägelseresultat för objekt i granskningsuppsättningen**. När det föregående steget i utbildningen är avslutat är nästa steg att använda filtret för förutsägelseresultat för objekten i granskningen för att visa att de objekt som modellen har fastställt är "mest relevanta" (du kan också använda ett prognosfilter för att visa objekt som är "inte relevanta"). När du använder filtret för förutsägelse anger du ett område med förutsägelseresultat som ska filtreras. Området med förutsägelseresultat ligger mellan **0** och **1,** **där 0** är "inte relevant" och **1** är relevanta. I allmänhet anses element med förutsägelseresultat mellan **0** och **0,5** vara "inte relevanta" och objekt med förutsägelseresultat mellan **0,5** och **1** anses vara relevanta.

   Mer information finns i Använda [ett prognosfilter för en granskningsuppsättning](predictive-coding-apply-prediction-filter.md).

4. **Utför fler utbildning avrundar tills modellens uppgångar har avrundats**. Du kan utföra ytterligare avrundar av utbildning om du vill skapa en modell med högre noggrannhet i förutsägelse och högre återkallelsefrekvenser. *Med* återkallelsehastigheten mäter du andelen av objekt som modellen förutsäger var relevanta bland objekt som faktiskt är relevanta (de objekt som du markerade som relevanta under utbildningen). Resultatintervallet för återkallelsefrekvens **från 0** till **1**. En poäng som ligger **närmare 1** anger att modellen identifierar mer relevanta objekt. I en ny utbildningsrunda kan du märka ytterligare objekt i en ny utbildningsuppsättning. När du har slutfört den utbildningsomgången uppdateras modellen baserat på ny utbildning från din senaste omgång med etiketter för objekt i utbildningsuppsättningen. Modellen bearbetar objekten i granskningsuppsättningen igen och tillämpar nya förutsägelseresultat. Du kan fortsätta att utföra utbildning avrundar tills modellen är kvar. En modell anses inte vara tänkt när fallskärmen efter den senaste utbildningsomgången är mindre än 5 %. *Churn-hastigheten* definieras som procentandel av objekt i en granskningsuppsättning där förutsägelseresultatet ändras mellan utbildning avrundar. Instrumentpanelen för förutsägelsekodning visar information och statistik som hjälper dig att bedöma stabiliteten i en modell.

5. **Använd filtret för "slutliga" förutsägelseresultat för att granska vilka objekt som ska prioriteras**. När du har slutfört alla utbildningsrundar och slutfört modellen är det sista steget att tillämpa det slutliga prognosresultatet på granskningsuppsättningen för att prioritera granskningen av relevanta och icke-relevanta objekt. Det här är samma aktivitet som du utförde i steg 3, men i det här läget är modellen stabil och du planerar inte att köra fler utbildningsrundar.
