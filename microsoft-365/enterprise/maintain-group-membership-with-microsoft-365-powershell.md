---
title: Behålla medlemskap i säkerhetsgrupper med PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Lär dig hur du använder PowerShell för att behålla medlemskap i Microsoft 365-grupper.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909580"
---
# <a name="maintain-security-group-membership-with-powershell"></a>Behålla medlemskap i säkerhetsgrupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrationscentret för Microsoft 365 för att behålla medlemskap i säkerhetsgrupper i Microsoft 365. 

>[!Note]
>[Lär dig hur du behåller Microsoft 365-gruppmedlemskap](../admin/create-groups/add-or-remove-members-from-groups.md) med administrationscentret för Microsoft 365. En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph-modulen
Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Lägga till eller ta bort användarkonton som medlemmar i en grupp

Om du vill lägga till ett användarkonto via dess UPN fyller du i **UPN**(User Principal Name) för användarkontot (exempel: belindan@contoso.com) och säkerhetsgruppens visningsnamn, tar bort tecknen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell Integrated Script Environment (ISE).

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du** vill lägga till ett användarkonto med dess visningsnamn fyller du i visningsnamnet för användarkontot (exempel: Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Om du vill ta bort ett användarkonto från **dess UPN** fyller du i UPN för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Om **du** vill ta bort ett användarkonto med dess visningsnamn fyller du i användarkontots visningsnamn (till exempel Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Lägga till eller ta bort grupper som medlemmar i en grupp

Säkerhetsgrupper kan innehålla andra grupper som medlemmar. Men Microsoft 365-grupper kan inte. Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper endast för en säkerhetsgrupp.

Om du vill lägga till en grupp efter visningsnamn fyller du i visningsnamnet för gruppen som du ska lägga till, och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Om **du** vill ta bort en grupp med dess visningsnamn fyller du i visningsnamnet för gruppen som du kommer att ta bort och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Lägga till eller ta bort användarkonton som medlemmar i en grupp

Om du vill lägga till ett användarkonto via dess UPN fyller du i **UPN**(User Principal Name) för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn, tar bort tecknen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Om du** vill lägga till ett användarkonto med dess visningsnamn fyller du i visningsnamnet för användarkontot (exempel: Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Om du vill ta bort ett användarkonto från **dess UPN** fyller du i UPN för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Om **du** vill ta bort ett användarkonto med dess visningsnamn fyller du i användarkontots visningsnamn (till exempel Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Lägga till eller ta bort grupper som medlemmar i en grupp

Säkerhetsgrupper kan innehålla andra grupper som medlemmar. Men Microsoft 365-grupper kan inte. Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper endast för en säkerhetsgrupp.

Om du vill lägga till en grupp efter visningsnamn fyller du i visningsnamnet för gruppen som du ska lägga till, och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

Om **du** vill ta bort en grupp med dess visningsnamn fyller du i visningsnamnet för gruppen som du kommer att ta bort och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)