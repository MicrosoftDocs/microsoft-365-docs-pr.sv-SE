---
title: Översikt över dokument förståelse
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokument kunskapen i Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294766"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="5ddd7-103">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="5ddd7-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="5ddd7-104">Användning av dokument med hjälp av AI-modeller (artificiell intelligens) för att automatisera klassificering av filer och extraktion av information.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="5ddd7-105">Den fungerar bäst med ostrukturerade dokument, till exempel brev och kontrakt.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="5ddd7-106">Dessa dokument måste innehålla text som kan identifieras baserat på fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="5ddd7-107">Den identifierade texten anger både den typ av fil den är (dess klassificering) och vad du vill extrahera (dess utdrag).</span><span class="sxs-lookup"><span data-stu-id="5ddd7-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="5ddd7-108">Dokument förståelse modeller skapas och hanteras i en typ av SharePoint-webbplats som kallas för *innehålls Center*.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="5ddd7-109">När modellen kopplas till ett SharePoint-dokumentbibliotek är den kopplad till en innehålls typ som innehåller kolumner för att lagra informationen som extraheras.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="5ddd7-110">Innehålls typen du skapar lagras i galleriet för SharePoint-innehålls typ.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="5ddd7-111">Du kan också välja att använda befintliga innehålls typer för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="5ddd7-112">Gör följande om du vill lägga till *klassificerare* och *utdrag* i dina dokument:</span><span class="sxs-lookup"><span data-stu-id="5ddd7-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="5ddd7-113">Klassificerare används för att identifiera och klassificera dokument som laddas upp till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="5ddd7-114">En klassificerare kan till exempel vara "utbildad" för att identifiera alla *förnyelse* dokument som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="5ddd7-115">Innehålls typen kontrakt förnyelse definieras av dig när du skapar en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="5ddd7-116">Utdrag ur dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="5ddd7-117">För alla kontrakt förnyelse dokument som identifieras i dokument biblioteket visas till exempel kolumnerna i vyn som också visar *tjänstens start datum* och  *klient* för varje kontrakts förnyelse dokument.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="5ddd7-118">Du kan använda exempelfiler för att träna och testa dina klassificerare och utdrag i din modell.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="5ddd7-119">Exempelfilerna innehåller exempel på vad du kan leta efter när du försöker identifiera och extrahera data från filer.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="5ddd7-120">Du kan till exempel utbilda dina klassificeringar och utdrag med exempel på förnyelse dokument som företaget samarbetar med.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="5ddd7-121">Du kan också använda exempelfiler för att testa effektiviteten hos modellen.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="5ddd7-122">När du har publicerat modellen kan du använda innehålls centret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="5ddd7-123">Se även</span><span class="sxs-lookup"><span data-stu-id="5ddd7-123">See Also</span></span>
[<span data-ttu-id="5ddd7-124">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="5ddd7-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="5ddd7-125">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="5ddd7-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="5ddd7-126">[Skapa ett innehålls Center](create-a-content-center.md) 
 [Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="5ddd7-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="5ddd7-127">[Använda en modell](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="5ddd7-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="5ddd7-128">Skillnaden mellan ett dokument och en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="5ddd7-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="5ddd7-129">Översikt över formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="5ddd7-129">Form processing overview</span></span>](form-processing-overview.md)
