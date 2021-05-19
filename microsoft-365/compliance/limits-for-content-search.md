---
title: Begränsningar för innehållssökning och bas-eDiscovery i efterlevnadscentret
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Läs mer om de gällande begränsningarna för funktionerna Innehållssökning och Grundläggande eDiscovery i Microsoft 365 efterlevnadscenter.
ms.openlocfilehash: 5ca6fd30b40fbfaa3b93095eee403979f541d154
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538429"
---
# <a name="limits-for-ediscovery-search"></a>Begränsningar för eDiscovery-sökning 

Olika begränsningar tillämpas på eDiscovery-sökverktygen i Microsoft 365 efterlevnadscenter. Det omfattar sökningar som körs på **sidan Innehållssökning** och sökningar som är associerade med eDiscovery-fall på **sidan Bas-eDiscovery.** De här begränsningarna bidrar till att bevara hälso- och kvaliteten på tjänster som ges till organisationer. Det finns också begränsningar för indexering av e-postmeddelanden i Exchange Online för sökning. Du kan inte ändra gränserna för eDiscovery-sökningar eller e-postindexering, men du bör känna till dem så att du kan ta med de här begränsningarna i beräkningen när du planerar, kör och felsöker eDiscovery-sökningar.

Information om begränsningar för Advanced eDiscovery finns i [Begränsningar i Advanced eDiscovery](limits-ediscovery20.md)
  
## <a name="search-limits"></a>Sökbegränsningar

I följande tabell visas sökbegränsningar när du använder verktyget för innehållssökning i kompatibilitetscentret för Microsoft 365 och för sökningar som är kopplade till ett bas-eDiscovery-ärende.
  
