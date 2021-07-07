---
title: Upload Binärfiler för program
description: Komma igång med Test Base för M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323169"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Steg 3: Upload dina binärfiler, beroenden och skript

På den här fliken laddar du upp ett enda zip-paket som innehåller dina binärfiler, beroenden och skript som används för att köra testpaketet.

## <a name="upload-package-zip-file"></a>Upload zip-fil med paket

![Upload dina binärfiler](Media/AddBinaries.png)

  - Uppladdade beroenden kan inkludera testramar, skriptmotorer eller data som kan användas för att köra programmet eller testfall. Du kan till exempel ladda upp Selenium och ett webdriver-installationsprogram för att köra webbläsarbaserade tester.
  - Det är bäst att se till att skriptaktiviteterna hålls i moduler, t.ex. 
    - Skriptet ```Install``` utför bara installationsåtgärder.
    - Skriptet ```Launch``` startar bara programmet.
    - Skriptet ```Close``` stänger bara programmet.
    - Det ```Uninstall``` valfria skriptet avinstallerar bara programmet.

**För närvarande har portalen endast stöd för PowerShell-skript.**


## <a name="next-steps"></a>Nästa steg 

Gå vidare till nästa artikel för att gå till Steg 4: **Ange testaktiviteter**.
> [!div class="nextstepaction"]
> [Gå tillbaka](uploadApplication.md)
> [!div class="nextstepaction"]
> [Nästa steg](testtask.md)

