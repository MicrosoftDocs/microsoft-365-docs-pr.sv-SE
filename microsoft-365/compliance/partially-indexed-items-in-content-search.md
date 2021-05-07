---
title: Delvis indexerade objekt i Innehållssökning och andra eDiscovery-verktyg
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Läs mer om icke indexerade objekt i Exchange och SharePoint som du kan ta med i en eDiscovery-sökning som du kör Microsoft 365 efterlevnadscenter.
ms.openlocfilehash: 40995aa403686caadd5e35b6fa9c6ca20ee017ee
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162808"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Delvis indexerade objekt i eDiscovery

En eDiscovery-sökning som du kör från efterlevnadscentret för Microsoft 365 inkluderar automatiskt delvis indexerade objekt i det uppskattade sökresultatet när du kör en sökning. Delvis indexerade objekt Exchange postlådeobjekt och dokument på SharePoint och OneDrive för företag-webbplatser som av någon anledning inte indexerats helt för sökning. I Exchange innehåller ett delvis indexerat objekt vanligtvis en fil (av en filtyp som inte kan indexeras) som bifogas i ett e-postmeddelande. Här är några andra orsaker till varför objekt inte kan indexeras för sökning och returneras som delvis indexerade objekt när du kör en eDiscovery-sökning:
  
- Filtypen är okänd eller stöds inte för indexering.

- Meddelanden har en bifogad fil utan en giltig hanterare, till exempel bildfiler. det här är den vanligaste orsaken till delvis indexerade e-postobjekt.

- Filtypen stöds för indexering men ett indexeringsfel uppstod för en viss fil.

- För många bifogade filer i ett e-postmeddelande.

- En fil som bifogas i ett e-postmeddelande är för stor.

- En fil krypteras med teknik som inte kommer från Microsoft.

- En fil är lösenordsskyddad.

> [!NOTE]
> De flesta organisationer har mindre än 1 % innehåll per volym och mindre än 12 % i storlek som har delvis indexerats. Anledningen till skillnaden mellan volym och storlek är att större filer har en högre sannolikhet för att innehålla innehåll som inte kan indexeras helt.
  
För juridiska undersökningar kan din organisation behöva granska delvis indexerade objekt. Du kan också ange om delvis indexerade objekt ska inkluderas när du exporterar sökresultatet till en lokal dator eller när du förbereder resultatet för analys Advanced eDiscovery. Mer information finns i [Undersöker delvis indexerade objekt i eDiscovery.](investigating-partially-indexed-items-in-ediscovery.md)
  
## <a name="file-types-not-indexed-for-search"></a>Filtyper som inte indexeras för sökning

Vissa typer av filer, till exempel Bitmapps- eller MP3-filer, innehåller inte innehåll som kan indexeras. Därför utför inte sökindexeringsservrarna i Exchange och SharePoint fulltextindexering på dessa typer av filer. Dessa typer av filer betraktas som filtyper som inte stöds. Det finns även filtyper för vilka fulltextindexering har inaktiverats, antingen som standard eller av en administratör. Filtyper som inte stöds och inaktiveras etiketteras som icke indexerade objekt i innehållssökningar. Som tidigare nämnts kan delvis indexerade objekt ingå i uppsättningen sökresultat när du kör en sökning, exportera sökresultatet till en lokal dator eller förbereda sökresultatet för Advanced eDiscovery.
  
En lista över filformat som stöds och inaktiveras finns i följande avsnitt:
  
