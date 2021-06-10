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
# <a name="device-list-csv-file"></a><span data-ttu-id="1bbbf-103">CSV-fil med enhetslista</span><span class="sxs-lookup"><span data-stu-id="1bbbf-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="1bbbf-104">Enhetslista .csv filformat</span><span class="sxs-lookup"><span data-stu-id="1bbbf-104">Device list .csv file format</span></span>

<span data-ttu-id="1bbbf-105">För att hantera och distribuera enheter via Windows Autopilot behöver du en .csv som innehåller specifik information om enheterna.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="1bbbf-106">Kolumnerna i enhetslistfilen måste ha följande rubriker i angiven ordning:</span><span class="sxs-lookup"><span data-stu-id="1bbbf-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="1bbbf-107">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="1bbbf-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="1bbbf-108">Kolumn B: lämna tomt</span><span class="sxs-lookup"><span data-stu-id="1bbbf-108">Column B: leave blank</span></span>

- <span data-ttu-id="1bbbf-109">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="1bbbf-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="1bbbf-110">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="1bbbf-111">När du lägger till enheter måste du också lägga till dem i en profil.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="1bbbf-112">En profil används för att använda AutoPilot-distributionsprofiler på en enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="1bbbf-113">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="1bbbf-113">Related articles</span></span>

[<span data-ttu-id="1bbbf-114">Microsoft 365 dokumentation och resurser för företag</span><span class="sxs-lookup"><span data-stu-id="1bbbf-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="1bbbf-115">Komma igång med Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="1bbbf-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="1bbbf-116">Hantera Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="1bbbf-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
