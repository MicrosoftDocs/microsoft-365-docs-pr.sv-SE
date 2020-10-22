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
description: I den här artikeln lär du dig hur snabbt och enkelt använder PowerShell för Microsoft 365 för att tilldela administratörs roller till användar konton.
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655953"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="76214-103">Tilldela administratörs roller till Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="76214-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="76214-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="76214-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="76214-105">Du kan snabbt och enkelt tilldela administratörs roller till användar konton med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76214-105">You can quickly and easily assign admin roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="76214-106">[Lär dig hur du tilldelar administratörs roller till användar konton](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) med Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="76214-106">[Learn how to assign admin roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="76214-107">En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="76214-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="76214-108">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="76214-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="76214-109">Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="76214-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="76214-110">Därefter bestämmer du inloggnings namnet för det användar konto som du vill lägga till i en roll (till exempel: fredsm@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="76214-110">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com).</span></span> <span data-ttu-id="76214-111">Detta kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="76214-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="76214-112">Därefter bestämmer du namnet på administratörs rollen.</span><span class="sxs-lookup"><span data-stu-id="76214-112">Next, determine the name of the admin role.</span></span> <span data-ttu-id="76214-113">Använd den här [listan över behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="76214-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="76214-114">Var uppmärksam på anteckningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="76214-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="76214-115">Vissa rollnamn är olika för Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76214-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="76214-116">Rollen "SharePoint-administratör" i administrations centret för Microsoft 365 heter till exempel "SharePoint service Administrator" för Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76214-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="76214-117">Fyll i inloggnings-och rollnamn och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="76214-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
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

<span data-ttu-id="76214-118">Här är ett exempel på en färdigställd kommando uppsättning som tilldelar administratören för administratör för SharePoint-belindan@contoso.com till kontot.</span><span class="sxs-lookup"><span data-stu-id="76214-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator admin role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="76214-119">Använd dessa kommandon för att visa listan över användar namn för en viss administratörs roll.</span><span class="sxs-lookup"><span data-stu-id="76214-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="76214-120">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76214-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="76214-121">Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="76214-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="76214-122">För en ändring av en roll</span><span class="sxs-lookup"><span data-stu-id="76214-122">For a single role change</span></span>

<span data-ttu-id="76214-123">De vanligaste sätten för ett visst användar konto är med dess visnings namn eller e-postnamn, och det kallas också dess inloggnings namn eller huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="76214-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="76214-124">Visa användar konto namn</span><span class="sxs-lookup"><span data-stu-id="76214-124">Display names of user accounts</span></span>

<span data-ttu-id="76214-125">Om du använder för att arbeta med användar kontonas visnings namn bestämmer du följande:</span><span class="sxs-lookup"><span data-stu-id="76214-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="76214-126">Det användar konto som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="76214-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="76214-127">För att ange användar kontot måste du bestämma dess visnings namn.</span><span class="sxs-lookup"><span data-stu-id="76214-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="76214-128">Använd det här kommandot för att få ett fullständigt List konto:</span><span class="sxs-lookup"><span data-stu-id="76214-128">To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="76214-129">Det här kommandot visar visnings namnet för dina användar konton, sorterade efter visnings namnet, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="76214-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="76214-130">Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="76214-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="76214-131">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="76214-131">Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="76214-132">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="76214-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="76214-133">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76214-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="76214-134">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="76214-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="76214-135">Den roll du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="76214-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="76214-136">Använd det här kommandot för att visa listan över tillgängliga administratörs roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="76214-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="76214-137">När du har bestämt visnings namnet på kontot och namnet på administratörs rollen använder du dessa kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="76214-137">Once you have determined the Display Name of the account and the Name of the admin role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="76214-138">Kopiera kommandona och klistra in dem i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="76214-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="76214-139">För variablerna **$dispName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken.</span><span class="sxs-lookup"><span data-stu-id="76214-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="76214-140">Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="76214-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="76214-141">Du kan också använda Windows PowerShell ISE (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="76214-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="76214-142">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="76214-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="76214-143">Inloggnings namn för användar konton</span><span class="sxs-lookup"><span data-stu-id="76214-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="76214-144">Om du är van vid att arbeta med inloggnings namnen eller UPN: er för användar konton kan du bestämma följande.</span><span class="sxs-lookup"><span data-stu-id="76214-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="76214-145">Användar kontots UPN.</span><span class="sxs-lookup"><span data-stu-id="76214-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="76214-146">Om du inte redan känner till UPN använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="76214-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="76214-147">Det här kommandot visar UPN för dina användar konton, sorterade efter UPN, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="76214-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="76214-148">Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="76214-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="76214-149">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="76214-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="76214-150">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="76214-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="76214-151">Den roll du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="76214-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="76214-152">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="76214-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="76214-153">När du har kontots UPN-namn och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="76214-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="76214-154">Kopiera kommandona och klistra in dem i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="76214-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="76214-155">För variablerna **$upnName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken.</span><span class="sxs-lookup"><span data-stu-id="76214-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="76214-156">Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="76214-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="76214-157">Du kan också använda Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="76214-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="76214-158">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="76214-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="76214-159">Ändringar i flera roller</span><span class="sxs-lookup"><span data-stu-id="76214-159">Multiple role changes</span></span>

<span data-ttu-id="76214-160">Om du vill ändra flera roller kontrollerar du följande:</span><span class="sxs-lookup"><span data-stu-id="76214-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="76214-161">Vilka användar konton som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="76214-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="76214-162">Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visnings namn eller UPN.</span><span class="sxs-lookup"><span data-stu-id="76214-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="76214-163">Vilka roller du vill tilldela till varje användar konto.</span><span class="sxs-lookup"><span data-stu-id="76214-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="76214-164">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="76214-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="76214-165">Skapa sedan en CSV-textfil som innehåller fälten visnings namn eller UPN och rollnamn.</span><span class="sxs-lookup"><span data-stu-id="76214-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="76214-166">Det är enkelt att göra det i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="76214-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="76214-167">Här är ett exempel på visnings namn:</span><span class="sxs-lookup"><span data-stu-id="76214-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="76214-168">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="76214-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="76214-169">Här följer ett exempel på UPN:</span><span class="sxs-lookup"><span data-stu-id="76214-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="76214-170">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="76214-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="76214-171">Se även</span><span class="sxs-lookup"><span data-stu-id="76214-171">See also</span></span>

- [<span data-ttu-id="76214-172">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="76214-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="76214-173">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="76214-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="76214-174">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76214-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
