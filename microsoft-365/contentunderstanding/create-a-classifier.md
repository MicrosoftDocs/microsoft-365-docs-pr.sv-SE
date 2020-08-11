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
# <a name="create-a-classifier-preview"></a><span data-ttu-id="4678f-103">Skapa en klassificerare (för hands version)</span><span class="sxs-lookup"><span data-stu-id="4678f-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4678f-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="4678f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4678f-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4678f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="4678f-106">En klassificerare är en typ av modell som används för att automatisera identifiering och klassificering av en dokument typ.</span><span class="sxs-lookup"><span data-stu-id="4678f-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="4678f-107">Du kanske till exempel vill identifiera alla *förlängnings* dokument som läggs till i ditt dokument bibliotek, som följande.</span><span class="sxs-lookup"><span data-stu-id="4678f-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Förnyelse dokument för kontrakt](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="4678f-109">Om du skapar en klassificerare skapas en ny [SharePoint-innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som associeras med modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="4678f-110">När du skapar en klassificerare måste du skapa *förklaringar* som hjälper dig att definiera modellen genom att ange vanliga data som du förväntar dig hitta konsekvent för den här dokument typen.</span><span class="sxs-lookup"><span data-stu-id="4678f-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="4678f-111">Du använder exempel på dokument typen ("exempel filer") för att "träna" din modell för att identifiera filer som har samma innehålls typ.</span><span class="sxs-lookup"><span data-stu-id="4678f-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="4678f-112">Om du vill skapa en klassificerare måste du:</span><span class="sxs-lookup"><span data-stu-id="4678f-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="4678f-113">Namnge modellen</span><span class="sxs-lookup"><span data-stu-id="4678f-113">Name your model</span></span>
2. <span data-ttu-id="4678f-114">Lägga till exempel filer</span><span class="sxs-lookup"><span data-stu-id="4678f-114">Add your example files</span></span>
3. <span data-ttu-id="4678f-115">Namnge dina exempel filer</span><span class="sxs-lookup"><span data-stu-id="4678f-115">Label your example files</span></span>
4. <span data-ttu-id="4678f-116">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="4678f-116">Create an explanation</span></span>
5. <span data-ttu-id="4678f-117">Testa modellen</span><span class="sxs-lookup"><span data-stu-id="4678f-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="4678f-118">När en klassificerare används av modellen för att identifiera och klassificera dokument typer kan du också välja att hämta specifika informations delar från varje fil som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="4678f-119">Det gör du genom att skapa en **Extractor** för att lägga till i din modell, så beskrivs i [skapa en Extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="4678f-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="4678f-120">Namnge modellen</span><span class="sxs-lookup"><span data-stu-id="4678f-120">Name your model</span></span>

<span data-ttu-id="4678f-121">Det första steget är att skapa en modell i innehålls Center genom att ge den ett namn:</span><span class="sxs-lookup"><span data-stu-id="4678f-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="4678f-122">I innehålls centret klickar du på **ny**och sedan på **skapa en modell**.</span><span class="sxs-lookup"><span data-stu-id="4678f-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="4678f-123">Skriv namnet på modellen i fältet **namn** i **modell fönstret nytt dokument**</span><span class="sxs-lookup"><span data-stu-id="4678f-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="4678f-124">Om vi till exempel vill identifiera förlängnings handlingar för kontrakt kan vi ge dig ett namn på *förnyelse*av den här modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="4678f-125">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="4678f-125">Click **Create**.</span></span> <span data-ttu-id="4678f-126">Detta skapar en start sida för modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-126">This will create a home page for the model.</span></span></br>

    ![Start sidan för klassificerings modell](../media/content-understanding/model-home.png)

<span data-ttu-id="4678f-128">När du skapar en modell skapar du en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="4678f-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="4678f-129">En SharePoint-innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en uppsättning kolumner eller metadataegenskaper för det specifika innehållet.</span><span class="sxs-lookup"><span data-stu-id="4678f-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4678f-130">SharePoint-innehålls typer hanteras via [galleriet innehålls typer]().</span><span class="sxs-lookup"><span data-stu-id="4678f-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="4678f-131">I vårt exempel kommer vi att skapa en ny innehålls typ för *kontrakt förnyelse* när vi skapar modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="4678f-132">Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehålls typ i galleriet SharePoint-innehålls typer för att använda dess schema.</span><span class="sxs-lookup"><span data-stu-id="4678f-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="4678f-133">Observera att när du kan använda en befintlig innehålls typ för att påverka dess schema för att hjälpa till med identifiering och klassificering måste du ändå träna din modell att extrahera information från filer som identifieras.</span><span class="sxs-lookup"><span data-stu-id="4678f-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="4678f-135">Lägga till exempel filer</span><span class="sxs-lookup"><span data-stu-id="4678f-135">Add your example files</span></span>

