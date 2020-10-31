---
title: Skapa en klassificerare
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Lär dig att skapa en klassificerare
ms.openlocfilehash: 97a7b28d45499a46d72029d47b422d2c32696a54
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804821"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="632b6-103">Skapa en klassificerare i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="632b6-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="632b6-104">En klassificerare är en modelltyp som du kan använda för att automatisera identifiering och klassificering av en dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="632b6-105">Du kanske, till exempel, vill identifiera alla *Kontraktförnyelse* dokument som har lagts till i ditt dokumentbibliotek, som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="632b6-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Kontraktförnyelse dokumentet](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="632b6-107">Genom att skapa en klassificerare kan du skapa en ny [SharePoint Innehållstyp](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som ska associeras med modellen.</span><span class="sxs-lookup"><span data-stu-id="632b6-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="632b6-108">När du skapar en klassificerare behöver du skapa *förklaringar* för att definiera modellen.</span><span class="sxs-lookup"><span data-stu-id="632b6-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="632b6-109">På så sätt kan du notera vanliga data som du skulle förvänta dig att konsekvent hitta den här dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="632b6-110">Använd exempel på dokumenttypen ("exempelfiler") för att "träna" din modell för att identifiera filer som har samma innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="632b6-111">För att skapa en klassificerare behöver du:</span><span class="sxs-lookup"><span data-stu-id="632b6-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="632b6-112">Ge din modell ett namn.</span><span class="sxs-lookup"><span data-stu-id="632b6-112">Name your model.</span></span>
2. <span data-ttu-id="632b6-113">Lägg till dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="632b6-113">Add your example files.</span></span>
3. <span data-ttu-id="632b6-114">Märka dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="632b6-114">Label your example files.</span></span>
4. <span data-ttu-id="632b6-115">Skapa en förklaring.</span><span class="sxs-lookup"><span data-stu-id="632b6-115">Create an explanation.</span></span>
5. <span data-ttu-id="632b6-116">Testa din modell.</span><span class="sxs-lookup"><span data-stu-id="632b6-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="632b6-117">Medan din modell använder en klassificerare för att identifiera och klassificera dokumenttyper, kan du också välja att hämta specifika delar av information från varje fil som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="632b6-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="632b6-118">Gör detta genom att skapa en **extraktor** för att lägga till din modell.</span><span class="sxs-lookup"><span data-stu-id="632b6-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="632b6-119">Se [Skapa en extraherare](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="632b6-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="632b6-120">Ge din modell ett namn</span><span class="sxs-lookup"><span data-stu-id="632b6-120">Name your model</span></span>

<span data-ttu-id="632b6-121">Första steget för att skapa din modell är att ge den ett namn:</span><span class="sxs-lookup"><span data-stu-id="632b6-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="632b6-122">I Innehållscentret välj **Ny** och sedan **Skapa en modell** .</span><span class="sxs-lookup"><span data-stu-id="632b6-122">From the content center, select **New** , and then **Create a model** .</span></span>
2. <span data-ttu-id="632b6-123">I **Ny modell för dokumenttolkning** fönstret, i **Namn** fältet, skrev namnet på modellen.</span><span class="sxs-lookup"><span data-stu-id="632b6-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="632b6-124">Om du, till exempel, vill identifiera kontraktförnyelse dokument, skulle du kunna get modellen namnet *Kontraktförnyelse* .</span><span class="sxs-lookup"><span data-stu-id="632b6-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal* .</span></span>
3. <span data-ttu-id="632b6-125">Välj **Skapa** .</span><span class="sxs-lookup"><span data-stu-id="632b6-125">Choose **Create** .</span></span> <span data-ttu-id="632b6-126">Då skapas en startsida för modellen.</span><span class="sxs-lookup"><span data-stu-id="632b6-126">This creates a home page for the model.</span></span></br>

    ![Startsidan för Klassificeringsmodellen](../media/content-understanding/model-home.png)

