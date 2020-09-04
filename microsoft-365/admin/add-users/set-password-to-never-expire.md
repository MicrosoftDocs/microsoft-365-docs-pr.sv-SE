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
ms.openlocfilehash: 01817aba0de1f5ca5f0b9bdf7feb1d03d72f6a24
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361755"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Ange att en enskild användares lösenord aldrig ska förfalla

I den här artikeln förklaras hur du anger ett lösen ord för en enskild användare som inte upphör att gälla. Du måste utföra de här stegen med PowerShell.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. För att utföra de här stegen måste du logga in med ditt Microsoft 365-administratörs konto. [Vad är ett administratörs konto?](../admin-overview/admin-overview.md). 

Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.

En global administratör för en Microsoft Cloud Service kan använda [Azure Active Directory PowerShell för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange att lösen ord inte upphör för vissa användare. Du kan också använda [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets för att ta bort konfigurationen aldrig-upphör att gälla eller för att se vilka användar lösen ord som aldrig förfaller.

Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets-och katalog tjänster. Lösen ordets förfallo dag är den enda delen av den princip som kan ändras.

> [!NOTE]
> Endast lösen ord för användar konton som inte synkroniseras med katalog synkronisering kan konfigureras så att de inte upphör att gälla. Mer information om katalog synkronisering finns i [ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Så här kontrollerar du giltighets principen för ett lösen ord

Mer information om kommandot Get-AzureADUser i modulen AzureAD finns i referens artikeln [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Kör något av följande kommandon:

- Om du vill se om en enskild användares lösen ord är inställda på att aldrig löpa ut kör du följande cmdlet genom att använda UPN (till exempel *user@contoso.onmicrosoft.com*) eller användar-ID: t för den användare som du vill kontrol lera.

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Exempel:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Om du vill se **lösen ordet upphör aldrig att gälla** för alla användare kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Så här får du en rapport om alla användare med PasswordNeverExpires i HTML på Skriv bordet för den aktuella användaren med namn  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Så här får du en rapport om alla användare med PasswordNeverExpires i CSV-filen på Skriv bordet för den aktuella användaren med namn **ReportPasswordNeverExpires.csv**

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

- Om du vill att lösen orden för alla användare i en organisation aldrig ska förfalla kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a>Ange ett lösen ord som upphör

Kör något av följande kommandon:

- Om du vill ange lösen ordet för en användare så att lösen ordet upphör att gälla kör du följande cmdlet genom att använda UPN eller användarens användar-ID:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Om du vill ange lösen ord för alla användare i organisationen så att de upphör kan du använda följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> Användar konton som har kon figurer ATS med `-PasswordPolicies DisablePasswordExpiration` parametern är tidsåldern baserat på `pwdLastSet` användar kontots attribut. Om du till exempel anger att användar lösen ord aldrig ska upphöra att gälla och sedan 90 eller fler dagar går du vidare. Baserat på `pwdLastSet` användar kontots attribut för användar konton som har kon figurer ATS med `-PasswordPolicies None` parametern måste alla lösen ord som har en `pwdLastSet` äldre än 90 dagar kräva att användaren ändrar dem nästa gång de loggar in. Den här ändringen kan påverka ett stort antal användare.

## <a name="related-content"></a>Relaterat innehåll

[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md)

[Återställa lösenord](../add-users/reset-passwords.md)