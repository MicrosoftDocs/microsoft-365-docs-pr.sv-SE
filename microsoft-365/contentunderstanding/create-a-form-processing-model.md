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
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="ed23b-103">Skapa en formulärbearbetningsmodell (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="ed23b-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="ed23b-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="ed23b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="ed23b-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ed23b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="ed23b-106">Använda [AI Builder](https://docs.microsoft.com/ai-builder/overview) - en funktion i Microsoft PowerApps - Project Cortex-användare kan skapa en [formulärbearbetningsmodell](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="ed23b-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="ed23b-107">Att skapa en formulärbearbetningsmodell innebär följande:</span><span class="sxs-lookup"><span data-stu-id="ed23b-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="ed23b-108">Steg 1: Skapa frånbearbetningsmodellen för att skapa innehållstypen</span><span class="sxs-lookup"><span data-stu-id="ed23b-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="ed23b-109">Steg 2: Lägga till och analysera exempelfiler</span><span class="sxs-lookup"><span data-stu-id="ed23b-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="ed23b-110">Steg 3: Markera formulärfälten</span><span class="sxs-lookup"><span data-stu-id="ed23b-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="ed23b-111">Steg 4: Träna och testa din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="ed23b-112">Steg 5: Publicera din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="ed23b-113">Steg 6: Använd din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="ed23b-114">Krav</span><span class="sxs-lookup"><span data-stu-id="ed23b-114">Requirements</span></span>

<span data-ttu-id="ed23b-115">Du kan bara skapa en formulärbearbetningsmodell i SharePoint-dokumentbibliotek där den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="ed23b-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="ed23b-116">Om formulärbearbetning är aktiverat kan du se **AI Builder** **"Skapa en formulärbearbetningsmodell"** under Menyn **Automatisera** i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="ed23b-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="ed23b-117">Om du behöver använda den i dokumentbiblioteket kontaktar du administratören.</span><span class="sxs-lookup"><span data-stu-id="ed23b-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="ed23b-119">Steg 1: Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="ed23b-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="ed23b-120">Det första steget i att skapa en formulärbearbetningsmodell är att namnge den för att skapa definiera den nya innehållstypen och skapa en ny dokumentbiblioteksvy för den.</span><span class="sxs-lookup"><span data-stu-id="ed23b-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="ed23b-121">Välj **menyn Automatisera** i dokumentbiblioteket, välj **AI Builder**och välj sedan Skapa **en formulärbearbetningsmodell**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="ed23b-123">Skriv ett namn på modellen i fältet **Nytt formulärbearbetning** i fältet **Nytt** formulärbearbetning *).*</span><span class="sxs-lookup"><span data-stu-id="ed23b-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Ny formulärbearbetningsmodell](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="ed23b-125">När du skapar en formulärbearbetningsmodell skapar du en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="ed23b-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="ed23b-126">En SharePoint-innehållstyp representerar en kategori av dokument som har gemensamma egenskaper och delar en samling kolumner eller metadataegenskaper för det aktuella innehållet.</span><span class="sxs-lookup"><span data-stu-id="ed23b-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="ed23b-127">SharePoint-innehållstyper hanteras via [galleriet Innehållstyper]().</span><span class="sxs-lookup"><span data-stu-id="ed23b-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="ed23b-128">Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehållstyp i galleriet SharePoint-innehållstyper för att använda schemat.</span><span class="sxs-lookup"><span data-stu-id="ed23b-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="ed23b-129">Din modell skapar en ny vy i dokumentbiblioteket för dina extraherade data.</span><span class="sxs-lookup"><span data-stu-id="ed23b-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="ed23b-130">Om du inte vill att det ska vara standardvyn avmarkerar du **Ange vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="ed23b-131">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="ed23b-132">Steg 2: Lägga till och analysera dokument</span><span class="sxs-lookup"><span data-stu-id="ed23b-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="ed23b-133">När du har skapat din nya formulärbearbetningsmodell öppnar webbläsaren en ny Modellsida för PowerApps AI Builder-formulär.</span><span class="sxs-lookup"><span data-stu-id="ed23b-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="ed23b-134">På den här sidan kan du lägga till och analysera dina exempeldokument.</span><span class="sxs-lookup"><span data-stu-id="ed23b-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="ed23b-135">När du letar efter exempelfiler att använda, se [formulärbearbetningsmodellens indatadokumentkrav och optimeringstips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="ed23b-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="ed23b-137">Klicka på **Lägg till dokument** om du vill börja lägga till exempeldokument som analyseras för att avgöra vilka namngivna värdepar som kan extraheras.</span><span class="sxs-lookup"><span data-stu-id="ed23b-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="ed23b-138">Du kan välja **antingen Ladda upp från lokal lagring,** **SharePoint**eller **Azure Blob storage**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="ed23b-139">Du måste använda minst fem filer för utbildning.</span><span class="sxs-lookup"><span data-stu-id="ed23b-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="ed23b-140">När du har lagt till dina filer väljer du **Analysera** för att söka efter all information som är vanlig är alla filer.</span><span class="sxs-lookup"><span data-stu-id="ed23b-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="ed23b-141">Observera att det kan ta flera minuter att slutföra detta.</span><span class="sxs-lookup"><span data-stu-id="ed23b-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="ed23b-143">När de har analyserats klickar du på filen i sidan **Välj de formulärfält som du vill spara** för att se de fält som upptäcktes.</span><span class="sxs-lookup"><span data-stu-id="ed23b-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Markera formulärfält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="ed23b-145">Steg 3: Markera formulärfälten</span><span class="sxs-lookup"><span data-stu-id="ed23b-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="ed23b-146">När du har analyserat dina dokument för fält kan du nu se vilka fält som hittades och vilka som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="ed23b-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="ed23b-147">Sparade fält visas som kolumner i modellens dokumentbiblioteksvy och visar de värden som extraherats från varje dokument.</span><span class="sxs-lookup"><span data-stu-id="ed23b-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="ed23b-148">På nästa sida visas en av dina exempelfiler och alla vanliga fält som automatiskt upptäcktes av systemet.</span><span class="sxs-lookup"><span data-stu-id="ed23b-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Markera formulärfält](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="ed23b-150">Markera de fält som du vill spara och markera kryssrutan för att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="ed23b-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="ed23b-151">I inköpsordermodellen kan du till exempel välja fälten *Datum,* *INKÖPSORDER*och *Totalt.*</span><span class="sxs-lookup"><span data-stu-id="ed23b-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="ed23b-152">Observera att du också kan välja att byta namn på ett fält om du vill.</span><span class="sxs-lookup"><span data-stu-id="ed23b-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Välj INKÖPSORDER #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="ed23b-154">Om ett fält inte upptäcktes av analysen kan du ändå välja att lägga till det.</span><span class="sxs-lookup"><span data-stu-id="ed23b-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="ed23b-155">Markera den information som du vill extrahera och skriv det namn som du vill ge den i namnrutan.</span><span class="sxs-lookup"><span data-stu-id="ed23b-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="ed23b-156">Välj sedan checken.</span><span class="sxs-lookup"><span data-stu-id="ed23b-156">Then select the check.</span></span> <span data-ttu-id="ed23b-157">Observera att du måste bekräfta oupptäckta fält i dina återstående exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="ed23b-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="ed23b-158">Klicka på **Bekräfta fält** när du har markerat de fält som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="ed23b-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Bekräfta fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="ed23b-160">På sidan **Välj de formulärfält som du vill spara** visas antalet fält som du har markerat.</span><span class="sxs-lookup"><span data-stu-id="ed23b-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="ed23b-161">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="ed23b-162">Steg 4: Träna och testa din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="ed23b-163">När du har valt de fält som du vill spara kan du träna och testa modellen på sidan **Modellsammanfattning.**</span><span class="sxs-lookup"><span data-stu-id="ed23b-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="ed23b-164">På sidan **Modellsammanfattning** visas de sparade fälten i avsnittet **Markerade fält.**</span><span class="sxs-lookup"><span data-stu-id="ed23b-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="ed23b-165">Välj **Träna** om du vill börja träna med dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="ed23b-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="ed23b-166">Observera att det kan ta några minuter att slutföra detta.</span><span class="sxs-lookup"><span data-stu-id="ed23b-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="ed23b-167">![Bekräfta fält](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="ed23b-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="ed23b-168">När du ser meddelandet om att utbildningen har slutförts väljer du **Gå till informationssidan**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="ed23b-169">På sidan **Modellinformation** kan du välja att testa hur modellen fungerar genom att välja **Snabbtest**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="ed23b-170">På så sätt kan du dra och släppa filer till sidan och se om fälten identifieras.</span><span class="sxs-lookup"><span data-stu-id="ed23b-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="ed23b-171">Steg 5: Publicera din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="ed23b-172">Om du är nöjd med resultatet av din modell väljer du **Publicera** för att göra den tillgänglig för användning.</span><span class="sxs-lookup"><span data-stu-id="ed23b-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="ed23b-173">När modellen har publicerats väljer du **Använd modell**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="ed23b-174">Detta skapar ett PowerAutomate-flöde som körs i SharePoint-dokumentbiblioteket och extraherar de fält som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="ed23b-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="ed23b-175">Välj **Skapa flöde**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="ed23b-176">När du är klar visas meddelandet **Ditt flöde har skapats**.</span><span class="sxs-lookup"><span data-stu-id="ed23b-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="ed23b-177">Steg 6: Använd din modell</span><span class="sxs-lookup"><span data-stu-id="ed23b-177">Step 6: Use your model</span></span>

<span data-ttu-id="ed23b-178">När du har publicerat modellen och skapat powerautomate-flödet kan du använda modellen i SharePoint-dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="ed23b-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="ed23b-179">När du har publicerat modellen väljer du **Gå till SharePoint** för att gå till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="ed23b-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="ed23b-180">Observera att de fält som du har markerat nu visas som kolumner i dokumentbiblioteksmodellvyn.</span><span class="sxs-lookup"><span data-stu-id="ed23b-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Dokumentbibliotek med modell tillämpad](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="ed23b-182">Observera också att informationslänken **bredvid Dokument** kommer att notera att en formulärbearbetningsmodell tillämpas på det här dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="ed23b-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Extraherade](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="ed23b-184">Ladda upp filer till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="ed23b-184">Upload files to your document library.</span></span> <span data-ttu-id="ed23b-185">Alla filer som modellen identifierar som innehållstyp visar filerna i vyn och visar de extraherade data i kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="ed23b-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Extraherade](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="ed23b-187">Se även</span><span class="sxs-lookup"><span data-stu-id="ed23b-187">See Also</span></span>
  
[<span data-ttu-id="ed23b-188">Dokumentation för Power Automate</span><span class="sxs-lookup"><span data-stu-id="ed23b-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="ed23b-189">Utbildning: Förbättra företagets resultat med AI Builder</span><span class="sxs-lookup"><span data-stu-id="ed23b-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




