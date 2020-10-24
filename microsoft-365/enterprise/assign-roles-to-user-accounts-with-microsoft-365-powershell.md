---
title: Tilldela roller till Microsoft 365-användarkonton med PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: I den här artikeln lär du dig hur snabbt och enkelt använder PowerShell för Microsoft 365 för att tilldela administratörs roller till användar konton.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754204"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Tilldela administratörs roller till Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan enkelt tilldela roller till användar konton med PowerShell för Microsoft 365.

>[!Note]
>Lär dig hur du  [tilldelar administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) till användar konton med Microsoft 365 Admin Center.
>
>En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Använd först ett globalt administratörs konto för att [ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Sedan identifierar du inloggnings namnet för det användar konto som du vill lägga till i en roll (till exempel: fredsm \@ contoso.com). Detta kallas även användarens huvud namn (UPN).

Därefter bestämmer du namnet på rollen. Se [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Var uppmärksam på anteckningarna i den här artikeln. Vissa rollnamn är olika för Azure Active Directory (Azure AD) PowerShell. *Administratörs* rollen för SharePoint i administrations centret för Microsoft 365 är till exempel *SharePoint service Administrator* i Azure AD PowerShell.
>

Fyll i inloggnings-och roll namnen och kör dessa kommandon:
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Här är ett exempel på en färdigställd kommando uppsättning som tilldelar rollen SharePoint service-administratör till det bekanta * \@ contoso.com* -kontot:
  
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

Använd dessa kommandon för att visa listan över användar namn för en viss administratörs roll.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Använd först ett globalt administratörs konto för att [ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
### <a name="for-a-single-role-change"></a>För en ändring av en roll

De vanligaste sätten att ange användar konto är med hjälp av dess visnings namn eller e-postnamn, som även kallas för dess inloggnings namn eller huvud namn (UPN).

#### <a name="display-names-of-user-accounts"></a>Visa användar konto namn

Om du använder för att arbeta med användar kontonas visnings namn bestämmer du följande information:
  
- Det användar konto som du vill konfigurera
    
    För att ange användar kontot måste du bestämma dess visnings namn. Använd det här kommandot för att få en fullständig lista över konton:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot visar visnings namnet för dina användar konton, sorterade efter visnings namnet, en skärm bild i taget. Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten. Se följande exempel.

   >[!Note]
   >PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* . Kör dessa cmdletar från Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".
    
- Den roll du vill tilldela
    
    Använd det här kommandot för att visa listan över tillgängliga administratörs roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har fastställt namnet på kontot och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Klistra in kommandon i anteckningar. För variablerna *$dispName* och *$roleName* ersätter du beskrivningen med deras värden. Ta bort \< and > tecknen men behåll citat tecknen. Kör de ändrade raderna till fönstret Microsoft Azure Active Directory-modul för Windows PowerShell för att köra dem. Du kan också använda Windows PowerShell ISE (Integrated script Environment).
  
Här är ett exempel på en färdigställd kommando uppsättning:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Inloggnings namn för användar konton

Om du använder för att arbeta med inloggnings namnen eller UPN: er för användar konton bestämmer du följande information:
  
- Användar kontots UPN
    
    Om du inte känner till UPN använder du det här kommandot:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot visar UPN för dina användar konton, sorterade efter UPN, en skärm bild i taget. Du kan använda **WHERE** -cmdleten för att filtrera listan. Här är ett exempel:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".
    
- Den roll du vill tilldela
    
    Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har UPN för kontot och namnet på rollen tilldelar du rollen till kontot genom att använda följande kommandon:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopiera kommandona och klistra in dem i anteckningar. För variablerna **$upnName** och **$roleName** . Ersätt beskrivningen med deras värden. Ta bort \< and > tecknen men behåll citat tecknen. Kopiera de ändrade raderna till Microsoft Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem. Du kan också använda Windows PowerShell ISE.
  
Här är ett exempel på en färdigställd kommando uppsättning:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Ändringar i flera roller

För ändringar av flera roller kontrollerar du följande information:
  
- Vilka användar konton du vill konfigurera. Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visnings namn eller UPN.
    
- Vilka roller du vill tilldela till varje användar konto. Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Skapa sedan en CSV-textfil som innehåller fälten visnings namn eller UPN och rollnamn. Det gör du enkelt i Microsoft Excel.

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

Här är ett exempel på UPN-användare:
  
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
- [Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
