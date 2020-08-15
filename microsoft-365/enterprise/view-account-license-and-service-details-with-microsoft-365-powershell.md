---
title: Visa Microsoft 365-konto och tjänste uppgifter med PowerShell
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
description: Förklarar hur du använder PowerShell för att kontrol lera vilka Microsoft 365-tjänster som har tilldelats till användarna.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694911"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="7c45e-103">Visa Microsoft 365-konto och tjänste uppgifter med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c45e-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="7c45e-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7c45e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7c45e-105">I Microsoft 365 ger licenser från licens planer (även kallade SKU: er eller Microsoft 365-abonnemang) åtkomst till de Microsoft 365-tjänster som är definierade för dessa abonnemang.</span><span class="sxs-lookup"><span data-stu-id="7c45e-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="7c45e-106">En användare kanske inte har till gång till alla tjänster som är tillgängliga i en licens som är tilldelad till dem.</span><span class="sxs-lookup"><span data-stu-id="7c45e-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="7c45e-107">Du kan använda PowerShell för Microsoft 365 för att visa statusen för tjänster på användar konton.</span><span class="sxs-lookup"><span data-stu-id="7c45e-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="7c45e-108">Mer information om licens planer, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="7c45e-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7c45e-109">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="7c45e-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7c45e-110">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="7c45e-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="7c45e-111">Sedan visar du licens abonnemang för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="7c45e-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="7c45e-112">Använd dessa kommandon för att lista de tjänster som är tillgängliga i varje licens plan.</span><span class="sxs-lookup"><span data-stu-id="7c45e-112">Use these commands to list the services that are available in each licensing plan.</span></span>

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

<span data-ttu-id="7c45e-113">Använd dessa kommandon för att lista de licenser som har tilldelats ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="7c45e-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7c45e-114">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c45e-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7c45e-115">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7c45e-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="7c45e-116">Kör sedan det här kommandot för att visa vilka licens abonnemang som är tillgängliga i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7c45e-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="7c45e-117">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="7c45e-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="7c45e-118">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c45e-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="7c45e-119">Kör sedan det här kommandot för att lista de tjänster som är tillgängliga i varje telefon plan och i vilken ordning de visas (index numret).</span><span class="sxs-lookup"><span data-stu-id="7c45e-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="7c45e-120">Använd det här kommandot för att lista de licenser som har tilldelats till en användare, och i vilken ordning de visas (index numret).</span><span class="sxs-lookup"><span data-stu-id="7c45e-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="7c45e-121">Visa tjänster för ett användar konto</span><span class="sxs-lookup"><span data-stu-id="7c45e-121">To view services for a user account</span></span>

<span data-ttu-id="7c45e-122">Om du vill visa alla Microsoft 365-tjänster som en användare har till gång till använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7c45e-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="7c45e-123">I det här exemplet visas de tjänster som användaren BelindaN@litwareinc.com har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="7c45e-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="7c45e-124">Då visas de tjänster som är kopplade till alla licenser som har tilldelats hennes konto.</span><span class="sxs-lookup"><span data-stu-id="7c45e-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="7c45e-125">I det här exemplet visas de tjänster som användaren BelindaN@litwareinc.com har åtkomst till från den första licens som tilldelats henne (index numret är 0).</span><span class="sxs-lookup"><span data-stu-id="7c45e-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="7c45e-126">Om du vill visa alla tjänster för en användare som har tilldelats *flera licenser*använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7c45e-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

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
 
## <a name="see-also"></a><span data-ttu-id="7c45e-127">Se även</span><span class="sxs-lookup"><span data-stu-id="7c45e-127">See also</span></span>

[<span data-ttu-id="7c45e-128">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c45e-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7c45e-129">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c45e-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7c45e-130">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c45e-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
