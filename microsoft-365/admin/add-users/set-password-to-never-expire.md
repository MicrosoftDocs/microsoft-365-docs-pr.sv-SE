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
description: Lär dig hur du ställer in vissa enskilda användar lösen ord så att de aldrig upphör att gälla, via Windows PowerShell.
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804214"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="746e6-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="746e6-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="746e6-104">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="746e6-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="746e6-105">I administrations centret går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> .</span><span class="sxs-lookup"><span data-stu-id="746e6-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="746e6-106">Välj **säkerhet & integritet**högst upp på sidan Inställningar.</span><span class="sxs-lookup"><span data-stu-id="746e6-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="746e6-107">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="746e6-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="746e6-108">Om lösen ord inte upphör att gälla markerar du kryss rutan intill **Ange användarens lösen ord så att de upphör efter ett antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="746e6-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="746e6-109">Du får ett alternativ för att ange antalet dagar tills lösen ordet upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="746e6-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="746e6-110">Ange förfallo princip för lösen ord för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="746e6-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="746e6-111">En global administratör för en Microsoft Cloud Service kan använda [Azure Active Directory PowerShell för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange att lösen ord inte upphör för vissa användare.</span><span class="sxs-lookup"><span data-stu-id="746e6-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="746e6-112">Du kan också använda [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets för att ta bort konfigurationen aldrig-upphör att gälla eller för att se vilka användar lösen ord som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="746e6-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="746e6-113">Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets-och katalog tjänster.</span><span class="sxs-lookup"><span data-stu-id="746e6-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="746e6-114">Lösen ordets förfallo dag är den enda delen av den princip som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="746e6-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="746e6-115">Mer information om Azure AD PowerShell för Graph finns i [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="746e6-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="746e6-116">Endast lösen ord för användar konton som inte synkroniseras med katalog synkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="746e6-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="746e6-117">Mer information om katalog synkronisering finns i [ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="746e6-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="746e6-118">Så här kontrollerar du giltighets principen för ett lösen ord</span><span class="sxs-lookup"><span data-stu-id="746e6-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="746e6-119">Mer information om kommandot Get-AzureADUser i modulen AzureAD finns i referens artikeln [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="746e6-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="746e6-120">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="746e6-120">Run one of the following commands:</span></span>

- <span data-ttu-id="746e6-121">Om du vill se om en enskild användares lösen ord är inställda på att aldrig löpa ut kör du följande cmdlet genom att använda UPN (till exempel *user@contoso.onmicrosoft.com*) eller användar-ID: t för den användare som du vill kontrol lera.</span><span class="sxs-lookup"><span data-stu-id="746e6-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="746e6-122">Exempel:</span><span class="sxs-lookup"><span data-stu-id="746e6-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="746e6-123">Om du vill se **lösen ordet upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="746e6-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="746e6-124">Så här får du en rapport om alla användare med PasswordNeverExpires i HTML på Skriv bordet för den aktuella användaren med namn  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="746e6-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="746e6-125">Så här får du en rapport om alla användare med PasswordNeverExpires i CSV-filen på Skriv bordet för den aktuella användaren med namn **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="746e6-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="746e6-126">Ange ett lösen ord som upphör</span><span class="sxs-lookup"><span data-stu-id="746e6-126">Set a password to expire</span></span>

<span data-ttu-id="746e6-127">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="746e6-127">Run one of the following commands:</span></span>

- <span data-ttu-id="746e6-128">Om du vill ange lösen ordet för en användare så att lösen ordet upphör att gälla kör du följande cmdlet genom att använda UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="746e6-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="746e6-129">Om du vill ange lösen ord för alla användare i organisationen så att de upphör kan du använda följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="746e6-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="746e6-130">Ange att ett lösen ord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="746e6-130">Set a password to never expire</span></span>

<span data-ttu-id="746e6-131">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="746e6-131">Run one of the following commands:</span></span>

- <span data-ttu-id="746e6-132">Om du vill att lösen ordet för en användare aldrig ska förfalla kan du köra följande cmdlet genom att använda UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="746e6-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="746e6-133">Om du vill att lösen orden för alla användare i en organisation aldrig ska förfalla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="746e6-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="746e6-134">Användar konton som har kon figurer ATS med `-PasswordPolicies DisablePasswordExpiration` parametern är tidsåldern baserat på `pwdLastSet` användar kontots attribut.</span><span class="sxs-lookup"><span data-stu-id="746e6-134">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="746e6-135">Om du till exempel anger att användar lösen ord aldrig ska upphöra att gälla och sedan 90 eller fler dagar går du vidare.</span><span class="sxs-lookup"><span data-stu-id="746e6-135">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="746e6-136">Baserat på `pwdLastSet` användar kontots attribut för användar konton som har kon figurer ATS med `-PasswordPolicies None` parametern måste alla lösen ord som har en `pwdLastSet` äldre än 90 dagar kräva att användaren ändrar dem nästa gång de loggar in. Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="746e6-136">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>
