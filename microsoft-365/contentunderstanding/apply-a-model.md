---
title: Använda en modell för dokumenttolkning på ett dokumentbibliotek
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Lär dig att använda en publicerad modell på ett SharePoint-dokumentbibliotek
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322159"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0f1c8-103">Använda en modell för dokumenttolkning i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0f1c8-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="0f1c8-104">När du har publicerat modellen för dokumenttolkning kan du använda den på ett eller flera SharePoint-dokumentbibliotek i din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="0f1c8-105">Du kan bara använda modellen på dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="0f1c8-106">Använd din modell på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-106">Apply your model to a document library.</span></span>

<span data-ttu-id="0f1c8-107">För att använda din modell på ett SharePoint-dokumentbibliotek:</span><span class="sxs-lookup"><span data-stu-id="0f1c8-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="0f1c8-108">På modellens startsida, under fliken **Använda modell på bibliotek**, väljer du **Publicera modell**.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="0f1c8-109">Eller så kan du välja  **+Lägg till bibliotek** i avsnittet **Bibliotek med den här modellen**.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Lägga till modell i bibliotek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="0f1c8-111">Sedan kan du välja den SharePoint-webbplats som innehåller det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="0f1c8-112">Om webbplatsen inte visas i listan kan du använda sökrutan för att hitta den.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="0f1c8-114">Du måste ha behörighet för *Hantera list* eller *Redigera* för det dokumentbibliotek som du använder modellen på.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="0f1c8-115">När du har valt webbplatsen väljer du det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="0f1c8-116">I exemplet väljer du dokumentbiblioteket *Dokument* från webbplatsen *Contoso Case Tracking*.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Välj ett dokumentbibliotek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="0f1c8-118">Eftersom modellen har kopplats till en innehållstyp, kommer den att lägga till innehållstypen och dess vy, med de etiketter du extraherat i form av kolumner, när den används i biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="0f1c8-119">Den här vyn är bibliotekets standardvy, men du kan även välja att inte använda den som standardvy under **Avancerade inställningar**, avmarkera **Ange den nya vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Biblioteksvy](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="0f1c8-121">Välj **Lägg till** för att tillämpa modellen på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="0f1c8-122">På modellens startsida i avsnittet **Bibliotek med den här modellen** ser du webbadressen till den SharePoint-webbplats som visas.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Valt bibliotek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="0f1c8-124">Gå till dokumentbiblioteket och se till att du är i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="0f1c8-125">Observera att om du väljer informationsknappen bredvid dokumentbibliotekets namn noterar ett meddelande att modellen har använts i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Informationsvy](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="0f1c8-127">När du har använt modellen på dokumentbiblioteket kan du börja ladda upp dokument till webbplatsen och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="0f1c8-128">Modellen identifierar alla filer med modellens kopplade innehållstyp och visar dem i vyn.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="0f1c8-129">Om din modell har några extraktorer visas kolumner för de data som du extraherar från varje fil.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="0f1c8-130">Använd modellen på filer som redan finns i dokumentbiblioteket</span><span class="sxs-lookup"><span data-stu-id="0f1c8-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="0f1c8-131">Även om en använd modell behandlar alla filer som laddats upp till dokumentbiblioteket efter att den har använts så kan du göra följande för att köra modellen på filer som redan fanns i dokumentbiblioteket innan modellen användes:</span><span class="sxs-lookup"><span data-stu-id="0f1c8-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="0f1c8-132">Markera de filer som du vill ska behandlas av din modell i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="0f1c8-133">När du har valt dina filer visas **Klassificera och extrahera** i dokumentbibliotekets menyfliksområde.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="0f1c8-134">Välj **Klassificera och extrahera**.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="0f1c8-135">De filer du valde kommer att läggas till i kön som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="0f1c8-135">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="0f1c8-137">Se även</span><span class="sxs-lookup"><span data-stu-id="0f1c8-137">See Also</span></span>
[<span data-ttu-id="0f1c8-138">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="0f1c8-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="0f1c8-139">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="0f1c8-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="0f1c8-140">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="0f1c8-140">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="0f1c8-141">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="0f1c8-141">Create a form processing model</span></span>](create-a-form-processing-model.md)  
