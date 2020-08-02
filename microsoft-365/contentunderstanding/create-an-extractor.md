---
title: Skapa en utsupre (förhandsgranskning)
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
description: Lär dig hur du skapar en utsugsor
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540112"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="4ccb4-103">Skapa en utsupre (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="4ccb4-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="4ccb4-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4ccb4-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4ccb4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="4ccb4-106">Antingen före eller efter att du har skapat en klassifierarmodell för att automatisera identifiering och klassificering av specifika dokumenttyper kan du också välja att lägga till utdrag till modellen för att hämta specifik information från dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="4ccb4-107">Du kanske till exempel vill att modellen inte bara ska identifiera alla dokument för *kontraktsförnyelse* som läggs till i dokumentbiblioteket, utan även visa *startdatumet* för tjänsten för varje dokument som en kolumn i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="4ccb4-108">Du måste skapa en utsutorn för varje entitet i dokumentet som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="4ccb4-109">I vårt exempel vill vi extrahera *tjänstens startdatum* för varje *kontraktsförnyelsedokument* som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="4ccb4-110">Vi vill kunna se en vy i dokumentbiblioteket för alla dokument *för kontraktsförnyelse,* med en kolumn som visar värdet för tjänstens startdatum för varje dokument.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="4ccb4-111">Innan du skapar en extractor måste du lägga till [dina exempelfiler](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) måste du hjälpa till att träna modellen för att identifiera den information du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="4ccb4-112">Använd samma exempelfiler som du använde för att skapa klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="4ccb4-113">Namnge din utsug</span><span class="sxs-lookup"><span data-stu-id="4ccb4-113">Name your extractor</span></span>

1. <span data-ttu-id="4ccb4-114">Klicka på **Tågutsugor**i panelen **Skapa och träna utsug** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="4ccb4-115">På skärmen **Ny entitetsutextör** skriver du namnet på extraheraren i fältet **Nytt utdragsnamn.**</span><span class="sxs-lookup"><span data-stu-id="4ccb4-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="4ccb4-116">Vi kan till exempel namnge det **Tjänstens startdatum** om vi vill extrahera tjänstens startdatum från varje dokument för kontraktsförnyelse.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="4ccb4-117">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="4ccb4-118">Lägga till en etikett</span><span class="sxs-lookup"><span data-stu-id="4ccb4-118">Add a label</span></span>

