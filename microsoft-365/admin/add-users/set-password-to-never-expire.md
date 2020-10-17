---
title: Ange att en enskild användares lösenord aldrig ska förfalla
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580922"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="61088-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="61088-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="61088-104">I den här artikeln förklaras hur du anger ett lösen ord för en enskild användare som inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="61088-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="61088-105">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61088-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="61088-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="61088-106">Before you begin</span></span>

<span data-ttu-id="61088-107">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="61088-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="61088-108">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="61088-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="61088-109">[Vad är ett administratörskonto?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61088-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="61088-110">Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="61088-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="61088-111">En global administratör för en Microsoft Cloud Service kan använda [Azure Active Directory PowerShell för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange att lösen ord inte upphör för vissa användare.</span><span class="sxs-lookup"><span data-stu-id="61088-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="61088-112">Du kan också använda [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets för att ta bort konfigurationen aldrig-upphör att gälla eller för att se vilka användar lösen ord som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="61088-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="61088-113">Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets-och katalog tjänster.</span><span class="sxs-lookup"><span data-stu-id="61088-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="61088-114">Lösen ordets förfallo dag är den enda delen av den princip som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="61088-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="61088-115">Endast lösen ord för användar konton som inte synkroniseras med katalog synkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="61088-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="61088-116">Mer information om katalog synkronisering finns i [ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="61088-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="61088-117">Så här kontrollerar du giltighets principen för ett lösen ord</span><span class="sxs-lookup"><span data-stu-id="61088-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="61088-118">Mer information om kommandot Get-AzureADUser i modulen AzureAD finns i artikeln [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="61088-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="61088-119">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="61088-119">Run one of the following commands:</span></span>

- <span data-ttu-id="61088-120">Om du vill se om en enskild användares lösen ord är inställda på att aldrig löpa ut kör du följande cmdlet genom att använda UPN (till exempel *user@contoso.onmicrosoft.com*) eller användar-ID: t för den användare som du vill kontrol lera.</span><span class="sxs-lookup"><span data-stu-id="61088-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="61088-121">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61088-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="61088-122">Om du vill se **lösen ordet upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="61088-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="61088-123">Så här får du en rapport om alla användare med PasswordNeverExpires i HTML på Skriv bordet för den aktuella användaren med namn  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="61088-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="61088-124">Så här får du en rapport om alla användare med PasswordNeverExpires i CSV-filen på Skriv bordet för den aktuella användaren med namn **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="61088-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="61088-125">Om du vill att lösen orden för alla användare i en organisation aldrig ska förfalla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="61088-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="61088-126">Ange ett lösen ord som upphör</span><span class="sxs-lookup"><span data-stu-id="61088-126">Set a password to expire</span></span>

<span data-ttu-id="61088-127">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="61088-127">Run one of the following commands:</span></span>

- <span data-ttu-id="61088-128">Om du vill ange lösen ordet för en användare så att lösen ordet upphör att gälla kör du följande cmdlet genom att använda UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="61088-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="61088-129">Om du vill ange lösen ord för alla användare i organisationen så att de upphör kan du använda följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="61088-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="61088-130">Användar konton som har kon figurer ATS med `-PasswordPolicies DisablePasswordExpiration` parametern är tidsåldern baserat på `pwdLastSet` användar kontots attribut.</span><span class="sxs-lookup"><span data-stu-id="61088-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="61088-131">Om du till exempel anger att användar lösen ord aldrig ska upphöra att gälla och sedan 90 eller fler dagar går du vidare.</span><span class="sxs-lookup"><span data-stu-id="61088-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="61088-132">Baserat på `pwdLastSet` användar kontots attribut för användar konton som har kon figurer ATS med `-PasswordPolicies None` parametern måste alla lösen ord som har en `pwdLastSet` äldre än 90 dagar kräva att användaren ändrar dem nästa gång de loggar in. Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="61088-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="61088-133">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="61088-133">Related content</span></span>

[<span data-ttu-id="61088-134">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="61088-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="61088-135">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="61088-135">Reset passwords</span></span>](../add-users/reset-passwords.md)