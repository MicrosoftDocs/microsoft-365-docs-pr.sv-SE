---
title: Ta Microsoft 365 bort användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Lär dig hur du använder olika moduler i PowerShell för att Microsoft 365 användarkonton.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919146"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Ta Microsoft 365 bort användarkonton med PowerShell

Du kan använda PowerShell för Microsoft 365 att ta bort och återställa användarkonton.

>[!Note]
>Lär dig hur [du återställer ett användarkonto](../admin/add-users/restore-user.md) med hjälp Microsoft 365 administrationscenter.
>
>En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

När du har anslutt använder du följande syntax för att ta bort ett enskilt användarkonto:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

I det här exemplet tas användarkontot *bort från \@ litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Parametern *-ObjectID* i cmdleten **Remove-AzureADUser** accepterar antingen kontots inloggningsnamn, som även kallas användarkontots huvudnamn eller kontots objekt-ID.
  
Om du vill visa kontonamnet baserat på användarens namn använder du följande kommandon:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas kontonamnet för *användaren Caleb Entsson.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Om du vill ta bort ett konto baserat på användarens visningsnamn använder du följande kommandon:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

När du tar bort ett användarkonto via Microsoft Azure Active Directory för Windows PowerShell tas kontot inte bort permanent. Du kan återställa det borttagna användarkontot inom 30 dagar.

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Använd följande syntax för att ta bort ett användarkonto:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet. Kör dessa cmdlets från Windows PowerShell.
>

I det här exemplet tas *användarkontot* BelindaN@litwareinc.com .
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Om du vill återställa ett borttagna användarkonto inom respitperioden på 30 dagar använder du följande syntax:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

I det här exemplet återställs det borttagna *kontot BelindaN \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Kör följande kommando för att se en lista över borttagna användare som kan återställas:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Om användarkontots ursprungliga huvudnamn används av ett annat konto, ska du använda parametern _NewUserPrincipalName_ i stället för _UserPrincipalName_ för att ange ett annat huvudnamn när du återställer användarkontot.


## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)