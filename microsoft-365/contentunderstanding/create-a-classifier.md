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
# <a name="create-a-classifier-preview"></a><span data-ttu-id="616de-103">Skapa en klassificerare (förhandsgranska)</span><span class="sxs-lookup"><span data-stu-id="616de-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="616de-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="616de-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="616de-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="616de-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="616de-106">En klassificerare är en typ av modell som automatiserar identifiering och klassificering av en dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="616de-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="616de-107">Du kanske till exempel vill identifiera alla dokument för *kontraktsförnyelse* som läggs till i dokumentbiblioteket, till exempel följande.</span><span class="sxs-lookup"><span data-stu-id="616de-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Dokument för kontraktsförnyelse](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="616de-109">Om du skapar en klassificerare skapas en ny [SharePoint-innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som ska associeras med modellen.</span><span class="sxs-lookup"><span data-stu-id="616de-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="616de-110">När du skapar klassificeraren måste du skapa *förklaringar* som hjälper till att definiera modellen genom att notera vanliga data som du förväntar dig att hitta konsekvent för den här dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="616de-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="616de-111">Du kan använda exempel på dokumenttyp ("exempelfiler") för att "träna" din modell för att identifiera filer med samma innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="616de-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="616de-112">Om du vill skapa en klassificerare måste du:</span><span class="sxs-lookup"><span data-stu-id="616de-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="616de-113">Namnge din modell</span><span class="sxs-lookup"><span data-stu-id="616de-113">Name your model</span></span>
2. <span data-ttu-id="616de-114">Lägga till dina exempelfiler</span><span class="sxs-lookup"><span data-stu-id="616de-114">Add your example files</span></span>
3. <span data-ttu-id="616de-115">Märka exempelfilerna</span><span class="sxs-lookup"><span data-stu-id="616de-115">Label your example files</span></span>
4. <span data-ttu-id="616de-116">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="616de-116">Create an explanation</span></span>
5. <span data-ttu-id="616de-117">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="616de-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="616de-118">Medan en klassificerare används av din modell för att identifiera och klassificera dokumenttyper, kan du också välja att hämta specifika informationsdelar från varje fil som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="616de-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="616de-119">Du gör detta genom att skapa en **utsutorn** att lägga till i din modell, och detta beskrivs i [Skapa en extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="616de-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="616de-120">Namnge din modell</span><span class="sxs-lookup"><span data-stu-id="616de-120">Name your model</span></span>

<span data-ttu-id="616de-121">Det första steget är att skapa din modell i Content Center genom att ge den ett namn:</span><span class="sxs-lookup"><span data-stu-id="616de-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="616de-122">Klicka på **Nytt**i Innehållscenter och klicka sedan på **Skapa en modell**.</span><span class="sxs-lookup"><span data-stu-id="616de-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="616de-123">Skriv namnet på modellen i fältet **Namn** i **rutan Ny modell för dokumentförståelse.**</span><span class="sxs-lookup"><span data-stu-id="616de-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="616de-124">Om vi till exempel vill identifiera dokument för förnyelse av kontrakt kan vi namnge den här modellen *För förnyelse av kontrakt.*</span><span class="sxs-lookup"><span data-stu-id="616de-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="616de-125">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="616de-125">Click **Create**.</span></span> <span data-ttu-id="616de-126">Då skapas en startsida för modellen.</span><span class="sxs-lookup"><span data-stu-id="616de-126">This will create a home page for the model.</span></span></br>

    ![Klassenyrmodells hemsida](../media/content-understanding/model-home.png)

<span data-ttu-id="616de-128">När du skapar en modell skapar du en ny SharePoint-innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="616de-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="616de-129">En SharePoint-innehållstyp representerar en kategori av dokument som har gemensamma egenskaper och delar en samling kolumner eller metadataegenskaper för det aktuella innehållet.</span><span class="sxs-lookup"><span data-stu-id="616de-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="616de-130">SharePoint-innehållstyper hanteras via [galleriet Innehållstyper]().</span><span class="sxs-lookup"><span data-stu-id="616de-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="616de-131">Till vår exempel, när vi skapar modellen, kommer vi att skapa en ny *avtalsförnyelse* innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="616de-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="616de-132">Välj **Avancerade inställningar** om du vill mappa den här modellen till en befintlig innehållstyp i galleriet SharePoint-innehållstyper för att använda schemat.</span><span class="sxs-lookup"><span data-stu-id="616de-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="616de-133">Observera att även om du kan använda en befintlig innehållstyp för att utnyttja schemat för att hjälpa till med identifiering och klassificering, måste du fortfarande träna din modell att extrahera information från filer som den identifierar.</span><span class="sxs-lookup"><span data-stu-id="616de-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="616de-135">Lägga till dina exempelfiler</span><span class="sxs-lookup"><span data-stu-id="616de-135">Add your example files</span></span>

<span data-ttu-id="616de-136">På modellens startsida kan du lägga till exempelfiler som du behöver för att träna modellen för att identifiera dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="616de-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="616de-137">Samma filer bör användas för både klassificerare och [utsugsträning](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="616de-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="616de-138">Du har alltid möjlighet att lägga till fler senare, men vanligtvis bör du lägga till en fullständig uppsättning exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="616de-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="616de-139">Du kommer att märka några för att träna din modell, och testa de återstående omärkta dem för att utvärdera modell kondition.</span><span class="sxs-lookup"><span data-stu-id="616de-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="616de-140">För din träningsuppsättning vill du använda både positiva exempel och negativa exempel:</span><span class="sxs-lookup"><span data-stu-id="616de-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="616de-141">Positivt exempel: Dokument som representerar dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="616de-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="616de-142">De innehåller strängar och information som alltid skulle finnas i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="616de-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="616de-143">Negativt exempel: Dokument som inte representerar dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="616de-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="616de-144">De saknar strängar och information som måste finnas i den här typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="616de-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="616de-145">Du kommer att vilja använda minst fem positiva exempel och ett negativt exempel för att träna din modell.</span><span class="sxs-lookup"><span data-stu-id="616de-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="616de-146">Du kommer att vilja ha ytterligare för att testa din modell efter träningen.</span><span class="sxs-lookup"><span data-stu-id="616de-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="616de-147">Så här lägger du till exempelfiler:</span><span class="sxs-lookup"><span data-stu-id="616de-147">To add sample files:</span></span>

1. <span data-ttu-id="616de-148">Klicka på **Lägg till filer**i panelen Skapa exempelbibliotek på startsidan för **byggprovsbibliotek** .</span><span class="sxs-lookup"><span data-stu-id="616de-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="616de-149">På sidan **Välj exempelfiler för modell** väljer du exempelfilerna från exempelfilsbiblioteket i Innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="616de-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="616de-150">Om du inte redan hade laddat upp dem där kan du välja att ladda upp dem nu genom att klicka på **Ladda upp** för att flytta dem till exempelfilbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="616de-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="616de-151">När du har valt dina exempelfiler som ska användas för att träna modellen klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="616de-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="616de-153">Märka exempelfilerna</span><span class="sxs-lookup"><span data-stu-id="616de-153">Label your example files</span></span>

<span data-ttu-id="616de-154">När du har lagt till dina exempelfiler måste du sedan märka dem som antingen positiva exempel eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="616de-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="616de-155">Klicka på **Träna klassificerare**på startsidan för modellen. **Classify files and run training**</span><span class="sxs-lookup"><span data-stu-id="616de-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="616de-156">Då visas etikettsidan som visar en lista över dina exempelfiler, med den första filen synlig i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="616de-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="616de-157">I visningsprogrammet, högst upp i den första exempelfilen, visas text som frågar dig om filen är ett exempel på den modell som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="616de-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="616de-158">Om det är ett positivt exempel väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="616de-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="616de-159">Om det är ett negativt exempel väljer du **Nej**.</span><span class="sxs-lookup"><span data-stu-id="616de-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="616de-160">I listan **Märkta exempel** till vänster väljer du ytterligare filer som du vill använda som exempel och även märker dem.</span><span class="sxs-lookup"><span data-stu-id="616de-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Klassenyrmodells hemsida](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="616de-162">Märk minst fem positiva exempel och ett negativt exempel.</span><span class="sxs-lookup"><span data-stu-id="616de-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="616de-163">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="616de-163">Create an explanation</span></span>

<span data-ttu-id="616de-164">Nästa steg är att skapa en förklaring på sidan Tåg.</span><span class="sxs-lookup"><span data-stu-id="616de-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="616de-165">En förklaring är en ledtråd eller ledtråd för att hjälpa modellen att förstå hur man känner igen det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="616de-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="616de-166">Våra dokument för kontraktsförnyelse innehåller till exempel alltid en *begäran om ytterligare textsträng för information.*</span><span class="sxs-lookup"><span data-stu-id="616de-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="616de-167">När du använder med utt extraherare används en förklaring för att identifiera strängen som du vill extrahera från dokumentet.</span><span class="sxs-lookup"><span data-stu-id="616de-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="616de-168">Så här skapar du en förklaring:</span><span class="sxs-lookup"><span data-stu-id="616de-168">To create an explanation:</span></span>

1. <span data-ttu-id="616de-169">Klicka på fliken **Tåg** på modellens startsida för att gå till sidan Tåg.</span><span class="sxs-lookup"><span data-stu-id="616de-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="616de-170">På sidan Tåg visas en lista över exempelfiler som du har märkt tidigare i avsnittet **Tränade filer.**</span><span class="sxs-lookup"><span data-stu-id="616de-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="616de-171">Välj en av dina positiva filer i listan och den visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="616de-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="616de-172">Klicka på **Nytt**i avsnittet Förklaring och klicka sedan på **Tom**.</span><span class="sxs-lookup"><span data-stu-id="616de-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="616de-173">På sidan **Skapa en förklaring:**</span><span class="sxs-lookup"><span data-stu-id="616de-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="616de-174">a.</span><span class="sxs-lookup"><span data-stu-id="616de-174">a.</span></span> <span data-ttu-id="616de-175">Skriv **namnet** (till exempel "Disclosure Block").</span><span class="sxs-lookup"><span data-stu-id="616de-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="616de-176">b.</span><span class="sxs-lookup"><span data-stu-id="616de-176">b.</span></span> <span data-ttu-id="616de-177">Välj **typ**.</span><span class="sxs-lookup"><span data-stu-id="616de-177">Select the **Type**.</span></span> <span data-ttu-id="616de-178">I vårt exempel väljer vi **Fraslista**eftersom vi lägger till en textsträng.</span><span class="sxs-lookup"><span data-stu-id="616de-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="616de-179">c.</span><span class="sxs-lookup"><span data-stu-id="616de-179">c.</span></span> <span data-ttu-id="616de-180">Skriv strängen i rutan **Typ här.**</span><span class="sxs-lookup"><span data-stu-id="616de-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="616de-181">I vårt exempel lägger vi till "Begäran om ytterligare avslöjande".</span><span class="sxs-lookup"><span data-stu-id="616de-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="616de-182">Du kan välja **Skiftlägeskänslig** om strängen måste vara skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="616de-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="616de-183">d.</span><span class="sxs-lookup"><span data-stu-id="616de-183">d.</span></span> <span data-ttu-id="616de-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="616de-184">Click **Save**.</span></span>

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="616de-186">Modellen kommer nu att kontrollera om förklaringen du skapade var tillräckligt bra för att identifiera dina återstående märkta exempelfiler korrekt som positiva och negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="616de-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="616de-187">I avsnittet Tränade filer kontrollerar du kolumnen **Utvärdering** efter att utbildningen har slutförts för att se resultaten.</span><span class="sxs-lookup"><span data-stu-id="616de-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="616de-188">Filerna visar värdet **Matchning** om förklaringen du skapade var tillräckligt för att matcha vad du hade märkt dem som (positiva eller negativa).</span><span class="sxs-lookup"><span data-stu-id="616de-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Skapa förklaring](../media/content-understanding/match.png) 

<span data-ttu-id="616de-190">Om du får en **felmatchning** på dina märkta filer kan du behöva skapa ytterligare en förklaring för att ge modellen mer information för att identifiera dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="616de-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="616de-191">Du kan klicka på filen för att få mer information om varför obalansen inträffade.</span><span class="sxs-lookup"><span data-stu-id="616de-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="616de-192">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="616de-192">Test your model</span></span>

<span data-ttu-id="616de-193">Om du har fått en matchning på dina märkta exempelfiler kan du nu testa modellen på de återstående omärkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="616de-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="616de-194">Klicka på fliken **Testa** på modellens startsida.  Då körs modellen på de omärkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="616de-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="616de-195">I listan **Testa filer** visas dina exempelfiler och visas om modellen förutspådde att de skulle vara positiva eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="616de-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="616de-196">Du kan använda den här informationen för att avgöra hur effektiv klassificeraren är när det gäller att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="616de-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa omärkta filer](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="616de-198">Se även</span><span class="sxs-lookup"><span data-stu-id="616de-198">See Also</span></span>
[<span data-ttu-id="616de-199">Skapa en utsutorn</span><span class="sxs-lookup"><span data-stu-id="616de-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="616de-200">Översikt över dokuments förståelse</span><span class="sxs-lookup"><span data-stu-id="616de-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="616de-201">Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="616de-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="616de-202">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="616de-202">Apply a model</span></span>](apply-a-model.md) 




