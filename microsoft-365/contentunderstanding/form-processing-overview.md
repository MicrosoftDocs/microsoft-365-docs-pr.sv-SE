---
title: Översikt av formulär bearbetning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Läs mer om formulärbearbetning i Microsoft SharePoint Syntex
ms.openlocfilehash: 9b5b9b1c54220037e1c10f2722a641b526592f84
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338619"
---
# <a name="form-processing-overview"></a><span data-ttu-id="477a6-103">Översikt av formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="477a6-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="477a6-105">I Microsoft SharePoint Syntex används formulärbearbetning i Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="477a6-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="477a6-106">Du kan använda formulärbearbetning i AI Builder för att skapa AI-modeller där maskininlärning används för att identifiera och extrahera nyckelvärdepar och tabelldata från strukturerade eller delvis strukturerade dokument, som formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="477a6-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="477a6-107">Organisationer får ofta fakturor i stora kvantiteter från en mängd olika källor, t. ex. post, fax, e-post osv. Det kan ta lång tid att bearbeta dessa dokument och lägga till dem manuellt i en databas.</span><span class="sxs-lookup"><span data-stu-id="477a6-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="477a6-108">Genom att använda AI för att extrahera text, nyckel/värdepar och tabeller från dina dokument utförs formulärbearbetningen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="477a6-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="477a6-109">Mer information om formulärbearbetning och scenarioexempel finns i [Införande av SharePoint Syntex: Kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="477a6-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="477a6-110">Du kan till exempel skapa en modell för formulärbearbetning som identifierar alla inköpsordrar som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="477a6-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="477a6-111">Från varje inköpsorder kan du extrahera och visa vissa data som är viktiga för dig, t. ex. *PO-nummer*, *datum* eller *summa*.</span><span class="sxs-lookup"><span data-stu-id="477a6-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Dokumentbiblioteksvy](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="477a6-113">Du kan också använda exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="477a6-113">You can also use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="477a6-114">Dokumentets layout lärs in genom att modellen tränas och lär sig att extrahera data från liknande platser i dina formulär eftersom de har en liknande layout med liknande struktur.</span><span class="sxs-lookup"><span data-stu-id="477a6-114">The layout of your document is learned by training your model, and it learns to extract your data from similar locations in your forms since they have a similar structured layout.</span></span> 

<span data-ttu-id="477a6-115">Du behöver minst fem formulärdokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="477a6-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="477a6-116">AI Builder analyserar dina exempelfiler för nyckel-värdepar och identifierar sedan manuellt de som eventuellt inte har identifierats.</span><span class="sxs-lookup"><span data-stu-id="477a6-116">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="477a6-117">Med AI Builder kan du testa din modells precision mot dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="477a6-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="477a6-118">När du har tränat och publicerat modellen kan du använda den för att skapa ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started) som körs när en fil laddats upp till dokumentbiblioteket i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="477a6-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="477a6-119">Därefter extraheras de data som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="477a6-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="477a6-120">Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="477a6-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="477a6-121">Du använder exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="477a6-121">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="477a6-122">Dokumentets layout registreras genom att modellen tränas.</span><span class="sxs-lookup"><span data-stu-id="477a6-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="477a6-123">Du behöver bara fem formulärdokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="477a6-123">You only need five form documents to get started.</span></span> <span data-ttu-id="477a6-124">AI Builder analyserar dina exempelfiler för nyckel-värdepar och du kan även manuellt identifiera de som eventuellt inte har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="477a6-124">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="477a6-125">Med AI Builder kan du testa din modells precision mot dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="477a6-125">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="477a6-126">När du har tränat och publicerat modellen skapar modellen ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="477a6-126">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="477a6-127">Flödet körs när en fil överförs till dokumentbiblioteket i SharePoint och hämtar data som har identifierats av modellen.</span><span class="sxs-lookup"><span data-stu-id="477a6-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="477a6-128">Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="477a6-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="477a6-129">En Office 365-administratör måste [aktivera formulärbearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) för SharePoint-dokumentbiblioteket för att användarna ska kunna [skapa en modell för formulärbearbetning](create-a-form-processing-model.md) i det.</span><span class="sxs-lookup"><span data-stu-id="477a6-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="477a6-130">Du kan välja webbplatser under eller efter konfigurationen i dina hanteringsinställningar.</span><span class="sxs-lookup"><span data-stu-id="477a6-130">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="477a6-131">Se även</span><span class="sxs-lookup"><span data-stu-id="477a6-131">See Also</span></span>
  
[<span data-ttu-id="477a6-132">Power Automate-dokumentation</span><span class="sxs-lookup"><span data-stu-id="477a6-132">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="477a6-133">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="477a6-133">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="477a6-134">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="477a6-134">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="477a6-135">Utbildning: Förbättra affärsprestanda med AI Builder</span><span class="sxs-lookup"><span data-stu-id="477a6-135">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
