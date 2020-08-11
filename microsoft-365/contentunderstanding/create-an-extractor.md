---
title: Skapa en Extractor (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du skapar en Extractor
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612768"
---
# <a name="create-an-extractor-preview"></a>Skapa en Extractor (för hands version)
> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Antingen förut eller efter att du har skapat en klassificerings modell för att automatisera identifiering och klassificering av specifika dokument typer kan du välja att lägga till utdrag i din modell för att hämta specifik information från dessa dokument. Du kanske till exempel vill använda modellen för att identifiera alla *förnyelse* dokument som läggs till i dokument biblioteket, men om du även vill visa *tjänstens start datum* för varje dokument som en kolumn i dokument biblioteket.

Du måste skapa en Extractor för varje enhet i dokumentet som du vill extrahera. I vårt exempel vill vi extrahera *tjänstens start datum* för varje *kontrakt förnyelse* dokument som identifieras av modellen. Vi vill kunna se en vy i dokument biblioteket för alla *förnyelse* dokument med en kolumn som visar värdet för tjänste start datum för varje dokument.

> [!Note]
> Innan du skapar en Extractor måste du [lägga till dina exempel filer](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) du måste hjälpa till att träna modellen för att identifiera informationen som du vill extrahera. Använd samma exempel filer som du använde när du skapade klassificeraren.


## <a name="name-your-extractor"></a>Ge din Extractor ett namn

1. Klicka på **träna Extractor**på panelen **skapa och träna extrakt** på modell start sidan.
2. På sidan **ny enhets Extractor** skriver du namnet på din Extractor i fältet **ny Extractor-namn** . Vi kan till exempel ge **Start datumet** för den tjänsten om vi vill extrahera tjänstens start datum från varje kontrakt förnyelse dokument.
3. Klicka på **Skapa**.

## <a name="add-a-label"></a>Lägga till en etikett

Nästa steg är att lägga till etiketter för den information som du vill ta fram i exempel utbildnings filerna.

När du skapar Extractor öppnas sidan Extractor där du ser en lista över dina exempelfiler, med den första filen i listan som visas i visnings programmet.

1. Markera de data som du vill extrahera från filerna i visnings programmet. Om du till exempel vill extrahera *Start tjänst datum*markerar du datumvärdet för det i den första filen (*måndag den 14 oktober 2019*). Klicka sedan på **Spara**.  Du ser värde visningen för filen i listan med namngivna exempel under kolumnen **etikett** .
2. Välj **nästa fil** för att spara automatiskt och öppna nästa fil i listan i visnings programmet, eller så kan du välja **Spara** och välja en annan fil i listan med **Etiketter** .
3. Upprepa steg 1 och 2 i visnings programmet tills du har sparat etiketten i fem filer.

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Lägga till ett negativt exempel

På samma sätt som när du lägger till en negativ exempel fil när du skapar en klassificerare måste du lägga till ett negativt exempel för Extractor. I vårt exempel ska det vara en fil som inte innehåller ett start datum värde.

1. Välj ett negativt exempel i listan med **Etiketter** .
2. Välj **ingen etikett tillgänglig**längst upp i artikeln i visnings programmet.
3. Klicka på **Spara**.
 
När du har märkt fem filer visas en meddelande banderoll som informerar dig om att flytta till utbildning. Du kan välja fler dokument eller gå vidare till utbildning. 

## <a name="add-an-explanation"></a>Lägga till en förklaring

I vårt exempel håller vi på att skapa en förklaring om själva enhets formatet och variationer den kan ha i exemplen. Ett datum värde kan till exempel vara i ett antal olika format, som:
- 10/14/2019
- 14 oktober 2019
- Måndagen den 14 oktober 2019
 

För att identifiera *tjänstens start datum* kan du skapa en mönster förklaring.

1. I avsnittet förklaring väljer du **nytt**och skriver sedan ett namn (till exempel *datum*).
2. Välj **mönster lista**för typen.
3. För värdet måste du ange datum variationen så som de visas i exempelfilerna. Om du till exempel har datum format som visas som 0/00/0000, anger du eventuella variationer som kan visas i dina dokument, som:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Välj **Spara**.


### <a name="use-the-explanation-library"></a>Använda förklarings biblioteket

När du skapar förklaringar för till exempel datum, är det mycket lättare att använda förklarings biblioteket än att manuellt ange alla variationer. Förklarings biblioteket är en uppsättning fördefinierade fraser och mönster förklaringar. Biblioteket försöker tillhandahålla alla format för vanliga fras-och mönster listor, till exempel datum, telefonnummer, post nummer och många andra. 

För vårt *start datum-* exempel är det mer effektivt att använda den färdiga förklaringen för *datum* i förklarings biblioteket:

1. I **avsnittet förklaring*** * väljer du **nytt**och väljer sedan **från förklarings bibliotek**.
2. Välj **datum**i förklarings biblioteket. Du kan visa alla datum variationer som kommer att kännas igen.
3. Välj **Lägg till**.</br>

    ![Förklarings bibliotek](../media/content-understanding/explanation-library.png) 

4. På sidan **skapa en förklaring** fylls *datum* informationen från i förklarings biblioteket i automatiskt. Välj **Spara**.</br>

    ![Förklarings bibliotek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Träna modellen 

Om du sparar din förklaring kan du börja öva. Om din modell har tillräckligt med information för att extrahera data från dina namngivna exempelfiler visas varje fil med etiketten **matcha**.  

![Förklarings bibliotek](../media/content-understanding/match2.png) 

Om förklaringen inte innehåller tillräckligt med information för att hitta de data som du vill extrahera är varje fil märkt med **fel**. Du kan klicka på de felmatchade filerna för att se mer information om varför det fanns ett fel.


## <a name="add-another-explanation"></a>Lägga till en förklaring

Ofta beror det på att den förklaring som vi tillhandahöll inte gav tillräckligt med information för att extrahera tjänstens start datum för att matcha våra etiketterade filer. Du kan behöva redigera den eller lägga till en annan förklaring.

I vårt exempel noterar vi att text strängens *start datum* alltid föregår det faktiska värdet. För att identifiera start datumet för tjänsten kan vi skapa en menings förklaring.

1. I avsnittet förklaring väljer du **nytt**och anger sedan ett namn (till exempel en *prefixlängd*).
2. Välj **fras lista**för typen.
3. Använd *tjänstens start datum* som värde.
4. Välj **Spara**.

    ![Förklarings bibliotek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Träna modellen

Om du sparar din förklaring börjar utbildningen igen, den här gången med hjälp av båda förklaringarna i vårt exempel. Om din modell har tillräckligt med information för att extrahera data från dina namngivna exempelfiler visas varje fil med etiketten **matcha**. 

Om du får ett fel meddelande om att dina etiketter **inte stämmer** överens kan du behöva skapa en ny förklaring för att ge modellen mer information för att identifiera dokument typen eller se hur du ändrar dina befintliga.

## <a name="test-your-model"></a>Testa modellen

Om du har fått en matchning på dina etiketterade exempelfiler kan du testa modellen på dina återstående ljudfiler.

1. Klicka på fliken **testa** på modell start sidan.  Då körs modellen på dina namnlösa exempelfiler.
2. I listan **testfiler** visas dina exempel filer och visar om modellen kan extrahera den information du behöver. Du kan använda den här informationen för att avgöra hur din klassificerarens effektivitet är för att identifiera dina dokument.

    ![Testa dina filer](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Se även
  




