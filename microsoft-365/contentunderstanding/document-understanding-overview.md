---
title: Dokument översikt (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Få en översikt över dokument kunskapen i Project cortex.
ms.openlocfilehash: c1e4092164ee96d4f244f10be9ebab62a2c8da5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950054"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="bc524-103">Dokument översikt (för hands version)</span><span class="sxs-lookup"><span data-stu-id="bc524-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="bc524-104">Project cortex är för närvarande för hands version.</span><span class="sxs-lookup"><span data-stu-id="bc524-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="bc524-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="bc524-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="bc524-106">Med dokument användning används AI-modeller för att automatisera klassificering av filer och extrahering av information.</span><span class="sxs-lookup"><span data-stu-id="bc524-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="bc524-107">Den fungerar bäst med ostrukturerade dokument, som till exempel brev och kontrakt.</span><span class="sxs-lookup"><span data-stu-id="bc524-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="bc524-108">Dokumenten bör innehålla text som kan identifieras baserat på fraser eller mönster.</span><span class="sxs-lookup"><span data-stu-id="bc524-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="bc524-109">Den identifierade texten kan ange både den typ av fil den är (dess klassificering) och vad du vill extrahera (dess utdrag).</span><span class="sxs-lookup"><span data-stu-id="bc524-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="bc524-110">Dokument förståelse modeller skapas och hanteras i en typ av SharePoint-webbplats som kallas för innehålls Center.</span><span class="sxs-lookup"><span data-stu-id="bc524-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="bc524-111">När den används i ett SharePoint-dokumentbibliotek är modellen kopplad till en innehålls typ som har kolumner där den extraherade informationen lagras.</span><span class="sxs-lookup"><span data-stu-id="bc524-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="bc524-112">Innehålls typen du skapar lagras i galleriet för SharePoint-innehålls typ.</span><span class="sxs-lookup"><span data-stu-id="bc524-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="bc524-113">Du kan också välja att använda befintliga innehålls typer för att använda deras schema.</span><span class="sxs-lookup"><span data-stu-id="bc524-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="bc524-114">Du kan lägga till *klassificerare* och *utdrag* i dina dokument för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="bc524-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="bc524-115">Klassificerare används för att identifiera och klassificera dokument som laddas upp till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="bc524-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="bc524-116">En klassificerare kan till exempel vara "utbildad" för att identifiera alla *förnyelse* dokument som laddas upp till biblioteket.</span><span class="sxs-lookup"><span data-stu-id="bc524-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="bc524-117">Innehålls typen kontrakt förnyelse definieras av dig när du skapar en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="bc524-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="bc524-118">Utdrag ur dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="bc524-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="bc524-119">För alla kontrakt förnyelse dokument som identifieras i dokument biblioteket visas kolumnerna i vyn som också visar *tjänstens start datum* och  *klient* för varje kontrakts förnyelse dokument.</span><span class="sxs-lookup"><span data-stu-id="bc524-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="bc524-120">Du använder exempel filer för att träna och testa dina klassificerare och utdrag i din modell.</span><span class="sxs-lookup"><span data-stu-id="bc524-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="bc524-121">Exempel på filer ger modellen ett exempel på vad du kan leta efter när du försöker identifiera och hämta data från filer.</span><span class="sxs-lookup"><span data-stu-id="bc524-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="bc524-122">Du kan till exempel utbilda dina klassificeringar och utdrag med ett exempel på förnyelse dokument som företaget samarbetar med.</span><span class="sxs-lookup"><span data-stu-id="bc524-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="bc524-123">Du kan också använda exempel filer för att testa effektiviteten hos modellen.</span><span class="sxs-lookup"><span data-stu-id="bc524-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="bc524-124">När du har publicerat modellen kan du använda innehålls centret för att tillämpa den på alla SharePoint-dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="bc524-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="bc524-125">Se även</span><span class="sxs-lookup"><span data-stu-id="bc524-125">See Also</span></span>
[<span data-ttu-id="bc524-126">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="bc524-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="bc524-127">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="bc524-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="bc524-128">[Skapa ett innehålls Center](create-a-content-center.md) 
 [Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="bc524-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="bc524-129">[Använda en modell](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="bc524-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="bc524-130">Skillnaden mellan ett dokument och en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="bc524-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="bc524-131">Översikt över formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="bc524-131">Form processing overview</span></span>](form-processing-overview.md)




