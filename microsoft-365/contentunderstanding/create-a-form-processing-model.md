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
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="123a5-103">Skapa en modell för formulär bearbetning (för hands version)</span><span class="sxs-lookup"><span data-stu-id="123a5-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="123a5-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="123a5-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="123a5-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="123a5-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="123a5-106">Använda [AI-verktyget](https://docs.microsoft.com/ai-builder/overview) – en funktion i Microsoft PowerApps – Project cortex-användare kan skapa en [modell för formulär bearbetning](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="123a5-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="123a5-107">Att skapa en modell för formulär bearbetning inbegriper följande:</span><span class="sxs-lookup"><span data-stu-id="123a5-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="123a5-108">Steg 1: skapa innehålls typen från bearbetnings modellen</span><span class="sxs-lookup"><span data-stu-id="123a5-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="123a5-109">Steg 2: lägga till och analysera exempel filer</span><span class="sxs-lookup"><span data-stu-id="123a5-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="123a5-110">Steg 3: Välj formulär fälten</span><span class="sxs-lookup"><span data-stu-id="123a5-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="123a5-111">Steg 4: träna och testa modellen</span><span class="sxs-lookup"><span data-stu-id="123a5-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="123a5-112">Steg 5: publicera din modell</span><span class="sxs-lookup"><span data-stu-id="123a5-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="123a5-113">Steg 6: använda modellen</span><span class="sxs-lookup"><span data-stu-id="123a5-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="123a5-114">Krav</span><span class="sxs-lookup"><span data-stu-id="123a5-114">Requirements</span></span>

