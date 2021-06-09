---
title: Skapa Microsoft 365-postkonton med PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Så här använder du PowerShell för att skapa enskilda eller Microsoft 365 användarkonton.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907570"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="9d59f-103">Skapa Microsoft 365-postkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d59f-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="9d59f-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9d59f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9d59f-105">Du kan använda PowerShell för Microsoft 365 effektivt skapa användarkonton, inklusive flera konton.</span><span class="sxs-lookup"><span data-stu-id="9d59f-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="9d59f-106">När du skapar användarkonton i PowerShell krävs alltid vissa kontoegenskaper.</span><span class="sxs-lookup"><span data-stu-id="9d59f-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="9d59f-107">Andra egenskaper krävs inte men är viktiga.</span><span class="sxs-lookup"><span data-stu-id="9d59f-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="9d59f-108">Se följande tabell.</span><span class="sxs-lookup"><span data-stu-id="9d59f-108">See the following table.</span></span>
  
|<span data-ttu-id="9d59f-109">**Egenskapsnamn**</span><span class="sxs-lookup"><span data-stu-id="9d59f-109">**Property name**</span></span>|<span data-ttu-id="9d59f-110">**Obligatorisk**</span><span class="sxs-lookup"><span data-stu-id="9d59f-110">**Required?**</span></span>|<span data-ttu-id="9d59f-111">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="9d59f-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d59f-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="9d59f-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="9d59f-113">Ja</span><span class="sxs-lookup"><span data-stu-id="9d59f-113">Yes</span></span>  <br/> |<span data-ttu-id="9d59f-114">Det här är visningsnamnet som används i Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="9d59f-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="9d59f-115">Till exempel *Caleb Några*.</span><span class="sxs-lookup"><span data-stu-id="9d59f-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="9d59f-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="9d59f-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="9d59f-117">Ja</span><span class="sxs-lookup"><span data-stu-id="9d59f-117">Yes</span></span>  <br/> |<span data-ttu-id="9d59f-118">Det här är kontonamnet som används för att logga in på Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="9d59f-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="9d59f-119">Till exempel *kan CalebS \@ contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="9d59f-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="9d59f-120">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="9d59f-120">**FirstName**</span></span> <br/> |<span data-ttu-id="9d59f-121">Nej</span><span class="sxs-lookup"><span data-stu-id="9d59f-121">No</span></span>  <br/> ||
|<span data-ttu-id="9d59f-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="9d59f-122">**LastName**</span></span> <br/> |<span data-ttu-id="9d59f-123">Nej</span><span class="sxs-lookup"><span data-stu-id="9d59f-123">No</span></span>  <br/> ||
|<span data-ttu-id="9d59f-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="9d59f-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="9d59f-125">Nej</span><span class="sxs-lookup"><span data-stu-id="9d59f-125">No</span></span>  <br/> |<span data-ttu-id="9d59f-126">Det här är licensplanen (kallas även licensplanen eller SKU:n) som en tillgänglig licens tilldelas till användarkontot från.</span><span class="sxs-lookup"><span data-stu-id="9d59f-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="9d59f-127">Licensen definierar Microsoft 365 tjänster som är tillgängliga för kontot.</span><span class="sxs-lookup"><span data-stu-id="9d59f-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="9d59f-128">Du behöver inte tilldela en licens till en användare när du skapar kontot, men kontot måste ha en licens för åtkomst Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="9d59f-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="9d59f-129">Du har 30 dagar på dig att licensiera användarkontot när du har skapat det.</span><span class="sxs-lookup"><span data-stu-id="9d59f-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="9d59f-130">**Lösenord**</span><span class="sxs-lookup"><span data-stu-id="9d59f-130">**Password**</span></span> <br/> |<span data-ttu-id="9d59f-131">Nej</span><span class="sxs-lookup"><span data-stu-id="9d59f-131">No</span></span>  <br/> | <span data-ttu-id="9d59f-132">Om du inte anger ett lösenord tilldelas ett slumpmässigt lösenord till användarkontot och lösenordet visas i resultatet av kommandot.</span><span class="sxs-lookup"><span data-stu-id="9d59f-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="9d59f-133">Om du anger ett lösenord måste det innehålla 8 till 16 ASCII-texttecken av följande typer: gemener, versaler, siffror och symboler.</span><span class="sxs-lookup"><span data-stu-id="9d59f-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="9d59f-134">**Användningsbeläggning**</span><span class="sxs-lookup"><span data-stu-id="9d59f-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="9d59f-135">Nej</span><span class="sxs-lookup"><span data-stu-id="9d59f-135">No</span></span>  <br/> |<span data-ttu-id="9d59f-136">Det här är en giltig landskod enligt ISO 3166-1 alfa-2.</span><span class="sxs-lookup"><span data-stu-id="9d59f-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="9d59f-137">Till exempel *USA* för USA och *FR* för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="9d59f-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="9d59f-138">Det är viktigt att tillhandahålla detta värde eftersom vissa Microsoft 365 tjänster inte är tillgängliga i vissa länder.</span><span class="sxs-lookup"><span data-stu-id="9d59f-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="9d59f-139">Du kan inte tilldela en licens till ett användarkonto om inte kontot har det här värdet konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="9d59f-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="9d59f-140">Mer information finns i [Om licensbegränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="9d59f-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="9d59f-141">[Lär dig hur du skapar användarkonton](../admin/add-users/add-users.md) i Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="9d59f-141">[Learn how to create user accounts](../admin/add-users/add-users.md) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="9d59f-142">En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="9d59f-142">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9d59f-143">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="9d59f-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9d59f-144">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9d59f-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="9d59f-145">När du har anslutt använder du följande syntax för att skapa ett enskilt konto:</span><span class="sxs-lookup"><span data-stu-id="9d59f-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="9d59f-146">I det här exemplet skapas ett konto för den amerikanska *användaren Caleb Beskrivning:*</span><span class="sxs-lookup"><span data-stu-id="9d59f-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9d59f-147">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d59f-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9d59f-148">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="9d59f-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="9d59f-149">Skapa ett enskilt användarkonto</span><span class="sxs-lookup"><span data-stu-id="9d59f-149">Create an individual user account</span></span>

