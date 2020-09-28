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
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Använda ett dokument för att förstå en modell i Microsoft SharePoint Syntex

Innehållet i den här artikeln gäller för projektets cortex privat för hands version. [Lär dig mer om Project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

När du har publicerat din dokument förståelse kan du tillämpa den på ett SharePoint-dokumentbibliotek i Microsoft 365-klient organisationen.

> [!NOTE]
> Du kan bara använda modellen för dokument bibliotek som du har åtkomst till.


## <a name="apply-your-model-to-a-document-library"></a>Tillämpa modellen på ett dokument bibliotek.

Så här använder du modellen till i ett SharePoint-dokumentbibliotek:

1. Välj **publicera modell**på panelen **Använd modell på bibliotek** på modell start sidan. Eller så kan du välja  **+ Lägg till bibliotek** i **biblioteken med den här modellen** . </br>

    ![Lägga till modell i bibliotek](../media/content-understanding/apply-to-library.png)</br>

2. Välj den SharePoint-webbplats som innehåller det dokument bibliotek som du vill använda modellen för. Om webbplatsen inte visas i listan kan du använda rutan Sök för att hitta den.</br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Du måste ha behörigheten *Hantera lista* eller *Redigera* rättigheter till det dokument bibliotek som du tillämpar modellen på.</br>

3. När du har valt webbplatsen väljer du det dokument bibliotek som du vill tillämpa modellen på. I exemplet väljer du dokument biblioteket *dokument* på sidan *contoso ärende uppföljning* .</br>

    ![Välj ett dokument bibliotek](../media/content-understanding/select-doc-library.png)</br>

4. Eftersom modellen är kopplad till en innehålls typ skapas en vy för innehålls typen när du använder den i biblioteket och etiketterna du extraherade visas som kolumner. Den här vyn är bibliotekets standardvy, men du kan välja att inte använda den som standardvy genom att välja **Avancerade inställningar** och avmarkera **Ange den här nya vyn som standard**.</br>

    ![Vyn bibliotek](../media/content-understanding/library-view.png)</br>

5. Välj **Lägg till** för att tillämpa modellen på biblioteket. 
6. På Start sidan för modeller i avsnittet **bibliotek med den här modellen** bör du se URL-adressen till den SharePoint-webbplats som visas.</br>

    ![Valt bibliotek](../media/content-understanding/selected-library.png)</br>

7. Gå till dokument biblioteket och kontrol lera att du är i modellens dokument bibliotek. Observera att om du väljer informations knappen bredvid dokument bibliotekets namn, visas ett meddelande om att modellen har lagts till i dokument biblioteket.

    ![Vyn information](../media/content-understanding/info-du.png)</br> 


När du har använt modellen i dokument biblioteket kan du börja överföra dokument till webbplatsen och se resultatet.

Modellen identifierar alla filer med modellens associerade innehålls typ och visar dem i vyn. Om modellen har några utdrag visar vyn kolumner för de data du extraherar från varje fil.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Tillämpa modellen på filer som redan finns i dokument biblioteket

När en tillämpad modell bearbetar alla filer som laddas upp till dokument biblioteket efter att den har tillämpats, kan du även göra följande för att köra modellen på filer som redan finns i dokument biblioteket innan modellen tillämpas:

1. Markera de filer som du vill bearbeta i din modell i dokument biblioteket.
2. När du har valt filer visas **klassificering och utdrag** i menyfliksområdet dokument bibliotek. Välj **klassificera och extrahera**.
3. De filer du valde kommer att läggas till i kön som ska bearbetas.

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Översikt över dokument förståelse](document-understanding-overview.md)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)  
