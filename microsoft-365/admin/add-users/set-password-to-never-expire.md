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
description: Logga in på ditt Microsoft 365-administratörskonto för att ställa in vissa enskilda användarlösenord så att de aldrig upphör att gälla med hjälp Windows PowerShell.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571931"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Ange att en enskild användares lösenord aldrig ska förfalla

I den här artikeln beskrivs hur du anger att ett lösenord för en enskild användare inte ska upphöra att gälla. Du måste slutföra dessa steg med PowerShell.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../../business-video/admin-center-overview.md). 

Du måste vara global [administratör eller lösenordsadministratör för](about-admin-roles.md) att kunna utföra dessa steg.

En global administratör för en Microsoft-molntjänst kan [använda Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) ställa in lösenord som inte ska upphöra att gälla för specifika användare. Du kan [](/powershell/module/Azuread) också använda AzureAD-cmdletar för att ta bort konfigurationen för att aldrig upphöra att gälla eller för att se vilka användarlösenord som är inställda på att aldrig upphöra att gälla.

Den här guiden gäller andra leverantörer, till exempel Intune och Microsoft 365, som också förlitar sig på Azure AD för identitets-och katalog tjänster. Förfallodatum för lösenord är den enda delen av principen som kan ändras.

> [!NOTE]
> Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla. Mer information om katalogsynkronisering finns i Anslut [AD med Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Så här kontrollerar du förfalloprincipen för ett lösenord

Mer information om kommandot Get-AzureADUser i AzureAD-modulen finns i referensartikeln [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Kör något av följande kommandon:

- Om du vill se om en enskild användares lösenord aldrig har upphört att gälla kör du följande cmdlet med hjälp av UPN *(till exempel user@contoso.onmicrosoft.com)* eller användar-ID:t för den användare som du vill kontrollera:

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

- Om du vill **se inställningen Lösenord upphör aldrig** att gälla för alla användare kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Så här hämtar du en rapport över alla användare med PasswordNeverExpires i Html på den aktuella användarens skrivbord med  **namnReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Så här hämtar du en rapport över alla användare med PasswordNeverExpires i CSV på den aktuella användarens skrivbord med **namnReportPasswordNeverExpires.csv**

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

- Om du vill att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Användarkonton som konfigurerats med `-PasswordPolicies DisablePasswordExpiration` parametern åldras fortfarande baserat på `pwdLastSet` attributet. Baserat på attributet kräver alla lösenord som har en pwdLastSet som är äldre än 90 dagar att användaren ändrar dem nästa gång de loggar in om du `pwdLastSet` `-PasswordPolicies None` ändrar förfallodatumet till. Den här ändringen kan påverka ett stort antal användare.

### <a name="set-a-password-to-expire"></a>Ange att ett lösenord ska upphöra att gälla

Kör något av följande kommandon:

- Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens användar-ID:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Relaterat innehåll

[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)

[Återställ lösenord](../add-users/reset-passwords.md) (artikel)