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
# <a name="apply-a-document-understanding-model-preview"></a>Använda en modell för dokumentförståelse (förhandsgranskning)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

När du har publicerat dokumentförståelsemodellen kan du använda den på ett SharePoint-dokumentbibliotek i microsoft 365-klienten.

> [!Note]
> Du kan bara använda modellen på dokumentbibliotek som du har åtkomst till.


## <a name="apply-your-model-to-a-document-library"></a>Använd modellen på ett dokumentbibliotek.

Så här använder du modellen på ett SharePoint-dokumentbibliotek:

1. På modellens startsida väljer du **Publicera modell**på panelen Använd modell **på bibliotek** . Du kan också välja **+Lägg till bibliotek** i **biblioteken med det här** modellavsnittet. </br>

    ![Lägga till modell i biblioteket](../media/content-understanding/apply-to-library.png)</br>

2. Du kan sedan välja den SharePoint-webbplats som innehåller det dokumentbibliotek som du vill använda modellen på. Om webbplatsen inte visas i listan använder du sökrutan för att hitta den.</br>

    ![Välj en webbplats](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > Du måste ha behörigheten *Hantera lista* eller *Redigera* rättigheter till det dokumentbibliotek som du använder modellen på.</br>

3. När du har valt webbplatsen måste du välja det dokumentbibliotek som du vill använda modellen på. I exemplet väljer vi *dokumentbiblioteket Dokument* från webbplatsen *Contoso Case Tracking.*</br>

    ![Välj ett dokumentbibliotek](../media/content-understanding/select-doc-library.png)</br>

4. Eftersom modellen är kopplad till en innehållstyp skapas en vy för innehållstypen när du använder den på biblioteket med etiketterna som du extraherade som kolumner. Den här vyn blir bibliotekets standardvy som standard, men du kan välja att inte ha det som standardvy genom att välja **Avancerade inställningar** och avmarkera Ange den **nya vyn som standard**.</br>

    ![Biblioteksvy](../media/content-understanding/library-view.png)</br>

5. Välj **Lägg till** om du vill använda modellen på biblioteket. 
6. På modellens startsida visas URL:en till SharePoint-webbplatsen i avsnittet **Bibliotek med den här modellen.**</br>

    ![Biblioteksvy](../media/content-understanding/selected-library.png)</br>

7. Gå till dokumentbiblioteket och se till att du är i modellens dokumentbiblioteksvy. Du kommer att märka att om du väljer informationsknappen bredvid dokumentbibliotekets namn kommer ett meddelande att notera att din modell har tillämpats på dokumentbiblioteket.

    ![Biblioteksvy](../media/content-understanding/info-du.png)</br> 


När du har använt modellen på dokumentbiblioteket kan du börja ladda upp dokument till webbplatsen och se resultaten.

Modellen identifierar alla filer med modellens associerade innehållstyp och listar dem i vyn. Om din modell har några utsug visas kolumner för de data som du extraherar från varje fil.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Använda modellen på filer som redan finns i dokumentbiblioteket

Medan en tillämpad modell bearbetar alla filer som överförs till dokumentbiblioteket när den har tillämpats, kan du också göra följande för att köra modellen på filer som redan fanns i dokumentbiblioteket innan modellen tillämpas:

1. Markera de filer som du vill bearbeta av modellen i dokumentbiblioteket.
2. När du har markerat dina filer visas **klassificera och extrahera** i menyfliksområdet för dokumentbiblioteket. Välj **Klassificera och extrahera**.
3. De filer du har valt läggs till i kön som ska bearbetas.

      ![Klassificera och extrahera](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en utsutorn](create-an-extractor.md)</br>
[Översikt över dokuments förståelse](document-understanding-overview.md)</br>
[Skapa en formulärbearbetningsmodell](create-a-form-processing-model.md)  




