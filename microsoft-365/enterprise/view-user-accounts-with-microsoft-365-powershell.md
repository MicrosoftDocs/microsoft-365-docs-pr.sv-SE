---
title: Visa Microsoft 365-användarkonton med PowerShell
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Lär dig att visa, lista eller Visa dina Microsoft 365-användarkonton på olika sätt med PowerShell.
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696765"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="1629c-103">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1629c-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="1629c-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1629c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1629c-105">Även om du kan använda administrations centret för Microsoft 365 för att Visa kontona för din Microsoft 365-klient organisation kan du också använda PowerShell för Microsoft 365 och göra vissa saker som administrations centret inte kan.</span><span class="sxs-lookup"><span data-stu-id="1629c-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1629c-106">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="1629c-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1629c-107">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1629c-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="1629c-108">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="1629c-108">View all accounts</span></span>

<span data-ttu-id="1629c-109">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1629c-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="1629c-110">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-110">You should see information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="1629c-111">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="1629c-111">View a specific account</span></span>

<span data-ttu-id="1629c-112">Om du vill visa ett specifikt användar konto fyller du i användar kontots namn för inloggnings konto, som även kallas UPN (User Principal Name), tar bort tecknen "<" och ">" och kör det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1629c-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="1629c-113">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="1629c-114">Visa ytterligare egenskaps värden för ett visst konto</span><span class="sxs-lookup"><span data-stu-id="1629c-114">View additional property values for a specific account</span></span>

<span data-ttu-id="1629c-115">Som standard visar cmdleten **Get-AzureADUser** bara egenskaperna ObjectID, DisplayName och userPrincipalName för konton.</span><span class="sxs-lookup"><span data-stu-id="1629c-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="1629c-116">Om du vill veta mer om listan med egenskaper att Visa kan du använda **Select** -cmdleten i kombination med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="1629c-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="1629c-117">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="1629c-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1629c-118">Här visas ett exempel kommando som visar visnings namn, avdelning och UsageLocation för varje användar konto:</span><span class="sxs-lookup"><span data-stu-id="1629c-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="1629c-119">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="1629c-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1629c-120">Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1629c-121">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="1629c-122">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1629c-123">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1629c-124">Du kan till exempel kontrol lera den aktiverade statusen för ett visst användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1629c-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="1629c-125">Visa vissa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="1629c-125">View some accounts based on a common property</span></span>

<span data-ttu-id="1629c-126">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="1629c-126">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="1629c-127">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="1629c-127">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1629c-128">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="1629c-128">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="1629c-129">Det här kommandot instruerar Azure Active Directory PowerShell för Graph till:</span><span class="sxs-lookup"><span data-stu-id="1629c-129">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="1629c-130">Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-130">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1629c-131">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-131">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="1629c-132">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-132">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="1629c-133">Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-133">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="1629c-134">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-134">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1629c-135">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-135">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1629c-136">I den här listan är till exempel **ort** namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-136">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="1629c-137">Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="1629c-137">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="1629c-138">Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="1629c-138">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="1629c-139">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**. > [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="1629c-139">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="1629c-140">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad> se [var](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) du kan få mer information.</span><span class="sxs-lookup"><span data-stu-id="1629c-140">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1629c-141">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1629c-141">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1629c-142">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1629c-142">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="1629c-143">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="1629c-143">View all accounts</span></span>

<span data-ttu-id="1629c-144">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1629c-144">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="1629c-145">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="1629c-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1629c-146">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1629c-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="1629c-147">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-147">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="1629c-148">Cmdleten **Get-MsolUser** har också en uppsättning parametrar som filtrerar uppsättningen med användar konton.</span><span class="sxs-lookup"><span data-stu-id="1629c-148">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="1629c-149">Om du till exempel vill visa en lista över ej licensierade användare (användare som har lagts till i Microsoft 365 men ännu inte har licensierats till att använda någon av tjänsterna) kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="1629c-149">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="1629c-150">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-150">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="1629c-151">Mer information om ytterligare parametrar för att filtrera visningen av uppsättningen användar konton som visas finns i [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="1629c-151">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="1629c-152">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="1629c-152">View a specific account</span></span>

