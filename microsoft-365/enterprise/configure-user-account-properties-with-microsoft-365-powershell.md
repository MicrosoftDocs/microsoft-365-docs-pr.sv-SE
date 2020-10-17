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
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att konfigurera egenskaper för enskilda eller flera användar konton i din Microsoft 365-klient organisation.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580934"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="effdf-103">Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell</span><span class="sxs-lookup"><span data-stu-id="effdf-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="effdf-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="effdf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="effdf-105">Även om du kan använda administrations centret för Microsoft 365 för att konfigurera egenskaper för användar kontona för din Microsoft 365-klient organisation, kan du också använda PowerShell och göra något av följande i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="effdf-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="effdf-106">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="effdf-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="effdf-107">Om du vill konfigurera egenskaper för användar konton med Azure Active Directory PowerShell för Graph kan du använda cmdleten [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) och ange egenskaper för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="effdf-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="effdf-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="effdf-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="effdf-109">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="effdf-109">Change properties for a specific user account</span></span>

<span data-ttu-id="effdf-110">Du identifierar kontot med parametern **-ObjectID** och anger eller ändrar specifika egenskaper med ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="effdf-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="effdf-111">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="effdf-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="effdf-112">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="effdf-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="effdf-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="effdf-115">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="effdf-116">-Efter namn " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="effdf-117">-Mobil " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="effdf-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="effdf-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="effdf-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="effdf-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="effdf-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="effdf-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="effdf-121">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="effdf-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="effdf-123">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="effdf-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="effdf-124">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="effdf-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="effdf-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="effdf-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="effdf-127">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="effdf-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="effdf-128">Se [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) för ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="effdf-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) for additional parameters.</span></span>

>[!Note]
><span data-ttu-id="effdf-129">Innan du kan tilldela licenser till ett användar konto måste du tilldela en användnings plats.</span><span class="sxs-lookup"><span data-stu-id="effdf-129">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="effdf-130">Om du vill visa användar kontots huvud namn kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="effdf-130">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="effdf-131">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-131">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-132">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-132">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-133">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-133">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-134">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="effdf-134">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="effdf-135">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="effdf-135">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="effdf-136">Det här kommandot visar alla dina konton.</span><span class="sxs-lookup"><span data-stu-id="effdf-136">This command will list all of your accounts.</span></span> <span data-ttu-id="effdf-137">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) fyller du i **$username** variabel nedan (tar bort \< and > tecknen) och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="effdf-137">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="effdf-138">I det här exemplet visas användarens huvud namn för användar kontot med visnings namnet för Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="effdf-138">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="effdf-139">Genom att använda en **$UPN** variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="effdf-139">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="effdf-140">Här är ett exempel på hur du anger Belinda Newman användnings plats för Frankrike, men anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="effdf-140">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="effdf-141">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="effdf-141">Change properties for all user accounts</span></span>

<span data-ttu-id="effdf-142">Om du vill ändra egenskaper för alla användare kan du använda kombinationen cmdleten **Get-AzureADUser** och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="effdf-142">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="effdf-143">Följande exempel ändrar användnings platsen för alla användare till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="effdf-143">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="effdf-144">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-144">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-145">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-145">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-146">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="effdf-146">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="effdf-147">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="effdf-147">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="effdf-148">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda kombinationen cmdleten **Get-AzureADUser**, **WHERE**och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="effdf-148">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="effdf-149">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="effdf-149">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="effdf-150">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-150">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-151">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-151">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-152">Hitta alla användar konton som har egenskapen avdelning inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-152">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-153">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="effdf-153">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="effdf-154">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="effdf-154">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="effdf-155">Om du vill konfigurera egenskaper för användar konton med Microsoft Azure Active Directory-modulen för Windows PowerShell använder du cmdleten **set-MsolUser** och anger egenskaperna för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="effdf-155">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="effdf-156">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="effdf-156">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="effdf-157">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="effdf-157">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="effdf-158">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="effdf-158">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="effdf-159">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="effdf-159">Change properties for a specific user account</span></span>

<span data-ttu-id="effdf-160">Om du vill konfigurera egenskaper för ett visst användar konto använder du cmdleten [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaperna för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="effdf-160">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="effdf-161">Du identifierar kontot med parametern **-userPrincipalName** och anger eller ändrar specifika egenskaper med ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="effdf-161">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="effdf-162">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="effdf-162">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="effdf-163">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-163">-City "\<city name>"</span></span>
    
- <span data-ttu-id="effdf-164">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-164">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="effdf-165">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-165">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="effdf-166">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-166">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="effdf-167">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-167">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="effdf-168">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-168">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="effdf-169">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-169">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="effdf-170">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-170">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="effdf-171">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="effdf-171">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="effdf-172">-Telefonnummer " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="effdf-172">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="effdf-173">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="effdf-173">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="effdf-174">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="effdf-174">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="effdf-175">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-175">-State "\<state name>"</span></span>
    
- <span data-ttu-id="effdf-176">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="effdf-176">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="effdf-177">-Rubrik " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="effdf-177">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="effdf-178">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="effdf-178">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="effdf-179">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="effdf-179">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="effdf-180">Se [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) för ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="effdf-180">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="effdf-181">Om du vill visa användarens huvud namn för alla användare kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="effdf-181">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="effdf-182">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-182">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-183">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-183">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-184">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-184">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-185">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="effdf-185">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="effdf-186">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="effdf-186">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="effdf-187">Det här kommandot visar alla dina konton.</span><span class="sxs-lookup"><span data-stu-id="effdf-187">This command will list all of your accounts.</span></span> <span data-ttu-id="effdf-188">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) fyller du i **$username** variabel nedan (tar bort \< and > tecknen) och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="effdf-188">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="effdf-189">I det här exemplet visas användarens huvud namn för användaren som heter Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="effdf-189">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="effdf-190">Genom att använda en **$UPN** variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="effdf-190">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="effdf-191">Här är ett exempel på hur du anger Belinda Newman användnings plats för Frankrike, men anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="effdf-191">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="effdf-192">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="effdf-192">Change properties for all user accounts</span></span>

<span data-ttu-id="effdf-193">Om du vill ändra egenskaper för alla användare kan du använda kombinationen cmdleten **Get-MsolUser** och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="effdf-193">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="effdf-194">Följande exempel ändrar användnings platsen för alla användare till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="effdf-194">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="effdf-195">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-195">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-196">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-196">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-197">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="effdf-197">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="effdf-198">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="effdf-198">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="effdf-199">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda kombinationen cmdleten **Get-MsolUser**, **WHERE**och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="effdf-199">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="effdf-200">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="effdf-200">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="effdf-201">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="effdf-201">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="effdf-202">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-202">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-203">Hitta alla användar konton som har egenskapen avdelning inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="effdf-203">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="effdf-204">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="effdf-204">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>


## <a name="see-also"></a><span data-ttu-id="effdf-205">Se även</span><span class="sxs-lookup"><span data-stu-id="effdf-205">See also</span></span>

[<span data-ttu-id="effdf-206">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="effdf-206">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="effdf-207">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="effdf-207">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="effdf-208">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="effdf-208">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
