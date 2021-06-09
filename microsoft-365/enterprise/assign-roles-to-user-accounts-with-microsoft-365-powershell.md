---
title: Tilldela roller till Microsoft 365 användarkonton med PowerShell
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
description: I den här artikeln lär du dig hur snabbt och enkelt du använder PowerShell Microsoft 365 att tilldela administratörsroller till användarkonton.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905386"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Tilldela administratörsroller Microsoft 365 användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan enkelt tilldela roller till användarkonton med hjälp av PowerShell för Microsoft 365.

>[!Note]
>Lär dig hur [du tilldelar](../admin/add-users/assign-admin-roles.md) administratörsroller till användarkonton Microsoft 365 administrationscentret.
>
>En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med att använda ett globalt administratörskonto [för att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Identifiera sedan inloggningsnamnet för det användarkonto som du vill lägga till i en roll (exempel: \@ contoso.com). Detta kallas även användarens huvudnamn (UPN).

Bestäm sedan namnet på rollen. Visa [behörigheter för administratörsroll i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Var uppmärksam på anteckningarna i den här artikeln. Vissa rollnamn är olika för PowerShell Azure Active Directory (Azure AD). Till exempel är *SharePoint administratörsrollen* i administrationscentret Microsoft 365 tjänst *SharePoint administratör i* Azure AD PowerShell.
>

Sedan fyller du i inloggnings- och rollnamnen och kör följande kommandon:
  
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

Här är ett exempel på en slutförd kommandouppsättning som tilldelar SharePoint tjänstadministratörsroll *till belindan \@ contoso.com konto:*
  
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

Använd de här kommandona för att visa listan med användarnamn för en specifik administratörsroll.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med att använda ett globalt administratörskonto [för att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>För en enda rolländring

De vanligaste sätten att ange användarkontot är med hjälp av visningsnamnet eller dess e-postnamn, som också kallas dess inloggningsnamn eller huvudnamn (UPN).

#### <a name="display-names-of-user-accounts"></a>Visa namn på användarkonton

Om du är van vid att arbeta med visningsnamnen för användarkonton bestämmer du följande information:
  
- Det användarkonto som du vill konfigurera
    
    Om du vill ange användarkontot måste du avgöra dess visningsnamn. Använd det här kommandot för att få en fullständig lista över konton:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot visar visningsnamnet för dina användarkonton, sorterade efter visningsnamnet, en skärmbild i taget. Du kan filtrera listan till en  mindre uppsättning med hjälp av cmdleten Where. Se följande exempel.

   >[!Note]
   >PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet. Kör dessa cmdlets från Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Det här kommandot visar endast användarkonton som visningsnamnet börjar på "John" för.
    
- Den roll som du vill tilldela
    
    Använd det här kommandot för att visa listan med tillgängliga administratörsroller som du kan tilldela användarkonton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har avgöra visningsnamnet för kontot och namnet på rollen använder du följande kommandon för att tilldela rollen till kontot:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Klistra in kommandona i Anteckningar. Ersätt *$dispName $roleName* *beskrivningstexten* med deras värden för variablerna. Ta bort \< and > tecknen men behåll citattecknen. Klistra in de ändrade raderna i Microsoft Azure Active Directory för att Windows PowerShell att köra dem. Alternativt kan du använda Windows PowerShell Integrated Script Environment (ISE).
  
Här är ett exempel på en slutförd kommandouppsättning:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Inloggningsnamn på användarkonton

Om du är van att arbeta med inloggningsnamn eller UPN för användarkonton ska du fastställa följande information:
  
- Användarkontons UPN
    
    Om du inte känner till UPN kan du använda det här kommandot:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot visar UPN för dina användarkonton, sorterade efter UPN, en skärmbild i taget. Du kan  använda cmdleten Where för att filtrera listan. Här är ett exempel:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Det här kommandot visar endast användarkonton som visningsnamnet börjar på "John" för.
    
- Den roll som du vill tilldela
    
    Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela användarkonton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

När du har UPN för kontot och namnet på rollen kan du använda de här kommandona för att tilldela rollen till kontot:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopiera kommandona och klistra in dem i Anteckningar. För **$upnName** och **$roleName** variabler. Ersätt beskrivningstexten med deras värden. Ta bort \< and > tecknen men behåll citattecknen. Klistra in de ändrade raderna i Microsoft Azure Active Directory för att Windows PowerShell att köra dem. Alternativt kan du använda Windows PowerShell ISE.
  
Här är ett exempel på en slutförd kommandouppsättning:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Flera rolländringar

Bestäm följande information för flerrollsändringar:
  
- Vilka användarkonton du vill konfigurera. Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visningsnamn eller UPN-namn.
    
- Vilka roller du vill tilldela varje användarkonto. Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela användarkonton:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Skapa sedan en fil med kommaavgränsade värden (CSV) med visningsnamnet eller UPN- och rollnamnsfälten. Du kan göra det enkelt i Microsoft Excel.

Här är ett exempel för visningsnamn:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Fyll sedan i CSV-filens plats och kör resulterande kommandon i PowerShell-kommandotolken.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Här är ett exempel för UPN:er:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Fyll sedan i CSV-filens plats och kör resulterande kommandon i PowerShell-kommandotolken.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Se även

- [Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)