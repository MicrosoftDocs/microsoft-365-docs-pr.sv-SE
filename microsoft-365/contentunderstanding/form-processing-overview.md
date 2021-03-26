---
title: Översikt av formulär bearbetning
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
description: Läs mer om formulärbearbetning i Microsoft SharePoint Syntex
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222263"
---
# <a name="form-processing-overview"></a><span data-ttu-id="9d77a-103">Översikt av formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="9d77a-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="9d77a-105">I Microsoft SharePoint Syntex används formulärbearbetning i Microsoft PowerApps [AI Builder](/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="9d77a-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="9d77a-106">Du kan använda formulärbearbetning i AI Builder för att skapa AI-modeller där maskininlärning används för att identifiera och extrahera nyckelvärdepar och tabelldata från strukturerade eller delvis strukturerade dokument, som formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="9d77a-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="9d77a-107">Organisationer får ofta fakturor i stora kvantiteter från en mängd olika källor, t. ex. post, fax, e-post osv. Det kan ta lång tid att bearbeta dessa dokument och lägga till dem manuellt i en databas.</span><span class="sxs-lookup"><span data-stu-id="9d77a-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="9d77a-108">Med formulärbearbetning automatiseras processen genom att AI används för att extrahera text, nyckel/värde-par och tabeller från dina dokument.</span><span class="sxs-lookup"><span data-stu-id="9d77a-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="9d77a-109">Mer information om formulärbearbetning och scenarioexempel finns i [Införande av SharePoint Syntex: Kom igång-guide](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="9d77a-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="9d77a-110">Du kan till exempel skapa en modell för formulärbearbetning som identifierar alla inköpsorder som laddas upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="9d77a-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="9d77a-111">Från varje inköpsorder kan du extrahera och visa vissa data som är viktiga för dig, t. ex. *PO-nummer*, *datum* eller *summa*.</span><span class="sxs-lookup"><span data-stu-id="9d77a-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Dokumentbiblioteksvy](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="9d77a-113">Du använder exempelfiler för att träna modellen och definiera vilken information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="9d77a-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="9d77a-114">Dokumentets layout registreras genom att modellen tränas.</span><span class="sxs-lookup"><span data-stu-id="9d77a-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="9d77a-115">Du behöver bara fem formulärdokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="9d77a-115">You only need five form documents to get started.</span></span> <span data-ttu-id="9d77a-116">AI Builder analyserar dina exempelfiler för nyckel-värdepar och du kan även manuellt identifiera de som eventuellt inte har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="9d77a-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="9d77a-117">Med AI Builder kan du testa din modells precision mot dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="9d77a-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="9d77a-118">När du har tränat och publicerat modellen skapar modellen ett [Power Automate-flöde](/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="9d77a-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="9d77a-119">Flödet körs när en fil överförs till dokumentbiblioteket i SharePoint och hämtar data som har identifierats av modellen.</span><span class="sxs-lookup"><span data-stu-id="9d77a-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="9d77a-120">Extraherade data visas i kolumner i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="9d77a-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="9d77a-121">En Office 365-administratör måste [aktivera formulärbearbetning](./set-up-content-understanding.md) för SharePoint-dokumentbiblioteket för att användarna ska kunna [skapa en modell för formulärbearbetning](create-a-form-processing-model.md) i det.</span><span class="sxs-lookup"><span data-stu-id="9d77a-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="9d77a-122">Du kan välja webbplatser under eller efter konfigurationen i dina hanteringsinställningar.</span><span class="sxs-lookup"><span data-stu-id="9d77a-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="9d77a-123">Filbegränsningar</span><span class="sxs-lookup"><span data-stu-id="9d77a-123">File limitations</span></span>

<span data-ttu-id="9d77a-124">När du använder formulärbearbetningsmodeller ska du observera [kraven och begränsningar för filanvändningen](/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="9d77a-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="9d77a-125">Multi-Geo miljöer</span><span class="sxs-lookup"><span data-stu-id="9d77a-125">Multi-Geo environments</span></span>

<span data-ttu-id="9d77a-126">När Du konfigurerar SharePoint Syntex i en [Microsoft 365 Multi-Geo-miljö](../enterprise/microsoft-365-multi-geo.md)kan du bara konfigurera den så att den använder formulärbearbetning på den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="9d77a-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="9d77a-127">Om du vill använda formulärbearbetning på en lokal plats kontaktar du Microsofts support.</span><span class="sxs-lookup"><span data-stu-id="9d77a-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="9d77a-128">Se även</span><span class="sxs-lookup"><span data-stu-id="9d77a-128">See Also</span></span>
  
[<span data-ttu-id="9d77a-129">Power Automate-dokumentation</span><span class="sxs-lookup"><span data-stu-id="9d77a-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="9d77a-130">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="9d77a-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="9d77a-131">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="9d77a-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="9d77a-132">Utbildning: Förbättra affärsprestanda med AI Builder</span><span class="sxs-lookup"><span data-stu-id="9d77a-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)