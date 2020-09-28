---
title: Skapa en klassificerare
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
description: Lär dig hur du skapar en klassificerare
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294908"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0b9de-103">Skapa en klassificerare i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0b9de-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="0b9de-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="0b9de-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="0b9de-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0b9de-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="0b9de-106">En klassificerare är en typ av modell som du kan använda för att automatisera identifiering och klassificering av en dokument typ.</span><span class="sxs-lookup"><span data-stu-id="0b9de-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="0b9de-107">Du kanske till exempel vill identifiera alla *förlängnings* dokument som läggs till i ditt dokument bibliotek, till exempel i följande bild.</span><span class="sxs-lookup"><span data-stu-id="0b9de-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Förnyelse dokument för kontrakt](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="0b9de-109">Om du skapar en klassificerare kan du skapa en ny [SharePoint-innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som associeras med modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="0b9de-110">När du skapar en klassificerare måste du skapa *förklaringar* för att definiera modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="0b9de-111">Det gör att du kan notera vanliga data som du förväntar dig att konsekvent hitta den här dokument typen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="0b9de-112">Använd exempel på dokument typen ("exempel filer") för att "träna" din modell för att identifiera filer som har samma innehålls typ.</span><span class="sxs-lookup"><span data-stu-id="0b9de-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="0b9de-113">Om du vill skapa en klassificerare måste du:</span><span class="sxs-lookup"><span data-stu-id="0b9de-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="0b9de-114">Namnge modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-114">Name your model.</span></span>
2. <span data-ttu-id="0b9de-115">Lägga till exempel filer.</span><span class="sxs-lookup"><span data-stu-id="0b9de-115">Add your example files.</span></span>
3. <span data-ttu-id="0b9de-116">Namnge dina exempel filer.</span><span class="sxs-lookup"><span data-stu-id="0b9de-116">Label your example files.</span></span>
4. <span data-ttu-id="0b9de-117">Skapa en förklaring.</span><span class="sxs-lookup"><span data-stu-id="0b9de-117">Create an explanation.</span></span>
5. <span data-ttu-id="0b9de-118">Testa modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9de-119">Medan modellen använder en klassificerare för att identifiera och klassificera dokument typer kan du också välja att hämta specifika informations delar från varje fil som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="0b9de-120">Gör det genom att skapa en **Extractor** för att lägga till i din modell.</span><span class="sxs-lookup"><span data-stu-id="0b9de-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="0b9de-121">Se [skapa en Extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="0b9de-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="0b9de-122">Namnge modellen</span><span class="sxs-lookup"><span data-stu-id="0b9de-122">Name your model</span></span>

<span data-ttu-id="0b9de-123">Det första steget för att skapa modellen är att ge den ett namn:</span><span class="sxs-lookup"><span data-stu-id="0b9de-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="0b9de-124">I innehålls centret väljer du **ny**och **skapar sedan en modell**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="0b9de-125">Ange namnet på modellen i fältet **namn** i **modell fönstret nytt dokument**</span><span class="sxs-lookup"><span data-stu-id="0b9de-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="0b9de-126">Om du till exempel vill identifiera förlängnings dokument för kontrakt kan du ange ett namn på *förnyelsen*av kostnads kontraktet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="0b9de-127">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-127">Choose **Create**.</span></span> <span data-ttu-id="0b9de-128">Då skapas en start sida för modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-128">This creates a home page for the model.</span></span></br>

    ![Start sidan för klassificerings modell](../media/content-understanding/model-home.png)

<span data-ttu-id="0b9de-130">När du skapar en modell skapar du också en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="0b9de-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="0b9de-131">En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0b9de-132">SharePoint-innehålls typer hanteras via [galleriet innehålls typer](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="0b9de-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="0b9de-133">I det här exemplet skapar du en ny innehålls typ för *kontrakt förnyelse* när du skapar modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="0b9de-134">Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema.</span><span class="sxs-lookup"><span data-stu-id="0b9de-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="0b9de-135">Tänk på att när du kan använda en befintlig innehålls typ för att utnyttja dess schema för att hjälpa till med identifiering och klassificering måste du ändå träna modellen för att extrahera information från filer som identifieras.</span><span class="sxs-lookup"><span data-stu-id="0b9de-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="0b9de-137">Lägga till exempel filer</span><span class="sxs-lookup"><span data-stu-id="0b9de-137">Add your example files</span></span>

<span data-ttu-id="0b9de-138">På Start sidan för modeller kan du lägga till dina exempel filer som du måste hjälpa till att träna modellen för att identifiera dokument typen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="0b9de-139">Du bör använda samma filer för både klassificerings-och [Extractor-utbildning](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="0b9de-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="0b9de-140">Du kan välja att lägga till mer senare, men normalt lägger du till en fullständig uppsättning exempel filer.</span><span class="sxs-lookup"><span data-stu-id="0b9de-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="0b9de-141">Märk lite för att träna modellen och testa resten av dem för att utvärdera modellens användbarhet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="0b9de-142">För din utbildning ställer du in både för positiva och negativa exempel:</span><span class="sxs-lookup"><span data-stu-id="0b9de-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="0b9de-143">Positivt exempel: dokument som representerar dokument typen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="0b9de-144">Dessa innehåller strängar och information som alltid ska finnas med i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="0b9de-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="0b9de-145">Negativt exempel: dokument som inte representerar dokument typen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="0b9de-146">Dessa saknar strängar och information som måste finnas med i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="0b9de-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="0b9de-147">Se till att använda minst fem positiva exempel och minst ett negativt exempel för att träna modellen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="0b9de-148">Du vill skapa fler för att testa modellen efter övnings processen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="0b9de-149">Så här lägger du till exempelfiler:</span><span class="sxs-lookup"><span data-stu-id="0b9de-149">To add sample files:</span></span>

1. <span data-ttu-id="0b9de-150">Klicka på **Lägg till filer**i panelen **Skapa exempel bibliotek** från modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="0b9de-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="0b9de-151">På sidan **Välj exempel filer för modellen** väljer du dina exempel filer från biblioteket för exempelfilerna i innehålls centret.</span><span class="sxs-lookup"><span data-stu-id="0b9de-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="0b9de-152">Om du inte redan har laddat upp dem där väljer du att överföra dem nu genom att klicka på **Ladda upp** för att flytta dem till exempel fil biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0b9de-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="0b9de-153">När du har valt exempel-filerna som ska användas för att träna modellen klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="0b9de-155">Namnge dina exempel filer</span><span class="sxs-lookup"><span data-stu-id="0b9de-155">Label your example files</span></span>

<span data-ttu-id="0b9de-156">När du har lagt till dina exempelfiler måste du förse dem med antingen positiva eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="0b9de-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="0b9de-157">På modell start sidan klickar du på **träna** **filer och kör utbildning** .</span><span class="sxs-lookup"><span data-stu-id="0b9de-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="0b9de-158">Då visas etikett sidan som visar en lista över dina exempelfiler, med den första filen synlig i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="0b9de-159">I visnings programmet högst upp i den första exempel filen bör du se text som frågar om filen är ett exempel på modellen du just skapade.</span><span class="sxs-lookup"><span data-stu-id="0b9de-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="0b9de-160">Om det är ett positivt exempel väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="0b9de-161">Om det är ett negativt exempel väljer du **Nej**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="0b9de-162">I listan med **namngivna exempel** till vänster väljer du ytterligare filer som du vill använda som exempel och etiketterar dem.</span><span class="sxs-lookup"><span data-stu-id="0b9de-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Start sidan för klassificering](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="0b9de-164">Ge minst fem positiva exempel ett negativt exempel.</span><span class="sxs-lookup"><span data-stu-id="0b9de-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="0b9de-165">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="0b9de-165">Create an explanation</span></span>

<span data-ttu-id="0b9de-166">Nästa steg är att skapa en förklaring på sidan tåg.</span><span class="sxs-lookup"><span data-stu-id="0b9de-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="0b9de-167">En förklaring hjälper modellen att känna igen dokumentet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="0b9de-168">Till exempel innehåller kontrakts förlängningarna alltid en *begäran om ytterligare text sträng för avslöjande* .</span><span class="sxs-lookup"><span data-stu-id="0b9de-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="0b9de-169">När en förklaring används med utdrag, identifieras strängen som du vill extrahera från dokumentet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="0b9de-170">Så här skapar du en förklaring:</span><span class="sxs-lookup"><span data-stu-id="0b9de-170">To create an explanation:</span></span>

1. <span data-ttu-id="0b9de-171">Från start sidan för modellen väljer du fliken **tåg** för att gå till sidan tåg.</span><span class="sxs-lookup"><span data-stu-id="0b9de-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="0b9de-172">I avsnittet **utbildade filer** på sidan tåg visas en lista med exempelfiler som du tidigare har märkt.</span><span class="sxs-lookup"><span data-stu-id="0b9de-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="0b9de-173">Välj en av de positiva filerna i listan och visa den i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="0b9de-174">I avsnittet förklaring väljer du **nytt** och sedan **Tom**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="0b9de-175">På sidan **skapa en förklaring** :</span><span class="sxs-lookup"><span data-stu-id="0b9de-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="0b9de-176">a.</span><span class="sxs-lookup"><span data-stu-id="0b9de-176">a.</span></span> <span data-ttu-id="0b9de-177">Skriv **namnet** (till exempel "textmeddelande").</span><span class="sxs-lookup"><span data-stu-id="0b9de-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="0b9de-178">b.</span><span class="sxs-lookup"><span data-stu-id="0b9de-178">b.</span></span> <span data-ttu-id="0b9de-179">Välj **typ**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-179">Select the **Type**.</span></span> <span data-ttu-id="0b9de-180">I exemplet väljer du **fras lista**sedan du lägger till en text sträng.</span><span class="sxs-lookup"><span data-stu-id="0b9de-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="0b9de-181">c.</span><span class="sxs-lookup"><span data-stu-id="0b9de-181">c.</span></span> <span data-ttu-id="0b9de-182">I rutan **Skriv här** skriver du strängen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="0b9de-183">Lägg till "begäran om ytterligare avslöjande".</span><span class="sxs-lookup"><span data-stu-id="0b9de-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="0b9de-184">Du kan välja **SKIFT läges känsligt** om strängen måste vara Skift läges känslig.</span><span class="sxs-lookup"><span data-stu-id="0b9de-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="0b9de-185">d.</span><span class="sxs-lookup"><span data-stu-id="0b9de-185">d.</span></span> <span data-ttu-id="0b9de-186">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0b9de-186">Click **Save**.</span></span>

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="0b9de-188">Nu kontrollerar modellen att den förklaring du skapade var tillräcklig nog för att identifiera de återstående filmärkta exemplen korrekt, som positiva och negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="0b9de-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="0b9de-189">I avsnittet utbildade filer markerar du kolumnen **utvärdering** efter att utbildningen är klar för att visa resultatet.</span><span class="sxs-lookup"><span data-stu-id="0b9de-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="0b9de-190">Filerna visar värdet **matchar**om förklaringarna du skapade räcker till för att matcha det du har angett som positivt eller negativt.</span><span class="sxs-lookup"><span data-stu-id="0b9de-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Matcha värde](../media/content-understanding/match.png) 

<span data-ttu-id="0b9de-192">Om du får ett **fel** meddelande om etiketter kan du behöva skapa ytterligare en förklaring för att ge modellen mer information för att identifiera dokument typen.</span><span class="sxs-lookup"><span data-stu-id="0b9de-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="0b9de-193">Om det inträffar klickar du på filen för att få mer information om varför matchnings felet inträffade.</span><span class="sxs-lookup"><span data-stu-id="0b9de-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="0b9de-194">Testa modellen</span><span class="sxs-lookup"><span data-stu-id="0b9de-194">Test your model</span></span>

<span data-ttu-id="0b9de-195">Om du har fått en matchning på dina etiketterade exempelfiler kan du testa modellen på dina återstående ljudfiler.</span><span class="sxs-lookup"><span data-stu-id="0b9de-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="0b9de-196">På Start sidan för modellen väljer du fliken **test** .  Då körs modellen på dina namnlösa exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="0b9de-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="0b9de-197">I listan **testfiler** visas och visar dina exempel filer om modellen förväntar sig vara positiv eller negativ.</span><span class="sxs-lookup"><span data-stu-id="0b9de-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="0b9de-198">Använd den här informationen för att fastställa hur din klassificerarens effektivitet är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="0b9de-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa omärkta filer](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="0b9de-200">Se även</span><span class="sxs-lookup"><span data-stu-id="0b9de-200">See Also</span></span>
[<span data-ttu-id="0b9de-201">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="0b9de-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="0b9de-202">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="0b9de-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="0b9de-203">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="0b9de-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="0b9de-204">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="0b9de-204">Apply a model</span></span>](apply-a-model.md) 
