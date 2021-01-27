---
title: Skicka innehållstyper till en navplats
description: Läs mer om att skicka innehållstyper till en navplats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975721"
---
# <a name="push-content-types-to-a-hub"></a>Skicka innehållstyper till en navplats

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


Om du vill göra viktiga innehållstyper mer kontinuerligt tillgängliga för SharePoint-bibliotek och -listor kan du skicka dem till de navplatser du väljer. Om du trycker på innehållstyperna läggs de automatiskt till i nya listor och bibliotek som skapas på de webbplatser som är kopplade till navet och till alla nya webbplatser som läggs till navet.

För att den här funktionen ska fungera måste innehållstyperna som publiceras redan vara publicerade.

Att skicka innehållstyper till en hubb

1. Öppna **Innehållstjänster** i administrationscenter för SharePoint och välj sedan **Galleri med innehållstyper**.
2. Välj den innehållstyp som du vill skicka till navet.
3. Välj **Redigera** i kommandofältet.
4. Välj **Välj navplatser**.
5. Välj de navplatser du vill använda och välj sedan **OK**.
6. Välj **Spara**.

När du skickar en innehållstyp till en befintlig hubb och dess befintliga kopplade webbplatser för första gången kan det ta upp till en timme från det att hubben eller tillhörande webbplatser besökts för inställningarna att uppdateras på webbplatsen. Alla nya associationer till hubben kräver inte detta utan där kommer inställningarna att återspeglas efter några minuter.

När inställningarna har uppdaterats blir innehållstypen med de här inställningarna tillgänglig på alla nyligen kopplade webbplatser med hubben på några minuter. Sedan en ny lista eller ett nytt bibliotek skapas kommer innehållstypen automatiskt, efter att ha gjorts tillgänglig, att läggas till på ett par minuter. En innehållstyp som skickas kommer bara att läggas till i ett dokumentbibliotek om den kommer direkt eller indirekt från dokumentets innehållstyp och en innehållstyp läggs endast till i en lista om den inte direkt eller indirekt kommer från dokumentets innehållstyp.

## <a name="see-also"></a>Se även
