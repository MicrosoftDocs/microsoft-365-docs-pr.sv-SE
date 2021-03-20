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
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="7ad94-103">Behålla medlemskap i säkerhetsgrupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ad94-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="7ad94-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7ad94-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7ad94-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrationscentret för Microsoft 365 för att behålla medlemskap i säkerhetsgrupper i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad94-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="7ad94-106">[Lär dig hur du behåller Microsoft 365-gruppmedlemskap](../admin/create-groups/add-or-remove-members-from-groups.md) med administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad94-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="7ad94-107">En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="7ad94-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7ad94-108">Använda Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="7ad94-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="7ad94-109">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7ad94-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="7ad94-110">Lägga till eller ta bort användarkonton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="7ad94-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="7ad94-111">Om du vill lägga till ett användarkonto via dess UPN fyller du i **UPN**(User Principal Name) för användarkontot (exempel: belindan@contoso.com) och säkerhetsgruppens visningsnamn, tar bort tecknen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell Integrated Script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="7ad94-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-112">**Om du** vill lägga till ett användarkonto med dess visningsnamn fyller du i visningsnamnet för användarkontot (exempel: Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-113">Om du vill ta bort ett användarkonto från **dess UPN** fyller du i UPN för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-114">Om **du** vill ta bort ett användarkonto med dess visningsnamn fyller du i användarkontots visningsnamn (till exempel Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="7ad94-115">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="7ad94-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="7ad94-116">Säkerhetsgrupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="7ad94-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="7ad94-117">Men Microsoft 365-grupper kan inte.</span><span class="sxs-lookup"><span data-stu-id="7ad94-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="7ad94-118">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper endast för en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7ad94-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="7ad94-119">Om du vill lägga till en grupp efter visningsnamn fyller du i visningsnamnet för gruppen som du ska lägga till, och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-120">Om **du** vill ta bort en grupp med dess visningsnamn fyller du i visningsnamnet för gruppen som du kommer att ta bort och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7ad94-121">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ad94-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7ad94-122">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7ad94-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="7ad94-123">Lägga till eller ta bort användarkonton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="7ad94-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="7ad94-124">Om du vill lägga till ett användarkonto via dess UPN fyller du i **UPN**(User Principal Name) för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn, tar bort tecknen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-125">**Om du** vill lägga till ett användarkonto med dess visningsnamn fyller du i visningsnamnet för användarkontot (exempel: Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-126">Om du vill ta bort ett användarkonto från **dess UPN** fyller du i UPN för användarkontot (exempel: belindan@contoso.com) och gruppens visningsnamn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="7ad94-127">Om **du** vill ta bort ett användarkonto med dess visningsnamn fyller du i användarkontots visningsnamn (till exempel Belinda Newman) och gruppens visningsnamn och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="7ad94-128">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="7ad94-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="7ad94-129">Säkerhetsgrupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="7ad94-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="7ad94-130">Men Microsoft 365-grupper kan inte.</span><span class="sxs-lookup"><span data-stu-id="7ad94-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="7ad94-131">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper endast för en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7ad94-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="7ad94-132">Om du vill lägga till en grupp efter visningsnamn fyller du i visningsnamnet för gruppen som du ska lägga till, och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="7ad94-133">Om **du** vill ta bort en grupp med dess visningsnamn fyller du i visningsnamnet för gruppen som du kommer att ta bort och visningsnamnet för gruppen som kommer att innehålla medlemsgruppen och kör dessa kommandon i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="7ad94-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="7ad94-134">Se även</span><span class="sxs-lookup"><span data-stu-id="7ad94-134">See also</span></span>

[<span data-ttu-id="7ad94-135">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ad94-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7ad94-136">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ad94-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7ad94-137">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ad94-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)