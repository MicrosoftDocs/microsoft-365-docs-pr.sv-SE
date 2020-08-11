---
title: Skapa en klassificerare (för hands version)
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
description: Lär dig hur du skapar en klassificerare
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612614"
---
# <a name="create-a-classifier-preview"></a>Skapa en klassificerare (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

En klassificerare är en typ av modell som används för att automatisera identifiering och klassificering av en dokument typ. Du kanske till exempel vill identifiera alla *förlängnings* dokument som läggs till i ditt dokument bibliotek, som följande.

![Förnyelse dokument för kontrakt](../media/content-understanding/contract-renewal.png)

Om du skapar en klassificerare skapas en ny [SharePoint-innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som associeras med modellen.

När du skapar en klassificerare måste du skapa *förklaringar* som hjälper dig att definiera modellen genom att ange vanliga data som du förväntar dig hitta konsekvent för den här dokument typen. 

Du använder exempel på dokument typen ("exempel filer") för att "träna" din modell för att identifiera filer som har samma innehålls typ.

Om du vill skapa en klassificerare måste du:
1. Namnge modellen
2. Lägga till exempel filer
3. Namnge dina exempel filer
4. Skapa en förklaring
5. Testa modellen 

> [!Note]
> När en klassificerare används av modellen för att identifiera och klassificera dokument typer kan du också välja att hämta specifika informations delar från varje fil som identifieras av modellen. Det gör du genom att skapa en **Extractor** för att lägga till i din modell, så beskrivs i [skapa en Extractor](create-an-extractor.md).

## <a name="name-your-model"></a>Namnge modellen

Det första steget är att skapa en modell i innehålls Center genom att ge den ett namn:

1. I innehålls centret klickar du på **ny**och sedan på **skapa en modell**.
2. Skriv namnet på modellen i fältet **namn** i **modell fönstret nytt dokument** Om vi till exempel vill identifiera förlängnings handlingar för kontrakt kan vi ge dig ett namn på *förnyelse*av den här modellen.
3. Klicka på **Skapa**. Detta skapar en start sida för modellen.</br>

    ![Start sidan för klassificerings modell](../media/content-understanding/model-home.png)

När du skapar en modell skapar du en ny SharePoint-innehållstyp. En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet. SharePoint-innehålls typer hanteras via [galleriet innehålls typer](). I vårt exempel kommer vi att skapa en ny innehålls typ för *kontrakt förnyelse* när vi skapar modellen.

Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema. Observera att när du kan använda en befintlig innehålls typ för att påverka dess schema för att hjälpa till med identifiering och klassificering måste du ändå träna din modell att extrahera information från filer som identifieras.</br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Lägga till exempel filer

På Start sidan för modeller kan du lägga till exempel filer som du måste hjälpa till att träna modellen för att identifiera din dokument typ. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Samma filer bör användas både för klassificerings-och [Extractor-utbildning](create-an-extractor.md). Du kan alltid lägga till mer senare, men normalt bör du lägga till en fullständig uppsättning exempel filer. Du kommer att märka en del för att träna modellen och testa resten av dem för att utvärdera modellens användbarhet. 

För din utbildning är det bara att använda både positiva och negativa exempel:
- Positivt exempel: dokument som representerar dokument typen. De innehåller strängar och information som alltid ska vara med i den här typen av dokument.
- Negativt exempel: dokument som inte representerar dokument typen.  De innehåller strängar och information som måste finnas med i den här typen av dokument.

Du ska använda minst fem positiva exempel och ett negativt exempel för att träna modellen.  Du vill att ytterligare testa modellen efter utbildning.

Så här lägger du till exempelfiler:

1. Klicka på **Lägg till filer**i panelen **Skapa exempel bibliotek** på modell start sidan.
2. På sidan **Välj exempel filer för modellen** väljer du dina exempel filer från biblioteket för exempelfilerna i innehålls centret. Om du inte redan har laddat upp dem där kan du välja att överföra dem nu genom att klicka på **Ladda upp** för att flytta dem till exempel fil biblioteket.
3. När du har valt exempel-filerna som ska användas för att träna modellen klickar du på **Lägg till**.

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Namnge dina exempel filer

När du har lagt till dina exempelfiler måste du märka dem som antingen positiva exempel eller negativa exempel.

1. På modell start sidan klickar du på **träna** **filer och kör utbildning** .
   Då visas etikett sidan som visar en lista över dina exempelfiler, med den första filen synlig i visnings programmet.
2. Längst upp i den första exempel filen i visnings programmet ser du text där du tillfrågas om filen är ett exempel på modellen du just skapade. Om det är ett positivt exempel väljer du **Ja**. Om det är ett negativt exempel väljer du **Nej**.
3. I listan med **Etiketter** till vänster väljer du ytterligare filer som du vill använda som exempel och förser dem också. 

    ![Start sidan för klassificerings modell](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Ge minst fem positiva exempel ett negativt exempel. 

## <a name="create-an-explanation"></a>Skapa en förklaring

Nästa steg är att skapa en förklaring på sidan tåg.  En förklaring är ett tips eller en LED tråd för att hjälpa modellen att känna igen det här dokumentet. Våra förnyelse dokument innehåller till exempel alltid en *begäran om ytterligare text sträng för avslöjande* .

> [!Note]
> När det används med utdrag används en förklaring för att identifiera strängen som du vill extrahera från dokumentet. 

Så här skapar du en förklaring:

1. På Start sidan för modellen klickar du på fliken **tåg** för att gå till sidan tåg.
2. I avsnittet **utbildade filer** på sidan tåg visas en lista med exempel filer som du hade märkt tidigare. Välj en av dina positiva filer i listan så visas den i visnings programmet.
3. I avsnittet förklaring klickar du på **nytt**och sedan på **Tom**.
4. På sidan **skapa en förklaring** :</br>
    a. Skriv **namnet** (till exempel "textmeddelande").</br>
    b. Välj **typ**. I vårt exempel väljer vi **fras lista**eftersom vi lägger till en text sträng.</br>
    c. I rutan **Skriv här** skriver du strängen.  I vårt exempel lägger vi till "begäran om ytterligare avslöjande". Du kan välja **SKIFT läges känsligt** om strängen måste vara Skift läges känslig.</br>
    d. Klicka på **Spara**.

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
 
5.  Modellen kontrol leras nu för att se om den förklaring du skapade var tillräcklig för att identifiera dina återstående märkta exempelfiler som positiva och negativa exempel. I avsnittet utbildade filer markerar du kolumnen **utvärdering** efter att utbildningen är klar för att visa resultatet.  Filerna visar ett värde för **matchning** om den förklaring du skapade räcker för att matcha det du hade angett (positivt eller negativt).

    ![Skapa förklaring](../media/content-understanding/match.png) 

Om du får ett **fel** meddelande om dina etiketter kan du behöva skapa en ytterligare förklaring för att ge modellen mer information för att identifiera dokument typen. Du kan klicka på filen för att få mer information om varför matchnings felet inträffade.

## <a name="test-your-model"></a>Testa modellen

Om du har fått en matchning på dina etiketterade exempelfiler kan du testa modellen på dina återstående ljudfiler.

1. Klicka på fliken **testa** på modell start sidan.  Då körs modellen på dina namnlösa exempelfiler.
2. I listan **testfiler** visas dina exempel filer och visas om modellen förväntar sig att vara positiva eller negativa exempel. Du kan använda den här informationen för att avgöra hur din klassificerarens effektivitet är för att identifiera dina dokument.

    ![Testa omärkta filer](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Se även
[Skapa en Extractor](create-an-extractor.md)</br>
[Översikt över dokument förståelse](document-understanding-overview.md)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</br>
[Använda en modell](apply-a-model.md) 




