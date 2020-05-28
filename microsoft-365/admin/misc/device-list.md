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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Lär dig hur du gör en CSV-fil för Autopilot i Microsoft 365 för företag.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399368"
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
  
[Komma igång med Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Hantera Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365/business/manage)
  
