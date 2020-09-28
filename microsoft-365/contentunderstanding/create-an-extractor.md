---
title: Skapa en Extractor
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
description: Lär dig hur du skapar en Extractor i Microsoft SharePoint-Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295462"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="eff89-103">Skapa en Extractor (för hands version)</span><span class="sxs-lookup"><span data-stu-id="eff89-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="eff89-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="eff89-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="eff89-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="eff89-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="eff89-106">Innan eller efter du skapar en klassificerings modell för att automatisera identifiering och klassificering av specifika dokument typer kan du välja att lägga till utdrag i din modell för att hämta specifik information från dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="eff89-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="eff89-107">Du kanske till exempel vill använda modellen för att identifiera alla *förnyelse* dokument som lagts till i dokument biblioteket, utan även för att visa *tjänstens start datum* för varje dokument som en kolumn i dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="eff89-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="eff89-108">Du måste skapa en Extractor för varje enhet i dokumentet som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="eff89-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="eff89-109">I exemplet vill du extrahera *tjänstens start datum* för varje *kontrakt förnyelse* dokument som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="eff89-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="eff89-110">Det här måste inträffa när du vill visa en vy i dokument biblioteket för alla *kontrakt förnyelse* dokument med en kolumn som visar värdet för tjänste start datum för varje dokument.</span><span class="sxs-lookup"><span data-stu-id="eff89-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="eff89-111">Innan du skapar en Extractor måste du [lägga till dina exempel filer](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) för att träna modellen att identifiera informationen som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="eff89-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="eff89-112">Använd samma exempelfiler som du använde när du skapade klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="eff89-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="eff89-113">Ge din Extractor ett namn</span><span class="sxs-lookup"><span data-stu-id="eff89-113">Name your extractor</span></span>

1. <span data-ttu-id="eff89-114">Klicka på **träna Extractor**på panelen **skapa och träna extrakt** på modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="eff89-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="eff89-115">På sidan **ny enhets Extractor** skriver du namnet på din Extractor i fältet **ny Extractor-namn** .</span><span class="sxs-lookup"><span data-stu-id="eff89-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="eff89-116">Om du till exempel vill extrahera tjänstens start datum från varje avtal för förnyelse av kontrakt namnger du Start datumet för **tjänsten** .</span><span class="sxs-lookup"><span data-stu-id="eff89-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="eff89-117">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="eff89-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="eff89-118">Lägga till en etikett</span><span class="sxs-lookup"><span data-stu-id="eff89-118">Add a label</span></span>

