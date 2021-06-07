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
# <a name="reliability-insights"></a>Tillförlitlighetsinsikter

Den här vyn ger dig en hälsosammanfattning av dina hanterade enheter. Om du vill visa tillförlitlighetsdata väljer du **fliken Tillförlitlighet.**


![Tillförlitlighetsfönster: Tillförlitlighet på enheter i det övre vänstra hörnet, tillförlitlighet över tid, diagram över övre högra hörnet, den översta problemtabellen längst ned. Knapparna Hjälp och Feedback längst ned till höger.](../../media/insights_reliability.png)

I **avsnittet Tillförlitlighet** på enheter får du en snabb sammanfattning av distributionen under de senaste 14 dagarna genom att rapportera procentandel enheter som anses vara "felfria" och den genomsnittliga tiden som observerats sedan det senast rapporterade felet. 

 
I **diagrammet Tillförlitlighet** över tid på höger sida visas antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tid.

Avsnittet **Om de viktigaste** problemen beskriver specifika identifierade problem som påverkar minst 5 % av dina hanterade enheter. Rapporterad information:

- Typ av problem
    - Programmet kraschar, där en app slutar fungera eller oväntat slutar fungera
    - Programmet hänger sig där ett program slutar svara på indata
    - Kritiska fel som inträffar när Windows har stött på problem kan det inte återställas från
- Antalet enheter som påverkas av samma problem
- Procentandelen hanterade enheter som talet representerar
- Det totala antalet förekomster av ett specifikt problem
- Programvarukomponenten som verkar vara orsaken till problemet
- Kategorin för det identifierade problemet:
    - Webbläsare (Edge, Chrome, IE)
    - Okänd (komponenter som inte kommer från Microsoft)
    - Drivrutin (ljud, grafik eller andra drivrutiner)
    - Produktivitet (slack, G-Microsoft Office, tillägg och tillägg, Teams)
    - Media (bild-, musik- eller videoappar)
    - Säkerhet (Windows säkerhetskomponenter)
- Den aktuella statusen Microsoft Hanterat skrivbord åtgärder undersöker och åtgärdar problemet

