---
title: Ta bort Microsoft 365-licenser från användarkonton med PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Här förklaras hur du använder PowerShell för att ta bort Microsoft 365-licenser som tidigare har tilldelats användare.
ms.openlocfilehash: 8ae7ca1013e26a60f16177f2dab7ced4cc8b97a8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289599"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="13a18-103">Ta bort Microsoft 365-licenser från användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="13a18-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="13a18-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="13a18-105">[Lär dig hur du tar bort licenser från användarkonton](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) med administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13a18-105">[Learn how to remove licenses from user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="13a18-106">En lista över ytterligare resurser finns i [Hantera användare och grupper.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="13a18-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="13a18-107">Använda Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="13a18-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="13a18-108">Anslut först [till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="13a18-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="13a18-109">Lista sedan licensplanerna för innehavaren med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="13a18-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="13a18-110">Hämta sedan inloggningsnamnet för det konto för vilket du vill ta bort en licens, som även kallas UPN (user principal name).</span><span class="sxs-lookup"><span data-stu-id="13a18-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="13a18-111">Slutligen anger du namnen på användarens inloggnings- och licensabonnemang, tar bort tecknen "<" och ">" och kör de här kommandona.</span><span class="sxs-lookup"><span data-stu-id="13a18-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="13a18-112">Om du vill ta bort alla licenser för ett visst användarkonto anger du användarens inloggningsnamn, tar bort tecknen "<" och ">" och kör kommandona.</span><span class="sxs-lookup"><span data-stu-id="13a18-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="13a18-113">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="13a18-114">Anslut först [till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="13a18-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="13a18-115">Du kan visa licensplanen **(AccountSkuID)** i din organisation i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="13a18-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="13a18-116">Visa licenser och tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="13a18-117">Visa kontolicens och tjänstinformation med PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="13a18-118">Om du använder **cmdleten Get-MsolUser** utan att använda parametern _-All_ returneras bara de första 500 kontona.</span><span class="sxs-lookup"><span data-stu-id="13a18-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="13a18-119">Ta bort licenser från användarkonton</span><span class="sxs-lookup"><span data-stu-id="13a18-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="13a18-120">Om du vill ta bort licenser från ett befintligt användarkonto använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="13a18-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="13a18-121">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="13a18-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="13a18-122">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13a18-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="13a18-123">I det här exemplet tas **licensen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise, E3) bort från användarkontots BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="13a18-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="13a18-124">Du kan inte använda `Set-MsolUserLicense` cmdleten för att ta bort tilldelning av användare *från avbeställt* licenser.</span><span class="sxs-lookup"><span data-stu-id="13a18-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="13a18-125">Du måste göra det individuellt för varje användarkonto i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13a18-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="13a18-126">Om du vill ta bort alla licenser från en grupp av befintliga licensierade användare använder du någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="13a18-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="13a18-127">**Filtrera kontona baserat på ett befintligt kontoattribut** Det gör du genom att använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="13a18-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="13a18-128">I det här exemplet tas alla licenser bort från alla användarkonton i försäljningsavdelningen i USA.</span><span class="sxs-lookup"><span data-stu-id="13a18-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="13a18-129">**Använda en lista med specifika konton för en viss licens** Gör så här:</span><span class="sxs-lookup"><span data-stu-id="13a18-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="13a18-130">Skapa och spara en textfil som innehåller ett konto på varje rad så här:</span><span class="sxs-lookup"><span data-stu-id="13a18-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="13a18-131">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="13a18-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="13a18-132">I det här exemplet tas **licensen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise, E3) bort från de användarkonton som definierats i textfilen C:\My Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="13a18-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="13a18-133">Om du vill ta bort alla licenser från alla befintliga användarkonton använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="13a18-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="13a18-134">Ett annat sätt att frigöra en licens är att ta bort användarkontot.</span><span class="sxs-lookup"><span data-stu-id="13a18-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="13a18-135">Mer information finns i Ta [bort och återställa användarkonton med PowerShell.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="13a18-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13a18-136">Se även</span><span class="sxs-lookup"><span data-stu-id="13a18-136">See also</span></span>

[<span data-ttu-id="13a18-137">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="13a18-138">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a18-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="13a18-139">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13a18-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

