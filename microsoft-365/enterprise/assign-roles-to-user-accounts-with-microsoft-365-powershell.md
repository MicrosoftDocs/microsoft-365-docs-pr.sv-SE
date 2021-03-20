---
title: Tilldela roller till Microsoft 365-användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: I den här artikeln lär du dig hur snabbt och enkelt du använder PowerShell för Microsoft 365 för att tilldela administratörsroller till användarkonton.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905386"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="512ed-103">Tilldela administratörsroller till Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="512ed-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="512ed-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="512ed-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="512ed-105">Du kan enkelt tilldela roller till användarkonton med hjälp av PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="512ed-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="512ed-106">Läs om hur  [du tilldelar](../admin/add-users/assign-admin-roles.md) administratörsroller till användarkonton i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="512ed-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="512ed-107">En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="512ed-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="512ed-108">Använda Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="512ed-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="512ed-109">Använd först ett globalt administratörskonto för att [ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="512ed-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="512ed-110">Identifiera sedan inloggningsnamnet för det användarkonto som du vill lägga till i en roll (exempel: \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="512ed-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="512ed-111">Detta kallas även användarens huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="512ed-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="512ed-112">Bestäm sedan namnet på rollen.</span><span class="sxs-lookup"><span data-stu-id="512ed-112">Next, determine the name of the role.</span></span> <span data-ttu-id="512ed-113">Visa [behörigheter för administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="512ed-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="512ed-114">Var uppmärksam på anteckningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="512ed-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="512ed-115">Vissa rollnamn är olika för Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="512ed-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="512ed-116">*SharePoint-administratörsrollen* i administrationscentret för Microsoft 365 är till exempel *SharePoint-tjänstadministratör* i Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="512ed-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="512ed-117">Sedan fyller du i inloggnings- och rollnamnen och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="512ed-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="512ed-118">Här är ett exempel på en slutförd kommandouppsättning som tilldelar rollen SharePoint-tjänstadministratör till *\@ belindan-contoso.com konto:*</span><span class="sxs-lookup"><span data-stu-id="512ed-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="512ed-119">Använd de här kommandona för att visa listan med användarnamn för en specifik administratörsroll.</span><span class="sxs-lookup"><span data-stu-id="512ed-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="512ed-120">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="512ed-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="512ed-121">Använd först ett globalt administratörskonto för att [ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="512ed-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="512ed-122">För en enda rolländring</span><span class="sxs-lookup"><span data-stu-id="512ed-122">For a single role change</span></span>

<span data-ttu-id="512ed-123">De vanligaste sätten att ange användarkontot är med hjälp av visningsnamnet eller dess e-postnamn, som också kallas dess inloggningsnamn eller huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="512ed-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="512ed-124">Visa namn på användarkonton</span><span class="sxs-lookup"><span data-stu-id="512ed-124">Display names of user accounts</span></span>

<span data-ttu-id="512ed-125">Om du är van vid att arbeta med visningsnamnen för användarkonton bestämmer du följande information:</span><span class="sxs-lookup"><span data-stu-id="512ed-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="512ed-126">Det användarkonto som du vill konfigurera</span><span class="sxs-lookup"><span data-stu-id="512ed-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="512ed-127">Om du vill ange användarkontot måste du avgöra dess visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="512ed-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="512ed-128">Använd det här kommandot för att få en fullständig lista över konton:</span><span class="sxs-lookup"><span data-stu-id="512ed-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="512ed-129">Det här kommandot visar visningsnamnet för dina användarkonton, sorterade efter visningsnamnet, en skärmbild i taget.</span><span class="sxs-lookup"><span data-stu-id="512ed-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="512ed-130">Du kan filtrera listan till en  mindre uppsättning med hjälp av cmdleten Where.</span><span class="sxs-lookup"><span data-stu-id="512ed-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="512ed-131">Se följande exempel.</span><span class="sxs-lookup"><span data-stu-id="512ed-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="512ed-132">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="512ed-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="512ed-133">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="512ed-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="512ed-134">Det här kommandot visar endast användarkonton som visningsnamnet börjar på "John" för.</span><span class="sxs-lookup"><span data-stu-id="512ed-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="512ed-135">Den roll som du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="512ed-135">The role you want to assign</span></span>
    
    <span data-ttu-id="512ed-136">Använd det här kommandot för att visa listan med tillgängliga administratörsroller som du kan tilldela användarkonton:</span><span class="sxs-lookup"><span data-stu-id="512ed-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="512ed-137">När du har avgöra visningsnamnet för kontot och namnet på rollen använder du följande kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="512ed-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="512ed-138">Klistra in kommandona i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="512ed-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="512ed-139">Ersätt *$dispName $roleName* *beskrivningstexten* med deras värden för variablerna.</span><span class="sxs-lookup"><span data-stu-id="512ed-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="512ed-140">Ta bort \< and > tecknen men behåll citattecknen.</span><span class="sxs-lookup"><span data-stu-id="512ed-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="512ed-141">Klistra in de ändrade raderna i Microsoft Azure Active Directory-modulen för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="512ed-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="512ed-142">Alternativt kan du använda Windows PowerShell Integrated Script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="512ed-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="512ed-143">Här är ett exempel på en slutförd kommandouppsättning:</span><span class="sxs-lookup"><span data-stu-id="512ed-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="512ed-144">Inloggningsnamn på användarkonton</span><span class="sxs-lookup"><span data-stu-id="512ed-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="512ed-145">Om du är van att arbeta med inloggningsnamn eller UPN för användarkonton ska du fastställa följande information:</span><span class="sxs-lookup"><span data-stu-id="512ed-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="512ed-146">Användarkontons UPN</span><span class="sxs-lookup"><span data-stu-id="512ed-146">The user account's UPN</span></span>
    
    <span data-ttu-id="512ed-147">Om du inte känner till UPN kan du använda det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="512ed-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="512ed-148">Det här kommandot visar UPN för dina användarkonton, sorterade efter UPN, en skärmbild i taget.</span><span class="sxs-lookup"><span data-stu-id="512ed-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="512ed-149">Du kan  använda cmdleten Where för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="512ed-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="512ed-150">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="512ed-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="512ed-151">Det här kommandot visar endast användarkonton som visningsnamnet börjar på "John" för.</span><span class="sxs-lookup"><span data-stu-id="512ed-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="512ed-152">Den roll som du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="512ed-152">The role you want to assign</span></span>
    
    <span data-ttu-id="512ed-153">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela användarkonton:</span><span class="sxs-lookup"><span data-stu-id="512ed-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="512ed-154">När du har UPN för kontot och namnet på rollen kan du använda de här kommandona för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="512ed-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="512ed-155">Kopiera kommandona och klistra in dem i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="512ed-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="512ed-156">För **$upnName** och **$roleName** variabler.</span><span class="sxs-lookup"><span data-stu-id="512ed-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="512ed-157">Ersätt beskrivningstexten med deras värden.</span><span class="sxs-lookup"><span data-stu-id="512ed-157">Replace the description text with their values.</span></span> <span data-ttu-id="512ed-158">Ta bort \< and > tecknen men behåll citattecknen.</span><span class="sxs-lookup"><span data-stu-id="512ed-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="512ed-159">Klistra in de ändrade raderna i fönstret Microsoft Azure Active Directory-modulen för Windows PowerShell för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="512ed-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="512ed-160">Alternativt kan du använda Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="512ed-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="512ed-161">Här är ett exempel på en slutförd kommandouppsättning:</span><span class="sxs-lookup"><span data-stu-id="512ed-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="512ed-162">Flera rolländringar</span><span class="sxs-lookup"><span data-stu-id="512ed-162">Multiple role changes</span></span>

<span data-ttu-id="512ed-163">Bestäm följande information för flerrollsändringar:</span><span class="sxs-lookup"><span data-stu-id="512ed-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="512ed-164">Vilka användarkonton du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="512ed-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="512ed-165">Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visningsnamn eller UPN-namn.</span><span class="sxs-lookup"><span data-stu-id="512ed-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="512ed-166">Vilka roller du vill tilldela varje användarkonto.</span><span class="sxs-lookup"><span data-stu-id="512ed-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="512ed-167">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela användarkonton:</span><span class="sxs-lookup"><span data-stu-id="512ed-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="512ed-168">Skapa sedan en fil med kommaavgränsade värden (CSV) med visningsnamnet eller UPN- och rollnamnsfälten.</span><span class="sxs-lookup"><span data-stu-id="512ed-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="512ed-169">Du kan göra det enkelt i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="512ed-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="512ed-170">Här är ett exempel för visningsnamn:</span><span class="sxs-lookup"><span data-stu-id="512ed-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="512ed-171">Fyll sedan i CSV-filens plats och kör resulterande kommandon i PowerShell-kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="512ed-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="512ed-172">Här är ett exempel för UPN:er:</span><span class="sxs-lookup"><span data-stu-id="512ed-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="512ed-173">Fyll sedan i CSV-filens plats och kör resulterande kommandon i PowerShell-kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="512ed-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="512ed-174">Se även</span><span class="sxs-lookup"><span data-stu-id="512ed-174">See also</span></span>

- [<span data-ttu-id="512ed-175">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="512ed-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="512ed-176">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="512ed-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="512ed-177">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="512ed-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)