<span data-ttu-id="1629c-153">Om du vill visa ett specifikt användar konto fyller du i inloggnings namnet för användar kontot för användar kontot, även kallat användarens huvud namn (UPN), tar bort tecknen "<" och ">" och kör det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1629c-153">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="1629c-154">Visa vissa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="1629c-154">View some accounts based on a common property</span></span>

<span data-ttu-id="1629c-155">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="1629c-155">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="1629c-156">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", vilket anger att PowerShell utför resultatet av ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="1629c-156">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1629c-157">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="1629c-157">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="1629c-158">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="1629c-158">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1629c-159">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-159">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1629c-160">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-160">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="1629c-161">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-161">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="1629c-162">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-162">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="1629c-163">Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-163">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="1629c-164">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-164">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1629c-165">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-165">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1629c-166">I den här listan är till exempel **ort** namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-166">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="1629c-167">Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="1629c-167">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="1629c-168">Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="1629c-168">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="1629c-169">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**.</span><span class="sxs-lookup"><span data-stu-id="1629c-169">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="1629c-170">[jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-** t för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="1629c-170">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="1629c-171">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad.</span><span class="sxs-lookup"><span data-stu-id="1629c-171">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="1629c-172">Se [var](https://technet.microsoft.com/library/hh849715.aspx) du kan få mer information.</span><span class="sxs-lookup"><span data-stu-id="1629c-172">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="1629c-173">Du kan kontrol lera den spärrade statusen för ett användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1629c-173">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="1629c-174">Visa ytterligare egenskaps värden för konton</span><span class="sxs-lookup"><span data-stu-id="1629c-174">View additional property values for accounts</span></span>

<span data-ttu-id="1629c-175">Cmdleten **Get-MsolUser** med standard visar tre egenskaper för användar konton:</span><span class="sxs-lookup"><span data-stu-id="1629c-175">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="1629c-176">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="1629c-176">UserPrincipalName</span></span>
    
- <span data-ttu-id="1629c-177">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1629c-177">DisplayName</span></span>
    
- <span data-ttu-id="1629c-178">Ärlicensierad</span><span class="sxs-lookup"><span data-stu-id="1629c-178">isLicensed</span></span>
    
<span data-ttu-id="1629c-179">Om du behöver ytterligare egenskaper, till exempel avdelningen som användaren arbetar med och landet/regionen där användaren använder Microsoft 365-tjänsterna, kan du köra **Get-MsolUser** i kombination med **Välj** cmdlet för att ange listan över användar konto egenskaper.</span><span class="sxs-lookup"><span data-stu-id="1629c-179">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="1629c-180">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-180">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="1629c-181">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="1629c-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1629c-182">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-182">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1629c-183">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-183">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="1629c-184">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-184">You should see information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="1629c-185">Med **Välj** cmdlet kan du välja och välja vilka egenskaper du vill visa.</span><span class="sxs-lookup"><span data-stu-id="1629c-185">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="1629c-186">Om du vill visa alla egenskaper för användar konton använder du jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="1629c-186">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1629c-187">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1629c-187">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1629c-188">Om du vill veta mer om listan med konton som ska visas kan du även använda **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="1629c-188">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="1629c-189">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="1629c-189">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="1629c-190">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="1629c-190">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1629c-191">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-191">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1629c-192">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-192">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="1629c-193">Inuti klamrarna anger kommandot PowerShell för att bara hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-193">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="1629c-194">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1629c-194">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="1629c-195">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="1629c-195">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="1629c-196">Om du använder Directory-synkronisering för att skapa och hantera dina Microsoft 365-användare kan du Visa vilka lokala konton en Microsoft 365-användare har projicerat från.</span><span class="sxs-lookup"><span data-stu-id="1629c-196">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="1629c-197">Följande förutsätter att Azure AD Connect är konfigurerat för att använda standard käll ankaret för ObjectGUID (mer information om hur du konfigurerar käll ankare finns i [Azure AD Connect: design koncept](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) och förutsätter att Active Directory Domain Services-modulen för PowerShell har installerats (se [rsat tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="1629c-197">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="1629c-198">Se även</span><span class="sxs-lookup"><span data-stu-id="1629c-198">See also</span></span>

[<span data-ttu-id="1629c-199">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1629c-199">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1629c-200">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1629c-200">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1629c-201">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1629c-201">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

