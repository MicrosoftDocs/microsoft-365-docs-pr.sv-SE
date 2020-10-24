---
title: Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Använd PowerShell för Microsoft 365 för att konfigurera egenskaper för enskilda eller flera användar konton i din Microsoft 365-klient organisation.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754334"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurera egenskaper för Microsoft 365-användarkonto med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda administrations centret för Microsoft 365 för att konfigurera egenskaper för användar konton för din Microsoft 365-klient organisation. I PowerShell kan du också göra det och andra saker du inte kan göra i administrations centret.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Om du vill konfigurera egenskaper för användar konton i Azure Active Directory PowerShell för Graph kan du använda cmdleten [**set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) och ange egenskaper för att ställa in eller ändra.

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Ändra egenskaper för ett visst användar konto

Du identifierar kontot med parametern *-ObjectID* och anger eller ändrar specifika egenskaper genom att använda ytterligare parametrar. Här är en lista över de vanligaste parametrarna:
  
- -Avdelning " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Efter namn " \<user last name> "
    
- -Mobil " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -Ort " \<city name> "
    
- -State " \<state name> "
    
- -Post nummer " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.
    
Fler parametrar finns i [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Innan du kan tilldela licenser till ett användar konto måste du tilldela en användnings plats.
>

Om du vill visa användar kontots huvud namn kör du följande kommando.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).
    
1. Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).
    
1. Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).

1. Visa dem en skärm bild i taget (**mer**).
    
Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) kör du följande kommandon. Fyll i *$username* variabel och ta bort \< and > tecknen:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas användarens huvud namn för det användar konto som har visnings namnet *Caleb brädor*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Genom att använda en *$UPN* variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn. Här är ett exempel som anger *Belinda Newman*användnings plats för Frankrike. Men det anger hennes visnings namn i stället för användarens huvud namn:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändra egenskaper för alla användar konton

Om du vill ändra egenskaper för alla användare kan du använda en kombination av cmdletarna **Get-AzureADUser** och **set-AzureADUser** . Följande exempel ändrar användnings platsen för alla användare till *Frankrike*:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell till att:
  
1. Hämta all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).
    
1. Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändra egenskaper för en viss uppsättning användar konton

Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda en kombination av cmdletarna **Get-AzureADUser**, **WHERE**och **set-AzureADUser** . Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till *Frankrike*:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).
    
1.  Hitta alla användar konton som har egenskapen *avdelning* inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).
    
1. Ange användarens plats till Frankrike (**set-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Om du vill konfigurera egenskaper för användar konton med Microsoft Azure Active Directory-modulen för Windows PowerShell kan du använda cmdleten **set-MsolUser** och ange egenskaper för att ställa in eller ändra.

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* . Kör dessa cmdletar från Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Ändra egenskaper för ett visst användar konto

Om du vill konfigurera egenskaper för ett specifikt användar konto använder du cmdleten [**set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaperna som ska anges eller ändras. 

Du identifierar kontot med parametern *-userPrincipalName* och anger eller ändrar specifika egenskaper genom att använda ytterligare parametrar. Här är en lista över de vanligaste parametrarna.
  
- -Ort " \<city name> "
    
- -Country " \<country name> "
    
- -Avdelning " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -Telefonnummer " \<office phone number> "
    
- -Post nummer " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Rubrik " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Det här är ISO 3166-1 alpha-2 (a2) lands-eller rikt nummer.
    
Fler parametrar finns i [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Om du vill visa användarens huvud namn för alla användare kör du följande kommando:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information för användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).
    
1. Sortera listan med UPN-namn alfabetiskt (**Sortera userPrincipalName**) och skicka det till nästa kommando ( **|** ).
    
1. Visa bara egenskapen användarens huvud namn för varje konto (**Välj userPrincipalName**).
    
1. Visa dem en skärm bild i taget (**mer**).
    
Om du vill visa UPN-namnet för ett konto baserat på dess visnings namn (för-och efter namn) kör du följande kommandon. Fyll i *$username* variabel och ta bort \< and > tecknen.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas användarens huvud namn för den användare som heter Caleb brädor:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Genom att använda en *$UPN* variabel kan du göra ändringar i enskilda konton baserat på deras visnings namn. Här är ett exempel som anger *Belinda Newman*användnings plats för *Frankrike*, men som anger hennes visnings namn i stället för användarens huvud namn:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändra egenskaper för alla användar konton

Om du vill ändra egenskaper för alla användare använder du en kombination av cmdletarna **Get-MsolUser** och **set-MsolUser** . Följande exempel ändrar användnings platsen för alla användare till *Frankrike*:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information för användar kontona (**Get-MsolUser**) och skicka den till nästa kommando ( **|** ).
    
1. Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändra egenskaper för en viss uppsättning användar konton

Om du vill ändra egenskaper för en viss uppsättning användar konton kan du använda en kombination av cmdletarna **Get-MsolUser**, **WHERE**och **set-MsolUser** . Följande exempel ändrar användnings platsen för alla användare i ekonomi avdelningen till *Frankrike*:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information för användar kontona (**Get-MsolUser**) och skicka den till nästa kommando ( **|** ).
    
1. Hitta alla användar konton som har egenskapen *avdelning* inställd på "redovisning" (**där {$ _. Department-EQ "Accounting"}**) och skicka den resulterande informationen till nästa kommando ( **|** ).
    
1. Ange användarens plats till Frankrike (**set-MsolUser-UsageLocation "fr"**).

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
