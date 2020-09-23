---
title: Ta bort Microsoft 365-användarkonton med PowerShell
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: I den här artikeln lär du dig hur du använder olika moduler i PowerShell för att ta bort Microsoft 365-användarkonton.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235448"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="53cc0-103">Ta bort Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="53cc0-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="53cc0-104">Du kan använda PowerShell för Microsoft 365 för att ta bort och återställa ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="53cc0-104">You can use PowerShell for Microsoft 365 to delete and restore a user account.</span></span>

>[!Note]
><span data-ttu-id="53cc0-105">[Lär dig hur du återställer ett användar konto](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) med administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53cc0-105">[Learn how to restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="53cc0-106">En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="53cc0-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="53cc0-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="53cc0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="53cc0-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="53cc0-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="53cc0-109">När du har anslutit kan du använda följande syntax för att ta bort ett enskilt användar konto:</span><span class="sxs-lookup"><span data-stu-id="53cc0-109">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="53cc0-110">Det här exemplet tar bort användar kontots fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="53cc0-110">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="53cc0-111">Parametern **-ObjectID** i cmdleten **Remove-AzureADUser** accepterar antingen kontots inloggnings namn, kallas även för användarens huvud namn, eller kontots objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="53cc0-111">The **-ObjectID** parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="53cc0-112">Använd följande kommandon för att Visa konto namnet baserat på användarens namn:</span><span class="sxs-lookup"><span data-stu-id="53cc0-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="53cc0-113">I det här exemplet visas konto namnet för den användare som heter Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="53cc0-113">This example displays the account name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="53cc0-114">Om du vill ta bort ett konto baserat på användarens visnings namn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="53cc0-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="53cc0-115">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53cc0-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="53cc0-116">När du tar bort ett användar konto med Microsoft Azure Active Directory-modulen för Windows PowerShell tas kontot inte bort permanent.</span><span class="sxs-lookup"><span data-stu-id="53cc0-116">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="53cc0-117">Du kan återställa det borttagna användar kontot inom 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="53cc0-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="53cc0-118">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="53cc0-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="53cc0-119">Använd följande syntax för att ta bort ett användar konto:</span><span class="sxs-lookup"><span data-stu-id="53cc0-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="53cc0-120">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="53cc0-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="53cc0-121">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53cc0-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="53cc0-122">Det här exemplet tar bort användar kontots BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="53cc0-122">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="53cc0-123">Om du vill återställa ett borttaget användar konto inom 30 dagar kan du använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="53cc0-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="53cc0-124">Det här exemplet återställer det borttagna kontot BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="53cc0-124">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="53cc0-125">**Kommentarer:**</span><span class="sxs-lookup"><span data-stu-id="53cc0-125">**Notes:**</span></span>
  
- <span data-ttu-id="53cc0-126">Om du vill visa listan med borttagna användare som kan återställas kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="53cc0-126">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="53cc0-127">Om användar kontots ursprungliga användar namn används av ett annat konto kan du använda parametern _NewUserPrincipalName_ i stället för _userPrincipalName_ för att ange ett annat huvud namn när du återställer användar kontot.</span><span class="sxs-lookup"><span data-stu-id="53cc0-127">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="53cc0-128">Se även</span><span class="sxs-lookup"><span data-stu-id="53cc0-128">See also</span></span>

[<span data-ttu-id="53cc0-129">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="53cc0-129">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="53cc0-130">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="53cc0-130">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="53cc0-131">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="53cc0-131">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
