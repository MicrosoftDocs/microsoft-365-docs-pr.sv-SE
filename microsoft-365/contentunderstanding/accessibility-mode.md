---
title: 'Tillgänglighetsläge för SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du använder hjälpmedelsläget när du utbildar en modell i SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515154"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Tillgänglighetsläge för SharePoint Syntex

I [SharePoint Syntex](index.md)kan användarna aktivera hjälpmedelsläget i alla steg av modellutbildning (etikett, utbilda, testa) när de arbetar med exempeldokument. Hjälpmedelsläget kan göra det lättare för användare med låg syn att använda tangentbordet när de navigerar och etiketterar objekt i dokumentvisningsprogrammet.

Det här hjälper användarna att använda tangentbordet för att navigera genom texten i dokumentvisningsprogrammet och höra en berättarröst som inte bara innehåller valda värden, utan även åtgärder (t.ex. märkning eller ta bort etiketter från markerad text) eller förutsagda etikettvärden när du utbildar modellen med ytterligare exempeldokument. 


![Hjälpmedelsläge](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Krav

För att höra ljudet av berättarrösten, se till att aktivera [Skärmläsaren-appen](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) i Skärmläsaren inställningarna på Windows 10 system.

![Aktivera Skärmläsaren](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Märkning för tangentbordsanvändare

För tangentbordsanvändare som använder hjälpmedelsläge kan du använda följande tangenter om du etiketterar text i ett exempeldokument i visningsprogrammet:

- Tabb: Flyttar dig framåt och markerar nästa ord.
- Tabb + Skift: Flyttar dig bakåt och markerar föregående ord.
- Retur: Etiketten eller tar bort en etikett från det markerade ordet.
- Högerpil: Flyttar dig framåt mellan enskilda tecken i ett markerat ord.
- Vänsterpil: Flyttar dig bakåt mellan enskilda tecken i ett markerat ord.

> [!NOTE]
> Om du använder flera ord för en enstaka etikett måste du märka varje ord.


## <a name="narration"></a>Berättarröst

Om Skärmläsaren använder hjälpmedelsläget använder du samma tangentbordsnavigering som beskrivs för tangentbordsanvändare för att gå igenom exempeldokumentet i visningsprogrammet.

När du navigerar genom exempeldokumenten och etikettsträngvärdena ger Skärmläsaren följande ljuduppnstruktionerna:

- När du använder tangentbordet för att navigera i dokumentvisaren visas Skärmläsaren den valda strängen.
- I en markerad sträng Skärmläsaren varje tecken i strängen när du markerar dem med hjälp av vänster- eller högerpil.
- Om du markerar en sträng som har etiketterats Skärmläsaren värdet och sedan "märkt".  Om etikettvärdet till exempel är "Contoso" står det "Costoso märkt". 
- Om du väljer en sträng i dokumentvisningsprogrammet som bara har förutsagts på fliken utbildning, Skärmläsaren ljud för att ange värdet och sedan "prognosteras". Detta inträffar när utbildning förutsäger ett värde i filen som inte matchar det som har märkts av användaren.
- Om du väljer en sträng i dokumentvisningsprogrammet som har etiketterats och prognostserats på fliken utbildning, visar Skärmläsaren-ljud värdet och "märkas och prognosteras". Detta inträffar när utbildningen är lyckad och det finns en matchning mellan ett förutsagt värde och användaretiketten.



När en sträng har etiketterats eller en etikett har tagits bort i Skärmläsaren varnas du om att spara ändringarna innan du avslutar.

## <a name="see-also"></a>Se även

[Skapa en extraherare](create-an-extractor.md)</br>

[Skapa en klassificerare](create-a-classifier.md)</br>










 


  
  



