---
title: Förklaringstyper
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex
ms.openlocfilehash: b34de9ffc565e3d1a17cac05084e4e4b4113a3c6
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994634"
---
# <a name="introduction-to-explanation-types"></a>Introduktion till förklaringstyper

Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex. När du skapar en förklaring måste du välja en förklaringstyp. Den här artikeln hjälper dig förstå olika förklaringstyper och hur de används. 

   ![Förklaringstyper](../media/content-understanding/explanation-types.png) 
   
Följande förklaringstyper är tillgängliga:

- **Fraslista**: lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar. Exempel: textsträngen **Hänvisande läkare** finns i alla medicinska referensdokument som du identifierar.</br>

- **Mönsterlista**: listar mönster med siffror, bokstäver eller andra tecken som du kan använda för att identifiera den information som du extraherar. Till exempel kan du extrahera den hänvisande läkarens **Telefonnumret** i alla medicinsk referensdokument som du identifierar.</br>

- **Närhet**: beskriver hur nära förklaringar är för varandra. Exempel: en mönsterlista för *gatunummer* ska ligga precis efter fraslistan för *gatunamn* utan tokens i mellan (du får lära dig mer om tokens senare i den här artikeln). Med närhetstypen måste du ha minst två förklaringar i modellen, annars är alternativet inaktiverat. 
 
## <a name="phrase-list"></a>Fraslista

Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen. Så som det beskrivs i exemplet med etikett för *Hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.

