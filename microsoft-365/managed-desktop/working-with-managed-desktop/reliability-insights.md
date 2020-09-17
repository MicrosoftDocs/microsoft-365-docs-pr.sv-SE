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
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950348"
---
# <a name="reliability-insights"></a>Tillförlitlighetsinsikter

I den här vyn får du en översikt över dina hanterade enheter. Om du vill visa pålitlighets data väljer du fliken **pålitlighet** .


![Fönstret tillförlitlighet: tillförlitlighet mellan enheter uppe till vänster, högre tillförlitlighet än tids diagram längst upp till höger, tabellen vanligaste problem nedtill. Knapparna hjälp och feedback längst ned till höger.](../../media/insights_reliability.png)

Avsnittet **tillförlitlighet i flera enheter** erbjuder en översikt över de senaste 14 dagarna genom rapportering om procent andelen av enheter som anses vara "felfri" och genomsnittlig tid som observerats sedan det senaste rapporterade felet. 

 
Diagrammets **tillförlitlighet över tid** till höger rapporterar antalet enheter med kritiska fel och det totala antalet observerade kritiska fel över tiden.

Avsnittet **TOPY** retails visar specifika upptäckta problem som påverkar minst 5% av dina hanterade enheter. Rapporterade uppgifter inkluderar:

- Typ av problem
    - Program kraschar, där ett program slutar fungera eller oväntat stoppas
    - Programmet hänger sig, där ett program slutar svara för inmatning
    - Kritiska fel, som uppstår när ett problem har uppstått i Windows
- Antalet enheter som påverkas av samma problem
- Procent andelen hanterade enheter som numret representerar
- Totalt antal förekomster av det specifika problemet
- Program varu komponenten som verkar vara orsaken till problemet
- Kategorin för det upptäckta problemet:
    - Webbläsare (Edge, Chrome, IE)
    - Okända (icke-Microsoft-komponenter)
    - Driv rutin (ljud, grafik eller andra driv rutiner)
    - Produktivitet (slack, G-sviter, Microsoft Office och tillägg och tillägg, Team)
    - Media (bild-, musik-eller videoappar
    - Säkerhet (Windows säkerhets komponenter)
- Den aktuella statusen som Microsoft Managed Desktop-operationer undersöker och åtgärdar problemet

