---
title: Skapa en extraktor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Lär dig hur du skapar en extraktor i Microsoft SharePoint-Syntex.
ms.openlocfilehash: 99d2a4602c03d8a7207736ea17ed500626ce43ac
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087469"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="fb1e7-103">Skapa en extraktor i Microsoft SharePoint-Syntex.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="fb1e7-104">Före eller efter det att du har skapat en klassificeringsmodell för att automatisera identifieringen och klassifikationen av specifika dokumenttyper kan du välja att lägga till extraktorer i din modell för att hämta specifik information från de här dokumenten.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="fb1e7-105">Du kanske, till exempel, vill att din modell inte bara ska identifiera alla *Kontraktförnyelse* dokument som lagts till i ditt dokumentbiblioteket, utan också för att visa *Tjänstens Startdatum* för varje dokument som ett kolumnvärde i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="fb1e7-106">Du behöver skapa en extraktor för varje enhet i det dokument som du vill extrahera.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="fb1e7-107">I vårt exempel vill vi extrahera **Tjänstens Startdatum** för varje **Kontraktförnyelse** dokument som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="fb1e7-108">Vi vill kunna se en vy i dokumentbiblioteket för alla  **Kontraktförnyelse** dokument med en kolumn som visar **Tjänstens Start**-datum värde för varje dokument.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb1e7-109">För att skapa en extraktor använder du samma filer som du tidigare har laddat upp för att träna klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="fb1e7-110">Namnge din extraktor</span><span class="sxs-lookup"><span data-stu-id="fb1e7-110">Name your extractor</span></span>

1. <span data-ttu-id="fb1e7-111">Från modellens startsida, i **Skapa och träna extraktorer** panel och klicka på **Träna extraktor**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="fb1e7-112">På skärmen **Ny enhet extraktor** skriv in namnet på din extraktor i fältet **Nytt extraktor-namn**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="fb1e7-113">Om du, till exempel, namnge det **Tjänstens Startdatum** om du vill extrahera tjänstens startdatum från varje Kontraktförnyelse dokument.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="fb1e7-114">Du kan också välja att återanvända en tidigare skapad kolumn, (t. ex. en hanterad metadata kolumn).</span><span class="sxs-lookup"><span data-stu-id="fb1e7-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="fb1e7-115">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="fb1e7-116">Lägga till en etikett</span><span class="sxs-lookup"><span data-stu-id="fb1e7-116">Add a label</span></span>

