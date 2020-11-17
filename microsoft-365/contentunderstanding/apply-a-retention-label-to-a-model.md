---
title: Använda kvarhållningsetiketter på modeller för dokumenttolkning
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Den här artikeln tar upp hur du använder kvarhållningsetiketter på modeller för dokumenttolkning
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087481"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Använda kvarhållningsetiketter på modeller för dokumenttolkning

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Du kan enkelt använda en [kvarhållningsetikett](https://docs.microsoft.com/microsoft-365/compliance/retention) på en modell för dokumenttolkning i Microsoft SharePoint Syntex.

Med hjälp av kvarhållningsetiketter kan du använda kvarhållningsinställningar för dokument som modellen för dokumenttolkning förstår.  Du vill till exempel kanske att din modell inte bara ska identifiera *Försäkringar* som laddats upp till dokumentbiblioteket, utan även använda kvarhållningsetiketten *Företag* på dem så att dokumenten inte kan tas bort från dokumentbiblioteket under den angivna tidsperioden (till exempel de kommande fem månaderna).

Du kan använda en befintlig kvarhållningsetikett på modellen för dokumenttolkning i modellinställningarna på modellens startsida. 

> [!Important]
> För att kvarhållningsetiketterna ska vara tillgängliga att använda på din modell för innehållstolkning måste de [skapas och publiceras i Microsoft 365 Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Att använda kvarhållningsetiketter på modeller för dokumenttolkning

1. På modellens startsida väljer du **Modellinställningar**.</br>
2. I **Modelinställningar**, i avsnittet **Säkerhet och efterlevnad**, väljer du menyn **Kvarhållningsetikett** för en lista över de kvarhållningsetiketter som finns tillgängliga att använda på modellen.</br>
 ![Kvarhållningsetikettmenyn](../media/content-understanding/retention-labels-menu.png)</br> 
3. Välj den kvarhållningsetikett som du vill använda för modellen och sedan **Spara**.</br>

När du har använt kvarhållningsetiketten på din modell kan du använda den på:
- Ett nytt dokumentbibliotek
- Ett dokumentbibliotek som modellen redan används för
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Använd kvarhållningsetiketten på ett dokumentbibliotek som modellen redan används för

Om modellen för dokumenttolkning redan har använts på ett dokumentbibliotek kan du göra följande för att synkronisera din uppdatering av kvarhållningsetiketten så att den används på dokumentbiblioteket:</br>

1. På modellens startsida, i avsnittet **Bibliotek med den här modellen** väljer du det dokumentbibliotek på vilket du vill använda uppdateringen av kvarhållningsetiketten. </br> 
2. Välj **Synkronisera**. </br>
 ![Synkronisera modell](../media/content-understanding/sync-model.png)</br> 


Efter tillämpning av uppdateringen och synkronisering med modellen kan du kontrollera att den har använts genom att göra följande:

1. I innehållscentret går du till avsnittet **Bibliotek med den här modellen**. Klicka på det bibliotek där din uppdaterade modell används. </br>
2. I vyn dokumentbibliotek väljer du informationsikonen för att kontrollera modellens egenskaper.</br>  
3. I listan över **Aktiva modeller** väljer du den uppdaterade modellen.</br>
4. I avsnittet **Kvarhållningsetikett** ser du namnet på den kvarhållningsetikett som används.</br>


På modellens visningssida i dokumentbiblioteket visas en ny kolumn för **Kvarhållningsetikett**.  Allt eftersom modellen klassificerar filer som tillhör dess innehållstyp och listar dem i biblioteksvyn visas också namnet på den kvarhållningsetikett som har använts på den genom modellen.


Till exempel kommer alla *Försäkringar* som modellen identifierar att ha kvarhållningsetiketten *Företag* så att de inte kan tas bort från dokumentbiblioteket på fem månader. Om du försöker ta bort filen från dokumentbiblioteket visas ett felmeddelande om att det inte är tillåtet eftersom kvarhållningsetiketten används.

## <a name="see-also"></a>Se även
[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)


