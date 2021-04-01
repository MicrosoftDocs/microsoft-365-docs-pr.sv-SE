---
title: Byt namn på en modell i Microsoft SharePoint Syntex
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
description: Lär dig hur och varför du byter namn på en modell i Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446060"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="2fe3f-103">Byt namn på en modell i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2fe3f-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="2fe3f-104">Vid något tillfälle kanske du vill byta namn på en modell för dokumenttolkning.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="2fe3f-105">Ett vanligt exempel är att när man skapar ett första utkast av en modell så kanske man inte har tänkt efter så noga när man namngav den (till exempel kanske man döpt den till ”AlexWilburModel1”).</span><span class="sxs-lookup"><span data-stu-id="2fe3f-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="2fe3f-106">När modellen börjar bli färdig för användning inser man att ett ordentligt namn borde vara ”Kontraktförnyelser”, och du kanske man vill byta namn på den.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="2fe3f-107">Ett annat exempel är när din organisation väljer att kalla en process eller dokumenttyp för något annat.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="2fe3f-108">Till exempel efter att du skapat din modell och är redo att använda den kanske din organisation bestämmer att alla ”kontrakt” numera formellt ska kallas ”avtal”.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="2fe3f-109">Om det behövs kan du välja att byta namn på din modell från ”Kontraktförnyelser” till “Avtalsförnyelser”.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fe3f-110">Du kan bara byta namn på en dokumenttolkningsmodell om den inte har tillämpats på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="2fe3f-111">Att byta namn på en modell byter också namnet på [innehållstypen](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) som är associerad med modellen.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="2fe3f-112">Byt namn på en modell</span><span class="sxs-lookup"><span data-stu-id="2fe3f-112">Rename a model</span></span>

<span data-ttu-id="2fe3f-113">Följ dessa steg för att byta namn på en dokumenttolkningsmodell.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="2fe3f-114">I innehållscentret väljer du **Modeller** för att visa listan med modeller.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="2fe3f-115">På sidan **Modeller** väljer du den modell du vill byta namn på.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="2fe3f-116">Genom att använda menyfliksområdet eller knappen **Visa åtgärder** (bredvid modellnamnet) väljer du **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![Skärmbild av sidan Modeller som visar en vald modell med alternativen för Byt namn markerade.](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="2fe3f-118">På panelen **Byt namn på modell** :</span><span class="sxs-lookup"><span data-stu-id="2fe3f-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="2fe3f-119">a.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-119">a.</span></span> <span data-ttu-id="2fe3f-120">Under **Nytt namn** anger du det nya namnet på modellen som du vill byta namn på.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![Skärmbild som visar panelen Byt namn på modell.](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="2fe3f-122">b.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-122">b.</span></span> <span data-ttu-id="2fe3f-123">(Valfritt) Under **Avancerade inställningar** väljer du om du vill associera en befintlig [innehållstyp](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span><span class="sxs-lookup"><span data-stu-id="2fe3f-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="2fe3f-124">Om du väljer **Använd en befintlig innehållstyp** så får modellen ett nytt namn som matchar den valda innehållstypen.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="2fe3f-125">Välj **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="2fe3f-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe3f-126">Se även</span><span class="sxs-lookup"><span data-stu-id="2fe3f-126">See Also</span></span>
[<span data-ttu-id="2fe3f-127">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="2fe3f-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="2fe3f-128">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="2fe3f-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="2fe3f-129">Byt namn på en extraktor</span><span class="sxs-lookup"><span data-stu-id="2fe3f-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="2fe3f-130">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="2fe3f-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="2fe3f-131">Förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="2fe3f-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="2fe3f-132">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="2fe3f-132">Apply a model</span></span>](apply-a-model.md) 
