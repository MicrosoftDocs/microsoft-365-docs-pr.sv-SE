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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357904"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="f0e2c-103">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e2c-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="f0e2c-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0e2c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f0e2c-105">Även om du kan använda administrations centret för Microsoft 365 för att Visa kontona för din Microsoft 365-klient organisation kan du också använda PowerShell för Microsoft 365 och göra vissa saker som administrations centret inte kan.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f0e2c-106">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="f0e2c-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f0e2c-107">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="f0e2c-108">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="f0e2c-108">View all accounts</span></span>

<span data-ttu-id="f0e2c-109">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="f0e2c-110">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="f0e2c-111">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="f0e2c-111">View a specific account</span></span>

<span data-ttu-id="f0e2c-112">Om du vill visa ett specifikt användar konto fyller du i användar kontots namn för inloggnings konto, som även kallas UPN (User Principal Name), tar bort tecknen "<" och ">" och kör det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="f0e2c-113">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="f0e2c-114">Visa ytterligare egenskaps värden för ett visst konto</span><span class="sxs-lookup"><span data-stu-id="f0e2c-114">View additional property values for a specific account</span></span>

<span data-ttu-id="f0e2c-115">Som standard visar cmdleten **Get-AzureADUser** bara egenskaperna ObjectID, DisplayName och userPrincipalName för konton.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="f0e2c-116">Om du vill veta mer om listan med egenskaper att Visa kan du använda **Select** -cmdleten i kombination med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f0e2c-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f0e2c-117">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f0e2c-118">Här visas ett exempel kommando som visar visnings namn, avdelning och UsageLocation för varje användar konto:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="f0e2c-119">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f0e2c-120">Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="f0e2c-121">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="f0e2c-122">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f0e2c-123">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f0e2c-124">Du kan till exempel kontrol lera den aktiverade statusen för ett visst användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="f0e2c-125">Visa synkroniseringsstatus för kontot</span><span class="sxs-lookup"><span data-stu-id="f0e2c-125">View account synchronization status</span></span>

<span data-ttu-id="f0e2c-126">Användar konton har två källor; Windows Server Active Directory (AD) som är konton som synkroniserar från lokala annonser till molnet och Azure AD som är direkt skapade i molnet.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="f0e2c-127">Det här kommandot instruerar PowerShell att hämta alla användare som har attributet **DirSyncEnabled** angivet till true.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="f0e2c-128">Den kan användas för att hämta konton som synkroniseras från en lokal annons.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="f0e2c-129">Det här kommandot instruerar PowerShell att hämta alla användare som har attributet **DirSyncEnabled** angett till falskt.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="f0e2c-130">Den kan användas för att hämta moln konton.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="f0e2c-131">Visa vissa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="f0e2c-131">View some accounts based on a common property</span></span>

