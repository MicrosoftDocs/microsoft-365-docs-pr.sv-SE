---
title: Duplicera en modell i Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lär dig hur och varför du duplicerar en modell i Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446083"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="1ab80-103">Duplicera en modell i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="1ab80-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="1ab80-104">Att skapa en dokumenttolkningsmodell kan spara tid och arbete om du behöver skapa en ny modell och vet att en befintlig modell liknar den du behöver.</span><span class="sxs-lookup"><span data-stu-id="1ab80-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="1ab80-105">Till exempel klassificerar en befintligt modell med namnet ”Kontrakt” samma filer som du behöver arbeta med.</span><span class="sxs-lookup"><span data-stu-id="1ab80-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="1ab80-106">Den nya modellen extraherar en del av befintliga data men måste uppdateras för att extrahera ytterligare data.</span><span class="sxs-lookup"><span data-stu-id="1ab80-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="1ab80-107">I stället för att skapa och träna en ny modell från grunden kan du använda funktionen för att duplicera modeller för att göra en kopia av Kontrakt-modellen, vilket också kommer kopiera alla associerade träningsobjekt, som exempelfiler och entitetsextraktorer.</span><span class="sxs-lookup"><span data-stu-id="1ab80-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="1ab80-108">När du duplicerar modellen kan du efter att du bytt namn på den (till exempel till ”Kontraktförnyelser”) göra uppdateringar på den.</span><span class="sxs-lookup"><span data-stu-id="1ab80-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="1ab80-109">Du kan till exempel välja att ta bort vissa av de befintliga extraherade fälten som du inte behöver och sedan träna modellen att extrahera ett nytt (till exempel ”Förnyelsedatum”).</span><span class="sxs-lookup"><span data-stu-id="1ab80-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="1ab80-110">Duplicera en modell</span><span class="sxs-lookup"><span data-stu-id="1ab80-110">Duplicate a model</span></span>

<span data-ttu-id="1ab80-111">Följ dessa steg för att duplicera en dokumenttolkningsmodell.</span><span class="sxs-lookup"><span data-stu-id="1ab80-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="1ab80-112">I innehållscentret väljer du **Modeller** för att visa listan med modeller.</span><span class="sxs-lookup"><span data-stu-id="1ab80-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="1ab80-113">På sidan **Modeller** väljer du den modell du vill duplicera.</span><span class="sxs-lookup"><span data-stu-id="1ab80-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="1ab80-114">Genom att använda menyfliksområdet eller knappen **Visa åtgärder** (bredvid modellnamnet) väljer du **Duplicera**.</span><span class="sxs-lookup"><span data-stu-id="1ab80-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Skärmbild av sidan Modeller som visar en vald modell med alternativen för Duplicera markerade.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="1ab80-116">På panelen **Duplicera modell**:</span><span class="sxs-lookup"><span data-stu-id="1ab80-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="1ab80-117">a.</span><span class="sxs-lookup"><span data-stu-id="1ab80-117">a.</span></span> <span data-ttu-id="1ab80-118">Under **Namn** anger du det nya namnet på modellen som du vill duplicera.</span><span class="sxs-lookup"><span data-stu-id="1ab80-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Skärmbild som visar panelen Duplicera modell.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="1ab80-120">b.</span><span class="sxs-lookup"><span data-stu-id="1ab80-120">b.</span></span> <span data-ttu-id="1ab80-121">Under **Beskrivning** lägger du till en beskrivning för den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="1ab80-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="1ab80-122">c.</span><span class="sxs-lookup"><span data-stu-id="1ab80-122">c.</span></span> <span data-ttu-id="1ab80-123">(Valfritt) Under **Avancerade inställningar** väljer du om du vill associera en befintlig [innehållstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span><span class="sxs-lookup"><span data-stu-id="1ab80-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="1ab80-124">Välj **Duplicera**.</span><span class="sxs-lookup"><span data-stu-id="1ab80-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ab80-125">Se även</span><span class="sxs-lookup"><span data-stu-id="1ab80-125">See Also</span></span>
[<span data-ttu-id="1ab80-126">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="1ab80-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="1ab80-127">Byt namn på en modell</span><span class="sxs-lookup"><span data-stu-id="1ab80-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="1ab80-128">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="1ab80-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="1ab80-129">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="1ab80-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="1ab80-130">Förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="1ab80-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="1ab80-131">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="1ab80-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="1ab80-132">Tillgänglighetsläge för SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="1ab80-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)