---
title: Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: I den här artikeln lär du dig hur du använder PowerShell för att inaktivera åtkomst till Microsoft 365-tjänster för användare.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694542"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

När ett Microsoft 365-konto tilldelas en licens från en licens plan blir Microsoft 365-tjänsterna tillgängliga för användaren från den licensen. Men du kan kontrol lera vilka Microsoft 365-tjänster som användaren har åtkomst till. Till exempel om licensen tillåter åtkomst till SharePoint Online-tjänsten kan du inaktivera åtkomsten till den. Du kan använda PowerShell för att inaktivera åtkomst till ett obegränsat antal tjänster för ett specifikt licens abonnemang för:

- Ett enskilt konto.
- En grupp med konton.
- Alla konton i organisationen.

>[!Note]
>Det finns Microsoft 365-tjänst beroenden som kan förhindra att du inaktiverar en angiven tjänst när andra tjänster är beroende av den.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Använd sedan det här kommandot för att visa de tillgängliga licens planerna, även kallade AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Mer information finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).
    
Information om hur du visar de föregående och efter resultaten av procedurerna i det här avsnittet finns i [Visa konto licens och tjänste Detaljer med PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).
    
Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet. Du kan också använda skript för att visa och inaktivera tjänster i Microsoft 365-organisationen, inklusive Sway. Mer information finns i [inaktivera åtkomst till Sway med PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Inaktivera specifika Microsoft 365-tjänster för specifika användare för en viss licens plan
  
Gör så här om du vill inaktivera en specifik uppsättning Microsoft 365-tjänster för användare för en viss licens plan:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Steg 1: identifiera de oönskade tjänsterna i licensierings planen genom att använda följande syntax:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

I följande exempel skapas ett **LicenseOptions** -objekt som inaktiverar Office-och SharePoint Online-tjänsterna i licensierings planen `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Steg 2: använda **LicenseOptions** -objektet från steg 1 på en eller flera användare.
    
Använd följande syntax för att skapa ett nytt konto som har tjänsterna inaktiverade:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

I följande exempel skapas ett nytt konto för Diana Bergqvist som tilldelar licensen och inaktiverar tjänsterna som beskrivs i steg 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Mer information om hur du skapar användar konton i PowerShell för Microsoft 365 finns i [skapa användar konton med PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Om du vill inaktivera tjänsterna för en befintlig licensierad användare använder du följande syntax:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

I det här exemplet inaktive ras tjänsterna för användaren BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Om du vill inaktivera tjänsterna som beskrivs i steg 1 för alla befintliga licensierade användare anger du namnet på ditt Microsoft 365-abonnemang från visningen av cmdleten **Get-MsolAccountSku** (till exempel **licens planen litwareinc: ENTERPRISEPACK**) och kör följande kommandon:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Om du använder cmdleten **Get-MsolUser** utan att använda parametern _alla_ returneras först de första 500-kontona.

Om du vill inaktivera tjänsterna för en grupp befintliga användare kan du använda någon av följande metoder för att identifiera användarna:
    
**Metod 1. Filtrera konton baserat på ett befintligt konto-attribut** 

Använd följande syntax:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

I följande exempel inaktive ras tjänsterna för användare på försäljnings avdelningen i USA.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Metod 2: använda en lista med specifika konton** 

Gör så här:
    
1. Skapa en textfil som innehåller ett konto på varje rad, så här:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   I det här exemplet är text filen C: \\ Mina dokument \\Accounts.txt.
    
2. Kör följande kommando:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Om du vill inaktivera åtkomst till tjänster för flera licensierings planer upprepar du ovanstående instruktioner för varje licens plan, som säkerställer att:

- Användar kontona har tilldelats licens planen.
- Tjänsterna som ska inaktive ras är tillgängliga i licens planen.

Information om hur du inaktiverar Microsoft 365-tjänster för användare när du tilldelar dem till en licens plan finns i [inaktivera åtkomst till tjänster när du tilldelar användar licenser](disable-access-to-services-while-assigning-user-licenses.md).

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Tilldela alla tjänster i en licens plan till ett användar konto

För användar konton som har inaktiverat tjänster kan du aktivera alla tjänster för ett specifikt licens abonnemang med dessa kommandon:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Närliggande ämne

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
