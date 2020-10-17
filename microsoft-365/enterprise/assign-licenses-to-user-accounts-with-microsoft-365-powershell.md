---
title: Tilldela Microsoft 365-licenser till användar konton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580946"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="053af-103">Tilldela Microsoft 365-licenser till användar konton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="053af-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="053af-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="053af-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="053af-105">Användare kan inte använda några Microsoft 365-tjänster förrän deras konto har tilldelats en licens från en licens plan.</span><span class="sxs-lookup"><span data-stu-id="053af-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="053af-106">Du kan använda PowerShell för att snabbt tilldela licenser till olicensierade konton.</span><span class="sxs-lookup"><span data-stu-id="053af-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="053af-107">Användar konton måste först tilldelas en plats.</span><span class="sxs-lookup"><span data-stu-id="053af-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="053af-108">Att ange en plats är en nödvändig del av att skapa ett nytt användar konto i [Microsoft 365 Admin Center](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="053af-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="053af-109">Konton som synkroniseras från lokala Active Directory Domain Services har ingen angiven plats som standard.</span><span class="sxs-lookup"><span data-stu-id="053af-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="053af-110">Du kan konfigurera en plats för dessa konton från:</span><span class="sxs-lookup"><span data-stu-id="053af-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="053af-111">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="053af-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="053af-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="053af-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="053af-113">[Azure-portalen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory**-  >  **användare** > användar konto > **profil**för  >  **kontakt information**  >  **land eller region**).</span><span class="sxs-lookup"><span data-stu-id="053af-113">The [Azure portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="053af-114">[Lär dig hur du tilldelar licenser till användar konton](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) med Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="053af-114">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="053af-115">En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="053af-115">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="053af-116">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="053af-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="053af-117">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="053af-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="053af-118">Sedan visar du licens abonnemang för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="053af-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="053af-119">Sedan hämtar du inloggnings namnet för det konto som du vill lägga till en licens för och det kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="053af-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="053af-120">Se sedan till att användar kontot har tilldelats en användnings plats.</span><span class="sxs-lookup"><span data-stu-id="053af-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="053af-121">Om det inte finns någon användnings plats kan du tilldela en med dessa kommandon:</span><span class="sxs-lookup"><span data-stu-id="053af-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="053af-122">Ange slutligen användar inloggnings namn och namn på en licens och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="053af-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="053af-123">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="053af-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="053af-124">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="053af-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="053af-125">Kör `Get-MsolAccountSku` kommandot för att visa tillgängliga licens planer och antalet tillgängliga licenser för varje plan i organisationen.</span><span class="sxs-lookup"><span data-stu-id="053af-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="053af-126">Antalet tillgängliga licenser för varje abonnemang är **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="053af-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="053af-127">Mer information om licens planer, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="053af-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="053af-128">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="053af-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="053af-129">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="053af-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="053af-130">Kör det här kommandot för att hitta de olicensierade kontona i organisationen.</span><span class="sxs-lookup"><span data-stu-id="053af-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="053af-131">Du kan bara tilldela licenser till användar konton som har egenskapen **UsageLocation** inställd på en giltig ISO 3166-1 alpha-2-landskod.</span><span class="sxs-lookup"><span data-stu-id="053af-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="053af-132">Till exempel för USA och FR för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="053af-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="053af-133">Vissa Microsoft 365-tjänster är inte tillgängliga i vissa länder.</span><span class="sxs-lookup"><span data-stu-id="053af-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="053af-134">Mer information finns i [om licens begränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="053af-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="053af-135">Kör det här kommandot för att hitta konton som inte har något **UsageLocation** -värde.</span><span class="sxs-lookup"><span data-stu-id="053af-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="053af-136">Om du vill ange **UsageLocation** -värdet för ett konto kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="053af-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="053af-137">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="053af-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="053af-138">Om du använder cmdleten **Get-MsolUser** utan att använda parametern **-all** returneras bara de första 500-kontona.</span><span class="sxs-lookup"><span data-stu-id="053af-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="053af-139">Tilldela licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="053af-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="053af-140">Om du vill tilldela en licens till en användare använder du följande kommando i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="053af-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="053af-141">I det här exemplet tilldelas en licens från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3)-licens plan till den olicensierade användaren \*\* \@ litwareinc.com\*\*:</span><span class="sxs-lookup"><span data-stu-id="053af-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="053af-142">Om du vill tilldela en licens till alla olicensierade användare kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="053af-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="053af-143">Du kan inte tilldela flera licenser till en användare från samma licens plan.</span><span class="sxs-lookup"><span data-stu-id="053af-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="053af-144">Om du inte har tillräckligt med licenser är de tilldelade till användarna i den ordning som de returneras av cmdleten **Get-MsolUser** tills de tillgängliga licenserna tar slut.</span><span class="sxs-lookup"><span data-stu-id="053af-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="053af-145">I det här exemplet tilldelas licenser från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) till alla olicensierade användare:</span><span class="sxs-lookup"><span data-stu-id="053af-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="053af-146">I det här exemplet tilldelas dessa licenser till olicensierade användare på försäljnings avdelningen i USA:</span><span class="sxs-lookup"><span data-stu-id="053af-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="053af-147">Flytta en användare till ett annat abonnemang (licens plan) med Azure Active Directory PowerShell för Graph</span><span class="sxs-lookup"><span data-stu-id="053af-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="053af-148">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="053af-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="053af-149">Sedan hämtar du inloggnings namnet för det användar konto som du vill byta abonnemang för och det kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="053af-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="053af-150">Sedan visar du abonnemangen (licens planerna) för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="053af-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="053af-151">Sedan visar du de abonnemang som användar kontot för närvarande har med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="053af-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="053af-152">Identifiera den prenumeration som användaren för närvarande har (från-prenumerationen) och det abonnemang som användaren flyttar (till-abonnemanget).</span><span class="sxs-lookup"><span data-stu-id="053af-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="053af-153">Ange slutligen till och från prenumerations namnen (SKU-artikelnummer) och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="053af-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="053af-154">Du kan kontrol lera prenumerationens ändring för användar kontot med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="053af-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="053af-155">Se även</span><span class="sxs-lookup"><span data-stu-id="053af-155">See also</span></span>

[<span data-ttu-id="053af-156">Hantera användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="053af-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="053af-157">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="053af-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="053af-158">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="053af-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
