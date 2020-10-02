---
title: Använda termlagringstaxonomi vid skapande av extraktor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Använd en termlagringstaxonomi vid skapande av extraktor i modellen för dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: f7219f6facc1d29242f7bd52743da92e13de3b89
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337283"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Använda termlagringstaxonomi vid skapande av extraktor

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>


När du skapar en extraktor i modellen för dokumenttolkning i SharePoint-Syntex kan du dra nytta av termlagringstaxonomins [Hanterade metadatatjänster](https://docs.microsoft.com/sharepoint/managed-metadata#terms) för att visa rekommenderade termer för data som du extraherar.  

Som exempel identifierar och klassificerar din modell alla **Kontrakt** som har laddats upp till dokumentbiblioteket.  Dessutom extraherar modellen också värdet **Kontraktstjänst** från varje kontrakt. Det visas i en kolumn i din biblioteksvy. Bland de olika värdena för kontraktstjänster i kontrakten finns det flera äldre värden som företaget inte längre använder och som har bytt namn. Exempel: alla hänvisningar till termernas *Design*, *Grafik* eller *Topografi* i kontraktstjänsterna ska nu kallas *Kreativa*. När din modell hämtar en inaktuell term från ett kontrakt vill du att det ska visa den aktuella termen – Kreativ – i din biblioteksvy. I exemplet nedan ser vi medan vi tränar modellen att ett exempeldokument innehåller inaktuella villkor för *Design*.

   ![Termlagring](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Använda en kolumn med hanterade metadata i din extraktor

Uppsättningar med termer konfigureras i hanterade metadatatjänstens termarkiv i administrationscenter för SharePoint. I exemplet nedan är *Kontraktstjänsters* [termuppsättning](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) konfigurerad att innehålla flera termer, bland annat *Kreativa*.  Informationen för den visar att termen har tre synonymer (*Design*, *Grafik*och *Topografi*) och att synonymerna ska översätta till *Kreativa*. 

   ![Termuppsättning](../media/content-understanding/term-store.png)</br>

Det kan finnas flera anledningar till att du vill använda en synonym i termuppsättningen. Det kan till exempel röra sig om föråldrade termer, termer som fått nya namn eller skillnader mellan företagets olika avdelningar.

Om du vill att fältet för hanterade metadata ska vara tillgängligt att välja när du skapar din extraktor i modellen måste du [lägga till det som en webbplatskolumn med hanterade metadata](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). När du har lagt till webbplatskolumnen blir den tillgänglig att välja när du skapar extraktorn för din modell.

   ![Kontraktstjänst](../media/content-understanding/contract-services.png)</br>


Efter att ha använt modellen på dokumentbiblioteket, när dokumenten är uppladda till biblioteket, kommer kolumnen *Kreativa tjänster* att visa föredragen term (*Kreativ*) när extraktorn hittar något av synonymvärdena (*Design*, *Grafik* och *Topografi*).

   ![Kontraktstjänstkolumnen](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>Se även
[Introduktion till hanterad metadata](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[Skapa en extraktor](create-an-extractor.md)

[Skapa en kolumn med hanterade metadata](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





