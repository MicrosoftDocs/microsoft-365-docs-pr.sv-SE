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

I [SharePoint Syntex](index.md)kan användare aktivera hjälpmedelsläge i alla steg av modellutbildning (etikett, utbildare, test) när de arbetar med exempeldokument. Med hjälpmedelsläget kan användare med låg syn få enklare tangentbordstillgänglighet när de navigerar och etikettobjekt i dokumentvisningsprogrammet.

Det hjälper användarna att använda tangentbordet för att navigera genom texten i dokumentvisningsprogrammet och höra en berättarröst om inte bara de valda värdena, utan även åtgärder (t.ex. etiketter eller ta bort etiketter från markerad text) eller förväntade etikettvärden när du utbildar modellen med ytterligare exempeldokument. 


![Hjälpmedelsläge](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Krav

Om du vill höra ljudet från berättarrösten [](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) måste du aktivera Skärmläsaren i inställningarna för Skärmläsaren i Windows 10.

![Aktivera Skärmläsaren](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Märkning för tangentbordsanvändare

För tangentbordsanvändare som använder hjälpmedelsläge kan du använda följande tangenter om du etiketterar text i ett exempeldokument i visningsprogrammet:

- Tabb: Flyttar dig framåt och markerar nästa ord.
- Tabb + Skift: Flyttar dig bakåt och markerar föregående ord.
- Retur: Etiketten eller tar bort en etikett från det markerade ordet.
- Högerpil: Du går framåt mellan enskilda tecken i ett markerat ord.
- Vänsterpil: Flyttar dig bakåt mellan enskilda tecken i ett markerat ord.

> [!NOTE]
> Om du märk flera ord för en enstaka etikett måste du märka varje ord.


## <a name="narration"></a>Berättarröst

För användare av Skärmläsaren som använder hjälpmedelsläge använder du samma tangentbordsnavigering som beskrivs för tangentbordsanvändare för att gå igenom exempeldokumentet i visningsprogrammet.

När du navigerar i exempeldokumenten och etikettsträngvärdena ger Skärmläsaren användaren följande ljuduppmaning:

- När du använder tangentbordet för att navigera i dokumentvisningsprogrammet styr Skärmläsaren upp den markerade strängen.
- Inom en markerad sträng anger Skärmläsaren ljud för varje tecken i strängen när du markerar dem med hjälp av vänster- eller högerpilen.
- Om du väljer en sträng som har etiketterats, uppger Skärmläsaren värdet och säger sedan "märkt".  Om etikettvärdet till exempel är "Contoso" står det "Costoso märkt". 
- Om du väljer en sträng i dokumentvisningsprogrammet som bara har förutsagts på fliken Utbildning, kommer Skärmläsaren att ange värdet och sedan "förutsäga". Detta inträffar när utbildningen förutsäger ett värde i filen som inte matchar det som har märkts av användaren.
- Om du väljer en sträng i dokumentvisningsprogrammet som har etiketterats och prognosterats på fliken Utbildning, kommer Skärmläsaren att ange värdet och sedan "märkas och förutsägas". Detta inträffar när utbildningen lyckas och det finns en matchning mellan ett förutsagt värde och användaretiketten.



När en sträng har etiketterats eller en etikett har tagits bort i visningsprogrammet får du en varning från Skärmläsaren om att ändringarna ska sparas innan du avslutar.

## <a name="see-also"></a>Se även

[Skapa en extraherare](create-an-extractor.md)</br>

[Skapa en klassificerare](create-a-classifier.md)</br>










 


  
  



