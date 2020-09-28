---
title: Använda en dokument förståelse för ett dokument bibliotek
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du använder en publicerad modell i ett SharePoint-dokumentbibliotek
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295496"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f3315-103">Använda ett dokument för att förstå en modell i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f3315-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f3315-104">Innehållet i den här artikeln gäller för projektets cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="f3315-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="f3315-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f3315-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="f3315-106">När du har publicerat din dokument förståelse kan du tillämpa den på ett SharePoint-dokumentbibliotek i Microsoft 365-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="f3315-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="f3315-107">Du kan bara använda modellen för dokument bibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="f3315-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="f3315-108">Tillämpa modellen på ett dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f3315-108">Apply your model to a document library.</span></span>

<span data-ttu-id="f3315-109">Så här använder du modellen till i ett SharePoint-dokumentbibliotek:</span><span class="sxs-lookup"><span data-stu-id="f3315-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="f3315-110">Välj **publicera modell**på panelen **Använd modell på bibliotek** på modell start sidan.</span><span class="sxs-lookup"><span data-stu-id="f3315-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="f3315-111">Eller så kan du välja  **+ Lägg till bibliotek** i **biblioteken med den här modellen** .</span><span class="sxs-lookup"><span data-stu-id="f3315-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Lägga till modell i bibliotek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="f3315-113">Välj den SharePoint-webbplats som innehåller det dokument bibliotek som du vill använda modellen för.</span><span class="sxs-lookup"><span data-stu-id="f3315-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="f3315-114">Om webbplatsen inte visas i listan kan du använda rutan Sök för att hitta den.</span><span class="sxs-lookup"><span data-stu-id="f3315-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="f3315-116">Du måste ha behörigheten *Hantera lista* eller *Redigera* rättigheter till det dokument bibliotek som du tillämpar modellen på.</span><span class="sxs-lookup"><span data-stu-id="f3315-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="f3315-117">När du har valt webbplatsen väljer du det dokument bibliotek som du vill tillämpa modellen på.</span><span class="sxs-lookup"><span data-stu-id="f3315-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="f3315-118">I exemplet väljer du dokument biblioteket *dokument* på sidan *contoso ärende uppföljning* .</span><span class="sxs-lookup"><span data-stu-id="f3315-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Välj ett dokument bibliotek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="f3315-120">Eftersom modellen är kopplad till en innehålls typ skapas en vy för innehålls typen när du använder den i biblioteket och etiketterna du extraherade visas som kolumner.</span><span class="sxs-lookup"><span data-stu-id="f3315-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="f3315-121">Den här vyn är bibliotekets standardvy, men du kan välja att inte använda den som standardvy genom att välja **Avancerade inställningar** och avmarkera **Ange den här nya vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="f3315-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Vyn bibliotek](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="f3315-123">Välj **Lägg till** för att tillämpa modellen på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="f3315-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="f3315-124">På Start sidan för modeller i avsnittet **bibliotek med den här modellen** bör du se URL-adressen till den SharePoint-webbplats som visas.</span><span class="sxs-lookup"><span data-stu-id="f3315-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Valt bibliotek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="f3315-126">Gå till dokument biblioteket och kontrol lera att du är i modellens dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f3315-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="f3315-127">Observera att om du väljer informations knappen bredvid dokument bibliotekets namn, visas ett meddelande om att modellen har lagts till i dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="f3315-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Vyn information](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="f3315-129">När du har använt modellen i dokument biblioteket kan du börja överföra dokument till webbplatsen och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="f3315-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="f3315-130">Modellen identifierar alla filer med modellens associerade innehålls typ och visar dem i vyn.</span><span class="sxs-lookup"><span data-stu-id="f3315-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="f3315-131">Om modellen har några utdrag visar vyn kolumner för de data du extraherar från varje fil.</span><span class="sxs-lookup"><span data-stu-id="f3315-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="f3315-132">Tillämpa modellen på filer som redan finns i dokument biblioteket</span><span class="sxs-lookup"><span data-stu-id="f3315-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="f3315-133">När en tillämpad modell bearbetar alla filer som laddas upp till dokument biblioteket efter att den har tillämpats, kan du även göra följande för att köra modellen på filer som redan finns i dokument biblioteket innan modellen tillämpas:</span><span class="sxs-lookup"><span data-stu-id="f3315-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="f3315-134">Markera de filer som du vill bearbeta i din modell i dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="f3315-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="f3315-135">När du har valt filer visas **klassificering och utdrag** i menyfliksområdet dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f3315-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="f3315-136">Välj **klassificera och extrahera**.</span><span class="sxs-lookup"><span data-stu-id="f3315-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="f3315-137">De filer du valde kommer att läggas till i kön som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="f3315-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="f3315-139">Se även</span><span class="sxs-lookup"><span data-stu-id="f3315-139">See Also</span></span>
[<span data-ttu-id="f3315-140">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="f3315-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="f3315-141">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="f3315-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="f3315-142">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="f3315-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="f3315-143">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="f3315-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
