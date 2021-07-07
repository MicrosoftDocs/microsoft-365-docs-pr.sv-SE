---
title: Minnes regressionsanalys
description: Här finns information om hur du härar minnes regression
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323109"
---
# <a name="memory-regression-analysis"></a>Minnes regressionsanalys

Testbas hjälper dig att tydligare märka en betydande minnesanvändning ökar i test de virtuella maskinerna som kör dina appar. Prestandamätvärden, t.ex. minnesanvändning, kan samtidigt visa att programmet är allmänt hållet och vi tror att det här tillägget gör att apparna fungerar optimalt.

Läs vidare för mer information eller titta på den här videon för en snabb genomgång av de senaste förbättringarna. 

Mer information om testbas för M365-möjligheten att bidra med regressionsanalys finns i Regressionsresultat baserat på processtillförlitlighet.

<b>Titta närmare på minnes regressioner</b>

Instrumentpanelen Testbas för M365 visar vilket minne som används av programmet i en ny förhandsuppdatering av Windows och jämför det med minnet som används av den senaste Windows uppdateringen. 

Med den här månadens förbättringar visas nu minnes regressionsanalys i dina favoritprocesser. Program kan innehålla flera processer och du kan manuellt välja dina favoritprocesser på fliken Tillförlitlighet. Vår tjänst identifierar sedan minnes regressioner i dessa favoritade processer samtidigt som testet jämförs körs över Windows uppdaterings versioner. Om en regression identifieras är information om regressionen lätt tillgänglig.

Nu ska vi titta på den här funktionen i detalj och diskutera hur du kan felsöka minnes regressioner med hjälp Windows Analysera prestanda.

Felsignalen som orsakas av minnes regression visas på instrumentpanelen Testbas för M365 på sidan Testresultat under Minnesutnyttjande:

![Resultat av minnesanvändning](Media/01_memory-utilization-results.png)


Fel i programmet på grund av högre minnesanvändning visas också som ```Fail``` på sidan Testsammanfattning:

![Testsammanfattningsresultat](Media/02_test-summary.png)

Genom att tillhandahålla dessa fel är vårt mål att tydligt flagga potentiella problem som kan störa och påverka slutanvändarupplevelsen för programmet. 

Du kan sedan ladda ned loggfilerna och använda Windows Performance Analyzer, eller det verktyg du föredrar, för att undersöka ytterligare. Du kan också samarbeta med M365-testgruppen för att åtgärda problemet och undvika problem som påverkar slutanvändarna.

Minnessignaler fångas på fliken Minnesutnyttjande i tjänsten Testbas för M365 för alla testkörningar. Exemplet nedan visar en testkörning med det onboarded-programmet "Test av minnesstress" mot säkerhetsuppdateringen i augusti 2020. (Det här programmet har skrivits av vårt team för att illustrera minnes regressioner.)

![Resultat av minnes regression](Media/03_memory-regression%20comparison.png)

I det här exemplet förbrukade favoritprocessen "USLTestMemoryStress.exe"-processen i genomsnitt cirka 100 MB vid förhandsuppdateringen av augusti jämfört med uppdateringen för juli, och därför identifieras en regression av testbasen för M365. 

De andra processerna – som visas här som "USLTestMemoryStress_Aux1.exe" och "USLTestMemoryStress_Aux2.exe" – hör också till samma program, men förbrukade ungefär samma mängd minne för de två versionerna så att de "passerat" och anses vara felfria.

Regressionen i huvudprocessen bestämdes vara "statistiskt signifikant" så att tjänsten kommunicerades och markerade den här skillnaden för användaren. Om jämförelsen inte är statistiskt signifikant markeras den inte. Minnesutnyttjande kan vara bullrigt, så vi använder statistiska modeller för att skilja på versioner och versioner samt meningsfulla skillnader från inkonsekvenser. 

En jämförelse kan sällan flaggas när det inte finns någon verklig skillnad (falsk positiv identifiering), men det är en nödvändig kompromiss för att förbättra sannolikheten för att korrekt identifiera regressioner (eller sant positiva identifieringar).)

Nästa steg är att förstå vad som orsakade minnes regressionen. Du kan ladda ned ZIP-filerna för båda körningarna med alternativet Ladda ned loggfiler, som du ser nedan. 

Zip-filerna innehåller resultatet av testkörningen, inklusive skriptresultat och minnes- och CPU-prestandadata som ingår i ETL-filen.

![Minnes regressionstestfiler](Media/04_memory-regression-test-files.png)

Du kan ladda ned och packa upp loggarna för de två testerna, leta upp ETL-filen i varje mapp och byta namn på dem som target.etl (för testkörningen kör på förhandsuppdateringen) och baseline.etl (för testkörningen som släpptes senast) för att förenkla utforskning och navigering.
 
## <a name="next-steps"></a>Nästa steg

Gå vidare till nästa artikel för att komma igång med att förstå intelligent regressionsanalys av processorkraften.
> [!div class="nextstepaction"]
> [Nästa steg](cpu.md)

<!---
Add button for next page
-->
