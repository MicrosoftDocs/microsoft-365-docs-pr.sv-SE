---
title: Underhåll Microsoft 365-gruppmedlemskap med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 61bdcb96433f4f384033768debf416900a305624
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694812"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="905f3-103">Underhåll Microsoft 365-gruppmedlemskap med PowerShell</span><span class="sxs-lookup"><span data-stu-id="905f3-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="905f3-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="905f3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="905f3-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att behålla grupp medlemskap i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="905f3-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="905f3-106">Om du vill skapa PowerShell-kommandon som är klara att köra genom att ange användar konto-och grupp namn använder du den här [gruppen Microsoft Excel-arbetsbok](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span><span class="sxs-lookup"><span data-stu-id="905f3-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="905f3-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="905f3-107">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="905f3-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="905f3-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="905f3-109">Lägga till eller ta bort användar konton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="905f3-109">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="905f3-110">**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell-integreringen (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="905f3-110">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-111">**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-111">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-112">**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-112">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-113">**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-113">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="905f3-114">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="905f3-114">Add or remove groups as members of a group</span></span>

<span data-ttu-id="905f3-115">Säkerhets grupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="905f3-115">Security groups can contain other groups as members.</span></span> <span data-ttu-id="905f3-116">Microsoft 365-grupper kan inte användas.</span><span class="sxs-lookup"><span data-stu-id="905f3-116">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="905f3-117">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="905f3-117">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="905f3-118">**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-118">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-119">**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-119">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="905f3-120">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="905f3-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="905f3-121">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="905f3-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="905f3-122">Lägga till eller ta bort användar konton som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="905f3-122">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="905f3-123">**Om du vill lägga till ett användar konto från UPN**-namnet fyller du i användar KONTOts UPN-namn (till exempel: belindan@contoso.com) och gruppens visnings namn, tar bort alternativen "<" och ">" och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-123">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-124">**Om du vill lägga till ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-124">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-125">**Om du vill ta bort ett användar konto från UPN**-namnet fyller du i användar kontots UPN (exempel: belindan@contoso.com) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-125">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="905f3-126">**Om du vill ta bort ett användar konto med dess visnings namn**fyller du i användar kontots visnings namn (till exempel: Belinda Newman) och gruppens visnings namn och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-126">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="905f3-127">Lägga till eller ta bort grupper som medlemmar i en grupp</span><span class="sxs-lookup"><span data-stu-id="905f3-127">Add or remove groups as members of a group</span></span>

<span data-ttu-id="905f3-128">Säkerhets grupper kan innehålla andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="905f3-128">Security groups can contain other groups as members.</span></span> <span data-ttu-id="905f3-129">Microsoft 365-grupper kan inte användas.</span><span class="sxs-lookup"><span data-stu-id="905f3-129">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="905f3-130">Det här avsnittet innehåller PowerShell-kommandon för att lägga till eller ta bort grupper för en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="905f3-130">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="905f3-131">**Om du vill lägga till en grupp med dess visnings namn**fyller du i visnings namnet på den grupp du vill lägga till och visnings namnet på gruppen som ska innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-131">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="905f3-132">**Om du vill ta bort en grupp från visnings namnet**fyller du i visnings namnet på den grupp du vill ta bort och visnings namnet på gruppen som kommer att innehålla medlems gruppen och kör de här kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="905f3-132">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="905f3-133">Se även</span><span class="sxs-lookup"><span data-stu-id="905f3-133">See also</span></span>

[<span data-ttu-id="905f3-134">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="905f3-134">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="905f3-135">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="905f3-135">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="905f3-136">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="905f3-136">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

