---
title: Visa statistik för eDiscovery-sökresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Lär dig hur du använder funktionen sökstatistik för att visa statistik för innehållssökningar och sökningar som är kopplade till ett grundläggande eDiscovery-ärende i Microsoft 365 efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311154"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Visa statistik för eDiscovery-sökresultat

När du har skapat och kört en innehållssökning eller en sökning som är kopplad till ett basfall för e-dataidentifiering kan du visa statistik om de uppskattade sökresultaten. Den innehåller en sammanfattning av sökresultaten (ungefär som sammanfattningen av det uppskattade sökresultatet som visas på den utfällande sidan för sökning), frågestatistik som antalet innehållsplatser med objekt som matchar sökfrågan och identiteten på innehållsplatser som har de mest matchande objekten.
  
Dessutom kan du använda listan nyckelord för att konfigurera en sökning för att returnera statistik för varje nyckelord i en sökfråga. På så sätt kan du jämföra antalet resultat som returneras av varje nyckelord i en fråga.
  
Du kan också ladda ned sökstatistik till en CSV-fil. På så sätt kan du använda filtrerings- och sorteringsfunktionerna i Excel för att jämföra resultat och förbereda rapporter för sökresultaten.
  
## <a name="get-statistics-for-searches"></a>Hämta statistik för sökningar

Så här visar du statistik för en innehållssökning eller en sökning kopplad till ett Bas-eDiscovery-ärende.:
  
1. Klicka Microsoft 365 alla i **kompatibilitetscentret** och gör sedan något av följande:

   - Klicka **på Innehållssökning** och välj sedan en sökning för att visa den utfällade sidan.

     ELLER

   - Klicka **på Bas för e-dataidentifiering,** markera ett ärende och välj sedan en sökning på fliken Sökningar för att visa den  >  utfällande sidan. 

2. Klicka på fliken Sökstatistik på den utfällade sidan av **den markerade** sökningen.
  
   ![Fliken Sökstatistik](../media/SearchStatistics1.png)

Fliken **Sökstatistik** innehåller följande avsnitt som innehåller olika typer av statistik om sökningen.

### <a name="search-content"></a>Söka efter innehåll

I det här avsnittet visas en grafisk sammanfattning av de uppskattade objekt som returneras av sökningen. Här visas antalet objekt som matchar sökvillkoren. Den här informationen ger dig en uppfattning om det uppskattade antalet objekt som returneras av sökningen.

![Sökberäkningar för en sökning](../media/SearchContentReport.png)

- **Uppskattade objekt efter platser:** Det totala antalet uppskattade objekt som returneras av sökningen. Det specifika antalet objekt i postlådor och på webbplatser visas också.

- **Uppskattade platser med träffar:** Det totala antalet innehållsplatser som innehåller objekt som returneras av sökningen. Det specifika antalet postlådor och webbplatser visas också.

- **Datavolym per plats (i MB)**: Total storlek för alla uppskattade objekt som returneras av sökningen. Den specifika storleken på postlådeobjekt och webbplatsobjekt visas också.

### <a name="condition-report"></a>Villkorsrapport

I det här avsnittet visas statistik om sökfrågan och antalet uppskattade objekt som matchade olika delar av sökfrågan. Du kan använda statistiken för att analysera antalet objekt som matchar varje komponent i sökfrågan. Det kan hjälpa dig att förfina sökvillkoren och vid behov begränsa omfattningen. Du kan också ladda ned en kopia av rapporten i CSV-format.

![Villkorsrapport](../media/SearchContentReportNoKeywordList.png)

- **Platstyp:** Den typ av innehållsplats som frågestatistiken gäller för. Värdet för en **Exchange** anger en postlådas plats. Värdet för en **SharePoint** anger en webbplatsplats.

