---
title: Blockera Microsoft 365-användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Så här använder du PowerShell för att blockera och häva blockeringen av åtkomst Microsoft 365 konton.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754686"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Blockera Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

När du blockerar åtkomst till ett Microsoft 365-konto hindrar du någon från att använda kontot för att logga in och få åtkomst till tjänster och data i Microsoft 365 organisation. Du kan använda PowerShell för att blockera åtkomst till enskilda eller flera användarkonton.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
### <a name="block-access-to-individual-user-accounts"></a>Blockera åtkomst till enskilda användarkonton

Använd följande syntax för att blockera ett enskilt användarkonto:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Parametern *-ObjectID* i cmdleten **Set-AzureAD** accepterar antingen kontots inloggningsnamn, som även kallas användarens huvudnamn, eller kontots objekt-ID.
  
I det här exemplet blockeras åtkomst till *användarkontot fabricec@litwareinc.com*.
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Om du vill häva blockeringen för det här användarkontot kör du följande kommando:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Om du vill visa UPN för användarkontot baserat på användarens visningsnamn använder du följande kommandon:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

I det här exemplet visas ANVÄNDARKONTOTS UPN för *användaren Caleb Hansson.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Använd följande kommandon för att blockera ett konto baserat på användarens visningsnamn:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Om du vill kontrollera blockerad status för ett användarkonto använder du följande kommando:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Blockera flera användarkonton

Om du vill blockera åtkomst för flera användarkonton skapar du en textfil som innehåller ett konto inloggningsnamn på varje rad så här:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

I följande kommandon är exempeltextfilen *C:\Mina Documents\Accounts.txt*. Ersätt det här filnamnet med sökvägen och filnamnet för textfilen.
  
Om du vill blockera åtkomst till de konton som visas i textfilen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Om du vill häva blockeringen av de konton som listas i textfilen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
### <a name="block-individual-user-accounts"></a>Blockera enskilda användarkonton

Använd följande syntax för att blockera åtkomst för ett enskilt användarkonto:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell och cmdlets som har *Msol* i sitt namn. Du måste köra dessa cmdlets från Windows PowerShell.

I det här exemplet blockeras åtkomst till *användarkontot och \@ litwareinc.com*.
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Om du vill häva blockeringen av användarkontot kör du följande kommando:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Om du vill kontrollera blockerad status för ett användarkonto kör du följande kommando:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Blockera åtkomst för flera användarkonton

Skapa först en textfil som innehåller ett konto på varje rad så här:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

I följande kommandon är exempeltextfilen *C:\Mina Documents\Accounts.txt*. Ersätt det här filnamnet med sökvägen och filnamnet för textfilen.
    
Om du vill blockera åtkomst för de konton som visas i textfilen kör du följande kommando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Om du vill häva blockeringen av de konton som visas i textfilen kör du följande kommando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
