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
# <a name="set-an-individual-users-password-to-never-expire"></a>Ange att en enskild användares lösenord aldrig ska förfalla

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Ange förfalloprincip för lösenord i organisationen

1. I administrations centret går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> .
2. Välj **säkerhet & integritet**högst upp på sidan Inställningar.
3. Välj **Förfalloprincip för lösenordet**. 
4. Om lösen ord inte upphör att gälla markerar du kryss rutan intill **Ange användarens lösen ord så att de upphör efter ett antal dagar**. Du får ett alternativ för att ange antalet dagar tills lösen ordet upphör att gälla.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Ange förfallo princip för lösen ord för enskilda användare

En global administratör för en Microsoft Cloud Service kan använda [Azure Active Directory PowerShell för](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) att ange att lösen ord inte upphör för vissa användare. Du kan också använda [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets för att ta bort konfigurationen aldrig-upphör att gälla eller för att se vilka användar lösen ord som aldrig förfaller.

Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också är beroende av Azure AD för identitets-och katalog tjänster. Lösen ordets förfallo dag är den enda delen av den princip som kan ändras.

Mer information om Azure AD PowerShell för Graph finns i [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

> [!NOTE]
> Endast lösen ord för användar konton som inte synkroniseras med katalog synkronisering kan konfigureras så att de inte upphör att gälla. Mer information om katalog synkronisering finns i [ansluta AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Så här kontrollerar du giltighets principen för ett lösen ord

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

### <a name="set-a-password-to-never-expire"></a>Ange att ett lösen ord aldrig ska förfalla

Kör något av följande kommandon:

- Om du vill att lösen ordet för en användare aldrig ska förfalla kan du köra följande cmdlet genom att använda UPN eller användarens användar-ID:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Om du vill att lösen orden för alla användare i en organisation aldrig ska förfalla kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Användar konton som har kon figurer ATS med `-PasswordPolicies DisablePasswordExpiration` parametern är tidsåldern baserat på `pwdLastSet` användar kontots attribut. Om du till exempel anger att användar lösen ord aldrig ska upphöra att gälla och sedan 90 eller fler dagar går du vidare. Baserat på `pwdLastSet` användar kontots attribut för användar konton som har kon figurer ATS med `-PasswordPolicies None` parametern måste alla lösen ord som har en `pwdLastSet` äldre än 90 dagar kräva att användaren ändrar dem nästa gång de loggar in. Den här ändringen kan påverka ett stort antal användare.
