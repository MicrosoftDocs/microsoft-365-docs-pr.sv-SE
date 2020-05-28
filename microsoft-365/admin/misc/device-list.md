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
# <a name="device-list-csv-file"></a><span data-ttu-id="cd21c-103">CSV-fil för enhetslista</span><span class="sxs-lookup"><span data-stu-id="cd21c-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="cd21c-104">Enhetslista .csv-filformat</span><span class="sxs-lookup"><span data-stu-id="cd21c-104">Device list .csv file format</span></span>

<span data-ttu-id="cd21c-105">Om du vill hantera och distribuera enheter via Windows Autopilot behöver du en CSV-fil som innehåller specifik information om enheterna.</span><span class="sxs-lookup"><span data-stu-id="cd21c-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="cd21c-106">Kolumnerna i enhetslistefilen måste ha följande rubriker i angiven ordning:</span><span class="sxs-lookup"><span data-stu-id="cd21c-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="cd21c-107">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="cd21c-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="cd21c-108">Kolumn B: Lämna tomt</span><span class="sxs-lookup"><span data-stu-id="cd21c-108">Column B: leave blank</span></span>

- <span data-ttu-id="cd21c-109">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="cd21c-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="cd21c-110">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="cd21c-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="cd21c-111">När du lägger till enheter måste du också lägga till dem i en profil.</span><span class="sxs-lookup"><span data-stu-id="cd21c-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="cd21c-112">En profil används för att tillämpa automatiska distributionsprofiler på en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="cd21c-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cd21c-113">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cd21c-113">Related articles</span></span>

[<span data-ttu-id="cd21c-114">Microsoft 365 för affärsdokumentation och resurser</span><span class="sxs-lookup"><span data-stu-id="cd21c-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="cd21c-115">Komma igång med Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cd21c-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="cd21c-116">Hantera Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cd21c-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
