---
title: Windows Testa serverprogram
description: Validera med windows server-programtestning
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
ms.openlocfilehash: d6e6d2098ab187d2473acb5dcf0c3938a9ef7459
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323277"
---
# <a name="windows-server-application-testing"></a>Windows Testa serverprogram 

Med Test Base för Microsoft 365 kan du nu verifiera dina program mot Windows Server 2016 och 2019, inklusive Server Core!

För att komma igång med validering av dina uppladdade program mot förhandsuppdateringar för Windows Server 2016- och 2019-operativsystem på Test Base för Microsoft 365 följer du följande steg:

1.   Logga in på vår portal för självbetjäning. I den vänstra navigeringsmenyn väljer ```Upload new package``` du under och fyller i ```Package catalogue``` testinformationen.

2.  Välj ```Security updates``` som OS-uppdateringstyp:

![Välj säkerhetsuppdateringar](Media/selecting-security-updates.png)

3. Under OS-versioner som ska testas väljer du tillämpliga OS-versioner. Du kan välja Windows Server OS-versioner eller en kombination av versioner av server- och klientoperativsystem.

![Välj OS-version](Media/selecting-OS-versions.png)

4. Ange annan information som krävs, granska den information som tillhandahålls och ladda upp ditt programpaket. När du har laddat upp kan du visa paketstatus på menyfliken Hantera paket.


5. Om du vill visa testresultat och insikter från validering av programmet mot säkerhetsuppdateringar i förväg för Windows Server 2016 och 2019 går du till sidan Testsammanfattning eller resultatsidan för säkerhetsuppdateringen.

![Visa testresultat](Media/access-test-results.png)

Gå vidare till nästa artikel för att komma igång med **funktionstestning**
> [!div class="nextstepaction"]
> [Nästa steg](functional.md)

