---
title: Visa licensierade och olicensierade Microsoft 365 användare med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: I den här artikeln förklaras hur du använder PowerShell för att visa licensierade och olicensierade Microsoft 365-användarkonton.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651390"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="1db2a-103">Visa licensierade och olicensierade Microsoft 365 användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1db2a-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="1db2a-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1db2a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1db2a-105">Användarkonton i Microsoft 365 organisation kan ha några, alla eller inga tillgängliga licenser tilldelade till dem från licensplanerna som är tillgängliga i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1db2a-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="1db2a-106">Du kan använda PowerShell för Microsoft 365 snabbt hitta licensierade och olicensierade användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1db2a-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1db2a-107">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="1db2a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1db2a-108">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1db2a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="1db2a-109">Om du vill visa listan över alla användarkonton i organisationen som INTE har tilldelats någon licens (olicensierade användare) kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1db2a-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="1db2a-110">Om du vill visa en lista över alla användarkonton i organisationen som har tilldelats någon av dina licensplaner (licensierade användare) kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1db2a-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="1db2a-111">Använd kommandot för att visa alla användare i din `Get-AzureAdUser -All $true` prenumeration.</span><span class="sxs-lookup"><span data-stu-id="1db2a-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1db2a-112">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1db2a-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1db2a-113">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="1db2a-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="1db2a-114">Om du vill visa listan över alla användarkonton och deras licensstatus i din organisation kör du följande kommando i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1db2a-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="1db2a-115">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="1db2a-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1db2a-116">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1db2a-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="1db2a-117">Om du vill visa listan över alla olicensierade användarkonton i organisationen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1db2a-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="1db2a-118">Om du vill visa listan över alla licensierade användarkonton i organisationen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1db2a-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="1db2a-119">Se även</span><span class="sxs-lookup"><span data-stu-id="1db2a-119">See also</span></span>

[<span data-ttu-id="1db2a-120">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1db2a-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1db2a-121">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1db2a-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1db2a-122">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1db2a-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
