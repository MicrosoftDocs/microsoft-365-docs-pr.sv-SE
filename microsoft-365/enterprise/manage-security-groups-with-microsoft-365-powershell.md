---
title: Hantera säkerhets grupper med PowerShell
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
description: Lär dig hur du använder PowerShell för att hantera säkerhets grupper.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073249"
---
# <a name="manage-security-groups-with-powershell"></a>Hantera säkerhets grupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att hantera säkerhets grupper. 

I den här artikeln beskrivs hur du skapar, ändrar inställningar och tar bort säkerhets grupper. 

När ett kommando block i den här artikeln kräver att du anger variabel värden följer du de här stegen.

1. Kopiera kommando blocket till Urklipp och klistra in det i anteckningar eller PowerShell ISE (Integrated script Environment).
2. Fyll i de variabla värdena och ta bort tecknen "<" och ">".
3. Kör kommandona i PowerShell-fönstret eller PowerShell ISE.

Se [Underhåll medlemskap i säkerhets grupper](maintain-group-membership-with-microsoft-365-powershell.md) för att hantera grupp medlemskap med PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Lista dina grupper

Använd det här kommandot för att lista alla dina grupper.

```powershell
Get-AzureADGroup
```
Använd dessa kommandon för att visa inställningarna för en viss grupp med dess visnings namn.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Skapa en ny grupp

Använd det här kommandot för att skapa en ny säkerhets grupp.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändra inställningarna för en grupp

Visa inställningarna för gruppen med dessa kommandon.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Använd sedan [AzureADGroup-](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) artikeln för att avgöra hur du ska ändra en inställning.

### <a name="remove-a-security-group"></a>Ta bort en säkerhets grupp

Använd dessa kommandon för att ta bort en säkerhets grupp.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Hantera ägarna till en säkerhets grupp

Använd dessa kommandon för att visa de nuvarande ägarna till en säkerhets grupp.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Använd dessa kommandon för att lägga till ett användar konto genom dess **huvud namn (UPN)** till de nuvarande ägarna till en säkerhets grupp.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Använd de här kommandona för att lägga till ett användar konto efter dess **visnings namn** för de nuvarande ägarna till en säkerhets grupp.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Använd dessa kommandon för att ta bort ett användar konto med dess **UPN** till de nuvarande ägarna till en säkerhets grupp.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Använd dessa kommandon för att ta bort ett användar konto med dess **visnings namn** till de nuvarande ägarna till en säkerhets grupp.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Lista dina grupper

Använd det här kommandot för att lista alla dina grupper.

```powershell
Get-MsolGroup
```
Använd dessa kommandon för att visa inställningarna för en viss grupp med dess visnings namn.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Skapa en ny grupp

Använd det här kommandot för att skapa en ny säkerhets grupp.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Ändra inställningarna för en grupp

Visa inställningarna för gruppen med dessa kommandon.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Använd sedan [MsolGroup-](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) artikeln för att avgöra hur du ska ändra en inställning.

### <a name="remove-a-security-group"></a>Ta bort en säkerhets grupp

Använd dessa kommandon för att ta bort en säkerhets grupp.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

