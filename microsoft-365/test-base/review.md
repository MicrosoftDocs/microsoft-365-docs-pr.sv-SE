---
title: Granska
description: Granska avsnittet efter registrering.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323289"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Steg 6: Granska dina val för att skapa paketet.

1.  På den här fliken visar tjänsten din testinformation och kör en snabb kompletthetskontroll. 

    Ett ```Validation passed``` eller flera meddelanden visas om du kan fortsätta med nästa steg eller ```Validation failed``` inte.

2.  Granska testinformationen och klicka på knappen om den är ```Create``` nöjd. 

![Visa verifiering](Media/validation.png)

3.  Paketet introduceras då i Test Base-miljön. Om paketet skapas körs ett automatiskt test som verifierar om paketet kan köras på Azure.

![Lyckat resultat](Media/successful.png)

> [!Note]
> Du får ett meddelande från Azure Portal om att paketverifieringen har lyckats eller misslyckats. 
>
> Observera att processen kan ta upp till 24 timmar, så det är troligt att tidsgränsen för din webbsida löper ut om du inte är aktiv på den, och du får därför inget meddelande om att den här on-demand-körningen är slutförd. 

  - Det här inträffar om du ser status för paketet på ```Manage packages``` fliken.

![Bild för hantering av paket](Media/managepackages.png)

  - För bra tester visas resultaten via och sidorna med schemalagda intervaller, som ofta startar några dagar ```Test Summary``` ```Security Updates Results``` efter ```Feature Updates Results``` uppladdningen.
  
  - Även om testerna misslyckades måste du ladda upp ett nytt paket. 
  
    Du kan ladda ned ```test logs``` för vidare analys från ' och ```Security update results``` ```Feature updates results``` sidor.

  - Om du får upprepade testfel får du gärna kontakta testbasepreview@microsoft.com information om felet. 

## <a name="next-steps"></a>Nästa steg

Upptäck våra riktlinjer för innehåll via länken nedan.
> [!div class="nextstepaction"]
> [Nästa steg](contentguideline.md)