<span data-ttu-id="9d59f-150">Om du vill skapa ett enskilt konto ska du använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="9d59f-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="9d59f-151">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell och cmdlets som har *Msol* i sitt namn.</span><span class="sxs-lookup"><span data-stu-id="9d59f-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="9d59f-152">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d59f-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="9d59f-153">Använd det här kommandot om du vill visa en lista över tillgängliga namn på licensplanen:</span><span class="sxs-lookup"><span data-stu-id="9d59f-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="9d59f-154">Det här exemplet skapar ett konto för den amerikanska användaren *Caleb Planers* och tilldelar en licens från `contoso:ENTERPRISEPACK` licensplanen (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="9d59f-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="9d59f-155">Skapa flera användarkonton</span><span class="sxs-lookup"><span data-stu-id="9d59f-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="9d59f-156">Skapa en fil med kommaavgränsade värden (CSV) som innehåller den användarkontoinformation som krävs.</span><span class="sxs-lookup"><span data-stu-id="9d59f-156">Create a comma-separated value (CSV) file that contains the required user account information.</span></span> <span data-ttu-id="9d59f-157">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9d59f-157">For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="9d59f-158">Kolumnnamnen och deras ordning i den första raden i CSV-filen är godtyckliga.</span><span class="sxs-lookup"><span data-stu-id="9d59f-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="9d59f-159">Men se till att ordningen på data i resten av filen matchar ordningsföljden för kolumnnamnen.</span><span class="sxs-lookup"><span data-stu-id="9d59f-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="9d59f-160">Och använd kolumnnamnen för parametervärdena i PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d59f-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="9d59f-161">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="9d59f-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="9d59f-162">I det här exemplet skapas användarkonton från filen *C:\My Documents\NewAccounts.csv* och resultatet loggas i en fil med namnet *C:\My Documents\NewAccountResults.csv*.</span><span class="sxs-lookup"><span data-stu-id="9d59f-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="9d59f-163">Granska utdatafilen för att se resultatet.</span><span class="sxs-lookup"><span data-stu-id="9d59f-163">Review the output file to see the results.</span></span> <span data-ttu-id="9d59f-164">Vi har inte angett lösenord, så de slumpmässiga lösenord Microsoft 365 som genereras visas i utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="9d59f-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9d59f-165">Se även</span><span class="sxs-lookup"><span data-stu-id="9d59f-165">See also</span></span>

[<span data-ttu-id="9d59f-166">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d59f-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9d59f-167">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d59f-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9d59f-168">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d59f-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)