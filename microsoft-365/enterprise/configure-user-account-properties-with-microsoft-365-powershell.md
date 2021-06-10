---
title: Konfigurera Microsoft 365 användarkontoegenskaper med PowerShell
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
description: Använd PowerShell för Microsoft 365 att konfigurera egenskaper för enskilda eller flera användarkonton i Microsoft 365 klientorganisationen.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911090"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="2f77e-103">Konfigurera Microsoft 365 användarkontoegenskaper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f77e-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="2f77e-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2f77e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2f77e-105">Du kan använda Microsoft 365 för att konfigurera egenskaper för användarkontona i klientorganisationen Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2f77e-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="2f77e-106">I PowerShell kan du göra detta, plus en del andra saker du inte kan göra i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="2f77e-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2f77e-107">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="2f77e-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2f77e-108">Om du vill konfigurera egenskaper för användarkonton i Azure Active Directory PowerShell för Graph-modulen använder du cmdleten [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) och anger vilka egenskaper du vill ange eller ändra.</span><span class="sxs-lookup"><span data-stu-id="2f77e-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="2f77e-109">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="2f77e-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="2f77e-110">Ändra egenskaper för ett visst användarkonto</span><span class="sxs-lookup"><span data-stu-id="2f77e-110">Change properties for a specific user account</span></span>

