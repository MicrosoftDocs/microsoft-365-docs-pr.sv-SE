---
title: Använda en modell för dokumenttolkning på ett dokumentbibliotek
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
description: Lär dig att använda en publicerad modell på ett SharePoint-dokumentbibliotek
ms.openlocfilehash: 17da1e37f72504ac5e0e26c0dd190efced08d285
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080782"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="e1b8d-103">Använda en modell för dokumenttolkning i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e1b8d-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="e1b8d-104">När du har publicerat modellen för dokumenttolkning kan du använda den på ett eller flera SharePoint-dokumentbibliotek i din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="e1b8d-105">Du kan bara använda modellen på dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="e1b8d-106">Använd din modell på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-106">Apply your model to a document library.</span></span>

<span data-ttu-id="e1b8d-107">För att använda din modell på ett SharePoint-dokumentbibliotek:</span><span class="sxs-lookup"><span data-stu-id="e1b8d-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="e1b8d-108">På modellens startsida, under fliken **Använda modell på bibliotek**, väljer du **Publicera modell**.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="e1b8d-109">Eller så kan du välja  **+Lägg till bibliotek** i avsnittet **Bibliotek med den här modellen**.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Lägga till modell i bibliotek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="e1b8d-111">Sedan kan du välja den SharePoint-webbplats som innehåller det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="e1b8d-112">Om webbplatsen inte visas i listan kan du använda sökrutan för att hitta den.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="e1b8d-114">Du måste ha behörighet för *Hantera list* eller *Redigera* för det dokumentbibliotek som du använder modellen på.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="e1b8d-115">När du har valt webbplatsen väljer du det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="e1b8d-116">I exemplet väljer du dokumentbiblioteket *Dokument* från webbplatsen *Contoso Case Tracking*.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Välj ett dokumentbibliotek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="e1b8d-118">Eftersom modellen har kopplats till en innehållstyp, kommer den att lägga till innehållstypen och dess vy, med de etiketter du extraherat i form av kolumner, när den används i biblioteket.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="e1b8d-119">Den här vyn är bibliotekets standardvy, men du kan även välja att inte använda den som standardvy under **Avancerade inställningar**, avmarkera **Ange den nya vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Biblioteksvy](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="e1b8d-121">Välj **Lägg till** för att tillämpa modellen på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="e1b8d-122">På modellens startsida i avsnittet **Bibliotek med den här modellen** ser du webbadressen till den SharePoint-webbplats som visas.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Valt bibliotek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="e1b8d-124">Gå till dokumentbiblioteket och se till att du är i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="e1b8d-125">Observera att om du väljer informationsknappen bredvid dokumentbibliotekets namn noterar ett meddelande att biblioteket har en modell som tillämpats på det.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Informationsvy](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="e1b8d-127">Du kan välja alternativet **Visa aktiva modeller** om du vill se information om eventuella modeller som tillämpas på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="e1b8d-128">I fönstret **Aktiva modeller** kan du se de modeller som tillämpas på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="e1b8d-129">Välj en modell om du vill se mer information om den, till exempel en modellbeskrivning, vem som publicerat modellen och om modellen tillämpar en kvarhållningsetikett på de filer den klassificerar.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Fönstret Aktiva modeller](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="e1b8d-131">När du har använt modellen på dokumentbiblioteket kan du börja ladda upp dokument till webbplatsen och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="e1b8d-132">Modellen identifierar alla filer med modellens kopplade innehållstyp och visar dem i vyn.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="e1b8d-133">Om din modell har några extraktorer visas kolumner för de data som du extraherar från varje fil.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="e1b8d-134">Använd modellen på filer som redan finns i dokumentbiblioteket</span><span class="sxs-lookup"><span data-stu-id="e1b8d-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="e1b8d-135">Även om en använd modell behandlar alla filer som laddats upp till dokumentbiblioteket efter att den har använts så kan du göra följande för att köra modellen på filer som redan fanns i dokumentbiblioteket innan modellen användes:</span><span class="sxs-lookup"><span data-stu-id="e1b8d-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="e1b8d-136">Markera de filer som du vill ska behandlas av din modell i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="e1b8d-137">När du har valt dina filer visas **Klassificera och extrahera** i dokumentbibliotekets menyfliksområde.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="e1b8d-138">Välj **Klassificera och extrahera**.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="e1b8d-139">De filer du valde kommer att läggas till i kön som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="e1b8d-141">Du kan kopiera enskilda filer till ett bibliotek och använda dem i en modell, men inte mappar.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="e1b8d-142">Fältet för klassificeringsdatum</span><span class="sxs-lookup"><span data-stu-id="e1b8d-142">The Classification Date field</span></span>

<span data-ttu-id="e1b8d-143">När en dokumenttolkning eller formulärbearbetningsmodell för SharePoint Syntex tillämpas på ett dokumentbibliotek ingår ett fält för <b> Klassificeringsdatum </b> i biblioteksschemat.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="e1b8d-144">Som standard är det här fältet tomt, men när dokument behandlas och klassificeras av en modell, uppdateras fältet med en stämpel för datum och tid för slutförande.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Kolumn för klassificeringsdatum](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="e1b8d-146">Fältet Klassificeringsdatum används av utlösaren [<b>När en fil klassificeras av en modell för innehållstolkning</b> ](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model)för att köra ett Power Automate-flöde när en modell för innehållstolkning för Syntex-innehåll har bearbetat en fil och uppdaterat fältet “Klassificeringsdatum”.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Flödesutlösare](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="e1b8d-148">Utlösaren <b>När en fil klassificeras av en modell för innehållstolkning</b> kan sedan användas för att starta ett annat arbetsflöde med hjälp av eventuell extraherad information från filen.</span><span class="sxs-lookup"><span data-stu-id="e1b8d-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="e1b8d-149">Se även</span><span class="sxs-lookup"><span data-stu-id="e1b8d-149">See Also</span></span>
[<span data-ttu-id="e1b8d-150">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="e1b8d-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e1b8d-151">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="e1b8d-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e1b8d-152">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="e1b8d-152">Document Understanding overview</span></span>](document-understanding-overview.md)


