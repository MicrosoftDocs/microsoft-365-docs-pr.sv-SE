---
title: Hantera lösenord med PowerShell
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
description: Lär dig hur du använder PowerShell för att hantera lösenord.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073244"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="0621b-103">Hantera lösenord med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0621b-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="0621b-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0621b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0621b-105">Du kan använda PowerShell för Microsoft 365 som ett alternativ till administrationscentret i Microsoft 365 för att hantera lösenord i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0621b-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="0621b-106">Använd de här stegen när ett kommandoblock i den här artikeln kräver att du anger variabelvärden.</span><span class="sxs-lookup"><span data-stu-id="0621b-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="0621b-107">Kopiera kommandoblocket till Urklipp och klistra in det i Anteckningar eller PowerShell Integrated Script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="0621b-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="0621b-108">Fyll i variabelvärdena och ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="0621b-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="0621b-109">Kör kommandona i PowerShell-fönstret eller PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="0621b-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0621b-110">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="0621b-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="0621b-111">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="0621b-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="0621b-112">Ange ett lösenord</span><span class="sxs-lookup"><span data-stu-id="0621b-112">Set a password</span></span>

<span data-ttu-id="0621b-113">Använd de här kommandona till att ange ett lösenord för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="0621b-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="0621b-114">Tvinga en användare att ändra sitt lösenord</span><span class="sxs-lookup"><span data-stu-id="0621b-114">Force a user to change their password</span></span>

<span data-ttu-id="0621b-115">Använd de här kommandona till att ange ett lösenord och tvinga en användare att ändra sitt nya lösenord.</span><span class="sxs-lookup"><span data-stu-id="0621b-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="0621b-116">Använd de här kommandona till att ange ett lösenord och tvinga en användare att ändra sitt nya lösenord nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="0621b-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0621b-117">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0621b-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0621b-118">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="0621b-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="0621b-119">Ange ett lösenord</span><span class="sxs-lookup"><span data-stu-id="0621b-119">Set a password</span></span>

<span data-ttu-id="0621b-120">Använd de här kommandona till att ange ett lösenord för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="0621b-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="0621b-121">Tvinga en användare att ändra sitt lösenord</span><span class="sxs-lookup"><span data-stu-id="0621b-121">Force a user to change their password</span></span>

<span data-ttu-id="0621b-122">Använd de här kommandona till att tvinga en användare att ändra sitt lösenord.</span><span class="sxs-lookup"><span data-stu-id="0621b-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="0621b-123">Se även</span><span class="sxs-lookup"><span data-stu-id="0621b-123">See also</span></span>

[<span data-ttu-id="0621b-124">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0621b-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0621b-125">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0621b-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0621b-126">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0621b-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

