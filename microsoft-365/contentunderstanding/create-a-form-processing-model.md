---
title: Skapa en modell för formulärbearbetning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Skapa en modell för formulärbearbetning i Microsoft SharePoint-Syntex.
ms.openlocfilehash: d71273e416bf7922627e44d9423eaa8903411689
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905852"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="3b7cd-103">Skapa en modell för formulärbearbetning i Microsoft SharePoint-Syntex</span><span class="sxs-lookup"><span data-stu-id="3b7cd-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="3b7cd-104">Använda [AI-verktyg](/ai-builder/overview) – en funktion i Microsoft PowerApps – SharePoint Syntex-användare kan skapa en[modell för formulärbearbetning](form-processing-overview.md) direkt från ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-104">Using [AI Builder](/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="3b7cd-105">Att skapa en modell för formulärbearbetning inbegriper följande:</span><span class="sxs-lookup"><span data-stu-id="3b7cd-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="3b7cd-106">Steg 1: Skapa modellen för formulärbearbetning för att skapa innehållstypen</span><span class="sxs-lookup"><span data-stu-id="3b7cd-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="3b7cd-107">Steg 2: Lägg till och analysera exempelfiler</span><span class="sxs-lookup"><span data-stu-id="3b7cd-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="3b7cd-108">Steg 3: Välj dina formulärfält</span><span class="sxs-lookup"><span data-stu-id="3b7cd-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="3b7cd-109">Steg 4: Träna och testa din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="3b7cd-110">Steg 5: Publicera din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="3b7cd-111">Steg 6: Använd din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="3b7cd-112">Krav</span><span class="sxs-lookup"><span data-stu-id="3b7cd-112">Requirements</span></span>

