---
title: Steg 1. Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/17/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du använder SharePoint Syntex för att identifiera kontraktsfiler och extrahera data med hjälp av en Microsoft 365 lösning.
ms.openlocfilehash: f246dd4ed619dd9885d2c45c69d607cfa9c2483f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538561"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="c74f1-104">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="c74f1-104">Step 1.</span></span> <span data-ttu-id="c74f1-105">Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data</span><span class="sxs-lookup"><span data-stu-id="c74f1-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="c74f1-106">Din organisation behöver ett sätt att identifiera och klassificera alla kontraktsdokument från de många filer du får.</span><span class="sxs-lookup"><span data-stu-id="c74f1-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="c74f1-107">Du vill också snabbt kunna visa flera nyckelelement i var och en av de identifierade kontraktsfilerna (till exempel *kund,* entreprenör *och* *avgiftsbelopp).*</span><span class="sxs-lookup"><span data-stu-id="c74f1-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="c74f1-108">Det kan du göra genom att [SharePoint Syntex för](index.md) att skapa en dokumentförståelsemodell och använda den på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="c74f1-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="c74f1-109">Översikt över processen</span><span class="sxs-lookup"><span data-stu-id="c74f1-109">Overview of the process</span></span>

<span data-ttu-id="c74f1-110">[Dokument förstå](document-understanding-overview.md) använder artificiell intelligens (AI) modeller för att automatisera klassificering av filer och extrahering av information.</span><span class="sxs-lookup"><span data-stu-id="c74f1-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="c74f1-111">Dokument förstå modeller är också optimala för att extrahera information från ostrukturerade och semi-strukturerade dokument där den information du behöver inte finns i tabeller eller formulär, till exempel kontrakt.</span><span class="sxs-lookup"><span data-stu-id="c74f1-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="c74f1-112">Först måste du hitta minst fem exempelfiler som du kan använda för att "utbilda" modellen för att söka efter egenskaper som är specifika för den innehållstyp som du försöker identifiera (ett kontrakt).</span><span class="sxs-lookup"><span data-stu-id="c74f1-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="c74f1-113">Med SharePoint Syntex kan du skapa en ny modell för dokumentförståelse.</span><span class="sxs-lookup"><span data-stu-id="c74f1-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="c74f1-114">När du använder exempelfilerna måste [du skapa en klassificerare](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="c74f1-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="c74f1-115">Genom att utbilda klassificeraren med dina exempelfiler lär du dig att söka efter egenskaper som är specifika för det du skulle se i företagets kontrakt.</span><span class="sxs-lookup"><span data-stu-id="c74f1-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="c74f1-116">Skapa till [exempel en "förklaring"](create-a-classifier.md#create-an-explanation) som söker efter specifika strängar som finns i ditt avtal, till exempel *Tjänstavtal,* *Avtalsvillkor* och *Kompensation.*</span><span class="sxs-lookup"><span data-stu-id="c74f1-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="c74f1-117">Du kan till och med utbilda din förklaring så att du kan leta efter de här strängarna i specifika avsnitt i dokumentet eller ligga bredvid andra strängar.</span><span class="sxs-lookup"><span data-stu-id="c74f1-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="c74f1-118">När du tror att du har utbildat din klassificerare med den information som behövs kan du testa modellen på en exempeluppsättning exempelfiler för att se hur effektivt den är.</span><span class="sxs-lookup"><span data-stu-id="c74f1-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="c74f1-119">Efter att ha testat kan du, om det behövs, välja att ändra dina förklaringar för att göra dem mer effektiva.</span><span class="sxs-lookup"><span data-stu-id="c74f1-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="c74f1-120">I modellen kan du skapa [en extraherare för att](create-an-extractor.md) hämta specifika data från varje kontrakt.</span><span class="sxs-lookup"><span data-stu-id="c74f1-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="c74f1-121">För varje kontrakt är den information som du är mest orolig för till exempel vem klienten är, namnet på entreprenören och totalkostnaden.</span><span class="sxs-lookup"><span data-stu-id="c74f1-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="c74f1-122">När du har skapat din modell kan [du använda den på SharePoint ett dokumentbibliotek](apply-a-model.md).</span><span class="sxs-lookup"><span data-stu-id="c74f1-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="c74f1-123">När du laddar upp dokument till dokumentbiblioteket körs dokument förstå modellen för dokument och kommer att identifiera och klassificera alla filer som matchar den typ av innehåll som du har definierat i modellen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="c74f1-124">Alla filer som klassificeras som kontrakt visas i en anpassad biblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="c74f1-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="c74f1-125">Filerna visar också värdena från varje kontrakt som du definierade i extraheraren.</span><span class="sxs-lookup"><span data-stu-id="c74f1-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Kontrakt i dokumentbibliotek](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="c74f1-127">Om du har kvarhållningskrav för kontrakten kan [](apply-a-retention-label-to-a-model.md) du även använda modellen för att använda en bevarandeetikett som gör att kontrakten inte raderas under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="c74f1-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="c74f1-128">Steg för att skapa och utbilda din modell</span><span class="sxs-lookup"><span data-stu-id="c74f1-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="c74f1-129">För de här stegen kan du använda exempelfilerna i [Microsoft SharePoint Syntex Samples-lagringsplatsen](https://github.com/pnp/syntex-samples).</span><span class="sxs-lookup"><span data-stu-id="c74f1-129">For these steps, you can use the example files in the [Microsoft SharePoint Syntex Samples repository](https://github.com/pnp/syntex-samples).</span></span> <span data-ttu-id="c74f1-130">Exemplen på den här lagringsplatsen innehåller både modellfiler för dokument förstå och filer som används för att utbilda modellen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-130">The samples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="c74f1-131">Skapa en kontraktsmodell</span><span class="sxs-lookup"><span data-stu-id="c74f1-131">Create a Contract model</span></span>

<span data-ttu-id="c74f1-132">Det första steget är att skapa din kontraktsmodell.</span><span class="sxs-lookup"><span data-stu-id="c74f1-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="c74f1-133">I Innehållscentret välj **Ny** och sedan **Skapa en modell**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="c74f1-134">I fönstret **Nytt dokument förstå modell** skriver du **namnet** på modellen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c74f1-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="c74f1-135">För den här kontraktshanteringslösningen kan du namnge modellen *Kontrakt.*</span><span class="sxs-lookup"><span data-stu-id="c74f1-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="c74f1-136">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-136">Choose **Create**.</span></span> <span data-ttu-id="c74f1-137">Då skapas en startsida för modellen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-137">This creates a home page for the model.</span></span></br>

    ![Skärmbild av startsidan för Avtal.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="c74f1-139">Utbilda din modell för att klassificera en typ av fil</span><span class="sxs-lookup"><span data-stu-id="c74f1-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="c74f1-140">Lägga till exempelfiler för modellen</span><span class="sxs-lookup"><span data-stu-id="c74f1-140">Add example files for your model</span></span>

<span data-ttu-id="c74f1-141">Du måste lägga till minst fem exempelfiler som är kontraktsdokument och en exempelfil som inte är ett kontraktsdokument (till exempel en arbetshandling).</span><span class="sxs-lookup"><span data-stu-id="c74f1-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="c74f1-142">På sidan **Modeller > Kontrakt under** Nyckelåtgärder Lägg till   >  **exempelfiler** väljer du Lägg **till filer.**</span><span class="sxs-lookup"><span data-stu-id="c74f1-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Skärmbild som visar sidan Kontrakt med alternativet Lägg till exempelfiler markerat.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="c74f1-144">På sidan **Välj exempelfiler för modellen** öppnar du mappen Kontrakt, väljer de filer du vill använda och väljer sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="c74f1-145">Om du inte har exempelfiler där väljer du Ta Upload för **att** lägga till dem.</span><span class="sxs-lookup"><span data-stu-id="c74f1-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="c74f1-146">Märka filerna som positiva eller negativa exempel</span><span class="sxs-lookup"><span data-stu-id="c74f1-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="c74f1-147">På sidan **Modeller > kontrakt** under **nyckelåtgärder**  >  **Klassificera filer och kör utbildning** väljer du **Utbildaren**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Skärmbild som visar sidan Kontrakt med alternativet Klassificera filer och kör utbildning markerat.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="c74f1-149">På sidan **Modeller >** kontrakt > kontrakts klassificerare, i visningsprogrammet högst upp i den första exempelfilen, visas text som frågar om filen är ett exempel på den kontraktsmodell du skapade.</span><span class="sxs-lookup"><span data-stu-id="c74f1-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="c74f1-150">Om det är ett positivt exempel välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="c74f1-151">Om det är ett positivt exempel välj **Nej**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="c74f1-152">I listan **Exempel med etiketter** till vänster väljer du andra filer som du vill använda som exempel och etiketterar dem.</span><span class="sxs-lookup"><span data-stu-id="c74f1-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Startsida för Klassificerare](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;c74f1-154&quot;>Lägga till minst en förklaring för att utbilda klassificeraren</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;c74f1-155&quot;>Välj **fliken > > på** sidan Modeller eller > kontrakt. </span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;c74f1-156&quot;>I avsnittet **Utbildningerade** filer visas en lista över de exempelfiler som du tidigare har etiketterat.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;c74f1-157&quot;>Välj en av de positiva filerna i listan för att visa den i visningsprogrammet.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;c74f1-158&quot;>I avsnittet **Förklaringar** väljer du **Nytt** och sedan **Tom**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;c74f1-159&quot;>På sidan för **Skapa en förklaring**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;c74f1-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c74f1-160&quot;>a.</span></span> <span data-ttu-id=&quot;c74f1-161&quot;>I fältet **Namn** skriver du namnet på förklaringen (till exempel &quot;Avtal").</span><span class="sxs-lookup"><span data-stu-id="c74f1-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="c74f1-162">b.</span><span class="sxs-lookup"><span data-stu-id="c74f1-162">b.</span></span> <span data-ttu-id="c74f1-163">I fältet **Förklaringstyp** väljer du **Fraslista eftersom** du lägger till en textsträng.</span><span class="sxs-lookup"><span data-stu-id="c74f1-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="c74f1-164">c.</span><span class="sxs-lookup"><span data-stu-id="c74f1-164">c.</span></span> <span data-ttu-id="c74f1-165">I **listrutan Fras** skriver du strängen (till exempel "AVTALET").</span><span class="sxs-lookup"><span data-stu-id="c74f1-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="c74f1-166">Du kan välja **Case sensitive** om strängen måste vara fallkänslig.</span><span class="sxs-lookup"><span data-stu-id="c74f1-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="c74f1-167">d.</span><span class="sxs-lookup"><span data-stu-id="c74f1-167">d.</span></span> <span data-ttu-id="c74f1-168">Välj **Spara och utbilda**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-168">Select **Save and train**.</span></span>

    ![Skärmbild av panelen Skapa en förklaring.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="c74f1-170">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="c74f1-170">Test your model</span></span>

<span data-ttu-id="c74f1-171">Du kan testa din kontraktsmodell på exempelfiler som den inte har sett förut.</span><span class="sxs-lookup"><span data-stu-id="c74f1-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="c74f1-172">Det här är valfritt, men det kan vara användbart.</span><span class="sxs-lookup"><span data-stu-id="c74f1-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="c74f1-173">På sidan **> eller > kontrakt väljer** du **fliken** Test. Det här kör modellen på de exempelfiler du inte har namn på.</span><span class="sxs-lookup"><span data-stu-id="c74f1-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="c74f1-174">I listan **Testfiler** visas och visas exempelfilerna om modellen förutsagt dem som positiva eller negativa.</span><span class="sxs-lookup"><span data-stu-id="c74f1-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="c74f1-175">Använd den här informationen för att ta reda på hur effektivt din klassificerare är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="c74f1-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Skärmbild av de oetiketterade filerna i listan Textfiler](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="c74f1-177">När du är klar väljer **du Avsluta utbildning**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="c74f1-178">Skapa och utbilda en extraherare</span><span class="sxs-lookup"><span data-stu-id="c74f1-178">Create and train an extractor</span></span>

1. <span data-ttu-id="c74f1-179">På sidan **Modeller > Kontrakt** under **Nyckelåtgärder Skapa** och träna  >  **extraherare** väljer du Skapa **extraherare**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Skärmbild som visar sidan Kontrakt med alternativet Skapa och utbildare markerat.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="c74f1-181">Skriv **namnet på extraheraren** i fältet **Nytt namn** på panelen Ny entitet extraheraren.</span><span class="sxs-lookup"><span data-stu-id="c74f1-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="c74f1-182">Ge den till exempel *namnet Klient* om du vill extrahera namnet på klienten från varje avtal.</span><span class="sxs-lookup"><span data-stu-id="c74f1-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="c74f1-183">När du är klar väljer du **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="c74f1-184">Märk den entitet som du vill extrahera</span><span class="sxs-lookup"><span data-stu-id="c74f1-184">Label the entity you want to extract</span></span>

<span data-ttu-id="c74f1-185">När du skapar extraheraren öppnas extraherarsidan.</span><span class="sxs-lookup"><span data-stu-id="c74f1-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="c74f1-186">Här visas en lista över dina exempelfiler, och den första filen i listan visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="c74f1-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Skärmbild av sidan Exempel med klientutdrag eller etiketter.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="c74f1-188">Så här märks entiteten:</span><span class="sxs-lookup"><span data-stu-id="c74f1-188">To label the entity:</span></span>

1. <span data-ttu-id="c74f1-189">Välj de data från visningsprogrammet som du vill extrahera från filerna.</span><span class="sxs-lookup"><span data-stu-id="c74f1-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="c74f1-190">Om du till exempel vill extrahera *Klienten* markerar du klientvärdet i den första filen (i det här exemplet *Bäst* för dig organiskt) och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="c74f1-191">Du ser värdet som visas från filen i listan **Exempel på etiketter** under **kolumnen** Etikett.</span><span class="sxs-lookup"><span data-stu-id="c74f1-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="c74f1-192">Välj **Nästa fil** för att spara automatiskt och öppna nästa fil i listan i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="c74f1-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="c74f1-193">Eller välj **Spara** och välj sedan en annan fil i **listan Exempel med etiketter.**</span><span class="sxs-lookup"><span data-stu-id="c74f1-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="c74f1-194">Upprepa steg 1 och 2 i visningsprogrammet och upprepa sedan tills du har sparat etiketten i alla filer.</span><span class="sxs-lookup"><span data-stu-id="c74f1-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="c74f1-195">När du har etiketterat filerna visas en meddelandebanderoll med information om att gå över till utbildningen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="c74f1-196">Du kan välja att märka fler dokument eller gå vidare till utbildningen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="c74f1-197">Lägg till förklaring</span><span class="sxs-lookup"><span data-stu-id="c74f1-197">Add an explanation</span></span>

<span data-ttu-id="c74f1-198">Du kan skapa en förklaring som ger en ledtråd om själva entitetsformatet och variationer som det kan ha i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="c74f1-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="c74f1-199">Ett datumvärde kan till exempel ha många olika format, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c74f1-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="c74f1-200">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="c74f1-200">10/14/2019</span></span>
- <span data-ttu-id="c74f1-201">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="c74f1-201">October 14, 2019</span></span>
- <span data-ttu-id="c74f1-202">Måndag, den 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="c74f1-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="c74f1-203">Du kan skapa en *mönsterförklaring för* att identifiera startdatumet för avtalet.</span><span class="sxs-lookup"><span data-stu-id="c74f1-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="c74f1-204">I avsnittet **Förklaringar** väljer du **Nytt** och sedan **Tom**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="c74f1-205">På sidan för **Skapa en förklaring**:</span><span class="sxs-lookup"><span data-stu-id="c74f1-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="c74f1-206">a.</span><span class="sxs-lookup"><span data-stu-id="c74f1-206">a.</span></span> <span data-ttu-id="c74f1-207">I fältet **Namn** skriver du namnet på förklaringen (till exempel *Datum).*</span><span class="sxs-lookup"><span data-stu-id="c74f1-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="c74f1-208">b.</span><span class="sxs-lookup"><span data-stu-id="c74f1-208">b.</span></span> <span data-ttu-id="c74f1-209">I fältet **Förklaringstyp** väljer du **Mönsterlista**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="c74f1-210">c.</span><span class="sxs-lookup"><span data-stu-id="c74f1-210">c.</span></span> <span data-ttu-id="c74f1-211">Ange **datumvariationen** så som de visas i exempelfilerna i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="c74f1-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="c74f1-212">Om du, till exempel, har datumformat som visas som 0/00/0000, kan du ange en variation som visas i dina dokument, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c74f1-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="c74f1-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="c74f1-213">0/0/0000</span></span>
    - <span data-ttu-id="c74f1-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="c74f1-214">0/00/0000</span></span>
    - <span data-ttu-id="c74f1-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="c74f1-215">00/0/0000</span></span>
    - <span data-ttu-id="c74f1-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="c74f1-216">00/00/0000</span></span>

4. <span data-ttu-id="c74f1-217">Välj **Spara och utbilda**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="c74f1-218">Testa modellen igen</span><span class="sxs-lookup"><span data-stu-id="c74f1-218">Test your model again</span></span>

<span data-ttu-id="c74f1-219">Du kan testa din kontraktsmodell på exempelfiler som den inte har sett förut.</span><span class="sxs-lookup"><span data-stu-id="c74f1-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="c74f1-220">Det här är valfritt, men det kan vara användbart.</span><span class="sxs-lookup"><span data-stu-id="c74f1-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="c74f1-221">På sidan **> eller > kontrakt väljer** du **fliken** Test. Det här kör modellen på de exempelfiler du inte har namn på.</span><span class="sxs-lookup"><span data-stu-id="c74f1-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="c74f1-222">I listan **Testa filer** visas exempelfilerna och visar om modellen kan extrahera den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="c74f1-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="c74f1-223">Använd den här informationen för att ta reda på hur effektivt din klassificerare är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="c74f1-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="c74f1-224">När du är klar väljer **du Avsluta utbildning**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="c74f1-225">Använda modellen på ett dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="c74f1-225">Apply your model to a document library</span></span>

<span data-ttu-id="c74f1-226">Så här använder du modellen på SharePoint ett dokumentbibliotek:</span><span class="sxs-lookup"><span data-stu-id="c74f1-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="c74f1-227">På sidan **Modeller > Kontrakt** under Nyckelåtgärder **Använd** modell för  >  **bibliotek väljer** du Använd **modell.**</span><span class="sxs-lookup"><span data-stu-id="c74f1-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Skärmbild som visar sidan Kontrakt med alternativet Använd modell för bibliotek markerat.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="c74f1-229">På panelen **Lägg till** kontrakt väljer du den SharePoint som innehåller det dokumentbibliotek där du vill använda modellen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="c74f1-230">Om webbplatsen inte visas i listan kan du använda sökrutan för att hitta den.</span><span class="sxs-lookup"><span data-stu-id="c74f1-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="c74f1-231">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c74f1-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c74f1-232">Du måste ha behörighet för *Hantera list* eller *Redigera* för det dokumentbibliotek som du använder modellen på.</span><span class="sxs-lookup"><span data-stu-id="c74f1-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="c74f1-233">När du har valt webbplatsen väljer du det dokumentbibliotek där du vill använda modellen.</span><span class="sxs-lookup"><span data-stu-id="c74f1-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="c74f1-234">Eftersom modellen är kopplad till en innehållstyp kommer innehållstypen och dess vy att läggas till med etiketterna som du extraherade och visas som kolumner när du använder den på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="c74f1-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="c74f1-235">Den här vyn är bibliotekets standardvy som standard, men du kan välja att  den inte  ska vara standardvyn genom att markera Avancerade inställningar och avmarkera kryssrutan Ange den här nya vyn som standard.</span><span class="sxs-lookup"><span data-stu-id="c74f1-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="c74f1-236">Välj **Lägg till** för att tillämpa modellen på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="c74f1-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="c74f1-237">I **avsnittet Bibliotek >** denna modell  på sidan Modeller eller kontrakt ser du URL-adressen till den SharePoint visas.</span><span class="sxs-lookup"><span data-stu-id="c74f1-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Skärmbild av startsidan för Avtal som visar biblioteken med den här modellens avsnitt.](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="c74f1-239">När du har tillämpat modellen på dokumentbiblioteket kan du börja ladda upp dokument till webbplatsen och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="c74f1-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="c74f1-240">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c74f1-240">Next step</span></span>

[<span data-ttu-id="c74f1-241">Steg 2. Använd Microsoft Teams för att skapa din kanal för kontraktshantering</span><span class="sxs-lookup"><span data-stu-id="c74f1-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)