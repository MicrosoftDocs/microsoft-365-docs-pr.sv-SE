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
description: Lär dig hur du visar, listar eller visar Microsoft 365-användarkonton på olika sätt med PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924654"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="32569-103">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="32569-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="32569-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="32569-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="32569-105">Du kan använda Microsoft 365 administrationscenter för att visa kontona för Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="32569-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="32569-106">PowerShell för Microsoft 365 detta men ger även ytterligare funktioner.</span><span class="sxs-lookup"><span data-stu-id="32569-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="32569-107">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="32569-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="32569-108">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="32569-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="32569-109">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="32569-109">View all accounts</span></span>

<span data-ttu-id="32569-110">Om du vill visa hela listan med användarkonton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="32569-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="32569-111">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="32569-112">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="32569-112">View a specific account</span></span>

<span data-ttu-id="32569-113">Om du vill visa ett specifikt användarkonto kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="32569-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="32569-114">Fyll i inloggningskontonamnet för användarkontot, som också kallas huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="32569-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="32569-115">Ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="32569-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="32569-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="32569-117">Visa ytterligare egenskapsvärden för ett visst konto</span><span class="sxs-lookup"><span data-stu-id="32569-117">View additional property values for a specific account</span></span>

<span data-ttu-id="32569-118">Som standard visar **cmdlet:en Get-AzureADUser** endast egenskaperna *ObjectID,* *DisplayName* *och UserPrincipalName* för konton.</span><span class="sxs-lookup"><span data-stu-id="32569-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="32569-119">Om du vill vara mer selektiv när det gäller egenskaper som ska visas använder du cmdleten **Select** i kombination med cmdleten **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="32569-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="32569-120">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om för Azure Active Directory PowerShell för Graph att ta resultaten från ett kommando och skicka det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="32569-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="32569-121">Här är ett exempelkommando som visar *DisplayName,* *Department* och *UsageLocation* för varje användarkonto:</span><span class="sxs-lookup"><span data-stu-id="32569-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="32569-122">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="32569-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="32569-123">Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="32569-124">Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**</span><span class="sxs-lookup"><span data-stu-id="32569-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="32569-125">Om du vill visa alla egenskaper för  ett visst användarkonto använder du cmdleten Select och jokertecknet (\*).</span><span class="sxs-lookup"><span data-stu-id="32569-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="32569-126">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="32569-127">Ett annat exempel är att köra följande kommando för att kontrollera aktiverad status för ett visst användarkonto:</span><span class="sxs-lookup"><span data-stu-id="32569-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="32569-128">Visa status för kontosynkronisering</span><span class="sxs-lookup"><span data-stu-id="32569-128">View account synchronization status</span></span>

<span data-ttu-id="32569-129">Användarkonton har två källor:</span><span class="sxs-lookup"><span data-stu-id="32569-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="32569-130">Windows Server Active Directory (AD), som är konton som synkroniseras från lokal AD till molnet.</span><span class="sxs-lookup"><span data-stu-id="32569-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="32569-131">Azure Active Directory (Azure AD) AD-konton, som skapas direkt i molnet.</span><span class="sxs-lookup"><span data-stu-id="32569-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="32569-132">Följande kommando instruerar PowerShell att få alla användare som har *attributet DirSyncEnabled* inställt på *Sant.*</span><span class="sxs-lookup"><span data-stu-id="32569-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="32569-133">Du kan använda den för att hitta konton som synkroniseras från den lokala AD.</span><span class="sxs-lookup"><span data-stu-id="32569-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="32569-134">Följande kommando instruerar PowerShell att få alla användare som har *attributet DirSyncEnabled* inställt på *Falskt.*</span><span class="sxs-lookup"><span data-stu-id="32569-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="32569-135">Du kan använda det för att hitta konton som endast är molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="32569-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="32569-136">Visa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="32569-136">View accounts based on a common property</span></span>

