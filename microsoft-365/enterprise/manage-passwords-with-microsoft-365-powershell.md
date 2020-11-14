---
title: Hantera lösen ord med PowerShell
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
description: Lär dig hur du använder PowerShell för att hantera lösen ord.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073244"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="869fd-103">Hantera lösen ord med PowerShell</span><span class="sxs-lookup"><span data-stu-id="869fd-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="869fd-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="869fd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="869fd-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrations centret för Microsoft 365 för att hantera lösen ord i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="869fd-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="869fd-106">När ett kommando block i den här artikeln kräver att du anger variabel värden följer du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="869fd-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="869fd-107">Kopiera kommando blocket till Urklipp och klistra in det i anteckningar eller PowerShell ISE (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="869fd-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="869fd-108">Fyll i de variabla värdena och ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="869fd-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="869fd-109">Kör kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="869fd-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="869fd-110">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="869fd-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="869fd-111">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="869fd-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="869fd-112">Ange ett lösen ord</span><span class="sxs-lookup"><span data-stu-id="869fd-112">Set a password</span></span>

<span data-ttu-id="869fd-113">Använd dessa kommandon för att ange ett lösen ord för ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="869fd-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="869fd-114">Tvinga en användare att ändra sitt lösen ord</span><span class="sxs-lookup"><span data-stu-id="869fd-114">Force a user to change their password</span></span>

<span data-ttu-id="869fd-115">Använd dessa kommandon för att ange ett lösen ord och tvinga en användare att ändra sitt nya lösen ord.</span><span class="sxs-lookup"><span data-stu-id="869fd-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="869fd-116">Använd dessa kommandon för att ange ett lösen ord och tvinga en användare att ändra sitt nya lösen ord nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="869fd-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="869fd-117">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="869fd-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="869fd-118">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="869fd-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="869fd-119">Ange ett lösen ord</span><span class="sxs-lookup"><span data-stu-id="869fd-119">Set a password</span></span>

<span data-ttu-id="869fd-120">Använd dessa kommandon för att ange ett lösen ord för ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="869fd-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="869fd-121">Tvinga en användare att ändra sitt lösen ord</span><span class="sxs-lookup"><span data-stu-id="869fd-121">Force a user to change their password</span></span>

<span data-ttu-id="869fd-122">Använd dessa kommandon för att tvinga en användare att ändra sitt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="869fd-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="869fd-123">Se även</span><span class="sxs-lookup"><span data-stu-id="869fd-123">See also</span></span>

[<span data-ttu-id="869fd-124">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="869fd-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="869fd-125">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="869fd-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="869fd-126">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="869fd-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

