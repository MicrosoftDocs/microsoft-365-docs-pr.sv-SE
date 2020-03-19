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
description: Läs om hur du anger att vissa enskilda användarlösenord aldrig upphör att gälla med Windows PowerShell.
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807703"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="55234-103">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="55234-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="55234-104">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="55234-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="55234-105">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">sekretesssidan</a> **Inställningar** \> & sekretess i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="55234-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="55234-106">Bredvid **Lösenordsprincip** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="55234-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="55234-107">Om lösenord en satt att aldrig upphöra att gälla ställer du in växlingsknappen på **Av**.</span><span class="sxs-lookup"><span data-stu-id="55234-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="55234-108">Du får möjlighet att ange antalet dagar tills lösenorden upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="55234-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="55234-109">Ange principen för förfallodatum för lösenord för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="55234-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="55234-110">En global administratör för en Microsoft-molntjänst kan använda Microsoft Azure AD Module för Windows PowerShell för att ange att lösenord inte ska upphöra att gälla för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="55234-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="55234-111">Du kan också använda Windows PowerShell-cmdlets för att ta bort konfigurationen som aldrig upphör att gälla eller för att se vilka användarlösenord som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="55234-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="55234-112">Den här guiden gäller för andra leverantörer, till exempel Intune och Office 365, som också är beroende av Azure AD för identitets- och katalogtjänster.</span><span class="sxs-lookup"><span data-stu-id="55234-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="55234-113">Förfallodatum för lösenord är den enda delen av principen som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="55234-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="55234-114">Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras för att inte upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="55234-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="55234-115">Mer information om katalogsynkronisering finns i [Anslut AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="55234-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="55234-116">Så här kontrollerar du förfalloprincipen för ett lösenord</span><span class="sxs-lookup"><span data-stu-id="55234-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="55234-117">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="55234-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="55234-118">Om du vill se om en enskild användares lösenord är inställt på att aldrig upphöra att gälla kör du följande cmdlet med hjälp av UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID för den användare som du vill kontrollera:</span><span class="sxs-lookup"><span data-stu-id="55234-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="55234-119">Exempel:</span><span class="sxs-lookup"><span data-stu-id="55234-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="55234-120">Om du vill se **inställningen Lösenord upphör aldrig att gälla** för alla användare kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="55234-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="55234-121">Så här hämtar du en rapport över alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="55234-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="55234-122">Så här hämtar du en rapport över alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="55234-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="55234-123">Ange att ett lösenord ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="55234-123">Set a password to expire</span></span>

<span data-ttu-id="55234-124">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="55234-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="55234-125">Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens ID:</span><span class="sxs-lookup"><span data-stu-id="55234-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="55234-126">Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="55234-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="55234-127">Ange att ett lösenord aldrig ska upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="55234-127">Set a password to never expire</span></span>

<span data-ttu-id="55234-128">Kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="55234-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="55234-129">Om du vill att lösenordet för en användare aldrig ska upphöra att gälla kör du följande cmdlet med hjälp av UPN eller användarens id:n för att ställa in lösenordet för en användare som aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="55234-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="55234-130">Om du vill ange att lösenorden för alla användare i en organisation aldrig upphör att gälla kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="55234-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="55234-131">Lösenord som `-PasswordPolicies DisablePasswordExpiration` fortfarande är ålderbaserade på attributet. `pwdLastSet`</span><span class="sxs-lookup"><span data-stu-id="55234-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="55234-132">Om du anger att användarlösenorden aldrig upphör att gälla och sedan går 90 + dagar, upphör lösenorden att gälla.</span><span class="sxs-lookup"><span data-stu-id="55234-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="55234-133">Baserat på `pwdLastSet` attributet, om du `-PasswordPolicies None`ändrar utgången till `pwdLastSet` , kräver alla lösenord som har en äldre än 90 dagar att användaren ändrar dem nästa gång de loggar in.</span><span class="sxs-lookup"><span data-stu-id="55234-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="55234-134">Den här ändringen kan påverka ett stort antal användare.</span><span class="sxs-lookup"><span data-stu-id="55234-134">This change can affect a large number of users.</span></span> 