<span data-ttu-id="3b7cd-113">Du kan bara skapa en modell för formulärbearbetning i SharePoint-dokumentbibliotek för vilka den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="3b7cd-114">Om formulärbearbetning är aktiverad kan du se **AI Builder** **"Skapa en modell för formulärbearbetning"** under **Automatisera** meny i ditt dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="3b7cd-115">Om du behöver få bearbetning aktiverad i ditt dokumentbibliotek måste du kontakta din SharePoint-administratör.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Skapa en AI Builder-modell](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="3b7cd-117">Steg 1: Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="3b7cd-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="3b7cd-118">Första steget för att skapa en modell för formulärbearbetning är att namnge den och skapa, definiera den nya innehållstyp och skapa ett nytt vy för dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="3b7cd-119">Välj **Automatisera** -menyn i dokumentbiblioteket, välj **AI Builder** och välj sedan **Skapa en modell för Formulärbearbetning**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Skapa en modell](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="3b7cd-121">I fönstret **Ny modell för formulärbearbetning**, **Namn**-fältet skriver du ett namn på din modell (t. ex *Inköpsorder*).</span><span class="sxs-lookup"><span data-stu-id="3b7cd-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Ny modell för formulärbearbetning](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="3b7cd-123">När du skapar en modell för formulärbearbetning skapar du en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="3b7cd-124">En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en samling kolumner eller metadata för det specifika innehåll.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="3b7cd-125">SharePoint Innehållstyper hanteras via [Innehållstyper galleriet ]().</span><span class="sxs-lookup"><span data-stu-id="3b7cd-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="3b7cd-126">Välj **Avancerade inställningar** om du vill mappa denna modell till en befintlig innehållstyp i SharePoint Innehållstyp galleriet för att använda dess schema.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="3b7cd-127">Din modell skapar en ny vy i ditt dokumentbibliotek för dina hämtade data.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="3b7cd-128">Om du inte vill använda den som standardvy avmarkerar du **Ställ in vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="3b7cd-129">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="3b7cd-130">Steg 2: Lägg till och analysera dokument</span><span class="sxs-lookup"><span data-stu-id="3b7cd-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="3b7cd-131">När du har skapat din nya modell för formulärbearbetning öppnas en ny PowerApps AI Builder sida för modell för formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="3b7cd-132">På den här sidan kan du lägga till och analysera dina exempel dokument.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="3b7cd-133">När du söker efter exempelfiler att använda, kolla i [modell för formulärbearbetning indata dokument krav och optimeringstips](/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="3b7cd-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="3b7cd-135">Välj **Lägg till dokument** för att börja lägga till exempeldokument som analyseras för att avgöra vilka namn/värde-par som kan extraheras.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="3b7cd-136">Sedan kan du välja antingen **Ladda upp från lokal lagring**, **SharePoint** eller **Azure-blobblagring**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="3b7cd-137">Du måste använda minst fem filer för utbildning.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="3b7cd-138">När du har lagt till filer välj **Analysera** för att kontrollera om det finns någon gemensam information för alla filer.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="3b7cd-139">Det kan ta flera minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-139">This may take several minutes to complete.</span></span></br> 
 
    ![Analysera filer](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="3b7cd-141">När filerna har analyserats gå till **Välj de formulärfält som du vill spara** sidan välj filen för att visa de upptäckta filerna.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Välj formulärfält](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="3b7cd-143">Steg 3: Välj dina formulärfält</span><span class="sxs-lookup"><span data-stu-id="3b7cd-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="3b7cd-144">När du har analyserat dokumenten för fält kan du nu se de fält som hittades och identifiera de som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="3b7cd-145">Sparade fält visas som kolumner i din modells dokumentbibliotek vy och visar de värden som extraheras från varje dokument.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="3b7cd-146">På nästa sida visas en av dina exempelfiler och markera alla gemensamma fält som har identifierats automatiskt av systemet.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Välj fältsida](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="3b7cd-148">Välj de fält som du vill spara och välj kryssrutan för att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="3b7cd-149">Till exempel, i Modellen för Inköpsorder välj *Datumet*, *IO* och *Summa* fälten.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="3b7cd-150">Notera att du kan också välja att byta namn på ett fält om du vill.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Välj IO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="3b7cd-152">Om ett fält inte har identifierats av analysen kan du fortfarande välja att lägga till det.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="3b7cd-153">Markera den information du vill extrahera och skriv namnet du vill ha i namnrutan.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="3b7cd-154">Markera sedan kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-154">Then select the check box.</span></span> <span data-ttu-id="3b7cd-155">Notera att du behöver bekräfta oidentifierade fält i dina återstående exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="3b7cd-156">Klicka på **Bekräfta fält** när du har valt de fält som du vill spara.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Bekräfta fält när du har valt fält](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="3b7cd-158">I **Välj de formulärfält du vill spara** sidan visas det antal fält som du har valt.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="3b7cd-159">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="3b7cd-160">Steg 4: Träna och testa din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="3b7cd-161">När du har valt de fält du vill spara kan du använda **Modellsammanfattnings**-sidan för att träna och testa din modell.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="3b7cd-162">På **Modellsammanfattnings**-sidan visas de sparade fälten i den **Valda fält** sektionen.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="3b7cd-163">Välj **Träna** för att påbörja utbildning på dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="3b7cd-164">Notera att det här kan ta några minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-164">Note that this may take a few minutes to complete.</span></span></br>

     ![Välj fältsida Träna](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="3b7cd-166">När du ser meddelandet om att utbildning har slutförts välj **Gå till informationssidan**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="3b7cd-167">På sidan **Modellinformation** kan du välja att testa hur din modell fungerar genom att välja **Snabbtest**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="3b7cd-168">På så sätt kan du dra och släppa filer till sidan och se om fälten har identifierats.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Bekräfta fält](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="3b7cd-170">När du ser meddelandet om att utbildning har slutförts välj **Gå till informationssidan**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="3b7cd-171">På sidan **Modellinformation** kan du välja att testa hur din modell fungerar genom att välja **Snabbtest**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="3b7cd-172">På så sätt kan du dra och släppa filer till sidan och se om fälten har identifierats.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="3b7cd-173">Steg 5: Publicera din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="3b7cd-174">Om du är nöjd med din modells resultat, välj **Publicera** för att göra den tillgängligt för användning.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="3b7cd-175">När modellen har publicerats välj **Använda modell**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="3b7cd-176">Detta skapar ett PowerAutomate-flöde som kan köras i ditt SharePoint-dokumentbibliotek och hämtar de fält som har identifierats i modellen, välj sedan **Skapa Flöde**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="3b7cd-177">När det är klart visas meddelandet **Ditt flöde har skapats framgångsrikt**.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="3b7cd-178">Steg 6: Använd din modell</span><span class="sxs-lookup"><span data-stu-id="3b7cd-178">Step 6: Use your model</span></span>

<span data-ttu-id="3b7cd-179">När du har publicerat din modell och skapat PowerAutomate flöde åt den, kan du använda din modell i ditt SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="3b7cd-180">När du har publicerat din modell, välj **Gå till SharePoint** för att gå till ditt dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="3b7cd-181">I vyn för modellen för dokumentbibliotek kan du se att de fält som du valde nu visas som kolumner.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modell för dokumentbibliotek tillämpad](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="3b7cd-183">Notera att informationslänken bredvid **Dokument** påpekar att en modell för formulärbearbetning används i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Informations-knappen](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="3b7cd-185">Ladda upp filer till ditt dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-185">Upload files to your document library.</span></span> <span data-ttu-id="3b7cd-186">Alla filer som modellen identifierar som innehållstyp listar filerna i din vy och visar den extraherade data i kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Klart](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="3b7cd-188">Se även</span><span class="sxs-lookup"><span data-stu-id="3b7cd-188">See Also</span></span>
  
[<span data-ttu-id="3b7cd-189">Power Automate dokumentation</span><span class="sxs-lookup"><span data-stu-id="3b7cd-189">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="3b7cd-190">Utbildning: Förbättra affärsprestanda med AI Builder</span><span class="sxs-lookup"><span data-stu-id="3b7cd-190">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)