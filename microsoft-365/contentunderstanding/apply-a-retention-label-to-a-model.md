---
title: Använda kvarhållningsetiketter på modeller för dokumenttolkning
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
description: Den här artikeln tar upp hur du använder kvarhållningsetiketter på modeller för dokumenttolkning
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976561"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="d7926-103">Använda kvarhållningsetiketter på modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="d7926-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="d7926-104">Du kan enkelt använda en [kvarhållningsetikett](https://docs.microsoft.com/microsoft-365/compliance/retention) på en modell för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="d7926-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="d7926-105">Med hjälp av kvarhållningsetiketter kan du använda kvarhållningsinställningar för dokument som modellen för dokumenttolkning förstår.</span><span class="sxs-lookup"><span data-stu-id="d7926-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="d7926-106">Du vill till exempel kanske att din modell inte bara ska identifiera *Försäkringar* som laddats upp till dokumentbiblioteket, utan även använda kvarhållningsetiketten *Företag* på dem så att dokumenten inte kan tas bort från dokumentbiblioteket under den angivna tidsperioden (till exempel de kommande fem månaderna).</span><span class="sxs-lookup"><span data-stu-id="d7926-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="d7926-107">Du kan använda en befintlig kvarhållningsetikett på modellen för dokumenttolkning i modellinställningarna på modellens startsida.</span><span class="sxs-lookup"><span data-stu-id="d7926-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="d7926-108">För att kvarhållningsetiketterna ska vara tillgängliga att använda på din modell för innehållstolkning måste de [skapas och publiceras i Microsoft 365 Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d7926-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="d7926-109">Att använda kvarhållningsetiketter på modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="d7926-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="d7926-110">På modellens startsida väljer du **Modellinställningar**.</span><span class="sxs-lookup"><span data-stu-id="d7926-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="d7926-111">I **Modelinställningar**, i avsnittet **Säkerhet och efterlevnad**, väljer du menyn **Kvarhållningsetikett** för en lista över de kvarhållningsetiketter som finns tillgängliga att använda på modellen.</span><span class="sxs-lookup"><span data-stu-id="d7926-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="d7926-112">![Kvarhållningsetikettmenyn](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="d7926-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="d7926-113">Välj den kvarhållningsetikett som du vill använda för modellen och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d7926-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="d7926-114">När du har använt kvarhållningsetiketten på din modell kan du använda den på:</span><span class="sxs-lookup"><span data-stu-id="d7926-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="d7926-115">Ett nytt dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="d7926-115">New document library</span></span>
- <span data-ttu-id="d7926-116">Ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="d7926-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="d7926-117">Använd kvarhållningsetiketten på ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="d7926-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="d7926-118">Om modellen för dokumenttolkning redan har använts på ett dokumentbibliotek kan du göra följande för att synkronisera din uppdatering av kvarhållningsetiketten så att den används på dokumentbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="d7926-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="d7926-119">På modellens startsida, i avsnittet **Bibliotek med den här modellen** väljer du det dokumentbibliotek på vilket du vill använda uppdateringen av kvarhållningsetiketten.</span><span class="sxs-lookup"><span data-stu-id="d7926-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="d7926-120">Välj **Synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="d7926-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="d7926-121">![Synkronisera modell](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="d7926-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="d7926-122">Efter tillämpning av uppdateringen och synkronisering med modellen kan du kontrollera att den har använts genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="d7926-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="d7926-123">I innehållscentret går du till avsnittet **Bibliotek med den här modellen**. Klicka på det bibliotek där din uppdaterade modell används.</span><span class="sxs-lookup"><span data-stu-id="d7926-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="d7926-124">I vyn dokumentbibliotek väljer du informationsikonen för att kontrollera modellens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="d7926-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="d7926-125">I listan över **Aktiva modeller** väljer du den uppdaterade modellen.</span><span class="sxs-lookup"><span data-stu-id="d7926-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="d7926-126">I avsnittet **Kvarhållningsetikett** ser du namnet på den kvarhållningsetikett som används.</span><span class="sxs-lookup"><span data-stu-id="d7926-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="d7926-127">På modellens visningssida i dokumentbiblioteket visas en ny kolumn för **Kvarhållningsetikett**.</span><span class="sxs-lookup"><span data-stu-id="d7926-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="d7926-128">Allt eftersom modellen klassificerar filer som tillhör dess innehållstyp och listar dem i biblioteksvyn visas också namnet på den kvarhållningsetikett som har använts på den genom modellen.</span><span class="sxs-lookup"><span data-stu-id="d7926-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="d7926-129">Till exempel kommer alla *Försäkringar* som modellen identifierar att ha kvarhållningsetiketten *Företag* så att de inte kan tas bort från dokumentbiblioteket på fem månader.</span><span class="sxs-lookup"><span data-stu-id="d7926-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="d7926-130">Om du försöker ta bort filen från dokumentbiblioteket visas ett felmeddelande om att det inte är tillåtet eftersom kvarhållningsetiketten används.</span><span class="sxs-lookup"><span data-stu-id="d7926-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7926-131">Se även</span><span class="sxs-lookup"><span data-stu-id="d7926-131">See Also</span></span>
[<span data-ttu-id="d7926-132">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="d7926-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d7926-133">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="d7926-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d7926-134">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="d7926-134">Document Understanding overview</span></span>](document-understanding-overview.md)


