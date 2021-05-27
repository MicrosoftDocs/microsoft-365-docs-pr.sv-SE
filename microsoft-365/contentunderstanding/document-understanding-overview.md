---
title: Översikt av dokumenttolkning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683829"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="db4da-103">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="db4da-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="db4da-104">Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen.</span><span class="sxs-lookup"><span data-stu-id="db4da-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="db4da-105">Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt.</span><span class="sxs-lookup"><span data-stu-id="db4da-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="db4da-106">De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="db4da-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="db4da-107">Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).</span><span class="sxs-lookup"><span data-stu-id="db4da-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="db4da-108">Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="db4da-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="db4da-109">Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*.</span><span class="sxs-lookup"><span data-stu-id="db4da-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="db4da-110">När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras.</span><span class="sxs-lookup"><span data-stu-id="db4da-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="db4da-111">Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="db4da-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="db4da-112">Du kan också välja befintliga innehållstyper för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="db4da-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="db4da-113">Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, alltså de kan inte användas i en modell.</span><span class="sxs-lookup"><span data-stu-id="db4da-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="db4da-114">Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="db4da-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="db4da-115">Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="db4da-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="db4da-116">En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="db4da-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="db4da-117">Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.</span><span class="sxs-lookup"><span data-stu-id="db4da-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="db4da-118">Extraktorer hämtar information från dokumenten.</span><span class="sxs-lookup"><span data-stu-id="db4da-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="db4da-119">Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse.</span><span class="sxs-lookup"><span data-stu-id="db4da-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="db4da-120">Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell.</span><span class="sxs-lookup"><span data-stu-id="db4da-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="db4da-121">Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer.</span><span class="sxs-lookup"><span data-stu-id="db4da-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="db4da-122">Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med.</span><span class="sxs-lookup"><span data-stu-id="db4da-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="db4da-123">Du kan också använda exempelfiler för att testa hur effektiv modellen är.</span><span class="sxs-lookup"><span data-stu-id="db4da-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="db4da-124">När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="db4da-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="db4da-125">Filbegränsningar</span><span class="sxs-lookup"><span data-stu-id="db4da-125">File limitations</span></span>

<span data-ttu-id="db4da-126">Dokument för dokumenttolkning använder optisk teckenläsning (OCR) för att skanna PDF-filer, bilder och TIFF-filer, både när du utbildar en modell med exempelfiler och när du kör modellen mot filer i ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="db4da-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="db4da-127">Observera följande skillnader i fråga om textbaserade filer i Microsoft Office och skannade OCR-filer (PDF, bild eller TIFF):</span><span class="sxs-lookup"><span data-stu-id="db4da-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="db4da-128">Office-filer: trunkeras vid 64 000 tecken (i utbildning och när de körs mot filer i ett dokumentbibliotek).</span><span class="sxs-lookup"><span data-stu-id="db4da-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="db4da-129">OCR-skannade filer: det finns en gräns på 20 sidor.</span><span class="sxs-lookup"><span data-stu-id="db4da-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="db4da-130">Krav</span><span class="sxs-lookup"><span data-stu-id="db4da-130">Requirements</span></span>

<span data-ttu-id="db4da-131">OCR-bearbetningen fungerar bäst med dokument som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="db4da-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="db4da-132">JPG-, PNG- eller PDF-format (text eller skannad).</span><span class="sxs-lookup"><span data-stu-id="db4da-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="db4da-133">PDF-filer med inbäddad text är bättre, eftersom det inte blir några fel i extrahering och placering av tecken.</span><span class="sxs-lookup"><span data-stu-id="db4da-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="db4da-134">Om PDF-filerna är lösenordslåsta måste du ta bort låset innan du skickar dem.</span><span class="sxs-lookup"><span data-stu-id="db4da-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="db4da-135">Den kombinerade filstorleken för dokument som används för utbildning per samling får inte överstiga 50 MB och PDF-dokument bör inte ha fler än 500 sidor.</span><span class="sxs-lookup"><span data-stu-id="db4da-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="db4da-136">För bilder måste måtten vara mellan 50 × 50 och 10 000 × 10 000 bildpunkter.</span><span class="sxs-lookup"><span data-stu-id="db4da-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="db4da-137">Bilder som är mycket breda eller har udda mått (t.ex. planritningar) kan trunkeras i OCR-processen och förlora precision.</span><span class="sxs-lookup"><span data-stu-id="db4da-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="db4da-138">För PDF-filer måste måtten vara högst 17 x 17 tum, motsvarande pappersstorlekerna juridiska filer eller A3 och mindre.</span><span class="sxs-lookup"><span data-stu-id="db4da-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="db4da-139">Om filen har skannats från pappersdokument bör skanningen vara av hög kvalitet.</span><span class="sxs-lookup"><span data-stu-id="db4da-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="db4da-140">Måste använda det latinska alfabetet (engelska tecken).</span><span class="sxs-lookup"><span data-stu-id="db4da-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="db4da-141">AI Builder stöder för närvarande inte följande typer av formulärbearbetning av indata:</span><span class="sxs-lookup"><span data-stu-id="db4da-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="db4da-142">– Kryssrutor eller alternativknappar</span><span class="sxs-lookup"><span data-stu-id="db4da-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="db4da-143">– signaturer</span><span class="sxs-lookup"><span data-stu-id="db4da-143">- Signatures</span></span><br><span data-ttu-id="db4da-144">– ifyllningsbara PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="db4da-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="db4da-145">Filtyper som stöds</span><span class="sxs-lookup"><span data-stu-id="db4da-145">Supported file types</span></span>

