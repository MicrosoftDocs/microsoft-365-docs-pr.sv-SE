---
title: Skapa en Extractor (för hands version)
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
description: Lär dig hur du skapar en Extractor
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612768"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="f8da0-103">Skapa en Extractor (för hands version)</span><span class="sxs-lookup"><span data-stu-id="f8da0-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="f8da0-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="f8da0-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f8da0-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f8da0-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="f8da0-106">Antingen förut eller efter att du har skapat en klassificerings modell för att automatisera identifiering och klassificering av specifika dokument typer kan du välja att lägga till utdrag i din modell för att hämta specifik information från dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="f8da0-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="f8da0-107">Du kanske till exempel vill använda modellen för att identifiera alla *förnyelse* dokument som läggs till i dokument biblioteket, men om du även vill visa *tjänstens start datum* för varje dokument som en kolumn i dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="f8da0-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="f8da0-108">Du måste skapa en Extractor för varje enhet i dokumentet som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="f8da0-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="f8da0-109">I vårt exempel vill vi extrahera *tjänstens start datum* för varje *kontrakt förnyelse* dokument som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="f8da0-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="f8da0-110">Vi vill kunna se en vy i dokument biblioteket för alla *förnyelse* dokument med en kolumn som visar värdet för tjänste start datum för varje dokument.</span><span class="sxs-lookup"><span data-stu-id="f8da0-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="f8da0-111">Innan du skapar en Extractor måste du [lägga till dina exempel filer](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) du måste hjälpa till att träna modellen för att identifiera informationen som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="f8da0-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="f8da0-112">Använd samma exempel filer som du använde när du skapade klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="f8da0-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="f8da0-113">Ge din Extractor ett namn</span><span class="sxs-lookup"><span data-stu-id="f8da0-113">Name your extractor</span></span>

1. <span data-ttu-id="f8da0-114">Klicka på **träna Extractor**på panelen **skapa och träna extrakt** på modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="f8da0-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="f8da0-115">På sidan **ny enhets Extractor** skriver du namnet på din Extractor i fältet **ny Extractor-namn** .</span><span class="sxs-lookup"><span data-stu-id="f8da0-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="f8da0-116">Vi kan till exempel ge **Start datumet** för den tjänsten om vi vill extrahera tjänstens start datum från varje kontrakt förnyelse dokument.</span><span class="sxs-lookup"><span data-stu-id="f8da0-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="f8da0-117">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="f8da0-118">Lägga till en etikett</span><span class="sxs-lookup"><span data-stu-id="f8da0-118">Add a label</span></span>

<span data-ttu-id="f8da0-119">Nästa steg är att lägga till etiketter för den information som du vill ta fram i exempel utbildnings filerna.</span><span class="sxs-lookup"><span data-stu-id="f8da0-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="f8da0-120">När du skapar Extractor öppnas sidan Extractor där du ser en lista över dina exempelfiler, med den första filen i listan som visas i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="f8da0-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="f8da0-121">Markera de data som du vill extrahera från filerna i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="f8da0-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="f8da0-122">Om du till exempel vill extrahera *Start tjänst datum*markerar du datumvärdet för det i den första filen (*måndag den 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="f8da0-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="f8da0-123">Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-123">Then click **Save**.</span></span>  <span data-ttu-id="f8da0-124">Du ser värde visningen för filen i listan med namngivna exempel under kolumnen **etikett** .</span><span class="sxs-lookup"><span data-stu-id="f8da0-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="f8da0-125">Välj **nästa fil** för att spara automatiskt och öppna nästa fil i listan i visnings programmet, eller så kan du välja **Spara** och välja en annan fil i listan med **Etiketter** .</span><span class="sxs-lookup"><span data-stu-id="f8da0-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="f8da0-126">Upprepa steg 1 och 2 i visnings programmet tills du har sparat etiketten i fem filer.</span><span class="sxs-lookup"><span data-stu-id="f8da0-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="f8da0-128">Lägga till ett negativt exempel</span><span class="sxs-lookup"><span data-stu-id="f8da0-128">Add a negative example</span></span>

