---
title: Förstå utvärdering i relevans i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Få en översikt över utvärderingssteget och dess roll för att avgöra hur omfattande problemen är under relevansutbildning i Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161785"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Utvärdering i modulen Relevans i Advanced eDiscovery
  
Advanced eDiscovery här alternativet möjliggör tidig bedömning, till exempel för definierade problem och data som importerats för ett ärende. Advanced eDiscovery att låta experten fatta beslut om en metod som används och tillämpa dessa beslut på dokumentgranskningsprojektet.
  
## <a name="understanding-assessment"></a>Förstå bedömning

I Utvärdering granskar experten en slumpuppsättning på minst 500 filer, som används för att fastställa huruvida ärendena är tillräckligt omfattande och för att skapa statistik som speglar utbildningsresultaten. Bedömningen lyckas när tillräckligt många relevanta filer påträffas för att nå en statistisk nivå som hjälper Advanced eDiscovery-relevans att tillhandahålla korrekt statistik och för att effektivt fastställa stabiliseringspunkten i utbildningsprocessen. 
  
Ju fler relevanta filer i utvärderingsuppsättningen, desto mer exakt är statistiken och effektiviteten i stabilitetsalgoritmen. Antalet relevanta filer i utvärderingsfilerna beror på hur omfattande problemet är. Relevans är den uppskattade procentandelen relevanta filer i den uppsättning som är relevant för ett problem. Problem med högre kvalitet kommer att nå ett högre antal relevanta filer snabbare än problem med lägre kvalitet. Problem med extremt låg richness (till exempel 2 % eller mindre) kräver en mycket stor utvärderingsuppsättning för att nå ett stort antal relevanta filer.
  
Statistiken, som visas på flikarna Spåra och Bestäm under utbildning och efter Batchberäkning, innehåller uppskattningar av återkallelsen för olika granskningsuppsättningar. I statistik ger uppskattningar som baseras på en urvalsuppsättning (i det här fallet utvärderingsfilerna) en marginal för felet och konfidensnivån för felmarginalen. Uppskattad återkallelse av 80 % kan till exempel ha en felmarginal på plus eller minus 5 % med en konfidensnivå på 95 %. Det innebär att den uppskattade återkallelsen faktiskt är 75 –85 % och den här uppskattningen har 95 % konfidens. Ju större bedömningsuppsättningen är, desto mindre blir felmarginalen och statistiken blir mer exakt. 
  
När experten granskar en första bedömningsuppsättning på 500 filer kan Relevans fastställa den aktuella marginalen för fel i återkallelsevärdena. Relevansen rekommenderar också en standardmarginal för fel att nå för att optimera utvärderingsuppsättningen. Här är några exempel:
  
- Om utvärderingsuppsättningen redan ger en felmarginal på plus eller minus 10 % rekommenderar relevans att du går vidare till utbildningen (ingen ytterligare utvärderingsgranskning krävs). 

- Om utvärderingsuppsättningen ger en felmarginal på plus eller minus 13 % kan relevansen rekommendera granskning av en annan uppsättning utvärderingsfiler för att nå en mindre marginal. 

- Om relevansen är extremt låg kan relevansen rekommendera att du stoppar bedömningen även om felmarginalen är stor (vilket gör det opraktiskt att använda statistik), eftersom den utvärderingsuppsättning som behövs för att nå en användbar marginal för fel är för stor.

Varje problem har sin egen användbarhet, den aktuella felmarginalen och det uppskattade antalet ytterligare utvärderingsfiler. Nästa utvärderingsuppsättning skapas enligt det maximala antalet filer (upp till 1 000 i en enda uppsättning).
  
Du kan acceptera relevansrekommendationerna eller justera den aktuella felmarginalen enligt dina behov. Standardmarginalen för aktuellt fel bestäms för återkallelsen som är lika med eller över 75 %.
  
> [!NOTE]
> Du kan kringgå utvärderingsstegen genom att avmarkera kryssrutan Utvärdering per problem  och sedan för "alla problem" på fliken Relevansspår i den utökade vyn för ett problem. **\>** Därför kommer det inte att finnas någon statistik för det här problemet. Det går **bara** att avmarkera kryssrutan Utvärdering innan utvärderingen utförs. Om det finns flera ärenden i ett ärende kringgås bedömningen endast om kryssrutan avmarkeras för varje ärende.
