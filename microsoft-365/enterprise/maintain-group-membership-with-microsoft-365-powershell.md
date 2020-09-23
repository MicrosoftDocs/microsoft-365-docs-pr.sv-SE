---
title: Underhåll Microsoft 365-gruppmedlemskap med PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Lär dig hur du använder PowerShell för att behålla medlemskap i Microsoft 365-grupper.
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235636"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a>Underhåll Microsoft 365-gruppmedlemskap med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att behålla grupp medlemskap i Microsoft 365. 

> [!TIP]
> Om du vill skapa PowerShell-kommandon som är klara att köra genom att ange användar konto-och grupp namn använder du den här [gruppen Microsoft Excel-arbetsbok](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx). 

>[!Note]
>[Lär dig hur du hanterar microsoft 365-gruppmedlemskap](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) med administrations centret för Microsoft 365. En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn
Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Lägga till eller ta bort användar konton som medlemmar i en grupp

**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell-integreringen (Integrated script Environment).

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Lägga till eller ta bort grupper som medlemmar i en grupp

Säkerhets grupper kan innehålla andra grupper som medlemmar. Microsoft 365-grupper kan inte användas. Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.

**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Lägga till eller ta bort användar konton som medlemmar i en grupp

**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Lägga till eller ta bort grupper som medlemmar i en grupp

Säkerhets grupper kan innehålla andra grupper som medlemmar. Microsoft 365-grupper kan inte användas. Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.

**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

