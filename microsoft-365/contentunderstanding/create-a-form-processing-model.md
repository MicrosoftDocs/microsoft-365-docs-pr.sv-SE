---
title: Skapa en formulärbearbetningsmodell (förhandsgranskning)
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
description: Skapa en formulärbearbetningsmodell i Project Cortex.
ms.openlocfilehash: d3ca64ff5923e95704b72fd748884549a18624a3
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540148"
---
# <a name="create-a-form-processing-model-preview"></a>Skapa en formulärbearbetningsmodell (förhandsgranskning)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Använda [AI Builder](https://docs.microsoft.com/ai-builder/overview) - en funktion i Microsoft PowerApps - Project Cortex-användare kan skapa en [formulärbearbetningsmodell](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek. 

Att skapa en formulärbearbetningsmodell innebär följande:
 - Steg 1: Skapa frånbearbetningsmodellen för att skapa innehållstypen
 - Steg 2: Lägga till och analysera exempelfiler
 - Steg 3: Markera formulärfälten
 - Steg 4: Träna och testa din modell
 - Steg 5: Publicera din modell
 - Steg 6: Använd din modell


## <a name="requirements"></a>Krav

Du kan bara skapa en formulärbearbetningsmodell i SharePoint-dokumentbibliotek där den är aktiverad. Om formulärbearbetning är aktiverat kan du se **AI Builder** **"Skapa en formulärbearbetningsmodell"** under Menyn **Automatisera** i dokumentbiblioteket.  Om du behöver använda den i dokumentbiblioteket kontaktar du administratören.

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Steg 1: Skapa en formulärbearbetningsmodell

Det första steget i att skapa en formulärbearbetningsmodell är att namnge den för att skapa definiera den nya innehållstypen och skapa en ny dokumentbiblioteksvy för den.

1. Välj **menyn Automatisera** i dokumentbiblioteket, välj **AI Builder**och välj sedan Skapa **en formulärbearbetningsmodell**.

    ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>
2. Skriv ett namn på modellen i fältet **Nytt formulärbearbetning** i fältet **Nytt** formulärbearbetning *).*

    ![Ny formulärbearbetningsmodell](../media/content-understanding/new-form-model.png)</br> 

3. När du skapar en formulärbearbetningsmodell skapar du en ny SharePoint-innehållstyp. En SharePoint-innehållstyp representerar en kategori av dokument som har gemensamma egenskaper och delar en samling kolumner eller metadataegenskaper för det aktuella innehållet. SharePoint-innehållstyper hanteras via [galleriet Innehållstyper]().

    Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehållstyp i galleriet SharePoint-innehållstyper för att använda schemat. 

4. Din modell skapar en ny vy i dokumentbiblioteket för dina extraherade data. Om du inte vill att det ska vara standardvyn avmarkerar du **Ange vyn som standard**.
5. Välj **Skapa**.


## <a name="step-2-add-and-analyze-documents"></a>Steg 2: Lägga till och analysera dokument

När du har skapat din nya formulärbearbetningsmodell öppnar webbläsaren en ny Modellsida för PowerApps AI Builder-formulär. På den här sidan kan du lägga till och analysera dina exempeldokument. </br>