<span data-ttu-id="4ccb4-119">Nästa steg är att märka den information som du vill extrahera i dina exempel träningsfiler.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="4ccb4-120">Om du skapar utdragsbladet öppnas utsugssidan där du ser en lista över dina exempelfiler, med den första filen i listan som visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="4ccb4-121">Markera de data som du vill extrahera från filerna i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="4ccb4-122">Om du till exempel vill extrahera *starttjänstdatumet*markerar du datumvärdet för det i den första filen (*måndag 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="4ccb4-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="4ccb4-123">Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-123">Then click **Save**.</span></span>  <span data-ttu-id="4ccb4-124">Du ser värdevisningen för filen i listan Märkta exempel under kolumnen **Etikett.**</span><span class="sxs-lookup"><span data-stu-id="4ccb4-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="4ccb4-125">Välj **Nästa fil** om du vill spara automatiskt och öppna nästa fil i listan i visningsprogrammet, eller så kan du välja **Spara** och välja en annan fil i listan **Märkta exempel.**</span><span class="sxs-lookup"><span data-stu-id="4ccb4-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="4ccb4-126">Upprepa steg 1 och 2 i visningsprogrammet och gör detta tills du har sparat etiketten i fem filer.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="4ccb4-128">Lägga till ett negativt exempel</span><span class="sxs-lookup"><span data-stu-id="4ccb4-128">Add a negative example</span></span>

<span data-ttu-id="4ccb4-129">På samma sätt som du vill lägga till en negativ exempelfil när du skapar en klassificerare måste du lägga till ett negativt exempel för utsugaren.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="4ccb4-130">Det bör till exempel vara en fil som inte innehåller ett startdatum för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="4ccb4-131">Välj ett negativt exempel i listan **Märkta exempel.**</span><span class="sxs-lookup"><span data-stu-id="4ccb4-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="4ccb4-132">Välj **Ingen etikett på**artikelns överkant i visningsprogrammet .</span><span class="sxs-lookup"><span data-stu-id="4ccb4-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="4ccb4-133">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-133">Click **Save**.</span></span>
 
<span data-ttu-id="4ccb4-134">När du har märkt fem filer visas en meddelandebanderoll där du informerar dig om att gå över till träningen.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="4ccb4-135">Du kan välja att fler dokument eller gå vidare till utbildning.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="4ccb4-136">Lägga till en förklaring</span><span class="sxs-lookup"><span data-stu-id="4ccb4-136">Add an explanation</span></span>

<span data-ttu-id="4ccb4-137">Vi kommer till exempel att skapa en förklaring som ger en ledtråd om själva enhetsformatet och variationer som den kan ha i exempeldokumenten.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="4ccb4-138">Ett datumvärde kan till exempel finnas i ett antal olika format, till exempel:</span><span class="sxs-lookup"><span data-stu-id="4ccb4-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="4ccb4-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="4ccb4-139">10/14/2019</span></span>
- <span data-ttu-id="4ccb4-140">den 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="4ccb4-140">October 14, 2019</span></span>
- <span data-ttu-id="4ccb4-141">måndagen den 14:e oktober 2019</span><span class="sxs-lookup"><span data-stu-id="4ccb4-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="4ccb4-142">För att identifiera *tjänstens startdatum* kan du skapa en mönsterförklaring.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="4ccb4-143">I avsnittet Förklaring väljer du **Nytt**och skriver sedan ett namn (till exempel *Datum*).</span><span class="sxs-lookup"><span data-stu-id="4ccb4-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="4ccb4-144">För listan Typ väljer du **Mönsterlista**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="4ccb4-145">För värdet måste du ange datumvariationen så som de visas i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="4ccb4-146">Om du till exempel har datumformat som visas som 0000-00-00 kan du ange alla variationer som kan visas i dina dokument, till exempel:</span><span class="sxs-lookup"><span data-stu-id="4ccb4-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="4ccb4-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="4ccb4-147">0/0/0000</span></span>
    - <span data-ttu-id="4ccb4-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="4ccb4-148">0/00/0000</span></span>
    - <span data-ttu-id="4ccb4-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="4ccb4-149">00/0/0000</span></span>
    - <span data-ttu-id="4ccb4-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="4ccb4-150">00/00/0000</span></span>
4. <span data-ttu-id="4ccb4-151">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="4ccb4-152">Använda förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="4ccb4-152">Use the Explanation library</span></span>

<span data-ttu-id="4ccb4-153">För att skapa förklaringar till saker som datum är det mycket enklare att använda förklaringsbiblioteket än att manuellt ange alla varianter.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="4ccb4-154">Förklaringsbiblioteket är en uppsättning färdiga fras- och mönsterförklaringar.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="4ccb4-155">Biblioteket försöker ange alla format för vanliga fras- eller mönsterlistor, till exempel datum, telefonnummer, postnummer och många andra.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="4ccb4-156">För vårt exempel *på tjänstens startdatum* är det mer effektivt att använda den färdiga förklaringen till *Datum* i förklaringsbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="4ccb4-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="4ccb4-157">Välj **Nytt**i **avsnittet Förklaring**och välj sedan **Från förklaringsbiblioteket**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="4ccb4-158">Välj **Datum**i förklaringsbiblioteket .</span><span class="sxs-lookup"><span data-stu-id="4ccb4-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="4ccb4-159">Du kan visa alla ändringar av datum som ska identifieras.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="4ccb4-160">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-160">Select **Add**.</span></span></br>

    ![Förklaringsbibliotek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="4ccb4-162">På sidan **Skapa en förklaring** fylls fälten i *datuminformationen* från förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="4ccb4-163">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-163">Select **Save**.</span></span></br>

    ![Förklaringsbibliotek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="4ccb4-165">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="4ccb4-165">Train the model</span></span> 

<span data-ttu-id="4ccb4-166">Spara din förklaring kommer att starta utbildningen.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="4ccb4-167">Om modellen har tillräckligt med information för att extrahera data från de märkta exempelfilerna visas varje fil med **matcha**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Förklaringsbibliotek](../media/content-understanding/match2.png) 

<span data-ttu-id="4ccb4-169">Om förklaringen inte har tillräckligt med information för att hitta de data du vill extrahera, kommer varje fil att märkas med **Felmatchning**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="4ccb4-170">Du kan klicka på filerna som inte stämmer överens för att se mer information om varför det fanns en obalans.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="4ccb4-171">Lägg till en annan förklaring</span><span class="sxs-lookup"><span data-stu-id="4ccb4-171">Add another explanation</span></span>

<span data-ttu-id="4ccb4-172">Ofta är obalansen en indikation på att förklaringen vi gav inte gav tillräckligt med information för att extrahera tjänstens startdatumvärde för att matcha våra märkta filer.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="4ccb4-173">Du kan behöva redigera den eller lägga till en annan förklaring.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="4ccb4-174">Vi märker till exempel att textsträngen *Startservicedatum* för alltid föregår det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="4ccb4-175">För att identifiera tjänstens startdatum kan vi skapa en frasförklaring.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="4ccb4-176">I avsnittet Förklaring väljer du **Nytt**och skriver sedan ett namn (till exempel *Prefixsträng*).</span><span class="sxs-lookup"><span data-stu-id="4ccb4-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="4ccb4-177">För text väljer du **Fraslista**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="4ccb4-178">Använd *Tjänstens startdatum* för som värde.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="4ccb4-179">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-179">Select **Save**.</span></span>

    ![Förklaringsbibliotek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="4ccb4-181">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="4ccb4-181">Train the model</span></span>

<span data-ttu-id="4ccb4-182">Spara din förklaring kommer att starta utbildningen igen, denna gång med hjälp av båda förklaringarna i vårt exempel.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="4ccb4-183">Om modellen har tillräckligt med information för att extrahera data från de märkta exempelfilerna visas varje fil med **matcha**.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="4ccb4-184">Om du återigen får en **felmatchning** på dina märkta filer kan du behöva skapa en annan förklaring för att ge modellen mer information för att identifiera dokumenttypen eller titta på att göra ändringar i dina befintliga.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4ccb4-185">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="4ccb4-185">Test your model</span></span>

<span data-ttu-id="4ccb4-186">Om du har fått en matchning på dina märkta exempelfiler kan du nu testa modellen på de återstående omärkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="4ccb4-187">Klicka på fliken **Testa** på modellens startsida.  Då körs modellen på de omärkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="4ccb4-188">I listan **Testa filer** visas dina exempelfiler och visar om modellen kan extrahera den information du behöver från dem.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="4ccb4-189">Du kan använda den här informationen för att avgöra hur effektiv klassificeraren är när det gäller att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="4ccb4-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa på dina filer](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="4ccb4-191">Se även</span><span class="sxs-lookup"><span data-stu-id="4ccb4-191">See Also</span></span>
  




