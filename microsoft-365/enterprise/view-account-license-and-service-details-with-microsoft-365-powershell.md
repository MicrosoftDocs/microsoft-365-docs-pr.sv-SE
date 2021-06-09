---
title: Visa Microsoft 365 kontolicens och tjänstinformation med PowerShell
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
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Förklarar hur du använder PowerShell för att avgöra Microsoft 365 tjänster som har tilldelats till användare.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694911"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="af7e3-103">Visa Microsoft 365 kontolicens och tjänstinformation med PowerShell</span><span class="sxs-lookup"><span data-stu-id="af7e3-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="af7e3-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="af7e3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="af7e3-105">I Microsoft 365 ger licenser från licensplaner (kallas även för SKU:er eller Microsoft 365-abonnemang) användarna åtkomst till de Microsoft 365-tjänster som är definierade för dessa abonnemang.</span><span class="sxs-lookup"><span data-stu-id="af7e3-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="af7e3-106">Men en användare kanske inte har åtkomst till alla tjänster som är tillgängliga i en licens som för närvarande är tilldelad till dem.</span><span class="sxs-lookup"><span data-stu-id="af7e3-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="af7e3-107">Du kan använda PowerShell för Microsoft 365 visa status för tjänster på användarkonton.</span><span class="sxs-lookup"><span data-stu-id="af7e3-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="af7e3-108">Mer information om licensplaner, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="af7e3-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="af7e3-109">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="af7e3-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="af7e3-110">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="af7e3-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="af7e3-111">Lista sedan licensplaner för din klientorganisation med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="af7e3-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="af7e3-112">Använd de här kommandona för att visa de tjänster som är tillgängliga i varje licensplan.</span><span class="sxs-lookup"><span data-stu-id="af7e3-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="af7e3-113">Använd de här kommandona för att visa de licenser som tilldelats ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="af7e3-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="af7e3-114">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af7e3-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="af7e3-115">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="af7e3-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="af7e3-116">Kör sedan det här kommandot för att visa de licensplaner som är tillgängliga i organisationen.</span><span class="sxs-lookup"><span data-stu-id="af7e3-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="af7e3-117">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="af7e3-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="af7e3-118">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af7e3-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="af7e3-119">Kör sedan det här kommandot för att visa de tjänster som är tillgängliga i varje licensplan och i vilken ordning de visas (indexnumret).</span><span class="sxs-lookup"><span data-stu-id="af7e3-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="af7e3-120">Använd det här kommandot för att visa de licenser som är tilldelade till en användare och i vilken ordning de visas (indexnumret).</span><span class="sxs-lookup"><span data-stu-id="af7e3-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="af7e3-121">Visa tjänster för ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="af7e3-121">To view services for a user account</span></span>

<span data-ttu-id="af7e3-122">Om du vill visa Microsoft 365 tjänster som en användare har tillgång till använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="af7e3-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="af7e3-123">Det här exemplet visar de tjänster som användaren BelindaN@litwareinc.com åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="af7e3-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="af7e3-124">Här visas de tjänster som är associerade med alla licenser som har tilldelats till hennes konto.</span><span class="sxs-lookup"><span data-stu-id="af7e3-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="af7e3-125">Det här exemplet visar de tjänster BelindaN@litwareinc.com har åtkomst till från den första licensen som har tilldelats till hennes konto (indexnumret är 0).</span><span class="sxs-lookup"><span data-stu-id="af7e3-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="af7e3-126">Om du vill visa alla tjänster för en användare som har tilldelats *flera* licenser använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="af7e3-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="af7e3-127">Se även</span><span class="sxs-lookup"><span data-stu-id="af7e3-127">See also</span></span>

[<span data-ttu-id="af7e3-128">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="af7e3-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="af7e3-129">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="af7e3-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="af7e3-130">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af7e3-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
