---
title: Översikt över formulärbearbetning (förhandsgranskning)
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
description: Läs mer om formulärbearbetning i Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540064"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="364b2-103">Översikt över formulärbearbetning (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="364b2-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="364b2-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="364b2-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="364b2-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="364b2-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="364b2-106">Project Cortex använder Microsoft PowerApps [AI Builder-formulärbearbetning](https://docs.microsoft.com/ai-builder/overview) för att skapa modeller i SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="364b2-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="364b2-107">Du kan använda AI Builder-formulärbearbetning för att skapa AI-modeller som använder maskininlärningsteknik för att identifiera och extrahera nyckelvärdespar och tabelldata från strukturerade eller halvstrukturerade dokument, till exempel formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="364b2-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="364b2-108">Företag får ofta fakturor i stora mängder och från en mängd olika källor, till exempel post, fax, e-post eller personligen.</span><span class="sxs-lookup"><span data-stu-id="364b2-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="364b2-109">Det kan ta lång tid att bearbeta dessa dokument och manuellt skriva in dem i databasen.</span><span class="sxs-lookup"><span data-stu-id="364b2-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="364b2-110">Genom att använda AI för att extrahera text, nyckel/värde-par och tabeller från dina dokument automatiserar formulärbearbetningen den här processen.</span><span class="sxs-lookup"><span data-stu-id="364b2-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="364b2-111">Du kan till exempel skapa en formulärbearbetningsmodell som identifierar alla inköpsorderdokument som överförs till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="364b2-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="364b2-112">Och från varje inköpsorder kan du extrahera och visa specifika data som är viktiga för dig, till exempel *PO-nummer,* *Datum*eller *Total kostnad*.</span><span class="sxs-lookup"><span data-stu-id="364b2-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="364b2-113">Du använder exempelfiler för att träna din modell och definiera den information som ska extraheras från formuläret.</span><span class="sxs-lookup"><span data-stu-id="364b2-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="364b2-114">Dokumentets layout lärs genom att din modell tränas.</span><span class="sxs-lookup"><span data-stu-id="364b2-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="364b2-115">Du behöver bara fem formulärdokument för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="364b2-115">You only need five form documents to get started.</span></span> <span data-ttu-id="364b2-116">AI-byggnaden analyserar dina exempelfiler för nyckel-värde-par, och du kan också manuellt identifiera de som kanske inte har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="364b2-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="364b2-117">Med AI-byggare kan du testa modellens noggrannhet på dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="364b2-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="364b2-118">När du har tränat och publicerat modellen skapar du ett [Power Automate-flöde](https://docs.microsoft.com/power-automate/getting-started) som körs när en fil överförs till SharePoint-dokumentbiblioteket och extraherar data som har identifierats i modellen.</span><span class="sxs-lookup"><span data-stu-id="364b2-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="364b2-119">De extraherade data visas i kolumner i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="364b2-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="364b2-120">En Office 365-administratör måste [aktivera formulärbearbetning](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) för SharePoint-dokumentbiblioteket för att användare ska kunna [skapa en formulärbearbetningsmodell](create-a-form-processing-model.md) i det.</span><span class="sxs-lookup"><span data-stu-id="364b2-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="364b2-121">Se även</span><span class="sxs-lookup"><span data-stu-id="364b2-121">See Also</span></span>
  
[<span data-ttu-id="364b2-122">Dokumentation för Power Automate</span><span class="sxs-lookup"><span data-stu-id="364b2-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="364b2-123">Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="364b2-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="364b2-124">Översikt över dokuments förståelse</span><span class="sxs-lookup"><span data-stu-id="364b2-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="364b2-125">Utbildning: Förbättra företagets resultat med AI Builder</span><span class="sxs-lookup"><span data-stu-id="364b2-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




