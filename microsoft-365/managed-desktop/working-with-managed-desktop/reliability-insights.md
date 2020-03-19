---
title: Tillförlitlighet insikter
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812268"
---
# <a name="reliability-insights"></a>Tillförlitlighet insikter

Den här vyn ger dig en hälsosammanfattning av dina hanterade enheter. Om du vill visa tillförlitlighetsdata väljer du fliken **Tillförlitlighet.**


![Tillförlitlighetsruta: tillförlitlighet mellan enheter i övre vänstra, tillförlitlighet över tidsdiagram i övre högra, översta problemtabellen längst ned. Hjälp- och återkopplingsknappar i nedre högra delen.](../../media/insights_reliability.png)

**Avsnittet Tillförlitlighet mellan enheter** ger en snabb hälsosammanfattning av distributionen under de senaste 14 dagarna genom att rapportera hur många procent av enheter som anses vara "felfria" och den genomsnittliga tiden som observerats sedan det senaste rapporterade felet. 

 
**Diagrammet Tillförlitlighet över tid** till höger visar antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tid.

Avsnittet **Översta problem** innehåller specifika problem som påverkar minst 5 % av dina hanterade enheter. Rapporterade uppgifter inkluderar:

- Typ av problem
    - Programmet kraschar, där en app slutar fungera eller oväntat slutar
    - Programmet låser sig, där ett program slutar svara på indata
    - Kritiska fel, som uppstår när windows har stött på ett problem som det inte kan återställa från
- Antalet enheter som påverkas av samma problem
- Procentandelen hanterade enheter som antalet representerar
- Det totala antalet händelser för det specifika problemet
- Programvarukomponenten som verkar vara källan till problemet
- Kategorin för det upptäckta problemet:
    - Webbläsare (Edge, Chrome, IE)
    - Okänd (komponenter som inte kommer från Microsoft)
    - Drivrutin (ljud, grafik eller andra drivrutiner)
    - Produktivitet (Slack, G-Suites, Microsoft Office och dess tillägg eller tillägg, Teams)
    - Medieappar (bild-, musik- eller videoappar
    - Säkerhet (Windows-säkerhetskomponenter)
- Den aktuella statusen när Microsoft Managed Desktop Operations undersöker och åtgärdar problemet

