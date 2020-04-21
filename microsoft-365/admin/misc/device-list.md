---
title: CSV-fil för enhetslista
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Lär dig hur du gör en CSV-fil för Autopilot i Microsoft 365 för företag.
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627866"
---
# <a name="device-list-csv-file"></a>CSV-fil för enhetslista

## <a name="device-list-csv-file-format"></a>Enhetslista .csv-filformat

Om du vill hantera och distribuera enheter via Windows Autopilot behöver du en CSV-fil som innehåller specifik information om enheterna.
  
Kolumnerna i enhetslistefilen måste ha följande rubriker i angiven ordning:
  
- Kolumn A: Enhetsserienummer

- Kolumn B: Lämna tomt

- Kolumn C: Maskinvaruhash

Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil. 

När du lägger till enheter måste du också lägga till dem i en profil. En profil används för att tillämpa automatiska distributionsprofiler på en enhet eller en grupp enheter.
  
## <a name="related-articles"></a>Relaterade artiklar

[Microsoft 365 för affärsdokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Komma igång med Microsoft 365 för företag](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[Hantera Microsoft 365 för företag](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
