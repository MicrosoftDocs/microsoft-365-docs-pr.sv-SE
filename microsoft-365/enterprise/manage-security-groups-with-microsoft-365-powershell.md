---
title: Hantera säkerhetsgrupper med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Lär dig hur du använder PowerShell för att hantera säkerhetsgrupper.
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909508"
---
# <a name="manage-security-groups-with-powershell"></a>Hantera säkerhetsgrupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrationscentret för Microsoft 365 för att hantera säkerhetsgrupper. 

I den här artikeln beskrivs listning, skapande, ändring av inställningar och borttagning av säkerhetsgrupper. 

Använd de här stegen när ett kommandoblock i den här artikeln kräver att du anger variabelvärden.

1. Kopiera kommandoblocket till Urklipp och klistra in det i Anteckningar eller PowerShell Integrated Script Environment (ISE).
2. Fyll i variabelvärdena och ta bort tecknen "<" och ">".
3. Kör kommandona i PowerShell-fönstret eller PowerShell ISE.

Se [Bevara medlemskap i säkerhetsgrupper om](maintain-group-membership-with-microsoft-365-powershell.md) du vill hantera gruppmedlemskap med PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph-modulen

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="list-your-groups"></a>Lista dina grupper

Använd det här kommandot för att lista alla dina grupper.

```powershell
Get-AzureADGroup
```
Använd de här kommandona till att visa inställningarna för en viss grupp efter dess visningsnamn.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Skapa en ny grupp

Använd det här kommandot för att skapa en ny säkerhetsgrupp.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändra inställningarna för en grupp

Visa inställningarna för gruppen med dessa kommandon.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Använd sedan [Set-AzureADGroup-artikeln](/powershell/module/azuread/set-azureadgroup) för att avgöra hur du ändrar en inställning.

### <a name="remove-a-security-group"></a>Ta bort en säkerhetsgrupp

Använd de här kommandona till att ta bort en säkerhetsgrupp.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Hantera ägare till en säkerhetsgrupp

Använd de här kommandona till att visa aktuella ägare av en säkerhetsgrupp.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Använd de här kommandona till att lägga till ett användarkonto med dess huvudnamn **(UPN)** för de aktuella ägarna av en säkerhetsgrupp.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Använd dessa kommandon för att lägga till ett användarkonto **med dess visningsnamn** för de aktuella ägarna av en säkerhetsgrupp.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Använd de här kommandona till att ta bort ett användarkonto **från dess UPN** till de aktuella ägarna av en säkerhetsgrupp.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Använd de här kommandona till att ta bort ett **användarkonto med dess** visningsnamn för de aktuella ägarna av en säkerhetsgrupp.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="list-your-groups"></a>Lista dina grupper

Använd det här kommandot för att lista alla dina grupper.

```powershell
Get-MsolGroup
```
Använd de här kommandona till att visa inställningarna för en viss grupp efter dess visningsnamn.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Skapa en ny grupp

Använd det här kommandot för att skapa en ny säkerhetsgrupp.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändra inställningarna för en grupp

Visa inställningarna för gruppen med dessa kommandon.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Använd sedan artikeln [Set-MsolGroup för](/powershell/module/msonline/set-msolgroup) att avgöra hur du ändrar en inställning.

### <a name="remove-a-security-group"></a>Ta bort en säkerhetsgrupp

Använd de här kommandona till att ta bort en säkerhetsgrupp.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)