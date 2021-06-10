---
title: CSV-fil med enhetslista
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Lär dig hur du gör en CSV-fil för AutoPilot i Microsoft 365 för företag.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579224"
---
# <a name="device-list-csv-file"></a>CSV-fil med enhetslista

## <a name="device-list-csv-file-format"></a>Enhetslista .csv filformat

För att hantera och distribuera enheter via Windows Autopilot behöver du en .csv som innehåller specifik information om enheterna.
  
Kolumnerna i enhetslistfilen måste ha följande rubriker i angiven ordning:
  
- Kolumn A: Enhetsserienummer

- Kolumn B: lämna tomt

- Kolumn C: Maskinvaruhash

Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil. 

När du lägger till enheter måste du också lägga till dem i en profil. En profil används för att använda AutoPilot-distributionsprofiler på en enhet eller en grupp av enheter.
  
## <a name="related-articles"></a>Relaterade artiklar

[Microsoft 365 dokumentation och resurser för företag](../../business/index.yml)
  
[Komma igång med Microsoft 365 för företag](../../business/microsoft-365-business-overview.md)
  
[Hantera Microsoft 365 för företag](../../business/manage.md)
