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
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754078"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="99808-103">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="99808-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="99808-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="99808-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="99808-105">Du kan använda administrations centret för Microsoft 365 för att Visa kontona för din Microsoft 365-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="99808-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="99808-106">Med PowerShell för Microsoft 365 kan du även få ytterligare funktioner.</span><span class="sxs-lookup"><span data-stu-id="99808-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="99808-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="99808-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="99808-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="99808-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="99808-109">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="99808-109">View all accounts</span></span>

<span data-ttu-id="99808-110">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="99808-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="99808-111">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="99808-112">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="99808-112">View a specific account</span></span>

<span data-ttu-id="99808-113">Om du vill visa ett specifikt användar konto kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99808-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="99808-114">Fyll i namnet på användar kontots inloggnings konto, som även kallas användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="99808-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="99808-115">Ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="99808-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="99808-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="99808-117">Visa ytterligare egenskaps värden för ett visst konto</span><span class="sxs-lookup"><span data-stu-id="99808-117">View additional property values for a specific account</span></span>

<span data-ttu-id="99808-118">Som standard visar cmdleten **Get-AzureADUser** bara egenskaperna *ObjectID*, *DisplayName*och *userPrincipalName* för konton.</span><span class="sxs-lookup"><span data-stu-id="99808-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="99808-119">Om du vill veta mer om vilka egenskaper som ska visas använder du cmdleten **Select** i kombination med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="99808-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="99808-120">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="99808-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="99808-121">Här är ett exempel kommando som visar *visnings*namn, *avdelning*och *UsageLocation* för alla användar konton:</span><span class="sxs-lookup"><span data-stu-id="99808-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="99808-122">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="99808-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="99808-123">Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="99808-124">Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="99808-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="99808-125">Om du vill visa alla egenskaper för ett visst användar konto använder du **Select** -cmdlet och jokertecknet (\*).</span><span class="sxs-lookup"><span data-stu-id="99808-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="99808-126">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="99808-127">I ett annat exempel kör du följande kommando för att kontrol lera den aktiverade statusen för ett specifikt användar konto:</span><span class="sxs-lookup"><span data-stu-id="99808-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="99808-128">Visa synkroniseringsstatus för kontot</span><span class="sxs-lookup"><span data-stu-id="99808-128">View account synchronization status</span></span>

<span data-ttu-id="99808-129">Användar konton har två källor:</span><span class="sxs-lookup"><span data-stu-id="99808-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="99808-130">Windows Server Active Directory (AD), som är konton som synkroniserar från lokal annons till molnet.</span><span class="sxs-lookup"><span data-stu-id="99808-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="99808-131">Azure Active Directory (Azure AD)-konton som skapas direkt i molnet.</span><span class="sxs-lookup"><span data-stu-id="99808-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="99808-132">Följande kommando instruerar PowerShell att hämta alla användare som har attributet *DirSyncEnabled* angivet till *True*.</span><span class="sxs-lookup"><span data-stu-id="99808-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="99808-133">Du kan använda den för att hitta konton som synkroniserar från den lokala ANNONSen.</span><span class="sxs-lookup"><span data-stu-id="99808-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="99808-134">Följande kommando instruerar PowerShell att hämta alla användare som har attributet *DirSyncEnabled* angivet till *false*.</span><span class="sxs-lookup"><span data-stu-id="99808-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="99808-135">Du kan använda den för att söka efter moln-konton.</span><span class="sxs-lookup"><span data-stu-id="99808-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="99808-136">Visa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="99808-136">View accounts based on a common property</span></span>

<span data-ttu-id="99808-137">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="99808-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="99808-138">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="99808-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="99808-139">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="99808-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="99808-140">Det här kommandot instruerar Azure Active Directory PowerShell för Graph till:</span><span class="sxs-lookup"><span data-stu-id="99808-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="99808-141">Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="99808-142">Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="99808-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="99808-143">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton som egenskapen UsageLocation User Account (\*\* $ \_ . UsageLocation**) är inte angivet (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="99808-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="99808-144">Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="99808-145">Om du vill visa alla egenskaper för ett visst användar konto använder du **Select** -cmdlet och jokertecknet (\*).</span><span class="sxs-lookup"><span data-stu-id="99808-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="99808-146">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="99808-147">Till exempel är **ort** namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="99808-148">Du kan använda följande kommando för att lista alla konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="99808-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="99808-149">Syntaxen för **WHERE** -cmdleten i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="99808-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="99808-150">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**. > [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="99808-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="99808-151">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad.</span><span class="sxs-lookup"><span data-stu-id="99808-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="99808-152">Mer information finns i [var](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="99808-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="99808-153">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99808-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="99808-154">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="99808-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="99808-155">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="99808-155">View all accounts</span></span>

