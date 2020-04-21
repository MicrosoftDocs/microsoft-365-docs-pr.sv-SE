---
title: Ange att en enskild användares lösenord aldrig ska förfalla
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Lär dig hur du anger att vissa enskilda användarlösenord aldrig upphör att gälla med Windows PowerShell.
ms.openlocfilehash: 66c4901d171f5ed2e07d7a9f5cccbf141dc3d04d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43624040"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="a9a96-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="a9a96-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="a9a96-104">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="a9a96-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="a9a96-105">Gå till sekretesssidan Inställningar <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">säkerhet & i</a> **administrationscentret.** \></span><span class="sxs-lookup"><span data-stu-id="a9a96-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="a9a96-106">Välj **Redigera** **bredvid lösenordsprincip** .</span><span class="sxs-lookup"><span data-stu-id="a9a96-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="a9a96-107">Om lösenorden aldrig upphör att gälla ställer du in växlingsknappen på **Av**.</span><span class="sxs-lookup"><span data-stu-id="a9a96-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="a9a96-108">Du får möjlighet att ange antalet dagar tills lösenorden upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="a9a96-108">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="a9a96-109">Ange principen för förfallodatum för lösenord för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="a9a96-109">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="a9a96-110">En global administratör för en Microsoft-molntjänst kan använda [Azure Active Directory PowerShell for Graph för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange lösenord som inte upphör att gälla för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="a9a96-110">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="a9a96-111">Du kan [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) också använda AzureAD-cmdlets för att ta bort konfigurationen för aldrig upphör att gälla eller för att se vilka användarlösenord som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="a9a96-111">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="a9a96-112">Den här guiden gäller för andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets- och katalogtjänster.</span><span class="sxs-lookup"><span data-stu-id="a9a96-112">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="a9a96-113">Lösenordsförfallodatum är den enda delen av principen som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="a9a96-113">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="a9a96-114">Mer information om Azure AD PowerShell för Graph finns i [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="a9a96-114">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="a9a96-115">Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="a9a96-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="a9a96-116">Mer information om katalogsynkronisering finns i [Ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="a9a96-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="a9a96-117">Så här kontrollerar du principen om förfallodatum för ett lösenord</span><span class="sxs-lookup"><span data-stu-id="a9a96-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="a9a96-118">Mer information om kommandot Get-AzureADUser i AzureAD-modulen finns i referensartikeln [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="a9a96-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="a9a96-119">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="a9a96-119">Run one of the following commands:</span></span>

- <span data-ttu-id="a9a96-120">Om du vill se om en enskild användares lösenord aldrig upphör att gälla kör du följande cmdlet med hjälp av UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID för den användare som du vill kontrollera:</span><span class="sxs-lookup"><span data-stu-id="a9a96-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="a9a96-121">Exempel:</span><span class="sxs-lookup"><span data-stu-id="a9a96-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="a9a96-122">Om du vill se inställningen **Lösenord upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9a96-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="a9a96-123">För att få en rapport om alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="a9a96-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="a9a96-124">För att få en rapport om alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="a9a96-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="a9a96-125">Ange att ett lösenord ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="a9a96-125">Set a password to expire</span></span>

<span data-ttu-id="a9a96-126">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="a9a96-126">Run one of the following commands:</span></span>

- <span data-ttu-id="a9a96-127">Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="a9a96-127">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="a9a96-128">Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9a96-128">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="a9a96-129">Ange att ett lösenord aldrig ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="a9a96-129">Set a password to never expire</span></span>

<span data-ttu-id="a9a96-130">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="a9a96-130">Run one of the following commands:</span></span>

- <span data-ttu-id="a9a96-131">Om du vill att lösenordet för en användare aldrig ska upphöra att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="a9a96-131">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="a9a96-132">Om du vill att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9a96-132">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="a9a96-133">Lösenord inställd `-PasswordPolicies DisablePasswordExpiration` på att fortfarande `pwdLastSet` ålder baserat på attributet.</span><span class="sxs-lookup"><span data-stu-id="a9a96-133">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="a9a96-134">Om du anger att användarlösenorden aldrig ska upphöra att gälla och sedan 90+ dagar går upphör att gälla upphör lösenorden att gälla.</span><span class="sxs-lookup"><span data-stu-id="a9a96-134">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="a9a96-135">Baserat på `pwdLastSet` attributet, om du `-PasswordPolicies None`ändrar förfallodatum till , alla lösenord som har en `pwdLastSet` äldre än 90 dagar kräver användaren att ändra dem nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="a9a96-135">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="a9a96-136">Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="a9a96-136">This change can affect a large number of users.</span></span>
