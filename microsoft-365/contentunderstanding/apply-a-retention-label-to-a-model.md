---
title: Använda kvarhållningsetikett på modeller för dokumenttolkning
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
description: Den här artikeln diskuterar hur man tillämpar en kvarhållningsetikett på en modell i SharePoint Syntex
ms.openlocfilehash: 796130bfa967663b5696f49279154cfe9b16f703
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925374"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="ba834-103">Du kan enkelt använda en kvarhållningsetikett på en modell för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="ba834-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="ba834-104">Du kan enkelt använda en [kvarhållningsetikett](../compliance/retention.md) på en modell för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="ba834-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="ba834-105">Du kan göra detta för både dokumentförståelse och formulärhanteringsmodeller. </span><span class="sxs-lookup"><span data-stu-id="ba834-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="ba834-106">Med hjälp av kvarhållningsetiketter kan du använda kvarhållningsinställningar för dokument som modellen för dokumenttolkning förstår.</span><span class="sxs-lookup"><span data-stu-id="ba834-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="ba834-107">Du vill till exempel kanske att din modell inte bara ska identifiera *Försäkringar* som laddats upp till dokumentbiblioteket, utan även använda kvarhållningsetiketten *Företag* på dem så att dokumenten inte kan tas bort från dokumentbiblioteket under den angivna tidsperioden (till exempel de kommande fem månaderna).</span><span class="sxs-lookup"><span data-stu-id="ba834-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="ba834-108">Du kan använda en befintlig kvarhållningsetikett på modellen för dokumenttolkning i modellinställningarna på modellens startsida.</span><span class="sxs-lookup"><span data-stu-id="ba834-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="ba834-109">För att kvarhållningsetiketterna ska vara tillgängliga att använda på din modell för innehållstolkning måste de [skapas och publiceras i Microsoft 365 Efterlevnadscenter](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="ba834-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="ba834-110">Att använda kvarhållningsetiketter på modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="ba834-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="ba834-111">På modellens startsida väljer du **Modellinställningar**.</span><span class="sxs-lookup"><span data-stu-id="ba834-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="ba834-112">I **Modelinställningar**, i avsnittet **Säkerhet och efterlevnad**, väljer du menyn **Kvarhållningsetikett** för en lista över de kvarhållningsetiketter som finns tillgängliga att använda på modellen.</span><span class="sxs-lookup"><span data-stu-id="ba834-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="ba834-113">![Kvarhållningsetikettmenyn](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="ba834-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="ba834-114">Välj den kvarhållningsetikett som du vill använda för modellen och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba834-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="ba834-115">När du har använt kvarhållningsetiketten på din modell kan du använda den på:</span><span class="sxs-lookup"><span data-stu-id="ba834-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="ba834-116">Ett nytt dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="ba834-116">New document library</span></span>
- <span data-ttu-id="ba834-117">Ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="ba834-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="ba834-118">Använd kvarhållningsetiketten på ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="ba834-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="ba834-119">Om modellen för dokumenttolkning redan har använts på ett dokumentbibliotek kan du göra följande för att synkronisera din uppdatering av kvarhållningsetiketten så att den används på dokumentbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="ba834-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="ba834-120">På modellens startsida, i avsnittet **Bibliotek med den här modellen** väljer du det dokumentbibliotek på vilket du vill använda uppdateringen av kvarhållningsetiketten.</span><span class="sxs-lookup"><span data-stu-id="ba834-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="ba834-121">Välj **Synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="ba834-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="ba834-122">![Synkronisera modell](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="ba834-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="ba834-123">Efter tillämpning av uppdateringen och synkronisering med modellen kan du kontrollera att den har använts genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="ba834-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="ba834-124">I innehållscentret går du till avsnittet **Bibliotek med den här modellen**. Klicka på det bibliotek där din uppdaterade modell används.</span><span class="sxs-lookup"><span data-stu-id="ba834-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="ba834-125">I vyn dokumentbibliotek väljer du informationsikonen för att kontrollera modellens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ba834-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="ba834-126">I listan över **Aktiva modeller** väljer du den uppdaterade modellen.</span><span class="sxs-lookup"><span data-stu-id="ba834-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="ba834-127">I avsnittet **Kvarhållningsetikett** ser du namnet på den kvarhållningsetikett som används.</span><span class="sxs-lookup"><span data-stu-id="ba834-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="ba834-128">På modellens visningssida i dokumentbiblioteket visas en ny kolumn för **Kvarhållningsetikett**.</span><span class="sxs-lookup"><span data-stu-id="ba834-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="ba834-129">Allt eftersom modellen klassificerar filer som tillhör dess innehållstyp och listar dem i biblioteksvyn visas också namnet på den kvarhållningsetikett som har använts på den genom modellen.</span><span class="sxs-lookup"><span data-stu-id="ba834-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="ba834-130">Till exempel kommer alla *Försäkringar* som modellen identifierar att ha kvarhållningsetiketten *Företag* så att de inte kan tas bort från dokumentbiblioteket på fem månader.</span><span class="sxs-lookup"><span data-stu-id="ba834-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="ba834-131">Om du försöker ta bort filen från dokumentbiblioteket visas ett felmeddelande om att det inte är tillåtet eftersom kvarhållningsetiketten används.</span><span class="sxs-lookup"><span data-stu-id="ba834-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="ba834-132">Att använda kvarhållningsetikett på modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="ba834-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="ba834-133">För att kvarhållningsetiketter ska vara tillgängliga för din formulärbehandlingsmodell måste de vara [skapas och publiceras i Microsoft 365 Efterlevnadscenter](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="ba834-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="ba834-134">Du kan antingen använda en kvarhållningsetikett på en formulärbehandlingsmodell när du skapar en modell eller tillämpa den på en befintlig modell.</span><span class="sxs-lookup"><span data-stu-id="ba834-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="ba834-135">Så här lägger du till en kvarhållningsetikett när du skapar en formbehandlingsmodell</span><span class="sxs-lookup"><span data-stu-id="ba834-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="ba834-136">När du [skapar en ny formulärbearbetningsmodell](./create-a-form-processing-model.md) väljer du <b>Avancerade inställningar.</b></span><span class="sxs-lookup"><span data-stu-id="ba834-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="ba834-137">I <b>Avancerade inställningar</b> väljer du menyn i avsnittet <b>Bevarandeetikett</b> och väljer sedan den bevarandeetikett som du vill använda på modellen.</b></span><span class="sxs-lookup"><span data-stu-id="ba834-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Lägga till i en ny formulärbearbetningsmodell](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="ba834-139">När du har slutfört dina återstående modellinställningar väljer du <b>Skapa</b> för att bygga modellen.</span><span class="sxs-lookup"><span data-stu-id="ba834-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="ba834-140">Lägga till en bevarandeetikett i en befintlig formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="ba834-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="ba834-141">Du kan lägga till en kvarhållningsetikett i en befintlig formulärbearbetningsmodell på olika sätt:</span><span class="sxs-lookup"><span data-stu-id="ba834-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="ba834-142">Genom Automatisera-menyn i dokumentbiblioteket</span><span class="sxs-lookup"><span data-stu-id="ba834-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="ba834-143">Genom de aktiva modellinställningarna i dokumentbiblioteket</span><span class="sxs-lookup"><span data-stu-id="ba834-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="ba834-144">Lägga till en bevarandeetikett till en befintlig formulärbearbetningsmodell via Automatisera-menyn</span><span class="sxs-lookup"><span data-stu-id="ba834-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="ba834-145">Du kan lägga till en kvarhållningsetikett till en befintlig formulärbearbetningsmodell som du äger via Automatisera-menyn i det dokumentbibliotek där modellen används.</span><span class="sxs-lookup"><span data-stu-id="ba834-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="ba834-146">I ditt dokumentbibliotek där formulärbehandlingsmodellen används, välj <b>Automatisera</b>-menyn, välj <b>AI Builder</b> och välj sedan <b>Visa information om formulärbehandlingsmodell</b>.</span><span class="sxs-lookup"><span data-stu-id="ba834-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Automatisera-menyn](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="ba834-148">I modellinformationen väljer du den <b>kvarhållningsetikett</b> som du vill tillämpa i avsnittet Lagringsetikett.</span><span class="sxs-lookup"><span data-stu-id="ba834-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="ba834-149">Välj sedan <b>Spara</b>.</span><span class="sxs-lookup"><span data-stu-id="ba834-149">Then select <b>Save</b>.</span></span>

     ![Lägga till i en befintlig formulärbearbetningsmodell](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="ba834-151">Lägga till en bevarandeetikett till en befintlig formulärbearbetningsmodell i inställningarna för aktiv modell</span><span class="sxs-lookup"><span data-stu-id="ba834-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="ba834-152">Du kan lägga till en kvarhållningsetikett till en befintlig formulärbearbetningsmodell som du äger via inställningarna för aktiv modell i det dokumentbibliotek där modellen används.</span><span class="sxs-lookup"><span data-stu-id="ba834-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="ba834-153">I det SharePoint-dokumentbibliotek där modellen används väljer du <b>Visa aktiva modeller</b> ikonen och väljer sedan <b>Visa aktiva modeller</b>.</b></span><span class="sxs-lookup"><span data-stu-id="ba834-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Visa aktiva modeller](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="ba834-155">I <b>aktiva modeller</b> välj den formulärbearbetningsmodell där du vill använda kvarhållningsetikett.</span><span class="sxs-lookup"><span data-stu-id="ba834-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Modellinformation](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="ba834-157">I modellinformationen väljer du den <b>kvarhållningsetikett</b> som du vill tillämpa i avsnittet Lagringsetikett.</span><span class="sxs-lookup"><span data-stu-id="ba834-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="ba834-158">Välj sedan <b>Spara</b>.</span><span class="sxs-lookup"><span data-stu-id="ba834-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="ba834-159">Du måste vara modellägare för fönstret för modellinställningar för att kunna redigeras.</span><span class="sxs-lookup"><span data-stu-id="ba834-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ba834-160">Se även</span><span class="sxs-lookup"><span data-stu-id="ba834-160">See Also</span></span>
[<span data-ttu-id="ba834-161">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="ba834-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="ba834-162">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="ba834-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="ba834-163">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="ba834-163">Document Understanding overview</span></span>](document-understanding-overview.md)