- **Exchange**  -  [Filformat som indexeras av Exchange Search](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- **Exchange**  -  [Get-SearchDocumentFormat](/powershell/module/exchange/get-searchdocumentformat)

- **SharePoint**  -  [Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Meddelanden och dokument med delvis indexerade filtyper kan returneras i sökresultat

Inte alla e-postmeddelanden med en delvis indexerad bifogad fil eller alla delvis SharePoint dokument returneras automatiskt som ett delvis indexerat objekt. Det beror på att andra egenskaper för meddelanden eller dokument,  till  exempel egenskapen Ämne i e-postmeddelanden och egenskaperna Rubrik eller Författare för dokument indexeras och går att söka i.  En nyckelordssökning efter "ekonomi" returnerar exempelvis objekt med en delvis indexerad bifogad fil om nyckelordet förekommer i ämnet för ett e-postmeddelande eller i filnamnet eller titeln på ett dokument. Men om nyckelordet bara visas i brödtexten i filen returneras meddelandet eller dokumentet som ett delvis indexerat objekt.
  
På samma sätt inkluderas meddelanden med delvis indexerade bifogade filer och dokument av en delvis indexerad filtyp i sökresultat när andra meddelande- eller dokumentegenskaper, som är indexerade och sökbara, uppfyller sökvillkoren. Meddelandeegenskaper som indexeras för sökning är bland annat datum för skickade och mottagna meddelanden, avsändare och mottagare, filnamnet på en bifogad fil och text i meddelandets brödtext. Dokumentegenskaper som indexeras för sökning omfattar datum som skapats och ändrats. Så även om en bifogad fil i ett meddelande kan vara ett delvis indexerat objekt inkluderas meddelandet i de vanliga sökresultaten om värdet för andra meddelande- eller dokumentegenskaper matchar sökvillkoren.
  
En lista med e-post- och dokumentegenskaper som du kan söka efter med hjälp av sökfunktionen i säkerhets- och efterlevnadscentret för & finns i Nyckelordsfrågor och sökvillkor för [eDiscovery.](keyword-queries-and-search-conditions.md)
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Delvis indexerade objekt ingår i sökresultatet

Organisationen kan behöva identifiera och utföra ytterligare analyser på delvis indexerade objekt för att fastställa vad de är, vad de innehåller och om de är relevanta för en viss undersökning. Som tidigare förklarats inkluderas delvis indexerade objekt på innehållsplatserna som genomsöks automatiskt i det uppskattade sökresultatet. Du kan välja att inkludera dessa delvis indexerade objekt när du exporterar sökresultat eller förbereder sökresultatet för Advanced eDiscovery.
  
Tänk på följande om delvis indexerade objekt:
  
- När du kör en eDiscovery-sökning visas det totala antalet och storleken på delvis indexerade Exchange-objekt (som returneras av sökfrågan) i sökstatistiken på den utfällda sidan och etiketterade som icke **indexerade objekt.** Statistik om delvis indexerade objekt som visas på den utfällda sidan omfattar inte delvis indexerade objekt i SharePoint eller OneDrive.

- Om sökningen du exporterar resultat från var en sökning på specifika innehållsplatser eller alla innehållsplatser i organisationen exporteras bara icke indexerade objekt från innehållsplatser som innehåller objekt som matchar sökvillkoren. Med andra ord exporteras inte icke indexerade objekt i postlådan eller webbplatsen om inga sökresultat hittas i en postlåda eller på en webbplats. Anledningen är att export av delvis indexerade objekt från många platser i organisationen kan öka sannolikheten för exportfel och öka tiden det tar att exportera och ladda ned sökresultaten.

    Om du vill exportera delvis indexerade objekt från alla innehållsplatser för en sökning konfigurerar du sökningen så att alla objekt returneras (genom att nyckelord tas bort från sökfrågan) och sedan exporteras endast delvis indexerade objekt när du exporterar sökresultatet (genom att klicka på Endast objekt som har ett okänt **format,** krypteras eller inte indexeras av andra orsaker **under** Utdataalternativ ).

- Om du väljer att ta med alla postlådeobjekt i sökresultatet, eller om en sökfråga inte anger några nyckelord eller bara anger ett datumintervall, kanske delvis indexerade objekt inte kopieras till PST-filen som innehåller delvis indexerade objekt. Det beror på att alla objekt, inklusive delvis indexerade objekt, automatiskt inkluderas i de vanliga sökresultaten.

- Delvis indexerade objekt kan inte förhandsgranskas. Du måste exportera sökresultatet för att visa delvis indexerade objekt som returneras av sökningen.

När du exporterar sökresultat och tar med delvis indexerade objekt i exporten exporteras dessutom delvis indexerade objekt från SharePoint-objekt till en mapp som heter **Ocrawlable**. När du exporterar delvis Exchange och objekt exporteras de på olika sätt beroende på om delvis indexerade objekt matchade sökfrågan och konfigurationen av exportinställningarna. 

I följande tabell visas exportbeteendet för indexerade och delvis indexerade objekt samt om respektive objekt ingår i de olika konfigurationsinställningarna för export.

|**Exportera konfiguration**|**Indexerade objekt som matchar sökfrågan**|**Delvis indexerade objekt som matchar sökfrågan**|**Delvis indexerade objekt som inte matchar sökfrågan**|
|:-----|:-----|:-----|:-----|
|Exportera endast indexerade objekt  <br/> |Exporterad<br/> |Exporteras (ingår i de indexerade objekten som exporteras)<br/>  |Inte exporterad <br/>|
|Exportera endast delvis indexerade objekt  <br/> |Inte exporterad  <br/> |Exporterade (som delvis indexerade objekt)<br/> |Exporterade (som delvis indexerade objekt)|
|Exportera indexerade och delvis indexerade objekt  <br/> |Exporterad<br/> |Exporteras (ingår i de indexerade objekten som exporteras)<br/>  |Exporterade (som delvis indexerade objekt)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Delvis indexerade objekt som inte finns med i sökresultatet

Om ett objekt är delvis indexerat men det inte uppfyller sökfrågevillkoren inkluderas det inte som ett delvis indexerat objekt i sökresultatet. Med andra ord är objektet exkluderat från sökresultatet. Om du väljer att inkludera delvis indexerade objekt när du exporterar resultatet av en sökning exporteras inte delvis indexerade objekt som uteslöts från sökresultaten.
  
Ett undantag till den här regeln är när du skapar ett frågebaserat undantag som är kopplat till ett eDiscovery-ärende. Om du skapar ett frågebaserat eDiscovery-rymmer sätts alla delvis indexerade objekt i register. Det omfattar delvis indexerade objekt som inte matchar sökfrågans villkor. Mer information om hur du skapar frågebaserade eDiscovery-rymmer finns i [Skapa ett eDiscovery-värde](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages"></a>Indexeringsbegränsningar för meddelanden

I följande tabell beskrivs indexeringsbegränsningar som kan resultera i att ett e-postmeddelande returneras som ett delvis indexerat objekt i en e-dataidentifieringssökning i Microsoft 365.
  
En lista över indexeringsbegränsningar för SharePoint dokument finns i [Sökbegränsningar för SharePoint Online.](/sharepoint/search-limits)
  
|**Indexeringsgräns**|**Maxvärde**|**Beskrivning**|
|:-----|:-----|:-----|
|Maximal storlek på bifogade filer (exklusive Excel filer)  <br/> |150 MB  <br/> |Den maximala storleken på en e-postbilaga som kommer att tolkas för indexering. Bifogade filer som är större än den här gränsen kommer inte att analyseras för indexering och meddelandet med den bifogade filen markeras som delvis indexerat.  <br/><br/> **Obs!** Tolkning är en process där indexeringstjänsten hämtar text från den bifogade filen, tar bort onödiga tecken som skiljetecken och blanksteg och delar sedan in texten i ord (i en process som kallas tokenisering) som sedan lagras i indexet.           |
|Maximal storlek Excel filer  <br/> |4 MB  <br/> |Den maximala storleken på en Excel som finns på en webbplats eller bifogad i ett e-postmeddelande som kommer att analyseras för indexering. Filer Excel filer som är större än denna gräns kommer inte att tolkas, och filen eller e-postmeddelandet med den bifogade filen markeras som icke indexerade.  <br/> |
|Maximalt antal bifogade filer  <br/> |250  <br/> |Maximalt antal bifogade filer i ett e-postmeddelande som kan analyseras för indexering. Om ett meddelande har fler än 250 bifogade filer analyseras och indexeras de första 250 och meddelandet markeras som delvis indexerats eftersom det hade ytterligare bifogade filer som inte tolkats.  <br/> |
|Maximalt djup för bifogade filer  <br/> |30  <br/> |Maximalt antal kapslade bifogade filer som tolkas. Om ett e-postmeddelande till exempel har ett annat meddelande bifogat och det bifogade meddelandet har ett bifogat Word-dokument indexeras Word-dokumentet och det bifogade meddelandet. Beteendet fortsätter för upp till 30 kapslade bifogade filer.  <br/> |
|Maximalt antal bifogade bilder  <br/> |0  <br/> |En bild som är bifogad i ett e-postmeddelande hoppas över av toningsern och indexeras inte.  <br/> |
|Maximal tid för tolkning av ett objekt  <br/> |30 sekunder  <br/> |Maximalt 30 sekunder läggs på tolkning av ett objekt för indexering. Om tolkningstiden överskrider 30 sekunder markeras objektet som delvis indexerats.  <br/> |
|Maximal utdata för tolkare  <br/> |2 miljoner tecken  <br/> |Största möjliga indexerad text från tolkaren. Om parsern till exempel extraherar 8 miljoner tecken från ett dokument indexeras endast de första 2 miljoner tecknen.  <br/> |
|Maximalt antal anteckningstoken  <br/> |2 miljoner  <br/> |När ett e-postmeddelande indexeras får varje ord olika bearbetningsinstruktioner som anger hur ordet ska indexeras. Varje uppsättning bearbetningsinstruktioner kallas en anteckningstoken. För att bevara kvaliteten på tjänsten i Office 365 finns det en gräns på 2 miljoner anteckningstoken för ett e-postmeddelande.  <br/> |
|Maximal storlek på brödtext i index  <br/> |67 miljoner tecken  <br/> |Det totala antalet tecken i brödtexten i ett e-postmeddelande och dess bifogade filer. När ett e-postmeddelande indexeras sammanfogas all text i brödtexten i meddelandet och i alla bifogade filer till en enda sträng. Den maximala storleken på strängen som indexeras är 67 miljoner tecken.  <br/> |
|Maximalt antal unika token i brödtexten  <br/> |1 miljon  <br/> |Som tidigare förklarats är token ett resultat av att extrahera text från innehåll, ta bort skiljetecken och blanksteg och sedan dela in det i ord (kallas token) som lagras i indexet. Frasen innehåller  `"cat, mouse, bird, dog, dog"` till exempel 5 token. Men endast 4 av dessa är unika token. Det finns en gräns på 1 miljon unika token per e-postmeddelande, vilket förhindrar att indexet blir för stort med slumpmässiga token.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Mer information om delvis indexerade objekt

- Eftersom meddelande- och dokumentegenskaper och deras metadata indexeras tidigare kan en nyckelordssökning ge resultat om nyckelordet visas i indexerade metadata. Men det kan hända att samma nyckelordssökning inte returnerar samma objekt om nyckelordet bara visas i innehållet för ett objekt med filtypen Stöds inte. I det här fallet returneras objektet som ett delvis indexerat objekt.

- Om ett delvis indexerat objekt ingår i sökresultatet eftersom det uppfyller sökfrågevillkoren (och inte uteslöts) tas det inte med som ett delvis indexerat objekt i den uppskattade sökstatistiken. Dessutom inkluderas det inte i delvis indexerade objekt när du exporterar sökresultat.

- Även om en filtyp stöds för indexering och indexeras kan det finnas indexerings- eller sökfel som gör att en fil returneras som ett delvis indexerat objekt. Till exempel kan sökningen efter en mycket stor Excel fil lyckas delvis (eftersom de första 4 MB indexeras), men sedan misslyckas eftersom begränsningen för filstorlek överskrids. I det här fallet är det möjligt att samma fil returneras med sökresultatet och som ett delvis indexerat objekt.

- Filer som är [](encryption.md) krypterade med Microsoft-krypteringsteknik och som bifogas i ett e-postmeddelande som matchar villkoren för en sökning kan förhandsgranskas och dekrypteras när de exporteras. För stunden är filer som krypteras med microsoft-krypteringsteknik (och som lagras i SharePoint eller OneDrive för företag) delvis indexerade.

- E-postmeddelanden som krypteras med S/MIME indexeras delvis. Det omfattar krypterade meddelanden med eller utan bifogade filer.

- E-postmeddelanden som skyddas med Azure Rights Management indexeras och inkluderas i sökresultaten om de matchar sökfrågan. Rättighetsskyddade e-postmeddelanden dekrypteras och kan förhandsgranskas och exporteras. Den här funktionen kräver att du har tilldelats rollen RMS-dekrypterad, som tilldelas rollgruppen för eDiscover-hanteraren som standard.

## <a name="see-also"></a>Se även

[Undersöker delvis indexerade objekt i eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)