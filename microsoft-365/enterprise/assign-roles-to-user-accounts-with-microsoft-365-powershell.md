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
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754204"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="87cd4-103">Tilldela administratörs roller till Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cd4-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="87cd4-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="87cd4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="87cd4-105">Du kan enkelt tilldela roller till användar konton med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87cd4-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="87cd4-106">Lär dig hur du  [tilldelar administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) till användar konton med Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="87cd4-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="87cd4-107">En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="87cd4-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="87cd4-108">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="87cd4-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="87cd4-109">Använd först ett globalt administratörs konto för att [ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="87cd4-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="87cd4-110">Sedan identifierar du inloggnings namnet för det användar konto som du vill lägga till i en roll (till exempel: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="87cd4-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="87cd4-111">Detta kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="87cd4-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="87cd4-112">Därefter bestämmer du namnet på rollen.</span><span class="sxs-lookup"><span data-stu-id="87cd4-112">Next, determine the name of the role.</span></span> <span data-ttu-id="87cd4-113">Se [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="87cd4-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="87cd4-114">Var uppmärksam på anteckningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="87cd4-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="87cd4-115">Vissa rollnamn är olika för Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87cd4-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="87cd4-116">*Administratörs* rollen för SharePoint i administrations centret för Microsoft 365 är till exempel *SharePoint service Administrator* i Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87cd4-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="87cd4-117">Fyll i inloggnings-och roll namnen och kör dessa kommandon:</span><span class="sxs-lookup"><span data-stu-id="87cd4-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
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

<span data-ttu-id="87cd4-118">Här är ett exempel på en färdigställd kommando uppsättning som tilldelar rollen SharePoint service-administratör till det bekanta \* \@ contoso.com\* -kontot:</span><span class="sxs-lookup"><span data-stu-id="87cd4-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
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

<span data-ttu-id="87cd4-119">Använd dessa kommandon för att visa listan över användar namn för en viss administratörs roll.</span><span class="sxs-lookup"><span data-stu-id="87cd4-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="87cd4-120">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cd4-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="87cd4-121">Använd först ett globalt administratörs konto för att [ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="87cd4-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="87cd4-122">För en ändring av en roll</span><span class="sxs-lookup"><span data-stu-id="87cd4-122">For a single role change</span></span>

<span data-ttu-id="87cd4-123">De vanligaste sätten att ange användar konto är med hjälp av dess visnings namn eller e-postnamn, som även kallas för dess inloggnings namn eller huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="87cd4-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="87cd4-124">Visa användar konto namn</span><span class="sxs-lookup"><span data-stu-id="87cd4-124">Display names of user accounts</span></span>

<span data-ttu-id="87cd4-125">Om du använder för att arbeta med användar kontonas visnings namn bestämmer du följande information:</span><span class="sxs-lookup"><span data-stu-id="87cd4-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="87cd4-126">Det användar konto som du vill konfigurera</span><span class="sxs-lookup"><span data-stu-id="87cd4-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="87cd4-127">För att ange användar kontot måste du bestämma dess visnings namn.</span><span class="sxs-lookup"><span data-stu-id="87cd4-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="87cd4-128">Använd det här kommandot för att få en fullständig lista över konton:</span><span class="sxs-lookup"><span data-stu-id="87cd4-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="87cd4-129">Det här kommandot visar visnings namnet för dina användar konton, sorterade efter visnings namnet, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="87cd4-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="87cd4-130">Du kan filtrera listan till en mindre uppsättning med hjälp av **WHERE** -cmdleten.</span><span class="sxs-lookup"><span data-stu-id="87cd4-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="87cd4-131">Se följande exempel.</span><span class="sxs-lookup"><span data-stu-id="87cd4-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="87cd4-132">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* .</span><span class="sxs-lookup"><span data-stu-id="87cd4-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="87cd4-133">Kör dessa cmdletar från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87cd4-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="87cd4-134">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="87cd4-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="87cd4-135">Den roll du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="87cd4-135">The role you want to assign</span></span>
    
    <span data-ttu-id="87cd4-136">Använd det här kommandot för att visa listan över tillgängliga administratörs roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="87cd4-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="87cd4-137">När du har fastställt namnet på kontot och namnet på rollen använder du dessa kommandon för att tilldela rollen till kontot:</span><span class="sxs-lookup"><span data-stu-id="87cd4-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="87cd4-138">Klistra in kommandon i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="87cd4-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="87cd4-139">För variablerna *$dispName* och *$roleName* ersätter du beskrivningen med deras värden.</span><span class="sxs-lookup"><span data-stu-id="87cd4-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="87cd4-140">Ta bort \< and > tecknen men behåll citat tecknen.</span><span class="sxs-lookup"><span data-stu-id="87cd4-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="87cd4-141">Kör de ändrade raderna till fönstret Microsoft Azure Active Directory-modul för Windows PowerShell för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="87cd4-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="87cd4-142">Du kan också använda Windows PowerShell ISE (Integrated script Environment).</span><span class="sxs-lookup"><span data-stu-id="87cd4-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="87cd4-143">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="87cd4-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="87cd4-144">Inloggnings namn för användar konton</span><span class="sxs-lookup"><span data-stu-id="87cd4-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="87cd4-145">Om du använder för att arbeta med inloggnings namnen eller UPN: er för användar konton bestämmer du följande information:</span><span class="sxs-lookup"><span data-stu-id="87cd4-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="87cd4-146">Användar kontots UPN</span><span class="sxs-lookup"><span data-stu-id="87cd4-146">The user account's UPN</span></span>
    
    <span data-ttu-id="87cd4-147">Om du inte känner till UPN använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="87cd4-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="87cd4-148">Det här kommandot visar UPN för dina användar konton, sorterade efter UPN, en skärm bild i taget.</span><span class="sxs-lookup"><span data-stu-id="87cd4-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="87cd4-149">Du kan använda **WHERE** -cmdleten för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="87cd4-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="87cd4-150">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="87cd4-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="87cd4-151">Det här kommandot listar bara de användar konton som visnings namnet börjar med "John".</span><span class="sxs-lookup"><span data-stu-id="87cd4-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="87cd4-152">Den roll du vill tilldela</span><span class="sxs-lookup"><span data-stu-id="87cd4-152">The role you want to assign</span></span>
    
    <span data-ttu-id="87cd4-153">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="87cd4-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="87cd4-154">När du har UPN för kontot och namnet på rollen tilldelar du rollen till kontot genom att använda följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="87cd4-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="87cd4-155">Kopiera kommandona och klistra in dem i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="87cd4-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="87cd4-156">För variablerna **$upnName** och **$roleName** .</span><span class="sxs-lookup"><span data-stu-id="87cd4-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="87cd4-157">Ersätt beskrivningen med deras värden.</span><span class="sxs-lookup"><span data-stu-id="87cd4-157">Replace the description text with their values.</span></span> <span data-ttu-id="87cd4-158">Ta bort \< and > tecknen men behåll citat tecknen.</span><span class="sxs-lookup"><span data-stu-id="87cd4-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="87cd4-159">Kopiera de ändrade raderna till Microsoft Azure Active Directory-modul för Windows PowerShell-fönstret för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="87cd4-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="87cd4-160">Du kan också använda Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="87cd4-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="87cd4-161">Här är ett exempel på en färdigställd kommando uppsättning:</span><span class="sxs-lookup"><span data-stu-id="87cd4-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="87cd4-162">Ändringar i flera roller</span><span class="sxs-lookup"><span data-stu-id="87cd4-162">Multiple role changes</span></span>

<span data-ttu-id="87cd4-163">För ändringar av flera roller kontrollerar du följande information:</span><span class="sxs-lookup"><span data-stu-id="87cd4-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="87cd4-164">Vilka användar konton du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="87cd4-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="87cd4-165">Du kan använda metoderna i föregående avsnitt för att samla in en uppsättning visnings namn eller UPN.</span><span class="sxs-lookup"><span data-stu-id="87cd4-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="87cd4-166">Vilka roller du vill tilldela till varje användar konto.</span><span class="sxs-lookup"><span data-stu-id="87cd4-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="87cd4-167">Använd det här kommandot för att visa listan över tillgängliga roller som du kan tilldela till användar konton:</span><span class="sxs-lookup"><span data-stu-id="87cd4-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="87cd4-168">Skapa sedan en CSV-textfil som innehåller fälten visnings namn eller UPN och rollnamn.</span><span class="sxs-lookup"><span data-stu-id="87cd4-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="87cd4-169">Det gör du enkelt i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="87cd4-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="87cd4-170">Här är ett exempel på visnings namn:</span><span class="sxs-lookup"><span data-stu-id="87cd4-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="87cd4-171">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="87cd4-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="87cd4-172">Här är ett exempel på UPN-användare:</span><span class="sxs-lookup"><span data-stu-id="87cd4-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="87cd4-173">Fyll sedan i platsen för CSV-filen och kör de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="87cd4-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="87cd4-174">Se även</span><span class="sxs-lookup"><span data-stu-id="87cd4-174">See also</span></span>

- [<span data-ttu-id="87cd4-175">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cd4-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="87cd4-176">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cd4-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="87cd4-177">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87cd4-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
