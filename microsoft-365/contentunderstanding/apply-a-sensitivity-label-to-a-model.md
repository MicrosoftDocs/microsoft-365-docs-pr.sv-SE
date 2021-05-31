---
title: Använda en kvarhållningsetikett på en modell för dokumenttolkning i Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Diskutera hur man tillämpar en kvarhållningsetikett på en modell i SharePoint Syntex.
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706726"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="408f5-103">Använda en kvarhållningsetikett på en modell för dokumenttolkning i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="408f5-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="408f5-104">Du kan enkelt använda en [känslighetsetikett](../compliance/sensitivity-labels.md) på modeller för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="408f5-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="408f5-105">Den här funktionen är inte tillgänglig ännu för modeller för formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="408f5-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="408f5-106">Med känslighetsetiketter kan du tillämpa krypterings-, delnings- och villkorsstyrda principer på de dokument som modeller identifierar.</span><span class="sxs-lookup"><span data-stu-id="408f5-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="408f5-107">Du vill till exempel att modellen inte bara ska identifiera finansiella dokument som innehåller bankkontonummer eller kreditkortsnummer som laddas upp till ditt dokumentbibliotek, utan även använda en *-krypteringsetikett* för att begränsa vem som kan komma åt innehållet och hur det kan användas.</span><span class="sxs-lookup"><span data-stu-id="408f5-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="408f5-108">Du kan använda en befintlig känslighetsetikett på modellen för dokumenttolkning i modellinställningarna på modellens startsida.</span><span class="sxs-lookup"><span data-stu-id="408f5-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="408f5-109">Etiketten måste redan vara publicerad för att vara tillgänglig för val från modellinställningar.</span><span class="sxs-lookup"><span data-stu-id="408f5-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="408f5-110">För att känslighetsetiketterna ska vara tillgängliga att använda på din modell för innehållstolkning måste de [skapas och publiceras i Microsoft 365 Efterlevnadscenter](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="408f5-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="408f5-111">Lägg till en känslighetsetikett på modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="408f5-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="408f5-112">På modellens startsida väljer du **Modellinställningar**.</span><span class="sxs-lookup"><span data-stu-id="408f5-112">From the model home page, select **Model settings**.</span></span>

   ![Skärmbild av sidan Modeller med alternativet Modellinställningar markerat.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="408f5-114">I fönstret **Modellinställningar**, i avsnittet **Efterlevnad**, väljer du menyn **Känslighetsetikett** för en lista över de känslighetsetiketter som finns tillgängliga att använda på modellen.</span><span class="sxs-lookup"><span data-stu-id="408f5-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Skärmbild av fönstret Modellinställningar med menyn för känslighetsetiketter.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="408f5-116">Välj den känslighetsetikett som du vill använda för modellen och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="408f5-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="408f5-117">När du har tillämpat känslighetsetiketten på modellen kan du använda den på en:</span><span class="sxs-lookup"><span data-stu-id="408f5-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="408f5-118">Ett nytt dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="408f5-118">New document library</span></span>
- <span data-ttu-id="408f5-119">Ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="408f5-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="408f5-120">Använd känslighetsetiketten på ett dokumentbibliotek som modellen redan används för</span><span class="sxs-lookup"><span data-stu-id="408f5-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="408f5-121">Om modellen för dokumenttolkning redan har använts på ett dokumentbibliotek kan du göra följande för att synkronisera din uppdatering av känslighetsetiketten så att den används på dokumentbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="408f5-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="408f5-122">På modellens startsida, i avsnittet **Bibliotek med den här modellen** väljer du det dokumentbibliotek på vilket du vill använda uppdateringen av känslighetsetiketten.</span><span class="sxs-lookup"><span data-stu-id="408f5-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="408f5-123">Välj **Synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="408f5-123">Select **Sync**.</span></span>

   ![Skärmbild som visar Bibliotek med den här modelldelen med Synkronisera markerat.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="408f5-125">Efter tillämpning av uppdateringen och synkronisering med modellen kan du kontrollera att den har använts genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="408f5-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="408f5-126">I innehållscentret går du till avsnittet **Bibliotek med den här modellen**. Välj det bibliotek där din uppdaterade modell används.</span><span class="sxs-lookup"><span data-stu-id="408f5-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="408f5-127">I vyn dokumentbibliotek väljer du informationsikonen för att kontrollera modellens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="408f5-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="408f5-128">I listan över **Aktiva modeller** väljer du den uppdaterade modellen.</span><span class="sxs-lookup"><span data-stu-id="408f5-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="408f5-129">I avsnittet **Känslighetsetikett** visas namnet på den använda känslighetsetiketten.</span><span class="sxs-lookup"><span data-stu-id="408f5-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="408f5-130">På modellens visningssida i dokumentbiblioteket visas en ny kolumn för **Känslighetsetikett**.</span><span class="sxs-lookup"><span data-stu-id="408f5-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="408f5-131">Allt eftersom modellen klassificerar filer som tillhör dess innehållstyp och listar dem i biblioteksvyn, visar kolumnen **Känslighetsetikett** också namnet på den känslighetsetikett som har använts på den genom modellen.</span><span class="sxs-lookup"><span data-stu-id="408f5-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="408f5-132">Till exempel kommer alla finansiella dokument som din modell identifierar även att få en etikett för *Kryptering* och hindra dem från att användas av obehöriga personer.</span><span class="sxs-lookup"><span data-stu-id="408f5-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="408f5-133">Om någon obehörig försöker komma åt filen från dokumentbiblioteket visas ett felmeddelande om att det inte är tillåtet eftersom känslighetsetiketten används.</span><span class="sxs-lookup"><span data-stu-id="408f5-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="408f5-134">Se även</span><span class="sxs-lookup"><span data-stu-id="408f5-134">See also</span></span>

[<span data-ttu-id="408f5-135">Använda en kvarhållningsetikett</span><span class="sxs-lookup"><span data-stu-id="408f5-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="408f5-136">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="408f5-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="408f5-137">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="408f5-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="408f5-138">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="408f5-138">Document Understanding overview</span></span>](document-understanding-overview.md)