<span data-ttu-id="fb1e7-117">Nästa steget är att sätta en etikett på den enhet du vill extrahera i dina utbildnings exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="fb1e7-118">När du skapar extraktor öppnas extraktorsidan.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="fb1e7-119">Här visas en lista över dina exempelfiler, och den första filen i listan visas i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="fb1e7-120">Välj de data från visningsprogrammet som du vill extrahera från filerna.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="fb1e7-121">Om du, till exempel, vill extrahera *Tjänstens Startdatum* markerar du datumet i den första filen (*måndag 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="fb1e7-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="fb1e7-122">och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-122">and then click **Save**.</span></span>  <span data-ttu-id="fb1e7-123">Du bör se värdet som visas från filen i listan med Etiketterade exempel under kolumnen **Etikett**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="fb1e7-124">Välj **Nästa fil** för att spara automatiskt och öppna nästa fil i listan i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="fb1e7-125">Eller välj **Spara** och sedan välj en annan fil från den **Etiketterade exempel** -listan.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="fb1e7-126">Upprepa steg 1 och 2 i visningsprogrammet och upprepa sedan tills du har sparat etiketten i alla fem filerna.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Avancerade inställningar](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="fb1e7-128">När du har etiketterade fem filer visas en meddelandebanderoll som informerar dig om att flytta till utbildning.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="fb1e7-129">Du kan välja att etikettera fler dokument eller att gå vidare till utbildning.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="fb1e7-130">Lägg till förklaring</span><span class="sxs-lookup"><span data-stu-id="fb1e7-130">Add an explanation</span></span>

<span data-ttu-id="fb1e7-131">I vårt exempel kommer vi att skapa en förklaring som ger en ledtråd om själva enhetsformatet och varianterna den kan ha i exempeldokumenten.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="fb1e7-132">Till exempel, ett datumvärde kan ha flera olika format, såsom:</span><span class="sxs-lookup"><span data-stu-id="fb1e7-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="fb1e7-133">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="fb1e7-133">10/14/2019</span></span>
- <span data-ttu-id="fb1e7-134">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="fb1e7-134">October 14, 2019</span></span>
- <span data-ttu-id="fb1e7-135">Måndag, den 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="fb1e7-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="fb1e7-136">För att identifiera *Tjänstens Startdatum* kan du skapa en förklaring av mönstret.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="fb1e7-137">I avsnittet Förklaringar välj **Ny** och skriv ett namn (t. ex. *Datum*).</span><span class="sxs-lookup"><span data-stu-id="fb1e7-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="fb1e7-138">För Typ välj **Mönsterlista**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="fb1e7-139">För Värde anger du datumvariationen så som de visas i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="fb1e7-140">Om du, till exempel, har datumformat som visas som 0/00/0000, kan du ange en variation som visas i dina dokument, till exempel:</span><span class="sxs-lookup"><span data-stu-id="fb1e7-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="fb1e7-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="fb1e7-141">0/0/0000</span></span>
    - <span data-ttu-id="fb1e7-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="fb1e7-142">0/00/0000</span></span>
    - <span data-ttu-id="fb1e7-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="fb1e7-143">00/0/0000</span></span>
    - <span data-ttu-id="fb1e7-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="fb1e7-144">00/00/0000</span></span>
4. <span data-ttu-id="fb1e7-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="fb1e7-146">Mer information om olika förklaringstyper finns i [Förklaringstyper](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="fb1e7-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="fb1e7-147">Använda Förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="fb1e7-147">Use the Explanation library</span></span>

<span data-ttu-id="fb1e7-148">För att skapa förklaringar för objekt, t. ex. datum, är det enklare att [använda förklaringsbiblioteket](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) än att ange alla variationer manuellt.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="fb1e7-149">Förklaringsbiblioteket är en uppsättning fördefinierade fraser och mönsterförklaringar.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="fb1e7-150">Biblioteket försöker tillhandahålla alla format för vanliga fras- eller mönster listor, till exempel datum, telefonnummer, postnummer och många andra.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="fb1e7-151">För *Tjänstens Startdatum* exempel är det mer effektivt att använda den fördefinierade förklaringen för *Datum* i förklaringsbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="fb1e7-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="fb1e7-152">I **Förklaringssektionen** välj **Ny** och välj sedan **From förklaringsbibliotek**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="fb1e7-153">Välj **Datum** från förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="fb1e7-154">Du kan visa alla datum variationer som är igenkända.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="fb1e7-155">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-155">Select **Add**.</span></span></br>

    ![Förklaringsbiblioteket](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="fb1e7-157">På sidan **Skapa en förklaring** kommer *Datum* informationen från förklaringensbiblioteket automatiskt fylla i fälten.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="fb1e7-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-158">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="fb1e7-160">Träna modellen</span><span class="sxs-lookup"><span data-stu-id="fb1e7-160">Train the model</span></span> 

<span data-ttu-id="fb1e7-161">Om du sparar förklaringen startar du utbildningen.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-161">Saving your explanation start the training.</span></span> <span data-ttu-id="fb1e7-162">Om din modell har tillräcklig information för att extrahera data från dina etiketterade exempelfiler, kommer du att se varje fil etiketterade med **Match**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="fb1e7-164">Om förklaringen inte har tillräcklig information för att hitta de data du vill extrahera kommer alla filer etiketteras med **Matchningsfel**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="fb1e7-165">För att se mer information om varför det fanns ett matchningsfel kan du klicka på de **Matchningsfel** filerna.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="fb1e7-166">Lägga till en till förklaring</span><span class="sxs-lookup"><span data-stu-id="fb1e7-166">Add another explanation</span></span>

<span data-ttu-id="fb1e7-167">Matchningsfelet är ofta en indikation på att förklaringen vi tillhandahöll inte innehöll tillräcklig information för att extrahera tjänstens startdatum för att matcha vår etiketterade filer.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="fb1e7-168">Du kan behöva redigera den eller lägga till ytterligare en förklaring.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="fb1e7-169">I vårt exempel kan du se att textsträngen *Starta Tjänstedatumet för* föregår alltid det verkliga värdet.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="fb1e7-170">För att identifiera Tjänstens Startdatum behöver du skapa en förklaring av frasen.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="fb1e7-171">I Förklaringssektionen välj **Ny** och sedan skriv ett namn (t. ex. *Prefixsträng*).</span><span class="sxs-lookup"><span data-stu-id="fb1e7-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="fb1e7-172">För Typ välj **Fraslista**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="fb1e7-173">Använd *Tjänstens Startdatum* som värde.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="fb1e7-174">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-174">Select **Save**.</span></span>

    ![Prefixsträng](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="fb1e7-176">Träna modellen igen</span><span class="sxs-lookup"><span data-stu-id="fb1e7-176">Train the model again</span></span>

<span data-ttu-id="fb1e7-177">Om du sparar förklaringen startar utbildningen igen, den här gången med hjälp av båda förklaringarna i exemplet.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="fb1e7-178">Om din modell har tillräcklig information för att extrahera data från dina etiketterade exempelfiler, kommer du att se varje fil etiketterade med **Match**.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="fb1e7-179">Om du får en **Matchningsfel** igen på dina etiketterade filer behöver du antagligen skapa ytterligare en förklaring för att ge modellen mer information för att identifiera dokumenttypen, eller så kan du göra ändringar i dina befintliga.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="fb1e7-180">Testa din modell</span><span class="sxs-lookup"><span data-stu-id="fb1e7-180">Test your model</span></span>

<span data-ttu-id="fb1e7-181">Om du får en matchning för dina etiketterade exempelfiler kan du nu testa din modell på de återstående omärkta exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="fb1e7-182">Det här är valfri, men ett användbar steg för att utvärdera "lämpligheten", eller beredskapen av modellen innan användning genom att testa den på filer som modellen inte har sett tidigare.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-182">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="fb1e7-183">Gå till start sidan för modellen och klicka på fliken **Test**.  Då körs modellen på dina omärkta exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="fb1e7-184">I **Testfil**-listan visas dina exempelfiler för att visa om modellen kan extrahera informationen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="fb1e7-185">Använd den här informationen för att ta reda på hur effektivt din klassificerare är för att identifiera dina dokument.</span><span class="sxs-lookup"><span data-stu-id="fb1e7-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testa din filer](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="fb1e7-187">Se även</span><span class="sxs-lookup"><span data-stu-id="fb1e7-187">See Also</span></span>
[<span data-ttu-id="fb1e7-188">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="fb1e7-188">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="fb1e7-189">Förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="fb1e7-189">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="fb1e7-190">Använd termlagringstaxonomi vid skapande av extraktor</span><span class="sxs-lookup"><span data-stu-id="fb1e7-190">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="fb1e7-191">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="fb1e7-191">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="fb1e7-192">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="fb1e7-192">Apply a model</span></span>](apply-a-model.md) 
