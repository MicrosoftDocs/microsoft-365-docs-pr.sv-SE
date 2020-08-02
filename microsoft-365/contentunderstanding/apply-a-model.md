---
title: Använda en dokumentförståelsemodell i ett dokumentbibliotek (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du använder en publicerad modell i ett SharePoint-dokumentbibliotek.
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537911"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="064ce-103">Använda en modell för dokumentförståelse (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="064ce-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="064ce-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="064ce-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="064ce-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="064ce-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="064ce-106">När du har publicerat dokumentförståelsemodellen kan du använda den på ett SharePoint-dokumentbibliotek i microsoft 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="064ce-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="064ce-107">Du kan bara använda modellen på dokumentbibliotek som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="064ce-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="064ce-108">Använd modellen på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="064ce-108">Apply your model to a document library.</span></span>

<span data-ttu-id="064ce-109">Så här använder du modellen på ett SharePoint-dokumentbibliotek:</span><span class="sxs-lookup"><span data-stu-id="064ce-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="064ce-110">På modellens startsida väljer du **Publicera modell**på panelen Använd modell **på bibliotek** .</span><span class="sxs-lookup"><span data-stu-id="064ce-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="064ce-111">Du kan också välja **+Lägg till bibliotek** i **biblioteken med det här** modellavsnittet.</span><span class="sxs-lookup"><span data-stu-id="064ce-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Lägga till modell i biblioteket](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="064ce-113">Du kan sedan välja den SharePoint-webbplats som innehåller det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="064ce-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="064ce-114">Om webbplatsen inte visas i listan använder du sökrutan för att hitta den.</span><span class="sxs-lookup"><span data-stu-id="064ce-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="064ce-116">Du måste ha behörigheten *Hantera lista* eller *Redigera* rättigheter till det dokumentbibliotek som du använder modellen på.</span><span class="sxs-lookup"><span data-stu-id="064ce-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="064ce-117">När du har valt webbplatsen måste du välja det dokumentbibliotek som du vill använda modellen på.</span><span class="sxs-lookup"><span data-stu-id="064ce-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="064ce-118">I exemplet väljer vi *dokumentbiblioteket Dokument* från webbplatsen *Contoso Case Tracking.*</span><span class="sxs-lookup"><span data-stu-id="064ce-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Välj ett dokumentbibliotek](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="064ce-120">Eftersom modellen är kopplad till en innehållstyp skapas en vy för innehållstypen när du använder den på biblioteket med etiketterna som du extraherade som kolumner.</span><span class="sxs-lookup"><span data-stu-id="064ce-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="064ce-121">Den här vyn blir bibliotekets standardvy som standard, men du kan välja att inte ha det som standardvy genom att välja **Avancerade inställningar** och avmarkera Ange den **nya vyn som standard**.</span><span class="sxs-lookup"><span data-stu-id="064ce-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Biblioteksvy](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="064ce-123">Välj **Lägg till** om du vill använda modellen på biblioteket.</span><span class="sxs-lookup"><span data-stu-id="064ce-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="064ce-124">På modellens startsida visas URL:en till SharePoint-webbplatsen i avsnittet **Bibliotek med den här modellen.**</span><span class="sxs-lookup"><span data-stu-id="064ce-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteksvy](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="064ce-126">Gå till dokumentbiblioteket och se till att du är i modellens dokumentbiblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="064ce-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="064ce-127">Du kommer att märka att om du väljer informationsknappen bredvid dokumentbibliotekets namn kommer ett meddelande att notera att din modell har tillämpats på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="064ce-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Biblioteksvy](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="064ce-129">När du har använt modellen på dokumentbiblioteket kan du börja ladda upp dokument till webbplatsen och se resultaten.</span><span class="sxs-lookup"><span data-stu-id="064ce-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="064ce-130">Modellen identifierar alla filer med modellens associerade innehållstyp och listar dem i vyn.</span><span class="sxs-lookup"><span data-stu-id="064ce-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="064ce-131">Om din modell har några utsug visas kolumner för de data som du extraherar från varje fil.</span><span class="sxs-lookup"><span data-stu-id="064ce-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="064ce-132">Använda modellen på filer som redan finns i dokumentbiblioteket</span><span class="sxs-lookup"><span data-stu-id="064ce-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="064ce-133">Medan en tillämpad modell bearbetar alla filer som överförs till dokumentbiblioteket när den har tillämpats, kan du också göra följande för att köra modellen på filer som redan fanns i dokumentbiblioteket innan modellen tillämpas:</span><span class="sxs-lookup"><span data-stu-id="064ce-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="064ce-134">Markera de filer som du vill bearbeta av modellen i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="064ce-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="064ce-135">När du har markerat dina filer visas **klassificera och extrahera** i menyfliksområdet för dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="064ce-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="064ce-136">Välj **Klassificera och extrahera**.</span><span class="sxs-lookup"><span data-stu-id="064ce-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="064ce-137">De filer du har valt läggs till i kön som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="064ce-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="064ce-139">Se även</span><span class="sxs-lookup"><span data-stu-id="064ce-139">See Also</span></span>
[<span data-ttu-id="064ce-140">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="064ce-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="064ce-141">Skapa en utsutorn</span><span class="sxs-lookup"><span data-stu-id="064ce-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="064ce-142">Översikt över dokuments förståelse</span><span class="sxs-lookup"><span data-stu-id="064ce-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="064ce-143">Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="064ce-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