| Beskrivning av gräns | Gräns |
|:-----|:-----|
|Maximalt antal postlådor eller webbplatser som kan sökas i en enda sökning  <br/> |Ingen gräns <sup>1</sup> <br/> |
|Maximalt antal sökningar som kan köras samtidigt i organisationen.  <br/> |30  <br/> |
|Maximalt antal organisationsomfattande sökningar som kan köras samtidigt. <br/> |3  <br/> |
|Det maximala antalet sökningar som en enskild användare kan starta samtidigt. Den här gränsen träffar troligen när användaren försöker starta flera sökningar med hjälp av **kommandot Get-ComplianceSearch \| Start-ComplianceSearch** i Security & Compliance Center PowerShell.  <br/> |10  <br/> |
|Maximalt antal objekt per användarpostlåda som visas på förhandsgranskningssidan när innehållssökningsresultat förhandsgranskas.  <br/> |100  <br/> |
|Maximalt antal objekt som hittas i alla användarpostlådor som visas på förhandsgranskningssidan när du förhandsgranskar sökresultat. De senaste objekten visas.  <br/> |1 000  <br/> |
|Maximalt antal användarpostlådor som kan förhandsgranskas för sökresultat. Om det finns fler än 1 000 postlådor som innehåller innehåll som matchar sökfrågan är endast de 1 000 postlådor som har flest sökresultat tillgängliga för förhandsgranskning.  <br/> |1 000  <br/> |
|Maximalt antal objekt på SharePoint och OneDrive för företag som visas på förhandsgranskningssidan när du förhandsgranskar sökresultat. De senaste objekten visas.  <br/> |200  <br/> |
|Maximalt antal webbplatser (i SharePoint och OneDrive för företag) som kan förhandsgranskas för sökresultat. Om det finns mer än 200 webbplatser totalt som innehåller innehåll som matchar sökfrågan är endast de 200 webbplatser som har flest sökresultat tillgängliga för förhandsgranskning.  <br/> |200  <br/> |
|Maximalt antal objekt per postlåda i den gemensamma mappen som visas på förhandsgranskningssidan när innehållssökningsresultat förhandsgranskas.  <br/> |100  <br/> |
|Maximalt antal objekt som hittas i alla postlådor i gemensamma mappar som visas på förhandsgranskningssidan när du förhandsgranskar innehållssökningsresultat.  <br/> |200  <br/> |
|Maximalt antal postlådor i gemensamma mappar som kan förhandsgranskas för sökresultat. Om det finns fler än 500 postlådor för gemensamma mappar som innehåller innehåll som matchar sökfrågan är endast de 500 postlådorna med flest sökresultat tillgängliga för förhandsgranskning.  <br/> |500  <br/> |
|Det maximala antalet tecken för sökfrågan (inklusive operatorer och villkor) för en sökning.  <br/><br/> **Obs!** Den här gränsen gäller efter att frågan har expanderats och innehåller tecken från nyckelordsfrågan, eventuella sökbehörighetsfilter som används för användaren och WEBBADRESSerna för alla webbplatsplatser. Det innebär att frågan utökas mot var och en av nyckelorden. Om en sökfråga till exempel har 15 nyckelord och ytterligare parametrar och villkor utökas frågan 15 gånger, var och en med de andra parametrarna och villkoren i frågan. Så även om antalet tecken i sökfrågan kan vara under gränsen, är det den utökade frågan som kan bidra till att överskrida gränsen.  <br/> |**Postlådor:** 10 000  <br/> **Webbplatser:** 4 000 vid sökning på alla webbplatser eller 2 000 vid sökning på upp till 20 webbplatser <sup>2</sup> <br/> |
|Maximalt antal varianter som returneras när ett prefix-jokertecken används för att söka efter  en exakt fras i en sökfråga eller när du använder ett prefix-jokertecken och NEAR-boolesk operator.  <br/> |10 000 <sup>3</sup> <br/> |
|Lägsta antal alfatecken för jokertecken i prefix. till exempel  `time*` ,  `one*` eller  `set*` .  <br/> |3  <br/> |
|Det maximala antalet postlådor i en sökning som du kan ta bort objekt i genom att göra en sök- och rensningsåtgärd (med kommandot **New-ComplianceSearchAction -Purge).** Om sökningen som du utför en rensning för har fler källpostlådor än den här gränsen misslyckas rensningsåtgärden. Mer information om hur du söker efter och rensar finns [i Söka efter och ta bort e-postmeddelanden i organisationen.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50 000  <br/> |
|Det maximala antalet platser i en sökning som du kan exportera objekt från. Om sökningen som du exporterar har fler platser än den här gränsen misslyckas exporten. Mer information finns i [Exportera sökresultat för innehåll.](export-search-results.md)  <br/> |100 000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Även om du kan söka i ett obegränsat antal postlådor i en enda sökning kan du bara ladda ned exporterade sökresultat från maximalt 100 000 postlådor med hjälp av eDiscovery-exportverktyget i efterlevnadscentret för Microsoft 365. <br/><br/> <sup>2</sup> När du SharePoint och OneDrive för företag räknas tecknen i webbadresserna till webbplatserna som genomsöks mot den här gränsen. <br/><br/> <sup>3</sup> För frågor som inte är fraserade (ett nyckelordsvärde som inte använder dubbla citattecken) används ett särskilt prefixindex. Det innebär att ett ord förekommer i ett dokument, men inte där det förekommer i dokumentet. Om du vill göra en frasfråga (ett nyckelordsvärde med dubbla citattecken) måste vi jämföra positionen i dokumentet för orden i frasen. Det innebär att vi inte kan använda prefixindexet för frasfrågor. I det här fallet expanderar vi frågan internt med alla möjliga ord som prefixet expanderar till. kan till  `"time*"` exempel expandera till  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10 000 är det maximala antalet varianter som ordet kan utökas till, inte antalet dokument som matchar frågan. Det finns ingen övre gräns för termer som inte är fraser. 
  
## <a name="search-times"></a>Söktider
Microsoft samlar in prestandainformation för sökningar som körs av alla organisationer. Sökfrågans komplexitet påverkar visserligen söktiden, men det är antalet postlådor som genomsöks som har störst påverkan på söktiden. Även om Microsoft inte tillhandahåller ett servicenivåavtal för söktider visar följande tabell genomsnittliga söktider för sökningar i samlingar baserat på antalet postlådor som ingår i sökningen.

|Antal postlådor|Genomsnittlig söktid|
|:-----|:-----|
|100|30 sekunder|
|1 000|45 sekunder|
|10 000|4 minuter|
|25 000|10 minuter|
|50 000|20 minuter|
|100 000|25 minuter|
|||

## <a name="export-limits"></a>Exportgränser
I följande tabell visas begränsningar när du exporterar resultatet av en innehållssökning. De här begränsningarna gäller även när du exporterar innehåll från ett Core eDiscovery-ärende.

|Beskrivning av gräns|Gräns|
|:-----|:-----|
|Maximal mängd exporterbara data från en enskild sökning  <br/><br/> **Obs!** Om sökresultaten är större än 2 TB bör du överväga att använda datumintervall eller andra typer av filter för att minska den totala storleken på sökresultatet. <br/>  |2 TB  <br/> | 
|Maximalt antal organisationer kan exportera på en enskild dag <br/><br/> **Obs!** Den här gränsen återställs dagligen kl. 12:00 UTC <br/> |2 TB <br/> |
|Maximalt antal samtidiga exporter som kan köras samtidigt inom organisationen <br/><br/> **Obs!** Om du **kör en rapport endast-export** räknas mot totalt antal samtidiga exporter för organisationen. Om tre användare utför tre exporter var kan endast en annan export utföras. Oavsett om det gäller export av en rapport eller sökresultat kan inga andra exporter utföras förrän en har slutförts.   <br/> |10 <br/> |
|Största antal exporter en enskild användare kan köras samtidigt <br/> |3 <br/> |
|Maximalt antal postlådor för sökresultat som kan laddas ned med eDiscovery-exportverktyget <br/>| 100 000 <br/>|
|Maximal storlek på PST-fil som kan exporteras <br/><br/> **Obs!** Om sökresultatet från en användares postlåda är större än 10 GB exporteras sökresultatet för postlådan i två (eller fler) separata PST-filer. Om du väljer att exportera alla sökresultat i en enskild PST-fil kommer PST-filen att spilla till ytterligare PST-filer om den totala storleken på sökresultatet är större än 10 GB. Om du vill ändra den här standardstorleken kan du redigera Windows-registret på den dator som du använder för att exportera sökresultatet. Se [Ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat](change-the-size-of-pst-files-when-exporting-results.md). Sökresultaten från en viss postlåda delas inte upp mellan flera PST-filer såvida inte innehållet från en enda postlåda är mer än 10 GB. Om du väljer att exportera sökresultatet i en PST-fil för som innehåller alla meddelanden i en enda mapp och sökresultaten är större än 10 GB är objekten fortfarande ordnade i kronologisk ordning, så de kommer att vara inskickade i ytterligare PST-filer baserat på skickat datum.<br/> | 10 GB <br/> |
|Hastighet då sökresultat från postlådor och webbplatser laddas upp till en Plats som tillhandahålls av Microsoft Azure Storage webbplats. |Maximalt 2 GB per timme|
|||

## <a name="indexing-limits-for-email-messages"></a>Indexeringsbegränsningar för e-postmeddelanden

I följande tabell beskrivs indexeringsbegränsningar som kan resultera i att ett e-postmeddelande returneras som ett icke indexerat objekt eller ett delvis indexerat objekt i resultatet av en innehållssökning.
  
| Indexeringsgräns | Maxvärde | Beskrivning |
|:-----|:-----|:-----|
|Maximal storlek på bifogade filer|150 MB  <br/> |Den maximala storleken på en e-postbilaga som kommer att tolkas för indexering. Bifogade filer som är större än den här gränsen kommer inte att analyseras för indexering och meddelandet med den bifogade filen markeras som delvis indexerat.  <br/> <br/>**Obs!** Tolkning är en process där indexeringstjänsten hämtar text från den bifogade filen, tar bort onödiga tecken som skiljetecken och blanksteg och delar sedan in texten i ord (i en process som kallas tokenisering) som sedan lagras i indexet.           |
|Maximalt antal bifogade filer  <br/> |250  <br/> |Maximalt antal bifogade filer i ett e-postmeddelande som kan analyseras för indexering. Om ett meddelande har fler än 250 bifogade filer analyseras och indexeras de första 250 och meddelandet markeras som delvis indexerats eftersom det hade ytterligare bifogade filer som inte tolkats.  <br/> |
|Maximalt djup för bifogade filer  <br/> |30  <br/> |Maximalt antal kapslade bifogade filer som tolkas. Om ett e-postmeddelande till exempel har ett annat meddelande bifogat och det bifogade meddelandet har ett bifogat Word-dokument indexeras Word-dokumentet och det bifogade meddelandet. Beteendet fortsätter för upp till 30 kapslade bifogade filer.  <br/> |
|Maximalt antal bifogade bilder  <br/> |0  <br/> |En bild som är bifogad i ett e-postmeddelande hoppas över av toningsern och indexeras inte.  <br/> |
|Maximal tid för tolkning av ett objekt  <br/> |30 sekunder  <br/> |Maximalt 30 sekunder läggs på tolkning av ett objekt för indexering. Om tolkningstiden överskrider 30 sekunder markeras objektet som delvis indexerats.  <br/> |
|Maximal utdata för tolkare  <br/> |2 miljoner tecken  <br/> |Största möjliga indexerad text från tolkaren. Om parsern till exempel extraherar 8 miljoner tecken från ett dokument indexeras endast de första 2 miljoner tecknen.  <br/> |
|Maximalt antal anteckningstoken  <br/> |2 miljoner  <br/> |När ett e-postmeddelande indexeras får varje ord olika bearbetningsinstruktioner som anger hur ordet ska indexeras. Varje uppsättning bearbetningsinstruktioner kallas en anteckningstoken. För att bevara kvaliteten på tjänsten i Office 365 finns det en gräns på 2 miljoner anteckningstoken för ett e-postmeddelande.  <br/> |
|Maximal storlek på brödtext i index  <br/> |67 miljoner tecken  <br/> |Det totala antalet tecken i brödtexten i ett e-postmeddelande och dess bifogade filer. När ett e-postmeddelande indexeras sammanfogas all text i brödtexten i meddelandet och i alla bifogade filer till en enda sträng. Den maximala storleken på strängen som indexeras är 67 miljoner tecken.  <br/> |
|Maximalt antal unika token i brödtexten  <br/> |1 miljon  <br/> |Som tidigare förklarats är token ett resultat av att extrahera text från innehåll, ta bort skiljetecken och blanksteg och sedan dela in det i ord (kallas token) som lagras i indexet. Frasen innehåller  `"cat, mouse, bird, dog, dog"` till exempel 5 token. Men endast 4 av dessa är unika token. Det finns en gräns på 1 miljon unika token per e-postmeddelande, vilket förhindrar att indexet blir för stort med slumpmässiga token.  <br/> |
|||
  
## <a name="more-information"></a>Mer information

Det finns ytterligare begränsningar relaterade till olika aspekter av sökning efter innehåll, till exempel innehållsindexering. Mer information om de här begränsningarna finns i följande avsnitt:

- [Delvis indexerade objekt i Innehållssökning](partially-indexed-items-in-content-search.md)

- [Undersöker delvis indexerade objekt i eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Sökbegränsningar för SharePoint Online](/sharepoint/search-limits)

Mer information om innehållssökningar finns i:
  
- [Innehållssökning i Microsoft 365](content-search.md)

- [Söka efter innehåll i ett grundläggande eDiscovery-ärende](search-for-content-in-core-ediscovery.md)

- [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md)

Information om begränsningar av ärendet som rör bas-e-dataidentifiering och Advanced eDiscovery finns i:

- [Begränsningar i bas-e-dataidentifiering](limits-core-ediscovery.md)

- [Begränsningar i Advanced eDiscovery](limits-ediscovery20.md)