<span data-ttu-id="99808-156">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="99808-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="99808-157">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* .</span><span class="sxs-lookup"><span data-stu-id="99808-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="99808-158">Kör dessa cmdletar från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99808-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="99808-159">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="99808-160">Cmdleten **Get-MsolUser** har också en uppsättning parametrar som filtrerar uppsättningen med användar konton.</span><span class="sxs-lookup"><span data-stu-id="99808-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="99808-161">Om du till exempel vill visa en lista över ej licensierade användare (användare som har lagts till i Microsoft 365 men ännu inte licensierats till att använda någon av tjänsterna) kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="99808-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="99808-162">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="99808-163">Information om ytterligare parametrar för att filtrera uppsättningen användar konton som visas finns i [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="99808-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="99808-164">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="99808-164">View a specific account</span></span>

<span data-ttu-id="99808-165">Om du vill visa ett specifikt användar konto kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99808-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="99808-166">Fyll i inloggnings namnet för användar kontot, som även kallas UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="99808-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="99808-167">Ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="99808-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="99808-168">Visa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="99808-168">View accounts based on a common property</span></span>

<span data-ttu-id="99808-169">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="99808-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="99808-170">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), vilket gör att PowerShell utför resultatet från ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="99808-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="99808-171">Här är ett exempel som bara visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="99808-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="99808-172">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="99808-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="99808-173">Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="99808-174">Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="99808-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="99808-175">Inuti klamrarna anger kommandot PowerShell för att hitta den uppsättning konton för vilka egenskapen UsageLocation User Account (\*\* $ \_ . UsageLocation**) är inte angivet (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="99808-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="99808-176">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="99808-177">Egenskapen *UsageLocation* är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="99808-178">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="99808-179">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="99808-180">Till exempel är *ort* namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="99808-181">Du kan använda följande kommando för att lista alla användar konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="99808-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="99808-182">Syntaxen för **WHERE** -cmdleten i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="99808-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="99808-183">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**.</span><span class="sxs-lookup"><span data-stu-id="99808-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="99808-184">[jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-** t för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="99808-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="99808-185">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad.</span><span class="sxs-lookup"><span data-stu-id="99808-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="99808-186">Mer information finns i [var](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="99808-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="99808-187">Använd följande kommando för att kontrol lera den spärrade statusen för ett användar konto:</span><span class="sxs-lookup"><span data-stu-id="99808-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="99808-188">Visa ytterligare egenskaps värden för konton</span><span class="sxs-lookup"><span data-stu-id="99808-188">View additional property values for accounts</span></span>

<span data-ttu-id="99808-189">Som standard visar cmdleten **Get-MsolUser** dessa tre egenskaper för användar konton:</span><span class="sxs-lookup"><span data-stu-id="99808-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="99808-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="99808-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="99808-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="99808-191">DisplayName</span></span>
    
- <span data-ttu-id="99808-192">Ärlicensierad</span><span class="sxs-lookup"><span data-stu-id="99808-192">isLicensed</span></span>
    
<span data-ttu-id="99808-193">Om du behöver fler egenskaper, till exempel den avdelning där användaren arbetar och det land/den region där de använder Microsoft 365-tjänsterna, kan du köra **Get-MsolUser** i kombination med **Välj** cmdlet för att ange listan över användar konto egenskaper.</span><span class="sxs-lookup"><span data-stu-id="99808-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="99808-194">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="99808-195">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="99808-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="99808-196">Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="99808-197">Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="99808-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="99808-198">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="99808-199">Med **Välj** cmdlet kan du välja vilka egenskaper du vill visa.</span><span class="sxs-lookup"><span data-stu-id="99808-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="99808-200">Använd jokertecknet (\*) om du vill visa alla egenskaper för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="99808-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="99808-201">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="99808-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="99808-202">Om du vill veta mer om listan med konton som ska visas kan du även använda **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="99808-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="99808-203">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="99808-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="99808-204">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="99808-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="99808-205">Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="99808-206">Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="99808-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="99808-207">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton som egenskapen UsageLocation User Account (\*\* $ \_ . UsageLocation**) är inte angivet (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="99808-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="99808-208">Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="99808-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="99808-209">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="99808-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="99808-210">Om du använder Directory-synkronisering för att skapa och hantera dina Microsoft 365-användare kan du Visa det lokala kontot som en Microsoft 365-användare har projicerats från.</span><span class="sxs-lookup"><span data-stu-id="99808-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="99808-211">Följande exempel förutsätter att:</span><span class="sxs-lookup"><span data-stu-id="99808-211">The following example assumes that:</span></span>

- <span data-ttu-id="99808-212">Azure AD Connect är konfigurerat för att använda standard käll ankaret för ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="99808-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="99808-213">(Mer information om hur du konfigurerar käll ankare finns i [Azure AD Connect: design koncept](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="99808-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="99808-214">Active Directory Domain Services-modulen för PowerShell har installerats (se [RSAT-verktyg](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="99808-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="99808-215">Se även</span><span class="sxs-lookup"><span data-stu-id="99808-215">See also</span></span>

[<span data-ttu-id="99808-216">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="99808-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="99808-217">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="99808-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="99808-218">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="99808-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