<span data-ttu-id="632b6-128">När du skapar en modell skapar du också en ny typ av webbplatsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="632b6-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="632b6-129">En innehållstyp representerar en kategori med dokument som har gemensamma egenskaper och delar en samling kolumner eller metadata för det specifika innehåll.</span><span class="sxs-lookup"><span data-stu-id="632b6-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="632b6-130">SharePoint Innehållstyper hanteras via [Innehållstyper galleri](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="632b6-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="632b6-131">I det här exemplet när du skapar modellen skapar du en ny *Kontraktförnyelse* innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="632b6-132">Välj **Avancerade inställningar** om du vill mappa denna modell till en befintlig företagsinnehållstyp i SharePoint Innehållstyp galleriet för att använda dess schema.</span><span class="sxs-lookup"><span data-stu-id="632b6-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="632b6-133">Företagsinnehållstyper lagras i Innehållstypsnav i SharePoint administrationscentret och syndikeras till alla webbplatser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="632b6-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="632b6-134">Notera att när du kan använda en befintlig innehållstyp för att använda sitt schema för att hjälpa till med identifiering och klassificering behöver du ändå träna din modell för att extrahera information från filerna som identifieras.</span><span class="sxs-lookup"><span data-stu-id="632b6-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Avancerade inställningar](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="632b6-136">Lägg till dina exempelfiler</span><span class="sxs-lookup"><span data-stu-id="632b6-136">Add your example files</span></span>

<span data-ttu-id="632b6-137">På modellens startsida lägger du till de exempelfilerna som du kommer att behöva för att träna modellen att identifiera din dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="632b6-138">Du bör använda samma filer för både klassificerare och [extraktorträning](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="632b6-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="632b6-139">Du kan alltid välja att lägga till mer senare, men vanligtvis lägger du till en hel uppsättning exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="632b6-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="632b6-140">Märka några för att träna din modell och testa de återstående omärkta för att utvärdera modellens fitness.</span><span class="sxs-lookup"><span data-stu-id="632b6-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="632b6-141">För din träning vill du använda både positiva och negativa exempel:</span><span class="sxs-lookup"><span data-stu-id="632b6-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="632b6-142">Positivt exempel: Dokument som representerar dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="632b6-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="632b6-143">Dessa innehåller strängar och information som alltid ska vara i den här dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="632b6-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="632b6-144">Negativt exempel: Alla andra dokument som inte representerar dokumentet du vill klassificera.</span><span class="sxs-lookup"><span data-stu-id="632b6-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="632b6-145">Se till att använda minst fem positiva exempel och minst ett negativt exempel för att träna din modell.</span><span class="sxs-lookup"><span data-stu-id="632b6-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="632b6-146">Du vill skapa ytterligare för att testa din modell efter utbildningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="632b6-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="632b6-147">Lägg till exempelfiler:</span><span class="sxs-lookup"><span data-stu-id="632b6-147">To add example files:</span></span>

1. <span data-ttu-id="632b6-148">På modellens startsida, i **Lägg till exempel filer** panelen klicka **Lägg till filer** .</span><span class="sxs-lookup"><span data-stu-id="632b6-148">On the model home page, in the **Add example files** tile, click **Add files** .</span></span>
2. <span data-ttu-id="632b6-149">På sidan **Välj exempelfiler för din modell** välj dina exempelfiler från biblioteket för utbildningsfiler i innehållscentret.</span><span class="sxs-lookup"><span data-stu-id="632b6-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="632b6-150">Om du inte redan har laddat upp dem där, välj att ladda upp dem nu genom att klicka på **Ladda upp** för att kopiera dem till biblioteket för utbildningsfiler.</span><span class="sxs-lookup"><span data-stu-id="632b6-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="632b6-151">När du har valt dina exempel-filer som ska användas för att träna modellen klicka på **Lägg till** .</span><span class="sxs-lookup"><span data-stu-id="632b6-151">After selecting your example files to use to train the model, click **Add** .</span></span>

    ![Välj exempelfiler](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="632b6-153">Märka dina exempelfiler</span><span class="sxs-lookup"><span data-stu-id="632b6-153">Label your example files</span></span>

<span data-ttu-id="632b6-154">När du har lagt till dina exempelfiler behöver du ge dem etiketter som positiva eller negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="632b6-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="632b6-155">Gå till modellens startsida och på den **Klassificera filer och kör utbildningen** panel, klicka på **Träna Klassificerare** .</span><span class="sxs-lookup"><span data-stu-id="632b6-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier** .</span></span>
   <span data-ttu-id="632b6-156">Etikett sidan visas med en lista över dina exempelfiler, med den första filen synlig i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="632b6-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="632b6-157">I visnings programmet längst upp i den första exempelfilen bör du se text som frågar om filen är ett exempel på modellen du just skapade.</span><span class="sxs-lookup"><span data-stu-id="632b6-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="632b6-158">Om det är ett positivt exempel välj **Ja** .</span><span class="sxs-lookup"><span data-stu-id="632b6-158">If it is a positive example, select **Yes** .</span></span> <span data-ttu-id="632b6-159">Om det är ett positivt exempel välj **Nej** .</span><span class="sxs-lookup"><span data-stu-id="632b6-159">If it is a negative example, select **No** .</span></span>
3. <span data-ttu-id="632b6-160">I **Märkta exempel** listan till vänster välj ytterligare filer som du vill använda som exempel och märk dem.</span><span class="sxs-lookup"><span data-stu-id="632b6-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Startsida för Klassificerare](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="632b6-162">Märk minst fem positiva exempel.</span><span class="sxs-lookup"><span data-stu-id="632b6-162">Label at least five positive examples.</span></span> <span data-ttu-id="632b6-163">Du måste också märka minst ett negativt exempel.</span><span class="sxs-lookup"><span data-stu-id="632b6-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="632b6-164">Skapa en förklaring</span><span class="sxs-lookup"><span data-stu-id="632b6-164">Create an explanation</span></span>

<span data-ttu-id="632b6-165">Nästa steget är att skapa en förklaring på Träningssidan.</span><span class="sxs-lookup"><span data-stu-id="632b6-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="632b6-166">En förklaring hjälper modellen att förstå hur man känner igen dokumentet.</span><span class="sxs-lookup"><span data-stu-id="632b6-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="632b6-167">Exempelvis innehåller Kontraktförnyelse dokument alltid en *Begäran om ytterligare avslöjande* textsträng.</span><span class="sxs-lookup"><span data-stu-id="632b6-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="632b6-168">När den används med extraktors, identifierar en förklaring den sträng som du vill extrahera från dokumentet.</span><span class="sxs-lookup"><span data-stu-id="632b6-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="632b6-169">För att skapa en förklaring:</span><span class="sxs-lookup"><span data-stu-id="632b6-169">To create an explanation:</span></span>

1. <span data-ttu-id="632b6-170">På modellens startsida välj fliken **Träna** för att gå till Träningssidan.</span><span class="sxs-lookup"><span data-stu-id="632b6-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="632b6-171">På Träningssidan, i sektionen **Tränade filer** bör du se en lista över de exempelfiler som du tidigare har märkt.</span><span class="sxs-lookup"><span data-stu-id="632b6-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="632b6-172">Välj en av de positiva filerna i listan och den visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="632b6-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="632b6-173">I Förklaringssektionen välj **Ny** och sedan **Blank** .</span><span class="sxs-lookup"><span data-stu-id="632b6-173">In the Explanation section, select **New** and then **Blank** .</span></span>
4. <span data-ttu-id="632b6-174">På sidan för **Skapa en förklaring** :</span><span class="sxs-lookup"><span data-stu-id="632b6-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="632b6-175">a.</span><span class="sxs-lookup"><span data-stu-id="632b6-175">a.</span></span> <span data-ttu-id="632b6-176">Skriv **Namnet** (till exempel "Avslöjande Block").</span><span class="sxs-lookup"><span data-stu-id="632b6-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="632b6-177">b.</span><span class="sxs-lookup"><span data-stu-id="632b6-177">b.</span></span> <span data-ttu-id="632b6-178">Välj **Typ** .</span><span class="sxs-lookup"><span data-stu-id="632b6-178">Select the **Type** .</span></span> <span data-ttu-id="632b6-179">I exemplet välj **Fraslista** eftersom du lägger till en textsträng.</span><span class="sxs-lookup"><span data-stu-id="632b6-179">For the sample, select **Phrase list** , since you add a text string.</span></span></br>
    <span data-ttu-id="632b6-180">c.</span><span class="sxs-lookup"><span data-stu-id="632b6-180">c.</span></span> <span data-ttu-id="632b6-181">I rutan **Skriv här** skriver du strängen.</span><span class="sxs-lookup"><span data-stu-id="632b6-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="632b6-182">För exemplet, lägg till "Begäran om ytterligare avslöjande".</span><span class="sxs-lookup"><span data-stu-id="632b6-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="632b6-183">Du kan välja **Skiftlägeskänsliga** om strängen behöver vara skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="632b6-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="632b6-184">d.</span><span class="sxs-lookup"><span data-stu-id="632b6-184">d.</span></span> <span data-ttu-id="632b6-185">Klicka på **Spara** .</span><span class="sxs-lookup"><span data-stu-id="632b6-185">Click **Save** .</span></span>

    ![Skapa förklaring](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="632b6-187">Nu kontrolleras Innehållscentret för att se om förklaringen du skapade var tillräckligt komplett för att identifiera de återstående märkta exempelfilerna korrekt, som positiva och negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="632b6-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="632b6-188">I sektionen för Tränade filer, märk kolumnen **Utvärdering** när träningen har slutförts för att se resultatet.</span><span class="sxs-lookup"><span data-stu-id="632b6-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="632b6-189">Filerna visar ett värde för **Matchning** , om förklaringarna du skapade är tillräckliga för att matcha det som du har märkt som positivt eller negativt.</span><span class="sxs-lookup"><span data-stu-id="632b6-189">The files show a value of **Match** , if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Matchningsvärde](../media/content-understanding/match.png) 

<span data-ttu-id="632b6-191">Om du får en **Matchningsfel** på de märkta filerna kan du behöva skapa en ytterligare förklaring för att ge modellen mer information för att identifiera dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="632b6-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="632b6-192">I så fall klickar du på filen för att få mer information om varför matchningsfelet har uppstått.</span><span class="sxs-lookup"><span data-stu-id="632b6-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="632b6-193">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="632b6-193">Test your model</span></span>

<span data-ttu-id="632b6-194">Om du får en matchning för dina etiketterade exempelfiler kan du nu testa din modell på de återstående omärkta exempelfilerna som modellen inte har sett tidigare.</span><span class="sxs-lookup"><span data-stu-id="632b6-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="632b6-195">Det här är valfritt, men ett användbart steg för att utvärdera "lämpligheten" eller beredskapen av modellen innan användning är genom att testa den på filer som modellen inte har sett tidigare.</span><span class="sxs-lookup"><span data-stu-id="632b6-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="632b6-196">Från modellens startsida välj fliken **Test** .  Då körs modellen på dina omärkta exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="632b6-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="632b6-197">I listan **Testfiler** visas dina exempelfiler och visar om modellen har uppskattad de som positiva eller negativa.</span><span class="sxs-lookup"><span data-stu-id="632b6-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="632b6-198">Använd den här informationen för att ta reda på hur effektivt din klassificerare är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="632b6-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test av omärkta filer](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="632b6-200">Se även</span><span class="sxs-lookup"><span data-stu-id="632b6-200">See Also</span></span>
[<span data-ttu-id="632b6-201">Skapa en extraherare</span><span class="sxs-lookup"><span data-stu-id="632b6-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="632b6-202">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="632b6-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="632b6-203">Förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="632b6-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="632b6-204">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="632b6-204">Apply a model</span></span>](apply-a-model.md) 
