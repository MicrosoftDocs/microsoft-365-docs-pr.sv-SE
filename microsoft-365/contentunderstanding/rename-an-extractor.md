---
title: Byt namn på en extraktor i Microsoft SharePoint Syntex.
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
description: Lär dig hur och varför du byter namn på en extraktor i Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446054"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="bf786-103">Byt namn på en extraktor i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="bf786-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="bf786-104">Förr eller senare kan du behöva byta namn på en extraktor om du vill referera till ett extraherat datafält med ett annat namn.</span><span class="sxs-lookup"><span data-stu-id="bf786-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="bf786-105">Din organisation bestämmer sig till exempel för att ändra sina kontraktsdokument och refererar till "kunder" som "klienter" i sina dokument.</span><span class="sxs-lookup"><span data-stu-id="bf786-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="bf786-106">Om du extraherade ett "Kund"-fält i modellen kan du välja att byta namn på det till "Klient".</span><span class="sxs-lookup"><span data-stu-id="bf786-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="bf786-107">När du synkroniserar din uppdaterade modell till ditt SharePoint-dokumentbibliotek ser du en ny Klientkolumn i dokumentbiblioteksvyn.</span><span class="sxs-lookup"><span data-stu-id="bf786-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="bf786-108">Vyn behåller kolumnen "Kund" för tidigare aktivitet, men uppdaterar den nya kolumnen "Klient" för alla nya dokument som bearbetas av modellen.</span><span class="sxs-lookup"><span data-stu-id="bf786-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="bf786-109">Se till att synkronisera den uppdaterade modellen med de dokumentbibliotek där du tidigare använt den för att det nya kolumnnamnet ska visas.</span><span class="sxs-lookup"><span data-stu-id="bf786-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="bf786-110">Byta namn på en extraktor</span><span class="sxs-lookup"><span data-stu-id="bf786-110">Rename an extractor</span></span>

<span data-ttu-id="bf786-111">Följ dessa steg om du vill byta namn på en entitetsextraktor.</span><span class="sxs-lookup"><span data-stu-id="bf786-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="bf786-112">I innehållscentret väljer du **Modeller** för att visa listan med modeller.</span><span class="sxs-lookup"><span data-stu-id="bf786-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="bf786-113">På sidan **Modeller**, i kolumnen **Name**, väljer du den modell för vilken du vill byta namn på en extraktor.</span><span class="sxs-lookup"><span data-stu-id="bf786-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="bf786-114">Under **Entitetsextraktor** väljer du namnet på den extraktor som du vill byta namn på och väljer sedan **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="bf786-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Skärmbild av avsnittet Entitetsextraktor med en vald extraktor med alternativet Byt namn markerat.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="bf786-116">På panelen **Byt namn på entitetsextraktorn**:</span><span class="sxs-lookup"><span data-stu-id="bf786-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="bf786-117">a.</span><span class="sxs-lookup"><span data-stu-id="bf786-117">a.</span></span> <span data-ttu-id="bf786-118">Under **Nytt namn** anger du det nya namnet på extraktorn.</span><span class="sxs-lookup"><span data-stu-id="bf786-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Skärmbild som visar panelen Entitetsextraktor.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="bf786-120">b.</span><span class="sxs-lookup"><span data-stu-id="bf786-120">b.</span></span> <span data-ttu-id="bf786-121">(Valfritt) Under **Avancerade inställningar** välj om du vill associera en befintlig webbplatskolumn.</span><span class="sxs-lookup"><span data-stu-id="bf786-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="bf786-122">Välj **Byt namn**.</span><span class="sxs-lookup"><span data-stu-id="bf786-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf786-123">Se även</span><span class="sxs-lookup"><span data-stu-id="bf786-123">See Also</span></span>
[<span data-ttu-id="bf786-124">Skapa en extraherare</span><span class="sxs-lookup"><span data-stu-id="bf786-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="bf786-125">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="bf786-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="bf786-126">Byt namn på en modell</span><span class="sxs-lookup"><span data-stu-id="bf786-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="bf786-127">Förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="bf786-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="bf786-128">Använd termlagringstaxonomi vid skapande av extraktor</span><span class="sxs-lookup"><span data-stu-id="bf786-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="bf786-129">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="bf786-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="bf786-130">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="bf786-130">Apply a model</span></span>](apply-a-model.md) 
