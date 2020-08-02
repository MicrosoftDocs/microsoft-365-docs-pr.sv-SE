---
title: Översikt över dokumentförståelse (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokumentöverenskommelsen i Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537406"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="2997d-103">Översikt över dokumentförståelse (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="2997d-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="2997d-104">Project Cortex är för närvarande i Förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="2997d-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="2997d-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2997d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="2997d-106">Dokumentöverensning använder AI-modeller för att automatisera klassificeringen av filer och extrahering av information.</span><span class="sxs-lookup"><span data-stu-id="2997d-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="2997d-107">Det fungerar bäst med ostrukturerade dokument, som brev eller kontrakt.</span><span class="sxs-lookup"><span data-stu-id="2997d-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="2997d-108">Dokumenten bör ha text som kan identifieras baserat på fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="2997d-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="2997d-109">Den identifierade texten kan ange både vilken typ av fil det är (dess klassificering) och vad du vill extrahera (dess extractors).</span><span class="sxs-lookup"><span data-stu-id="2997d-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="2997d-110">Dokumentförståelsemodeller skapas och hanteras på en typ av SharePoint-webbplats som kallas innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="2997d-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="2997d-111">När den tillämpas på ett SharePoint-dokumentbibliotek associeras modellen med en innehållstyp som har kolumner för att lagra den information som extraheras.</span><span class="sxs-lookup"><span data-stu-id="2997d-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="2997d-112">Den innehållstyp du skapar lagras i sharepoint-innehållstypgalleriet.</span><span class="sxs-lookup"><span data-stu-id="2997d-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="2997d-113">Du kan också välja att använda befintliga innehållstyper för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="2997d-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="2997d-114">Du kan lägga till *klassificerare* och *extraherare* i dina dokumentförståelsemodeller för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="2997d-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="2997d-115">Klassificerare används för att identifiera och klassificera dokument som överförs till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="2997d-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="2997d-116">En klassificerare kan till exempel "tränas" för att identifiera alla *kontraktsförnyelsedokument* som överförs till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="2997d-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="2997d-117">Innehållstypen kontraktsförnyelse definieras av dig när du skapar klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="2997d-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="2997d-118">Utdragarna hämtar information från dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="2997d-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="2997d-119">För alla dokumentförnyelsedokument som identifieras i dokumentbiblioteket visas kolumner i vyn som också visar *startdatumet* för tjänsten och *klienten* för varje kontraktsförnyelsedokument.</span><span class="sxs-lookup"><span data-stu-id="2997d-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="2997d-120">Du använder exempelfiler för att träna och testa klassificerare och utsug i din modell.</span><span class="sxs-lookup"><span data-stu-id="2997d-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="2997d-121">Exempelfiler ger dina modellexempel på vad du ska leta efter när du försöker identifiera och extrahera data från filer.</span><span class="sxs-lookup"><span data-stu-id="2997d-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="2997d-122">Du skulle till exempel träna dina klassificeringsklassificerare och utsug av kontraktsförnyelse med exempel på kontraktsförnyelsedokument som ditt företag arbetar med.</span><span class="sxs-lookup"><span data-stu-id="2997d-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="2997d-123">Du kan också använda exempelfiler för att testa modellens effektivitet.</span><span class="sxs-lookup"><span data-stu-id="2997d-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="2997d-124">När du har publicerat modellen använder du innehållscentret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="2997d-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="2997d-125">Se även</span><span class="sxs-lookup"><span data-stu-id="2997d-125">See Also</span></span>
[<span data-ttu-id="2997d-126">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="2997d-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="2997d-127">Skapa en utsutorn</span><span class="sxs-lookup"><span data-stu-id="2997d-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="2997d-128">[Skapa ett innehållscenter](create-a-content-center.md) 
 [Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="2997d-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="2997d-129">[Använda en modell](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="2997d-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="2997d-130">Skillnad mellan en dokumentöverensning och en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="2997d-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="2997d-131">Översikt över formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="2997d-131">Form processing overview</span></span>](form-processing-overview.md)




