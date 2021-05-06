---
title: Beslut baserat på resultaten i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Läs om hur du hittar data Advanced eDiscovery fliken Bestämmer i Advanced eDiscovery som kan hjälpa dig att avgöra rätt storlek på granskningsuppsättningen med ärendefiler.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161773"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Beslut baserade på relevansresultat i Advanced eDiscovery
  
I modulen Relevans i Advanced eDiscovery på fliken Bestämmer finns mer information för att visa och använda statistik för beslutssupport för att fastställa storleken på granskningsuppsättningen av ärendefiler.
  
## <a name="using-the-decide-tab"></a>Använda fliken Bestämmer

![Relevans Bestäm](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Den här fliken innehåller följande komponenter:
  
- **Problem:** Härifrån kan du välja intressefrågan i listan.

- **Review-recall ratio**: Jämförelser av Advanced eDiscovery granska i enlighet med relevansresultat. Brytpunkten i diagrammet representerar procentandelen filer att granska, mappade till ett relevansresultat. Det här används i fasen Relevanstest och som ett exporttröskelvärde för testning. Som standard är saldot mellan Återkallelse och Precision optimalt för antalet filer som ska granskas. Den faktiska brytpunkten ska fastställas av användaren beroende på mål och kostnads kompromiss (%review) och risk (%recall). Med skjutreglaget kan du justera brytpunkten och se effekten på diagrammet och parametrarna, när du justerar hur många procent av relevanta filer som ska hämtas och innan du verifierar ett beslut.

- **Parametrar:** Granska, Återkalla, Nästa relevanta parametrar och Parametrar för totalkostnad är ackumulerad beräknad statistik som hör till granskningsuppsättningen i relation till samlingen för hela ärendet. Definitioner för dessa parametrar är följande:

  - **Granska:** Procentandel av filer som ska granskas baserat på den här brytningen.

  - **Återkalla:** Procentandel av relevanta filer i granskningsuppsättningen.

  - **Nästa relevanta**: Kostnad för granskning och identifiera en annan relevant fil som inte finns med i granskningsuppsättningen.

  - **Total kostnad:** Kostnad för att granska denna procent av ärendefilerna. Kostnadsparameterinställningar kan anges av ärendehanteraren.

  - **Fördelning efter relevansresultat:** Filer i den mörkgrå visningen till vänster är under brytresultatet. I en verktygstips visas Relevansresultat och den relaterade procentandelen filer i granskningsfilen som angetts i förhållande till det totala antalet filer.

I det utökade **informationsfönstret** visas mer information. Filer på samlingsfigurer omfattar inte tomma eller nebulous-filer. Familjefiler representerar filer som inte lästs in i Relevans, men fortfarande räknas som en del av familjen.