<span data-ttu-id="f0e2c-132">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f0e2c-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f0e2c-133">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f0e2c-134">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f0e2c-135">Det här kommandot instruerar Azure Active Directory PowerShell för Graph till:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="f0e2c-136">Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="f0e2c-137">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="f0e2c-138">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="f0e2c-139">Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f0e2c-140">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f0e2c-141">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f0e2c-142">I den här listan är till exempel **ort** namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-142">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="f0e2c-143">Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-143">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f0e2c-144">Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f0e2c-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f0e2c-145">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**. > [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f0e2c-146">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad> se [var](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) du kan få mer information.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f0e2c-147">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e2c-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f0e2c-148">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="f0e2c-149">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="f0e2c-149">View all accounts</span></span>

<span data-ttu-id="f0e2c-150">Om du vill visa hela listan över användar konton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="f0e2c-151">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f0e2c-152">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f0e2c-153">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f0e2c-154">Cmdleten **Get-MsolUser** har också en uppsättning parametrar som filtrerar uppsättningen med användar konton.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="f0e2c-155">Om du till exempel vill visa en lista över ej licensierade användare (användare som har lagts till i Microsoft 365 men ännu inte har licensierats till att använda någon av tjänsterna) kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="f0e2c-156">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f0e2c-157">Mer information om ytterligare parametrar för att filtrera visningen av uppsättningen användar konton som visas finns i [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="f0e2c-158">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="f0e2c-158">View a specific account</span></span>

<span data-ttu-id="f0e2c-159">Om du vill visa ett specifikt användar konto fyller du i inloggnings namnet för användar kontot för användar kontot, även kallat användarens huvud namn (UPN), tar bort tecknen "<" och ">" och kör det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="f0e2c-160">Visa vissa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="f0e2c-160">View some accounts based on a common property</span></span>

<span data-ttu-id="f0e2c-161">Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="f0e2c-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="f0e2c-162">Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", vilket anger att PowerShell utför resultatet av ett kommando och skickar det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f0e2c-163">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f0e2c-164">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f0e2c-165">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="f0e2c-166">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="f0e2c-167">Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="f0e2c-168">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="f0e2c-169">Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f0e2c-170">Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f0e2c-171">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f0e2c-172">I den här listan är till exempel **ort** namnet på ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-172">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="f0e2c-173">Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-173">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f0e2c-174">Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f0e2c-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f0e2c-175">[användar kontots egenskaps namn] [jämförelse operator] värdepar **}**.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="f0e2c-176">[jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-** t för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f0e2c-177">[värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="f0e2c-178">Se [var](https://technet.microsoft.com/library/hh849715.aspx) du kan få mer information.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="f0e2c-179">Du kan kontrol lera den spärrade statusen för ett användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="f0e2c-180">Visa ytterligare egenskaps värden för konton</span><span class="sxs-lookup"><span data-stu-id="f0e2c-180">View additional property values for accounts</span></span>

<span data-ttu-id="f0e2c-181">Cmdleten **Get-MsolUser** med standard visar tre egenskaper för användar konton:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="f0e2c-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f0e2c-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="f0e2c-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f0e2c-183">DisplayName</span></span>
    
- <span data-ttu-id="f0e2c-184">Ärlicensierad</span><span class="sxs-lookup"><span data-stu-id="f0e2c-184">isLicensed</span></span>
    
<span data-ttu-id="f0e2c-185">Om du behöver ytterligare egenskaper, till exempel avdelningen som användaren arbetar med och landet/regionen där användaren använder Microsoft 365-tjänsterna, kan du köra **Get-MsolUser** i kombination med **Välj** cmdlet för att ange listan över användar konto egenskaper.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="f0e2c-186">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f0e2c-187">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f0e2c-188">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="f0e2c-189">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="f0e2c-190">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="f0e2c-191">Med **Välj** cmdlet kan du välja och välja vilka egenskaper du vill visa.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="f0e2c-192">Om du vill visa alla egenskaper för användar konton använder du jokertecknet (\*) för att visa alla för ett visst användar konto.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f0e2c-193">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f0e2c-194">Om du vill veta mer om listan med konton som ska visas kan du även använda **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="f0e2c-195">Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f0e2c-196">Det här kommandot instruerar PowerShell till att:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f0e2c-197">Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="f0e2c-198">Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ) och skicka den resulterande informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="f0e2c-199">Inuti klamrarna anger kommandot PowerShell för att bara hitta den uppsättning konton där egenskapen UsageLocation User Account ( \*\* $ \_ . UsageLocation\*\* ) är inte angivet ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="f0e2c-200">Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="f0e2c-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="f0e2c-201">Här visas information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="f0e2c-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="f0e2c-202">Om du använder Directory-synkronisering för att skapa och hantera dina Microsoft 365-användare kan du Visa vilka lokala konton en Microsoft 365-användare har projicerat från.</span><span class="sxs-lookup"><span data-stu-id="f0e2c-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="f0e2c-203">Följande förutsätter att Azure AD Connect är konfigurerat för att använda standard käll ankaret för ObjectGUID (mer information om hur du konfigurerar käll ankare finns i [Azure AD Connect: design koncept](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) och förutsätter att Active Directory Domain Services-modulen för PowerShell har installerats (se [rsat tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="f0e2c-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="f0e2c-204">Se även</span><span class="sxs-lookup"><span data-stu-id="f0e2c-204">See also</span></span>

[<span data-ttu-id="f0e2c-205">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e2c-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f0e2c-206">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e2c-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f0e2c-207">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0e2c-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