<span data-ttu-id="f8da0-129">På samma sätt som när du lägger till en negativ exempel fil när du skapar en klassificerare måste du lägga till ett negativt exempel för Extractor.</span><span class="sxs-lookup"><span data-stu-id="f8da0-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="f8da0-130">I vårt exempel ska det vara en fil som inte innehåller ett start datum värde.</span><span class="sxs-lookup"><span data-stu-id="f8da0-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="f8da0-131">Välj ett negativt exempel i listan med **Etiketter** .</span><span class="sxs-lookup"><span data-stu-id="f8da0-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="f8da0-132">Välj **ingen etikett tillgänglig**längst upp i artikeln i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="f8da0-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="f8da0-133">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-133">Click **Save**.</span></span>
 
<span data-ttu-id="f8da0-134">När du har märkt fem filer visas en meddelande banderoll som informerar dig om att flytta till utbildning.</span><span class="sxs-lookup"><span data-stu-id="f8da0-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="f8da0-135">Du kan välja fler dokument eller gå vidare till utbildning.</span><span class="sxs-lookup"><span data-stu-id="f8da0-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="f8da0-136">Lägga till en förklaring</span><span class="sxs-lookup"><span data-stu-id="f8da0-136">Add an explanation</span></span>

<span data-ttu-id="f8da0-137">I vårt exempel håller vi på att skapa en förklaring om själva enhets formatet och variationer den kan ha i exemplen.</span><span class="sxs-lookup"><span data-stu-id="f8da0-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="f8da0-138">Ett datum värde kan till exempel vara i ett antal olika format, som:</span><span class="sxs-lookup"><span data-stu-id="f8da0-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="f8da0-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="f8da0-139">10/14/2019</span></span>
- <span data-ttu-id="f8da0-140">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="f8da0-140">October 14, 2019</span></span>
- <span data-ttu-id="f8da0-141">Måndagen den 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="f8da0-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="f8da0-142">För att identifiera *tjänstens start datum* kan du skapa en mönster förklaring.</span><span class="sxs-lookup"><span data-stu-id="f8da0-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="f8da0-143">I avsnittet förklaring väljer du **nytt**och skriver sedan ett namn (till exempel *datum*).</span><span class="sxs-lookup"><span data-stu-id="f8da0-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="f8da0-144">Välj **mönster lista**för typen.</span><span class="sxs-lookup"><span data-stu-id="f8da0-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="f8da0-145">För värdet måste du ange datum variationen så som de visas i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="f8da0-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="f8da0-146">Om du till exempel har datum format som visas som 0/00/0000, anger du eventuella variationer som kan visas i dina dokument, som:</span><span class="sxs-lookup"><span data-stu-id="f8da0-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="f8da0-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="f8da0-147">0/0/0000</span></span>
    - <span data-ttu-id="f8da0-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="f8da0-148">0/00/0000</span></span>
    - <span data-ttu-id="f8da0-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="f8da0-149">00/0/0000</span></span>
    - <span data-ttu-id="f8da0-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="f8da0-150">00/00/0000</span></span>
4. <span data-ttu-id="f8da0-151">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="f8da0-152">Använda förklarings biblioteket</span><span class="sxs-lookup"><span data-stu-id="f8da0-152">Use the Explanation library</span></span>

