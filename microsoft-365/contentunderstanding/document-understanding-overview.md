---
title: Översikt av dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222761"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="b5091-103">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="b5091-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="b5091-104">Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen.</span><span class="sxs-lookup"><span data-stu-id="b5091-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="b5091-105">Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt.</span><span class="sxs-lookup"><span data-stu-id="b5091-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="b5091-106">De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="b5091-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="b5091-107">Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).</span><span class="sxs-lookup"><span data-stu-id="b5091-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="b5091-108">Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="b5091-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="b5091-109">Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*.</span><span class="sxs-lookup"><span data-stu-id="b5091-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="b5091-110">När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras.</span><span class="sxs-lookup"><span data-stu-id="b5091-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="b5091-111">Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b5091-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="b5091-112">Du kan också välja befintliga innehållstyper för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="b5091-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="b5091-113">Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, så de kan inte användas i en modell.</span><span class="sxs-lookup"><span data-stu-id="b5091-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="b5091-114">Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="b5091-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="b5091-115">Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="b5091-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="b5091-116">En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="b5091-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="b5091-117">Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.</span><span class="sxs-lookup"><span data-stu-id="b5091-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="b5091-118">Extraktorer hämtar information från dokumenten.</span><span class="sxs-lookup"><span data-stu-id="b5091-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="b5091-119">Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse.</span><span class="sxs-lookup"><span data-stu-id="b5091-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="b5091-120">Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell.</span><span class="sxs-lookup"><span data-stu-id="b5091-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="b5091-121">Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer.</span><span class="sxs-lookup"><span data-stu-id="b5091-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="b5091-122">Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med.</span><span class="sxs-lookup"><span data-stu-id="b5091-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="b5091-123">Du kan också använda exempelfiler för att testa hur effektiv modellen är.</span><span class="sxs-lookup"><span data-stu-id="b5091-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="b5091-124">När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="b5091-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="b5091-125">Filbegränsningar</span><span class="sxs-lookup"><span data-stu-id="b5091-125">File limitations</span></span>

<span data-ttu-id="b5091-126">Dokument för dokumenttolkning använder optisk teckenläsning (OCR) för att skanna PDF-filer, bilder och TIFF-filer, både när du utbildar en modell med exempelfiler och när du kör modellen mot filer i ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="b5091-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="b5091-127">Observera följande skillnader i fråga om textbaserade filer i Microsoft Office och skannade OCR-filer (PDF, bild eller TIFF):</span><span class="sxs-lookup"><span data-stu-id="b5091-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="b5091-128">Office-filer: Vi trunkerar vid 64 000 tecken (i utbildning och när vi kör mot filer i ett dokumentbibliotek).</span><span class="sxs-lookup"><span data-stu-id="b5091-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="b5091-129">OCR-skannade filer: Det finns en gräns på 20 sidor.</span><span class="sxs-lookup"><span data-stu-id="b5091-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="b5091-130">Filtyper som stöds</span><span class="sxs-lookup"><span data-stu-id="b5091-130">Supported file types</span></span>

<span data-ttu-id="b5091-131">Dokument för dokumenttolkning stöder följande filtyper:</span><span class="sxs-lookup"><span data-stu-id="b5091-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="b5091-132">dokument</span><span class="sxs-lookup"><span data-stu-id="b5091-132">doc</span></span>
- <span data-ttu-id="b5091-133">docx</span><span class="sxs-lookup"><span data-stu-id="b5091-133">docx</span></span>
- <span data-ttu-id="b5091-134">eml</span><span class="sxs-lookup"><span data-stu-id="b5091-134">eml</span></span>
- <span data-ttu-id="b5091-135">heic</span><span class="sxs-lookup"><span data-stu-id="b5091-135">heic</span></span>
- <span data-ttu-id="b5091-136">heif</span><span class="sxs-lookup"><span data-stu-id="b5091-136">heif</span></span>
- <span data-ttu-id="b5091-137">htm</span><span class="sxs-lookup"><span data-stu-id="b5091-137">htm</span></span>
- <span data-ttu-id="b5091-138">html</span><span class="sxs-lookup"><span data-stu-id="b5091-138">html</span></span>
- <span data-ttu-id="b5091-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="b5091-139">jpeg</span></span>
- <span data-ttu-id="b5091-140">jpg</span><span class="sxs-lookup"><span data-stu-id="b5091-140">jpg</span></span>
- <span data-ttu-id="b5091-141">markdown</span><span class="sxs-lookup"><span data-stu-id="b5091-141">markdown</span></span>
- <span data-ttu-id="b5091-142">md</span><span class="sxs-lookup"><span data-stu-id="b5091-142">md</span></span>
- <span data-ttu-id="b5091-143">msg</span><span class="sxs-lookup"><span data-stu-id="b5091-143">msg</span></span>
- <span data-ttu-id="b5091-144">pdf</span><span class="sxs-lookup"><span data-stu-id="b5091-144">pdf</span></span>
- <span data-ttu-id="b5091-145">png</span><span class="sxs-lookup"><span data-stu-id="b5091-145">png</span></span>
- <span data-ttu-id="b5091-146">ppt</span><span class="sxs-lookup"><span data-stu-id="b5091-146">ppt</span></span>
- <span data-ttu-id="b5091-147">pptx</span><span class="sxs-lookup"><span data-stu-id="b5091-147">pptx</span></span>
- <span data-ttu-id="b5091-148">rtf</span><span class="sxs-lookup"><span data-stu-id="b5091-148">rtf</span></span>
- <span data-ttu-id="b5091-149">tif</span><span class="sxs-lookup"><span data-stu-id="b5091-149">tif</span></span>
- <span data-ttu-id="b5091-150">tiff</span><span class="sxs-lookup"><span data-stu-id="b5091-150">tiff</span></span>
- <span data-ttu-id="b5091-151">txt</span><span class="sxs-lookup"><span data-stu-id="b5091-151">txt</span></span>
- <span data-ttu-id="b5091-152">xls</span><span class="sxs-lookup"><span data-stu-id="b5091-152">xls</span></span>
- <span data-ttu-id="b5091-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="b5091-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="b5091-154">Se även</span><span class="sxs-lookup"><span data-stu-id="b5091-154">See Also</span></span>
[<span data-ttu-id="b5091-155">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="b5091-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="b5091-156">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="b5091-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="b5091-157">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="b5091-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="b5091-158">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="b5091-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="b5091-159">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="b5091-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="b5091-160">Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="b5091-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="b5091-161">Översikt av formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="b5091-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="b5091-162">Tillgänglighetsläge för SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b5091-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)