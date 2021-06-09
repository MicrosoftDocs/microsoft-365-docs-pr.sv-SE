---
title: Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: I den här artikeln får du lära dig hur du använder PowerShell för att inaktivera åtkomst Microsoft 365 tjänster för användare.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694542"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="649df-103">Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="649df-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="649df-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="649df-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="649df-105">När ett Microsoft 365-konto tilldelas en licens från en licensplan blir Microsoft 365 tillgängliga för användaren från den licensen.</span><span class="sxs-lookup"><span data-stu-id="649df-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="649df-106">Du kan dock styra vilka Microsoft 365 som användaren kan komma åt.</span><span class="sxs-lookup"><span data-stu-id="649df-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="649df-107">Även om licensen till exempel ger åtkomst till SharePoint Online-tjänsten kan du inaktivera åtkomsten till den.</span><span class="sxs-lookup"><span data-stu-id="649df-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="649df-108">Du kan använda PowerShell för att inaktivera åtkomst till valbara antal tjänster för en specifik licensplan för:</span><span class="sxs-lookup"><span data-stu-id="649df-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="649df-109">Ett enskilt konto.</span><span class="sxs-lookup"><span data-stu-id="649df-109">An individual account.</span></span>
- <span data-ttu-id="649df-110">En grupp konton.</span><span class="sxs-lookup"><span data-stu-id="649df-110">A group of accounts.</span></span>
- <span data-ttu-id="649df-111">Alla konton i organisationen.</span><span class="sxs-lookup"><span data-stu-id="649df-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="649df-112">Det finns Microsoft 365 tjänstberoenden som kan hindra dig från att inaktivera en viss tjänst när andra tjänster är beroende av den.</span><span class="sxs-lookup"><span data-stu-id="649df-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="649df-113">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="649df-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="649df-114">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="649df-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="649df-115">Använd sedan det här kommandot för att visa dina tillgängliga licensplaner, så kallade AccountSkuIds:</span><span class="sxs-lookup"><span data-stu-id="649df-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="649df-116">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="649df-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="649df-117">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="649df-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="649df-118">Mer information finns i [Visa licenser och tjänster med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="649df-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="649df-119">Information om hur du visar resultatet av procedurerna före och efter i det här avsnittet finns i [Visa kontolicens och tjänstinformation med PowerShell.](view-account-license-and-service-details-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="649df-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="649df-120">Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="649df-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="649df-121">Med skriptet kan du visa och inaktivera tjänster i din organisation Microsoft 365, inklusive Sway.</span><span class="sxs-lookup"><span data-stu-id="649df-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="649df-122">Mer information finns i Inaktivera [åtkomst till Sway med PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="649df-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="649df-123">Inaktivera specifika Microsoft 365 för specifika användare för ett visst licensabonnemang</span><span class="sxs-lookup"><span data-stu-id="649df-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="649df-124">Gör så här om du vill inaktivera Microsoft 365 specifika användartjänster för en specifik licensplan:</span><span class="sxs-lookup"><span data-stu-id="649df-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="649df-125">Steg 1: Identifiera de oönskade tjänsterna i licensplanen genom att använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="649df-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="649df-126">I följande exempel skapas ett **LicenseOptions-objekt** som inaktiverar Office och SharePoint Online-tjänsterna i licensplanen med namnet `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="649df-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="649df-127">Steg 2: Använd **objektet LicenseOptions** från steg 1 för en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="649df-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="649df-128">Om du vill skapa ett nytt konto där tjänsterna är inaktiverade använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="649df-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="649df-129">I följande exempel skapas ett nytt konto för Allie Bellew som tilldelar licensen och inaktiverar tjänsterna som beskrivs i steg 1.</span><span class="sxs-lookup"><span data-stu-id="649df-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="649df-130">Mer information om hur du skapar användarkonton i PowerShell för Microsoft 365 finns i [Skapa användarkonton med PowerShell.](create-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="649df-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="649df-131">Om du vill inaktivera tjänsterna för en befintlig licensierad användare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="649df-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="649df-132">Det här exemplet inaktiverar tjänsterna för användaren BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="649df-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="649df-133">Om du vill inaktivera tjänsterna som beskrivs i steg 1 för alla befintliga licensierade användare anger du namnet på ditt Microsoft 365-abonnemang från visningen av **Get-MsolAccountSku-cmdleten** (till exempel **litwareinc:ENTERPRISEPACK)** och kör sedan följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="649df-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="649df-134">Om du använder **cmdlet:en Get-MsolUser** utan att använda parametern _Alla_ returneras bara de första 500 användarkontona.</span><span class="sxs-lookup"><span data-stu-id="649df-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="649df-135">Om du vill inaktivera tjänsterna för en grupp av befintliga användare använder du någon av följande metoder för att identifiera användarna:</span><span class="sxs-lookup"><span data-stu-id="649df-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="649df-136">**Metod 1. Filtrera kontona baserat på ett befintligt kontoattribut**</span><span class="sxs-lookup"><span data-stu-id="649df-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="649df-137">Det gör du genom att använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="649df-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="649df-138">I följande exempel inaktiveras tjänsterna för användare i försäljningsavdelningen i USA.</span><span class="sxs-lookup"><span data-stu-id="649df-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="649df-139">**Metod 2: Använd en lista med specifika konton**</span><span class="sxs-lookup"><span data-stu-id="649df-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="649df-140">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="649df-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="649df-141">Skapa en textfil som innehåller ett konto på varje rad så här:</span><span class="sxs-lookup"><span data-stu-id="649df-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="649df-142">I det här exemplet är textfilen C: \\ Mina dokument \\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="649df-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="649df-143">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="649df-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="649df-144">Om du vill inaktivera åtkomst till tjänster för flera licensabonnemang upprepar du anvisningarna ovan för varje licensplan och ser till att:</span><span class="sxs-lookup"><span data-stu-id="649df-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="649df-145">Användarkontona har tilldelats licensplanen.</span><span class="sxs-lookup"><span data-stu-id="649df-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="649df-146">De tjänster som du inaktiverar finns tillgängliga i licensplanen.</span><span class="sxs-lookup"><span data-stu-id="649df-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="649df-147">Om du Microsoft 365 tjänster för användare medan du tilldelar dem till en licensplan kan du gå till Inaktivera åtkomst till tjänster medan [du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="649df-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="649df-148">Tilldela alla tjänster i en licensplan till ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="649df-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="649df-149">För användarkonton som har inaktiverat tjänster kan du aktivera alla tjänster för en specifik licensplan med följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="649df-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="649df-150">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="649df-150">Related topic</span></span>

[<span data-ttu-id="649df-151">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="649df-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="649df-152">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="649df-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="649df-153">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="649df-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
