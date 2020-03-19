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
# <a name="set-an-individual-users-password-to-never-expire"></a>Ange att en enskild användares lösenord aldrig ska förfalla

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Ange förfalloprincip för lösenord i organisationen

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">sekretesssidan</a> **Inställningar** \> & sekretess i administrationscentret.
2. Bredvid **Lösenordsprincip** väljer du **Redigera**. 
3. Om lösenord en satt att aldrig upphöra att gälla ställer du in växlingsknappen på **Av**. Du får möjlighet att ange antalet dagar tills lösenorden upphör att gälla. 


## <a name="set-the-password-expiration-policy-for-individual-users"></a>Ange principen för förfallodatum för lösenord för enskilda användare 

En global administratör för en Microsoft-molntjänst kan använda Microsoft Azure AD Module för Windows PowerShell för att ange att lösenord inte ska upphöra att gälla för specifika användare. Du kan också använda Windows PowerShell-cmdlets för att ta bort konfigurationen som aldrig upphör att gälla eller för att se vilka användarlösenord som aldrig upphör att gälla. 

Den här guiden gäller för andra leverantörer, till exempel Intune och Office 365, som också är beroende av Azure AD för identitets- och katalogtjänster. Förfallodatum för lösenord är den enda delen av principen som kan ändras.

> [!NOTE]
> Endast lösenord för användarkonton som inte synkroniseras via katalogsynkronisering kan konfigureras för att inte upphöra att gälla. Mer information om katalogsynkronisering finns i [Anslut AD med Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).


### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Så här kontrollerar du förfalloprincipen för ett lösenord

* Kör något av följande kommandon:

   * Om du vill se om en enskild användares lösenord är inställt på att aldrig upphöra att gälla kör du följande cmdlet med hjälp av UPN (till exempel *user@contoso.onmicrosoft.com)* eller användar-ID för den användare som du vill kontrollera:
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
Exempel:
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * Om du vill se **inställningen Lösenord upphör aldrig att gälla** för alla användare kör du följande cmdlet: 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* Så här hämtar du en rapport över alla användare med PasswordNeverExpires i Html på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.html**


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* Så här hämtar du en rapport över alla användare med PasswordNeverExpires i CSV på skrivbordet för den aktuella användaren med namnet **ReportPasswordNeverExpires.csv**


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a>Ange att ett lösenord ska upphöra att gälla

Kör något av följande kommandon:

   * Om du vill ange lösenordet för en användare så att lösenordet upphör att gälla kör du följande cmdlet med hjälp av UPN eller användarens ID:

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * Om du vill ange lösenord för alla användare i organisationen så att de upphör att gälla använder du följande cmdlet:

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a>Ange att ett lösenord aldrig ska upphöra att gälla

Kör något av följande kommandon:

   * Om du vill att lösenordet för en användare aldrig ska upphöra att gälla kör du följande cmdlet med hjälp av UPN eller användarens id:n för att ställa in lösenordet för en användare som aldrig upphör att gälla: 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * Om du vill ange att lösenorden för alla användare i en organisation aldrig upphör att gälla kör du följande cmdlet: 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > Lösenord som `-PasswordPolicies DisablePasswordExpiration` fortfarande är ålderbaserade på attributet. `pwdLastSet` Om du anger att användarlösenorden aldrig upphör att gälla och sedan går 90 + dagar, upphör lösenorden att gälla. Baserat på `pwdLastSet` attributet, om du `-PasswordPolicies None`ändrar utgången till `pwdLastSet` , kräver alla lösenord som har en äldre än 90 dagar att användaren ändrar dem nästa gång de loggar in. Den här ändringen kan påverka ett stort antal användare. 
