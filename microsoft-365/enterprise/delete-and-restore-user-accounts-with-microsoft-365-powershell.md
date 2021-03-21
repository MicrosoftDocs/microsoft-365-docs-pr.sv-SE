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
description: Lär dig hur du använder olika moduler i PowerShell för att ta bort Microsoft 365-användarkonton.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919146"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="f89cf-103">Ta bort Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f89cf-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="f89cf-104">Du kan använda PowerShell för Microsoft 365 för att ta bort och återställa användarkonton.</span><span class="sxs-lookup"><span data-stu-id="f89cf-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="f89cf-105">Lär dig hur [du återställer ett användarkonto](../admin/add-users/restore-user.md) med hjälp av administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f89cf-105">Learn how to [restore a user account](../admin/add-users/restore-user.md) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="f89cf-106">En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="f89cf-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f89cf-107">Använda Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="f89cf-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f89cf-108">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="f89cf-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="f89cf-109">När du har anslutt använder du följande syntax för att ta bort ett enskilt användarkonto:</span><span class="sxs-lookup"><span data-stu-id="f89cf-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="f89cf-110">I det här exemplet tas användarkontot *bort från \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="f89cf-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="f89cf-111">Parametern *-ObjectID* i cmdleten **Remove-AzureADUser** accepterar antingen kontots inloggningsnamn, som även kallas användarkontots huvudnamn eller kontots objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="f89cf-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="f89cf-112">Om du vill visa kontonamnet baserat på användarens namn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f89cf-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f89cf-113">I det här exemplet visas kontonamnet för *användaren Caleb Entsson.*</span><span class="sxs-lookup"><span data-stu-id="f89cf-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f89cf-114">Om du vill ta bort ett konto baserat på användarens visningsnamn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f89cf-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f89cf-115">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f89cf-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f89cf-116">När du tar bort ett användarkonto via Microsoft Azure Active Directory-modulen för Windows PowerShell tas kontot inte bort permanent.</span><span class="sxs-lookup"><span data-stu-id="f89cf-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="f89cf-117">Du kan återställa det borttagna användarkontot inom 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f89cf-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="f89cf-118">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f89cf-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="f89cf-119">Använd följande syntax för att ta bort ett användarkonto:</span><span class="sxs-lookup"><span data-stu-id="f89cf-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="f89cf-120">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="f89cf-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f89cf-121">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f89cf-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="f89cf-122">I det här exemplet tas *användarkontot* BelindaN@litwareinc.com .</span><span class="sxs-lookup"><span data-stu-id="f89cf-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="f89cf-123">Om du vill återställa ett borttagna användarkonto inom respitperioden på 30 dagar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f89cf-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="f89cf-124">I det här exemplet återställs det borttagna *kontot BelindaN \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="f89cf-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="f89cf-125">Kör följande kommando för att se en lista över borttagna användare som kan återställas:</span><span class="sxs-lookup"><span data-stu-id="f89cf-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="f89cf-126">Om användarkontots ursprungliga huvudnamn används av ett annat konto, ska du använda parametern _NewUserPrincipalName_ i stället för _UserPrincipalName_ för att ange ett annat huvudnamn när du återställer användarkontot.</span><span class="sxs-lookup"><span data-stu-id="f89cf-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="f89cf-127">Se även</span><span class="sxs-lookup"><span data-stu-id="f89cf-127">See also</span></span>

[<span data-ttu-id="f89cf-128">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f89cf-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f89cf-129">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f89cf-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f89cf-130">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f89cf-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)