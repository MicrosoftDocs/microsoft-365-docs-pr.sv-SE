---
title: Skillnaden mellan dokumentförståelse och formulärbearbetningsmodeller (förhandsversion)
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
description: Beskriver tangentskillnaden mellan dokumentöverensning och formulärbearbetningsmodeller.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537431"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="1662b-103">Skillnaden mellan dokumentförståelse och formulärbearbetningsmodeller (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="1662b-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="1662b-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="1662b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="1662b-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="1662b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="1662b-106">Med innehållsöverensande i Project Cortex kan du identifiera och klassificera dokument som laddas upp till SharePoint-dokumentbibliotek samt extrahera relevant information från varje fil.</span><span class="sxs-lookup"><span data-stu-id="1662b-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="1662b-107">Till exempel, när filer överförs till ett SharePoint-dokumentbibliotek, klassificeras alla filer som identifieras som *inköpsorder* som sådana och visas i en anpassad dokumentbiblioteksvy där de visas.</span><span class="sxs-lookup"><span data-stu-id="1662b-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="1662b-108">Dessutom kan du hämta specifik information från varje fil (till exempel *PO-nummer* och *totalt)* och visa den i en kolumn i dokumentbiblioteksvyn.</span><span class="sxs-lookup"><span data-stu-id="1662b-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="1662b-109">Med innehållsöverensing kan du skapa *modeller* för att identifiera och extrahera den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="1662b-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="1662b-110">Det finns två typer av modeller som kan användas:</span><span class="sxs-lookup"><span data-stu-id="1662b-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="1662b-111">Modeller för dokuments förståelse</span><span class="sxs-lookup"><span data-stu-id="1662b-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="1662b-112">Formulärbearbetningsmodeller</span><span class="sxs-lookup"><span data-stu-id="1662b-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="1662b-113">Även om båda modellerna används för i allmänhet samma ändamål, det finns viktiga skillnader som kommer att påverka vilka du kan välja att använda.</span><span class="sxs-lookup"><span data-stu-id="1662b-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="1662b-114">Strukturerat kontra ostrukturerat och halvstrukturerat innehåll</span><span class="sxs-lookup"><span data-stu-id="1662b-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="1662b-115">Använd dokumentförståelsemodeller för att identifiera och extrahera data från ostrukturerade dokument, till exempel brev eller kontrakt, där textentiteterna som du vill extrahera finns i meningar eller specifika regioner i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="1662b-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="1662b-116">Ett ostrukturerat dokument kan till exempel vara ett brev om kontraktsförlängning som kan skrivas på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="1662b-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="1662b-117">Det finns dock information som konsekvent finns i brödtexten i varje kontraktsförnyelsedokument, till exempel textsträngen "Tjänstens startdatum" följt av ett faktiskt datum.</span><span class="sxs-lookup"><span data-stu-id="1662b-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="1662b-118">Använd formulärbearbetningsmodeller för att identifiera filer och extrahera data från strukturerade eller halvstrukturerade dokument, till exempel formulär eller fakturor, där du har tydliga nyckelvärdespar (till exempel *Datum: 10/1/2020*)\* eller tabelldata.</span><span class="sxs-lookup"><span data-stu-id="1662b-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="1662b-119">Som ett exempel skulle en bra kandidat för formulärbearbetning vara ett företags formulär för orderbegäran där klienter måste tillhandahålla sin information för specifika fält som finns i samma område i dokumentlayouten, till exempel *Namn,* *Telefonnummer*, *Total kostnad*, etc.  Ett skatteformulär är ett bra exempel på ett strukturerat dokument.</span><span class="sxs-lookup"><span data-stu-id="1662b-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="1662b-120">Där de skapas</span><span class="sxs-lookup"><span data-stu-id="1662b-120">Where they are created</span></span>

<span data-ttu-id="1662b-121">Dokumentförståelsemodeller skapas och hanteras på en SharePoint-webbplats för innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="1662b-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="1662b-122">Du måste ha tillgång till en content center-webbplats för att kunna skapa en dokumentöverensåningsmodell eller tillämpa en på ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="1662b-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="1662b-123">När du skapar en modell för dokumentöversståelse skapar du en ny [SharePoint-innehållstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i sharepoint-galleriet för innehållstyper.</span><span class="sxs-lookup"><span data-stu-id="1662b-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="1662b-124">Du kan också använda befintliga innehållstyper för att definiera din modell om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1662b-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="1662b-125">Formulärbearbetningsmodeller skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), men skapandet initieras direkt från ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="1662b-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="1662b-126">Formulärbearbetningsmodell måste aktiveras i dokumentbiblioteket för att en användare ska kunna skapa en formulärbearbetningsmodell för den, och en administratör kan göra detta i administratörsinställningarna för innehållsförståelse.</span><span class="sxs-lookup"><span data-stu-id="1662b-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="1662b-127">Formulärbearbetningsmodeller använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="1662b-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="1662b-128">Formulärbearbetningsmodeller skapar också nya [SharePoint-innehållstyper](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), som också lagras i sharepoint-galleriet för innehållstyper.</span><span class="sxs-lookup"><span data-stu-id="1662b-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="1662b-129">Om de kan tillämpas</span><span class="sxs-lookup"><span data-stu-id="1662b-129">Where they can be applied</span></span>

<span data-ttu-id="1662b-130">Dokumentöverensningsmodeller kan tillämpas på olika SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="1662b-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="1662b-131">Du kan använda innehållscentret för att inte bara skapa en modell för dokumentöverensning, utan också för att tillämpa den på olika dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="1662b-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="1662b-132">Innehållscentret ger en mer central kontroll över hur dokumentöverensåelsemodeller används och var de används, eftersom den här informationen måste samlas upp till ett innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="1662b-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="1662b-133">Formulärbearbetningsmodeller kan för närvarande endast tillämpas på det SharePoint-dokumentbibliotek som de skapades från.</span><span class="sxs-lookup"><span data-stu-id="1662b-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="1662b-134">Detta gör det möjligt för alla licensierade användare som har åtkomst till webbplatsen att skapa en formulärbearbetningsmodell.</span><span class="sxs-lookup"><span data-stu-id="1662b-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="1662b-135">Se även</span><span class="sxs-lookup"><span data-stu-id="1662b-135">See Also</span></span>
[<span data-ttu-id="1662b-136">Utbildning: Förbättra företagets resultat med AI Builder</span><span class="sxs-lookup"><span data-stu-id="1662b-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="1662b-137">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="1662b-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="1662b-138">Skapa en utsutorn</span><span class="sxs-lookup"><span data-stu-id="1662b-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="1662b-139">Använda en modell för dokuments förståelse</span><span class="sxs-lookup"><span data-stu-id="1662b-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="1662b-140">Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="1662b-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



