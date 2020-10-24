---
title: Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Använd PowerShell för Microsoft 365 för att konfigurera egenskaper för enskilda eller flera användar konton i din Microsoft 365-klient organisation.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754334"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="88606-103">Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell</span><span class="sxs-lookup"><span data-stu-id="88606-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="88606-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="88606-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="88606-105">Du kan använda administrations centret för Microsoft 365 för att konfigurera egenskaper för användar konton för din Microsoft 365-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="88606-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="88606-106">I PowerShell kan du också göra det och andra saker du inte kan göra i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="88606-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="88606-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="88606-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="88606-108">Om du vill konfigurera egenskaper för användar konton i Azure Active Directory PowerShell för Graph kan du använda cmdleten [**set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) och ange egenskaper för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="88606-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="88606-109">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="88606-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="88606-110">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="88606-110">Change properties for a specific user account</span></span>

<span data-ttu-id="88606-111">Du identifierar kontot med parametern *-ObjectID* och anger eller ändrar specifika egenskaper genom att använda ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="88606-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="88606-112">Här är en lista över de vanligaste parametrarna:</span><span class="sxs-lookup"><span data-stu-id="88606-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="88606-113">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="88606-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="88606-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="88606-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="88606-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="88606-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="88606-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="88606-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="88606-117">-Efter namn " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="88606-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="88606-118">-Mobil " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="88606-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="88606-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="88606-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="88606-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="88606-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="88606-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="88606-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="88606-122">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="88606-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="88606-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="88606-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="88606-124">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="88606-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="88606-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="88606-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="88606-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="88606-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="88606-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="88606-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="88606-128">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="88606-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="88606-129">Fler parametrar finns i [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="88606-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="88606-130">Innan du kan tilldela licenser till ett användar konto måste du tilldela en användnings plats.</span><span class="sxs-lookup"><span data-stu-id="88606-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="88606-131">Om du vill visa användar kontots huvud namn kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="88606-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="88606-132">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-133">Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-134">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-135">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="88606-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="88606-136">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="88606-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="88606-137">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) kör du följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="88606-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="88606-138">Fyll i *$username* variabel och ta bort \< and > tecknen:</span><span class="sxs-lookup"><span data-stu-id="88606-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="88606-139">I det här exemplet visas användarens huvud namn för det användar konto som har visnings namnet *Caleb brädor*.</span><span class="sxs-lookup"><span data-stu-id="88606-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="88606-140">Genom att använda en *$UPN* variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="88606-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="88606-141">Här är ett exempel som anger *Belinda Newman*användnings plats för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="88606-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="88606-142">Men det anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="88606-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="88606-143">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="88606-143">Change properties for all user accounts</span></span>

<span data-ttu-id="88606-144">Om du vill ändra egenskaper för alla användare kan du använda en kombination av cmdletarna **Get-AzureADUser** och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="88606-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="88606-145">Följande exempel ändrar användnings platsen för alla användare till *Frankrike*:</span><span class="sxs-lookup"><span data-stu-id="88606-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="88606-146">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-147">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-148">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="88606-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="88606-149">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="88606-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="88606-150">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda en kombination av cmdletarna **Get-AzureADUser**, **WHERE**och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="88606-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="88606-151">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till *Frankrike*:</span><span class="sxs-lookup"><span data-stu-id="88606-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="88606-152">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-153">Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="88606-154">Hitta alla användar konton som har egenskapen *avdelning* inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-155">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="88606-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="88606-156">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88606-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="88606-157">Om du vill konfigurera egenskaper för användar konton med Microsoft Azure Active Directory-modulen för Windows PowerShell kan du använda cmdleten **set-MsolUser** och ange egenskaper för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="88606-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="88606-158">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="88606-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="88606-159">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* .</span><span class="sxs-lookup"><span data-stu-id="88606-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="88606-160">Kör dessa cmdletar från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88606-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="88606-161">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="88606-161">Change properties for a specific user account</span></span>

<span data-ttu-id="88606-162">Om du vill konfigurera egenskaper för ett specifikt användar konto använder du cmdleten [**set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaperna som ska anges eller ändras.</span><span class="sxs-lookup"><span data-stu-id="88606-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="88606-163">Du identifierar kontot med parametern *-userPrincipalName* och anger eller ändrar specifika egenskaper genom att använda ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="88606-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="88606-164">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="88606-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="88606-165">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="88606-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="88606-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="88606-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="88606-167">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="88606-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="88606-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="88606-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="88606-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="88606-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="88606-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="88606-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="88606-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="88606-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="88606-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="88606-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="88606-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="88606-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="88606-174">-Telefonnummer " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="88606-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="88606-175">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="88606-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="88606-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="88606-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="88606-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="88606-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="88606-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="88606-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="88606-179">-Rubrik " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="88606-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="88606-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="88606-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="88606-181">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="88606-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="88606-182">Fler parametrar finns i [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="88606-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="88606-183">Om du vill visa användarens huvud namn för alla användare kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="88606-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="88606-184">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-185">Få all information för användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-186">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-187">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="88606-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="88606-188">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="88606-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="88606-189">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) kör du följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="88606-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="88606-190">Fyll i *$username* variabel och ta bort \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="88606-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="88606-191">I det här exemplet visas användarens huvud namn för den användare som heter Caleb brädor:</span><span class="sxs-lookup"><span data-stu-id="88606-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="88606-192">Genom att använda en *$UPN* variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="88606-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="88606-193">Här är ett exempel som anger *Belinda Newman*användnings plats för *Frankrike*, men som anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="88606-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="88606-194">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="88606-194">Change properties for all user accounts</span></span>

<span data-ttu-id="88606-195">Om du vill ändra egenskaper för alla användare använder du en kombination av cmdletarna **Get-MsolUser** och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="88606-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="88606-196">Följande exempel ändrar användnings platsen för alla användare till *Frankrike*:</span><span class="sxs-lookup"><span data-stu-id="88606-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="88606-197">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-198">Få all information för användar kontona (**Get-MsolUser**) och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-199">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="88606-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="88606-200">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="88606-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="88606-201">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda en kombination av cmdletarna **Get-MsolUser**, **WHERE**och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="88606-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="88606-202">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till *Frankrike*:</span><span class="sxs-lookup"><span data-stu-id="88606-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="88606-203">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="88606-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="88606-204">Få all information för användar kontona (**Get-MsolUser**) och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-205">Hitta alla användar konton som har egenskapen *avdelning* inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="88606-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="88606-206">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="88606-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="88606-207">Se även</span><span class="sxs-lookup"><span data-stu-id="88606-207">See also</span></span>

[<span data-ttu-id="88606-208">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="88606-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="88606-209">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="88606-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="88606-210">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88606-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
