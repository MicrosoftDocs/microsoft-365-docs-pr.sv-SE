---
title: Använda en bevarande etikett på en dokument modell
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: I den här artikeln beskrivs hur du använder en bevarande etikett på en dokument förståelse
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294940"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="b736e-103">Använda en bevarande etikett på en dokument modell</span><span class="sxs-lookup"><span data-stu-id="b736e-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="b736e-104">Du kan enkelt använda en [behållnings etikett](https://docs.microsoft.com/microsoft-365/compliance/retention) för att förstå en modell i Microsoft SharePoint-Syntex.</span><span class="sxs-lookup"><span data-stu-id="b736e-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="b736e-105">Med behållnings etiketter kan du tillämpa inställningar för behållning för de dokument som ditt dokument förstår.</span><span class="sxs-lookup"><span data-stu-id="b736e-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="b736e-106">Om du till exempel vill att din modell inte bara ska identifiera några *försäkrings* dokument som laddas upp till dokument biblioteket, men om du även vill använda en affärsmall för ett *företag* , så att dessa dokument inte kan tas bort från dokument biblioteket för den angivna tids perioden (till exempel följande fem månader).</span><span class="sxs-lookup"><span data-stu-id="b736e-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="b736e-107">Du kan använda en befintlig behållnings etikett till dokumentet förstå modellen via modell inställningarna på modellens start sida.</span><span class="sxs-lookup"><span data-stu-id="b736e-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="b736e-108">För att lagrings etiketterna ska vara tillgängliga för att tillämpas på din innehålls förståelses modell måste de [skapas och publiceras i Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b736e-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="b736e-109">Så här lägger du till en bevarande etikett i en dokument modell</span><span class="sxs-lookup"><span data-stu-id="b736e-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="b736e-110">Välj **modell inställningar**från start sidan för modellen.</span><span class="sxs-lookup"><span data-stu-id="b736e-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="b736e-111">I **modell inställningar**i avsnittet **säkerhet och efterlevnad** väljer du menyn **bevarande etikett** för att se en lista över behållnings etiketter som är tillgängliga för att tillämpas på modellen.</span><span class="sxs-lookup"><span data-stu-id="b736e-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="b736e-112">![Menyn bevarande etikett](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="b736e-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="b736e-113">Välj den bevarande etikett som du vill använda för modellen och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b736e-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="b736e-114">När du har använt den här etiketten i din modell kan du använda den på en:</span><span class="sxs-lookup"><span data-stu-id="b736e-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="b736e-115">Nytt dokument bibliotek</span><span class="sxs-lookup"><span data-stu-id="b736e-115">New document library</span></span>
- <span data-ttu-id="b736e-116">Dokument bibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="b736e-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="b736e-117">Använda etiketten för att lägga till ett dokument bibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="b736e-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="b736e-118">Om du redan har använt en modell för dokument förståelse i ett dokument bibliotek kan du göra följande för att synkronisera uppdaterings etiketten så att den används i dokument biblioteket:</span><span class="sxs-lookup"><span data-stu-id="b736e-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="b736e-119">Välj det dokument bibliotek som du vill tillämpa etikett uppdateringen för i avsnittet **bibliotek med den här modellen** på modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="b736e-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="b736e-120">Välj **Synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="b736e-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="b736e-121">![Synkroniseringsklient](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="b736e-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="b736e-122">När du har tillämpat uppdateringen och synkroniserat den med modellen kan du bekräfta att den har tillämpats genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="b736e-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="b736e-123">I innehålls centret, i avsnittet **bibliotek med den här modellen** , klickar du på det bibliotek där den uppdaterade modellen användes.</span><span class="sxs-lookup"><span data-stu-id="b736e-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="b736e-124">I vyn dokument bibliotek väljer du informations ikonen för att kontrol lera modell egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="b736e-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="b736e-125">I listan **aktiva modeller** väljer du den uppdaterade modellen.</span><span class="sxs-lookup"><span data-stu-id="b736e-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="b736e-126">I avsnittet **bevarande etikett** ser du namnet på den använda lagrings etiketten.</span><span class="sxs-lookup"><span data-stu-id="b736e-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="b736e-127">På modellens visnings sida i dokument biblioteket visas en ny kolumn för **bevarande etikett** .</span><span class="sxs-lookup"><span data-stu-id="b736e-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="b736e-128">När din modell klassificerar filer som identifieras som tillhör ande innehålls typ och visar dem i vyn Bibliotek, visas även namnet på den behållnings etikett som har lagts till i modellen med hjälp av mallen för kvarhållande.</span><span class="sxs-lookup"><span data-stu-id="b736e-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="b736e-129">Till exempel, alla *meddelanden om försäkrings brev* som modellen identifierar kommer att ha etiketten för *affärs* innehåll som du använder för att förhindra att de tas bort från dokument biblioteket för fem månader.</span><span class="sxs-lookup"><span data-stu-id="b736e-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="b736e-130">Om ett försök görs att ta bort filen från dokument biblioteket visas ett fel meddelande om att det inte är tillåtet på grund av den använda lagrings etiketten.</span><span class="sxs-lookup"><span data-stu-id="b736e-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="b736e-131">Se även</span><span class="sxs-lookup"><span data-stu-id="b736e-131">See Also</span></span>
[<span data-ttu-id="b736e-132">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="b736e-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b736e-133">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="b736e-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="b736e-134">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="b736e-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="b736e-135">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="b736e-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