<span data-ttu-id="32569-137">Om du vill vara mer selektiv när det gäller listan med konton som ska visas kan du använda cmdleten **Where** i kombination med **cmdleten Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="32569-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="32569-138">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om för Azure Active Directory PowerShell för Graph att ta resultaten från ett kommando och skicka det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="32569-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="32569-139">Här är ett exempelkommando som endast visar de användarkonton som har en ospecificerad användningsplats:</span><span class="sxs-lookup"><span data-stu-id="32569-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="32569-140">Det här kommandot instruerar Azure Active Directory PowerShell för Graph att:</span><span class="sxs-lookup"><span data-stu-id="32569-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="32569-141">Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="32569-142">Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="32569-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="32569-143">Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="32569-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="32569-144">Egenskapen **Användningsbeläggning** är bara en av många egenskaper som är kopplade till ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="32569-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="32569-145">Om du vill visa alla egenskaper för  ett visst användarkonto använder du cmdleten Select och jokertecknet (\*).</span><span class="sxs-lookup"><span data-stu-id="32569-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="32569-146">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="32569-147">Ort **är** till exempel namnet på en användarkontoegenskap.</span><span class="sxs-lookup"><span data-stu-id="32569-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="32569-148">Du kan använda följande kommando för att lista alla konton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="32569-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="32569-149">Syntaxen för  cmdleten Where i de här exemplen **är Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="32569-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="32569-150">[användarnamn för användarkontoegenskap] [jämförelseoperator] [värde] **}**.> [jämförelseoperator] är **-eq** för lika med, **-ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.</span><span class="sxs-lookup"><span data-stu-id="32569-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="32569-151">[värde] är vanligtvis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** ospecificerat värde.</span><span class="sxs-lookup"><span data-stu-id="32569-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="32569-152">Mer information finns i [Var](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="32569-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="32569-153">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32569-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="32569-154">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="32569-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="32569-155">Visa alla konton</span><span class="sxs-lookup"><span data-stu-id="32569-155">View all accounts</span></span>

