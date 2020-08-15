---
title: Tilldela roller till Microsoft 365-användarkonton med PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: I den här artikeln lär du dig hur snabbt och enkelt kan använda PowerShell för Microsoft 365 för att tilldela roller till användar konton.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694362"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a>Tilldela roller till Microsoft 365-användarkonton med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan snabbt och enkelt tilldela roller till användar konton med PowerShell för Microsoft 365.

>[!Note]
>Information om hur du tilldelar roller till användar konton med Microsoft 365 Admin Center finns i [de här anvisningarna](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) med ett globalt administratörs konto.
  
Därefter bestämmer du inloggnings namnet för det användar konto som du vill lägga till i en roll (till exempel: fredsm@contoso.com). Detta kallas även användarens huvud namn (UPN).

Därefter bestämmer du namnet på rollen. Använd den här [listan över behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Var uppmärksam på anteckningarna i den här artikeln. Vissa rollnamn är olika för Azure AD PowerShell. Rollen "SharePoint-administratör" i administrations centret för Microsoft 365 heter till exempel "SharePoint service Administrator" för Azure AD PowerShell.
>

Fyll i inloggnings-och rollnamn och kör dessa kommandon.
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Här är ett exempel på en färdigställd kommando uppsättning som tilldelar rollen som administratör för SharePoint-belindan@contoso.com till kontot konto:
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Använd dessa kommandon för att visa listan över användar namn för en viss roll.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med ett globalt administratörs konto.
  
### <a name="for-a-single-role-change"></a>För en ändring av en roll

De vanligaste sätten för ett visst användar konto är med dess visnings namn eller e-postnamn, och det kallas också dess inloggnings namn eller huvud namn (UPN).

#### <a name="display-names-of-user-accounts"></a>Visa användar konto namn

Om du använder för att arbeta med användar kontonas visnings namn bestämmer du följande:
  
- Det användar konto som du vill konfigurera.
    
    För att ange användar kontot måste du bestämma dess visnings namn. Använd det här kommandot för att få ett fullständigt List konto:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot visar visnings namnet för dina användar konton, sorterade efter visnings namnet, en skärm bild i taget. Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten. Här är ett exempel:

   >[!Note]
   >PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".
    
- Den roll du vill tilldela.
    
    Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har bestämt visnings namnet på kontot och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Kopiera kommandona och klistra in dem i anteckningar. För variablerna **$dispName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken. Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem. Du kan också använda Windows PowerShell ISE (Integrated script Environment).
  
Här är ett exempel på en färdigställd kommando uppsättning:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Inloggnings namn för användar konton

Om du är van vid att arbeta med inloggnings namnen eller UPN: er för användar konton kan du bestämma följande.
  
- Användar kontots UPN.
    
    Om du inte redan känner till UPN använder du det här kommandot:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot visar UPN för dina användar konton, sorterade efter UPN, en skärm bild i taget. Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten. Här är ett exempel:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".
    
- Den roll du vill tilldela.
    
    Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har kontots UPN-namn och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopiera kommandona och klistra in dem i anteckningar. För variablerna **$upnName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken. Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem. Du kan också använda Windows PowerShell ISE.
  
Här är ett exempel på en färdigställd kommando uppsättning:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Ändringar i flera roller

Om du vill ändra flera roller kontrollerar du följande:
  
- Vilka användar konton som du vill konfigurera. Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visnings namn eller UPN.
    
- Vilka roller du vill tilldela till varje användar konto.
    
    Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Skapa sedan en CSV-textfil som innehåller fälten visnings namn eller UPN och rollnamn. Det är enkelt att göra det i Microsoft Excel.

Här är ett exempel på visnings namn:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Här följer ett exempel på UPN:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Se även

- [Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