<span data-ttu-id="eff89-119">Nästa steg är att förse den information som du vill ha med i exempel utbildnings filerna.</span><span class="sxs-lookup"><span data-stu-id="eff89-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="eff89-120">När du skapar Extractor öppnas sidan Extractor.</span><span class="sxs-lookup"><span data-stu-id="eff89-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="eff89-121">Här visas en lista över dina exempelfiler med den första filen i listan som visas i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="eff89-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="eff89-122">Markera de data som du vill extrahera från filerna i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="eff89-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="eff89-123">Om du till exempel vill extrahera *Start tjänst datum*markerar du datumet i den första filen (*måndag 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="eff89-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="eff89-124">och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eff89-124">and then click **Save**.</span></span>  <span data-ttu-id="eff89-125">Du bör se värde visningen från filen i listan med namngivna exempel under kolumnen **etikett** .</span><span class="sxs-lookup"><span data-stu-id="eff89-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="eff89-126">Välj **nästa fil** om du vill spara automatiskt och öppna nästa fil i listan i visnings programmet.</span><span class="sxs-lookup"><span data-stu-id="eff89-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="eff89-127">Eller Välj **Spara** och välj sedan en annan fil i listan med **Etiketter** .</span><span class="sxs-lookup"><span data-stu-id="eff89-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="eff89-128">Upprepa steg 1 och 2 i visnings programmet och upprepa sedan tills du sparade etiketten i alla fem filer.</span><span class="sxs-lookup"><span data-stu-id="eff89-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="eff89-130">Lägga till ett negativt exempel</span><span class="sxs-lookup"><span data-stu-id="eff89-130">Add a negative example</span></span>

<span data-ttu-id="eff89-131">På samma sätt som du lägger till en negativ exempel fil när du skapar en klassificerare måste du lägga till ett negativt prov för Extractor.</span><span class="sxs-lookup"><span data-stu-id="eff89-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="eff89-132">Det bör vara en fil som inte innehåller ett datum värde för "tjänst start".</span><span class="sxs-lookup"><span data-stu-id="eff89-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="eff89-133">Välj ett negativt exempel i listan med **Etiketter** .</span><span class="sxs-lookup"><span data-stu-id="eff89-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="eff89-134">I visnings programmet högst upp i artikeln väljer du **ingen etikett presentation**.</span><span class="sxs-lookup"><span data-stu-id="eff89-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="eff89-135">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eff89-135">Click **Save**.</span></span>
 
<span data-ttu-id="eff89-136">När du har märkt fem filer visas ett meddelande som informerar dig om att flytta till utbildning.</span><span class="sxs-lookup"><span data-stu-id="eff89-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="eff89-137">Du kan välja fler dokument eller gå vidare till utbildning.</span><span class="sxs-lookup"><span data-stu-id="eff89-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="eff89-138">Lägga till en förklaring</span><span class="sxs-lookup"><span data-stu-id="eff89-138">Add an explanation</span></span>

<span data-ttu-id="eff89-139">Du kan till exempel skapa en förklaring om själva enhets formatet och variationer i exempel dokumenten.</span><span class="sxs-lookup"><span data-stu-id="eff89-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="eff89-140">Ett datum värde kan till exempel vara i ett antal olika format, som:</span><span class="sxs-lookup"><span data-stu-id="eff89-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="eff89-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="eff89-141">10/14/2019</span></span>
- <span data-ttu-id="eff89-142">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="eff89-142">October 14, 2019</span></span>
- <span data-ttu-id="eff89-143">Måndagen den 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="eff89-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="eff89-144">För att identifiera *tjänstens start datum* kan du skapa en mönster förklaring.</span><span class="sxs-lookup"><span data-stu-id="eff89-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="eff89-145">I avsnittet förklaring väljer du **nytt** och skriver ett namn (till exempel *datum*).</span><span class="sxs-lookup"><span data-stu-id="eff89-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="eff89-146">Välj **mönster lista**för typ.</span><span class="sxs-lookup"><span data-stu-id="eff89-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="eff89-147">För värde anger du datum variationen så som den visas i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="eff89-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="eff89-148">Om du till exempel har datum format som visas som 0/00/0000, anger du de variationer som visas i dokumenten, som:</span><span class="sxs-lookup"><span data-stu-id="eff89-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="eff89-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="eff89-149">0/0/0000</span></span>
    - <span data-ttu-id="eff89-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="eff89-150">0/00/0000</span></span>
    - <span data-ttu-id="eff89-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="eff89-151">00/0/0000</span></span>
    - <span data-ttu-id="eff89-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="eff89-152">00/00/0000</span></span>
4. <span data-ttu-id="eff89-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eff89-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="eff89-154">Använda förklarings biblioteket</span><span class="sxs-lookup"><span data-stu-id="eff89-154">Use the Explanation library</span></span>

<span data-ttu-id="eff89-155">När du skapar förklaringar för objekt, till exempel datum, är det enklare att använda förklarings biblioteket än att manuellt ange alla variationer.</span><span class="sxs-lookup"><span data-stu-id="eff89-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="eff89-156">Förklarings biblioteket är en uppsättning fördefinierade fraser och mönster förklaringar.</span><span class="sxs-lookup"><span data-stu-id="eff89-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="eff89-157">Biblioteket innehåller alla format för vanliga fras-och mönster listor, till exempel datum, telefonnummer, post nummer osv.</span><span class="sxs-lookup"><span data-stu-id="eff89-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="eff89-158">För test av *tjänstens start datum* är det mer effektivt att använda den färdiga förklaringen för *datum* i förklarings biblioteket:</span><span class="sxs-lookup"><span data-stu-id="eff89-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="eff89-159">I **avsnittet förklaring**väljer du **nytt**och väljer sedan **från förklarings bibliotek**.</span><span class="sxs-lookup"><span data-stu-id="eff89-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="eff89-160">Välj **datum**i förklarings biblioteket.</span><span class="sxs-lookup"><span data-stu-id="eff89-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="eff89-161">Du kan visa alla variationer av datum som känns igen.</span><span class="sxs-lookup"><span data-stu-id="eff89-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="eff89-162">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="eff89-162">Select **Add**.</span></span></br>

    ![Förklarings bibliotek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="eff89-164">På sidan **skapa en förklaring** fylls fälten automatiskt i med *datum* informationen från förklarings biblioteket.</span><span class="sxs-lookup"><span data-stu-id="eff89-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="eff89-165">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eff89-165">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="eff89-167">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="eff89-167">Train the model</span></span> 

<span data-ttu-id="eff89-168">När du sparar din förklaring är det bara att börja öva.</span><span class="sxs-lookup"><span data-stu-id="eff89-168">Saving your explanation start the training.</span></span> <span data-ttu-id="eff89-169">Om din modell har tillräckligt med information för att extrahera data från dina namngivna exempelfiler visas varje fil med etiketten **matcha**.</span><span class="sxs-lookup"><span data-stu-id="eff89-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Matcha](../media/content-understanding/match2.png) 

<span data-ttu-id="eff89-171">Om förklaringen inte innehåller tillräckligt med information för att hitta de data som du vill extrahera är varje fil märkt med **fel**.</span><span class="sxs-lookup"><span data-stu-id="eff89-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="eff89-172">Du kan klicka på de **felmatchade** filerna för att se mer information om varför det fanns ett fel.</span><span class="sxs-lookup"><span data-stu-id="eff89-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="eff89-173">Lägga till en förklaring</span><span class="sxs-lookup"><span data-stu-id="eff89-173">Add another explanation</span></span>

<span data-ttu-id="eff89-174">Ofta beror det på att den förklaring som vi tillhandahöll inte gav tillräckligt med information för att extrahera tjänstens start datum för att matcha våra etiketterade filer.</span><span class="sxs-lookup"><span data-stu-id="eff89-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="eff89-175">Du kan behöva redigera den eller lägga till en annan förklaring.</span><span class="sxs-lookup"><span data-stu-id="eff89-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="eff89-176">Observera att text strängens *start datum* alltid föregår det faktiska värdet för provet.</span><span class="sxs-lookup"><span data-stu-id="eff89-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="eff89-177">För att hjälpa till att identifiera tjänstens start datum måste du skapa en menings förklaring.</span><span class="sxs-lookup"><span data-stu-id="eff89-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="eff89-178">I avsnittet förklaring väljer du **nytt**och anger sedan ett namn (till exempel en *prefixlängd*).</span><span class="sxs-lookup"><span data-stu-id="eff89-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="eff89-179">Välj **fras lista**för typen.</span><span class="sxs-lookup"><span data-stu-id="eff89-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="eff89-180">Använd *tjänstens start datum* som värde.</span><span class="sxs-lookup"><span data-stu-id="eff89-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="eff89-181">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eff89-181">Select **Save**.</span></span>

    ![Prefixlängd](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="eff89-183">Träna modellen igen</span><span class="sxs-lookup"><span data-stu-id="eff89-183">Train the model again</span></span>

<span data-ttu-id="eff89-184">Om du sparar förklaringen startas utbildningen igen, den här gången med hjälp av båda förklaringarna i exemplet.</span><span class="sxs-lookup"><span data-stu-id="eff89-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="eff89-185">Om din modell har tillräckligt med information för att extrahera data från de namngivna exempelfilerna kan du se varje fil med etiketten **matcha**.</span><span class="sxs-lookup"><span data-stu-id="eff89-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="eff89-186">Om du får ett fel meddelande om att dina etiketter **inte stämmer** överens måste du skapa en ny förklaring för att ge modellen mer information för att identifiera dokument typen eller överväga att ändra exempel modellen.</span><span class="sxs-lookup"><span data-stu-id="eff89-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="eff89-187">Testa modellen</span><span class="sxs-lookup"><span data-stu-id="eff89-187">Test your model</span></span>

<span data-ttu-id="eff89-188">Om du får en träff på dina etiketterade exempelfiler kan du testa modellen på de återstående icke-märkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="eff89-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="eff89-189">Klicka på fliken **test** på modell start sidan.  Då körs modellen på dina namnlösa exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="eff89-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="eff89-190">I listan **testfiler** visas dina exempel filer för att visa om modellen kan extrahera den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="eff89-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="eff89-191">Använd den här informationen för att fastställa hur din klassificerarens effektivitet är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="eff89-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa dina filer](../media/content-understanding/test-filies-extractor.png) 
