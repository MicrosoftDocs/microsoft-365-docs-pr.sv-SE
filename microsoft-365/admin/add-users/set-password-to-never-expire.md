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
ms.openlocfilehash: 275fedf7bf4e52320b769689516ad39a31c63ea1
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105741"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="13090-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="13090-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="13090-104">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="13090-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="13090-105">Gå till sekretesssidan Inställningar <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">säkerhet & i</a> **administrationscentret.** \></span><span class="sxs-lookup"><span data-stu-id="13090-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="13090-106">Välj **Redigera** **bredvid lösenordsprincip** .</span><span class="sxs-lookup"><span data-stu-id="13090-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="13090-107">Om lösenorden aldrig upphör att gälla ställer du in växlingsknappen på **Av**.</span><span class="sxs-lookup"><span data-stu-id="13090-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="13090-108">Du får möjlighet att ange antalet dagar tills lösenorden upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="13090-108">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="13090-109">Ange principen för förfallodatum för lösenord för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="13090-109">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="13090-110">En global administratör för en Microsoft-molntjänst kan använda Microsoft Azure AD Module för Windows PowerShell för att ange lösenord som inte upphör att gälla för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="13090-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="13090-111">Du kan också använda Windows PowerShell-cmdletar för att ta bort konfigurationen för aldrig upphör att gälla eller för att se vilka användarlösenord som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="13090-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="13090-112">Den här guiden gäller för andra leverantörer, till exempel Intune och Office 365, som också är beroende av Azure AD för identitets- och katalogtjänster.</span><span class="sxs-lookup"><span data-stu-id="13090-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="13090-113">Lösenordsförfallodatum är den enda delen av principen som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="13090-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="13090-114">Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="13090-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="13090-115">Mer information om katalogsynkronisering finns i [Ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="13090-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="13090-116">Så här kontrollerar du principen om förfallodatum för ett lösenord</span><span class="sxs-lookup"><span data-stu-id="13090-116">How to check the expiration policy for a password</span></span>
<span data-ttu-id="13090-117">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="13090-117">Run one of the following commands:</span></span>

- <span data-ttu-id="13090-118">Om du vill se om en enskild användares lösenord aldrig upphör att gälla kör du följande cmdlet med hjälp av UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID för den användare som du vill kontrollera:</span><span class="sxs-lookup"><span data-stu-id="13090-118">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="13090-119">Exempel:</span><span class="sxs-lookup"><span data-stu-id="13090-119">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="13090-120">Om du vill se inställningen **Lösenord upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="13090-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="13090-121">För att få en rapport om alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="13090-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="13090-122">För att få en rapport om alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="13090-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="13090-123">Ange att ett lösenord ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="13090-123">Set a password to expire</span></span>

<span data-ttu-id="13090-124">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="13090-124">Run one of the following commands:</span></span>

- <span data-ttu-id="13090-125">Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="13090-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="13090-126">Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="13090-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="13090-127">Ange att ett lösenord aldrig ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="13090-127">Set a password to never expire</span></span>

<span data-ttu-id="13090-128">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="13090-128">Run one of the following commands:</span></span>

- <span data-ttu-id="13090-129">Om du vill att lösenordet för en användare aldrig ska upphöra att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="13090-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="13090-130">Om du vill att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="13090-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="13090-131">Lösenord inställd `-PasswordPolicies DisablePasswordExpiration` på att fortfarande `pwdLastSet` ålder baserat på attributet.</span><span class="sxs-lookup"><span data-stu-id="13090-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="13090-132">Om du anger att användarlösenorden aldrig ska upphöra att gälla och sedan 90+ dagar går upphör att gälla upphör lösenorden att gälla.</span><span class="sxs-lookup"><span data-stu-id="13090-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="13090-133">Baserat på `pwdLastSet` attributet, om du `-PasswordPolicies None`ändrar förfallodatum till , alla lösenord som har en `pwdLastSet` äldre än 90 dagar kräver användaren att ändra dem nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="13090-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="13090-134">Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="13090-134">This change can affect a large number of users.</span></span>