<span data-ttu-id="4678f-136">På Start sidan för modeller kan du lägga till exempel filer som du måste hjälpa till att träna modellen för att identifiera din dokument typ.</span><span class="sxs-lookup"><span data-stu-id="4678f-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="4678f-137">Samma filer bör användas både för klassificerings-och [Extractor-utbildning](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="4678f-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="4678f-138">Du kan alltid lägga till mer senare, men normalt bör du lägga till en fullständig uppsättning exempel filer.</span><span class="sxs-lookup"><span data-stu-id="4678f-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="4678f-139">Du kommer att märka en del för att träna modellen och testa resten av dem för att utvärdera modellens användbarhet.</span><span class="sxs-lookup"><span data-stu-id="4678f-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="4678f-140">För din utbildning är det bara att använda både positiva och negativa exempel:</span><span class="sxs-lookup"><span data-stu-id="4678f-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="4678f-141">Positivt exempel: dokument som representerar dokument typen.</span><span class="sxs-lookup"><span data-stu-id="4678f-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="4678f-142">De innehåller strängar och information som alltid ska vara med i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="4678f-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="4678f-143">Negativt exempel: dokument som inte representerar dokument typen.</span><span class="sxs-lookup"><span data-stu-id="4678f-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="4678f-144">De innehåller strängar och information som måste finnas med i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="4678f-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="4678f-145">Du ska använda minst fem positiva exempel och ett negativt exempel för att träna modellen.</span><span class="sxs-lookup"><span data-stu-id="4678f-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="4678f-146">Du vill att ytterligare testa modellen efter utbildning.</span><span class="sxs-lookup"><span data-stu-id="4678f-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="4678f-147">Så här lägger du till exempelfiler:</span><span class="sxs-lookup"><span data-stu-id="4678f-147">To add sample files:</span></span>

1. <span data-ttu-id="4678f-148">Klicka på **Lägg till filer**i panelen **Skapa exempel bibliotek** på modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="4678f-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="4678f-149">På sidan **Välj exempel filer för modellen** väljer du dina exempel filer från biblioteket för exempelfilerna i innehålls centret.</span><span class="sxs-lookup"><span data-stu-id="4678f-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="4678f-150">Om du inte redan har laddat upp dem där kan du välja att överföra dem nu genom att klicka på **Ladda upp** för att flytta dem till exempel fil biblioteket.</span><span class="sxs-lookup"><span data-stu-id="4678f-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="4678f-151">När du har valt exempel-filerna som ska användas för att träna modellen klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4678f-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="4678f-153">Namnge dina exempel filer</span><span class="sxs-lookup"><span data-stu-id="4678f-153">Label your example files</span></span>

