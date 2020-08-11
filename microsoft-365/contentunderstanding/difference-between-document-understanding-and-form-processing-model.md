---
title: Skillnad mellan dokument förståelse och modeller för formulär bearbetning (för hands version)
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
description: Beskriver viktig skillnad mellan dokument-och formulär bearbetnings modeller.
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612744"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="b9929-103">Skillnad mellan dokument förståelse och modeller för formulär bearbetning (för hands version)</span><span class="sxs-lookup"><span data-stu-id="b9929-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b9929-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="b9929-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b9929-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b9929-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b9929-106">Med innehålls förståelse i Project cortex kan du identifiera och klassificera dokument som laddas upp till SharePoint-dokumentbibliotek, samt att extrahera relevant information från varje fil.</span><span class="sxs-lookup"><span data-stu-id="b9929-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="b9929-107">När till exempel filer laddas upp till ett SharePoint-dokumentbibliotek klassificeras alla filer som identifieras som *inköps order* som sådana och visas i en anpassad vy för dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="b9929-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="b9929-108">Dessutom kan du hämta specifik information från varje fil (till exempel *inköps order nummer* och *totalt*) och visa den i en kolumn i vyn dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="b9929-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="b9929-109">Med innehålls förståelse kan du skapa *modeller* för att identifiera och extrahera den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="b9929-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="b9929-110">Det finns två typer av modeller som kan användas:</span><span class="sxs-lookup"><span data-stu-id="b9929-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="b9929-111">Förstå dokument</span><span class="sxs-lookup"><span data-stu-id="b9929-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="b9929-112">Formulär bearbetnings modeller</span><span class="sxs-lookup"><span data-stu-id="b9929-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="b9929-113">Även om båda modellerna används i samma syfte är det viktiga skillnader som påverkar vilka du kan välja att använda.</span><span class="sxs-lookup"><span data-stu-id="b9929-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="b9929-114">Strukturerat kontra ostrukturerat och indelat innehåll</span><span class="sxs-lookup"><span data-stu-id="b9929-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="b9929-115">Använd dokument förståelse modeller för att identifiera och hämta data från ostrukturerade dokument, till exempel bokstäver eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller vissa områden i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="b9929-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="b9929-116">Ett ostrukturerat dokument kan till exempel vara ett förnyelse brev som kan skrivas på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="b9929-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="b9929-117">Men det finns information som är konsekvent i bröd texten i varje kontrakt förnyelse dokument, till exempel text strängen "start datum" följt av ett faktiskt datum.</span><span class="sxs-lookup"><span data-stu-id="b9929-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="b9929-118">Använd formulär bearbetnings modeller för att identifiera filer och hämta data från strukturerade eller halv strukturerade dokument, till exempel formulär eller fakturor, där du har tydliga par av viktiga värden (t. ex. *datum: 10/1/2020*) \* eller tabell data.</span><span class="sxs-lookup"><span data-stu-id="b9929-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="b9929-119">Som ett exempel är en bra kandidat för formulär bearbetning att skapa ett företags order förfrågnings formulär där klienter behöver uppge sin information för specifika fält som finns i samma område i dokumentlayouten, till exempel *namn*, *telefonnummer*, *Total kostnad*etc.  Ett moms formulär är ett bra exempel på ett strukturerat dokument.</span><span class="sxs-lookup"><span data-stu-id="b9929-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="b9929-120">Var de skapas</span><span class="sxs-lookup"><span data-stu-id="b9929-120">Where they are created</span></span>

<span data-ttu-id="b9929-121">Dokument förståelse modeller skapas och hanteras på en webbplats för SharePoint-innehåll.</span><span class="sxs-lookup"><span data-stu-id="b9929-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="b9929-122">Du måste ha till gång till en innehålls Center webbplats för att skapa en dokument modell eller för att använda en i ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="b9929-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="b9929-123">När du skapar en dokument metod kan du skapa en ny [SharePoint-innehållstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för SharePoint-innehålls typer.</span><span class="sxs-lookup"><span data-stu-id="b9929-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="b9929-124">Du kan också använda befintliga innehålls typer för att definiera modellen om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b9929-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="b9929-125">Formulär bearbetnings modeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)men skapandet startas direkt från ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="b9929-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="b9929-126">Skapande av formulär bearbetnings modeller måste aktive ras i dokument biblioteket för att en användare ska kunna skapa en formulär bearbetnings modell för det och en administratör kan göra detta i administratörs inställningarna för innehåll.</span><span class="sxs-lookup"><span data-stu-id="b9929-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="b9929-127">För formulär bearbetnings modeller används PowerAutomate-flöden för att bearbeta filer när de överförs till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="b9929-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="b9929-128">Formulär bearbetnings modeller skapar också nya [SharePoint-innehålls typer](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), som också lagras i galleriet SharePoint-innehålls typer.</span><span class="sxs-lookup"><span data-stu-id="b9929-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="b9929-129">Var de kan användas</span><span class="sxs-lookup"><span data-stu-id="b9929-129">Where they can be applied</span></span>

<span data-ttu-id="b9929-130">Dokument förståelse modeller kan tillämpas på olika SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="b9929-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="b9929-131">Du kan använda innehålls centret för att inte bara skapa en dokument förståelse, utan även för att tillämpa den på olika dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="b9929-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="b9929-132">Innehålls Center ger en mer Central kontroll av hur dokument tolka modeller används och var de används, eftersom dessa uppgifter måste lyftas upp till ett innehålls Center.</span><span class="sxs-lookup"><span data-stu-id="b9929-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="b9929-133">Formulär bearbetnings modeller kan för närvarande endast användas i det SharePoint-dokumentbibliotek som de skapades från.</span><span class="sxs-lookup"><span data-stu-id="b9929-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="b9929-134">Då kan alla licensierade användare som har åtkomst till webbplatsen skapa en modell för formulär bearbetning.</span><span class="sxs-lookup"><span data-stu-id="b9929-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="b9929-135">Se även</span><span class="sxs-lookup"><span data-stu-id="b9929-135">See Also</span></span>
[<span data-ttu-id="b9929-136">Utbildning: förbättra företags prestanda med hjälp av AI Builder</span><span class="sxs-lookup"><span data-stu-id="b9929-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="b9929-137">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="b9929-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b9929-138">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="b9929-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="b9929-139">Använda en modell för dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="b9929-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="b9929-140">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="b9929-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



