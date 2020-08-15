---
title: Tilldela roller till Microsoft 365-användarkonton med PowerShell
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: I den här artikeln lär du dig hur snabbt och enkelt kan använda PowerShell för Microsoft 365 för att tilldela roller till användar konton.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694362"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="8083f-103">Tilldela roller till Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8083f-103">Assign roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="8083f-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8083f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8083f-105">Du kan snabbt och enkelt tilldela roller till användar konton med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8083f-105">You can quickly and easily assign roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="8083f-106">Information om hur du tilldelar roller till användar konton med Microsoft 365 Admin Center finns i [de här anvisningarna](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="8083f-106">To assign roles to user accounts with the Microsoft 365 admin center, see [these instructions](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8083f-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="8083f-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8083f-108">Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="8083f-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="8083f-109">Därefter bestämmer du inloggnings namnet för det användar konto som du vill lägga till i en roll (till exempel: fredsm@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8083f-109">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com).</span></span> <span data-ttu-id="8083f-110">Detta kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="8083f-110">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="8083f-111">Därefter bestämmer du namnet på rollen.</span><span class="sxs-lookup"><span data-stu-id="8083f-111">Next, determine the name of the role.</span></span> <span data-ttu-id="8083f-112">Använd den här [listan över behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="8083f-112">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="8083f-113">Var uppmärksam på anteckningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8083f-113">Pay attention to the notes in this article.</span></span> <span data-ttu-id="8083f-114">Vissa rollnamn är olika för Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8083f-114">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="8083f-115">Rollen "SharePoint-administratör" i administrations centret för Microsoft 365 heter till exempel "SharePoint service Administrator" för Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8083f-115">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="8083f-116">Fyll i inloggnings-och rollnamn och kör dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="8083f-116">Next, fill in the sign-in and role names and run these commands.</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="8083f-117">Här är ett exempel på en färdigställd kommando uppsättning som tilldelar rollen som administratör för SharePoint-belindan@contoso.com till kontot konto:</span><span class="sxs-lookup"><span data-stu-id="8083f-117">Here is an example of a completed command set that assigns the SharePoint Service Administrator role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="8083f-118">Använd dessa kommandon för att visa listan över användar namn för en viss roll.</span><span class="sxs-lookup"><span data-stu-id="8083f-118">To display the list of user names for a specific role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8083f-119">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8083f-119">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8083f-120">Först [ansluter du till din Microsoft 365-klient](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="8083f-120">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="8083f-121">För en ändring av en roll</span><span class="sxs-lookup"><span data-stu-id="8083f-121">For a single role change</span></span>

<span data-ttu-id="8083f-122">De vanligaste sätten för ett visst användar konto är med dess visnings namn eller e-postnamn, och det kallas också dess inloggnings namn eller huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="8083f-122">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="8083f-123">Visa användar konto namn</span><span class="sxs-lookup"><span data-stu-id="8083f-123">Display names of user accounts</span></span>

<span data-ttu-id="8083f-124">Om du använder för att arbeta med användar kontonas visnings namn bestämmer du följande:</span><span class="sxs-lookup"><span data-stu-id="8083f-124">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="8083f-125">Det användar konto som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="8083f-125">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="8083f-126">För att ange användar kontot måste du bestämma dess visnings namn.</span><span class="sxs-lookup"><span data-stu-id="8083f-126">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="8083f-127">Använd det här kommandot för att få ett fullständigt List konto:</span><span class="sxs-lookup"><span data-stu-id="8083f-127">To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="8083f-128">Det här kommandot visar visnings namnet för dina användar konton, sorterade efter visnings namnet, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="8083f-128">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="8083f-129">Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="8083f-129">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="8083f-130">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="8083f-130">Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="8083f-131">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="8083f-131">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="8083f-132">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8083f-132">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="8083f-133">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="8083f-133">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="8083f-134">Den roll du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="8083f-134">The role you want to assign.</span></span>
    
    <span data-ttu-id="8083f-135">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="8083f-135">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="8083f-136">När du har bestämt visnings namnet på kontot och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="8083f-136">Once you have determined the Display Name of the account and the Name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="8083f-137">Kopiera kommandona och klistra in dem i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="8083f-137">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="8083f-138">För variablerna **$dispName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken.</span><span class="sxs-lookup"><span data-stu-id="8083f-138">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="8083f-139">Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="8083f-139">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="8083f-140">Du kan också använda Windows PowerShell ISE (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="8083f-140">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="8083f-141">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="8083f-141">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="8083f-142">Inloggnings namn för användar konton</span><span class="sxs-lookup"><span data-stu-id="8083f-142">Sign-in names of user accounts</span></span>

<span data-ttu-id="8083f-143">Om du är van vid att arbeta med inloggnings namnen eller UPN: er för användar konton kan du bestämma följande.</span><span class="sxs-lookup"><span data-stu-id="8083f-143">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="8083f-144">Användar kontots UPN.</span><span class="sxs-lookup"><span data-stu-id="8083f-144">The user account's UPN.</span></span>
    
    <span data-ttu-id="8083f-145">Om du inte redan känner till UPN använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="8083f-145">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="8083f-146">Det här kommandot visar UPN för dina användar konton, sorterade efter UPN, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="8083f-146">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="8083f-147">Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="8083f-147">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="8083f-148">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="8083f-148">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="8083f-149">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="8083f-149">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="8083f-150">Den roll du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="8083f-150">The role you want to assign.</span></span>
    
    <span data-ttu-id="8083f-151">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="8083f-151">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="8083f-152">När du har kontots UPN-namn och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="8083f-152">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="8083f-153">Kopiera kommandona och klistra in dem i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="8083f-153">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="8083f-154">För variablerna **$upnName** och **$roleName** ersätter du beskrivningen med deras värden, tar bort \< and > tecknen och lämnar citationstecken.</span><span class="sxs-lookup"><span data-stu-id="8083f-154">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="8083f-155">Kopiera de ändrade raderna och klistra in dem i din Windows Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="8083f-155">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="8083f-156">Du kan också använda Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="8083f-156">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="8083f-157">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="8083f-157">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="8083f-158">Ändringar i flera roller</span><span class="sxs-lookup"><span data-stu-id="8083f-158">Multiple role changes</span></span>

<span data-ttu-id="8083f-159">Om du vill ändra flera roller kontrollerar du följande:</span><span class="sxs-lookup"><span data-stu-id="8083f-159">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="8083f-160">Vilka användar konton som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="8083f-160">Which user accounts that you want to configure.</span></span> <span data-ttu-id="8083f-161">Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visnings namn eller UPN.</span><span class="sxs-lookup"><span data-stu-id="8083f-161">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="8083f-162">Vilka roller du vill tilldela till varje användar konto.</span><span class="sxs-lookup"><span data-stu-id="8083f-162">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="8083f-163">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="8083f-163">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="8083f-164">Skapa sedan en CSV-textfil som innehåller fälten visnings namn eller UPN och rollnamn.</span><span class="sxs-lookup"><span data-stu-id="8083f-164">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="8083f-165">Det är enkelt att göra det i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="8083f-165">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="8083f-166">Här är ett exempel på visnings namn:</span><span class="sxs-lookup"><span data-stu-id="8083f-166">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="8083f-167">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="8083f-167">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="8083f-168">Här följer ett exempel på UPN:</span><span class="sxs-lookup"><span data-stu-id="8083f-168">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="8083f-169">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="8083f-169">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="8083f-170">Se även</span><span class="sxs-lookup"><span data-stu-id="8083f-170">See also</span></span>

- [<span data-ttu-id="8083f-171">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8083f-171">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8083f-172">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8083f-172">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8083f-173">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8083f-173">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
