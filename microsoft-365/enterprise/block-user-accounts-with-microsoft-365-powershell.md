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
description: I den här artikeln förklarar vi hur du använder PowerShell till att blockera och avblockera åtkomst till Microsoft 365-konton.
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694561"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Blockera Microsoft 365-användarkonton med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du blockerar åtkomst till ett Microsoft 365-konto kan ingen använda kontot för att logga in och komma åt tjänsterna och informationen i din Microsoft 365-organisation. Du kan använda PowerShell för att blockera åtkomst till enskilda och flera användar konton.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
### <a name="block-access-to-individual-user-accounts"></a>Blockera åtkomst till enskilda användar konton

Använd följande syntax för att blockera ett enskilt användar konto:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Parametern-ObjectID i cmdleten Set-AzureAD accepterar antingen konto inloggnings namnet, även kallat användarens huvud namn, eller kontots objekt-ID. 
  
Det här exemplet blockerar åtkomst till användar kontots fabricec@litwareinc.com.
  
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

I det här exemplet visas UPN för användar kontot för den användare som heter Caleb brädor.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Om du vill blockera ett konto baserat på användarens visnings namn använder du följande kommandon:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Du kan när som helst kontrol lera den spärrade statusen för ett användar konto med följande kommando:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a>Blockera åtkomst till flera användar konton

Om du vill blockera åtkomst till flera användar konton skapar du en textfil som innehåller ett inloggnings namn för konto på varje rad, så här:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

I följande kommandon är exempel text filen C:\Mina Documents\Accounts.txt. Ersätt det med sökvägen och fil namnet för text filen.
  
Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Om du vill häva blockeringen för kontona i text filen kör du följande kommando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
### <a name="block-access-to-individual-user-accounts"></a>Blockera åtkomst till enskilda användar konton

Använd följande syntax för att blockera åtkomst till ett enskilt användar konto:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Det här exemplet blockerar åtkomst till användar kontots fabricec@litwareinc.com.
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Om du vill häva blockeringen för användar kontot kör du följande kommando:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Du kan när som helst kontrol lera den spärrade statusen för ett användar konto med följande kommando:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a>Blockera åtkomst till flera användar konton

Börja med att skapa en textfil som innehåller ett konto på varje rad, så här:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

I följande kommandon är exempel text filen C:\Mina Documents\Accounts.txt. Ersätt det med sökvägen och fil namnet för text filen.
    
Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:
    
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
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
