---
title: Tilldela Microsoft 365 licenser till användarkonton med PowerShell
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
description: I den här artikeln får du lära dig hur du använder PowerShell för att tilldela Microsoft 365 licens till olicensierade användare.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572627"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="e0794-103">Tilldela Microsoft 365 licenser till användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0794-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="e0794-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e0794-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e0794-105">Användare kan inte använda några Microsoft 365 förrän deras konto har tilldelats en licens från en licensplan.</span><span class="sxs-lookup"><span data-stu-id="e0794-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="e0794-106">Du kan använda PowerShell för att snabbt tilldela licenser till olicensierade konton.</span><span class="sxs-lookup"><span data-stu-id="e0794-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="e0794-107">Användarkonton måste först tilldelas en plats.</span><span class="sxs-lookup"><span data-stu-id="e0794-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="e0794-108">Att ange en plats är en obligatorisk del av att skapa ett nytt användarkonto [i Microsoft 365 administrationscenter](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="e0794-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="e0794-109">Konton som synkroniserats från dina lokala Active Directory Domain Services har som standard ingen plats angiven.</span><span class="sxs-lookup"><span data-stu-id="e0794-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="e0794-110">Du kan konfigurera en plats för dessa konton från:</span><span class="sxs-lookup"><span data-stu-id="e0794-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="e0794-111">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0794-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="e0794-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0794-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="e0794-113">Azure [Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **(Active**  >  **Directory-användare** > användarkonto > **profilkontaktinformation**  >    >  **land eller region**).</span><span class="sxs-lookup"><span data-stu-id="e0794-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="e0794-114">[Lär dig hur du tilldelar licenser till användarkonton](../admin/manage/assign-licenses-to-users.md) Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e0794-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="e0794-115">En lista över ytterligare resurser finns i [Hantera användare och grupper](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="e0794-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e0794-116">Använd Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="e0794-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e0794-117">Anslut först [till din Microsoft 365 klient .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e0794-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="e0794-118">Lista sedan licensplanerna för din klient med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="e0794-119">Hämta sedan inloggningsnamnet för det konto som du vill lägga till en licens till, även kallat UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="e0794-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="e0794-120">Se sedan till att användarkontot har en användningsplats tilldelad.</span><span class="sxs-lookup"><span data-stu-id="e0794-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="e0794-121">Om ingen användningsplats har tilldelats kan du tilldela en med följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="e0794-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="e0794-122">Slutligen anger du användarens inloggningsnamn och licensplansnamn och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="e0794-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e0794-123">Använd Microsoft Azure Active Directory modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0794-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e0794-124">Observera att vi kommer att börja deprecate denna modul när funktionaliteten i denna modul är tillgänglig [i den nyare Azure Active Directory PowerShell för Graph modul.](/powershell/azuread/v2/azureactivedirectory)</span><span class="sxs-lookup"><span data-stu-id="e0794-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="e0794-125">Vi rekommenderar kunder som skapar nya PowerShell-skript att använda den nyare modulen i stället för den här modulen.</span><span class="sxs-lookup"><span data-stu-id="e0794-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="e0794-126">Anslut först [till din Microsoft 365 klient .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e0794-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="e0794-127">Kör kommandot `Get-MsolAccountSku` för att visa tillgängliga licensplaner och antalet tillgängliga licenser i varje plan i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e0794-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="e0794-128">Antalet tillgängliga licenser i varje plan är **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="e0794-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="e0794-129">Mer information om licensplaner, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e0794-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="e0794-130">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="e0794-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e0794-131">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0794-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e0794-132">Om du vill hitta de olicensierade kontona i organisationen kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="e0794-133">Du kan bara tilldela licenser till användarkonton som har **egenskapen UsageLocation** inställd på en giltig ISO 3166-1 alpha-2-landskod.</span><span class="sxs-lookup"><span data-stu-id="e0794-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="e0794-134">Till exempel USA för Förenta staterna och FR för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="e0794-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="e0794-135">Vissa Microsoft 365 tjänster är inte tillgängliga i vissa länder.</span><span class="sxs-lookup"><span data-stu-id="e0794-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="e0794-136">Mer information finns i [Om licensbegränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="e0794-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="e0794-137">Om du vill söka efter konton som inte har ett **UsageLocation-värde** kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="e0794-138">Om du vill **ange värdet UsageLocation** på ett konto kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="e0794-139">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e0794-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="e0794-140">Om du använder **cmdleten Get-MsolUser** utan att använda **parametern -All** returneras bara de första 500 kontona.</span><span class="sxs-lookup"><span data-stu-id="e0794-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="e0794-141">Tilldela licenser till användarkonton</span><span class="sxs-lookup"><span data-stu-id="e0794-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="e0794-142">Om du vill tilldela en licens till en användare använder du följande kommando i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0794-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="e0794-143">I det här exemplet tilldelas en licens från **licensplanen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) till den olicensierade användaren **litwareinc.com: \@**</span><span class="sxs-lookup"><span data-stu-id="e0794-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="e0794-144">Om du vill tilldela en licens till alla olicensierade användare kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="e0794-145">Du kan inte tilldela flera licenser till en användare från samma licensplan.</span><span class="sxs-lookup"><span data-stu-id="e0794-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="e0794-146">Om du inte har tillräckligt med tillgängliga licenser tilldelas licenserna till användare i den ordning de returneras av **Cmdleten Get-MsolUser** tills de tillgängliga licenserna tar.</span><span class="sxs-lookup"><span data-stu-id="e0794-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="e0794-147">I det här exemplet tilldelas licenser från **licensplanen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) till alla olicensierade användare:</span><span class="sxs-lookup"><span data-stu-id="e0794-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="e0794-148">I det här exemplet tilldelas samma licenser till olicensierade användare på försäljningsavdelningen i USA:</span><span class="sxs-lookup"><span data-stu-id="e0794-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e0794-149">Flytta en användare till en annan prenumeration (licensplan) med Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="e0794-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e0794-150">Anslut först [till din Microsoft 365 klient .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e0794-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e0794-151">Hämta sedan inloggningsnamnet för det användarkonto som du vill byta prenumerationer för, även kallat UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="e0794-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="e0794-152">Lista sedan prenumerationerna (licensplanerna) för din klient med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="e0794-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="e0794-153">Lista sedan de prenumerationer som användarkontot för närvarande har med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="e0794-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="e0794-154">Identifiera den prenumeration som användaren för närvarande har (FRÅN-prenumerationen) och prenumerationen som användaren flyttar till (TILL-prenumerationen).</span><span class="sxs-lookup"><span data-stu-id="e0794-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="e0794-155">Slutligen anger du till- och FRÅN-prenumerationsnamnen (SKU-artikelnummer) och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="e0794-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="e0794-156">Du kan verifiera ändringen av prenumerationen för användarkontot med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="e0794-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="e0794-157">Se även</span><span class="sxs-lookup"><span data-stu-id="e0794-157">See also</span></span>

[<span data-ttu-id="e0794-158">Hantera användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0794-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e0794-159">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0794-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e0794-160">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0794-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
