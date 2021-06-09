---
title: Skapa en prediktiv kodningsmodell i Advanced eDiscovery
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
description: Lär dig hur du skapar en prediktiv kodningsmodell i Advanced eDiscovery. Det här är det första steget när du använder funktionerna för maskininlärning i Advanced eDiscovery för att hjälpa dig att identifiera relevant och icke-relevant innehåll i en granskningsuppsättning.
ms.openlocfilehash: 7724062848d8d757fbfd3a7870853d6f2c409d84
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822638"
---
# <a name="create-a-predictive-coding-model-preview"></a>Skapa en prediktiv kodningsmodell (förhandsversion)

Det första steget i att använda maskininlärningsfunktionerna för prediktiv kodning i Advanced eDiscovery är att skapa en prediktiv kodningsmodell. När du har skapat en modell kan du utbilda den att identifiera relevant och icke-relevant innehåll i en granskningsuppsättning.

Information om hur du granskar arbetsflödet för förutsägelsekodning finns [i Lär dig mer om prediktiv kodning i Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Innan du skapar en modell

- Det måste finnas minst 2 000 objekt i en granskningsuppsättning för att skapa en prediktiv kodningsmodell.

- Se till att spara alla samlingar i granskningsuppsättningen innan du skapar en modell. Objekt som läggs till i en granskningsuppsättning efter att modellen har skapats bearbetas inte och tilldelas ett prognosresultat som genereras av modellen.

- Objekt i granskningsuppsättningen som inte innehåller text bearbetas inte av modellen eller tilldelas ett prognosresultat. Objekt med text inkluderas i kontrolluppsättningen eller i en utbildningsuppsättning.

## <a name="create-a-model"></a>Skapa en modell

1. I Microsoft 365, öppna ett ärende Advanced eDiscovery välj sedan fliken **Granska uppsättningar.**

2. Öppna en granskningsuppsättning och klicka sedan **på Analys**  >  **Hantera prediktiv kodning (förhandsgranskning).**

   ![Klicka på listrutan Analysera i granskningsuppsättningen för att gå till sidan Predictive coding](..\media\ManagePredictiveCoding.png)

3. Klicka på **Ny modell på sidan Prediktiv kodningsmodeller (förhandsversion).** 

4. Ange ett namn för modellen och en valfri beskrivning på den utfällbara sidan.

5. Du kan också konfigurera avancerade inställningar  (genom att klicka på Avancerade alternativ på den utfällbara sidan) som relaterar till konfidensnivån och felmarginalen. De här inställningarna påverkar antalet objekt som ingår i kontrolluppsättningen. *Kontrolluppsättningen* används under utbildningsprocessen för att utvärdera de förutsägelseresultat som modellen tilldelar till objekt med den etikett som du utför under utbildning avrundas. Om din organisation har riktlinjer för förtroendenivå och felmarginal för dokumentgranskning anger du dem i lämpliga rutor. I annat fall använder du standardinställningarna.

6. Klicka **på** Spara för att skapa modellen.

   Det tar några minuter innan systemet har förberett modellen. När den är klar kan du utföra den första utbildningsomgången.

## <a name="what-happens-after-you-create-a-model"></a>Vad händer efter att du har skapat en modell

När du har skapat en modell uppstår följande saker i bakgrunden när modellen skapas och förberedas:

- Systemet beräknar antalet objekt för kontrolluppsättningen. Den här storleken baseras på antalet objekt i granskningsuppsättningen och inställningarna för konfidensnivån och felmarginalen. Objekten i kontrolluppsättningen markeras slumpmässigt och anges som kontrolluppsättningsobjekt. Systemet innehåller 10 objekt från kontrolluppsättningen i den första utbildningsomgången.

- Systemet väljer slumpmässigt 40 objekt från granskningsuppsättningen som ska ingå i utbildningsuppsättningen för den första utbildningsomgången. Därför innehåller den första utbildningsomgången 50 objekt för märkning: 40 objekt från utbildningsuppsättningen och 10 objekt från kontrolluppsättningen.

## <a name="next-steps"></a>Nästa steg

När du har skapat en modell för en granskningsuppsättning genomför nästa steg utbildning avrundar för att "lära ut" modellen för att identifiera innehåll som är relevant för din undersökning. Mer information finns i Utbilda [en prediktiv kodningsmodell](predictive-coding-train-model.md).
