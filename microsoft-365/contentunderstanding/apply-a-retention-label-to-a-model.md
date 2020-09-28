---
title: Använda en bevarande etikett på en dokument modell
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: I den här artikeln beskrivs hur du använder en bevarande etikett på en dokument förståelse
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294940"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Använda en bevarande etikett på en dokument modell

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Du kan enkelt använda en [behållnings etikett](https://docs.microsoft.com/microsoft-365/compliance/retention) för att förstå en modell i Microsoft SharePoint-Syntex.

Med behållnings etiketter kan du tillämpa inställningar för behållning för de dokument som ditt dokument förstår.  Om du till exempel vill att din modell inte bara ska identifiera några *försäkrings* dokument som laddas upp till dokument biblioteket, men om du även vill använda en affärsmall för ett *företag* , så att dessa dokument inte kan tas bort från dokument biblioteket för den angivna tids perioden (till exempel följande fem månader).

Du kan använda en befintlig behållnings etikett till dokumentet förstå modellen via modell inställningarna på modellens start sida. 

> [!Important]
> För att lagrings etiketterna ska vara tillgängliga för att tillämpas på din innehålls förståelses modell måste de [skapas och publiceras i Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Så här lägger du till en bevarande etikett i en dokument modell

1. Välj **modell inställningar**från start sidan för modellen.</br>
2. I **modell inställningar**i avsnittet **säkerhet och efterlevnad** väljer du menyn **bevarande etikett** för att se en lista över behållnings etiketter som är tillgängliga för att tillämpas på modellen.</br>
 ![Menyn bevarande etikett](../media/content-understanding/retention-labels-menu.png)</br> 
3. Välj den bevarande etikett som du vill använda för modellen och välj sedan **Spara**.</br>

När du har använt den här etiketten i din modell kan du använda den på en:
- Nytt dokument bibliotek
- Dokument bibliotek som modellen redan används för
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Använda etiketten för att lägga till ett dokument bibliotek som modellen redan används för

Om du redan har använt en modell för dokument förståelse i ett dokument bibliotek kan du göra följande för att synkronisera uppdaterings etiketten så att den används i dokument biblioteket:</br>

1. Välj det dokument bibliotek som du vill tillämpa etikett uppdateringen för i avsnittet **bibliotek med den här modellen** på modell start sidan. </br> 
2. Välj **Synkronisera**. </br>
 ![Synkroniseringsklient](../media/content-understanding/sync-model.png)</br> 


När du har tillämpat uppdateringen och synkroniserat den med modellen kan du bekräfta att den har tillämpats genom att göra följande:

1. I innehålls centret, i avsnittet **bibliotek med den här modellen** , klickar du på det bibliotek där den uppdaterade modellen användes. </br>
2. I vyn dokument bibliotek väljer du informations ikonen för att kontrol lera modell egenskaperna.</br>  
3. I listan **aktiva modeller** väljer du den uppdaterade modellen.</br>
4. I avsnittet **bevarande etikett** ser du namnet på den använda lagrings etiketten.</br>


På modellens visnings sida i dokument biblioteket visas en ny kolumn för **bevarande etikett** .  När din modell klassificerar filer som identifieras som tillhör ande innehålls typ och visar dem i vyn Bibliotek, visas även namnet på den behållnings etikett som har lagts till i modellen med hjälp av mallen för kvarhållande.


Till exempel, alla *meddelanden om försäkrings brev* som modellen identifierar kommer att ha etiketten för *affärs* innehåll som du använder för att förhindra att de tas bort från dokument biblioteket för fem månader. Om ett försök görs att ta bort filen från dokument biblioteket visas ett fel meddelande om att det inte är tillåtet på grund av den använda lagrings etiketten.

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Översikt över dokument förståelse](document-understanding-overview.md)</br>
[Skapa en modell för formulär bearbetning](create-a-form-processing-model.md)  
