---
title: Konfigurera Microsoft 365 användarkontoegenskaper med PowerShell
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
description: Använd PowerShell för Microsoft 365 att konfigurera egenskaper för enskilda eller flera användarkonton i Microsoft 365 klientorganisationen.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911090"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Konfigurera Microsoft 365 användarkontoegenskaper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda Microsoft 365 för att konfigurera egenskaper för användarkontona i klientorganisationen Microsoft 365 klientorganisationen. I PowerShell kan du göra detta, plus en del andra saker du inte kan göra i administrationscentret.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Om du vill konfigurera egenskaper för användarkonton i Azure Active Directory PowerShell för Graph-modulen använder du cmdleten [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) och anger vilka egenskaper du vill ange eller ändra.

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Ändra egenskaper för ett visst användarkonto

Du identifierar kontot med parametern *-ObjectID och* anger eller ändrar specifika egenskaper med hjälp av ytterligare parametrar. Här är en lista över de vanligaste parametrarna:
  
- -Avdelning \<department name> " "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Efternamn " \<user last name> "
    
- -Mobil " \<mobile phone number> "
    
- -JobTitle \<job title> " "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -Ort \<city name> " "
    
- -State " \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber \<office phone number> " "
    
- -UsageLocation " \<2-character country or region code> "
    
    Det här är lands- eller regionskoden enligt ISO 3166-1 alfa-2 (A2).
    
Fler parametrar finns i [Set-AzureADUser.](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>Innan du kan tilldela licenser till ett användarkonto måste du tilldela en användningsplats.
>

Om du vill visa användarkontons huvudnamn kör du följande kommando.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Det här kommandot instruerar PowerShell att:
  
1. Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).
    
1. Sortera listan med användarhuvudnamn i alfabetisk **ordning (Sortera UserPrincipalName)** och skicka den till nästa kommando ( **|** ).
    
1. Visa bara egenskapen User Principal Name för varje konto (**Select UserPrincipalName**).

1. Visa dem en skärmbild i taget **(Mer).**
    
Kör följande kommandon om du vill visa användarkontons huvudnamn baserat på dess visningsnamn (för- och efternamn). Fyll i *$userName* variabeln och ta bort \< and > tecknen:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas Användarkontots huvudnamn för användarkontot som har visningsnamnet *Caleb Hass*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Genom att *använda $upn* variabel kan du göra ändringar i enskilda konton baserat på deras visningsnamn. Här är ett exempel som anger *Belinda Newman's* användningsplats till Frankrike. Men det anger hennes visningsnamn i stället för hennes huvudnamn:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändra egenskaper för alla användarkonton

Om du vill ändra egenskaper för alla användare kan du använda en kombination av cmdletarna **Get-AzureADUser** och **Set-AzureADUser.** I följande exempel ändras användningsplatsen för alla användare till *Frankrike:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell att:
  
1. Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).
    
1. Ställ in användarens plats på Frankrike **(Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändra egenskaper för en viss uppsättning användarkonton

Om du vill ändra egenskaper för en viss uppsättning användarkonton kan du använda en kombination av cmdlet:arna **Get-AzureADUser**, **Where** och **Set-AzureADUser.** I följande exempel ändras användningsplatsen för alla användare på redovisningsavdelningen till *Frankrike:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell att:
  
1. Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).
    
1.  Hitta alla användarkonton som  har avdelningsegenskapen inställd på "Redovisning" (**Där {$_. Avdelning -eq "Accounting"} )** och skicka informationen till nästa kommando ( **|** ).
    
1. Ställ in användarens plats på Frankrike **(Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Om du vill konfigurera egenskaper för användarkonton med Microsoft Azure Active Directory-modulen för Windows PowerShell, använder du cmdleten **Set-MsolUser** och anger egenskaper som du vill ange eller ändra.

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet. Kör dessa cmdlets från Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Ändra egenskaper för ett visst användarkonto

Om du vill konfigurera egenskaper för ett specifikt användarkonto använder du cmdleten [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) och anger egenskaper som du vill ange eller ändra. 

Du identifierar kontot med *parametern -UserPrincipalName och* anger eller ändrar specifika egenskaper med hjälp av ytterligare parametrar. Här är en lista över de vanligaste parametrarna.
  
- -Ort \<city name> " "
    
- -Country " \<country name> "
    
- -Avdelning \<department name> " "
    
- -DisplayName " \<full user name> "
    
- -Fax " \<fax number> "
    
- -Förnamn " \<user first name> "
    
- -Efternamn " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber \<office phone number> " "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Titel " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Det här är lands- eller regionskoden enligt ISO 3166-1 alfa-2 (A2).
    
Fler parametrar finns i [Set-MsolUser.](/previous-versions/azure/dn194136(v=azure.100))

Om du vill visa användarhuvudnamn för alla dina användare kör du följande kommando:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Det här kommandot instruerar PowerShell att:
  
1. Få all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).
    
1. Sortera listan med användarhuvudnamn i alfabetisk **ordning (Sortera UserPrincipalName)** och skicka den till nästa kommando ( **|** ).
    
1. Visa bara egenskapen User Principal Name för varje konto (**Select UserPrincipalName**).
    
1. Visa dem en skärmbild i taget **(Mer).**
    
Kör följande kommandon om du vill visa användarkontons huvudnamn baserat på dess visningsnamn (för- och efternamn). Fyll i *$userName* och ta bort \< and > tecknen.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

I det här exemplet visas användarens huvudnamn för användaren Caleb Beskrivning:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Genom att *använda $upn* variabel kan du göra ändringar i enskilda konton baserat på deras visningsnamn. Här är ett exempel som *anger Belinda Newman:s* användningsplats till *Frankrike,* men anger hennes visningsnamn i stället för hennes användarhuvudnamn:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Ändra egenskaper för alla användarkonton

Om du vill ändra egenskaper för alla användare använder du en kombination av cmdlet:arna **Get-MsolUser** **och Set-MsolUser.** I följande exempel ändras användningsplatsen för alla användare till *Frankrike:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell att:
  
1. Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).
    
1. Ställ in användarens plats på Frankrike **(Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Ändra egenskaper för en viss uppsättning användarkonton

Om du vill ändra egenskaper för en viss uppsättning användarkonton kan du använda en kombination av cmdlet:arna **Get-MsolUser**, **Where** och **Set-MsolUser.** I följande exempel ändras användningsplatsen för alla användare på redovisningsavdelningen till *Frankrike:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Det här kommandot instruerar PowerShell att:
  
1. Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).
    
1. Hitta alla användarkonton där *Avdelning-egenskapen* är inställd på "Redovisning" (**Där {$_. Avdelning -eq "Accounting"}**) och skicka informationen till nästa kommando ( **|** ).
    
1. Ställ in användarens plats på Frankrike **(Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)