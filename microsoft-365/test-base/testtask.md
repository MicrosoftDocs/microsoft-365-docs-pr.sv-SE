---
title: Ställa in testaktiviteterna
description: Ställa in testaktiviteterna
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322947"
---
# <a name="step-4-the-tasks-tab"></a>Steg 4: Fliken Uppgifter

På fliken uppgifter ska du ange sökvägar till testskripten som finns i zip-mappen som du har laddat upp under fliken binärfiler.

  - **In of Box-testskript:** Ange de relativa sökvägarna till installationen, starta, stäng och avinstallera skript. Du kan också välja ytterligare inställningar för installationsskriptet.
  - **Funktionstestskript:** Skriv den relativa sökvägen till varje funktionstestskript som laddas upp. Ytterligare funktionstestskript kan läggas till med ```Add Script``` knappen. Du behöver minst ett (1) skript och kan lägga till upp till åtta (8) funktionstestskript. 
  
    Skripten körs i överföringssekvens och ett fel i ett visst skript stoppar efterföljande skript att köras.
    Du kan också välja ytterligare inställningar för varje skript som tillhandahålls.

## <a name="set-script-path"></a>Ange skriptsökväg

![Bild av testaktivitet](Media/testtask.png)

Exempel på hur du anger den relativa sökvägen till en mappstruktur nedan:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** skulle ha gjort det. _ScriptX.ps1_ som den relativa sökvägen.
  - **Script.ps1** kunde ha _mapp1/script.ps1_ som den relativa sökvägen.


## <a name="next-steps"></a>Nästa steg

Visa information om fliken Testalternativ i nästa artikel 
> [!div class="nextstepaction"]
> [Nästa steg](testoptions.md)
