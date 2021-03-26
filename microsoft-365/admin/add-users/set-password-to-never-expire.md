---
title: Ange att en enskild användares lösenord aldrig ska förfalla
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: Lär dig hur du ställer in att vissa användares lösenord aldrig ska upphöra att gälla med Windows PowerShell.
ms.openlocfilehash: c70fce1c3ea9cb1dea66982a27ddb24e2b2de255
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222079"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="146fd-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="146fd-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="146fd-104">I den här artikeln förklaras hur du anger ett lösenord så att en enskild användare inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="146fd-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="146fd-105">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="146fd-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="146fd-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="146fd-106">Before you begin</span></span>

<span data-ttu-id="146fd-107">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="146fd-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="146fd-108">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="146fd-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="146fd-109">[Vad är ett administratörskonto?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span><span class="sxs-lookup"><span data-stu-id="146fd-109">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span> 

<span data-ttu-id="146fd-110">Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="146fd-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="146fd-111">En global administratör för en Microsoft-molntjänst kan använda [Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) för Graph för att ange att lösenord inte ska upphöra att gälla för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="146fd-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="146fd-112">Du kan [](/powershell/module/Azuread) också använda AzureAD-cmdlets för att ta bort konfigurationen med aldrig upphör att gälla eller för att se vilka användarlösenord som är inställda på att aldrig upphöra.</span><span class="sxs-lookup"><span data-stu-id="146fd-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="146fd-113">Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också förlitar sig på Azure AD för identitets- och katalogtjänster.</span><span class="sxs-lookup"><span data-stu-id="146fd-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="146fd-114">Lösenordsförfallotid är den enda del av principen som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="146fd-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="146fd-115">Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="146fd-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="146fd-116">Mer information om katalogsynkronisering finns i [Ansluta AD till Azure AD.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="146fd-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="146fd-117">Så här kontrollerar du förfalloprincipen för ett lösenord</span><span class="sxs-lookup"><span data-stu-id="146fd-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="146fd-118">Mer information om kommandot Get-AzureADUser AzureAD-modulen finns i referensartikeln [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="146fd-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="146fd-119">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="146fd-119">Run one of the following commands:</span></span>

- <span data-ttu-id="146fd-120">Kör följande cmdlet med UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID:t för den användare du vill kontrollera för att se om en enskild användares lösenord är inställt på att aldrig upphöra att gälla:</span><span class="sxs-lookup"><span data-stu-id="146fd-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="146fd-121">Exempel:</span><span class="sxs-lookup"><span data-stu-id="146fd-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="146fd-122">Om du vill **se inställningen för Lösenord upphör** aldrig att gälla för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="146fd-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="146fd-123">För att få en rapport över alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med  **namnReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="146fd-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="146fd-124">För att få en rapport över alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="146fd-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="146fd-125">Om du vill ange att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="146fd-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="146fd-126">Användarkonton som konfigurerats med `-PasswordPolicies DisablePasswordExpiration` parameterns ålder baserat på `pwdLastSet` attributet.</span><span class="sxs-lookup"><span data-stu-id="146fd-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="146fd-127">Baserat på attributet måste användaren ändra alla lösenord som har en pwdLastSet som är äldre än `pwdLastSet` 90 dagar om du ändrar förfallodatumet till . `-PasswordPolicies None`</span><span class="sxs-lookup"><span data-stu-id="146fd-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="146fd-128">Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="146fd-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="146fd-129">Ange att ett lösenord ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="146fd-129">Set a password to expire</span></span>

<span data-ttu-id="146fd-130">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="146fd-130">Run one of the following commands:</span></span>

- <span data-ttu-id="146fd-131">Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:</span><span class="sxs-lookup"><span data-stu-id="146fd-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="146fd-132">Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="146fd-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="146fd-133">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="146fd-133">Related content</span></span>

[<span data-ttu-id="146fd-134">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="146fd-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="146fd-135">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="146fd-135">Reset passwords</span></span>](../add-users/reset-passwords.md)