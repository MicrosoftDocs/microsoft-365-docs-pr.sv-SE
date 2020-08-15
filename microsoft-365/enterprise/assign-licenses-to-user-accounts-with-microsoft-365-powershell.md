---
title: Tilldela Microsoft 365-licenser till användar konton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: I den här artikeln lär du dig hur du använder PowerShell till att tilldela en Microsoft 365-licens till olicensierade användare.
ms.openlocfilehash: 7bd217dfeed762a11161c3f512fb55a8e6c4968e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694363"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="3c756-103">Tilldela Microsoft 365-licenser till användar konton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c756-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="3c756-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3c756-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3c756-105">Användare kan inte använda några Microsoft 365-tjänster förrän deras konto har tilldelats en licens från en licens plan.</span><span class="sxs-lookup"><span data-stu-id="3c756-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="3c756-106">Du kan använda PowerShell för att snabbt tilldela licenser till olicensierade konton.</span><span class="sxs-lookup"><span data-stu-id="3c756-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

>[!Note]
><span data-ttu-id="3c756-107">Användar konton måste tilldelas en plats.</span><span class="sxs-lookup"><span data-stu-id="3c756-107">User accounts must be assigned a location.</span></span> <span data-ttu-id="3c756-108">Du kan göra detta från egenskaperna för ett användar konto i Microsoft 365 Admin Center eller från PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c756-108">You can do this from the properties of a user account in the Microsoft 365 admin center or from PowerShell.</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3c756-109">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="3c756-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3c756-110">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3c756-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="3c756-111">Sedan visar du licens abonnemang för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="3c756-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3c756-112">Sedan hämtar du inloggnings namnet för det konto som du vill lägga till en licens för och det kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="3c756-112">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3c756-113">Se sedan till att användar kontot har tilldelats en användnings plats.</span><span class="sxs-lookup"><span data-stu-id="3c756-113">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="3c756-114">Om det inte finns någon användnings plats kan du tilldela en med dessa kommandon:</span><span class="sxs-lookup"><span data-stu-id="3c756-114">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="3c756-115">Ange slutligen användar inloggnings namn och namn på en licens och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="3c756-115">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3c756-116">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c756-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3c756-117">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3c756-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="3c756-118">Kör `Get-MsolAccountSku` kommandot för att visa tillgängliga licens planer och antalet tillgängliga licenser för varje plan i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c756-118">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="3c756-119">Antalet tillgängliga licenser för varje abonnemang är **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="3c756-119">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="3c756-120">Mer information om licens planer, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3c756-120">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="3c756-121">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="3c756-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="3c756-122">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c756-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="3c756-123">Kör det här kommandot för att hitta de olicensierade kontona i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c756-123">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="3c756-124">Du kan bara tilldela licenser till användar konton som har egenskapen **UsageLocation** inställd på en giltig ISO 3166-1 alpha-2-landskod.</span><span class="sxs-lookup"><span data-stu-id="3c756-124">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="3c756-125">Till exempel för USA och FR för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="3c756-125">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="3c756-126">Vissa Microsoft 365-tjänster är inte tillgängliga i vissa länder.</span><span class="sxs-lookup"><span data-stu-id="3c756-126">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="3c756-127">Mer information finns i [om licens begränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="3c756-127">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="3c756-128">Kör det här kommandot för att hitta konton som inte har något **UsageLocation** -värde.</span><span class="sxs-lookup"><span data-stu-id="3c756-128">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="3c756-129">Om du vill ange **UsageLocation** -värdet för ett konto kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="3c756-129">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="3c756-130">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="3c756-130">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="3c756-131">Om du använder cmdleten **Get-MsolUser** utan att använda parametern **-all** returneras bara de första 500-kontona.</span><span class="sxs-lookup"><span data-stu-id="3c756-131">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="3c756-132">Tilldela licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="3c756-132">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="3c756-133">Om du vill tilldela en licens till en användare använder du följande kommando i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c756-133">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="3c756-134">I det här exemplet tilldelas en licens från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3)-licens plan till den olicensierade användaren \*\* \@ litwareinc.com\*\*:</span><span class="sxs-lookup"><span data-stu-id="3c756-134">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3c756-135">Om du vill tilldela en licens till alla olicensierade användare kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="3c756-135">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="3c756-136">Du kan inte tilldela flera licenser till en användare från samma licens plan.</span><span class="sxs-lookup"><span data-stu-id="3c756-136">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="3c756-137">Om du inte har tillräckligt med licenser är de tilldelade till användarna i den ordning som de returneras av cmdleten **Get-MsolUser** tills de tillgängliga licenserna tar slut.</span><span class="sxs-lookup"><span data-stu-id="3c756-137">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="3c756-138">I det här exemplet tilldelas licenser från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) till alla olicensierade användare:</span><span class="sxs-lookup"><span data-stu-id="3c756-138">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3c756-139">I det här exemplet tilldelas dessa licenser till olicensierade användare på försäljnings avdelningen i USA:</span><span class="sxs-lookup"><span data-stu-id="3c756-139">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3c756-140">Flytta en användare till ett annat abonnemang (licens plan) med Azure Active Directory PowerShell för Graph</span><span class="sxs-lookup"><span data-stu-id="3c756-140">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3c756-141">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3c756-141">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="3c756-142">Sedan hämtar du inloggnings namnet för det användar konto som du vill byta abonnemang för och det kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="3c756-142">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3c756-143">Sedan visar du abonnemangen (licens planerna) för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="3c756-143">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3c756-144">Sedan visar du de abonnemang som användar kontot för närvarande har med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="3c756-144">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="3c756-145">Identifiera den prenumeration som användaren för närvarande har (från-prenumerationen) och det abonnemang som användaren flyttar (till-abonnemanget).</span><span class="sxs-lookup"><span data-stu-id="3c756-145">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="3c756-146">Ange slutligen till och från prenumerations namnen (SKU-artikelnummer) och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="3c756-146">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="3c756-147">Du kan kontrol lera prenumerationens ändring för användar kontot med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="3c756-147">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="3c756-148">Se även</span><span class="sxs-lookup"><span data-stu-id="3c756-148">See also</span></span>

[<span data-ttu-id="3c756-149">Hantera användar konton, licenser och grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c756-149">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3c756-150">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c756-150">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3c756-151">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c756-151">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