<span data-ttu-id="32569-156">Om du vill visa hela listan med användarkonton kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="32569-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="32569-157">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="32569-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="32569-158">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32569-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="32569-159">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="32569-160">**Cmdlet:en Get-MsolUser** har också en uppsättning parametrar för att filtrera uppsättningen användarkonton som visas.</span><span class="sxs-lookup"><span data-stu-id="32569-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="32569-161">Kör följande kommando för listan över olicensierade användare (användare som har lagts till i Microsoft 365 men ännu inte har licensierats för att använda någon av tjänsterna):</span><span class="sxs-lookup"><span data-stu-id="32569-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="32569-162">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="32569-163">Mer information om ytterligare parametrar för att filtrera den uppsättning användarkonton som visas finns i [Get-MsolUser.](/previous-versions/azure/dn194133(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="32569-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="32569-164">Visa ett specifikt konto</span><span class="sxs-lookup"><span data-stu-id="32569-164">View a specific account</span></span>

<span data-ttu-id="32569-165">Om du vill visa ett specifikt användarkonto kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="32569-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="32569-166">Fyll i inloggningsnamnet för användarkontot, som också kallas användarens huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="32569-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="32569-167">Ta bort tecknen "<" och ">".</span><span class="sxs-lookup"><span data-stu-id="32569-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="32569-168">Visa konton baserat på en gemensam egenskap</span><span class="sxs-lookup"><span data-stu-id="32569-168">View accounts based on a common property</span></span>

<span data-ttu-id="32569-169">Om du vill vara mer selektiv när det gäller listan med konton som ska visas kan du använda cmdleten **Where** i kombination med cmdleten **Get-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="32569-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="32569-170">Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som säger till PowerShell att ta resultatet från ett kommando och skicka det till nästa kommando.</span><span class="sxs-lookup"><span data-stu-id="32569-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="32569-171">Här är ett exempel som endast visar de användarkonton som har en ospecificerad användningsplats:</span><span class="sxs-lookup"><span data-stu-id="32569-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="32569-172">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="32569-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="32569-173">Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="32569-174">Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="32569-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="32569-175">Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="32569-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="32569-176">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="32569-177">Egenskapen *Användningsbeläggning* är bara en av många egenskaper som är kopplade till ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="32569-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="32569-178">Om du vill visa alla egenskaper för användarkonton använder du cmdleten **Select** och jokertecknet (\*) för att visa dem alla för ett visst användarkonto.</span><span class="sxs-lookup"><span data-stu-id="32569-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="32569-179">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="32569-180">Ort *är* till exempel namnet på en användarkontoegenskap.</span><span class="sxs-lookup"><span data-stu-id="32569-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="32569-181">Du kan använda följande kommando för att visa alla användarkonton för användare som bor i London:</span><span class="sxs-lookup"><span data-stu-id="32569-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="32569-182">Syntaxen för  cmdleten Where i de här exemplen **är Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="32569-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="32569-183">[användarnamn för användarkontoegenskap] [jämförelseoperator] [värde] **}**.</span><span class="sxs-lookup"><span data-stu-id="32569-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="32569-184">[jämförelseoperator] är **-eq** för lika med, **-ne** för inte lika med, **-lt** för mindre än, **-gt för** större än och andra.</span><span class="sxs-lookup"><span data-stu-id="32569-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="32569-185">[värde] är vanligtvis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** ospecificerat värde.</span><span class="sxs-lookup"><span data-stu-id="32569-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="32569-186">Mer information finns i [Var](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="32569-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="32569-187">Om du vill kontrollera blockerad status för ett användarkonto använder du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="32569-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="32569-188">Visa ytterligare egenskapsvärden för konton</span><span class="sxs-lookup"><span data-stu-id="32569-188">View additional property values for accounts</span></span>

<span data-ttu-id="32569-189">Som standard visar **cmdlet:en Get-MsolUser** dessa tre egenskaper för användarkonton:</span><span class="sxs-lookup"><span data-stu-id="32569-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="32569-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="32569-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="32569-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="32569-191">DisplayName</span></span>
    
- <span data-ttu-id="32569-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="32569-192">isLicensed</span></span>
    
<span data-ttu-id="32569-193">Om du behöver ytterligare egenskaper, till exempel avdelningen där användaren arbetar och landet/regionen där de använder Microsoft 365-tjänster, kan du köra **Get-MsolUser** i kombination med cmdleten **Select** och ange listan med egenskaper för användarkonton.</span><span class="sxs-lookup"><span data-stu-id="32569-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="32569-194">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="32569-195">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="32569-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="32569-196">Hämta all information om användarkontona **(Get-MsolUser)** och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="32569-197">Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**</span><span class="sxs-lookup"><span data-stu-id="32569-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="32569-198">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="32569-199">Med  cmdleten Select kan du välja vilka egenskaper som ska visas.</span><span class="sxs-lookup"><span data-stu-id="32569-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="32569-200">Om du vill visa alla egenskaper för ett visst användarkonto använder du jokertecknet (\*).</span><span class="sxs-lookup"><span data-stu-id="32569-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="32569-201">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="32569-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="32569-202">Om du vill vara mer selektiv när det gäller  listan med konton som ska visas kan du också använda cmdleten Where.</span><span class="sxs-lookup"><span data-stu-id="32569-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="32569-203">Här är ett exempelkommando som endast visar de användarkonton som har en ospecificerad användningsplats:</span><span class="sxs-lookup"><span data-stu-id="32569-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="32569-204">Det här kommandot instruerar PowerShell att:</span><span class="sxs-lookup"><span data-stu-id="32569-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="32569-205">Hämta all information om användarkontona **(Get-MsolUser)** och skicka det till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="32569-206">Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null} )** och skicka informationen till nästa kommando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="32569-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="32569-207">Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="32569-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="32569-208">Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**</span><span class="sxs-lookup"><span data-stu-id="32569-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="32569-209">Du bör få information som liknar den här:</span><span class="sxs-lookup"><span data-stu-id="32569-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="32569-210">Om du använder katalogsynkronisering för att skapa och hantera dina Microsoft 365-användare kan du visa det lokala konto som en Microsoft 365-användare har projicerats från.</span><span class="sxs-lookup"><span data-stu-id="32569-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="32569-211">I följande exempel antas att:</span><span class="sxs-lookup"><span data-stu-id="32569-211">The following example assumes that:</span></span>

- <span data-ttu-id="32569-212">Azure AD Anslut är konfigurerat att använda standardkällans fästpunkt för ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="32569-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="32569-213">(Mer information om hur du konfigurerar en fästpunkt för källor finns [i Azure AD Anslut: Designkoncept](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="32569-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="32569-214">Modulen Active Directory Domain Services för PowerShell har installerats (se [RSAT-verktyg](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="32569-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="32569-215">Se även</span><span class="sxs-lookup"><span data-stu-id="32569-215">See also</span></span>

[<span data-ttu-id="32569-216">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="32569-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="32569-217">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="32569-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="32569-218">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32569-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)