<span data-ttu-id="f8da0-153">När du skapar förklaringar för till exempel datum, är det mycket lättare att använda förklarings biblioteket än att manuellt ange alla variationer.</span><span class="sxs-lookup"><span data-stu-id="f8da0-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="f8da0-154">Förklarings biblioteket är en uppsättning fördefinierade fraser och mönster förklaringar.</span><span class="sxs-lookup"><span data-stu-id="f8da0-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="f8da0-155">Biblioteket försöker tillhandahålla alla format för vanliga fras-och mönster listor, till exempel datum, telefonnummer, post nummer och många andra.</span><span class="sxs-lookup"><span data-stu-id="f8da0-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="f8da0-156">För vårt *start datum-* exempel är det mer effektivt att använda den färdiga förklaringen för *datum* i förklarings biblioteket:</span><span class="sxs-lookup"><span data-stu-id="f8da0-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="f8da0-157">I **avsnittet förklaring**\* \* väljer du **nytt**och väljer sedan **från förklarings bibliotek**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="f8da0-158">Välj **datum**i förklarings biblioteket.</span><span class="sxs-lookup"><span data-stu-id="f8da0-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="f8da0-159">Du kan visa alla datum variationer som kommer att kännas igen.</span><span class="sxs-lookup"><span data-stu-id="f8da0-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="f8da0-160">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-160">Select **Add**.</span></span></br>

    ![Förklarings bibliotek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="f8da0-162">På sidan **skapa en förklaring** fylls *datum* informationen från i förklarings biblioteket i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f8da0-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="f8da0-163">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-163">Select **Save**.</span></span></br>

    ![Förklarings bibliotek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="f8da0-165">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="f8da0-165">Train the model</span></span> 

<span data-ttu-id="f8da0-166">Om du sparar din förklaring kan du börja öva.</span><span class="sxs-lookup"><span data-stu-id="f8da0-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="f8da0-167">Om din modell har tillräckligt med information för att extrahera data från dina namngivna exempelfiler visas varje fil med etiketten **matcha**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Förklarings bibliotek](../media/content-understanding/match2.png) 

<span data-ttu-id="f8da0-169">Om förklaringen inte innehåller tillräckligt med information för att hitta de data som du vill extrahera är varje fil märkt med **fel**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="f8da0-170">Du kan klicka på de felmatchade filerna för att se mer information om varför det fanns ett fel.</span><span class="sxs-lookup"><span data-stu-id="f8da0-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="f8da0-171">Lägga till en förklaring</span><span class="sxs-lookup"><span data-stu-id="f8da0-171">Add another explanation</span></span>

<span data-ttu-id="f8da0-172">Ofta beror det på att den förklaring som vi tillhandahöll inte gav tillräckligt med information för att extrahera tjänstens start datum för att matcha våra etiketterade filer.</span><span class="sxs-lookup"><span data-stu-id="f8da0-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="f8da0-173">Du kan behöva redigera den eller lägga till en annan förklaring.</span><span class="sxs-lookup"><span data-stu-id="f8da0-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="f8da0-174">I vårt exempel noterar vi att text strängens *start datum* alltid föregår det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="f8da0-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="f8da0-175">För att identifiera start datumet för tjänsten kan vi skapa en menings förklaring.</span><span class="sxs-lookup"><span data-stu-id="f8da0-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="f8da0-176">I avsnittet förklaring väljer du **nytt**och anger sedan ett namn (till exempel en *prefixlängd*).</span><span class="sxs-lookup"><span data-stu-id="f8da0-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="f8da0-177">Välj **fras lista**för typen.</span><span class="sxs-lookup"><span data-stu-id="f8da0-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="f8da0-178">Använd *tjänstens start datum* som värde.</span><span class="sxs-lookup"><span data-stu-id="f8da0-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="f8da0-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-179">Select **Save**.</span></span>

    ![Förklarings bibliotek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="f8da0-181">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="f8da0-181">Train the model</span></span>

<span data-ttu-id="f8da0-182">Om du sparar din förklaring börjar utbildningen igen, den här gången med hjälp av båda förklaringarna i vårt exempel.</span><span class="sxs-lookup"><span data-stu-id="f8da0-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="f8da0-183">Om din modell har tillräckligt med information för att extrahera data från dina namngivna exempelfiler visas varje fil med etiketten **matcha**.</span><span class="sxs-lookup"><span data-stu-id="f8da0-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="f8da0-184">Om du får ett fel meddelande om att dina etiketter **inte stämmer** överens kan du behöva skapa en ny förklaring för att ge modellen mer information för att identifiera dokument typen eller se hur du ändrar dina befintliga.</span><span class="sxs-lookup"><span data-stu-id="f8da0-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="f8da0-185">Testa modellen</span><span class="sxs-lookup"><span data-stu-id="f8da0-185">Test your model</span></span>

<span data-ttu-id="f8da0-186">Om du har fått en matchning på dina etiketterade exempelfiler kan du testa modellen på dina återstående ljudfiler.</span><span class="sxs-lookup"><span data-stu-id="f8da0-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="f8da0-187">Klicka på fliken **testa** på modell start sidan.  Då körs modellen på dina namnlösa exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="f8da0-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="f8da0-188">I listan **testfiler** visas dina exempel filer och visar om modellen kan extrahera den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="f8da0-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="f8da0-189">Du kan använda den här informationen för att avgöra hur din klassificerarens effektivitet är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="f8da0-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa dina filer](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="f8da0-191">Se även</span><span class="sxs-lookup"><span data-stu-id="f8da0-191">See Also</span></span>
  




