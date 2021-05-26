---
title: Skillnader mellan uppskattade och faktiska eDiscovery-sökresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Förstå varför uppskattade och faktiska sökresultat kan variera i sökningar som körs med eDiscovery-verktyg i Office 365.
ms.openlocfilehash: 17a4c2eea9833afa2112fa8ab918dcda074eeb36
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653517"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Skillnader mellan uppskattade och faktiska eDiscovery-sökresultat

Det här avsnittet gäller sökningar som du kan köra med något av följande Microsoft 365 eDiscovery-verktyg: 

- Innehållssökning
- Core eDiscovery

När du kör en eDiscovery-sökning returnerar verktyget du använder en uppskattning av antalet objekt (och deras totala storlek) som matchar sökvillkoren. När du till exempel kör en sökning i kompatibilitetscentret för Microsoft 365, visas det uppskattade sökresultatet på den utfällade sidan för den markerade sökningen.
  
![Uppskattning av resultat som visas på den utfällade söksidan](../media/EstimatedSearchResults1.png)
  
Det här är samma uppskattning av den totala storleken och antalet objekt som visas i verktyget för eDiscovery-export när du exporterar resultaten till en lokal dator och i rapporten Om sammanfattning av export som hämtas med sökresultaten.
  
**Uppskattade resultat i eDiscovery-exportverktyget**

