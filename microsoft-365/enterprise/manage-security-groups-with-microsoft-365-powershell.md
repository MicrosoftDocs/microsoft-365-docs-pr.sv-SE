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
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="40365-103">Hantera säkerhetsgrupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="40365-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="40365-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="40365-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="40365-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrationscentret Microsoft 365 att hantera säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="40365-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="40365-106">I den här artikeln beskrivs listning, skapande, ändring av inställningar och borttagning av säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="40365-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="40365-107">Använd de här stegen när ett kommandoblock i den här artikeln kräver att du anger variabelvärden.</span><span class="sxs-lookup"><span data-stu-id="40365-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="40365-108">Kopiera kommandoblocket till Urklipp och klistra in det i Anteckningar eller PowerShell Integrated Script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="40365-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="40365-109">Fyll i variabelvärdena och ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="40365-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="40365-110">Kör kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="40365-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="40365-111">Se [Bevara medlemskap i säkerhetsgrupper om](maintain-group-membership-with-microsoft-365-powershell.md) du vill hantera gruppmedlemskap med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40365-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="40365-112">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="40365-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="40365-113">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="40365-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="40365-114">Lista dina grupper</span><span class="sxs-lookup"><span data-stu-id="40365-114">List your groups</span></span>

<span data-ttu-id="40365-115">Använd det här kommandot för att lista alla dina grupper.</span><span class="sxs-lookup"><span data-stu-id="40365-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="40365-116">Använd de här kommandona till att visa inställningarna för en viss grupp efter dess visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="40365-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="40365-117">Skapa en ny grupp</span><span class="sxs-lookup"><span data-stu-id="40365-117">Create a new group</span></span>

<span data-ttu-id="40365-118">Använd det här kommandot för att skapa en ny säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="40365-119">Ändra inställningarna för en grupp</span><span class="sxs-lookup"><span data-stu-id="40365-119">Change the settings on a group</span></span>

<span data-ttu-id="40365-120">Visa inställningarna för gruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="40365-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="40365-121">Använd sedan [Set-AzureADGroup-artikeln](/powershell/module/azuread/set-azureadgroup) för att avgöra hur du ändrar en inställning.</span><span class="sxs-lookup"><span data-stu-id="40365-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="40365-122">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="40365-122">Remove a security group</span></span>

<span data-ttu-id="40365-123">Använd de här kommandona till att ta bort en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="40365-124">Hantera ägare till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="40365-124">Manage the owners of a security group</span></span>

<span data-ttu-id="40365-125">Använd de här kommandona till att visa aktuella ägare av en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="40365-126">Använd de här kommandona till att lägga till ett användarkonto med dess huvudnamn **(UPN)** för de aktuella ägarna av en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="40365-127">Använd dessa kommandon för att lägga till ett användarkonto **med dess visningsnamn** för de aktuella ägarna av en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="40365-128">Använd de här kommandona till att ta bort ett användarkonto **från dess UPN** till de aktuella ägarna av en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="40365-129">Använd de här kommandona till att ta bort ett **användarkonto med dess** visningsnamn för de aktuella ägarna av en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="40365-130">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40365-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="40365-131">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="40365-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="40365-132">Lista dina grupper</span><span class="sxs-lookup"><span data-stu-id="40365-132">List your groups</span></span>

<span data-ttu-id="40365-133">Använd det här kommandot för att lista alla dina grupper.</span><span class="sxs-lookup"><span data-stu-id="40365-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="40365-134">Använd de här kommandona till att visa inställningarna för en viss grupp efter dess visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="40365-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="40365-135">Skapa en ny grupp</span><span class="sxs-lookup"><span data-stu-id="40365-135">Create a new group</span></span>

<span data-ttu-id="40365-136">Använd det här kommandot för att skapa en ny säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="40365-137">Ändra inställningarna för en grupp</span><span class="sxs-lookup"><span data-stu-id="40365-137">Change the settings on a group</span></span>

<span data-ttu-id="40365-138">Visa inställningarna för gruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="40365-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="40365-139">Använd sedan artikeln [Set-MsolGroup för](/powershell/module/msonline/set-msolgroup) att avgöra hur du ändrar en inställning.</span><span class="sxs-lookup"><span data-stu-id="40365-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="40365-140">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="40365-140">Remove a security group</span></span>

<span data-ttu-id="40365-141">Använd de här kommandona till att ta bort en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="40365-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="40365-142">Se även</span><span class="sxs-lookup"><span data-stu-id="40365-142">See also</span></span>

[<span data-ttu-id="40365-143">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="40365-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="40365-144">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="40365-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="40365-145">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="40365-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)