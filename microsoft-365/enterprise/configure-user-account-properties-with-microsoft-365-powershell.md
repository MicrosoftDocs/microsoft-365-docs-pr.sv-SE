---
title: Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694282"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="f757a-103">Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f757a-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="f757a-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f757a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f757a-105">Även om du kan använda administrations centret för Microsoft 365 för att konfigurera egenskaper för användar kontona för din Microsoft 365-klient organisation, kan du också använda PowerShell och göra något av följande i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f757a-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f757a-106">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="f757a-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f757a-107">Om du vill konfigurera egenskaper för användar konton med Azure Active Directory PowerShell för Graph kan du använda cmdleten [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) och ange egenskaper för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="f757a-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f757a-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="f757a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="f757a-109">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="f757a-109">Change properties for a specific user account</span></span>

<span data-ttu-id="f757a-110">Du identifierar kontot med parametern **-ObjectID** och anger eller ändrar specifika egenskaper med ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="f757a-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="f757a-111">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="f757a-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="f757a-112">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="f757a-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="f757a-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="f757a-115">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="f757a-116">-Efter namn " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="f757a-117">-Mobil " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="f757a-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="f757a-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="f757a-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="f757a-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="f757a-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="f757a-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="f757a-121">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="f757a-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="f757a-123">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="f757a-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="f757a-124">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="f757a-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="f757a-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="f757a-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="f757a-127">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="f757a-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="f757a-128">Se [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) för ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="f757a-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="f757a-129">Om du vill visa användar kontots huvud namn kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="f757a-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="f757a-130">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-131">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-132">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-133">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="f757a-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="f757a-134">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="f757a-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="f757a-135">Det här kommandot visar alla dina konton.</span><span class="sxs-lookup"><span data-stu-id="f757a-135">This command will list all of your accounts.</span></span> <span data-ttu-id="f757a-136">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) fyller du i **$username** variabel nedan (tar bort \< and > tecknen) och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f757a-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f757a-137">I det här exemplet visas användarens huvud namn för användar kontot med visnings namnet för Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="f757a-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f757a-138">Genom att använda en **$UPN** variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="f757a-138">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="f757a-139">Här är ett exempel på hur du anger Belinda Newman användnings plats för Frankrike, men anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="f757a-139">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="f757a-140">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="f757a-140">Change properties for all user accounts</span></span>

<span data-ttu-id="f757a-141">Om du vill ändra egenskaper för alla användare kan du använda kombinationen cmdleten **Get-AzureADUser** och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f757a-141">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="f757a-142">Följande exempel ändrar användnings platsen för alla användare till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="f757a-142">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="f757a-143">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-144">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-145">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f757a-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="f757a-146">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="f757a-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="f757a-147">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda kombinationen cmdleten **Get-AzureADUser**, **WHERE**och **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f757a-147">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="f757a-148">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="f757a-148">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="f757a-149">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-150">Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-151">Hitta alla användar konton som har egenskapen avdelning inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-152">Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f757a-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f757a-153">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f757a-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f757a-154">Om du vill konfigurera egenskaper för användar konton med Microsoft Azure Active Directory-modulen för Windows PowerShell använder du cmdleten **set-MsolUser** och anger egenskaperna för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="f757a-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f757a-155">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f757a-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="f757a-156">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="f757a-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f757a-157">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f757a-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="f757a-158">Ändra egenskaper för ett visst användar konto</span><span class="sxs-lookup"><span data-stu-id="f757a-158">Change properties for a specific user account</span></span>

<span data-ttu-id="f757a-159">Om du vill konfigurera egenskaper för ett visst användar konto använder du cmdleten [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaperna för att ställa in eller ändra.</span><span class="sxs-lookup"><span data-stu-id="f757a-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f757a-160">Du identifierar kontot med parametern **-userPrincipalName** och anger eller ändrar specifika egenskaper med ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="f757a-160">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="f757a-161">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="f757a-161">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="f757a-162">-Ort " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="f757a-163">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="f757a-164">-Avdelning " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="f757a-165">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="f757a-166">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="f757a-167">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="f757a-168">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="f757a-169">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="f757a-170">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="f757a-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="f757a-171">-Telefonnummer " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="f757a-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="f757a-172">-Post nummer " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="f757a-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="f757a-173">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="f757a-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="f757a-174">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="f757a-175">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="f757a-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="f757a-176">-Rubrik " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="f757a-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="f757a-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="f757a-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="f757a-178">Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.</span><span class="sxs-lookup"><span data-stu-id="f757a-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="f757a-179">Se [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) för ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="f757a-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="f757a-180">Om du vill visa användarens huvud namn för alla användare kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="f757a-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="f757a-181">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-182">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-183">Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-184">Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="f757a-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="f757a-185">Visa dem en skärm bild i taget (**mer**).</span><span class="sxs-lookup"><span data-stu-id="f757a-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="f757a-186">Det här kommandot visar alla dina konton.</span><span class="sxs-lookup"><span data-stu-id="f757a-186">This command will list all of your accounts.</span></span> <span data-ttu-id="f757a-187">Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) fyller du i **$username** variabel nedan (tar bort \< and > tecknen) och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f757a-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f757a-188">I det här exemplet visas användarens huvud namn för användaren som heter Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="f757a-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f757a-189">Genom att använda en **$UPN** variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn.</span><span class="sxs-lookup"><span data-stu-id="f757a-189">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="f757a-190">Här är ett exempel på hur du anger Belinda Newman användnings plats för Frankrike, men anger hennes visnings namn i stället för användarens huvud namn:</span><span class="sxs-lookup"><span data-stu-id="f757a-190">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="f757a-191">Ändra egenskaper för alla användar konton</span><span class="sxs-lookup"><span data-stu-id="f757a-191">Change properties for all user accounts</span></span>

<span data-ttu-id="f757a-192">Om du vill ändra egenskaper för alla användare kan du använda kombinationen cmdleten **Get-MsolUser** och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="f757a-192">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="f757a-193">Följande exempel ändrar användnings platsen för alla användare till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="f757a-193">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="f757a-194">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-195">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-196">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f757a-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="f757a-197">Ändra egenskaper för en viss uppsättning användar konton</span><span class="sxs-lookup"><span data-stu-id="f757a-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="f757a-198">Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda kombinationen cmdleten **Get-MsolUser**, **WHERE**och **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="f757a-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="f757a-199">Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till Frankrike:</span><span class="sxs-lookup"><span data-stu-id="f757a-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="f757a-200">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f757a-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f757a-201">Hämta all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-202">Hitta alla användar konton som har egenskapen avdelning inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f757a-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="f757a-203">Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f757a-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="f757a-204">Se även</span><span class="sxs-lookup"><span data-stu-id="f757a-204">See also</span></span>

[<span data-ttu-id="f757a-205">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f757a-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f757a-206">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f757a-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f757a-207">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f757a-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
