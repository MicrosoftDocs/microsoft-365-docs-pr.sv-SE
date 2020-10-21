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
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651390"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Visa licensierade och olicensierade Microsoft 365-användare med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Användar konton i din Microsoft 365-organisation kan ha vissa, alla eller inga av de tillgängliga licenserna tilldelade till dem från de licens planer som är tillgängliga i din organisation. Du kan använda PowerShell för Microsoft 365 för att snabbt hitta licensierade och olicensierade användare i organisationen.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Om du vill visa en lista över alla användar konton i din organisation som inte har tilldelats något av dina licens planer (olicensierade användare) kör du följande kommando:
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Om du vill visa en lista över alla användar konton i organisationen som har tilldelats alla dina licens planer (licensierade användare) kör du följande kommando:
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Använd kommandot för att visa en lista över alla användare i ditt abonnemang `Get-AzureAdUser -All $true` .
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Om du vill visa listan över alla användar konton och deras licensierings status i organisationen kör du följande kommando i PowerShell:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

Om du vill visa listan över alla olicensierade användar konton i organisationen kör du följande kommando:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Om du vill visa listan över alla licensierade användar konton i organisationen kör du följande kommando:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
