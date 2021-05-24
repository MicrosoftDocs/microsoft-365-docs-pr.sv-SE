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
description: Logga in på ditt Microsoft 365 för att ange att vissa lösenord aldrig ska upphöra att gälla genom att använda Windows PowerShell.
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635564"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Ange att en enskild användares lösenord aldrig ska förfalla

I den här artikeln förklaras hur du anger ett lösenord så att en enskild användare inte upphör att gälla. Du måste utföra de här stegen med PowerShell.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../../business-video/admin-center-overview.md). 

Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.

En global administratör för en Microsoft-molntjänst kan använda [PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) för Azure Active Directory för Graph ange att lösenord inte ska upphöra att gälla för specifika användare. Du kan [](/powershell/module/Azuread) också använda AzureAD-cmdlets för att ta bort konfigurationen med aldrig upphör att gälla eller för att se vilka användarlösenord som är inställda på att aldrig upphöra.

Den här guiden gäller för andra leverantörer, till exempel Intune och Microsoft 365, som också förlitar sig på Azure AD för identitet och katalogtjänster. Lösenordsförfallotid är den enda del av principen som kan ändras.

> [!NOTE]
> Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras så att de inte upphör att gälla. Mer information om katalogsynkronisering finns i [Anslut AD med Azure AD.](/azure/active-directory/connect/active-directory-aadconnect)

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Så här kontrollerar du förfalloprincipen för ett lösenord

Mer information om kommandot Get-AzureADUser AzureAD-modulen finns i referensartikeln [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)

Kör något av följande kommandon:

- Kör följande cmdlet med UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID:t för den användare du vill kontrollera för att se om en enskild användares lösenord är inställt på att aldrig upphöra att gälla:

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

- Om du vill **se inställningen för Lösenord upphör** aldrig att gälla för alla användare kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- För att få en rapport över alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med  **namnReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- För att få en rapport över alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med **ReportPasswordNeverExpires.csv**

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

- Om du vill ange att lösenorden för alla användare i en organisation aldrig ska upphöra att gälla kör du följande cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Användarkonton som konfigurerats med `-PasswordPolicies DisablePasswordExpiration` parameterns ålder baserat på `pwdLastSet` attributet. Baserat på attributet måste användaren ändra alla lösenord som har en pwdLastSet som är äldre än `pwdLastSet` 90 dagar om du ändrar förfallodatumet till . `-PasswordPolicies None` Den här ändringen kan påverka ett stort antal användare.

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

[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)\
[Återställ lösenord](../add-users/reset-passwords.md) (artikel)\
[Ange förfalloprincip för lösenord för din organisation](../manage/set-password-expiration-policy.md) (artikel)