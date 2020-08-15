---
title: Ta bort Microsoft 365-användarkonton med PowerShell
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: I den här artikeln lär du dig hur du använder olika moduler i PowerShell för att ta bort Microsoft 365-användarkonton.
ms.openlocfilehash: 6da2d83b3f305db09f8c1d02f54e643a0ad1978b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694686"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Ta bort Microsoft 365-användarkonton med PowerShell

Du kan använda PowerShell för Microsoft 365 för att ta bort ett användar konto.
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

När du har anslutit kan du använda följande syntax för att ta bort ett enskilt användar konto:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

Det här exemplet tar bort användar kontots fabricec@litwareinc.com.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Parametern **-ObjectID** i cmdleten **Remove-AzureADUser** accepterar antingen kontots inloggnings namn, kallas även för användarens huvud namn, eller kontots objekt-ID.
  
Använd följande kommandon för att Visa konto namnet baserat på användarens namn:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas konto namnet för den användare som heter Caleb brädor.
  
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

När du tar bort ett användar konto med Microsoft Azure Active Directory-modulen för Windows PowerShell tas kontot inte bort permanent. Du kan återställa det borttagna användar kontot inom 30 dagar.

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Använd följande syntax för att ta bort ett användar konto:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Det här exemplet tar bort användar kontots BelindaN@litwareinc.com.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Om du vill återställa ett borttaget användar konto inom 30 dagar kan du använda följande syntax:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

Det här exemplet återställer det borttagna kontot BelindaN@litwareinc.com.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 **Kommentarer:**
  
- Om du vill visa listan med borttagna användare som kan återställas kör du följande kommando:
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- Om användar kontots ursprungliga användar namn används av ett annat konto kan du använda parametern _NewUserPrincipalName_ i stället för _userPrincipalName_ för att ange ett annat huvud namn när du återställer användar kontot.


## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
