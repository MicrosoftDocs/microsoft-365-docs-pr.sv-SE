---
title: Funktionstestning på testbas
description: Information om hur du testar programmet med befintliga automatiska funktionstester
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323229"
---
# <a name="functional-testing"></a>Funktionstestning

Som programvaruleverantör kan du nu utföra anpassade funktionstester med valfri testram – via självbetjäning för M365-portalen. 

När vi först startade tjänsten erbjöd vi de färdiga testerna, som är en fördefinierad uppsättning tester som drivs via standardiserade skript. Detta kunde dock inte få fullständig testtäckning för många oberoende programvaruleverantörer (ISV). 

Som svar på din feedback ger vi våra ISV möjlighet att ladda upp automatiska funktionstest.

Följ stegen nedan om du vill använda den här funktionen:

1. Upload dina filer (binärfiler, beroenden och skript) som ett enda .zip paket.
2. Välj om du vill starta om virtuella testdatorer vid olika körningspunkter.
3. Hantera tillgängliga alternativ för dina skript.
4. Välj när den ska Windows på den virtuella maskinerna under körning.

Detaljerade beskrivningar av stegen ovan är markerade nedan:

**Upload ett funktionellt testpaket**

Kom igång genom att gå till Upload-sidan genom att välja Upload nytt program under Programkatalog på navigeringsmenyn till vänster på Testbas för M365-portalen i Azure. Därifrån kan du:

Flik 1 – Ange grundläggande information. Ange namnet på och versionen av programmet. I alternativet Typ av test väljer du ```Functional tests``` . 

*Observera att alternativet OOB (out-of-Box) är obligatoriskt som standard.*


![Välj fliken funktionstestning](Media/functional_testing_tab1.png)

Flik 2 – Upload de olika komponenterna i paketet genom att ladda upp en ZIP-fil med hela testet (binärfiler, beroenden, skript osv.). 

Se aka.ms/usl-package-outline för mer information. (Obs! Både in-box-testskripten och innehållet i funktionstestet bör placeras i samma zip-fil). För närvarande är filstorleken begränsad till 2 GB.

Flik 3 – Konfigurera de inflikar- och funktionstestaktiviteterna. Välj sökvägarna till PowerShell-skripten som installerar, startar, stänger och avinstallerar programmet (för In-of-Box) samt sökvägarna till alla dina egna skript för att utföra funktionstestet. **(Obs! Ett skript för att avinstallera programmet är valfritt).**

För närvarande kan du ladda upp mellan 1 och 8 skript för dina funktionstester. (Kommentera det här inlägget på ett bra sätt om du behöver fler skript!)

![Upload upp till 8 skript med funktionstester](Media/functional_testing_tab3.png)

(Valfritt) Konfigurera en omstart efter installationen. För vissa program krävs en omstart efter installationen. 

Välj för det specifika skriptet på fliken Uppgifter om du vill att en ```Reboot After Execution``` omstart ska ske efter körningen av skriptet.

Flik 4 – Välj när Windows-uppdateringen installeras: Programmet för korrigeringen Windows Uppdatering utförs innan något skript som du väljer. Vi rekommenderar att du installerar en Windows uppdatering efter programmets installation för att nära efterlikna dina verkliga användningsscenarier.

![Uppdateringen Windows kan installeras efter ett visst skript](Media/functional_testing_tab4.png)

Flik 5 – Granska och skapa paketet. När du har utfört stegen ovan väljer du att ```Create``` slutföra uppladdningsprocessen.

När paketet har skapats kan du kontrollera verifieringsstatus för paketet.

Vi kör ett första test för att installera, starta, stänga och avinstallera programmet. Det gör att vi kan verifiera att ditt paket kan installeras på vår tjänst utan fel.

Verifieringsprocessen kan ta upp till 24 timmar. När verifieringen är klar kan du se status i ```Manage packages``` menyn, vilket är en av två poster:

1. Verifieringen lyckas: Paketet testas automatiskt mot förhandsuppdateringar Windows de OS-versioner du valt.
eller
2. Verifieringen misslyckas: Du måste undersöka orsakerna till felet, åtgärda problemet och ladda upp paketet på ny plats.

Du får också ett meddelande om båda resultaten via meddelandeikonen i Azure Portal.
