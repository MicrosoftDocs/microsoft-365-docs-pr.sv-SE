---
title: Ta bort Microsoft 365-användarkonton med PowerShell
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
description: Lär dig hur du använder olika moduler i PowerShell för att ta bort Microsoft 365-användarkonton.
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754546"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Ta bort Microsoft 365-användarkonton med PowerShell

Du kan använda PowerShell för Microsoft 365 för att ta bort och återställa användar konton.

>[!Note]
>Lär dig hur du [återställer ett användar konto](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) med hjälp av administrations centret för Microsoft 365.
>
>En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

När du har anslutit kan du använda följande syntax för att ta bort ett enskilt användar konto:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

Det här exemplet tar bort användar kontot *fabricec \@ litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Parametern *-ObjectID* i cmdleten **Remove-AzureADUser** accepterar antingen kontots inloggnings namn, som även kallas användar huvud namnet eller kontots objekt-ID.
  
Använd följande kommandon för att Visa konto namnet baserat på användarens namn:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas konto namnet för användaren *Caleb brädor*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Om du vill ta bort ett konto baserat på användarens visnings namn använder du följande kommandon:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

När du tar bort ett användar konto via Microsoft Azure Active Directory-modulen för Windows PowerShell, tas kontot inte bort permanent. Du kan återställa det borttagna användar kontot inom 30 dagar.

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Använd följande syntax för att ta bort ett användar konto:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* . Kör dessa cmdletar från Windows PowerShell.
>

Det här exemplet tar bort användar kontots *BelindaN@litwareinc.com*.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Om du vill återställa ett borttaget användar konto inom 30 dagar kan du använda följande syntax:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

I det här exemplet återställs det borttagna kontot * \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Om du vill visa listan med borttagna användare som kan återställas kör du följande kommando:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Om användar kontots ursprungliga användar namn används av ett annat konto kan du använda parametern _NewUserPrincipalName_ i stället för _userPrincipalName_ för att ange ett annat huvud namn när du återställer användar kontot.


## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