<span data-ttu-id="4678f-154">När du har lagt till dina exempelfiler måste du märka dem som antingen positiva exempel eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="4678f-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="4678f-155">På modell start sidan klickar du på **träna** **filer och kör utbildning** .</span><span class="sxs-lookup"><span data-stu-id="4678f-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="4678f-156">Då visas etikett sidan som visar en lista över dina exempelfiler, med den första filen synlig i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="4678f-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="4678f-157">Längst upp i den första exempel filen i visnings programmet ser du text där du tillfrågas om filen är ett exempel på modellen du just skapade.</span><span class="sxs-lookup"><span data-stu-id="4678f-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="4678f-158">Om det är ett positivt exempel väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4678f-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="4678f-159">Om det är ett negativt exempel väljer du **Nej**.</span><span class="sxs-lookup"><span data-stu-id="4678f-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="4678f-160">I listan med **Etiketter** till vänster väljer du ytterligare filer som du vill använda som exempel och förser dem också.</span><span class="sxs-lookup"><span data-stu-id="4678f-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Start sidan för klassificerings modell](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="4678f-162">Ge minst fem positiva exempel ett negativt exempel.</span><span class="sxs-lookup"><span data-stu-id="4678f-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="4678f-163">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="4678f-163">Create an explanation</span></span>

<span data-ttu-id="4678f-164">Nästa steg är att skapa en förklaring på sidan tåg.</span><span class="sxs-lookup"><span data-stu-id="4678f-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="4678f-165">En förklaring är ett tips eller en LED tråd för att hjälpa modellen att känna igen det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4678f-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="4678f-166">Våra förnyelse dokument innehåller till exempel alltid en *begäran om ytterligare text sträng för avslöjande* .</span><span class="sxs-lookup"><span data-stu-id="4678f-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="4678f-167">När det används med utdrag används en förklaring för att identifiera strängen som du vill extrahera från dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4678f-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="4678f-168">Så här skapar du en förklaring:</span><span class="sxs-lookup"><span data-stu-id="4678f-168">To create an explanation:</span></span>

1. <span data-ttu-id="4678f-169">På Start sidan för modellen klickar du på fliken **tåg** för att gå till sidan tåg.</span><span class="sxs-lookup"><span data-stu-id="4678f-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="4678f-170">I avsnittet **utbildade filer** på sidan tåg visas en lista med exempel filer som du hade märkt tidigare.</span><span class="sxs-lookup"><span data-stu-id="4678f-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="4678f-171">Välj en av dina positiva filer i listan så visas den i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="4678f-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="4678f-172">I avsnittet förklaring klickar du på **nytt**och sedan på **Tom**.</span><span class="sxs-lookup"><span data-stu-id="4678f-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="4678f-173">På sidan **skapa en förklaring** :</span><span class="sxs-lookup"><span data-stu-id="4678f-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="4678f-174">a.</span><span class="sxs-lookup"><span data-stu-id="4678f-174">a.</span></span> <span data-ttu-id="4678f-175">Skriv **namnet** (till exempel "textmeddelande").</span><span class="sxs-lookup"><span data-stu-id="4678f-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="4678f-176">b.</span><span class="sxs-lookup"><span data-stu-id="4678f-176">b.</span></span> <span data-ttu-id="4678f-177">Välj **typ**.</span><span class="sxs-lookup"><span data-stu-id="4678f-177">Select the **Type**.</span></span> <span data-ttu-id="4678f-178">I vårt exempel väljer vi **fras lista**eftersom vi lägger till en text sträng.</span><span class="sxs-lookup"><span data-stu-id="4678f-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="4678f-179">c.</span><span class="sxs-lookup"><span data-stu-id="4678f-179">c.</span></span> <span data-ttu-id="4678f-180">I rutan **Skriv här** skriver du strängen.</span><span class="sxs-lookup"><span data-stu-id="4678f-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="4678f-181">I vårt exempel lägger vi till "begäran om ytterligare avslöjande".</span><span class="sxs-lookup"><span data-stu-id="4678f-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="4678f-182">Du kan välja **SKIFT läges känsligt** om strängen måste vara Skift läges känslig.</span><span class="sxs-lookup"><span data-stu-id="4678f-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="4678f-183">d.</span><span class="sxs-lookup"><span data-stu-id="4678f-183">d.</span></span> <span data-ttu-id="4678f-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4678f-184">Click **Save**.</span></span>

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="4678f-186">Modellen kontrol leras nu för att se om den förklaring du skapade var tillräcklig för att identifiera dina återstående märkta exempelfiler som positiva och negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="4678f-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="4678f-187">I avsnittet utbildade filer markerar du kolumnen **utvärdering** efter att utbildningen är klar för att visa resultatet.</span><span class="sxs-lookup"><span data-stu-id="4678f-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="4678f-188">Filerna visar ett värde för **matchning** om den förklaring du skapade räcker för att matcha det du hade angett (positivt eller negativt).</span><span class="sxs-lookup"><span data-stu-id="4678f-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Skapa förklaring](../media/content-understanding/match.png) 

<span data-ttu-id="4678f-190">Om du får ett **fel** meddelande om dina etiketter kan du behöva skapa en ytterligare förklaring för att ge modellen mer information för att identifiera dokument typen.</span><span class="sxs-lookup"><span data-stu-id="4678f-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="4678f-191">Du kan klicka på filen för att få mer information om varför matchnings felet inträffade.</span><span class="sxs-lookup"><span data-stu-id="4678f-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4678f-192">Testa modellen</span><span class="sxs-lookup"><span data-stu-id="4678f-192">Test your model</span></span>

<span data-ttu-id="4678f-193">Om du har fått en matchning på dina etiketterade exempelfiler kan du testa modellen på dina återstående ljudfiler.</span><span class="sxs-lookup"><span data-stu-id="4678f-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="4678f-194">Klicka på fliken **testa** på modell start sidan.  Då körs modellen på dina namnlösa exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="4678f-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="4678f-195">I listan **testfiler** visas dina exempel filer och visas om modellen förväntar sig att vara positiva eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="4678f-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="4678f-196">Du kan använda den här informationen för att avgöra hur din klassificerarens effektivitet är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="4678f-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa omärkta filer](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="4678f-198">Se även</span><span class="sxs-lookup"><span data-stu-id="4678f-198">See Also</span></span>
[<span data-ttu-id="4678f-199">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="4678f-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="4678f-200">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="4678f-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="4678f-201">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="4678f-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4678f-202">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="4678f-202">Apply a model</span></span>](apply-a-model.md) 




