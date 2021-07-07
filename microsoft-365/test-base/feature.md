---
title: Validering av funktionsuppdatering
description: Information om hur du laddar upp programmet för validering av funktionsuppdatering
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
ms.openlocfilehash: ce048796acd52e6daf8d4694cf72a0bd17c75ab4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323326"
---
# <a name="windows-feature-update-validation"></a>Windows Validering av funktionsuppdatering

Behöver du insikter om hur dina program fungerar med nästa version av Windows 10 eller Windows 11 – utan att du behöver underhålla en miljö för att verifiera nya Windows funktioner? 

Vill du köra valideringstesterna mot Windows Insider Program-versionerna i vår Azure-miljö?

**Validering av** funktionsuppdateringen på testbas för M365 kan hjälpa dig att uppnå alla dessa och fler!

Ta en steg-för-steg-beskrivning nedan för att ta reda på hur du kommer åt den här nya funktionen i Testbas för M365-tjänsten.

För att komma igång med Test Base för M365 laddar du upp dina program (och relaterade filer) via ```Feature update validation``` självbetjäningsportalen. 

Nedan visas de åtgärder du kan vidta när du fyller i **testinformationen:**

1. Välj **Funktionsuppdatering** som OS-uppdateringstyp:

![Verifieringsoperativtyp för funktionsuppdatering](Media/Feature-update-validation-01.png)

2. Välj den Windows Insider-kanal som du vill att programmet ska valideras mot.  

![Validering av funktionsuppdatering. Välja Insider Beta-kanalen](Media/Feature-update-validation-02.png)

3. Välj en version på marknaden av Windows 10 eller Windows 11 som baslinje för testet (och resulterande insikter!) och ange annan information som krävs för att ditt paket ska kunna introduceras.

![Validering av funktionsuppdatering med släppta versioner Windows 10 och Windows 11](Media/Feature-update-validation-03.png)

4. Om du vill visa resultatet från valideringen av programmet mot förhandsutgivna Windows 10 kan du gå till ```Feature Updates Test Results``` .

![Med validering av funktionsuppdateringen kan du snabbt granska resultaten](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>Nästa steg

Gå vidare till nästa artikel för att komma igång med förståelsen av regressionsanalys av minne.
> [!div class="nextstepaction"]
> [Nästa steg](memory.md)

<!---
Add button for next page
-->
