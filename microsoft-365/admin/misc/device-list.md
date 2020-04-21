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
# <a name="device-list-csv-file"></a><span data-ttu-id="ace5d-103">CSV-fil för enhetslista</span><span class="sxs-lookup"><span data-stu-id="ace5d-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="ace5d-104">Enhetslista .csv-filformat</span><span class="sxs-lookup"><span data-stu-id="ace5d-104">Device list .csv file format</span></span>

<span data-ttu-id="ace5d-105">Om du vill hantera och distribuera enheter via Windows Autopilot behöver du en CSV-fil som innehåller specifik information om enheterna.</span><span class="sxs-lookup"><span data-stu-id="ace5d-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="ace5d-106">Kolumnerna i enhetslistefilen måste ha följande rubriker i angiven ordning:</span><span class="sxs-lookup"><span data-stu-id="ace5d-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="ace5d-107">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="ace5d-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="ace5d-108">Kolumn B: Lämna tomt</span><span class="sxs-lookup"><span data-stu-id="ace5d-108">Column B: leave blank</span></span>

- <span data-ttu-id="ace5d-109">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="ace5d-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="ace5d-110">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="ace5d-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="ace5d-111">När du lägger till enheter måste du också lägga till dem i en profil.</span><span class="sxs-lookup"><span data-stu-id="ace5d-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="ace5d-112">En profil används för att tillämpa automatiska distributionsprofiler på en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="ace5d-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="ace5d-113">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ace5d-113">Related articles</span></span>

[<span data-ttu-id="ace5d-114">Microsoft 365 för affärsdokumentation och resurser</span><span class="sxs-lookup"><span data-stu-id="ace5d-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="ace5d-115">Komma igång med Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ace5d-115">Get started with Microsoft 365 for business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="ace5d-116">Hantera Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ace5d-116">Manage Microsoft 365 for business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
