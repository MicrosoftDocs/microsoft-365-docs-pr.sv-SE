---
title: Underhåll Microsoft 365-gruppmedlemskap med PowerShell
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
ms.openlocfilehash: 7763f4275ff31f3dc26aa7fecba93e545f7c7644
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580980"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="36d25-103">Underhåll Microsoft 365-gruppmedlemskap med PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d25-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="36d25-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="36d25-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="36d25-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att behålla grupp medlemskap i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36d25-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="36d25-106">[Lär dig hur du hanterar microsoft 365-gruppmedlemskap](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) med administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36d25-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="36d25-107">En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="36d25-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="36d25-108">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="36d25-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="36d25-109">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="36d25-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="36d25-110">Lägga till eller ta bort användar konton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="36d25-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="36d25-111">**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell-integreringen (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="36d25-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-112">**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-113">**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-114">**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="36d25-115">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="36d25-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="36d25-116">Säkerhets grupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="36d25-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="36d25-117">Microsoft 365-grupper kan inte användas.</span><span class="sxs-lookup"><span data-stu-id="36d25-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="36d25-118">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="36d25-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="36d25-119">**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-120">**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="36d25-121">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d25-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="36d25-122">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="36d25-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="36d25-123">Lägga till eller ta bort användar konton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="36d25-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="36d25-124">**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-125">**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-126">**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="36d25-127">**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="36d25-128">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="36d25-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="36d25-129">Säkerhets grupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="36d25-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="36d25-130">Microsoft 365-grupper kan inte användas.</span><span class="sxs-lookup"><span data-stu-id="36d25-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="36d25-131">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="36d25-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="36d25-132">**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="36d25-133">**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="36d25-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="36d25-134">Se även</span><span class="sxs-lookup"><span data-stu-id="36d25-134">See also</span></span>

[<span data-ttu-id="36d25-135">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d25-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="36d25-136">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d25-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="36d25-137">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36d25-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

