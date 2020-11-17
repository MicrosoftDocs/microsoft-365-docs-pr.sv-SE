---
title: Översikt av dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Få en översikt av dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: b26ed9a9ed9b8d1f332ccf14377660e634349b3d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087373"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="a15dc-103">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="a15dc-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="a15dc-104">Dokumenttolkning använder AI-modeller (artificiell intelligens) för att automatisera klassificeringen av filer och datautvinningen.</span><span class="sxs-lookup"><span data-stu-id="a15dc-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="a15dc-105">Det fungerar bäst med ostrukturerade dokument, till exempel brev eller kontrakt.</span><span class="sxs-lookup"><span data-stu-id="a15dc-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="a15dc-106">De här dokumenten måste innehålla text som kan identifieras utifrån fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="a15dc-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="a15dc-107">Med den identifierade texten anges både vilken typ av fil det är (klassificeringen) och vad du vill extrahera (dess extraherare).</span><span class="sxs-lookup"><span data-stu-id="a15dc-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="a15dc-108">Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint-Syntex: Kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="a15dc-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="a15dc-109">Modeller för dokumenttolkning skapas och hanteras på en typ av SharePoint-webbplats som kallas *innehållscenter*.</span><span class="sxs-lookup"><span data-stu-id="a15dc-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="a15dc-110">När den används i ett SharePoint-dokumentbibliotek kopplas modellen till en innehållstyp med kolumner för att lagra den information som extraheras.</span><span class="sxs-lookup"><span data-stu-id="a15dc-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="a15dc-111">Innehållstypen som du skapar lagras i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a15dc-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="a15dc-112">Du kan också välja befintliga innehållstyper för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="a15dc-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="a15dc-113">Lägg till *klassificerare* och *extraktorer* till modellen för dokumenttolkning för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="a15dc-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="a15dc-114">Klassificerare används för att identifiera och klassificera dokument som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="a15dc-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="a15dc-115">En klassificerare kan t. ex. tränas till att identifiera alla *avtalsförnyelser* som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="a15dc-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="a15dc-116">Innehållstypen avtalsförnyelse definieras av dig när du skapar din klassificerare.</span><span class="sxs-lookup"><span data-stu-id="a15dc-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="a15dc-117">Extraktorer hämtar information från dokumenten.</span><span class="sxs-lookup"><span data-stu-id="a15dc-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="a15dc-118">Om du till exempel vill att alla avtalsförnyelser som identifieras i ditt dokumentbibliotek visar kolumnerna i vyn också *Tjänstens startdatum* och  *Klient* för varje avtalsförnyelse.</span><span class="sxs-lookup"><span data-stu-id="a15dc-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="a15dc-119">Du kan använda exempelfiler för att träna och testa dina klassificerare och extraktorer på din modell.</span><span class="sxs-lookup"><span data-stu-id="a15dc-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="a15dc-120">Exempelfiler tillhandahåller modellexemplen för vad du ska titta efter när du försöker identifiera och hämta data från filer.</span><span class="sxs-lookup"><span data-stu-id="a15dc-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="a15dc-121">Till exempel kan du träna dina klassificerare för avtalsförnyelse och extraktorer med exempel på avtalsförlängningar som företaget arbetar med.</span><span class="sxs-lookup"><span data-stu-id="a15dc-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="a15dc-122">Du kan också använda exempelfiler för att testa hur effektiv modellen är.</span><span class="sxs-lookup"><span data-stu-id="a15dc-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="a15dc-123">När du har publicerat modellen använder du innehållscentret för att använda det på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="a15dc-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="a15dc-124">Se även</span><span class="sxs-lookup"><span data-stu-id="a15dc-124">See Also</span></span>
[<span data-ttu-id="a15dc-125">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="a15dc-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a15dc-126">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="a15dc-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a15dc-127">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="a15dc-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="a15dc-128">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="a15dc-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="a15dc-129">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="a15dc-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="a15dc-130">Skillnader mellan en modell för dokumenttolkning och en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="a15dc-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="a15dc-131">Översikt av formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="a15dc-131">Form processing overview</span></span>](form-processing-overview.md)