> [!Note]
> När du letar efter exempelfiler att använda, se [formulärbearbetningsmodellens indatadokumentkrav och optimeringstips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. Klicka på **Lägg till dokument** om du vill börja lägga till exempeldokument som analyseras för att avgöra vilka namngivna värdepar som kan extraheras. Du kan välja **antingen Ladda upp från lokal lagring,** **SharePoint**eller **Azure Blob storage**. Du måste använda minst fem filer för utbildning.
2. När du har lagt till dina filer väljer du **Analysera** för att söka efter all information som är vanlig är alla filer. Observera att det kan ta flera minuter att slutföra detta.</br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. När de har analyserats klickar du på filen i sidan **Välj de formulärfält som du vill spara** för att se de fält som upptäcktes.</br>

    ![Markera formulärfält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Steg 3: Markera formulärfälten

När du har analyserat dina dokument för fält kan du nu se vilka fält som hittades och vilka som du vill spara. Sparade fält visas som kolumner i modellens dokumentbiblioteksvy och visar de värden som extraherats från varje dokument.

1. På nästa sida visas en av dina exempelfiler och alla vanliga fält som automatiskt upptäcktes av systemet. </br>

    ![Markera formulärfält](../media/content-understanding/select-fields-page.png)</br> 

2. Markera de fält som du vill spara och markera kryssrutan för att bekräfta ditt val. I inköpsordermodellen kan du till exempel välja fälten *Datum,* *INKÖPSORDER*och *Totalt.*  Observera att du också kan välja att byta namn på ett fält om du vill. </br>

    ![Välj INKÖPSORDER #](../media/content-understanding/po.png)</br> 

3. Om ett fält inte upptäcktes av analysen kan du ändå välja att lägga till det. Markera den information som du vill extrahera och skriv det namn som du vill ge den i namnrutan. Välj sedan checken. Observera att du måste bekräfta oupptäckta fält i dina återstående exempelfiler.
4. Klicka på **Bekräfta fält** när du har markerat de fält som du vill spara. </br>
 
    ![Bekräfta fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. På sidan **Välj de formulärfält som du vill spara** visas antalet fält som du har markerat. Välj **Klar**.

## <a name="step-4-train-and-test-your-model"></a>Steg 4: Träna och testa din modell

När du har valt de fält som du vill spara kan du träna och testa modellen på sidan **Modellsammanfattning.**

1. På sidan **Modellsammanfattning** visas de sparade fälten i avsnittet **Markerade fält.** Välj **Träna** om du vill börja träna med dina exempelfiler. Observera att det kan ta några minuter att slutföra detta.</br>
    ![Bekräfta fält](../media/content-understanding/select-fields-train.png)</br> 
2. När du ser meddelandet om att utbildningen har slutförts väljer du **Gå till informationssidan**. 
3. På sidan **Modellinformation** kan du välja att testa hur modellen fungerar genom att välja **Snabbtest**. På så sätt kan du dra och släppa filer till sidan och se om fälten identifieras.

## <a name="step-5-publish-your-model"></a>Steg 5: Publicera din modell



1. Om du är nöjd med resultatet av din modell väljer du **Publicera** för att göra den tillgänglig för användning.
2. När modellen har publicerats väljer du **Använd modell**. Detta skapar ett PowerAutomate-flöde som körs i SharePoint-dokumentbiblioteket och extraherar de fält som har identifierats i modellen. Välj **Skapa flöde**.  
3. När du är klar visas meddelandet **Ditt flöde har skapats**.
 
 
## <a name="step-6-use-your-model"></a>Steg 6: Använd din modell

När du har publicerat modellen och skapat powerautomate-flödet kan du använda modellen i SharePoint-dokumentbiblioteket.

1. När du har publicerat modellen väljer du **Gå till SharePoint** för att gå till dokumentbiblioteket.
2. Observera att de fält som du har markerat nu visas som kolumner i dokumentbiblioteksmodellvyn.</br>

    ![Dokumentbibliotek med modell tillämpad](../media/content-understanding/doc-lib-view.png)</br> 

    Observera också att informationslänken **bredvid Dokument** kommer att notera att en formulärbearbetningsmodell tillämpas på det här dokumentbiblioteket.

    ![Extraherade](../media/content-understanding/info-button.png)</br>  

3. Ladda upp filer till dokumentbiblioteket. Alla filer som modellen identifierar som innehållstyp visar filerna i vyn och visar de extraherade data i kolumnerna.</br>

    ![Extraherade](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Se även
  
[Dokumentation för Power Automate](https://docs.microsoft.com/power-automate/)</br>
[Utbildning: Förbättra företagets resultat med AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




