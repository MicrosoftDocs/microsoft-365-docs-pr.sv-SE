---
title: Översikt över formulär bearbetning (för hands version)
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
description: Lär dig mer om formulär bearbetning i Project cortex.
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612732"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="da512-103">Översikt över formulär bearbetning (för hands version)</span><span class="sxs-lookup"><span data-stu-id="da512-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="da512-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="da512-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="da512-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="da512-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="da512-106">Project cortex använder Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="da512-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="da512-107">Du kan använda hjälp av AI Builder för att skapa AI-modeller som använder maskin inlärnings teknologi för att identifiera och extrahera nyckelord och tabell data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="da512-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="da512-108">Företag tar ofta emot fakturor i stora mängder och från en mängd olika källor, till exempel e-post, Fax, e-post eller personligen.</span><span class="sxs-lookup"><span data-stu-id="da512-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="da512-109">Det kan ta en avsevärd tid att bearbeta dessa dokument och ange dem manuellt i databasen.</span><span class="sxs-lookup"><span data-stu-id="da512-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="da512-110">Genom att använda AI för att extrahera text, viktiga par och tabeller från dina dokument automatiserar formulär bearbetning den processen.</span><span class="sxs-lookup"><span data-stu-id="da512-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="da512-111">Du kan till exempel skapa en modell för formulär bearbetning som identifierar alla inköps order dokument som laddas upp till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="da512-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="da512-112">Och från varje inköps order kan du extrahera och visa specifika data som är viktiga för dig, till exempel *inköps order nummer*, *datum*eller *totalkostnad*.</span><span class="sxs-lookup"><span data-stu-id="da512-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="da512-113">Du använder exempel filer för att träna modellen och ange vilken information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="da512-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="da512-114">Layouten i dokumentet bevaras genom att öva på modellen.</span><span class="sxs-lookup"><span data-stu-id="da512-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="da512-115">Du behöver bara fem formulär dokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="da512-115">You only need five form documents to get started.</span></span> <span data-ttu-id="da512-116">AI-byggnaden analyserar dina exempel filer för par med nyckelord och du kan också manuellt identifiera dem som eventuellt inte har identifierats.</span><span class="sxs-lookup"><span data-stu-id="da512-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="da512-117">Med hjälp av AI-verktyget kan du testa korrektheten hos dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="da512-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="da512-118">När du tränar och publicerar modellen kan du använda den för att skapa ett [Power automatiserat flöde](https://docs.microsoft.com/power-automate/getting-started) som körs när en fil laddas upp till SharePoint-dokumentbiblioteket och hämtar data som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="da512-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="da512-119">Extraherade data visas i kolumner i modellens dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="da512-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="da512-120">En 365 Office-administratör måste [Aktivera formulär bearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) för att användare ska kunna [skapa en modell för formulär bearbetning](create-a-form-processing-model.md) i SharePoint-dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="da512-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="da512-121">Se även</span><span class="sxs-lookup"><span data-stu-id="da512-121">See Also</span></span>
  
[<span data-ttu-id="da512-122">Automatiserad energi dokumentation</span><span class="sxs-lookup"><span data-stu-id="da512-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="da512-123">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="da512-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="da512-124">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="da512-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="da512-125">Utbildning: förbättra företags prestanda med hjälp av AI Builder</span><span class="sxs-lookup"><span data-stu-id="da512-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