<span data-ttu-id="db4da-146">Dokument för dokumenttolkning stöder följande filtyper:</span><span class="sxs-lookup"><span data-stu-id="db4da-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="db4da-147">dokument</span><span class="sxs-lookup"><span data-stu-id="db4da-147">doc</span></span>
- <span data-ttu-id="db4da-148">docx</span><span class="sxs-lookup"><span data-stu-id="db4da-148">docx</span></span>
- <span data-ttu-id="db4da-149">eml</span><span class="sxs-lookup"><span data-stu-id="db4da-149">eml</span></span>
- <span data-ttu-id="db4da-150">heic</span><span class="sxs-lookup"><span data-stu-id="db4da-150">heic</span></span>
- <span data-ttu-id="db4da-151">heif</span><span class="sxs-lookup"><span data-stu-id="db4da-151">heif</span></span>
- <span data-ttu-id="db4da-152">htm</span><span class="sxs-lookup"><span data-stu-id="db4da-152">htm</span></span>
- <span data-ttu-id="db4da-153">html</span><span class="sxs-lookup"><span data-stu-id="db4da-153">html</span></span>
- <span data-ttu-id="db4da-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="db4da-154">jpeg</span></span>
- <span data-ttu-id="db4da-155">jpg</span><span class="sxs-lookup"><span data-stu-id="db4da-155">jpg</span></span>
- <span data-ttu-id="db4da-156">markdown</span><span class="sxs-lookup"><span data-stu-id="db4da-156">markdown</span></span>
- <span data-ttu-id="db4da-157">md</span><span class="sxs-lookup"><span data-stu-id="db4da-157">md</span></span>
- <span data-ttu-id="db4da-158">msg</span><span class="sxs-lookup"><span data-stu-id="db4da-158">msg</span></span>
- <span data-ttu-id="db4da-159">pdf</span><span class="sxs-lookup"><span data-stu-id="db4da-159">pdf</span></span>
- <span data-ttu-id="db4da-160">png</span><span class="sxs-lookup"><span data-stu-id="db4da-160">png</span></span>
- <span data-ttu-id="db4da-161">ppt</span><span class="sxs-lookup"><span data-stu-id="db4da-161">ppt</span></span>
- <span data-ttu-id="db4da-162">pptx</span><span class="sxs-lookup"><span data-stu-id="db4da-162">pptx</span></span>
- <span data-ttu-id="db4da-163">rtf</span><span class="sxs-lookup"><span data-stu-id="db4da-163">rtf</span></span>
- <span data-ttu-id="db4da-164">tif</span><span class="sxs-lookup"><span data-stu-id="db4da-164">tif</span></span>
- <span data-ttu-id="db4da-165">tiff</span><span class="sxs-lookup"><span data-stu-id="db4da-165">tiff</span></span>
- <span data-ttu-id="db4da-166">txt</span><span class="sxs-lookup"><span data-stu-id="db4da-166">txt</span></span>
- <span data-ttu-id="db4da-167">xls</span><span class="sxs-lookup"><span data-stu-id="db4da-167">xls</span></span>
- <span data-ttu-id="db4da-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="db4da-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="db4da-169">Se även</span><span class="sxs-lookup"><span data-stu-id="db4da-169">See Also</span></span>
[<span data-ttu-id="db4da-170">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="db4da-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="db4da-171">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="db4da-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="db4da-172">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="db4da-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="db4da-173">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="db4da-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="db4da-174">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="db4da-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="db4da-175">Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="db4da-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="db4da-176">Översikt av formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="db4da-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="db4da-177">Tillgänglighetsläge för SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="db4da-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)