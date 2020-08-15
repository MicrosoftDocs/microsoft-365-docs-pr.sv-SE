---
title: Ta bort Microsoft 365-licenser från användar konton med PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Förklarar hur du använder PowerShell för att ta bort Microsoft 365-licenser som tidigare tilldelats till användare.
ms.openlocfilehash: 815b2290ca3b5ac4ee3cfec87383161ea70f3dca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694404"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="4fb29-103">Ta bort Microsoft 365-licenser från användar konton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="4fb29-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4fb29-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4fb29-105">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="4fb29-105">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4fb29-106">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4fb29-106">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="4fb29-107">Sedan visar du licens abonnemang för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="4fb29-107">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="4fb29-108">Sedan hämtar du inloggnings namnet för det konto som du vill ta bort en licens för, även kallat UPN-namnet.</span><span class="sxs-lookup"><span data-stu-id="4fb29-108">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="4fb29-109">Ange slutligen användar namn för inloggning och licens plan för att ta bort tecknen "<" och ">" och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="4fb29-109">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="4fb29-110">Om du vill ta bort alla licenser för ett visst användar konto anger du användarens inloggnings namn, tar bort tecknen "<" och ">" och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="4fb29-110">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4fb29-111">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-111">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4fb29-112">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4fb29-112">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="4fb29-113">Information om hur du visar**AccountSkuID**-informationen i organisationen finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="4fb29-113">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="4fb29-114">Visa licenser och tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-114">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="4fb29-115">Visa information om konto licenser och tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-115">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="4fb29-116">Om du använder cmdleten **Get-MsolUser** utan att använda parametern _-all_ returneras bara de första 500-kontona.</span><span class="sxs-lookup"><span data-stu-id="4fb29-116">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="4fb29-117">Ta bort licenser från användar konton</span><span class="sxs-lookup"><span data-stu-id="4fb29-117">Removing licenses from user accounts</span></span>

<span data-ttu-id="4fb29-118">Om du vill ta bort licenser från ett befintligt användar konto använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="4fb29-118">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="4fb29-119">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="4fb29-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4fb29-120">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fb29-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="4fb29-121">I det här exemplet tas licensen **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) bort från användar kontot BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4fb29-121">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="4fb29-122">Du kan inte använda `Set-MsolUserLicense` cmdleten för att koppla bort användare från *avbrutna* licenser.</span><span class="sxs-lookup"><span data-stu-id="4fb29-122">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="4fb29-123">Du måste göra detta individuellt för varje användar konto i Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4fb29-123">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="4fb29-124">Använd någon av följande metoder för att ta bort alla licenser från en grupp med befintliga licensierade användare:</span><span class="sxs-lookup"><span data-stu-id="4fb29-124">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="4fb29-125">**Filtrera konton baserat på ett befintligt konto-attribut** Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="4fb29-125">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="4fb29-126">I det här exemplet tas alla licenser bort från alla användar konton i USA.</span><span class="sxs-lookup"><span data-stu-id="4fb29-126">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="4fb29-127">**Använda en lista över specifika konton för en viss licens** Gör så här:</span><span class="sxs-lookup"><span data-stu-id="4fb29-127">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="4fb29-128">Skapa och spara en textfil som innehåller ett konto på varje rad, så här:</span><span class="sxs-lookup"><span data-stu-id="4fb29-128">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="4fb29-129">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="4fb29-129">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="4fb29-130">I det här exemplet tas licensen för **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) bort från användar kontona i text filen c:\Mina Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="4fb29-130">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="4fb29-131">Använd följande syntax för att ta bort alla licenser från alla befintliga användar konton:</span><span class="sxs-lookup"><span data-stu-id="4fb29-131">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="4fb29-132">Ett annat sätt att frigöra en licens är genom att ta bort användar kontot.</span><span class="sxs-lookup"><span data-stu-id="4fb29-132">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="4fb29-133">Mer information finns i [ta bort och återställa användar konton med PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4fb29-133">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4fb29-134">Se även</span><span class="sxs-lookup"><span data-stu-id="4fb29-134">See also</span></span>

[<span data-ttu-id="4fb29-135">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4fb29-136">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fb29-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4fb29-137">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4fb29-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

