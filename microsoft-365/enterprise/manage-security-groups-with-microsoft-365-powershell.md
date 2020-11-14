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
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="5e340-103">Hantera säkerhets grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e340-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="5e340-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5e340-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5e340-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att hantera säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="5e340-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="5e340-106">I den här artikeln beskrivs hur du skapar, ändrar inställningar och tar bort säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="5e340-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="5e340-107">När ett kommando block i den här artikeln kräver att du anger variabel värden följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="5e340-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="5e340-108">Kopiera kommando blocket till Urklipp och klistra in det i anteckningar eller PowerShell ISE (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="5e340-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="5e340-109">Fyll i de variabla värdena och ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="5e340-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="5e340-110">Kör kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="5e340-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="5e340-111">Se [Underhåll medlemskap i säkerhets grupper](maintain-group-membership-with-microsoft-365-powershell.md) för att hantera grupp medlemskap med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e340-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5e340-112">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="5e340-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5e340-113">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5e340-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="5e340-114">Lista dina grupper</span><span class="sxs-lookup"><span data-stu-id="5e340-114">List your groups</span></span>

<span data-ttu-id="5e340-115">Använd det här kommandot för att lista alla dina grupper.</span><span class="sxs-lookup"><span data-stu-id="5e340-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="5e340-116">Använd dessa kommandon för att visa inställningarna för en viss grupp med dess visnings namn.</span><span class="sxs-lookup"><span data-stu-id="5e340-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="5e340-117">Skapa en ny grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-117">Create a new group</span></span>

<span data-ttu-id="5e340-118">Använd det här kommandot för att skapa en ny säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="5e340-119">Ändra inställningarna för en grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-119">Change the settings on a group</span></span>

<span data-ttu-id="5e340-120">Visa inställningarna för gruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="5e340-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="5e340-121">Använd sedan [AzureADGroup-](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) artikeln för att avgöra hur du ska ändra en inställning.</span><span class="sxs-lookup"><span data-stu-id="5e340-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="5e340-122">Ta bort en säkerhets grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-122">Remove a security group</span></span>

<span data-ttu-id="5e340-123">Använd dessa kommandon för att ta bort en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="5e340-124">Hantera ägarna till en säkerhets grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-124">Manage the owners of a security group</span></span>

<span data-ttu-id="5e340-125">Använd dessa kommandon för att visa de nuvarande ägarna till en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="5e340-126">Använd dessa kommandon för att lägga till ett användar konto genom dess **huvud namn (UPN)** till de nuvarande ägarna till en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="5e340-127">Använd de här kommandona för att lägga till ett användar konto efter dess **visnings namn** för de nuvarande ägarna till en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="5e340-128">Använd dessa kommandon för att ta bort ett användar konto med dess **UPN** till de nuvarande ägarna till en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="5e340-129">Använd dessa kommandon för att ta bort ett användar konto med dess **visnings namn** till de nuvarande ägarna till en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5e340-130">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e340-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5e340-131">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5e340-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="5e340-132">Lista dina grupper</span><span class="sxs-lookup"><span data-stu-id="5e340-132">List your groups</span></span>

<span data-ttu-id="5e340-133">Använd det här kommandot för att lista alla dina grupper.</span><span class="sxs-lookup"><span data-stu-id="5e340-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="5e340-134">Använd dessa kommandon för att visa inställningarna för en viss grupp med dess visnings namn.</span><span class="sxs-lookup"><span data-stu-id="5e340-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="5e340-135">Skapa en ny grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-135">Create a new group</span></span>

<span data-ttu-id="5e340-136">Använd det här kommandot för att skapa en ny säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="5e340-137">Ändra inställningarna för en grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-137">Change the settings on a group</span></span>

<span data-ttu-id="5e340-138">Visa inställningarna för gruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="5e340-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="5e340-139">Använd sedan [MsolGroup-](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) artikeln för att avgöra hur du ska ändra en inställning.</span><span class="sxs-lookup"><span data-stu-id="5e340-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="5e340-140">Ta bort en säkerhets grupp</span><span class="sxs-lookup"><span data-stu-id="5e340-140">Remove a security group</span></span>

<span data-ttu-id="5e340-141">Använd dessa kommandon för att ta bort en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="5e340-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="5e340-142">Se även</span><span class="sxs-lookup"><span data-stu-id="5e340-142">See also</span></span>

[<span data-ttu-id="5e340-143">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e340-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5e340-144">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e340-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5e340-145">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e340-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

