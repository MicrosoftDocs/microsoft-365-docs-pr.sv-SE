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
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405635"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="7c65b-103">Översikt över formulär bearbetning (för hands version)</span><span class="sxs-lookup"><span data-stu-id="7c65b-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="7c65b-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="7c65b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="7c65b-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="7c65b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="7c65b-106">Project cortex använder Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="7c65b-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="7c65b-107">Du kan använda hjälp av AI Builder för att skapa AI-modeller som använder maskin Learning Technology för att identifiera och extrahera nyckelord och tabell data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="7c65b-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="7c65b-108">Företag tar ofta emot fakturor i stora mängder och från en mängd olika källor, till exempel e-post, Fax, e-post eller personligen.</span><span class="sxs-lookup"><span data-stu-id="7c65b-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="7c65b-109">Det kan ta en avsevärd tid att bearbeta dessa dokument och ange dem manuellt i databasen.</span><span class="sxs-lookup"><span data-stu-id="7c65b-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="7c65b-110">Genom att använda AI för att extrahera text, viktiga par och tabeller från dina dokument automatiserar formulär bearbetning den processen.</span><span class="sxs-lookup"><span data-stu-id="7c65b-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="7c65b-111">Du kan till exempel skapa en modell för formulär bearbetning som identifierar alla inköps order dokument som laddas upp till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="7c65b-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="7c65b-112">Och från varje inköps order kan du extrahera och visa specifika data som är viktiga för dig, till exempel *inköps order nummer*, *datum*eller *totalkostnad*.</span><span class="sxs-lookup"><span data-stu-id="7c65b-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="7c65b-113">Du använder exempel filer för att träna modellen och ange vilken information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="7c65b-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="7c65b-114">Layouten i dokumentet bevaras genom att öva på modellen.</span><span class="sxs-lookup"><span data-stu-id="7c65b-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="7c65b-115">Du behöver bara fem formulär dokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="7c65b-115">You only need five form documents to get started.</span></span> <span data-ttu-id="7c65b-116">AI Builder analyserar dina exempel filer för par med nyckelord och du kan också manuellt identifiera dem som eventuellt inte har identifierats.</span><span class="sxs-lookup"><span data-stu-id="7c65b-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="7c65b-117">Med hjälp av AI-verktyget kan du testa korrektheten hos dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="7c65b-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="7c65b-118">När du tränar och publicerar modellen kan du använda den för att skapa ett [energi](https://docs.microsoft.com/power-automate/getting-started)spår.</span><span class="sxs-lookup"><span data-stu-id="7c65b-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="7c65b-119">Flödet körs när en fil laddas upp till SharePoint-dokumentbiblioteket och extraherar data som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="7c65b-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="7c65b-120">Extraherade data visas i kolumner i modellens dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="7c65b-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="7c65b-121">En 365 Office-administratör måste [Aktivera formulär bearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) för att användare ska kunna [skapa en modell för formulär bearbetning](create-a-form-processing-model.md) i SharePoint-dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="7c65b-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="7c65b-122">Se även</span><span class="sxs-lookup"><span data-stu-id="7c65b-122">See Also</span></span>
  
[<span data-ttu-id="7c65b-123">Automatiserad energi dokumentation</span><span class="sxs-lookup"><span data-stu-id="7c65b-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="7c65b-124">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="7c65b-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="7c65b-125">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="7c65b-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="7c65b-126">Utbildning: förbättra företags prestanda med hjälp av AI Builder</span><span class="sxs-lookup"><span data-stu-id="7c65b-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




