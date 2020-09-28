---
title: Förklaringar
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Läs mer om förklarings typer i Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296218"
---
# <a name="introduction-to-explanation-types"></a>Introduktion till förklarings typer

Använd förklaringar för att definiera informationen som du vill lägga till och extrahera i dokumentet förstå modellerna för Microsoft SharePoint Syntex. När du skapar en förklaring bör du välja en typ av förklaring. 

Den här artikeln hjälper dig att förstå olika typer av förklaringar och hur de används.

   ![Förklaringar](../media/content-understanding/explanation-types.png) 
   
Följande förklaringar är tillgängliga:

- **Fras lista**: lista över ord, fraser, tal eller andra tecken som du kan använda i dokumentet eller informationen som du extraherar. Text strängen som **refererar till läkare** är till exempel i alla medicinska hänvisnings dokument som du identifierar.</br>

- **Mönster lista**: lista med tecken mönster med siffror, bokstäver eller andra specialtecken som du kan använda för att identifiera informationen som du extraherar. Du kan till exempel extrahera **telefonnumret** från det dokument för medicinsk hänvisning som du identifierar.</br>

- **Närhet**: beskriver hur nära förklaringar är till varandra. Till exempel kan en lista med *gatu nummer* mönster placeras direkt före *gatu namns* frasen, med inga tokens mellan (du lär dig mer om tokens längre fram i den här artikeln). 
 
## <a name="phrase-list"></a>Fras lista

En förklarings typ för en fras lista används vanligt vis för att identifiera och klassificera ett dokument genom modellen. Enligt beskrivningen i exemplet *hänvisar* till exempel är det en sträng med ord, fraser, tal eller tecken som är konsekvent i de dokument som du identifierar.

Men inte ett krav kan du få bättre framgång med din förklaring om den fras du hämtar finns på en konsekvent plats i dokumentet. Etiketten för den *refererande läkaren* kan till exempel finnas konsekvent i det första stycket i dokumentet.

