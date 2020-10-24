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
description: Använda PowerShell för att blockera och avblockera åtkomst till Microsoft 365-konton.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754686"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Blockera Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

När du blockerar åtkomst till ett Microsoft 365-konto kan du hindra andra från att använda kontot för att logga in och komma åt tjänsterna och informationen i din Microsoft 365-organisation. Du kan använda PowerShell för att blockera åtkomst till enskilda eller flera användar konton.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
### <a name="block-access-to-individual-user-accounts"></a>Blockera åtkomst till enskilda användar konton

Använd följande syntax för att blockera ett enskilt användar konto:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Parametern *-ObjectID* i cmdleten **set-AzureAD** accepterar antingen konto inloggnings namnet, även kallat användarens huvud namn, eller kontots objekt-ID.
  
Det här exemplet blockerar åtkomst till användar kontots *fabricec@litwareinc.com*.
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Om du vill häva blockeringen för det här användar kontot kör du följande kommando:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

För att Visa användar kontots UPN baserat på användarens visnings namn, Använd följande kommandon:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

I det här exemplet visas UPN för användar kontot för användaren  *Caleb brädor*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Om du vill blockera ett konto baserat på användarens visnings namn använder du följande kommandon:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Använd följande kommando för att kontrol lera den spärrade statusen för ett användar konto:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Blockera flera användar konton

Om du vill blockera åtkomst för flera användar konton skapar du en textfil som innehåller ett inloggnings namn för konto på varje rad, så här:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

I följande kommandon är exempel text filen *c:\mina Documents\Accounts.txt*. Ersätt fil namnet med text filens sökväg och fil namn.
  
Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Om du vill häva blockeringen för de konton som visas i text filen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
### <a name="block-individual-user-accounts"></a>Blockera enskilda användar konton

Använd följande syntax för att blockera åtkomst för ett enskilt användar konto:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *MSOL* i sitt namn. Du måste köra de här cmdletarna från Windows PowerShell.

I det här exemplet blockeras åtkomst till användar kontot *fabricec \@ litwareinc.com*.
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Om du vill häva blockeringen för användar kontot kör du följande kommando:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Kör följande kommando för att kontrol lera den spärrade statusen för ett användar konto:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Blockera åtkomst för flera användar konton

Börja med att skapa en textfil som innehåller ett konto på varje rad, så här:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

I följande kommandon är exempel text filen *c:\mina Documents\Accounts.txt*. Ersätt fil namnet med text filens sökväg och fil namn.
    
Om du vill blockera åtkomst för de konton som visas i text filen kör du följande kommando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Om du vill häva blockeringen för kontona i text filen kör du följande kommando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
