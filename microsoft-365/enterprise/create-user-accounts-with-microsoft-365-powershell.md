---
title: Skapa Microsoft 365-användarkonton med PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Hur du använder PowerShell för att skapa enskilda eller flera Microsoft 365-användarkonton.
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754216"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Skapa Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 för att effektivt skapa användar konton, inklusive flera konton.

När du skapar användar konton i PowerShell behövs alltid vissa konto egenskaper. Andra egenskaper är inte obligatoriska men är viktiga. Se tabellen nedan.
  
|**Egenskaps namn**|**Obligatorisk**|**Beskrivning**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Ja  <br/> |Det här är visnings namnet som används i Microsoft 365-tjänster. Till exempel *Caleb brädor*. <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Det här är det konto namn som används för att logga in på Microsoft 365-tjänster. Till exempel *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**Förnamn** <br/> |Nej  <br/> ||
|**Efter namn** <br/> |Nej  <br/> ||
|**LicenseAssignment** <br/> |Nej  <br/> |Det här är licens planen (kallas även licens planen eller SKU) som en tillgänglig licens har tilldelats till. Licensen definierar vilka Microsoft 365-tjänster som är tillgängliga för kontot. Du behöver inte tilldela en licens till en användare när du skapar kontot, men kontot måste ha en licens för åtkomst till Microsoft 365-tjänster. Du har 30 dagar på dig att licensiera användar kontot när du har skapat det. |
|**Lösenord** <br/> |Nej  <br/> | Om du inte anger något lösen ord tilldelas användar kontot ett slumpmässigt lösen ord och lösen ordet visas i resultatet av kommandot. Om du anger ett lösen ord måste det vara 8 till 16 ASCII-tecken av följande typer: gemener, versaler, siffror och symboler.<br/> |
|**UsageLocation** <br/> |Nej  <br/> |Det här är en giltig ISO 3166-1 alpha-2-landskod. *Till exempel för USA* och *fr* för Frankrike. Det är viktigt att ange det här värdet eftersom vissa Microsoft 365-tjänster inte är tillgängliga i vissa länder. Du kan inte tilldela en licens till ett användar konto om inte kontot har det här värdet konfigurerat. Mer information finns i [om licens begränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).<br/> |

>[!Note]
>[Lär dig hur du skapar användar konton](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) med administrations centret för Microsoft 365.
> 
> En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

När du har anslutit kan du använda följande syntax för att skapa ett enskilt konto:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

I det här exemplet skapas ett konto för användarnas *Caleb-brädor*:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Skapa ett enskilt användar konto

Använd följande syntax för att skapa ett enskilt konto:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *MSOL* i sitt namn. Kör dessa cmdletar från Windows PowerShell.
>

Använd det här kommandot för att lista de tillgängliga namnen på licens planerna:

````powershell
Get-MsolAccountSku
````

I det här exemplet skapas ett konto för användarnas *Caleb-brädor*och tilldelas en licens från `contoso:ENTERPRISEPACK` licens planen (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Skapa flera användar konton

1. Skapa en CSV-fil (kommaseparerade värden) som innehåller den användar konto information som krävs. Till exempel:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >Kolumn namnen och deras ordning i den första raden i CSV-filen är valfria. Men kontrol lera att ordningen på data i resten av filen matchar ordningen på kolumn namnen. Och Använd kolumn namnen för parameter värden i PowerShell för Microsoft 365-kommandot.
    
2. Använd följande syntax:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   I det här exemplet skapas användar konton från filen *c:\mina Documents\NewAccounts.csv* och resultatet loggas i en fil med namnet *c:\Mina Documents\NewAccountResults.csv*.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Granska utdatafilen för att se resultatet. Vi angav inte lösen ord, så de slumpmässiga lösen ord som Microsoft 365 genererade visas i utdatafilen.
    
## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