<span data-ttu-id="2f77e-111">Du identifierar kontot med parametern *-ObjectID och* anger eller ändrar specifika egenskaper med hjälp av ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="2f77e-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="2f77e-112">Här är en lista över de vanligaste parametrarna:</span><span class="sxs-lookup"><span data-stu-id="2f77e-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="2f77e-113">-Avdelning \<department name> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="2f77e-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="2f77e-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="2f77e-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="2f77e-117">-Efternamn " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="2f77e-118">-Mobil " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="2f77e-119">-JobTitle \<job title> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="2f77e-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="2f77e-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="2f77e-122">-Ort \<city name> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="2f77e-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="2f77e-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="2f77e-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="2f77e-126">-TelephoneNumber \<office phone number> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="2f77e-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="2f77e-128">Det här är lands- eller regionskoden enligt ISO 3166-1 alfa-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="2f77e-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="2f77e-129">Fler parametrar finns i [Set-AzureADUser.](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="2f77e-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="2f77e-130">Innan du kan tilldela licenser till ett användarkonto måste du tilldela en användningsplats.</span><span class="sxs-lookup"><span data-stu-id="2f77e-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="2f77e-131">Om du vill visa användarkontons huvudnamn kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="2f77e-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="2f77e-132">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-133">Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-134">Sortera listan med användarhuvudnamn i alfabetisk **ordning (Sortera UserPrincipalName)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-135">Visa bara egenskapen User Principal Name för varje konto (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="2f77e-136">Visa dem en skärmbild i taget **(Mer).**</span><span class="sxs-lookup"><span data-stu-id="2f77e-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="2f77e-137">Kör följande kommandon om du vill visa användarkontons huvudnamn baserat på dess visningsnamn (för- och efternamn).</span><span class="sxs-lookup"><span data-stu-id="2f77e-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="2f77e-138">Fyll i *$userName* variabeln och ta bort \< and > tecknen:</span><span class="sxs-lookup"><span data-stu-id="2f77e-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="2f77e-139">I det här exemplet visas Användarkontots huvudnamn för användarkontot som har visningsnamnet *Caleb Hass*.</span><span class="sxs-lookup"><span data-stu-id="2f77e-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="2f77e-140">Genom att *använda $upn* variabel kan du göra ändringar i enskilda konton baserat på deras visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="2f77e-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="2f77e-141">Här är ett exempel som anger *Belinda Newman's* användningsplats till Frankrike.</span><span class="sxs-lookup"><span data-stu-id="2f77e-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="2f77e-142">Men det anger hennes visningsnamn i stället för hennes huvudnamn:</span><span class="sxs-lookup"><span data-stu-id="2f77e-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="2f77e-143">Ändra egenskaper för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="2f77e-143">Change properties for all user accounts</span></span>

<span data-ttu-id="2f77e-144">Om du vill ändra egenskaper för alla användare kan du använda en kombination av cmdletarna **Get-AzureADUser** och **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="2f77e-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="2f77e-145">I följande exempel ändras användningsplatsen för alla användare till *Frankrike:*</span><span class="sxs-lookup"><span data-stu-id="2f77e-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="2f77e-146">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-147">Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-148">Ställ in användarens plats på Frankrike **(Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="2f77e-149">Ändra egenskaper för en viss uppsättning användarkonton</span><span class="sxs-lookup"><span data-stu-id="2f77e-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="2f77e-150">Om du vill ändra egenskaper för en viss uppsättning användarkonton kan du använda en kombination av cmdlet:arna **Get-AzureADUser**, **Where** och **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="2f77e-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="2f77e-151">I följande exempel ändras användningsplatsen för alla användare på redovisningsavdelningen till *Frankrike:*</span><span class="sxs-lookup"><span data-stu-id="2f77e-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="2f77e-152">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-153">Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="2f77e-154">Hitta alla användarkonton som  har avdelningsegenskapen inställd på "Redovisning" (**Där {$_. Avdelning -eq "Accounting"} )** och skicka informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-155">Ställ in användarens plats på Frankrike **(Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2f77e-156">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f77e-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2f77e-157">Om du vill konfigurera egenskaper för användarkonton med Microsoft Azure Active Directory-modulen för Windows PowerShell, använder du cmdleten **Set-MsolUser** och anger egenskaper som du vill ange eller ändra.</span><span class="sxs-lookup"><span data-stu-id="2f77e-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="2f77e-158">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f77e-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="2f77e-159">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="2f77e-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="2f77e-160">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f77e-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="2f77e-161">Ändra egenskaper för ett visst användarkonto</span><span class="sxs-lookup"><span data-stu-id="2f77e-161">Change properties for a specific user account</span></span>

<span data-ttu-id="2f77e-162">Om du vill konfigurera egenskaper för ett specifikt användarkonto använder du cmdleten [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaper som du vill ange eller ändra.</span><span class="sxs-lookup"><span data-stu-id="2f77e-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="2f77e-163">Du identifierar kontot med *parametern -UserPrincipalName och* anger eller ändrar specifika egenskaper med hjälp av ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="2f77e-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="2f77e-164">Här är en lista över de vanligaste parametrarna.</span><span class="sxs-lookup"><span data-stu-id="2f77e-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="2f77e-165">-Ort \<city name> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="2f77e-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="2f77e-167">-Avdelning \<department name> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="2f77e-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="2f77e-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="2f77e-170">-Förnamn " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="2f77e-171">-Efternamn " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="2f77e-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="2f77e-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="2f77e-174">-PhoneNumber \<office phone number> " "</span><span class="sxs-lookup"><span data-stu-id="2f77e-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="2f77e-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="2f77e-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="2f77e-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="2f77e-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="2f77e-179">-Titel " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="2f77e-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="2f77e-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="2f77e-181">Det här är lands- eller regionskoden enligt ISO 3166-1 alfa-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="2f77e-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="2f77e-182">Fler parametrar finns i [Set-MsolUser.](/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="2f77e-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="2f77e-183">Om du vill visa användarhuvudnamn för alla dina användare kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="2f77e-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="2f77e-184">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-185">Få all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-186">Sortera listan med användarhuvudnamn i alfabetisk **ordning (Sortera UserPrincipalName)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-187">Visa bara egenskapen User Principal Name för varje konto (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="2f77e-188">Visa dem en skärmbild i taget **(Mer).**</span><span class="sxs-lookup"><span data-stu-id="2f77e-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="2f77e-189">Kör följande kommandon om du vill visa användarkontons huvudnamn baserat på dess visningsnamn (för- och efternamn).</span><span class="sxs-lookup"><span data-stu-id="2f77e-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="2f77e-190">Fyll i *$userName* och ta bort \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="2f77e-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="2f77e-191">I det här exemplet visas användarens huvudnamn för användaren Caleb Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2f77e-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="2f77e-192">Genom att *använda $upn* variabel kan du göra ändringar i enskilda konton baserat på deras visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="2f77e-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="2f77e-193">Här är ett exempel som *anger Belinda Newman:s* användningsplats till *Frankrike,* men anger hennes visningsnamn i stället för hennes användarhuvudnamn:</span><span class="sxs-lookup"><span data-stu-id="2f77e-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="2f77e-194">Ändra egenskaper för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="2f77e-194">Change properties for all user accounts</span></span>

<span data-ttu-id="2f77e-195">Om du vill ändra egenskaper för alla användare använder du en kombination av cmdlet:arna **Get-MsolUser** **och Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="2f77e-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="2f77e-196">I följande exempel ändras användningsplatsen för alla användare till *Frankrike:*</span><span class="sxs-lookup"><span data-stu-id="2f77e-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="2f77e-197">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-198">Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-199">Ställ in användarens plats på Frankrike **(Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="2f77e-200">Ändra egenskaper för en viss uppsättning användarkonton</span><span class="sxs-lookup"><span data-stu-id="2f77e-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="2f77e-201">Om du vill ändra egenskaper för en viss uppsättning användarkonton kan du använda en kombination av cmdlet:arna **Get-MsolUser**, **Where** och **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="2f77e-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="2f77e-202">I följande exempel ändras användningsplatsen för alla användare på redovisningsavdelningen till *Frankrike:*</span><span class="sxs-lookup"><span data-stu-id="2f77e-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="2f77e-203">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="2f77e-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="2f77e-204">Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-205">Hitta alla användarkonton där *Avdelning-egenskapen* är inställd på "Redovisning" (**Där {$_. Avdelning -eq "Accounting"}**) och skicka informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2f77e-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="2f77e-206">Ställ in användarens plats på Frankrike **(Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="2f77e-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f77e-207">Se även</span><span class="sxs-lookup"><span data-stu-id="2f77e-207">See also</span></span>

[<span data-ttu-id="2f77e-208">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f77e-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2f77e-209">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f77e-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2f77e-210">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f77e-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)