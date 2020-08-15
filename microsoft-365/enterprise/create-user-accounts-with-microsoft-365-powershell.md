---
title: Skapa Microsoft 365-användarkonton med PowerShell
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: I den här artikeln lär du dig hur du använder PowerShell för att skapa användar konton eller flera Microsoft 365-användarkonton.
ms.openlocfilehash: 53077352862b6d0df6bb569300e2d8bc2475df91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694693"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="bb839-103">Skapa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb839-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="bb839-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bb839-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bb839-105">Du kan använda PowerShell för Microsoft 365 för att effektivt skapa användar konton, särskilt flera användar konton.</span><span class="sxs-lookup"><span data-stu-id="bb839-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, especially multiple user accounts.</span></span> <span data-ttu-id="bb839-106">När du skapar användar konton i PowerShell behövs alltid vissa konto egenskaper.</span><span class="sxs-lookup"><span data-stu-id="bb839-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="bb839-107">Andra egenskaper behövs inte för att skapa kontot, men annars är det viktigt.</span><span class="sxs-lookup"><span data-stu-id="bb839-107">Other properties aren't required to create the account, but are otherwise important.</span></span> <span data-ttu-id="bb839-108">Dessa egenskaper beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="bb839-108">These properties are described in the following table:</span></span>
  
