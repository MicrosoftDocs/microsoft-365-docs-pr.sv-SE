---
title: Använda term lagrings taxonomi när du skapar en Extractor
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
description: Använda term lagrings platsen när du skapar en Extractor i dokumentet förstås i Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296222"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Använda term lagrings taxonomi när du skapar en Extractor


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

När du skapar en Extractor i din dokument kunskaps modell i SharePoint Syntex kan du utnyttja den här [termen för](https://docs.microsoft.com/sharepoint/managed-metadata#terms) att Visa önskade villkor för data som du extraherar.  

Som exempel identifieras och klassificeras alla **kontrakts** dokument som laddas upp till dokument biblioteket.  Dessutom extraherar modellen också ett **kontrakts tjänst** värde från varje kontrakt och visas i en kolumn i vyn bibliotek. Bland de olika kontrakts tjänstens värden finns det flera äldre värden som företaget inte längre använder och har bytt namn. Till exempel ska alla referenser till *design*-, *grafik*-och *topografi* -tjänster nu vara *kreativa*. När din modell extraherar ett av de föråldrade villkoren från ett kontrakts dokument vill du att den ska visas i din Library-vy. I exemplet nedan, och utbildning för modellen ser vi att ett exempel dokument innehåller den inaktuella *designens layout*.

   ![Term lagrings plats](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Synonymer för term uppsättning 

Term uppsättningar konfigureras i term lagrings platsen för hanterade metadata i administrations centret för SharePoint. I exemplet nedan är [termen uppsättning](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) för *kontrakt tjänster* konfigurerat till att omfatta flera villkor, inklusive *Creative*.  Informationen för det visar att termen har tre synonymer (*design*, *grafik*och *topografi*) och synonymerna bör översättas till *kreativ*.

   ![Term uppsättning](../media/content-understanding/term-store.png)</br>

<Mike, här är jag osäker på hur du beskriver detta.  Vilken åtgärd visar modellen när jag skapar en kolumn för att extrahera och visa kolumnen kontrakt tjänster, hur är att kolumnen "märkt" används för att använda term uppsättningen hanterade metadata för Creative Services? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>Konfigurera kolumnen webbplats för dokument bibliotek för ett fält med hanterade metadata


   ![Skapa hanterade metadata](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Se även
[Introduktion till hanterade metadata](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Skapa en Extractor](create-an-extractor.md)</br>
[Skapa en kolumn med hanterade metadata](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





