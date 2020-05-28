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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Lär dig hur du anger att vissa enskilda användarlösenord aldrig upphör att gälla med Windows PowerShell.
ms.openlocfilehash: 6562a4092c47d9c4bf7bf294767e6050a3e0577a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387015"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="b9909-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="b9909-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="b9909-104">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="b9909-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="b9909-105">Gå till sidan **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Inställningar.</a></span><span class="sxs-lookup"><span data-stu-id="b9909-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="b9909-106">Högst upp på sidan Inställningar väljer du **Sekretess för & .**</span><span class="sxs-lookup"><span data-stu-id="b9909-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="b9909-107">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="b9909-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="b9909-108">Om lösenorden aldrig upphör att gälla klickar du på kryssrutan **bredvid Ange att användarlösenord ska upphöra att gälla efter ett antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="b9909-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="b9909-109">Du får möjlighet att ange antalet dagar tills lösenorden upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b9909-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="b9909-110">Ange principen för förfallodatum för lösenord för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="b9909-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="b9909-111">En global administratör för en Microsoft-molntjänst kan använda [Azure Active Directory PowerShell for Graph för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange lösenord som inte upphör att gälla för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="b9909-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="b9909-112">Du kan [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) också använda AzureAD-cmdlets för att ta bort konfigurationen för aldrig upphör att gälla eller för att se vilka användarlösenord som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b9909-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="b9909-113">Den här guiden gäller för andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets- och katalogtjänster.</span><span class="sxs-lookup"><span data-stu-id="b9909-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="b9909-114">Lösenordsförfallodatum är den enda delen av principen som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="b9909-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="b9909-115">Mer information om Azure AD PowerShell för Graph finns i [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="b9909-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="b9909-116">Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b9909-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="b9909-117">Mer information om katalogsynkronisering finns i [Ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="b9909-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="b9909-118">Så här kontrollerar du principen om förfallodatum för ett lösenord</span><span class="sxs-lookup"><span data-stu-id="b9909-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="b9909-119">Mer information om kommandot Get-AzureADUser i AzureAD-modulen finns i referensartikeln [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="b9909-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="b9909-120">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b9909-120">Run one of the following commands:</span></span>

- <span data-ttu-id="b9909-121">Om du vill se om en enskild användares lösenord aldrig upphör att gälla kör du följande cmdlet med hjälp av UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID för den användare som du vill kontrollera:</span><span class="sxs-lookup"><span data-stu-id="b9909-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="b9909-122">Exempel:</span><span class="sxs-lookup"><span data-stu-id="b9909-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="b9909-123">Om du vill se inställningen **Lösenord upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9909-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="b9909-124">För att få en rapport om alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="b9909-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="b9909-125">För att få en rapport om alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="b9909-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="b9909-126">Ange att ett lösenord ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="b9909-126">Set a password to expire</span></span>

<span data-ttu-id="b9909-127">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b9909-127">Run one of the following commands:</span></span>

- <span data-ttu-id="b9909-128">Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="b9909-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="b9909-129">Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9909-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="b9909-130">Ange att ett lösenord aldrig ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="b9909-130">Set a password to never expire</span></span>

<span data-ttu-id="b9909-131">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b9909-131">Run one of the following commands:</span></span>

- <span data-ttu-id="b9909-132">Om du vill att lösenordet för en användare aldrig ska upphöra att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="b9909-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="b9909-133">Om du vill att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b9909-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="b9909-134">Lösenord inställd på `-PasswordPolicies DisablePasswordExpiration` att fortfarande ålder baserat på `pwdLastSet` attributet.</span><span class="sxs-lookup"><span data-stu-id="b9909-134">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="b9909-135">Om du anger att användarlösenorden aldrig ska upphöra att gälla och sedan 90+ dagar går upphör att gälla upphör lösenorden att gälla.</span><span class="sxs-lookup"><span data-stu-id="b9909-135">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="b9909-136">Baserat på `pwdLastSet` attributet, om du ändrar förfallodatum till `-PasswordPolicies None` , alla lösenord som har en äldre än `pwdLastSet` 90 dagar kräver användaren att ändra dem nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="b9909-136">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="b9909-137">Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="b9909-137">This change can affect a large number of users.</span></span>
