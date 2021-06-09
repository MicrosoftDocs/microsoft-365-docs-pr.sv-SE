---
title: Inaktivera åtkomst till Sway med PowerShell för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: 7221a4c9-ae03-4598-81fe-a655c02f40ab
description: Lär dig var du laddar ManageSway.ps1 PowerShell-skript som gör att du kan inaktivera åtkomst till Sway i Microsoft 365 organisation.
ms.openlocfilehash: bec96c6232eee88355997f56e49f1f99b8cc2fbd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694538"
---
# <a name="disable-access-to-sway-with-powershell-for-microsoft-365"></a><span data-ttu-id="94e1d-103">Inaktivera åtkomst till Sway med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94e1d-103">Disable access to Sway with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="94e1d-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="94e1d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94e1d-105">Med ManageSway.ps1 PowerShell-skript kan du visa och inaktivera tjänster i din Microsoft 365 organisation, inklusive Sway.</span><span class="sxs-lookup"><span data-stu-id="94e1d-105">The ManageSway.ps1 PowerShell script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="94e1d-106">Det här skriptet automatiserar procedurerna som beskrivs i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="94e1d-106">This script automates the procedures that are described in the following topics:</span></span>
  
- [<span data-ttu-id="94e1d-107">Visa licenser och tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="94e1d-107">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="94e1d-108">Inaktivera åtkomst till tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="94e1d-108">Disable access to services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
    
<span data-ttu-id="94e1d-109">Du måste ladda ned de två filer som är kopplade till skriptet:</span><span class="sxs-lookup"><span data-stu-id="94e1d-109">You need to download the two files that are associated with the script:</span></span>
  
- <span data-ttu-id="94e1d-110">Skriptet ManageSway.ps1 vid [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span><span class="sxs-lookup"><span data-stu-id="94e1d-110">The ManageSway.ps1 script at [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span></span>
    
- <span data-ttu-id="94e1d-111">Hjälpfilen för skriptet vid [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span><span class="sxs-lookup"><span data-stu-id="94e1d-111">The help file for the script at [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span></span>
    

