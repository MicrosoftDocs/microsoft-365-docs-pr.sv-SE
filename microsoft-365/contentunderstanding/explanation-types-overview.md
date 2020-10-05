---
title: Förklaringstyper
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350309"
---
# <a name="introduction-to-explanation-types"></a>Introduktion till förklaringstyper

Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex. När du skapar en förklaring måste du välja en förklaringstyp. I den här artikeln får du hjälp att lära dig mer för att bättre förstå olika förklaringstyper och hur de används. 

   ![Förklaringstyper](../media/content-understanding/explanation-types.png) 
   
Följande förklaringstyper är tillgängliga:

- **Fraslista**: lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar. Exempel: textsträngen **Hänvisande läkare** finns i alla medicinska referensdokument som du identifierar.</br>

- **Mönsterlista**: listar mönster med siffror, bokstäver eller andra tecken som du kan använda för att identifiera den information som du extraherar. Till exempel kan du extrahera den hänvisande läkarens **Telefonnumret** i alla medicinsk referensdokument som du identifierar.</br>

- **Närhet**: beskriver hur nära förklaringar är för varandra. Exempel: en mönsterlista för *gatunummer* ska ligga precis efter fraslistan för *gatunamn* utan tokens i mellan (du får lära dig mer om tokens senare i den här artikeln). Med närhetstypen måste du ha minst två förklaringar i modellen eller så är alternativet inaktiverat. 
 
## <a name="phrase-list"></a>Fraslista

Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen. Så som det beskrivs i exemplet med etikett för *Hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.

Även om det inte är obligatoriskt kan du få mer framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i ditt dokument. Till exempel kan etiketten *Hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.

Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.

   ![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Mönsterlistor

Typen mönsterlista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument. Den visas vanligtvis i olika format, till exempel datum, telefonnummer eller kreditkortsnummer. Ett datum kan till exempel visas i flera olika format (1/1 2020, 2020-01-01, 1 januari 2020 osv.). Genom att definiera en mönsterlista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera. 

För exemplet **Telefonnummer** extraheras telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar. När du skapar förklaringen väljer du typen mönsterlista för att tillåta de olika format som du kan förvänta dig returneras.

   ![Mönsterlista för telefonnummer](../media/content-understanding/pattern-list.png)

I det här exemplet väljer du kryssrutan **Valfri siffra från 0-9**. Att välja det här alternativet känner igen varje "0"-värde som används i mönsterlistan som valfri siffra mellan 0 och 9.

   ![Alla siffror från 0-9](../media/content-understanding/digit-identity.png)

Om du skapar en mönsterlista som innehåller texttecken markerar du kryssrutan **Valfri bokstav från a-ö**. Om du väljer det här alternativet tolkas alla "a"-tecken som används i mönsterlistan som valfritt tecken från "a" till "ö".

Om du till exempel skapar en mönsterlista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen måste du:
- Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din mönsterlista.
- Kontrollera att **Valfri bokstav från a-ö** också är markerad.

   ![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

Om du även har krav på stor begynnelsebokstav i din mönsterlista kan du välja kryssrutan **Endast exakta versaler**. Om du kräver att den första bokstaven i månaden för datumexemplet har stor begynnelsebokstav behöver du:

- Lägga till *0 Aaaaaaa 0000* och *00 Aaaaaaa 0000* i din mönsterlista.
- Kontrollera att **Endast exakta versaler** också är markerad.

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> I stället för att manuellt skapa en förklaring för mönsterlista kan du använda [förklaringsbiblioteket](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) för att använda färdiga mönsterlistmallar för vanliga mönsterlistor, till exempel *datum*, *telefonnummer*, *kreditkortsnummer*osv.. 

## <a name="proximity"></a>Närhet 

Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den. I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*. 

Du ser också att kundens telefonnummer alltid visas före gatunumret. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.

   ![Närhetsförklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Vad är tokens?

Om du vill använda närhetsförklaringstypen behöver du förstå vad en token är eftersom antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan.  

En token är ett sammanhängande intervall (inga blanksteg eller skiljetecken) för bokstäver och siffror. Ett blanksteg är INTE en token. Varje skiljetecken är en token. I tabellen nedan visas några exempel på hur du kan ta reda på antalet tokens i en fras.

|Fras|Antal tokens|Förklaring|
|--|--|--|
|`Dog`|1|Ett enstaka ord utan skiljetecken eller blanksteg.|
|`RMT33W`|1|Ett lokaliseringsnummer för posten. Det kan finnas siffror och bokstäver men inga skiljetecken.|
|`425-555-5555`|5|Ett telefonnummer. Varje skiljetecken är ett enda token, så  `425-555-5555` blir 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurera typen närhetsförklaring

Konfigurera inställningen närhet för urvalet så att vi kan definiera intervallet för antalet tokens som förklaringen för *telefonnummer* är från förklaringen *gatunummer*.

Du bör se att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.

För vissa telefonnummer i urvalsdokumenten läggs emellertid till *(mobil)*.

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

## <a name="use-explanation-templates"></a>Använda förklaringsmallar

Även om du kan lägga till olika mönsterlistvärden för dina förklaringar manuellt kan det vara mycket enklare att använda de färdiga mallar som har skapat år dig i förklaringsbiblioteket.

I stället för att manuellt lägga till alla variationer för *datum* kan du använda mönsterlistmallen för *datum*, som redan har ett antal mönsterlistvärden:</br>

   ![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)</br>
 
I förklaringsbiblioteket finns flera vanliga förklaringar för mönsterlistor, t. ex.:</br>

- Datum</br>
- Datum (numeriskt)</br>
- Tid</br>
- Siffra</br>
- Telefonnummer</br>
- Postnummer</br>
- Första ord i mening</br>
- Kontokort</br>
- Personnummer</br>

Observera att förklaringsbiblioteket även innehåller mallar för frasllistförklaringar, t. ex.:
- Slutet av meningen
- Valuta

#### <a name="to-use-a-template-from-the-explanation-library"></a>Använda en mall från förklaringsbiblioteket

1. Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</br>

   ![Skapa från mall](../media/content-understanding/from-template.png)</br>

2.  På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. Informationen för den mall som du valde visas på sidan **Skapa en förklaring**. Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från mönsterlistan. </br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. Klicka på **Spara** när du är klar.
