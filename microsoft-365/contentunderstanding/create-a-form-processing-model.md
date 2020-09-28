---
title: Skapa en modell för formulär bearbetning
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa en formulär bearbetnings modell i Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295484"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Skapa en formulär bearbetnings modell i Microsoft SharePoint Syntex

Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Använda [AI-verktyget](https://docs.microsoft.com/ai-builder/overview) – en funktion i Microsoft PowerApps – Project cortex-användare kan skapa en [modell för formulär bearbetning](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek. 

Att skapa en modell för formulär bearbetning inbegriper följande:
 - Steg 1: skapa innehålls typen från bearbetnings modellen
 - Steg 2: lägga till och analysera exempel filer
 - Steg 3: Välj formulär fälten
 - Steg 4: träna och testa modellen
 - Steg 5: publicera din modell
 - Steg 6: använda modellen

## <a name="requirements"></a>Krav

Du kan bara skapa en formulär bearbetnings modell i SharePoint-dokumentbibliotek för vilka den är aktive rad. Om formulär bearbetning är aktiverat kan du se **AI-verktyget** **"skapa en formulär bearbetnings modell"** under menyn **Automatisera** i dokument biblioteket.  Om du behöver arbeta aktiverat i dokument biblioteket måste du kontakta SharePoint-administratören.

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Steg 1: skapa en modell för formulär bearbetning

Det första steget när du skapar en modell för formulär bearbetning är att namnge den och skapa en ny vy för dokument bibliotek.

1. Välj menyn **Automatisera** i dokument biblioteket, Välj **AI Builder**och välj sedan **skapa en modell för formulär bearbetning**.

    ![Skapa en modell](../media/content-understanding/create-ai-builder-model.png)</br>

2. I fönstret **ny formulär bearbetnings modell** anger du ett namn på modellen (till exempel *inköps order*) i fältet **namn** .

    ![Ny modell för formulär bearbetning](../media/content-understanding/new-form-model.png)</br> 

3. När du skapar en formulär bearbetnings modell skapar du en ny SharePoint-innehållstyp. En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet. SharePoint-innehålls typer hanteras via [galleriet innehålls typer]().

    Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema. 

4. Modellen skapar en ny vy i dokument biblioteket för dina extraherade data. Om du inte vill använda den som standardvy avmarkerar du **Ställ in vyn som standard**.

5. Välj **skapa**.

## <a name="step-2-add-and-analyze-documents"></a>Steg 2: lägga till och analysera dokument

När du har skapat den nya modellen för formulär bearbetning öppnas en ny PowerApps AI Builder-sida med formulär bearbetnings modell. På den här sidan kan du lägga till och analysera exempel dokument. </br>

> [!NOTE]
> När du letar efter exempel filer som ska användas läser du [krav för inmatnings dokument och optimerings tips för formulär bearbetnings modellen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![AI-verktyg för Power Apps](../media/content-understanding/powerapps.png)</br> 
 
1. Välj **Lägg till dokument** för att lägga till exempel dokument som analyseras för att avgöra vilka namngivna värde par som kan extraheras. Du kan sedan välja **Ladda upp från lokal lagring**, **SharePoint**eller **Azure-Blob-lagring**. Du måste använda minst fem filer för utbildning.

2. När du har lagt till filer väljer du **analysera** för att söka efter information som är gemensam för alla filer. Det kan ta några minuter att slutföra.</br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. När filerna har analyser ATS går du till sidan **Markera de formulär fält du vill spara** och väljer filen för att visa de identifierade fälten.</br>

    ![Välj formulär fält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Steg 3: Välj formulär fälten

När du har analyserat dokumenten för fält kan du se de fält som hittades och identifiera dem som du vill spara. Sparade fält visas som kolumner i modellens dokument biblioteks vy och visar de värden som extraheras från varje dokument.

1. Nästa sida visar en av dina exempelfiler och markerar alla gemensamma fält som identifieras automatiskt av systemet. </br>

    ![Sidan Markera fält](../media/content-understanding/select-fields-page.png)</br> 

2. Markera de fält som du vill spara och markera kryss rutan för att bekräfta ditt val. I till exempel inköps order modellen väljer du att välja fälten *datum*, *IO*och *Total* .  Observera att du också kan byta namn på ett fält om du vill. </br>

    ![Välj PO #](../media/content-understanding/po.png)</br> 

3. Om ett fält inte identifieras av analysen kan du ändå välja att lägga till det. Markera den information som du vill extrahera och ange önskat namn i rutan namn. Markera sedan kryss rutan. Observera att du måste bekräfta de oidentifierade fälten i dina återstående exempelfiler.

4. Klicka på **Bekräfta fält** när du har markerat fälten som du vill spara. </br>
 
    ![Bekräfta fält efter markering av fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. På sidan **Markera de formulär fält du vill spara** visas det antal fält du valt. Välj **klar**.

## <a name="step-4-train-and-test-your-model"></a>Steg 4: träna och testa modellen

När du har valt de fält du vill spara kan du träna och testa modellen med **modell sammanfattnings** sidan.

1. På sidan **modell Sammanfattning** visas de sparade fälten i avsnittet **valda fält** . Välj **träna** för att påbörja träning för dina exempelfiler. Observera att det kan ta några minuter att slutföra.</br>

     ![Välj fält tåg](../media/content-understanding/select-fields-train.png)</br> 

2. När du ser meddelandet om att utbildningen har slutförts väljer du **gå till sidan information**. 

3. På sidan **modell information** kan du välja att testa hur modellen fungerar genom att välja **snabb test**. Med det här alternativet kan du dra och släppa filer till sidan och se om fälten identifieras.

    ![Bekräfta fält](../media/content-understanding/select-fields-train.png)</br> 

2. När du ser meddelandet om att utbildningen har slutförts väljer du **gå till sidan information**. 

3. På sidan **modell information** väljer du för att testa hur modellen fungerar genom att välja **snabb test**. Med det här alternativet kan du dra och släppa filer till sidan och se om fälten identifieras.

## <a name="step-5-publish-your-model"></a>Steg 5: publicera din modell

1. Om du är nöjd med resultatet av modellen väljer du **publicera** för att göra den tillgänglig för användning.

2. När modellen har publicerats väljer du **Använd modell**. Då skapas ett PowerAutomate-flöde som kan köras i SharePoint-dokumentbiblioteket och de fält som har identifierats i modellen extraheras och sedan **skapas ett flöde**.
  
3. När du är klar kommer du att se meddelandet att **flödet har skapats**.
 
## <a name="step-6-use-your-model"></a>Steg 6: använda modellen

När du har publicerat modellen och skapat det PowerAutomate flödet kan du använda modellen i ditt SharePoint-dokumentbibliotek.

1. När du har publicerat modellen väljer du **gå till SharePoint** för att gå till ditt dokument bibliotek.

2. Observera att fälten du valde nu visas som kolumner i modellen för dokument bibliotek.</br>

    ![Dokument biblioteks modell som tillämpas](../media/content-understanding/doc-lib-view.png)</br> 

3. Observera att informations länken bredvid **dokument** anteckningar som en modell för formulär bearbetning används för det här dokument biblioteket.

    ![Knappen info](../media/content-understanding/info-button.png)</br>  

4. Ladda upp filer till ett dokument bibliotek. Alla filer som modellen identifierar som innehålls typ listar filerna i vyn och visar extraherade data i kolumnerna.</br>

    ![Åstadkomma](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Se även
  
[Automatiserad energi dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
