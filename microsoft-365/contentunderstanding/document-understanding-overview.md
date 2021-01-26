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
ms.openlocfilehash: c0396c8e702d3e32db93d26dba23ab038546bea0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976525"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="1a7a3-103">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="1a7a3-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="1a7a3-104">Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="1a7a3-105">Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="1a7a3-106">De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="1a7a3-107">Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).</span><span class="sxs-lookup"><span data-stu-id="1a7a3-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="1a7a3-108">Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="1a7a3-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="1a7a3-109">Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="1a7a3-110">När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="1a7a3-111">Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="1a7a3-112">Du kan också välja befintliga innehållstyper för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="1a7a3-113">Skrivskyddat eller förseglade innehållstyper kan inte uppdateras, så de kan inte användas i en modell.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="1a7a3-114">Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="1a7a3-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="1a7a3-115">Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="1a7a3-116">En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="1a7a3-117">Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="1a7a3-118">Extraktorer hämtar information från dokumenten.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="1a7a3-119">Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="1a7a3-120">Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="1a7a3-121">Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="1a7a3-122">Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="1a7a3-123">Du kan också använda exempelfiler för att testa hur effektiv modellen är.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-123">You can also use example files to test the effectiveness of your model.</span></span>

> [!NOTE]
> <span data-ttu-id="1a7a3-124">Om du använder optisk teckenläsning (OCR) för att skanna dokument, har Syntex en gräns på 15 sidor för modellträning.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-124">If you use optical character recognition (OCR) technology to scan documents, Syntex has a 15-page limit for model training.</span></span>

<span data-ttu-id="1a7a3-125">När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="1a7a3-125">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1a7a3-126">Se även</span><span class="sxs-lookup"><span data-stu-id="1a7a3-126">See Also</span></span>
[<span data-ttu-id="1a7a3-127">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="1a7a3-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="1a7a3-128">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="1a7a3-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="1a7a3-129">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="1a7a3-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="1a7a3-130">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="1a7a3-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="1a7a3-131">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="1a7a3-131">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="1a7a3-132">Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="1a7a3-132">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="1a7a3-133">Översikt av formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="1a7a3-133">Form processing overview</span></span>](form-processing-overview.md)