Om SKIFT läges känslighet är ett krav för att identifiera din etikett kan du använda fras listans typ för att ange den i din förklaring genom att markera kryss rutan **endast exakta versaler** .

   ![Skift läges känslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Mönster listor

En typ av en mönster lista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument. Det visas normalt i olika format, till exempel datum, telefonnummer eller kreditkorts nummer. Ett datum kan till exempel visas i ett antal olika format (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020 osv.). Om du definierar en mönster lista blir din förklaring mer effektiv genom att fånga eventuella variationer i de data som du försöker identifiera och extrahera. 

Extrahera **telefonnumret** för varje referent från alla dokument för medicinsk hänvisning som identifieras av modellen. När du skapar en förklaring väljer du typen av mönster lista för att tillåta de olika format som du kan förvänta dig att returneras.

   ![Telefon nummer mönster lista](../media/content-understanding/pattern-list.png)

För det här exemplet markerar du kryss rutan **valfri siffra från 0-9** . Om du väljer det här alternativet tolkas varje "0"-värde som används i din mönster lista som valfri siffra mellan 0 och 9.

   ![Valfri siffra från 0-9](../media/content-understanding/digit-identity.png)

Om du skapar en mönster lista som innehåller text tecken markerar du rutan **valfri bokstav från en-z** . Om du väljer det här alternativet tolkas varje "a"-tecken som används i listan mönster som ett tecken från "a" till "z".

Om du till exempel skapar en **datum** mönster lista och vill vara säker på att ett datum format som *1 januari 2020* känns igen, måste du:
- Lägg till *AAA 0, 0000* och *AAA 00, 0000* i din mönster lista.
- Se till att **alla bokstäver från a-z** också är markerade.

   ![Valfri bokstav från a-z](../media/content-understanding/any-letter.png)

Om du har behov av villkor i din Pattern-lista kan du välja att markera kryss rutan **endast exakta versaler** . Om du behöver den första bokstaven i månaden för att ange ett datum-exempel måste du göra följande:

- Lägg till *AAA 0, 0000* och *AAA 00, 0000* i din mönster lista.
- Kontrol lera att **endast exakta Skift läge** är markerat.

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> I stället för att manuellt skapa mönster listans förklaring kan du använda [förklaringen]() för att använda mallarna för färdiga mönster listor för vanliga mönster listor, till exempel *datum*, *telefonnummer*, *kreditkorts nummer*etc.. 

## <a name="proximity"></a>Närhet 

Med hjälp av den här typen av förklaringar kan modellen identifiera data genom att definiera hur nära en annan del av data ska vara. I din modell har du till exempel två förklaringar som Märk både kundens *gatuadress* och *telefonnummer*. 

Du märker också att kundernas telefonnummer alltid visas före gatuadress. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Använd närhets förklaringen för att definiera hur långt bort det aktuella telefonnumret är för att bättre identifiera gatuadressen i dina dokument.

   ![Närhets förklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Vad är tokens?

För att använda funktionen för närhets förklaringar kan du förstå vad en token är, eftersom antalet tokens är hur avståndet mellan två förklaringar mäter avstånd från en förklaring till en annan.  

Ett token är ett sammanhängande intervall (inga blank steg eller skiljetecken) av bokstäver och siffror. Ett blank steg är inte ett token. Varje skiljetecken är ett token. Följande tabell visar några exempel på hur du kan avgöra antalet tokens i en fras.

|Verbfras|Antal token|Förklaring|
|--|--|--|
|`Dog`|9.1|Ett enstaka ord utan skiljetecken eller blank steg.|
|`RMT33W`|9.1|Ett post nummer. Den kan ha siffror och bokstäver, men har inte skiljetecken.|
|`425-555-5555`|T5|Ett telefonnummer. Varje skiljetecken är en enda token så  `425-555-5555` att den blir 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|borttagning|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurera typ av en närhet

För det här exemplet ska du konfigurera inställningen för närhet så att vi kan definiera intervallet för antalet *tokens som kundens förklaring är* från rikt *nummer* förklaringen.

Du bör se att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatuadressen.

Men vissa telefonnummer i exempel dokumenten läggs till med *(mobil)*.

Nestor Wilke<br>
111-111-1111 (mobil)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Det finns tre tokens i *(mobil)*:

|Verbfras|Antal token|
|--|--|
|(|9.1|
|mobilvy|två|
|)|amp;3D|

Konfigurera inställningen för närhet till att ha ett område på mellan 0 och 3.

   ![Exempel på närhet](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>Använda förklarings biblioteket

Du kan lägga till olika värden för dina förklaringar manuellt, det är mycket enklare att använda de färdiga mallarna som finns i förklarings biblioteket.

I stället för att lägga till alla variationer för *datum*kan du använda mallen mönster lista för *datum*, som redan innehåller ett antal mönster listor:</br>

   ![Förklarings bibliotek](../media/content-understanding/explanation-template.png)</br>
 
I förklarings biblioteket finns många förklaringar som ofta används, bland annat:</br>

- Datum</br>
- Datum (numeriskt)</br>
- Tider</br>
- Tal</br>
- Telefonnummer</br>
- Postnummer</br>
- Första ord med mening</br>
- Kredit kort</br>
- Person nummer</br>

Observera att förklarings biblioteket också innehåller mallar för förklarings listor, inklusive:
- Slutet av meningen
- Valuta

#### <a name="to-use-a-template-from-the-explanation-library"></a>Så här använder du en mall från förklarings biblioteket

1. Välj **nytt**i avsnittet **förklaringar** på modellens **tåg** sida och välj sedan **från en mall**.</br>

   ![Skapa från mall](../media/content-understanding/from-template.png)</br>

2.  På sidan **förklaringar** väljer du den förklaring du vill använda och väljer sedan **Lägg till**.</br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. Informationen för den mall som du valde visas på sidan **skapa en förklaring** . Om det behövs redigerar du förklarings namnet och lägger till eller tar bort objekt från listan med mönster. </br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. När du är klar väljer du **Spara**.
