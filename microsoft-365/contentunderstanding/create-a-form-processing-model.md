---
title: Skapa en modell för formulär bearbetning (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa en formulär bearbetnings modell i Project cortex.
ms.openlocfilehash: cec3b9a8b1b58237c4beb745377709d4938a2dba
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950150"
---
# <a name="create-a-form-processing-model-preview"></a>Skapa en modell för formulär bearbetning (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

Använda [AI-verktyget](https://docs.microsoft.com/ai-builder/overview) – en funktion i Microsoft PowerApps – Project cortex-användare kan skapa en [modell för formulär bearbetning](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek. 

Att skapa en modell för formulär bearbetning inbegriper följande:
 - Steg 1: skapa innehålls typen från bearbetnings modellen
 - Steg 2: lägga till och analysera exempel filer
 - Steg 3: Välj formulär fälten
 - Steg 4: träna och testa modellen
 - Steg 5: publicera din modell
 - Steg 6: använda modellen


## <a name="requirements"></a>Krav

Du kan bara skapa en formulär bearbetnings modell i SharePoint-dokumentbibliotek där den är aktive rad. Om formulär bearbetning är aktiverat kan du se **AI-verktyget** **"skapa en formulär bearbetnings modell"** under **Automatisera** -menyn i dokument biblioteket.  Om du behöver använda bearbetnings funktionen i dokument biblioteket kontaktar du din administratör.

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Steg 1: skapa en modell för formulär bearbetning

Det första steget när du skapar en modell för formulär bearbetning är att namnge den för att skapa fönstret definiera den nya innehålls typen och skapa en ny vy för dokument bibliotek.

1. I dokument biblioteket väljer du menyn **Automatisera** , väljer **AI Builder**och väljer sedan **skapa en modell för formulär bearbetning**.

    ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>
2. I fönstret **ny formulär bearbetnings modell** anger du ett namn på modellen (till exempel *inköps order*) i fältet **namn** .

    ![Ny modell för formulär bearbetning](../media/content-understanding/new-form-model.png)</br> 

3. När du skapar en formulär bearbetnings modell skapar du en ny SharePoint-innehållstyp. En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet. SharePoint-innehålls typer hanteras via [galleriet innehålls typer]().

    Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema. 

4. Modellen skapar en ny vy i dokument biblioteket för dina extraherade data. Om du inte vill använda den som standardvy avmarkerar du **Ställ in vyn som standard**.
5. Välj **skapa**.


## <a name="step-2-add-and-analyze-documents"></a>Steg 2: lägga till och analysera dokument

När du har skapat den nya modellen för formulär bearbetning öppnas en ny PowerApps AI Builder-sida med formulär bearbetnings modell. På den här sidan kan du lägga till och analysera exempel dokument. </br>

> [!Note]
> När du letar efter exempel filer som ska användas läser du [krav för inmatnings dokument och optimerings tips för formulär bearbetnings modellen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![AI-verktyg för Power Apps](../media/content-understanding/powerapps.png)</br> 
 

1. Klicka på **Lägg till dokument** för att lägga till exempel dokument som analyseras för att avgöra vilka namngivna värde par som kan extraheras. Du kan välja **Ladda upp från lokal lagring**, **SharePoint**eller **Azure-Blob-lagring**. Du måste använda minst fem filer för utbildning.
2. När du har lagt till filerna väljer du **analysera** för att kontrol lera eventuell information som är gemensam för alla filer. Observera att det kan ta flera minuter att slutföra.</br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. När de har analyser ATS klickar du på filen i listan **Markera de formulär fält som du vill spara** .</br>

    ![Välj formulär fält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Steg 3: Välj formulär fälten

När du har analyserat dina dokument för fält kan du se vilka fält som hittades och vilka som du vill spara. Sparade fält visas som kolumner i modellens dokument bibliotek och visar de värden som extraheras från varje dokument.

1. Nästa sida visar en av dina exempelfiler och markerar alla gemensamma fält som identifieras automatiskt av systemet. </br>

    ![Välj formulär fält](../media/content-understanding/select-fields-page.png)</br> 

2. Markera de fält som du vill spara och markera kryss rutan för att bekräfta ditt val. I modellen för inköps order kan du till exempel välja *datum*, *IO*och *total summa* .  Observera att du också kan byta namn på ett fält om du vill. </br>

    ![Välj PO #](../media/content-understanding/po.png)</br> 

3. Om ett fält inte identifieras av analysen kan du ändå välja att lägga till det. Markera den information som du vill extrahera och ange namnet på den i rutan namn. Markera sedan kryss rutan. Observera att du måste bekräfta de oidentifierade fälten i de återstående exemplen.
4. Klicka på **Bekräfta fält** när du har markerat fälten som du vill spara. </br>
 
    ![Bekräfta fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. I rutan **Markera de formulär fält du vill spara** visas det antal fält du har valt. Välj **klar**.

## <a name="step-4-train-and-test-your-model"></a>Steg 4: träna och testa modellen

När du har valt de fält du vill spara kan du träna och testa modellen med **modell sammanfattnings** sidan.

1. På sidan **modell Sammanfattning** visas de sparade fälten i avsnittet **valda fält** . Välj **träna** för att påbörja träning för dina exempelfiler. Observera att det kan ta några minuter att slutföra.</br>
    ![Bekräfta fält](../media/content-understanding/select-fields-train.png)</br> 
2. När du ser meddelandet om att utbildningen har slutförts väljer du **gå till sidan information**. 
3. På sidan **modell information** kan du välja att testa hur modellen fungerar genom att välja **snabb test**. Med det här alternativet kan du dra och släppa filer till sidan och se om fälten identifieras.

## <a name="step-5-publish-your-model"></a>Steg 5: publicera din modell



1. Om du är nöjd med resultatet av modellen väljer du **publicera** för att göra den tillgänglig för användning.
2. När modellen har publicerats väljer du **Använd modell**. Detta skapar ett PowerAutomate-flöde som körs i SharePoint-dokumentbiblioteket och extraherar de fält som har identifierats i modellen. Välj **skapa flöde**.  
3. När du är klar kommer du att se meddelandet att **flödet har skapats**.
 
 
## <a name="step-6-use-your-model"></a>Steg 6: använda modellen

När du har publicerat modellen och skapat det PowerAutomate flödet kan du använda modellen i ditt SharePoint-dokumentbibliotek.

1. När du har publicerat modellen väljer du **gå till SharePoint** för att gå till ditt dokument bibliotek.
2. I modell vyn för dokument bibliotek kan du se att fälten du valde nu visas som kolumner.</br>

    ![Dokument bibliotek med modellen använda](../media/content-understanding/doc-lib-view.png)</br> 

    Observera också att informations länken bredvid **dokument** anger att en modell för formulär bearbetning används för det här dokument biblioteket.

    ![Pack](../media/content-understanding/info-button.png)</br>  

3. Ladda upp filer till ett dokument bibliotek. Alla filer som modellen identifierar som innehålls typ visas i listan och visar extraherade data i kolumnerna.</br>

    ![Pack](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Se även
  
[Automatiserad energi dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Utbildning: förbättra företags prestanda med hjälp av AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