<span data-ttu-id="123a5-115">Du kan bara skapa en formulär bearbetnings modell i SharePoint-dokumentbibliotek där den är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="123a5-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="123a5-116">Om formulär bearbetning är aktiverat kan du se **AI-verktyget** **"skapa en formulär bearbetnings modell"** under **Automatisera** -menyn i dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="123a5-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="123a5-117">Om du behöver använda bearbetnings funktionen i dokument biblioteket kontaktar du din administratör.</span><span class="sxs-lookup"><span data-stu-id="123a5-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="123a5-119">Steg 1: skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="123a5-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="123a5-120">Det första steget när du skapar en modell för formulär bearbetning är att namnge den för att skapa fönstret definiera den nya innehålls typen och skapa en ny vy för dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="123a5-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="123a5-121">I dokument biblioteket väljer du menyn **Automatisera** , väljer **AI Builder**och väljer sedan **skapa en modell för formulär bearbetning**.</span><span class="sxs-lookup"><span data-stu-id="123a5-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="123a5-123">I fönstret **ny formulär bearbetnings modell** anger du ett namn på modellen (till exempel *inköps order*) i fältet **namn** .</span><span class="sxs-lookup"><span data-stu-id="123a5-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Ny modell för formulär bearbetning](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="123a5-125">När du skapar en formulär bearbetnings modell skapar du en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="123a5-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="123a5-126">En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet.</span><span class="sxs-lookup"><span data-stu-id="123a5-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="123a5-127">SharePoint-innehålls typer hanteras via [galleriet innehålls typer]().</span><span class="sxs-lookup"><span data-stu-id="123a5-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="123a5-128">Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema.</span><span class="sxs-lookup"><span data-stu-id="123a5-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="123a5-129">Modellen skapar en ny vy i dokument biblioteket för dina extraherade data.</span><span class="sxs-lookup"><span data-stu-id="123a5-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="123a5-130">Om du inte vill använda den som standardvy avmarkerar du **Ställ in vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="123a5-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="123a5-131">Välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="123a5-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="123a5-132">Steg 2: lägga till och analysera dokument</span><span class="sxs-lookup"><span data-stu-id="123a5-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="123a5-133">När du har skapat den nya modellen för formulär bearbetning öppnas en ny PowerApps AI Builder-sida med formulär bearbetnings modell.</span><span class="sxs-lookup"><span data-stu-id="123a5-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="123a5-134">På den här sidan kan du lägga till och analysera exempel dokument.</span><span class="sxs-lookup"><span data-stu-id="123a5-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="123a5-135">När du letar efter exempel filer som ska användas läser du [krav för inmatnings dokument och optimerings tips för formulär bearbetnings modellen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="123a5-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![AI-verktyg för Power Apps](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="123a5-137">Klicka på **Lägg till dokument** för att lägga till exempel dokument som analyseras för att avgöra vilka namngivna värde par som kan extraheras.</span><span class="sxs-lookup"><span data-stu-id="123a5-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="123a5-138">Du kan välja **Ladda upp från lokal lagring**, **SharePoint**eller **Azure-Blob-lagring**.</span><span class="sxs-lookup"><span data-stu-id="123a5-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="123a5-139">Du måste använda minst fem filer för utbildning.</span><span class="sxs-lookup"><span data-stu-id="123a5-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="123a5-140">När du har lagt till filerna väljer du **analysera** för att kontrol lera eventuell information som är gemensam för alla filer.</span><span class="sxs-lookup"><span data-stu-id="123a5-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="123a5-141">Observera att det kan ta flera minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="123a5-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="123a5-143">När de har analyser ATS klickar du på filen i listan **Markera de formulär fält som du vill spara** .</span><span class="sxs-lookup"><span data-stu-id="123a5-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Välj formulär fält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="123a5-145">Steg 3: Välj formulär fälten</span><span class="sxs-lookup"><span data-stu-id="123a5-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="123a5-146">När du har analyserat dina dokument för fält kan du se vilka fält som hittades och vilka som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="123a5-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="123a5-147">Sparade fält visas som kolumner i modellens dokument bibliotek och visar de värden som extraheras från varje dokument.</span><span class="sxs-lookup"><span data-stu-id="123a5-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="123a5-148">Nästa sida visar en av dina exempelfiler och markerar alla gemensamma fält som identifieras automatiskt av systemet.</span><span class="sxs-lookup"><span data-stu-id="123a5-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Välj formulär fält](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="123a5-150">Markera de fält som du vill spara och markera kryss rutan för att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="123a5-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="123a5-151">I modellen för inköps order kan du till exempel välja *datum*, *IO*och *total summa* .</span><span class="sxs-lookup"><span data-stu-id="123a5-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="123a5-152">Observera att du också kan byta namn på ett fält om du vill.</span><span class="sxs-lookup"><span data-stu-id="123a5-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Välj PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="123a5-154">Om ett fält inte identifieras av analysen kan du ändå välja att lägga till det.</span><span class="sxs-lookup"><span data-stu-id="123a5-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="123a5-155">Markera den information som du vill extrahera och ange namnet på den i rutan namn.</span><span class="sxs-lookup"><span data-stu-id="123a5-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="123a5-156">Markera sedan kryss rutan.</span><span class="sxs-lookup"><span data-stu-id="123a5-156">Then select the check.</span></span> <span data-ttu-id="123a5-157">Observera att du måste bekräfta de oidentifierade fälten i de återstående exemplen.</span><span class="sxs-lookup"><span data-stu-id="123a5-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="123a5-158">Klicka på **Bekräfta fält** när du har markerat fälten som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="123a5-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Bekräfta fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="123a5-160">I rutan **Markera de formulär fält du vill spara** visas det antal fält du har valt.</span><span class="sxs-lookup"><span data-stu-id="123a5-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="123a5-161">Välj **klar**.</span><span class="sxs-lookup"><span data-stu-id="123a5-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="123a5-162">Steg 4: träna och testa modellen</span><span class="sxs-lookup"><span data-stu-id="123a5-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="123a5-163">När du har valt de fält du vill spara kan du träna och testa modellen med **modell sammanfattnings** sidan.</span><span class="sxs-lookup"><span data-stu-id="123a5-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="123a5-164">På sidan **modell Sammanfattning** visas de sparade fälten i avsnittet **valda fält** .</span><span class="sxs-lookup"><span data-stu-id="123a5-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="123a5-165">Välj **träna** för att påbörja träning för dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="123a5-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="123a5-166">Observera att det kan ta några minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="123a5-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="123a5-167">![Bekräfta fält](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="123a5-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="123a5-168">När du ser meddelandet om att utbildningen har slutförts väljer du **gå till sidan information**.</span><span class="sxs-lookup"><span data-stu-id="123a5-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="123a5-169">På sidan **modell information** kan du välja att testa hur modellen fungerar genom att välja **snabb test**.</span><span class="sxs-lookup"><span data-stu-id="123a5-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="123a5-170">Med det här alternativet kan du dra och släppa filer till sidan och se om fälten identifieras.</span><span class="sxs-lookup"><span data-stu-id="123a5-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="123a5-171">Steg 5: publicera din modell</span><span class="sxs-lookup"><span data-stu-id="123a5-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="123a5-172">Om du är nöjd med resultatet av modellen väljer du **publicera** för att göra den tillgänglig för användning.</span><span class="sxs-lookup"><span data-stu-id="123a5-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="123a5-173">När modellen har publicerats väljer du **Använd modell**.</span><span class="sxs-lookup"><span data-stu-id="123a5-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="123a5-174">Detta skapar ett PowerAutomate-flöde som körs i SharePoint-dokumentbiblioteket och extraherar de fält som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="123a5-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="123a5-175">Välj **skapa flöde**.</span><span class="sxs-lookup"><span data-stu-id="123a5-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="123a5-176">När du är klar kommer du att se meddelandet att **flödet har skapats**.</span><span class="sxs-lookup"><span data-stu-id="123a5-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="123a5-177">Steg 6: använda modellen</span><span class="sxs-lookup"><span data-stu-id="123a5-177">Step 6: Use your model</span></span>

<span data-ttu-id="123a5-178">När du har publicerat modellen och skapat det PowerAutomate flödet kan du använda modellen i ditt SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="123a5-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="123a5-179">När du har publicerat modellen väljer du **gå till SharePoint** för att gå till ditt dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="123a5-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="123a5-180">I modell vyn för dokument bibliotek kan du se att fälten du valde nu visas som kolumner.</span><span class="sxs-lookup"><span data-stu-id="123a5-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Dokument bibliotek med modellen använda](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="123a5-182">Observera också att informations länken bredvid **dokument** anger att en modell för formulär bearbetning används för det här dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="123a5-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Pack](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="123a5-184">Ladda upp filer till ett dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="123a5-184">Upload files to your document library.</span></span> <span data-ttu-id="123a5-185">Alla filer som modellen identifierar som innehålls typ visas i listan och visar extraherade data i kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="123a5-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Pack](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="123a5-187">Se även</span><span class="sxs-lookup"><span data-stu-id="123a5-187">See Also</span></span>
  
[<span data-ttu-id="123a5-188">Automatiserad energi dokumentation</span><span class="sxs-lookup"><span data-stu-id="123a5-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="123a5-189">Utbildning: förbättra företags prestanda med hjälp av AI Builder</span><span class="sxs-lookup"><span data-stu-id="123a5-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




