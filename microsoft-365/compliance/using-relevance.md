---
title: Använd modulen Relevans för att analysera data i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur relevansmodulen analyserar data som bevis tillsammans med en beskrivning av arbetsflödet för relevans och utbildning i Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161627"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Använd modulen Relevans för att analysera data i Advanced eDiscovery

I Advanced eDiscovery i relevansmodulen ingår relevansutbildning och granskning av filer som är relaterade till ett ärende. Om du vill använda arbetsflödet Relevans går du till Hantera granskningsuppsättningen i en granskningsuppsättning och klickar på Visa relevans. Det finns några steg du måste slutföra innan du kan starta arbetsflödet:

- Process: varje inläsningsuppsättning som läggs till i granskningsuppsättningen visas som en "behållare" här. Du måste bearbeta de här dokumenten innan du kan lägga till dem i relevansmodulen. Här kan du också markera dem som starttagg eller förtaggade för ett specifikt problem.

- Lägg till i Relevans: Under Relevans läses in kan du lägga till dokument som har bearbetats i \> relevans för att göra dem tillgängliga för utbildning.

Arbetsflödet Relevans visas och beskrivs på följande sätt:
  
![Arbetsflöde för relevans](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Utvärderings- och spårningscykler:**
    
  - **Utvärdering**: Möjliggör tidig utvärdering baserat på ett slumpmässigt urval av filer och använder den här utvärderingen för att tillämpa beslut för att fastställa prestanda för prediktiv kodningsprocess. 
    
  - **Spåra**: Beräkna och visa interimresultaten från utvärderingen medan du övervakar processens statistiska giltighet. 
    
- **Cykler för utbildning och spårning**
    
  - **Tagg:** Advanced eDiscovery relevanskriterier som är specifika för varje problem baserat på expertens iterativa granskning och taggning av enskilda filer.
    
  - **Spåra**: Beräkna och visa interimresultat av relevansutbildningen samtidigt som du övervakar processens statistiska giltighet. 
    
- **Batchberäkning:** De ackumulerade och inlärda relevansvillkoren tillämpas på hela filsamlingen och ett relevansresultat genereras för varje fil.
    
- **Bestäm**: Resultatet av analysen som tillämpas på hela ärendet visas efter Batchberäkning, och data som används för att fatta beslut om dokumentgranskning visas.
    
- **Test:** Resultaten kan testas för att verifiera giltigheten och effektiviteten i Advanced eDiscovery bearbetningen.

- **Sökning:** När relevansarbetsflödet har slutförts kan du använda utdata, till exempel läs percentilen av ett dokument för problemet, när du kör en fråga i din granskningsuppsättning.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Riktlinjer för relevansutbildning och granskning

Här följer en översikt över riktlinjer för relevansutbildning och granskning:
  
- **Fel och inkonsekvenser:** Om taggningsfel görs under utbildningen återgår du till tidigare filexempel för att korrigera dem. Om det finns för många fel att åtgärda, eller om ärendet har ett nytt perspektiv, bör relevansvillkoren definieras om av administratören och relevansutbildningen startas om.
    
- **Märkning och utbildning:** 
    
  - Filer ska taggas baserat på endast innehåll. Ta inte hänsyn till metadata, t.ex. dokument, datum eller sökväg. 
    
  - Överväg inte datumintervallsdikationer i texten när du taggar filer.
    
  - Överväg inte att bädda in grafiska bilder när du taggar filer.
     
  - Ignorera text som har relevans tas bort i det filinnehåll som visas i textvyn i Relevans. Om värdena för Ignorera text har definierats efter att Relevansutbildning redan påbörjats, tillämpas den nya ignorerade texten på exempelfiler som skapades från den plats där den definierades. Funktionen Ignorera text bör användas försiktig, eftersom dess användning kan försämra prestandan för filanalys
    
  - Använd alternativet **Hoppa över taggningen** endast när det behövs. Advanced eDiscovery utbildas inte baserat på överhoppade filer. Om det är svårt att avgöra om en fil är relevant är det bättre att tagga som Relevant (R) eller Inte relevant (NR) när det är möjligt i stället för att välja **Hoppa över**. När Advanced eDiscovery utvärderar utbildning kan du sedan se hur bra de här typerna av filer har bearbetats.
    
  - Även filer med mycket lite extraherad text ska om möjligt taggas i utbildning som R/NR i stället för som "Hoppa över". 
    
  - Taggningen kan påverka klassificeraren så länge filen är läsbar och kan märkas som R/NR.
    
  - Med filsekvensnumret i listan Exempelfiler  på fliken Tagg kan användaren återgå till den ursprungliga visade ordningen för filerna. 
    
  - Du kan gå tillbaka till ett urval och ändra taggningen för utvärderings- och utbildningsuppsättningsfilerna. Ändringarna används när nästa exempel skapas.
    
  - Genomsökta Excel-filer i PDF-format bör behandlas på samma sätt som ursprungliga filer Excel filer när du taggar filer.
    
  - Om du är osäker på relevansmarkeringar för en fil bör du kontakta en expert. Felaktiga taggningar under relevansutbildningen kan leda till förlorad tid senare i processen och kan också påverka kvaliteten på det övergripande resultatet negativt.
    
  - Nyckelord som har definierats i nyckelordslistor visas i färger som hjälper användaren att identifiera relevanta filer medan de taggas.
    
- **Batchberäkning:** Filer som har taggats som R/NR av experten får poäng på antingen 0 eller 100. Det här gäller taggning som gjorts före batchberäkning. Om experten bytte problemet till Inaktiv efter Batchberäkning och fortsätter att tagga problemet blir de nyligen taggade betygen inte 100/0 utan snarare det ursprungliga resultatet.
    
- **Problem- och samplingsläge:** Ärenden är vanligtvis avstängt när arbete med dem har slutförts (Relevansutbildning har avslutats och Batchberäkning utfördes), när ärendena avbryts eller när en annan användare arbetar med ärendena.
    
## <a name="steps-in-relevance-training"></a>Steg i Relevansutbildning

På fliken **\> Relevansspår** finns Advanced eDiscovery rekommendationer om hur du går vidare i bearbetningen, med följande steg. Konsekvenserna beskrivs nedan när var och en av följande steg rekommenderas i relevansutbildningsprocessen. 
  
- Taggning/fortsätt-taggning: Filgranskning och relevanstaggar som utförs av en expert för varje fil och problem i ett urval.
    
  - Implication: Ett befintligt urval måste märkas.
    
- Utvärdering/Fortsätt bedömning: Möjliggör tidig validering av relevans för ärende och en preliminär vy av relevansen för den importerade filpopulationen för det aktuella ärendet.
    
  - Implication: More assessment is required or recommended.
    
- Utbildning/Fortsätt utbildning: Processen under vilken Advanced eDiscovery lär sig av experten som taggar filproven och får möjlighet att identifiera relevanskriterier som är relevanta för varje problem inom ramen för varje ärende.
    
  - Implication: The issue needs more training; Nästa exempel bör skapas och taggas. 
    
- Batchberäkning: Relevansprocessen där Advanced eDiscovery kunskap från utbildningsfasen tillämpas på hela filpopulationen. Alla filer i den relevanta filgruppen bedöms som relevanta och tilldelas ett relevansresultat.
    
  - Implication: The issue has enkelt, and Batch calculation can be performed.
    
- Uppläsning: Relevans anger när en expert granskar och taggar ett urval av filer som valts ut vid ytterligare filinläsning under ett scenario med rullnings läses in.
    
  - Implication: A new load has been added, and Catch-up is required to continue working.
    
- Tagga inkonsekvenser: Processen identifierar, via en Advanced eDiscovery-algoritm, inkonsekvenser i filtaggsprocessen som kan påverka analysen negativt.
    
  - Implication: I nästa exempel visas filer som har taggats i tidigare exempel, och deras taggning måste göras om.
    
- Uppdatera klassificerare: Gör att användaren kan använda taggning eller lägga till ändringar.
    
  - Implication: Tagga och lägga till ändringar kan användas utan att du behöver köra ett annat exempel på Relevans manuellt.
    
- Väntad: Relevansutbildningsprocessen har slutförts.
    
  - Implication: No Relevance training is required at this point.
    
Även om Advanced eDiscovery hjälper dig genom processen, med rekommenderade steg i Nästa i olika steg, kan du också navigera mellan flikar och sidor och göra val för att ta itu med situationer som kan vara relevanta för ditt ärende, problem eller dokumentgranskningsprocessen. 
  
Det går att godkänna eller åsidosätta bearbetningsalternativen Advanced eDiscovery nästa steg. Om du vill utföra ett annat steg än  det rekommenderade nästa steget klickar du på nästa  steg som visas i den expanderade problemvisningen i dialogrutan, klickar på knappen Ändra bredvid nästa steg och väljer ett annat alternativ för Nästa steg. 
  
> [!NOTE]
> Vissa alternativ kan vara inaktiverade efter upplåsning eftersom de inte stöds för användning vid den tidpunkten. 
  
## <a name="more-information"></a>Mer information

[Förstå utvärdering i relevans](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Märkning och utvärdering](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagga och relevansutbildning](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Spåra relevansanalys](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Bestämma resultat](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testa relevansanalys](test-relevance-analysis-in-advanced-ediscovery.md)

[Fråga data i en granskningsuppsättning](review-set-search.md)