![Uppskattade resultat i verktyget eDiscovery-export](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Uppskattat resultat i rapporten Exportsammanfattning**

![Uppskattade sökresultat ingår i rapporten Exportsammanfattning](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Som du ser i föregående skärmbild av rapporten Exportsammanfattning skiljer sig storleken och antalet verkliga sökresultat som hämtas från från storleken och antalet uppskattade sökresultat.
  
![Skillnad mellan uppskattade och hämtade sökresultat](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Här är några anledningar till dessa skillnader:
  
- **Sättet som resultaten beräknas på.** En uppskattning av sökresultatet är just det, en uppskattning (och inte ett faktiskt antal) av de objekt som uppfyller sökfrågans villkor. För att sammanställa uppskattningen av Exchange objekt begärs en lista med meddelande-ID:er som uppfyller sökvillkoren från Exchange-databasen av det eDiscovery-verktyg som du använder. Men när du exporterar sökresultaten kör sökningen igen och de faktiska meddelandena hämtas från Exchange databas. Skillnaderna kan därför vara ett resultat av hur det uppskattade antalet objekt och det faktiska antalet objekt bestäms.

- **Ändringar som inträffar mellan tidpunkter när du uppskattar och exporterar sökresultat**. När du exporterar sökresultat startas sökningen om för att samla in de senaste objekten i sökindexet som uppfyller sökvillkoren. Det är möjligt att det finns ytterligare objekt som skapats, skickats eller tagits emot och som uppfyller sökvillkoren under tiden från det att det uppskattade sökresultatet samlades in och när sökresultatet exporterades. Det är också möjligt att objekt som fanns i sökindexet när sökresultaten uppskattades inte längre finns där eftersom de togs bort från innehållsplatsen innan sökresultaten exporterades. Ett sätt att minimera det här problemet är att ange ett datumintervall för en e-dataidentifieringssökning. Ett annat sätt är att placera ett lager på innehållsplatser så att objekt bevaras och inte kan rensas. 

   Även om det är ovanligt, även om ett undantag används, kan underhåll av inbyggda kalenderobjekt (som inte kan redigeras av användaren men ingår i många sökresultat) tas bort då och då. Den här periodiska borttagningen av kalenderobjekt resulterar i färre objekt som exporteras.

- **Icke indexerade objekt.** Objekt som inte är indexerade för sökning kan orsaka skillnader mellan uppskattade och faktiska sökresultat. Du kan ta med icke indexerade objekt när du exporterar sökresultatet. Om du tar med icke indexerade objekt när du exporterar sökresultat kan det finnas fler objekt som exporteras. Det här orsakar en skillnad mellan det uppskattade och exporterade sökresultatet.

    När du använder verktyget Innehållssökning kan du välja att inkludera icke indexerade objekt när du exporterar sökresultat. Antalet icke indexerade objekt som returneras av sökningen visas på den utfällda sidan tillsammans med andra uppskattade sökresultat. Icke indexerade objekt inkluderas också i den totala storleken på det uppskattade sökresultatet. När du exporterar sökresultat kan du välja att ta med eller inte inkludera icke indexerade objekt. Hur du konfigurerar alternativen kan resultera i skillnader mellan uppskattat och de faktiska sökresultat som hämtas.

- **Exportera resultatet av en innehållssökning som omfattar alla innehållsplatser**. Om sökningen du exporterar resultat från var en sökning på alla innehållsplatser i organisationen exporteras bara icke indexerade objekt från innehållsplatser som innehåller objekt som matchar sökvillkoren. Med andra ord exporteras inte icke indexerade objekt i postlådan eller webbplatsen om inga sökresultat hittas i en postlåda eller på en webbplats. Icke indexerade objekt från alla innehållsplatser (även de som inte innehåller objekt som matchar sökfrågan) inkluderas emellertid i det uppskattade sökresultatet.

    Alternativt, om sökningen du exporterar resultat från inkluderade specifika innehållsplatser, exporteras icke indexerade objekt (som inte utesluts av sökvillkoren) från alla innehållsplatser som anges i sökningen. I det här fallet ska det uppskattade antalet icke indexerade objekt och antalet icke indexerade objekt som exporteras vara detsamma.

    Anledningen till att du inte exporterar icke indexerade objekt från varje plats i organisationen beror på att det kan öka sannolikheten för exportfel och öka tiden det tar att exportera och ladda ned sökresultaten.

- **Icke indexerade objekt i SharePoint och OneDrive inte ingår i sökberäkningarna.** Icke indexerade objekt SharePoint webbplatser och OneDrive för företag-konton tas inte med i det uppskattade sökresultatet. Det beror på SharePoint-indexet inte innehåller data för icke indexerade objekt. Endast icke indexerade objekt från postlådor ingår i sökberäkningarna. Men om du tar med icke indexerade objekt när du exporterar sökresultat ingår icke indexerade objekt i SharePoint och OneDrive, vilket ökar antalet objekt som faktiskt exporteras. Det leder till skillnader mellan det uppskattade resultatet (som inte inkluderar icke indexerade objekt på SharePoint- OneDrive-webbplatserna) och de faktiska objekt som laddas ned. Regeln om att exportera icke indexerade objekt endast från innehållsplatser som innehåller objekt som matchar sökvillkoren gäller fortfarande i det här fallet.

- **Dokumentversioner i SharePoint och OneDrive**. När du SharePoint från OneDrive-konton tas inte flera versioner av ett dokument med i det uppskattade sökresultatet. Men du kan välja att inkludera alla dokumentversioner när du exporterar sökresultatet. Om du inkluderar dokumentversioner när du exporterar sökresultat, ökas det faktiska antalet (och den totala storleken) för de exporterade objekten.

- **SharePoint mappar**. Om mappnamnet i SharePoint matchar en sökfråga inkluderas ett antal sådana mappar i sökberäkningen (men inte objekten i de mapparna). När du exporterar sökresultatet exporteras objekten i mappen, men den faktiska mappen exporteras inte. Resultatet är att antalet exporterade objekt är mer än det uppskattade sökresultatet. Om en mapp är tom minskas antalet faktiska sökresultat med ett objekt, eftersom den faktiska mappen inte exporteras.

- **SharePoint listor**. Om namnet på en söklista SharePoint en sökfråga inkluderas ett antal av alla objekt i listan i sökberäkningen. När du exporterar sökresultaten exporteras listan (och listobjekten) som en enda CSV-fil. Det här minskar det faktiska antalet objekt som faktiskt exporteras. Om listan innehåller bifogade filer exporteras de bifogade filerna som separata dokument, vilket också ökar antalet exporterade objekt.

- **Rådatafilformat och exporterade filformat.** För Exchange objekt beräknas den uppskattade storleken på sökresultatet med hjälp av storlekarna för Exchange meddelanden. Men e-postmeddelanden exporteras i en PST-fil eller som enskilda meddelanden (som är formaterade som EML-filer). Båda dessa exportalternativ använder ett annat filformat än obearbetade meddelanden Exchange, vilket resulterar i att den totala exporterade filstorleken skiljer sig från den uppskattade filstorleken.

- **Avduplicering av Exchange objekt under exporten.** För Exchange objekt minskar avdupliceringen antalet objekt som exporteras. Du kan välja att duplicera sökresultaten när du exporterar dem. För Exchange innebär det att bara en instans av ett meddelande exporteras, även om meddelandet kan hittas i flera postlådor. Det uppskattade sökresultatet inkluderar alla förekomster av ett meddelande. Om du väljer alternativet för avduplicering när du exporterar sökresultat kan det faktiska antalet exporterade objekt bli betydligt mindre än det uppskattade antalet objekt.

Sökresultatrapporten (Results.csv) innehåller en post för varje dubblettmeddelande och identifierar källpostlådan där det finns ett dubblettmeddelande. På så sätt kan du identifiera alla postlådor som innehåller ett duplicerat meddelande.

> [!NOTE]
> Om du inte markerar alternativet Inkludera objekt som är krypterade eller har ett okänt **format** när du exporterar sökresultaten eller laddar ned rapporter, laddas rapporterna om indexfel ned men de innehåller inga poster. Det betyder inte att det inte finns indexfel. Det innebär bara att icke indexerade objekt inte inkluderades i exporten.