- **Del**: Den del av sökfrågan som statistiken gäller för. **Primär** anger hela sökfrågan. **Nyckelord** anger att statistiken på raden är för ett visst nyckelord. Om du använder en nyckelordslista för sökfråga inkluderas statistik för varje komponent i frågan i den här tabellen. Mer information finns i Hämta [nyckelordsstatistik för sökningar](#get-keyword-statistics-for-searches).

- **Villkor:** Den faktiska komponenten (nyckelord eller villkor) i sökfrågan som returnerar den statistik som visas på motsvarande rad.

- **Platser med träffar:** Antalet innehållsplatser (anges av  kolumnen Platstyp) som innehåller objekt som matchar den primära frågan eller nyckelordsfrågan som visas i **kolumnen** Villkor.

- **Objekt:** Det antal objekt (från den angivna innehållsplatsen) som matchar frågan som visas i **kolumnen** Villkor. Som tidigare förklarats räknas ett objekt bara en gång i den här kolumnen om det innehåller flera förekomster av ett nyckelord som söks igenom.

- **Storlek (MB)**: Den totala storleken på alla objekt som hittades (på den angivna innehållsplatsen) som matchar sökfrågan i **kolumnen** Villkor.

### <a name="top-locations"></a>Mest populära platserna

I det här avsnittet visas statistik för specifika innehållsplatser med de flesta objekt som returneras av sökningen. De 1 000 översta platserna visas. Du kan också ladda ned en kopia av rapporten i CSV-format.

- Namnet på platsnamnet (postlådors e-postadress och webbplatsadressen).

- Platstyp (en postlåda eller webbplats).

- Beräknat antal objekt på innehållsplatsen som returneras av sökningen.

- Den totala storleken på uppskattade objekt på varje innehållsplats.

## <a name="get-keyword-statistics-for-searches"></a>Hämta nyckelordsstatistik för sökningar

Som tidigare förklarats **visar villkorsrapporten** sökfrågan och antalet (och storleken) objekt som matchar frågan. Om du använder en nyckelordslista när du skapar eller redigerar en sökfråga kan du få utökad statistik som visar hur många objekt som matchar varje nyckelord eller nyckelordsfras. Det kan hjälpa dig att snabbt identifiera vilka delar av frågan som är mest (och minst) effektiva. Om ett nyckelord till exempel returnerar ett stort antal objekt kan du välja att förfina nyckelordsfrågan för att begränsa sökresultatet.

Så här skapar du en nyckelordslista och visar nyckelordsstatistik för en sökning:
  
1. Skapa en Microsoft 365 innehållssökning eller en sökning kopplad till ett Core eDiscovery-ärende i säkerhets- och efterlevnadscentret.

2. På **sidan** Villkor i sökguiden. markera **kryssrutan Visa** nyckelordslista.

   ![Kryssrutan Visa lista över nyckelord](../media/SearchKeywordsList1.png)

3. Skriv ett nyckelord eller en nyckelordsfas på en rad i tabellen nyckelord. Skriv till exempel **budget på** den  första raden, ange säkerhet på den andra raden och **skriv RÅ2021** på den tredje raden.

   ![Skriv upp till 20 nyckelord eller nyckelordsfraser i listan](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > För att minska problemen som orsakas av stora nyckelordslistor är du begränsad till högst 20 rader i nyckelordslistan för en sökfråga.

4. Kör sökningen när du har lagt till nyckelorden i listan som du vill söka efter och hämta statistik för.

5. När sökningen är klar väljer du den för att visa den utfällklara sidan.

6. Klicka på **villkorsrapporten** på fliken **Sökstatistik om** du vill visa nyckelordsstatistik för sökningen.

    ![Statistiken för varje nyckelord visas](../media/SearchKeywordsList3.png)
  
    Som du ser i föregående skärmbild visas statistiken för varje nyckelord. detta omfattar:

    - Nyckelordsstatistik för varje typ av innehållsplats som ingår i sökningen.

    - Antalet icke indexerade postlådeobjekt.

    - Den faktiska sökfrågan och resultaten för varje  nyckelord (identifieras som **Nyckelord** i kolumnen Del), som innehåller eventuella villkor från sökfrågan.

    - Den fullständiga sökfrågan (identifieras **som primär** i **kolumnen** Del) och statistik för hela frågan för varje platstyp. Observera att detta är samma statistik som visas på **fliken** Sammanfattning.
