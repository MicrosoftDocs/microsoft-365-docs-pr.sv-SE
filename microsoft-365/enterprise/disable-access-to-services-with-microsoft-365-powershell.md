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
description: I den här artikeln får du lära dig hur du använder PowerShell för att inaktivera åtkomst Microsoft 365 tjänster för användare.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694542"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

När ett Microsoft 365-konto tilldelas en licens från en licensplan blir Microsoft 365 tillgängliga för användaren från den licensen. Du kan dock styra vilka Microsoft 365 som användaren kan komma åt. Även om licensen till exempel ger åtkomst till SharePoint Online-tjänsten kan du inaktivera åtkomsten till den. Du kan använda PowerShell för att inaktivera åtkomst till valbara antal tjänster för en specifik licensplan för:

- Ett enskilt konto.
- En grupp konton.
- Alla konton i organisationen.

>[!Note]
>Det finns Microsoft 365 tjänstberoenden som kan hindra dig från att inaktivera en viss tjänst när andra tjänster är beroende av den.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Använd sedan det här kommandot för att visa dina tillgängliga licensplaner, så kallade AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

Mer information finns i [Visa licenser och tjänster med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)
    
Information om hur du visar resultatet av procedurerna före och efter i det här avsnittet finns i [Visa kontolicens och tjänstinformation med PowerShell.](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet. Med skriptet kan du visa och inaktivera tjänster i din organisation Microsoft 365, inklusive Sway. Mer information finns i Inaktivera [åtkomst till Sway med PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Inaktivera specifika Microsoft 365 för specifika användare för ett visst licensabonnemang
  
Gör så här om du vill inaktivera Microsoft 365 specifika användartjänster för en specifik licensplan:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Steg 1: Identifiera de oönskade tjänsterna i licensplanen genom att använda följande syntax:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

I följande exempel skapas ett **LicenseOptions-objekt** som inaktiverar Office och SharePoint Online-tjänsterna i licensplanen med namnet `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Steg 2: Använd **objektet LicenseOptions** från steg 1 för en eller flera användare.
    
Om du vill skapa ett nytt konto där tjänsterna är inaktiverade använder du följande syntax:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

I följande exempel skapas ett nytt konto för Allie Bellew som tilldelar licensen och inaktiverar tjänsterna som beskrivs i steg 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Mer information om hur du skapar användarkonton i PowerShell för Microsoft 365 finns i [Skapa användarkonton med PowerShell.](create-user-accounts-with-microsoft-365-powershell.md)
    
Om du vill inaktivera tjänsterna för en befintlig licensierad användare använder du följande syntax:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

Det här exemplet inaktiverar tjänsterna för användaren BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Om du vill inaktivera tjänsterna som beskrivs i steg 1 för alla befintliga licensierade användare anger du namnet på ditt Microsoft 365-abonnemang från visningen av **Get-MsolAccountSku-cmdleten** (till exempel **litwareinc:ENTERPRISEPACK)** och kör sedan följande kommandon:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Om du använder **cmdlet:en Get-MsolUser** utan att använda parametern _Alla_ returneras bara de första 500 användarkontona.

Om du vill inaktivera tjänsterna för en grupp av befintliga användare använder du någon av följande metoder för att identifiera användarna:
    
**Metod 1. Filtrera kontona baserat på ett befintligt kontoattribut** 

Det gör du genom att använda följande syntax:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

I följande exempel inaktiveras tjänsterna för användare i försäljningsavdelningen i USA.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Metod 2: Använd en lista med specifika konton** 

Gör så här:
    
1. Skapa en textfil som innehåller ett konto på varje rad så här:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   I det här exemplet är textfilen C: \\ Mina dokument \\Accounts.txt.
    
2. Kör följande kommando:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Om du vill inaktivera åtkomst till tjänster för flera licensabonnemang upprepar du anvisningarna ovan för varje licensplan och ser till att:

- Användarkontona har tilldelats licensplanen.
- De tjänster som du inaktiverar finns tillgängliga i licensplanen.

Om du Microsoft 365 tjänster för användare medan du tilldelar dem till en licensplan kan du gå till Inaktivera åtkomst till tjänster medan [du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Tilldela alla tjänster i en licensplan till ett användarkonto

För användarkonton som har inaktiverat tjänster kan du aktivera alla tjänster för en specifik licensplan med följande kommandon:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Relaterat ämne

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
