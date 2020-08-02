---
title: Skapa en klassificerare (förhandsgranska)
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
description: Lär dig hur du skapar en klassificerare
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537901"
---
# <a name="create-a-classifier-preview"></a>Skapa en klassificerare (förhandsgranska)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

En klassificerare är en typ av modell som automatiserar identifiering och klassificering av en dokumenttyp. Du kanske till exempel vill identifiera alla dokument för *kontraktsförnyelse* som läggs till i dokumentbiblioteket, till exempel följande.

![Dokument för kontraktsförnyelse](../media/content-understanding/contract-renewal.png)

Om du skapar en klassificerare skapas en ny [SharePoint-innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som ska associeras med modellen.

När du skapar klassificeraren måste du skapa *förklaringar* som hjälper till att definiera modellen genom att notera vanliga data som du förväntar dig att hitta konsekvent för den här dokumenttypen. 

Du kan använda exempel på dokumenttyp ("exempelfiler") för att "träna" din modell för att identifiera filer med samma innehållstyp.

Om du vill skapa en klassificerare måste du:
1. Namnge din modell
2. Lägga till dina exempelfiler
3. Märka exempelfilerna
4. Skapa en förklaring
5. Testa din modell 

> [!Note]
> Medan en klassificerare används av din modell för att identifiera och klassificera dokumenttyper, kan du också välja att hämta specifika informationsdelar från varje fil som identifieras av modellen. Du gör detta genom att skapa en **utsutorn** att lägga till i din modell, och detta beskrivs i [Skapa en extractor](create-an-extractor.md).

## <a name="name-your-model"></a>Namnge din modell

Det första steget är att skapa din modell i Content Center genom att ge den ett namn:

1. Klicka på **Nytt**i Innehållscenter och klicka sedan på **Skapa en modell**.
2. Skriv namnet på modellen i fältet **Namn** i **rutan Ny modell för dokumentförståelse.** Om vi till exempel vill identifiera dokument för förnyelse av kontrakt kan vi namnge den här modellen *För förnyelse av kontrakt.*
3. Klicka på **Skapa**. Då skapas en startsida för modellen.</br>

    ![Klassenyrmodells hemsida](../media/content-understanding/model-home.png)

När du skapar en modell skapar du en ny SharePoint-innehållstyp. En SharePoint-innehållstyp representerar en kategori av dokument som har gemensamma egenskaper och delar en samling kolumner eller metadataegenskaper för det aktuella innehållet. SharePoint-innehållstyper hanteras via [galleriet Innehållstyper](). Till vår exempel, när vi skapar modellen, kommer vi att skapa en ny *avtalsförnyelse* innehållstyp.

Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehållstyp i galleriet SharePoint-innehållstyper för att använda schemat. Observera att även om du kan använda en befintlig innehållstyp för att utnyttja schemat för att hjälpa till med identifiering och klassificering, måste du fortfarande träna din modell att extrahera information från filer som den identifierar.</br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Lägga till dina exempelfiler

På modellens startsida kan du lägga till exempelfiler som du behöver för att träna modellen för att identifiera dokumenttypen. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Samma filer bör användas för både klassificerare och [utsugsträning](create-an-extractor.md). Du har alltid möjlighet att lägga till fler senare, men vanligtvis bör du lägga till en fullständig uppsättning exempelfiler. Du kommer att märka några för att träna din modell, och testa de återstående omärkta dem för att utvärdera modell kondition. 

För din träningsuppsättning vill du använda både positiva exempel och negativa exempel:
- Positivt exempel: Dokument som representerar dokumenttypen. De innehåller strängar och information som alltid skulle finnas i den här typen av dokument.
- Negativt exempel: Dokument som inte representerar dokumenttypen.  De saknar strängar och information som måste finnas i den här typen av dokument.

Du kommer att vilja använda minst fem positiva exempel och ett negativt exempel för att träna din modell.  Du kommer att vilja ha ytterligare för att testa din modell efter träningen.

Så här lägger du till exempelfiler:

1. Klicka på **Lägg till filer**i panelen Skapa exempelbibliotek på startsidan för **byggprovsbibliotek** .
2. På sidan **Välj exempelfiler för modell** väljer du exempelfilerna från exempelfilsbiblioteket i Innehållscenter. Om du inte redan hade laddat upp dem där kan du välja att ladda upp dem nu genom att klicka på **Ladda upp** för att flytta dem till exempelfilbiblioteket.
3. När du har valt dina exempelfiler som ska användas för att träna modellen klickar du på **Lägg till**.

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Märka exempelfilerna

När du har lagt till dina exempelfiler måste du sedan märka dem som antingen positiva exempel eller negativa exempel.

1. Klicka på **Träna klassificerare**på startsidan för modellen. **Classify files and run training**
   Då visas etikettsidan som visar en lista över dina exempelfiler, med den första filen synlig i visningsprogrammet.
2. I visningsprogrammet, högst upp i den första exempelfilen, visas text som frågar dig om filen är ett exempel på den modell som du just skapade. Om det är ett positivt exempel väljer du **Ja**. Om det är ett negativt exempel väljer du **Nej**.
3. I listan **Märkta exempel** till vänster väljer du ytterligare filer som du vill använda som exempel och även märker dem. 

    ![Klassenyrmodells hemsida](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Märk minst fem positiva exempel och ett negativt exempel. 

## <a name="create-an-explanation"></a>Skapa en förklaring

Nästa steg är att skapa en förklaring på sidan Tåg.  En förklaring är en ledtråd eller ledtråd för att hjälpa modellen att förstå hur man känner igen det här dokumentet. Våra dokument för kontraktsförnyelse innehåller till exempel alltid en *begäran om ytterligare textsträng för information.*

> [!Note]
> När du använder med utt extraherare används en förklaring för att identifiera strängen som du vill extrahera från dokumentet. 

Så här skapar du en förklaring:

1. Klicka på fliken **Tåg** på modellens startsida för att gå till sidan Tåg.
2. På sidan Tåg visas en lista över exempelfiler som du har märkt tidigare i avsnittet **Tränade filer.** Välj en av dina positiva filer i listan och den visas i visningsprogrammet.
3. Klicka på **Nytt**i avsnittet Förklaring och klicka sedan på **Tom**.
4. På sidan **Skapa en förklaring:**</br>
    a. Skriv **namnet** (till exempel "Disclosure Block").</br>
    b. Välj **typ**. I vårt exempel väljer vi **Fraslista**eftersom vi lägger till en textsträng.</br>
    c. Skriv strängen i rutan **Typ här.**  I vårt exempel lägger vi till "Begäran om ytterligare avslöjande". Du kan välja **Skiftlägeskänslig** om strängen måste vara skiftlägeskänslig.</br>
    d. Klicka på **Spara**.

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
 
5.  Modellen kommer nu att kontrollera om förklaringen du skapade var tillräckligt bra för att identifiera dina återstående märkta exempelfiler korrekt som positiva och negativa exempel. I avsnittet Tränade filer kontrollerar du kolumnen **Utvärdering** efter att utbildningen har slutförts för att se resultaten.  Filerna visar värdet **Matchning** om förklaringen du skapade var tillräckligt för att matcha vad du hade märkt dem som (positiva eller negativa).

    ![Skapa förklaring](../media/content-understanding/match.png) 

Om du får en **felmatchning** på dina märkta filer kan du behöva skapa ytterligare en förklaring för att ge modellen mer information för att identifiera dokumenttypen. Du kan klicka på filen för att få mer information om varför obalansen inträffade.

## <a name="test-your-model"></a>Testa din modell

Om du har fått en matchning på dina märkta exempelfiler kan du nu testa modellen på de återstående omärkta exempelfilerna.

1. Klicka på fliken **Testa** på modellens startsida.  Då körs modellen på de omärkta exempelfilerna.
2. I listan **Testa filer** visas dina exempelfiler och visas om modellen förutspådde att de skulle vara positiva eller negativa exempel. Du kan använda den här informationen för att avgöra hur effektiv klassificeraren är när det gäller att identifiera dina dokument.

    ![Testa omärkta filer](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Se även
[Skapa en utsutorn](create-an-extractor.md)</br>
[Översikt över dokuments förståelse](document-understanding-overview.md)</br>
[Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)</br>
[Använda en modell](apply-a-model.md) 