|<span data-ttu-id="bb839-109">**Egenskaps namn**</span><span class="sxs-lookup"><span data-stu-id="bb839-109">**Property name**</span></span>|<span data-ttu-id="bb839-110">**Obligatorisk**</span><span class="sxs-lookup"><span data-stu-id="bb839-110">**Required?**</span></span>|<span data-ttu-id="bb839-111">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="bb839-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb839-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="bb839-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="bb839-113">Ja</span><span class="sxs-lookup"><span data-stu-id="bb839-113">Yes</span></span>  <br/> |<span data-ttu-id="bb839-114">Det här är visnings namnet som används i Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="bb839-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="bb839-115">Till exempel Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="bb839-115">For example, Caleb Sills.</span></span>  <br/> |
|<span data-ttu-id="bb839-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="bb839-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="bb839-117">Ja</span><span class="sxs-lookup"><span data-stu-id="bb839-117">Yes</span></span>  <br/> |<span data-ttu-id="bb839-118">Det här är det konto namn som används för att logga in på Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="bb839-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="bb839-119">Till exempel CalebS@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bb839-119">For example, CalebS@contoso.onmicrosoft.com.</span></span>  <br/> |
|<span data-ttu-id="bb839-120">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="bb839-120">**FirstName**</span></span> <br/> |<span data-ttu-id="bb839-121">Nej</span><span class="sxs-lookup"><span data-stu-id="bb839-121">No</span></span>  <br/> ||
|<span data-ttu-id="bb839-122">**Efter namn**</span><span class="sxs-lookup"><span data-stu-id="bb839-122">**LastName**</span></span> <br/> |<span data-ttu-id="bb839-123">Nej</span><span class="sxs-lookup"><span data-stu-id="bb839-123">No</span></span>  <br/> ||
|<span data-ttu-id="bb839-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="bb839-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="bb839-125">Nej</span><span class="sxs-lookup"><span data-stu-id="bb839-125">No</span></span>  <br/> |<span data-ttu-id="bb839-126">Det här är licens planen (kallas även licens planen eller SKU) som en tillgänglig licens har tilldelats till.</span><span class="sxs-lookup"><span data-stu-id="bb839-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="bb839-127">Licensen definierar vilka Microsoft 365-tjänster som är tillgängliga för konto.</span><span class="sxs-lookup"><span data-stu-id="bb839-127">The license defines the Microsoft 365 services that are available to account.</span></span> <span data-ttu-id="bb839-128">Du behöver inte tilldela en licens till en användare när du skapar kontot, men kontot kräver en licens för åtkomst till Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="bb839-128">You don't have to assign a license to a user when you create the account, but the account requires a license to access Microsoft 365 services.</span></span> <span data-ttu-id="bb839-129">Du har 30 dagar på dig att licensiera användar kontot när du har skapat det.</span><span class="sxs-lookup"><span data-stu-id="bb839-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="bb839-130">**Lösenord**</span><span class="sxs-lookup"><span data-stu-id="bb839-130">**Password**</span></span> <br/> |<span data-ttu-id="bb839-131">Nej</span><span class="sxs-lookup"><span data-stu-id="bb839-131">No</span></span>  <br/> | <span data-ttu-id="bb839-132">Om du inte anger något lösen ord tilldelas användar kontot ett slumpmässigt lösen ord och lösen ordet visas i resultatet av kommandot.</span><span class="sxs-lookup"><span data-stu-id="bb839-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="bb839-133">Om du anger ett lösen ord måste det vara 8 till 16 ASCII-tecken från någon av följande typer: gemener, versaler, siffror och symboler.</span><span class="sxs-lookup"><span data-stu-id="bb839-133">If you specify a password, it needs to be 8 to 16 ASCII text characters from any three of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <br/> |
|<span data-ttu-id="bb839-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="bb839-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="bb839-135">Nej</span><span class="sxs-lookup"><span data-stu-id="bb839-135">No</span></span>  <br/> |<span data-ttu-id="bb839-136">Det här är en giltig ISO 3166-1 alpha-2-landskod.</span><span class="sxs-lookup"><span data-stu-id="bb839-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="bb839-137">Till exempel för USA och FR för Frankrike.</span><span class="sxs-lookup"><span data-stu-id="bb839-137">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="bb839-138">Det är viktigt att ange det här värdet eftersom vissa Microsoft 365-tjänster inte är tillgängliga i vissa länder, så du kan inte tilldela en licens till ett användar konto om inte kontot har konfigurerat det här värdet.</span><span class="sxs-lookup"><span data-stu-id="bb839-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries, so you can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="bb839-139">Mer information finns i [om licens begränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="bb839-139">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>  <br/> |
   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="bb839-140">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="bb839-140">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="bb839-141">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="bb839-141">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="bb839-142">När du har anslutit kan du använda följande syntax för att skapa ett enskilt konto:</span><span class="sxs-lookup"><span data-stu-id="bb839-142">After you have connected, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="bb839-143">I det här exemplet skapas ett konto för United States användare som heter Caleb brädor:</span><span class="sxs-lookup"><span data-stu-id="bb839-143">This example creates an account for the United States user named Caleb Sills:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="bb839-144">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb839-144">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="bb839-145">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bb839-145">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="bb839-146">Skapa ett enskilt användar konto</span><span class="sxs-lookup"><span data-stu-id="bb839-146">Create an individual user account</span></span>

<span data-ttu-id="bb839-147">Använd följande syntax för att skapa ett enskilt konto:</span><span class="sxs-lookup"><span data-stu-id="bb839-147">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="bb839-148">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="bb839-148">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="bb839-149">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb839-149">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="bb839-150">Använd det här kommandot för att lista de tillgängliga namnen på licens planerna:</span><span class="sxs-lookup"><span data-stu-id="bb839-150">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="bb839-151">I det här exemplet skapas ett konto för United States användare som heter Caleb brädor och tilldelar en licens från `contoso:ENTERPRISEPACK` licens planen (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="bb839-151">This example creates an account for the United States user named Caleb Sills, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="bb839-152">Skapa flera användar konton</span><span class="sxs-lookup"><span data-stu-id="bb839-152">Create multiple user accounts</span></span>

1. <span data-ttu-id="bb839-153">Skapa en CSV-fil (kommaseparerade värden) som innehåller den användar konto information som krävs.</span><span class="sxs-lookup"><span data-stu-id="bb839-153">Create a comma-separated value (CSV) file that contains the required user account information.</span></span> <span data-ttu-id="bb839-154">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="bb839-154">For example:</span></span>
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
><span data-ttu-id="bb839-155">Kolumn namnen och deras ordning i den första raden i CSV-filen är valfria, men kontrol lera att data i resten av filen matchar ordningen på kolumn namnen och Använd kolumn namnen för parameter värden i PowerShell för Microsoft 365-kommandot.</span><span class="sxs-lookup"><span data-stu-id="bb839-155">The column names and their order in the first row of the CSV file are arbitrary, but make sure the data in the rest of the file matches the order of the column names, and use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="bb839-156">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="bb839-156">Use the following syntax:</span></span>
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

<span data-ttu-id="bb839-157">I det här exemplet skapas användar konton från filen C:\Mina Documents\NewAccounts.csv och resultatet loggas i filen C:\Mina Documents\NewAccountResults.csv</span><span class="sxs-lookup"><span data-stu-id="bb839-157">This example creates the user accounts from the file named C:\My Documents\NewAccounts.csv, and logs the results in the file named C:\My Documents\NewAccountResults.csv</span></span>
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. <span data-ttu-id="bb839-158">Granska utdatafilen för att se resultatet.</span><span class="sxs-lookup"><span data-stu-id="bb839-158">Review the output file to see the results.</span></span> <span data-ttu-id="bb839-159">Vi angav inte lösen ord, så de slumpmässiga lösen ord som Microsoft 365 genererade visas i utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="bb839-159">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb839-160">Se även</span><span class="sxs-lookup"><span data-stu-id="bb839-160">See also</span></span>

[<span data-ttu-id="bb839-161">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb839-161">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bb839-162">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb839-162">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bb839-163">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb839-163">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
