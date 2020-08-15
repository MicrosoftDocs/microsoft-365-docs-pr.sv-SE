---
title: Visa licensierade och olicensierade Microsoft 365-användare med PowerShell
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
description: I den här artikeln förklarar vi hur du använder PowerShell för att Visa licensierade och olicensierade Microsoft 365-användarkonton.
ms.openlocfilehash: 8a99ba2a80f1d814ec5268c4f8f479837eb54dc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694496"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="5efa4-103">Visa licensierade och olicensierade Microsoft 365-användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5efa4-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="5efa4-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5efa4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5efa4-105">Användar konton i din Microsoft 365-organisation kan ha vissa, alla eller inga av de tillgängliga licenserna tilldelade till dem från de licens planer som är tillgängliga i din organisation.</span><span class="sxs-lookup"><span data-stu-id="5efa4-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="5efa4-106">Du kan använda PowerShell för Microsoft 365 för att snabbt hitta licensierade och olicensierade användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5efa4-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5efa4-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="5efa4-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5efa4-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5efa4-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="5efa4-109">Om du vill visa en lista över alla användar konton i din organisation som inte har tilldelats något av dina licens planer (olicensierade användare) kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5efa4-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="5efa4-110">Om du vill visa en lista över alla användar konton i organisationen som har tilldelats alla dina licens planer (licensierade användare) kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5efa4-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="5efa4-111">Använd kommandot för att visa en lista över alla användare i ditt abonnemang `Get-AzureAdUser -All $true` .</span><span class="sxs-lookup"><span data-stu-id="5efa4-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5efa4-112">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5efa4-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5efa4-113">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5efa4-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="5efa4-114">Om du vill visa listan över alla användar konton och deras licensierings status i organisationen kör du följande kommando i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5efa4-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="5efa4-115">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="5efa4-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5efa4-116">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5efa4-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="5efa4-117">Om du vill visa listan över alla olicensierade användar konton i organisationen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5efa4-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="5efa4-118">Om du vill visa listan över alla licensierade användar konton i organisationen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5efa4-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="5efa4-119">Se även</span><span class="sxs-lookup"><span data-stu-id="5efa4-119">See also</span></span>

[<span data-ttu-id="5efa4-120">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5efa4-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5efa4-121">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5efa4-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5efa4-122">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5efa4-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
