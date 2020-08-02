---
title: Skapa en utsupre (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du skapar en utsugsor
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540112"
---
# <a name="create-an-extractor-preview"></a>Skapa en utsupre (förhandsgranskning)
> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Antingen före eller efter att du har skapat en klassifierarmodell för att automatisera identifiering och klassificering av specifika dokumenttyper kan du också välja att lägga till utdrag till modellen för att hämta specifik information från dessa dokument. Du kanske till exempel vill att modellen inte bara ska identifiera alla dokument för *kontraktsförnyelse* som läggs till i dokumentbiblioteket, utan även visa *startdatumet* för tjänsten för varje dokument som en kolumn i dokumentbiblioteket.

Du måste skapa en utsutorn för varje entitet i dokumentet som du vill extrahera. I vårt exempel vill vi extrahera *tjänstens startdatum* för varje *kontraktsförnyelsedokument* som identifieras av modellen. Vi vill kunna se en vy i dokumentbiblioteket för alla dokument *för kontraktsförnyelse,* med en kolumn som visar värdet för tjänstens startdatum för varje dokument.

> [!Note]
> Innan du skapar en extractor måste du lägga till [dina exempelfiler](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) måste du hjälpa till att träna modellen för att identifiera den information du vill extrahera. Använd samma exempelfiler som du använde för att skapa klassificeraren.


## <a name="name-your-extractor"></a>Namnge din utsug

1. Klicka på **Tågutsugor**i panelen **Skapa och träna utsug** på startsidan.
2. På skärmen **Ny entitetsutextör** skriver du namnet på extraheraren i fältet **Nytt utdragsnamn.** Vi kan till exempel namnge det **Tjänstens startdatum** om vi vill extrahera tjänstens startdatum från varje dokument för kontraktsförnyelse.
3. Klicka på **Skapa**.

## <a name="add-a-label"></a>Lägga till en etikett

Nästa steg är att märka den information som du vill extrahera i dina exempel träningsfiler.

Om du skapar utdragsbladet öppnas utsugssidan där du ser en lista över dina exempelfiler, med den första filen i listan som visas i visningsprogrammet.

1. Markera de data som du vill extrahera från filerna i visningsprogrammet. Om du till exempel vill extrahera *starttjänstdatumet*markerar du datumvärdet för det i den första filen (*måndag 14 oktober 2019*). Klicka sedan på **Spara**.  Du ser värdevisningen för filen i listan Märkta exempel under kolumnen **Etikett.**
2. Välj **Nästa fil** om du vill spara automatiskt och öppna nästa fil i listan i visningsprogrammet, eller så kan du välja **Spara** och välja en annan fil i listan **Märkta exempel.**
3. Upprepa steg 1 och 2 i visningsprogrammet och gör detta tills du har sparat etiketten i fem filer.

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Lägga till ett negativt exempel

På samma sätt som du vill lägga till en negativ exempelfil när du skapar en klassificerare måste du lägga till ett negativt exempel för utsugaren. Det bör till exempel vara en fil som inte innehåller ett startdatum för tjänsten.

1. Välj ett negativt exempel i listan **Märkta exempel.**
2. Välj **Ingen etikett på**artikelns överkant i visningsprogrammet .
3. Klicka på **Spara**.
 
När du har märkt fem filer visas en meddelandebanderoll där du informerar dig om att gå över till träningen. Du kan välja att fler dokument eller gå vidare till utbildning. 

## <a name="add-an-explanation"></a>Lägga till en förklaring

Vi kommer till exempel att skapa en förklaring som ger en ledtråd om själva enhetsformatet och variationer som den kan ha i exempeldokumenten. Ett datumvärde kan till exempel finnas i ett antal olika format, till exempel:
- 10/14/2019
- den 14 oktober 2019
- måndagen den 14:e oktober 2019
 

För att identifiera *tjänstens startdatum* kan du skapa en mönsterförklaring.

1. I avsnittet Förklaring väljer du **Nytt**och skriver sedan ett namn (till exempel *Datum*).
2. För listan Typ väljer du **Mönsterlista**.
3. För värdet måste du ange datumvariationen så som de visas i exempelfilerna. Om du till exempel har datumformat som visas som 0000-00-00 kan du ange alla variationer som kan visas i dina dokument, till exempel:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Välj **Spara**.


### <a name="use-the-explanation-library"></a>Använda förklaringsbiblioteket

För att skapa förklaringar till saker som datum är det mycket enklare att använda förklaringsbiblioteket än att manuellt ange alla varianter. Förklaringsbiblioteket är en uppsättning färdiga fras- och mönsterförklaringar. Biblioteket försöker ange alla format för vanliga fras- eller mönsterlistor, till exempel datum, telefonnummer, postnummer och många andra. 

För vårt exempel *på tjänstens startdatum* är det mer effektivt att använda den färdiga förklaringen till *Datum* i förklaringsbiblioteket:

1. Välj **Nytt**i **avsnittet Förklaring**och välj sedan **Från förklaringsbiblioteket**.
2. Välj **Datum**i förklaringsbiblioteket . Du kan visa alla ändringar av datum som ska identifieras.
3. Välj **Lägg till**.</br>

    ![Förklaringsbibliotek](../media/content-understanding/explanation-library.png) 

4. På sidan **Skapa en förklaring** fylls fälten i *datuminformationen* från förklaringsbiblioteket. Välj **Spara**.</br>

    ![Förklaringsbibliotek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Träna modellen 

Spara din förklaring kommer att starta utbildningen. Om modellen har tillräckligt med information för att extrahera data från de märkta exempelfilerna visas varje fil med **matcha**.  

![Förklaringsbibliotek](../media/content-understanding/match2.png) 

Om förklaringen inte har tillräckligt med information för att hitta de data du vill extrahera, kommer varje fil att märkas med **Felmatchning**. Du kan klicka på filerna som inte stämmer överens för att se mer information om varför det fanns en obalans.


## <a name="add-another-explanation"></a>Lägg till en annan förklaring

Ofta är obalansen en indikation på att förklaringen vi gav inte gav tillräckligt med information för att extrahera tjänstens startdatumvärde för att matcha våra märkta filer. Du kan behöva redigera den eller lägga till en annan förklaring.

Vi märker till exempel att textsträngen *Startservicedatum* för alltid föregår det faktiska värdet. För att identifiera tjänstens startdatum kan vi skapa en frasförklaring.

1. I avsnittet Förklaring väljer du **Nytt**och skriver sedan ett namn (till exempel *Prefixsträng*).
2. För text väljer du **Fraslista**.
3. Använd *Tjänstens startdatum* för som värde.
4. Välj **Spara**.

    ![Förklaringsbibliotek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Träna modellen

Spara din förklaring kommer att starta utbildningen igen, denna gång med hjälp av båda förklaringarna i vårt exempel. Om modellen har tillräckligt med information för att extrahera data från de märkta exempelfilerna visas varje fil med **matcha**. 

Om du återigen får en **felmatchning** på dina märkta filer kan du behöva skapa en annan förklaring för att ge modellen mer information för att identifiera dokumenttypen eller titta på att göra ändringar i dina befintliga.

## <a name="test-your-model"></a>Testa din modell

Om du har fått en matchning på dina märkta exempelfiler kan du nu testa modellen på de återstående omärkta exempelfilerna.

1. Klicka på fliken **Testa** på modellens startsida.  Då körs modellen på de omärkta exempelfilerna.
2. I listan **Testa filer** visas dina exempelfiler och visar om modellen kan extrahera den information du behöver från dem. Du kan använda den här informationen för att avgöra hur effektiv klassificeraren är när det gäller att identifiera dina dokument.

    ![Testa på dina filer](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Se även
  