Även om det inte är obligatoriskt kan du få mer framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i ditt dokument. Till exempel kan etiketten *Hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.

Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.

   ![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Mönsterlistor

Typen mönsterlista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument. Den visas vanligtvis i olika format, till exempel datum, telefonnummer och kreditkortsnummer. Ett datum kan till exempel visas i flera olika format (1/1 2020, 2020-01-01, 1 januari 2020 osv.). Genom att definiera en mönsterlista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera. 

För exemplet **Telefonnummer** extraheras telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar. När du skapar förklaringen väljer du typen mönsterlista för att tillåta de olika format som du kan förvänta dig returneras.

   ![Mönsterlista för telefonnummer](../media/content-understanding/pattern-list.png)

I det här exemplet väljer du kryssrutan **Alla siffror mellan 0-9** för att känna igen alla "0"-värden som används i mönsterlistan som alla siffror mellan 0 och 9.

   ![Alla siffror mellan 0-9](../media/content-understanding/digit-identity.png)

Om du på liknande sätt skapar en mönsterlista som innehåller texttecken markerar du kryssrutan **Alla bokstäver mellan a-ö** för att känna igen alla "a"-tecken som används i mönsterlistan som alla tecken mellan "a" till "ö".

Om du till exempel skapar en mönsterlista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen måste du:
- Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din mönsterlista.
- Kontrollera att **Valfri bokstav från a-ö** också är markerad.

   ![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

Om du även har krav på stor begynnelsebokstav i din mönsterlista kan du välja kryssrutan **Endast exakta versaler**. Om du kräver att den första bokstaven i månaden för datumexemplet har stor begynnelsebokstav behöver du:

- Lägga till *0 Aaaaaaa 0000* och *00 Aaaaaaa 0000* i din mönsterlista.
- Kontrollera att **Endast exakta versaler** också är markerad.

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> I stället för att manuellt skapa en förklaring för en mönsterlista kan du använda [förklaringsbiblioteket](#use-explanation-templates) för att använda färdiga mönsterlistmallar för vanliga mönsterlistor, till exempel *datum*, *telefonnummer*, *kreditkortsnummer* osv.

## <a name="proximity"></a>Närhet 

Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den. I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*. 

Notera att kundens telefonnummer alltid visas före gatunumret. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.

   ![Närhetsförklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Vad är tokens?

Om du vill använda närhetsförklaringstypen behöver du förstå vad en token är eftersom antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan. En token är ett sammanhängande intervall (exklusive blanksteg eller skiljetecken) för bokstäver och siffror. 

I tabellen nedan visas exempel på hur du kan ta reda på antalet tokens i en fras.

|Fras|Antal tokens|Förklaring|
|--|--|--|
|`Dog`|1|Ett enstaka ord utan skiljetecken eller blanksteg.|
|`RMT33W`|1|Ett lokaliseringsnummer för posten. Det kan innehålla siffror och bokstäver men inga skiljetecken.|
|`425-555-5555`|5|Ett telefonnummer. Varje skiljetecken är ett enda token, så `425-555-5555` är 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurera typen närhetsförklaring

Konfigurera inställningen närhet för detta exempel att definiera intervallet för antalet tokens i förklaringen för *Telefonnummer* från förklaringen *Gatunummer*. Notera att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.

Men vissa telefonnummer i urvalsdokumenten har tillägget *(mobil)*.

Viktor Magnusson<br>
111-111-1111 (mobil)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Det finns tre tokens i *(mobil)*:

|Fras|Antal tokens|
|--|--|
|(|1|
|mobil|2|
|)|3|

Konfigurera inställningen för närhet så att den har ett område med 0 till 3.

   ![Exempel på närhet](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a>Konfigurera var fraser förekommer i dokumentet

När du skapar en förklaring söks som standard hela dokumentet efter frasen du försöker extrahera. Du kan dock använda inställningen <b>Där fraserna förekommer</b> avancerade inställning för att hjälpa till att isolera en specifik plats i dokumentet som en fras förekommer på. Detta är användbart i situationer där liknande förekomster av en fras kan förekomma någon annanstans i dokumentet, och du vill kontrollera att rätt förekomst är markerad. Med hänvisning till vårt exempel på medicinsk remiss nämns alltid den **hänvisande läkaren** i första stycket i dokumentet. Med inställningen <b>Var dessa fraser förekommer</b> kan du i det här exemplet konfigurera förklaringen så att den bara söker efter den här etiketten i början av dokumentet eller någon annan plats där den kan förekomma.

   ![Var dessa fraser förekommer inställning](../media/content-understanding/phrase-location.png)</br>

Du kan välja följande alternativ för den här inställningen:

- Var som helst i filen: Hela dokumentet söks efter frasen.
- Början av filen: Dokumentet genomsöks från början till frasen plats.</br> 
   ![Början på filen](../media/content-understanding/beginning-of-file.png)</br>
I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar. Den <b>slutpositionens</b> värde uppdateras för att visa antalet tokens som ditt valda område innehåller. Observera att du också kan uppdatera slutpositionsvärdet för att justera det valda området.</br>
   ![Början på filens positionsruta](../media/content-understanding/beginning-box.png)</br>

- Slut av filen: Dokumentet genomsöks från slutet till frasens plats.</br> 
   ![Slutet av filen](../media/content-understanding/end-of-file.png)</br>
I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar. Värdet <b>startposition</b> uppdateras för att visa antalet tokens som ditt valda område innehåller. Observera att du också kan uppdatera startpositionens värde för att justera det markerade området.</br> 
   ![Slutet på filens slutruta](../media/content-understanding/end-box.png)</br>
- Anpassat intervall: Dokumentet genomsöks inom ett angivet intervall inom det för frasplatsen.</br> 
   ![Anpassat intervall](../media/content-understanding/custom-file.png)</br>
I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar. För den här inställningen måste du välja en <b>start</b>- och en <b>slut</b>position. De här värdena representerar antalet tokens från början av dokumentet. Även om du kan ange dessa värden manuellt är det enklare att justera urvalsrutan i visningsprogrammet manuellt.</br> 
   
## <a name="use-explanation-templates"></a>Använda förklaringsmallar

Medan du manuellt kan lägga till olika fraslistvärden för din förklaring kan det vara lättare att använda mallarna som du har fått i förklaringsbiblioteket.

Till exempel, istället för att manuellt lägga till alla variationer för *Datum*, kan du använda fraslistmallen för *Datum* eftersom den redan innehåller ett antal värden för fraslistor:</br>

   ![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)</br>
 
I förklaringsbiblioteket finns flera vanliga förklaringar för mönsterlistor, till exempel:</br>

- Datum: kalenderdatum, alla format. Innehåller text och tal (till exempel "9 dec 2020").</br>
- Datum (numeriskt): kalenderdatum, alla format. Inkluderar tal (till exempel 1-11-2020).</br>
- Tid: 12- och 24-timmarsformat.</br>
- Tal: positiva och negativa tal upp till 2 decimaler. </br>
- Procent: en lista över mönster som representerar en procentsats. Till exempel: 1%, 11%, 100%, 11.11%, osv.</br>
- Telefonnummer: Vanliga amerikanska och internationella format. Till exempel: 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, osv.</br>
- Postnummer: amerikanska postnummerformat. Till exempel: 11111, 11111-1111.</br>
- Första ordet i meningen: vanliga mönster för ord upp till 9 tecken. </br>
- Slutet av mening: vanligt skiljetecken för slutet av en mening</br>
- Kreditkort: vanliga talformat för kreditkort. Till exempel: 1111-1111-1111-1111. </br>
- Personnummer: US personnummer-format. Till exempel: 111-11-1111. </br>
- Kryssruta: en fraslista som representerar variationer på en ifylld kryssruta. Till exempel _X_, _ _X_ osv.</br>
- Valuta: vanligaste internationella symboler. Exempel: $. </br>
- Kopia i e-post: en fraslista med termen "CC:" som ofta finns nära namnen eller e-postadresserna till ytterligare personer eller grupper som meddelandet skickades till.</br>
- E-postdatum: en fraslista med termen "Skickat den:" förekommer ofta nära det datum då meddelandet skickades.</br>
- E-posthälsning: vanliga inledande rader för e-postmeddelanden.</br>
- E-postmottagare: en fraslista med termen "Till:" som ofta finns nära namnen eller e-postadresserna till personer eller grupper som meddelandet skickades till. </br>
- E-postavsändare: en fraslista med termen "Från:" förekommer ofta nära avsändarens namn eller e-postadress. </br>
- Ämne för e-post: en fraslista med termen "Ämne:" som ofta finns nära e-postmeddelandets ämne. </br>

I förklaringsbiblioteket finns också tre automatiska malltyper som fungerar med de data som du har märkt i exempelfilerna:

- Efter etikett: De ord eller tecken som förekommer efter etiketterna i exempelfilerna.</br>
- Före etikett: De ord eller tecken som förekommer före etiketterna i exempelfilerna.</br>
- Etiketter: Upp till de första 10 etiketterna från exempelfilerna.</br>

Om du vill ge dig ett exempel på hur automatiska mallar fungerar, i följande exempelfil, kommer vi att använda förklaringsmallen före etikett för att ge modellen mer information för att få en mer exakt matchning.

   ![Exempelfil](../media/content-understanding/before-label.png)</br>

När du väljer mallen Före etikettförklaring letar den efter den första uppsättningen ord som visas före etiketten i dina exempelfiler. I exemplet är orden som identifierats i den första exempelfilen "Från och med".

   ![Före etikettmall](../media/content-understanding/before-label-explanation.png)</br>

Du kan välja <b>Lägg</b> om du vill skapa en förklaring från mallen.  När du lägger till fler exempelfiler identifieras och läggs ytterligare ord till i fraslistan.

   ![Lägga till etiketten](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a>Använda en mall från förklaringsbiblioteket

1. Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</br>

   ![Lägg till före etikett](../media/content-understanding/from-template.png)</br>

2.  På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. Informationen för den mall som du valde visas på sidan **Skapa en förklaring**. Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från fraslistan. </br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. Klicka på **Spara** när du är klar.